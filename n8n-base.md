# n8n — Node-by-Node Build Steps

Hands-on guide: every node to add, where to put it, and the exact field values —
mapped to your real workflows (`Main Tasia`, `Dispatcher`, `Send Message (Orion)`).

```
API base = https://auto2000-genai-api-dev.astra.co.id
Phone (in Main Tasia) = {{ $('InputNormalizer').first().json.customerPhone }}
Tasia reply text      = {{ $json.response }}   (at the Send Message node)
```

> **Fields to confirm** (open your `InputNormalizer` node → Output to check exact names):
> the **customer name** (assumed `customerName`) and the **inbound message text**
> (assumed `text`). If they differ, swap them in the bodies below.

Every HTTP Request node uses the same header setup:
- **Send Headers = ON** → `Content-Type: application/json`
- (recommended) `X-Internal-Token: <your-shared-secret>`  ← see §0
- **Send Body = ON** → Body Content Type = **JSON** → paste the JSON shown.

---

## §0. One-time: shared-secret credential (recommended)
The dev backend has auth-bypass. Before pointing n8n at it, add a secret so only n8n
can call it:
- In n8n, create/set an environment or a value you'll paste as header `X-Internal-Token`.
- Tell me the value and I'll make the backend require it. (Skip for a first local test.)

---

## Workflow 1 — `Main Tasia`  (4 new nodes)

### Current wiring (the part we touch)
```
… InputNormalizer → Switch → … → Switch2 → Orchestrator → … → Call 'Send Message (Orion)'
```

### New wiring
```
InputNormalizer → [A] Ensure Conversation → [B] Log Inbound → [C] Human handling? (If)
                                                                 ├─ TRUE  → (stop; do nothing)
                                                                 └─ FALSE → Switch  (existing path continues)
… Orchestrator → [D] Log Tasia Reply → Call 'Send Message (Orion)'
```
(You are re-pointing the arrow that today goes `InputNormalizer → Switch` so it goes
through A → B → C, and C's **FALSE** output connects to `Switch`.)

### Node A — "Ensure Conversation"
- **Type:** HTTP Request  ·  **Method:** `POST`
- **URL:** `https://auto2000-genai-api-dev.astra.co.id/api/conversations/ensure`
- **Body (JSON):**
  ```json
  {
    "conversation_id": "={{ $('InputNormalizer').first().json.customerPhone }}",
    "phone_no": "={{ $('InputNormalizer').first().json.customerPhone }}",
    "customer_name": "={{ $('InputNormalizer').first().json.customerName }}"
  }
  ```
- **Returns** the conversation, including `id` and `mode` — used by B, C, D.
- **Connect:** `InputNormalizer → Ensure Conversation`.

### Node B — "Log Inbound"
- **Type:** HTTP Request  ·  **Method:** `POST`
- **URL:** `…/api/conversations/{{ $('Ensure Conversation').first().json.id }}/messages`
- **Body (JSON):**
  ```json
  {
    "author_type": "customer",
    "direction": "inbound",
    "text": "={{ $('InputNormalizer').first().json.text }}"
  }
  ```
- **Connect:** `Ensure Conversation → Log Inbound`.

### Node C — "Human handling?"  (the gate)
- **Type:** If
- **Conditions** (combinator **OR**), both String:
  1. `{{ $('Ensure Conversation').first().json.mode }}`  **equals**  `HUMAN`
  2. `{{ $('Ensure Conversation').first().json.mode }}`  **equals**  `PENDING_HANDOFF`
- **TRUE output:** leave unconnected (a human is handling → Tasia does nothing).
- **FALSE output:** connect to **`Switch`** (your existing next node).
- **Connect in:** `Log Inbound → Human handling?`

### Node D — "Log Tasia Reply"
- **Type:** HTTP Request  ·  **Method:** `POST`
- **URL:** `…/api/conversations/{{ $('Ensure Conversation').first().json.id }}/messages`
- **Body (JSON):**
  ```json
  {
    "author_type": "ai",
    "direction": "outbound",
    "text": "={{ $json.response }}",
    "status": "sent"
  }
  ```
- **Place:** just **before** `Call 'Send Message (Orion)'` (same spot `$json.response` is valid).
  Connect: `…(Orchestrator output)… → Log Tasia Reply → Call 'Send Message (Orion)'`.

> **Do the gate first.** Add A + C only, wire C-FALSE → Switch, and test: flip a chat to
> HUMAN in the console, message the bot → Tasia should stay silent. Add B and D after.

---

## Workflow 2 — `Dispatcher`  (2 new nodes)

Placed **right after `Insert ChatbotSummary Table`**, in parallel with the rest.
Use the **same field expressions** your `Insert ChatbotSummary Table` node already uses
for phone, branch, and role/target.

### Node A — "Ensure Conversation"
- **Type:** HTTP Request  ·  **Method:** `POST`
- **URL:** `…/api/conversations/ensure`
- **Body (JSON):** (replace the `…` expressions with the ones your Insert node uses)
  ```json
  {
    "conversation_id": "={{ <phone expression> }}",
    "phone_no": "={{ <phone expression> }}"
  }
  ```

### Node B — "Mark Handoff"
- **Type:** HTTP Request  ·  **Method:** `POST`
- **URL:** `…/api/conversations/{{ $('Ensure Conversation').first().json.id }}/handoff`
- **Body (JSON):**
  ```json
  {
    "owner_role": "={{ <the target/role expression> }}",
    "branch_code": "={{ <the branchCode expression> }}",
    "summary": "={{ <the summary expression> }}"
  }
  ```
- **Connect:** `Insert ChatbotSummary Table → Ensure Conversation → Mark Handoff`.

This flips the conversation to `PENDING_HANDOFF` so it shows up in the Agent Console queue.

---

## Workflow 3 — NEW workflow "Agent Reply Sender"  (2 nodes)

Lets a reply typed in the console reach the customer, by reusing `Send Message (Orion)`.

### Node A — Webhook
- **Type:** Webhook  ·  **HTTP Method:** `POST`  ·  **Path:** `agent-reply`
- Copy its **Production URL** (you'll give this to me for the backend call).

### Node B — Execute Workflow
- **Type:** Execute Workflow (a.k.a. "Call n8n Workflow")
- **Workflow:** `Send Message (Orion)`
- **Inputs:**
  - `to`   = `={{ $json.body.to }}`
  - `text` = `={{ $json.body.text }}`
- **Connect:** `Webhook → Execute Workflow`.

*(Backend half is mine: after an agent message is saved, the backend POSTs
`{ "to": "<phone>", "text": "<reply>" }` to your Webhook URL.)*

---

## Build order & test
1. **Main Tasia — Node A + C only** (the gate). Test: console → claim a chat (mode HUMAN) → message the bot → **Tasia stays silent.** ✅ This proves the whole idea.
2. Add **B + D** (message logging) → the console shows the full transcript.
3. **Dispatcher — A + B** (handoff) → a dispatch makes the chat appear in the console queue.
4. **Agent Reply Sender** + backend call → console replies reach the phone.

## Quick reference — what each node calls
| Node | Method | URL |
|------|--------|-----|
| Ensure Conversation | POST | `/api/conversations/ensure` |
| Log Inbound / Log Tasia Reply | POST | `/api/conversations/{id}/messages` |
| Human handling? | (If) | reads `mode` from Ensure Conversation |
| Mark Handoff | POST | `/api/conversations/{id}/handoff` |
| Agent Reply Sender | (Webhook→Execute) | reuses `Send Message (Orion)` |
