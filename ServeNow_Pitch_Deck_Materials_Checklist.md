# ServeNow × BAP — Pitch Deck Materials Checklist

**Purpose of this doc:** map everything already written across the repo's `.md` files onto the slide-by-slide structure of `BCC_COMPFEST_BAP_Pitch Deck.pdf` (the CircuBat deck), and list exactly what's still missing to fill that structure for **ServeNow**.

---

## 0. Framing — read this before building slides

- **The PDF is a structural template only.** Its actual content (CircuBat / low-carbon EV battery circularity) is a *different case* from ServeNow (BizzIT COMPFEST case — omnichannel CS platform, governance + product + sales transformation). Reuse its slide types, layout rhythm, and production polish — not a single sentence of its content.
- **Content maturity is uneven across your three tasks right now:**
  | Task | Doc(s) | Maturity |
  |---|---|---|
  | Task 1 — Governance | `ServeNow_Task1_Governance_Master_Strategy.md` + `ServeNow_Governance_Refinement_Analysis.md` | ✅ Essentially complete, consulting-grade, self-critiqued (Section 16) and stress-tested (Section 18) |
  | Task 2 — Product & Innovation Roadmap | `outline_solution.md` §4, `branchsolution.md`, `handoff-takeover-design.md`, `n8n-base.md` | 🟡 Deep *technical/architecture* detail, but no market-trend research, no competitor analysis, no polished narrative doc |
  | Task 3 — Sales & Expansion Strategy | `outline_solution.md` §5 only | 🔴 Thin — two short subsections, no data, no channel plan |
- **Important tension to resolve early:** `ServeNow_Task1_Governance_Master_Strategy.md` §14 *explicitly declines* to fabricate a financial model ("the case does not disclose cost structure... no financial impact is therefore estimated here"). The CircuBat template's Financial Projection slide (NPV, IRR, ROI, 7-year cash flow, capex schedule) is the opposite move — a fully quantified model built on stated assumptions. **You need to decide, once, which posture ServeNow's deck takes**, and apply it consistently instead of being rigorous in Section 14 and inventing hard numbers on slide 10. See §3 below.

---

## 1. Slide-by-slide mapping

| # | Template slide (CircuBat) | ServeNow equivalent | Status | What you still need to produce |
|---|---|---|---|---|
| 1 | Title — case name, team BAP, member photos, COMPFEST year | Title slide for ServeNow deck | 🔴 | Final deck title (e.g. *"From Founder Bandwidth to System Throughput: Governing, Productizing, and Selling ServeNow"*), 3 member headshots, COMPFEST/BizzIT branding line |
| 2 | Background Analysis: Situation → Issues (3) → Key Question → Strategy (3 pillars) → Impact (5 metrics) | One-pager overview of the whole case | 🟡 | Have the raw material (caseproblem.md target table + Task1 diagnosis). Missing: (a) the **single Key Question** sentence tying governance+product+sales together, (b) final **3-pillar names** styled like the template's ("Pillar I: ... / II: ... / III: ..." — see §3), (c) the **5 impact tiles** — you have SLA 78→96%, churn 16.7→<5%; you still need agreed figures for margin, revenue, and a break-even/payback year (see financial-model decision) |
| 3 | Issue Tree (MECE, A/B/C rows) → root causes → strategic solution per row | Root-cause structuring across governance / product / sales | 🟡 | Governance rows: draw directly from Task1 §1.2–§2.2 (7 bottlenecks) — easy. Product rows: draw from caseproblem.md "Masalah Utama" #3 (sales infra) + `branchsolution.md` cost leak — needs restructuring into MECE A/B/C form. Sales rows: currently the weakest — needs its own root-cause list (see Task 3 gap below) |
| 4 | Pillar I system design — phased SOP (4 phases) + network/map graphic | Governance & Escalation system design (mode state machine, SLA ladder) | 🟡 | Strong source material: `handoff-takeover-design.md` §2 (state machine), §9 (build order), §12 (SLA/escalation ladder) map almost 1:1 onto the template's 4-phase SOP layout. **Missing:** a redrawn diagram in the template's visual style (state machine + escalation ladder as a designed graphic, not a text state diagram) and an org-chart-style graphic replacing the "regional hub map" (4-layer target operating model from Task1 §4) |
| 5 | Pillar II — What/Why/How + sequence diagram | AI Omnichannel product (Single-Number Branch Solution, n8n orchestrator) | 🟡 | What/Why is well covered by `outline_solution.md` §4 + `branchsolution.md` §1–2. Sequence diagram source exists in `n8n-base.md` (node-by-node flow) — needs to be redrawn as a clean UML-style sequence diagram like the template's (Customer → API Gateway → n8n → LLM/Qdrant → downstream) |
| 6 | Pillar II — dashboard mockups (multiple screens) + differentiators | Agent Console, Team Lead/Manager view, VP/C-Level analytics dashboard, customer-facing thread | 🔴 | You have detailed *functional specs* for each screen (`handoff-takeover-design.md` §6 Agent console; Task1 §6.3/§17.5 for what a manager/exec dashboard should show) but **zero visual mockups**. Needs actual UI design (Figma) for: (1) Agent inbox/queue, (2) Manager SLA/escalation view, (3) VP macro dashboard, (4) customer WhatsApp thread w/ AI↔human handoff badge |
| 7 | Pillar III — operational reality + economic impact (cost/return numbers) + 5-phase how-to | Sales & Expansion economics (WA API cost removal, margin impact) | 🔴 | `branchsolution.md` §5 gives a *qualitative* cost comparison table (generic pattern vs branch) but no Rupiah figures. Needs: quantified WA API/group-messaging savings in IDR/year, and a 5-phase build-out narrative for the sales engine (see Task 3 gap) |
| 8 | Risk & Mitigation — table + 3×3 likelihood/impact matrix | Risk register across all 3 pillars | 🔴 | Task1 §16 Q11 ("which recommendations have highest failure risk") is the seed for governance risks but isn't yet a formal register. Product risks (AI misclassification, n8n reliability, WA 24h-window violations — flagged in `handoff-takeover-design.md` §7, §10 open questions) and sales risks are ungathered. Needs: full Strategy/Risk/Mitigation table (aim for ~9 rows, 3 per pillar) + plotted 3×3 matrix |
| 9 | Timeline & KPIs — 12-month Gantt across 3 pillars + KPI target table | Consolidated implementation roadmap | 🟡 | Governance timeline exists and is strong: Task1 §13 (Stabilize 0–3 / Institutionalize 3–6 / Scale 6–12). Product roadmap exists at quarter-granularity: `outline_solution.md` §4B (Q1–Q4). Sales timeline: none yet. **Missing:** merge all three into one month-by-month Gantt (M1–M12) in the template's swim-lane style, and a single consolidated KPI table (SLA, churn, implementation weeks, non-Jabodetabek revenue %, employees/customer) |
| 10 | Financial Projection — 7-yr P&L chart, cash flow, NPV/ROI/IRR/GMROI, market capture rate | ServeNow financial model | 🔴 | **Nothing built yet.** This is the single biggest gap. See §3 for the strategic decision this requires before you build it. |
| 11 | Thank You | Same | 🔴 | Trivial — branding only, do last |
| 12 | References (17 sources, academic/industry) | Citations for CX/SaaS industry trends, WhatsApp Business API economics, org design literature | 🔴 | None gathered yet. Needed regardless of financial-model decision because caseproblem.md Task 2(a) explicitly requires "tren industri layanan pelanggan" — see Research list §2 below |
| 13 | Appendix — formal SOP doc + SWOT-TOWS with IFE/EFE scoring | ServeNow governance/product SOP + SWOT-TOWS | 🟡 | Task1 has the substance for SWOT ("what should NOT change" §15, strengths to protect) but not the formal SOP-document format (Doc No., Version, Owner, SOP Index table) or a scored SWOT-TOWS matrix. Both need to be built as standalone appendix docs |
| 14 | Appendix — market/sales data (charts + regional table) | Indonesian CS-software / WhatsApp Business market data, ServeNow customer base by sector/region | 🔴 | Not researched. Needed for Task 2(a)(b)(c) — industry trend, market need, competitor analysis — and for framing Task 3's non-Jabodetabek expansion target |
| 15 | Appendix — end-user mobile app mockups | Customer-facing chat experience (or agent mobile view, if relevant) | 🔴 | No mockup. Lower priority than #6 — ServeNow's customer touchpoint is WhatsApp itself, not a branded app, so this slide may not even apply 1:1 (see note in §4) |
| 16 | Appendix — 2 more dashboard mockup sets | Additional dashboard detail views (e.g. escalation ladder live view, transfer/claim history) | 🔴 | Same visual-design gap as #6 |
| 17 | Appendix — 2 more operational dashboard sets | Exec/ops dashboards detail views | 🔴 | Same visual-design gap as #6 |
| 18 | Appendix — full financial detail tables (capex schedule, key assumptions, annual cash flow, unit costs) | Detailed financial backup tables | 🔴 | Depends entirely on §3's decision |

---

## 2. Research to gather (needed regardless of the financial-model decision)

The case brief (`caseproblem.md`, "Tugas untuk Peserta" #2) *requires* these for Task 2 — they're not optional polish:

- [ ] **Customer service / CX industry trends** — omnichannel adoption, GenAI in CX (agent assist, RAG-based self-service), WhatsApp Business API growth in Indonesia/SEA
- [ ] **Market need data** — Indonesian SME/enterprise digital CS adoption rate, sector breakdown (retail, health, education, fintech, gov — matching ServeNow's existing base)
- [ ] **Competitor analysis** — at least 2–3 global players (e.g. Zendesk, Freshdesk, Intercom, Salesforce Service Cloud) and 2–3 local/regional players, compared on price, implementation time, local support, AI features — this is the direct evidence base for ServeNow's "flexible + cheaper WA-cost architecture" USP claimed in `outline_solution.md` §5B
- [ ] **WhatsApp Business API pricing** (conversation-based pricing tiers) — needed both to quantify the cost savings claimed in `branchsolution.md` and to cite as a reference (mirrors the template's citation of GAIKINDO/IEA-style primary sources)
- [ ] **Org design / governance benchmarks** (optional but strengthens Task 1's citations) — span-of-control literature, SaaS company org-scaling case studies

---

## 3. The financial model decision (resolve before touching slide 10 or 18)

Two honest options — pick one and say so explicitly in the deck rather than mixing postures:

**Option A — Match the template's rigor (full quantified model).**
Build assumptions from scratch (stated explicitly as assumptions, same way the CircuBat appendix states WACC, tax rate, inflation, USD/IDR): revenue-per-customer tiers, cost-per-employee estimate, WA API savings, marketing spend ramp, then derive 7-year P&L, cash flow, NPV/IRR/ROI, payback year. Pros: matches template's visual firepower and likely scores well on "Data Pendukung" / "Rasionalitas" rubric lines. Cons: every number is an assumption on top of a case that deliberately withholds cost data — need to be transparent that these are illustrative, sourced from stated inputs.

**Option B — Keep Section 14's discipline (impact-logic model, no fabricated P&L).**
Redesign slide 10 as an "Intervention → Mechanism → KPI → Financial Direction" panel (reuse Task1 §14.1/§14.2 almost verbatim) instead of a fabricated cash-flow chart. Pros: consistent, defensible, matches the rigor already built into Task 1. Cons: visually thinner than the template's slide 10 — needs strong chart design to not look like "we skipped this slide."

*Recommendation:* Option A **only if** you clearly label assumption tables (mirrors what the template itself already does on its appendix slide 18 — "Key Assumptions" box). A hybrid also works: headline slide 10 stays impact-logic (Option B) for credibility, and a fully-modeled version lives in the appendix (Option A) for anyone who wants to check the math — this is close to what the template itself does (slide 10 = story, slide 18 = detail).

Either way, you need to build, from scratch:
- [ ] Revenue model by year (2026 baseline Rp15.8B → Rp45B target — interpolate a growth curve)
- [ ] Cost structure assumptions (headcount cost, infra/API cost, marketing) — stated explicitly as assumptions
- [ ] If Option A: WACC, discount rate, tax rate, planning horizon, capex schedule (governance tooling build, dashboard/console dev, n8n+Qdrant infra)
- [ ] Payback/break-even year estimate
- [ ] Employees-per-customer trajectory chart (1.86 → ≤1.41) — this one *is* already derived in Task1 §14.2 and is your strongest, most defensible chart candidate for slide 10

---

## 4. Visual/design assets to produce (none exist yet)

All of these are currently only *functional specs in prose* — they need an actual design pass (Figma or similar):

- [ ] **State machine + escalation ladder diagram** (source: `handoff-takeover-design.md` §2, §12) — for slide 4
- [ ] **4-layer target operating model / org chart** (source: Task1 §4) — replaces the template's regional-hub map on slide 4
- [ ] **Conversation lifecycle sequence diagram** (source: `n8n-base.md` node flow, `handoff-takeover-design.md` §4) — for slide 5
- [ ] **Agent Console mockup** (queue/inbox + claim + reply, SLA countdown, AI/human badge — spec in `handoff-takeover-design.md` §6) — for slide 6
- [ ] **Manager/Team Lead dashboard mockup** (escalation view, review/QA of transcripts — spec in `outline_solution.md` §3B) — for slide 6/16
- [ ] **VP/C-Level analytics dashboard mockup** (macro trends only — spec in Task1 §17.5) — for slide 6/17
- [ ] **Customer WhatsApp thread mockup** (single number, AI↔human handoff transition line — spec in `handoff-takeover-design.md` §6) — for slide 6, may substitute for the template's "EV Owner App" appendix slide 15
- [ ] **3×3 risk matrix plot** — for slide 8
- [ ] **12-month Gantt, swim-laned by pillar** — for slide 9
- [ ] **Financial charts** (P&L bar chart, cash-flow table, employees-per-customer line chart) — for slide 10/18, pending §3 decision
- [ ] **SWOT-TOWS matrix with IFE/EFE scoring** — for appendix (slide 13)

---

## 5. Documents to draft (text, not yet written anywhere)

- [ ] **One-page Executive Summary** — case brief requires this explicitly (max 1 page) and it's a separate deliverable, not just slide 2's infographic. Draft exists implicitly across `outline_solution.md` §1 (Indonesian) — needs a final polished English-or-Indonesian version depending on presentation language
- [ ] **Task 2 narrative doc** (peer to `ServeNow_Task1_Governance_Master_Strategy.md`) — synthesizing industry trends + market need + competitor analysis + the existing technical architecture into one coherent product/innovation roadmap story. Right now the technical depth exists but there's no "Task1-quality" narrative wrapper for Task 2.
- [ ] **Task 3 sales & expansion strategy doc** — currently the thinnest task. Needs: lead-gen funnel detail (beyond the one-paragraph "Hunting vs Harvesting" in `outline_solution.md` §5A), a channel/GTM plan for non-Jabodetabek expansion, a sales team structure/hiring plan (this should link back to Task1 §8's Head of Sales role and delegated pricing authority in §17.4), and a quantified sales funnel (leads → qualified → demo → close) with target conversion rates
- [ ] **Formal SOP document** (Document No., Version, Owner, SOP Index table format like the template's appendix 13) — covering: ticket claim protocol, SLA escalation protocol, conversation handoff/transfer protocol, QA review cadence
- [ ] **References list** — populate once research (§2) is done; match the template's ~17-source academic/industry citation format
- [ ] **10-minute audio presentation script** — explicit deliverable per `caseproblem.md`; needs a final narrative arc across all 3 tasks once slides are locked

---

## 6. Suggested pillar naming (for visual/verbal consistency with the template's style)

The template names pillars as terse, technical, ownable statements (e.g. *"Mode State Machine & Atomic First-Claim-Wins"*). Your existing docs already contain equivalents — just need to be shortened to that style:

| Pillar | Draft long-form (already in your docs) | Suggested short pillar name |
|---|---|---|
| I — Governance | Task1's "Decision Rights Matrix + 3-Tier Escalation + 6 Functional Owners" | **"Bounded Decision Rights & Tiered Escalation"** |
| II — Product | `branchsolution.md`'s "Single-Number Branch Solution" + `handoff-takeover-design.md`'s mode state machine | **"Single-Number GenAI Omnichannel & Human Takeover"** |
| III — Sales | `outline_solution.md` §5A's "Hunting vs Harvesting" | **"AI-Qualified Lead Engine & Named Account Ownership"** |

---

## 7. Suggested build order

1. **Lock the financial-model posture** (§3) — everything downstream on slides 2, 9, 10, 18 depends on this decision.
2. **Write the Task 3 sales doc** — it's the weakest link and every other pillar references it (Task1 §14.2 already flags Task 3 as owner of the revenue/margin targets).
3. **Do the industry-trend/competitor research** (§2) — required content, not just decoration, and unblocks the Task 2 narrative doc.
4. **Write the Task 2 narrative doc** — synthesize existing technical docs + new research into one coherent story, mirroring Task 1's structure.
5. **Build the financial model** (§3) once Tasks 2 & 3 give you real assumptions to hang numbers on.
6. **Commission/build the visual assets** (§4) — these can start in parallel with steps 2–5 once functional specs are locked, since the specs already exist.
7. **Assemble slides 1–12** (core deck) first; appendix slides 13–18 last.
8. **Write the 1-page executive summary and the audio script** — genuinely last, once the story is final.
