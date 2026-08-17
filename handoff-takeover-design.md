# Design Foundation — Department Handoff & Human Takeover Bridge

**Status:** Design draft for discussion (no code changed yet)
**Date:** 2026-07-02
**Companion docs:** `CODEBASE-ANALYSIS.md`, `TSO-PIPELINE-OPTIMIZATION-PROPOSAL.md`

## Decisions locked (from design discussion)

| Decision | Choice | Implication |
|----------|--------|-------------|
| Where agents work | **Web console in the dashboard** | Build a live agent inbox in the existing React app; reuse OIDC auth + message-thread renderer |
| Model: relay vs takeover | **Option B — human takeover** (bot steps aside) | No LLM relay; agent messages go out verbatim. Lower risk, esp. for complaints |
| n8n ownership | **Team owns n8n** | The inbound routing bridge + outbound agent-send are implemented in n8n |
| First increment | **Handoff/takeover bridge first** | This doc scopes that; full QA-all-history is a natural byproduct (see §8) |

**Guiding example (used throughout):** Customer complains about their car → Tasia classifies it as a complaint → hands off to the **Service / CRC** department → a Service agent **claims** the conversation in the console and **takes over**; Tasia goes silent until handback. The conversation can later be **transferred** to another department (e.g. Sales for a trade-in) — your "re-approach" requirement.

---

## Contents

| § | Section | Plane |
|---|---------|-------|
| 1 | The core problem restated | — |
| 2 | Conversation ownership — the state machine (the bridge) | Governance |
| 3 | Data model | All |
| 4 | The n8n inbound bridge | Routing |
| 5 | Backend API surface | Backend |
| 6 | Agent console | Frontend |
| 7 | Constraint: WhatsApp 24-hour window | Channel |
| 8 | QA/QC — all conversations | Governance |
| 9 | Suggested build order | — |
| 10 | Open questions | — |
| 11 | Confirmed scope (+ 11.1 per-dept diversification) | — |
| 12 | Response SLA & escalation (+ 12.7 ML tiering) | Governance |
| 13 | Unified message store (WhatsApp-style transcript) | Content |

**Build order, deploy steps, and status live in `GO-LIVE-RUNBOOK.md`; exact n8n node settings in `N8N-NODE-STEPS.md`.**

## Entity-relationship overview

Four entities, two planes. **Governance** = *how* a conversation is handled; **Content** = *what was said*.

```
                         ┌──────────────────────────────┐
                         │        conversation          │  GOVERNANCE (current state)
                         │  mode · owner_role · owner    │  1 row per conversation
                         │  branch_code · SLA fields     │  ← n8n gate + console inbox read this
                         └───────────┬──────────────────┘
             1─────────────────┐     │ 1                    1
             │ (audit)          │     │                      │ (transcript)
             ▼ N                │     ▼ N                    ▼ N
   ┌────────────────────┐      │  ┌───────────────────┐   ┌──────────────────────┐
   │ conversation_event │      │  │     message       │   │   chat_histories     │
   │ claim/transfer/    │      │  │ every turn, every │   │  LLM memory (n8n's,  │
   │ handback/sla_esc   │      │  │ author (cust/ai/  │   │  kept as-is)         │
   │ append-only        │      │  │ agent) · WA-style │   │  append-only         │
   └────────────────────┘      │  └───────────────────┘   └──────────────────────┘
        GOVERNANCE journal      │       CONTENT (source of truth for QA + UI)
                                │
                     chatbot_summary (attribute: lead/inquiry classification)
```

- `conversation` links to everything via `id` / `session_id`.
- `message` is the **new** source-of-truth transcript (§13); `chat_histories` stays as the agent's memory.
- One-liner: **`conversation` governs it · `conversation_event` records how it was governed · `message` is what was said · `chat_histories` is what the AI remembers.**

---

## 1. The core problem restated

Today a "dispatch" is a **one-way notification** into a staff WhatsApp group. There is:
- **No conversation ownership state** — nothing records that Service now owns this chat, so nothing tells the bot to stop replying.
- **No bridge for a human to reply to the customer** through the same WhatsApp number.
- **No cross-department transfer / re-approach** path.

The fix is to make a **conversation** a first-class object with an **owner** and a **mode**, and to insert a **routing gate** in n8n that respects that mode. That gate *is* the missing bridge.

---

## 2. Conversation ownership — the state machine (the bridge)

```
                        ┌─────────┐
   customer message ───►│   BOT   │  Tasia answers (today's behavior)
                        └────┬────┘
             Tasia dispatch  │ (complaint / lead / inquiry + consent)
                             ▼
                    ┌──────────────────┐
                    │ PENDING_HANDOFF  │  bot silent; "sedang kami hubungkan…"
                    └────────┬─────────┘  claimable item shown to dept queue
              agent claims   │                        │ timeout / no claim
                             ▼                        ▼
                        ┌─────────┐            (SLA escalation:
   customer message ───►│  HUMAN  │◄──┐         backup PIC / branch head)
   agent reply ────────►│ (owned) │   │ transfer (re-route to another dept,
                        └────┬────┘   │  keeps history + audit trail)
              agent resolves │        └──────────────┘
                             ▼
                     ┌──────────────┐   handback
                     │  RESOLVED    │──────────────► BOT   (or CLOSED)
                     └──────────────┘
```

**Modes** (the single new field the whole bridge hinges on):
- `BOT` — Tasia handles (default, unchanged).
- `PENDING_HANDOFF` — dispatched, awaiting an agent to claim. Bot does not answer.
- `HUMAN` — an agent owns it; **bot is fully off**.
- `RESOLVED` / `CLOSED` — done; optionally auto-handback to `BOT`.

**Transitions** map to actions: `dispatch`, `claim`, `transfer`, `resolve`, `handback`, `sla_escalate`.

---

## 3. Data model

Anchor on the identifiers already in use: `chat_histories.session_id`, and `chatbot_summary(phone_no, conversation_id)` where the backend already resolves `session_id = phone_no || '_' || conversation_id` (`admin/routes.py:311`).

### 3.1 New: `conversation` (the registry + ownership)
One row per conversation — created for **every** conversation, not only dispatched ones (this is what unlocks QA-all-history in §8).

| Column | Type | Notes |
|--------|------|-------|
| `id` | uuid pk | |
| `conversation_id` | varchar | WhatsApp conversation id (matches `chatbot_summary.conversation_id`) |
| `phone_no` | varchar | customer |
| `session_id` | varchar | = `phone_no || '_' || conversation_id`; links to `chat_histories` |
| `mode` | varchar | `BOT / PENDING_HANDOFF / HUMAN / RESOLVED / CLOSED` |
| `owner_role` | varchar | `sa / crc / sales / bp_advisor / partman / trade_in` (nullable) |
| `owner_agent_id` | uuid | claimed agent `user_id` (nullable) |
| `branch_code` | varchar | routing target |
| `handoff_at`, `claimed_at`, `resolved_at` | timestamp | lifecycle |
| `claimed_by`, `resolved_by` | varchar | audit |
| `last_customer_msg_at` | timestamp | **drives the WhatsApp 24h window** (§7) |
| `created_at`, `updated_at` | timestamp | |

> Alternative: extend `customer_sessions` (which already has `phone_number`, `branch_code`, `status`). A dedicated `conversation` table is cleaner because `customer_sessions.status` is only `active/expired` and the keys don't line up with `chatbot_summary`. Recommendation: **new table**, backfill-friendly.

### 3.2 New: `conversation_event` (append-only audit / transfer trail)
Every state change is a row — essential for QA and for "re-approach" history.

| Column | Type | Notes |
|--------|------|-------|
| `id` | bigserial pk | |
| `conversation_id` | uuid fk → conversation | |
| `event_type` | varchar | `dispatch / claim / transfer / resolve / handback / sla_escalate / message_in / message_out` |
| `from_role`, `to_role` | varchar | for transfers |
| `actor` | varchar | agent user_id or `bot` / `system` |
| `payload` | jsonb | summary, next_action, note |
| `created_at` | timestamp | |

### 3.3 Reused as-is
- `chat_histories` — raw messages (JSONB), keyed by `session_id`. **Becomes the single source for the full thread.**
- `chatbot_summary` — becomes an **attribute** of a conversation (the lead/inquiry classification + next_action), not the entry point.
- `master_branch_route` / `master_branch_pic` — unchanged; still resolve branch+role → WA group / agent.
- `inbox_kafka` — natural backbone for reliable handoff eventing if we want async.

---

## 4. The n8n inbound bridge (highest-priority change)

Insert **one gate** at the top of the inbound flow, before the LLM node:

```
inbound WA message
      │
      ▼
 look up conversation.mode  (GET /conversations/by-phone/{phone})
      │
      ├─ BOT             → run Tasia (unchanged) → reply
      ├─ PENDING_HANDOFF → persist msg; send holding line; DO NOT run LLM
      └─ HUMAN           → persist msg; notify owning agent's console; DO NOT run LLM
```

And a second small n8n change: an **outbound agent-send** entry (webhook/queue the backend calls) that pushes an agent's typed message to the customer via the existing WhatsApp send node. This is required because the customer-send path lives in n8n, **not** in `admin/wa_gateway.py` (that client only manages staff groups).

---

## 5. Backend API surface (FastAPI, new `conversations` router)

All behind the existing OIDC dependency (`verify_token`); reuse the `AURAADM`/role checks, later refined to per-agent.

| Method | Path | Purpose |
|--------|------|---------|
| `GET` | `/api/conversations` | Agent inbox: filter by `mode`, `branch_code`, `owner_role`, assigned-to-me |
| `GET` | `/api/conversations/{id}` | Detail + resolved thread from `chat_histories` |
| `GET` | `/api/conversations/by-phone/{phone}` | n8n gate lookup (returns current `mode`/owner) |
| `POST` | `/api/conversations/{id}/handoff` | Set `PENDING_HANDOFF`; create claimable item (called by Tasia's Dispatch, replacing the pure group-notify) |
| `POST` | `/api/conversations/{id}/claim` | `→ HUMAN`, set `owner_agent_id` |
| `POST` | `/api/conversations/{id}/messages` | Agent reply → persists + calls n8n outbound-send |
| `POST` | `/api/conversations/{id}/transfer` | Re-route to another dept (`to_role`, note) → back to `PENDING_HANDOFF` for that queue |
| `POST` | `/api/conversations/{id}/handback` | `→ BOT` or `RESOLVED/CLOSED` |

Each writes a `conversation_event` row.

---

## 6. Agent console (new dashboard screen)

Reuses OIDC auth + the message-thread renderer already in `ChatbotSummaryDetailPage`.

- **Inbox / queue:** conversations in `PENDING_HANDOFF` for the agent's branch+role (claimable) and `HUMAN` owned-by-me (active). Sort by age; show SLA countdown.
- **Conversation view:** full thread (customer + bot + agent turns), the Tasia-generated `summary` + `next_action` at top, and a **reply box** (sends via §5 `/messages`).
- **Handler indicator:** every conversation shows a clear badge — **🤖 AI (bot)** vs **🧑 Human (agent name)** — driven by `mode`. Optional customer-facing transition line on takeover/handback (e.g. "Anda terhubung dengan tim kami" / "kembali ke asisten Tasia").
- **Actions:** Claim · Transfer (dept picker) · Resolve · **Hand back to bot** (the "done" button → `mode = BOT`).
- **Live updates:** SSE/poll (SSE infra already used for pipelines).

---

## 7. Constraint: WhatsApp 24-hour window

Free-text replies to a customer are only allowed within **24h of the customer's last message** (that's why `conversation.last_customer_msg_at` exists). Outside it, only **approved template messages** send. Foundations:
- Show the window status/countdown in the console; disable free-text + offer a template when expired.
- "Re-approach a cold lead days later" ⇒ must start from an approved template. Worth cataloguing templates early.

---

## 8. QA/QC — all conversations, as a byproduct

Because §3.1 creates a `conversation` row for **every** chat (not only dispatched/lead ones) and the console lists from that registry, **every** conversation becomes reviewable — fixing "only leads are saved." To fully close it:
- Verify n8n's chat-memory writes **all** inbound/outbound turns to `chat_histories` (if yes, the gap was only *surfacing*; if no, add the write).
- Add QA fields to `conversation` later (disposition, was-human-handled, review flag, CSAT). These also feed the funnel metrics in the proposal.

---

## 9. Suggested build order (this increment)

1. **DB migration:** `conversation` + `conversation_event` tables; backfill `conversation` from existing `chatbot_summary` + `chat_histories`.
2. **Backend:** `conversations` router (§5), read endpoints first, then claim/message/transfer/handback.
3. **n8n:** inbound mode-gate (§4) + outbound agent-send webhook.
4. **Frontend:** agent console (§6) — inbox → detail → reply → claim/transfer/resolve.
5. **Wire Dispatch → handoff:** point Tasia's Dispatch Message at `/handoff` so it sets `PENDING_HANDOFF` (in addition to / instead of the group notify).
6. **SLA + escalation** (from the proposal) once the loop works.

---

## 10. Open questions to resolve before build

1. **Identity mapping:** the console needs to know *which agent = which `master_branch_pic.user_id`*. Do agents log in with the same OSP identity that populates `master_branch_pic`? (Determines claim/authorization.)
2. **Multi-agent claim:** if several PICs share a branch+role queue, first-claim-wins? Supervisor reassignment?
3. **Bot-during-human:** while `HUMAN`, should Tasia still run silently to (a) draft suggested replies for the agent, or (b) stay completely off? (Off is simplest for v1; copilot is a fast-follow.)
4. **Handback trigger:** manual only, or auto-handback after N minutes of resolution/inactivity?
5. **WhatsApp templates:** do we already have approved templates for re-approach, or does that need a parallel workstream?

---

## 11. Confirmed scope (design review 2026-07-02)

Statements confirmed with the product owner, and where each is handled in this doc:

| # | Confirmed requirement | Verdict | Where |
|---|-----------------------|---------|-------|
| 1 | The new tables handle **conversation history, transfer, and QA/QC** | ✅ True | `conversation` + `conversation_event` (§3); QA-all-history (§8) |
| 2 | UI shows a **declaration of AI vs human agent** handling the session | ✅ True | Handler badge driven by `mode` (§6); optional customer-facing transition line |
| 3 | A **"done" button** hands the chat **back to AI** | ✅ True | `handback` action → `mode = BOT` (§2, §5, §6) |
| 4 | **Dashboard diversification per dispatch/department** so queues don't get messy | ✅ True — **phase 2** | See §11.1 |

### 11.1 Further development — per-department dashboard diversification
Rather than one shared inbox, split the console into **per-dispatch-role queues** (`sa`, `crc`, `sales`, `bp_advisor`, `partman`, `trade_in`), scoped to the agent's `branch_code`. An agent sees only their department's `PENDING_HANDOFF` + owned `HUMAN` conversations; supervisors get an all-departments view. No data-model change needed — it filters on `conversation.owner_role` + `branch_code` (already in §3.1). Deferred to phase 2 to keep the v1 bridge focused.

### 11.2 Locked build decisions (design review 2026-07-02)
- **Agent identity → Same OSP identity.** Console SSO `user_id` = `master_branch_pic.user_id`. Authorization: token → user_id → their branch/role. *Confirm before go-live:* agents have OSP accounts and `master_branch_pic` is populated with those user_ids.
- **Bot during HUMAN → Fully OFF in v1.** No LLM output while `mode = HUMAN`. Copilot (bot drafts, human approves) is a fast-follow.
- **Handback → Manual only in v1.** Agent clicks Resolve/Hand-back → `mode = BOT`. A supervisor-facing stale flag (does NOT auto-reengage the bot) comes in Phase 5. No auto-handback.
- **Message ordering → `(created_at, id)` with monotonic `bigserial` id.** Never order by timestamp alone; no Snowflake (single-Postgres scale).

---

## 12. Response SLA & escalation

**Goal:** contact a dispatched customer *while the lead is still hot*. Research on lead response is consistent — reaching a lead within minutes vs. 30+ minutes changes conversion by an order of magnitude, and odds fall sharply after the first hour. A response timer with real escalation is the highest-ROI addition to the bridge.

### 12.1 Tiered SLA (not one flat number)
The timer threshold is read from config keyed on `category` / `inquiry_type` / `dispatch_role` — a flat 15–30 min for everything is too blunt:

| Tier | Example | Target first-response |
|------|---------|----------------------|
| 🔥 Hot lead | `Leads` (specific model + purchase timeframe) | **5–10 min** |
| 😟 Complaint | routed to `crc` | **10–15 min** |
| 🙂 General inquiry / service booking | everything else | **~30 min** (the proposed default) |

Stored as a small SLA-config (per role/category), not hardcoded — so thresholds tune without a deploy.

### 12.2 Two checkpoints (not one)
"Response" is ambiguous — measure both:
- `claimed_at` — agent took ownership (§3.1).
- `first_response_at` — agent's **first actual message to the customer** = the SLA the customer feels, and the real time-to-first-response (TTFR) metric.

### 12.3 Escalation ladder (a timer must *do* something)
- **T0** — dispatch → `PENDING_HANDOFF`, notify the department queue.
- **T + SLA, unclaimed** → escalate: ping backup PIC / branch head, bump priority.
- **T + 2×SLA** → escalate to supervisor / central CRC.

Each step writes a `conversation_event` (`sla_escalate`) — auditable and measurable.

### 12.4 New `conversation` fields
- `response_due_at` (= `handoff_at` + SLA-for-this-category)
- `first_response_at`
- `sla_state` (`on_time / due_soon / breached`)

### 12.5 Who fires the breach
A **scheduled n8n workflow** (~every 1 min) finds `PENDING_HANDOFF` conversations past `response_due_at` and not yet escalated, runs the ladder, and re-notifies via WhatsApp. This is the recommended approach — simple and self-contained.

*(Event-driven alternative, if ever needed: an **outbox** table — escalation events written in the same DB transaction as the state change, then published by a worker. Note: the existing `inbox_kafka` table is the reverse direction — it ingests events coming IN from other systems' Kafka topics — so it is **not** the right vehicle for firing our own SLA timers.)*

### 12.6 Two gotchas
- **Business hours:** the SLA clock should respect **branch operating hours** (already in the branch tables) — a 15-min timer at 2 AM must not mark the whole branch as breached. Decide: pause outside hours, or a separate after-hours rule.
- **24-h WhatsApp window:** the response SLA lives *inside* the care window (fine for live handoffs). A lead gone cold past 24 h can only be re-approached via an approved template (§7). Timer handles "hot"; templates handle "gone cold."

### 12.7 Further development — data-driven customer tiering
Today's tiering is **rule-based** (model named? + purchase timeframe? → hot). Once enough labelled conversations accumulate (dispatch outcome + whether it converted), replace/augment the rules with a lightweight model:
- **TF-IDF** over the conversation text → surface intent/urgency signals.
- **Logistic regression** (or similar simple classifier) on features like intent keywords, model mentioned, timeframe, prior visits, response latency → a **lead-score / tier probability**.

Kept intentionally simple (interpretable, cheap to train, easy to sanity-check) — the point is to prioritize the queue and set SLA tiers from *learned* conversion likelihood rather than fixed rules. Prerequisite: the QA-all-history capture (§8) + outcome labels, so there's a dataset to train on. Ship as a *hint/score* with human override, never a hard gate.

---

## 13. Unified message store (the WhatsApp-style transcript)

**Goal:** a dashboard chat view that shows **every** message — from the customer, from Tasia (AI), and from a human agent after takeover — as one chronological WhatsApp-style thread, and stores it durably for QA/QC.

### 13.1 Why not reuse `chat_histories`
`chat_histories` is **n8n's LangChain chat *memory*** — it exists to feed the model its own context, not to be a transcript:
- JSON is **LLM-shaped** (`type: human/ai/tool`, tool-call objects, sometimes double-encoded) — not "who said what, when."
- **No concept of a human agent** as an author; no delivery status; no media model.
- n8n **owns and may window/prune it** (memory has limits). QA needs a **complete, immutable** record.

So we add a dedicated store and leave `chat_histories` as agent memory.

### 13.2 The four entities, final
| Entity | Role |
|--------|------|
| `conversation` | current state / who controls the session |
| `conversation_event` | governance audit (claim/transfer/handback/SLA) |
| `chat_histories` | **LLM memory** (n8n's — kept as-is) |
| **`message`** *(new)* | **canonical transcript: every turn, every author — display + QA source of truth** |

### 13.3 `message` schema (modeled on messaging-app design)
```
message
  id                uuid pk
  conversation_id   uuid  fk → conversation      -- groups the thread
  author_type       enum: customer | ai | agent | system
  author_id         varchar        -- agent user_id, customer phone, or 'tasia'
  direction         enum: inbound | outbound
  content_type      enum: text | image | audio | document | location | template | interactive
  text              text                          -- the body
  media             jsonb null                    -- {url, mime, caption} — store a REFERENCE, not the blob
  wa_message_id     varchar unique null           -- WhatsApp msg id → dedup + delivery receipts
  status            enum: sent | delivered | read | failed
  reply_to          uuid null                     -- quoted replies
  created_at        timestamptz                   -- THE ordering key
  raw               jsonb null                    -- original payload, for audit
  -- index: (conversation_id, created_at)         -- the whole WhatsApp view is this one query
```
`author_type` makes the AI-vs-human distinction native to every message → bubble label ("🤖 Tasia" vs "🧑 Budi – Service") is trivial, and QA can filter to human-only turns.

### 13.4 Ingestion — one write path, three sources
```
customer msg   → n8n WhatsApp trigger ─┐
AI reply       → n8n AI Agent node ────┼─→  POST /api/conversations/{id}/messages  → INSERT message
agent reply    → dashboard console ────┘        (agent path also sends to customer via n8n → WhatsApp)
delivery/read  → n8n WhatsApp status webhook → PATCH message.status WHERE wa_message_id = ?
```
All three funnel through **one endpoint** so every row has an identical shape — a complete record even across takeover.

### 13.5 Rendering like WhatsApp (frontend)
- Query `WHERE conversation_id=? ORDER BY created_at` with **keyset pagination** (infinite scroll upward — not offset paging).
- Inbound left / outbound right; author label + timestamp; delivery ticks from `status`; media bubbles from `media`.
- Repoint the existing thread renderer in `ChatbotSummaryDetailPage` at this clean table instead of parsing LangChain JSON.

### 13.6 Efficiency notes
- Index `(conversation_id, created_at)`; **unique** `wa_message_id` handles webhook retries/dedup.
- Media = object-storage URL reference, never blobs in Postgres.
- Table grows fast → plan time-based partitioning/archival later (not v1).

### 13.7 References to understand the flow
Study two distinct bodies of knowledge — and **skip a third**:

**A. Chat-system data model & design (the core of what you're building):**
- 📘 Alex Xu — *System Design Interview, Vol. 2*, chapter **"Design a Chat System"** — message table, ordering/IDs, delivery status, 1:1 vs group. *(Best single source.)*
- 🎥 **ByteByteGo** (Alex Xu) on YouTube — "Design a Chat System / WhatsApp / Messenger."
- 🎥 **Gaurav Sen** and **Hussein Nasser** (YouTube) — "Design WhatsApp / chat application database schema."

**B. WhatsApp Business (Cloud) API — your actual channel, for ingestion + delivery status:**
- 📄 Meta — Cloud API **Webhooks**: https://developers.facebook.com/docs/whatsapp/cloud-api/webhooks
- 📄 Meta — **Message status** (sent/delivered/read) — the source of `wa_message_id` and delivery ticks.

**C. Real-world reference architecture (closest analog to this project):**
- 💻 **Chatwoot** (open-source shared inbox with AI + human agents over WhatsApp): https://github.com/chatwoot/chatwoot — skim its `messages` / `conversations` / `contacts` schema for a battle-tested version of exactly this design.

**⚠️ Skip:** consumer-WhatsApp *internal architecture* talks (Erlang, millions of connections, Signal protocol). That's infrastructure scale, not your problem — you're building a help-desk on top of the Business API, so the data model (A) + the API webhook flow (B) are what matter.
