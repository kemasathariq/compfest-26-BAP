**COMPFEST 18 — BUSINESS IT CASE  |  TASK 1**

**ServeNow Technologies**

**Governance & Organization**

**MASTER STRATEGY DOCUMENT**

| THE QUESTION THIS DOCUMENT ANSWERS *How should ServeNow redesign its governance and organizational operating model so that it can scale from Rp15.8B to Rp45B revenue, reduce founder dependency, improve operational reliability, and create the operating leverage required to achieve 15–20% net margin?* |
| :---- |

| THE ANSWER IN ONE SENTENCE ServeNow must move capability, decision rights, and customer trust out of three individuals and into six accountable functional owners governed by explicit decision boundaries, a four-tier performance architecture, and a single institutional record — so that the company’s throughput stops being limited by director bandwidth and each additional customer stops requiring 1.86 additional employees. |
| :---- |

*Sources: ServeNow case (primary) · Root Cause Diagnosis v2 (revised & stress-tested)*

August 2026

# **Data Correction Before We Begin**

| One input correction, flagged before any analysis depends on it. The brief instructs: "Do not design a corporate bureaucracy for a 59-person company." The case states ServeNow has 78 employees (45 → 61 → 78 across three years). 59 does not appear in the case; it is close to the Year-2 figure of 61, which may be the source of the slip. This matters materially for organizational design. At 59 people, three directors and a handful of leads is arguably survivable. At 78 people — growing toward roughly 169 under the target model — the absence of a management layer is not a stylistic weakness but a structural failure. All spans of control, role counts, and layer decisions in this document are calculated on 78 actual and \~169 target. *The instruction’s intent — do not over-engineer — is correct and is honoured throughout. This document proposes the minimum viable management structure, not a corporate hierarchy.* |
| :---- |

# **Contents**

**Section 1**   Executive Diagnosis

**Section 2**   Current-State Governance Model

**Section 3**   Governance Design Principles

**Section 4**   Target Organizational Operating Model

**Section 5**   Decision Rights Architecture

**Section 6**   Performance Management System

**Section 7**   Employee Discipline & Accountability

**Section 8**   Management Layer & Key Roles

**Section 9**   Customer Trust Transfer

**Section 10**   Information & Management System

**Section 11**   Governance Cadence

**Section 12**   Target Operating Model Integration

**Section 13**   Implementation Roadmap (0–12 Months)

**Section 14**   Quantified Impact Logic

**Section 15**   What Should NOT Change

**Section 16**   Self-Critique & Revision

**Section 17**   Final Consulting Synthesis

**Section 18**   Response to External Stress-Test Review

# **Section 1 — Executive Diagnosis**

## **1.1  The Current Governance Problem**

ServeNow does not have a weak governance model. It has, in the strict sense, almost no governance model at all — it has three individuals performing the work that a governance model would otherwise do.

The company operates with three directors holding between five and eight functional roles each, no management layer between them and 78 staff, no documented decision boundaries, no performance architecture, and no single institutional record of the business. Coordination happens through informal communication and direct founder intervention. This is not a design flaw; it is the natural residue of a company that grew from 45 to 78 people without ever deciding how it would be run at that size.

## **1.2  Root Cause**

Root Cause Diagnosis v2 established three fundamental causes. Two sit squarely inside Task 1’s scope; the third constrains what governance alone can achieve.

| Root Cause | In Scope for Task 1? | Governance Implication |
| ----- | ----- | ----- |
| **F1. Founder-embedded capability, trust & knowledge** | **Primary scope** | Capability, decision authority, and customer relationships live in three people. Governance must relocate them into roles, processes, and records. |
| **F2. No institutional operating system** | **Primary scope** | No documented process, no measurement, no single source of truth. Governance must build the layer that makes delegation safe and performance visible. |
| **F3. No defined product boundary** | **Out of scope — but binding** | Owned by Task 2\. Governance can create the role that owns product boundaries and grant it authority — it cannot define the boundaries themselves. |

**Critical interdependency:** F3 is a Task 2 deliverable, but it constrains Task 1\. Governance can create the *role* that owns product boundaries and the *authority* that role needs — it cannot define the boundaries themselves. Section 14 is explicit about which margin improvements governance can and cannot claim.

## **1.3  Testing the Provided Causal Chain**

The brief supplies a causal chain and asks that it not be accepted blindly. Tested against the case, it is directionally sound but requires three corrections before it can carry a strategy.

| Correction | Issue with the Chain as Given | Revised Statement |
| ----- | ----- | ----- |
| 1\. "Inconsistent execution → long implementation" is under-specified | It implies implementation is long because execution is sloppy. The case shows a structural cause: scope is re-negotiated per customer and re-approved by a single technical authority. | Long implementation has two parents — undefined product boundary (F3) and single-point technical approval (E1). Governance can only fix the second. |
| 2\. The chain is linear; the system has feedback | A linear chain predicts a stable bad equilibrium. The case shows deterioration: churn 8.3%→12.1%→16.7%, complaints/customer 0.58→1.02. | Two reinforcing loops operate: Attention Depletion (growth consumes the capacity that serves) and Customization Lock. Governance breaks the first, not the second. |
| 3\. It ends at "margin compression" | Margin compression is not the terminal state. At Rp395jt absolute profit, the company cannot fund its own transformation. | Terminal consequence: self-funding capacity is lost. This raises urgency and constrains how expensive the governance redesign may be. |

## **1.4  Business Consequence**

| Dimension | Current | Governance Mechanism Producing It |
| ----- | ----- | ----- |
| Implementation time | 16–22 weeks | Every scope decision and technical approval routes through one Technology Director holding six roles simultaneously |
| SLA attainment | 78% (22% of commitments breached) | No escalation tiers; service problems travel directly to directors rather than being contained by an accountable owner |
| Churn | 16.7% — consuming 44% of gross new logos | Service failures accumulate because no one below director level owns retention outcomes |
| Employee productivity | Overtime from poor planning; missed deadlines; staff unreachable | No capacity planning, no role clarity, no output measurement — individual contribution is invisible |
| Revenue per employee | Rp202.6jt (+11.2% over 3 yrs) | Improved slightly, but cost per employee rose faster (+14.1%) — no mechanism exists through which productivity could systematically improve |
| Profit per employee | **Rp9.1jt → Rp5.1jt (−44%)** | Headcount grew 73.3% against customer growth of 75.0% — headcount is a function of customers, not of strategy |
| Net margin | **5% → 4% → 2.5%** | Incremental margin on the last Rp7.6B of revenue: −0.2%. Growth has stopped creating value. |
| Founder workload | 5–8 concurrent roles each | All operational problems escalate upward; subordinates depend on direction; no delegated authority exists |

## **1.5  Strategic Implication — Why Governance Must Change First**

Three arguments establish governance as the prerequisite phase rather than one of three parallel workstreams.

* **Director bandwidth is the binding constraint on every other initiative.** Product definition, sales-process design, and marketing all require sustained senior attention. That attention does not currently exist — it is consumed by pricing negotiations, implementation supervision, support escalations, and technical approvals. Governance is the only workstream that *creates* the capacity the other two need to consume.

* **Delegation has two preconditions, and both are governance deliverables.** You cannot delegate a decision without a documented boundary defining what "correct" looks like, and you cannot delegate an outcome without a measurement system that makes it visible. Neither exists today. This is why appointing managers without first building these two layers would reproduce the current situation under different titles.

* **Retention is the cheapest available lever, and it is governance-owned.** Churn at 16.7% requires \~38 gross new customers per year to reach 120; at 5% it requires \~29. Cutting churn removes roughly a quarter of the sales burden without hiring a single salesperson — and churn is driven by SLA and escalation failures, which are governance problems.

| One-Sentence Diagnosis ServeNow cannot sustainably scale its current growth model because its capability, decision rights, and customer trust remain embedded in three individuals whose capacity is fixed — making director attention, not capital or demand, the true constraint on growth, and forcing every additional customer to consume roughly 1.86 additional employees plus a share of a resource that cannot be purchased. |
| :---- |

# **Section 2 — Current-State Governance Model**

Reconstructed from the case. Where the case is silent, the inference is labelled.

| CURRENT STATE  —  Three-Person Bottleneck     \[ Direktur Utama \]    \[ Direktur Teknologi \]    \[ Direktur Operasional \]       8 concurrent roles      6 concurrent roles       5 concurrent roles             \\                      |                       /              \\\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_|\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_/                                    |                         NO MANAGEMENT LAYER                                    |    \+---------+---------+-----------+-----------+---------+    |         |         |           |           |  Tech    Impl.    Support      Sales       Admin                                  (3 ppl)                         — 78 employees total — Every escalation, approval and non-routine decision travels upward. Span of control per director: \~26 staff, across unrelated functions. |
| ----- |

## **2.1  Governance Element Analysis**

| Element | Current State | Evidence | Problem Created | Root Cause |
| ----- | ----- | ----- | ----- | ----- |
| Founders / Executive | Three founders operating as full-time executors, not governors | Directors hold 5–8 functional roles each | Strategy is unstaffed; the case notes reduced management focus on strategy | F1 |
| Directors | Functional titles but operational content — CTO is also architect, reviewer, security owner, implementation advisor | Case lists all six CTO roles explicitly | Single-point approval on every technical decision → 16–22-week implementation | F1 / E1 |
| Managers | **Absent entirely** | No function heads named; directors themselves hold "kepala implementasi" and "kepala customer support" | No one owns an outcome below director level; span of control \~26 per director | F1 |
| Team Leads | **Absent or informal** | Not mentioned in the case (Inference: if formal leads existed, escalation would not reach directors directly) | No first-line containment of operational problems | F1 |
| Staff (78) | Capable but dependent — wait for direction rather than deciding | Case: subordinate dependence on direction | Decision latency; capability never develops because authority is never exercised | E1 |
| Decision-making | Undocumented, ad hoc, founder-mediated | No decision boundaries described anywhere in the case | Decisions queue behind three people; throughput \= director bandwidth | E1 |
| Information flow | Fragmented and informal | Sales data across spreadsheets, WhatsApp, email, personal notes; excessive informal communication | No one can see the state of the business without asking a founder | F2 |
| Customer ownership | Owned by founders personally | Case: customers buy on personal relationship with the owner; trust not transferred to the organization | Revenue attached to individuals; blocks delegation and geographic expansion | F1 |
| Performance management | **Attendance only** | Attendance app exists, but no system linking discipline, targets, work quality, individual responsibility | Output is unmanaged; delegation is unsafe because outcomes are invisible | E2 |
| Escalation | No tiers — direct to board | Case: operational problems rise to the directorate | Directors are the support tier of last resort; SLA stuck at 78% | E1 |

## **2.2  The Seven Governance Bottlenecks, Ranked**

Ranked by strategic impact — defined as the number of transformation targets each bottleneck blocks, weighted by whether governance alone can resolve it.

| \# | Bottleneck | Why It Ranks Here | Targets Blocked |
| ----- | ----- | ----- | ----- |
| **1** | **Absence of a management layer** | The single structural void from which most others follow. Nothing can be delegated to a layer that does not exist. Fully within governance control. | Director dependency; SLA; Implementation; Customers 42→120 |
| **2** | **No documented decision boundaries** | Even with managers appointed, decisions would still route upward without explicit authority limits. This is what converts titles into actual delegation. | Implementation; SLA; Director dependency |
| **3** | **No performance architecture** | The precondition that makes delegation safe. Without visible outcomes, directors cannot rationally let go — and would be right not to. | Margin; Director dependency; SLA |
| **4** | **No escalation containment** | Directly produces the 78% SLA and feeds churn. Highest-speed win available: tiering can be designed in weeks, not quarters. | SLA 78→96%; Churn 16.7→\<5% |
| **5** | **Founder-owned customer trust** | Severe and strategically central, but ranked below the structural items because it cannot be installed — it accrues from demonstrated reliability over quarters. | Churn; Non-Jabodetabek 12→40%; Customers |
| **6** | **No single source of truth** | Enables 1–4 rather than acting alone. Without it, managers cannot manage and patterns stay invisible. | Margin; SLA; Implementation |
| **7** | **No capacity planning discipline** | Produces the visible "discipline" symptoms — overtime, missed deadlines. Real, but downstream of 1–3 and largely dissolved by fixing them. | Margin; SLA |

**Ranking logic worth noting:** bottlenecks 1–3 are ordered by *dependency*, not by visibility. Bottleneck 4 is the most *visible* problem and the fastest to improve, which is why the roadmap in Section 13 starts there in parallel — early visible wins fund the political capital required for the structural changes.

# **Section 3 — Governance Design Principles**

Six principles govern every design decision that follows. Five are adapted from the brief; the sixth is added because the case makes it necessary, and one from the brief is deliberately reframed.

## **3.1  What Changed From the Brief’s Proposed Principles**

| Brief’s Principle | Verdict | Change Made |
| ----- | ----- | ----- |
| Institutionalize capability | **Accepted** | Retained as Principle 1 — it is the direct answer to F1. |
| Distribute decision rights | **Accepted** | Retained as Principle 2, with explicit boundaries added — "push down" without limits is abdication, not delegation. |
| Make accountability explicit | **Accepted** | Retained as Principle 3\. |
| Manage outcomes, not activity | **Accepted** | Retained as Principle 4 — the attendance-app failure is direct evidence for it. |
| Institutionalize customer trust | **Accepted** | Retained as Principle 5\. |
| Protect entrepreneurial speed | **Reframed** | Reframed as Principle 6: "Governance must be cheaper than the coordination it replaces." "Protect speed" is a sentiment; this is a testable constraint. |
| — | **Added** | Principle 7 added: "Sequence capability before authority." The case shows staff have never exercised judgement; handing authority to unprepared managers is the highest-probability failure mode of this transformation. |

## **3.2  The Seven Principles**

### **Principle 1 — Institutionalize Capability**

| Any capability that exists only in a person’s head is an unmanaged risk. Critical knowledge must live in documented processes, defined roles, and shared records. |
| :---- |

**Why (root cause):** F1 — capability, execution knowledge, and customer context are embedded in three founders. This is why delegation has never been possible and why 78 people wait for direction.

**Design test:** Could a competent new manager perform this task correctly using only what is written down? If not, the capability has not been institutionalized.

**Trade-off accepted:** Documentation consumes time from people who are already overloaded. This is why Section 13 sequences documentation into the phase where escalation containment has already freed capacity.

### **Principle 2 — Distribute Decision Rights Within Explicit Boundaries**

| Decisions belong at the lowest level competent to make them — bounded by written thresholds that define exactly where authority ends and escalation begins. |
| :---- |

**Why (root cause):** E1 — all decisions route through three people, making company throughput equal to director bandwidth. But unbounded delegation would substitute one failure mode for another.

**Design test:** Can the decision owner state, without asking anyone, whether a given decision is theirs to make? If the boundary is ambiguous, it will default upward — which is the current state.

**Trade-off accepted:** Some decisions will be made worse than a founder would have made them. This is the intended price: a slightly worse decision made in one day beats a slightly better one made in three weeks.

### **Principle 3 — One Named Owner Per Outcome**

| Every outcome that matters — SLA, implementation duration, churn, pipeline, retention of a named account — has exactly one owner. Not a committee, not a function, a person. |
| :---- |

**Why (root cause):** The case describes unclear responsibility as a direct consequence of role duplication. Where three directors each partly own implementation, no one owns it.

**Design test:** For each transformation target, can we name the single individual who is accountable? If two names appear, ownership is not yet designed.

**Trade-off accepted:** Single ownership can create silos. Mitigated by the cadence in Section 11, which forces cross-functional visibility weekly rather than by committee ownership.

### **Principle 4 — Manage Outcomes, Not Presence**

| Performance is measured by delivered outcomes against defined standards — never by attendance, hours logged, or visible activity. |
| :---- |

**Why (root cause):** E2 — the company deployed an attendance application and the problem persisted. That is direct empirical evidence that presence was never the binding variable.

**Design test:** If an employee met every attendance requirement and delivered nothing, would the system detect it? Today it would not.

**Trade-off accepted:** Outcome measurement is harder to design and easier to game than attendance. Section 6 addresses gaming explicitly through paired metrics.

### **Principle 5 — Transfer Trust From People to the Institution**

| The organization — not the founder — must become the thing customers rely on. Trust is transferred through demonstrated reliability, named institutional ownership, and consistent service standards. |
| :---- |

**Why (root cause):** F1 — the case states plainly that customers buy on personal relationship with the owner and have not transferred trust to the organization. This caps sales capacity and blocks geographic expansion.

**Design test:** If a founder were unavailable for a quarter, which accounts would become at-risk? The size of that list is the measure of institutional trust.

**Trade-off accepted:** Transfer is slow and cannot be accelerated by declaration. It is measured over quarters, which is why Section 13 places its outcome in months 12–18 while starting the mechanism in month 1\.

### **Principle 6 — Governance Must Be Cheaper Than the Coordination It Replaces**

| Every meeting, report, approval, and role must remove more coordination cost than it adds. Governance that adds process without removing founder intervention has failed. |
| :---- |

**Why (root cause):** At 2.5% net margin and Rp395jt absolute profit, ServeNow cannot afford governance overhead that does not pay for itself. This is a financial constraint, not a philosophical preference.

**Design test:** For each new mechanism: what specific existing coordination does it eliminate? If the answer is "none," the mechanism is rejected.

**Trade-off accepted:** This principle deliberately blocks several standard practices — no separate PMO function, no matrix reporting, no formal committee structures. Section 15 lists what is deliberately not built.

### **Principle 7 — Sequence Capability Before Authority**

| Authority is transferred only after the receiving manager has demonstrated the judgement to exercise it — through structured coaching, shadowed decisions, and a defined competence checkpoint. |
| :---- |

**Why (root cause):** The case states subordinates depend on direction. Capability has never been exercised because authority has never been granted; granting authority instantly to people who have never used it is the most likely way this transformation fails.

**Design test:** Before a decision right transfers, has the new owner made that class of decision at least three times under supervision with the outcome reviewed?

**Trade-off accepted:** This slows delegation by roughly one quarter versus an immediate handover. Accepted deliberately: a failed delegation would set the transformation back further and would harden director scepticism about delegating at all.

# **Section 4 — Target Organizational Operating Model**

## **4.1  Challenging the Proposed Five-Layer Structure**

The brief proposes: Founders → Functional Directors → Managers / Functional Owners → Team Leads → Staff. Five layers.

| Verdict: rejected as specified. Five layers is one layer too many for a 78-person company, and the redundancy sits precisely where ServeNow can least afford it. |
| :---- |

The problem is the separation of "Founders / Executive Leadership" from "Functional Directors." At ServeNow these are the same three people. Creating both layers would either require hiring three more directors — unaffordable at 2.5% margin and unnecessary at this scale — or would produce a hollow layer that exists on the chart and not in reality, which is the current situation restated.

The correct structure is four layers, with the third conditional rather than universal:

| Layer | Population | Content | Rationale |
| ----- | ----- | ----- | ----- |
| 1\. Executive | 3 (existing directors) | Strategy, architecture standards, capital allocation, top-10 accounts, partnerships | The founders remain — their role is redesigned, not removed. See 4.4. |
| 2\. Functional Owners | 6 (new) | Own one functional outcome end-to-end with named accountability and bounded authority | This is the missing layer. Span of \~13 per Head at current size; \~28 at target size, which is why Layer 3 exists conditionally. |
| 3\. Team Leads | **\~6, conditional** | First-line supervision, shift coverage, quality review | Created only where span exceeds 12 or where 24-hour operations require shift coverage. Not created uniformly. |
| 4\. Staff | \~63 today | Execution with defined decision authority at task level | Unchanged in count; changed in that they now have a named manager and explicit authority. |

| TARGET STATE  —  Minimum Viable Management Structure   LAYER 1   \[ CEO \]        \[ CTO \]         \[ COO \]             Strategy,      Architecture,   Governance,             major accts,   security,       capacity,             partnerships   tech standards  finance                  \\             |             /                   \\\_\_\_\_\_\_\_\_\_\_\_\_|\_\_\_\_\_\_\_\_\_\_\_\_/                                |   LAYER 2      SIX FUNCTIONAL OWNERS (new layer)                                |   \+--------+--------+--------+--------+--------+--------+   |        |        |        |        |        | Head of  Head of  Head of  Head of  Head of  Head of Engin-   Delivery  Product  Customer  Sales   People & eering   (Impl.)   (Owner)  Success           Business Ops  \~25      \~20       \~2       \~20      \~4        \~7   |        |                  |   |        |                  |   LAYER 3  TEAM LEADS — only where span \>12 or 24/7 shifts   |        |                  | 2 leads  1 lead          3 shift leads                                |   LAYER 4                    STAFF Net new management positions: 6 Heads \+ \~6 Team Leads Of which external hires: 2 (Delivery, Sales). Remainder: internal promotion. |
| ----- |

## **4.2  Span-of-Control Analysis**

Team composition below is inferred: the case names five functions (technology, implementation, support, sales, administration) and states sales has 3 people, but does not size the others. Sizes are estimated proportionally to workload evidence in the case — 24-hour service for some customers implies substantial support headcount; 16–22-week implementations imply substantial delivery headcount. (Inference — flagged.)

| Function | Est. Staff Today | Span at Today | Team Leads Needed | Span at \~169 (target) |
| ----- | ----- | ----- | ----- | ----- |
| Engineering / Technology | \~25 | 25 — too wide | **2** | \~50 → 4 leads |
| Delivery / Implementation | \~20 | 20 — too wide | **1** | \~45 → 3 leads |
| Customer Success / Support | \~20 | 20 \+ 24/7 shifts | **3 (shift)** | \~45 → 4 shift leads |
| Sales & Business Development | 3 (case-stated) | 3 — fine | **0** | \~12 → 1 lead |
| Product | \~2 | 2 — fine | **0** | \~6 → 0 |
| People & Business Ops | \~7 | 7 — fine | **0** | \~10 → 0 |

**Design rule applied:** a team lead is created only when span exceeds 12 or when 24-hour coverage makes single-manager supervision physically impossible. This produces \~6 leads today rather than the \~12 a uniform structure would generate — consistent with Principle 6\.

## **4.3  Structural Changes: Problem → Change → Mechanism → Outcome**

| Current Problem | Structural Change | Mechanism | Expected Outcome |
| ----- | ----- | ----- | ----- |
| All escalations reach directors; SLA 78% | Create Head of Customer Success owning SLA end-to-end, with 3-tier escalation | Tier 1 (staff) and Tier 2 (Head of CS) contain issues; only Tier 3 — material churn risk or systemic failure — reaches a director | SLA → 96%; director time reclaimed; churn pressure reduced |
| Every technical decision waits on the CTO | Create Head of Engineering owning delivery of technical work; CTO retains architecture standards only | CTO defines the standard patterns once; Head of Engineering applies them without re-approval | Approval latency falls from weeks to days; implementation compresses |
| Scope re-negotiated per deal; 16–22-week implementations | Create Head of Product as the single owner of what is standard, configurable, and custom | Product owner adjudicates scope requests against a defined boundary rather than each deal being escalated | Implementation → 6–10 weeks (jointly with Task 2\) |
| CEO personally negotiates all pricing | Create Head of Sales owning the commercial process within a price band | Discount authority delegated to a threshold; only exceptions escalate | CEO exits routine deals; sales capacity no longer capped by founder calendar |
| No capacity planning; overtime from poor planning | Create Head of People & Business Ops owning workforce planning and the performance system | Signed deals trigger a resourcing check before commitment; capacity is forecast rather than discovered | Avoidable overtime falls; deadline reliability improves |
| Customers attached to founders personally | Assign every account a named institutional owner (CS or Sales) with the founder as escalation, not primary | Customer’s day-to-day counterpart becomes an employee, not a founder | Founder dependency falls; expansion outside Jabodetabek becomes feasible |

## **4.4  The Redesigned Founder Role**

The founders are not removed and their number does not change. Their content changes — from executing functions to governing them.

| Director | Roles Held Today | Roles Retained | Roles Transferred To |
| ----- | ----- | ----- | ----- |
| **CEO / Direktur Utama** | Sales, price negotiation, major accounts, product decisions, recruitment approval, project evaluation, operational problem-solving, certain technical decisions (8) | Strategy, capital allocation, top-10 strategic accounts, partnerships, executive escalation, external representation | Head of Sales (pricing, pipeline); Head of Product (product decisions); Head of People (recruitment); Functional Heads (project evaluation, operations) |
| **CTO / Direktur Teknologi** | Product manager, development head, system architect, technical reviewer, security owner, implementation advisor (6) | Architecture standards, security accountability, technical due diligence on major deals, technology strategy | Head of Product (product management); Head of Engineering (development, routine technical review); Head of Delivery (implementation advisory) |
| **COO / Direktur Operasional** | Implementation head, customer support head, staff scheduling, vendor management, contract administration (5) | Operating governance, capacity & financial planning, vendor strategy, cadence ownership | Head of Delivery (implementation); Head of Customer Success (support); Head of People & BizOps (scheduling, contract administration) |

| The founder-role test A director’s calendar should contain no recurring operational item. If a director attends a weekly meeting about delivery status, support queues, or individual deals, the delegation has not actually occurred — only the title has moved. Section 11 enforces this by excluding directors from the weekly operational forum entirely. |
| :---- |

# **Section 5 — Decision Rights Architecture**

This is the operative core of the transformation. Structure without decision rights is a chart; decision rights without boundaries is abdication. Twenty-two recurring decisions are specified below, each with an explicit boundary and escalation trigger.

| Governing rule Push every decision to the lowest competent level, bounded by a written threshold. Where the threshold is ambiguous, the decision defaults upward — which is exactly the current state. Ambiguity is therefore treated as a design defect, not an acceptable grey area. |
| :---- |

## **5.1  Commercial Decisions**

| Decision | Current Owner | Target Owner | Decision Boundary | Escalation Trigger | Founder Involvement |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Standard pricing within list | CEO | Head of Sales | List price to −15% discount | Discount \>15%, or non-standard payment terms | None below trigger |
| Non-standard discount / strategic pricing | CEO | CEO | \>15% discount; multi-year concessions | — (already executive) | Decision owner |
| Deal qualification / bid-no-bid on tender | CEO ad hoc | Head of Sales | Deals within standard product scope and served sectors | Deal requires \>2 weeks custom development, or a new sector | Consulted at trigger |
| Proposal & scope commitment to customer | CEO / CTO | Head of Sales \+ Head of Delivery (joint sign-off) | Scope drawn from standard/configurable catalogue | Any element outside the catalogue | Notified; approves only at trigger |
| Contract terms & legal exceptions | CEO | Head of Sales within standard template | Standard template, standard SLA, standard liability | Any deviation from template; liability or IP terms | Approves deviations |
| Strategic / top-10 account relationship | CEO personally | CEO retains; Head of CS owns day-to-day | Top-10 by revenue remain founder-sponsored | Churn risk flagged by Head of CS | Retained deliberately — see §15 |
| Partnership & reseller agreements | CEO | CEO | All partnership commitments | — | Decision owner |

## **5.2  Delivery & Product Decisions**

| Decision | Current Owner | Target Owner | Decision Boundary | Escalation Trigger | Founder Involvement |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Implementation kickoff & resourcing | COO | Head of Delivery | Any project within standard packages | Project needs resources beyond planned capacity | None below trigger |
| Change request within project | CTO / COO | Head of Delivery | Change ≤ 5 person-days, no architectural impact | \>5 person-days, or architectural change | Notified via monthly review |
| Customization approval | CTO | Head of Product | Configurable-tier: approved. Custom-tier ≤2 weeks: approved with pricing. | Custom work \>2 weeks effort, or a request that should become standard product | CTO consulted on architecture only |
| Promotion of custom work into standard product | Nobody — does not occur | Head of Product | Recurring requests (3+ customers) enter the standard roadmap | Change alters product positioning or pricing model | CEO/CTO approve at quarterly review |
| Quarterly roadmap prioritization | CTO ad hoc | Head of Product proposes; Executive approves | Prioritization within approved capacity envelope | Strategic reallocation between product lines | Approve quarterly, not continuously |
| Technical architecture — applying standards | CTO | Head of Engineering | Any solution using approved architectural patterns | New pattern, new core technology, or security-sensitive design | CTO owns the standard, not each application |
| Technical architecture — setting standards | CTO | CTO | Defining approved patterns and platforms | — | Decision owner |
| Security incident response | CTO | Head of Engineering (containment) | Containment and remediation per playbook | Customer-data exposure or regulatory implication | CTO immediate, at any hour |

## **5.3  Service & Customer Decisions**

| Decision | Current Owner | Target Owner | Decision Boundary | Escalation Trigger | Founder Involvement |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Support resolution — Tier 1 | Escalates to directors | Support staff | Documented playbook cases | No resolution within SLA window | None |
| Support escalation — Tier 2 | Directors | Head of Customer Success | Non-standard issues; SLA breach recovery | Material churn risk, or systemic defect affecting 3+ customers | None below trigger |
| Executive escalation — Tier 3 | Undefined; all reach board | COO (operational) / CEO (relationship) | Churn risk on a material account; systemic failure | — | Deliberate and rare — the point of the tier |
| SLA credit / service remediation | CEO | Head of Customer Success | Credits within a published remediation schedule | Credit exceeding schedule, or contract renegotiation | Approves beyond schedule |
| Shift scheduling & 24/7 coverage | COO | Head of Customer Success | Within approved headcount and overtime budget | Structural understaffing requiring new hires | None below trigger |

## **5.4  Organizational & Financial Decisions**

| Decision | Current Owner | Target Owner | Decision Boundary | Escalation Trigger | Founder Involvement |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Hiring — non-managerial, budgeted | CEO | Functional Head \+ Head of People | Within approved headcount plan and salary band | Outside band, or unbudgeted position | None below trigger |
| Hiring — managerial (Head / Team Lead) | CEO | Executive (CEO \+ relevant director) | All management appointments | — | Decision owner — retained deliberately |
| Performance rating, improvement plan, exit | Nobody formally | Functional Head; Head of People assures process | Within the performance framework | Termination; any legal exposure | Notified; approves terminations |
| Operating spend within budget | CEO / COO | Functional Head | Within approved functional budget envelope | Any unbudgeted spend, or exceeding envelope | None below trigger |
| Vendor selection & renewal | COO | Head of Delivery / relevant Head | Within budget, standard terms, existing categories | New vendor category; material contract value; data-processing vendors | COO approves at trigger |

## **5.5  Delegation Summary — What Actually Moves**

| Director | Decisions Held Today | Decisions Retained | Net Change |
| ----- | ----- | ----- | ----- |
| **CEO** | Pricing (all), deal qualification, contracts, proposals, all accounts, partnerships, all hiring, budget, product decisions | Strategic pricing exceptions, contract deviations, partnerships, top-10 accounts, management hiring, unbudgeted spend | **\~9 categories → 6, and 5 of the 6 are exception-triggered rather than routine** |
| **CTO** | Architecture (setting and applying), all technical review, customization approval, product management, security, implementation advisory | Architecture standards, security accountability, technical due diligence on major deals | **\~6 categories → 3, with the routine volume removed entirely** |
| **COO** | Implementation kickoff, all escalations, scheduling, vendor management, contract administration, budget | Operating governance, capacity planning, vendor strategy, Tier-3 operational escalation | **\~6 categories → 4, all now exception-based** |

| The critical design feature Notice that founders retain a meaningful number of decision categories — this is intentional. What changes is not primarily how many decisions they own, but that nearly all retained decisions are exception-triggered rather than routine. A CEO who approves discounts above 15% touches perhaps a handful of deals per quarter; a CEO who approves all pricing touches every deal. The volume, not the category count, is what frees capacity. |
| :---- |

# **Section 6 — Performance Management System**

The instruction "implement KPIs" is precisely the kind of recommendation that produced the attendance app. What follows is an architecture: what is measured, by whom, against what target, reviewed in which forum, and with what corrective action.

| THE PERFORMANCE CASCADE   COMPANY   Employees/Customer 1.86 → ≤1.41    (north star)             Margin 2.5% → 15–20%  ·  Churn 16.7% → \<5%                               |                               v   FUNCTION  Each Head owns ONE primary outcome metric             \+ one counter-metric that prevents gaming                               |                               v   TEAM      Operational drivers of the function metric             Weekly visibility, lead-time based                               |                               v   INDIVIDUAL  3–5 metrics: output, quality, reliability               No attendance metrics at any level  |
| ----- |

## **6.1  Company Level**

| KPI | Type | Definition | Owner | Target | Frequency | Review Forum |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **Employees per Customer** | Lagging | Total headcount ÷ active customers | CEO | 1.86 → ≤1.41 | Quarterly | Quarterly Strategy Review |
| Decisions Resolved Below Director Level | Leading | % of logged decisions/escalations closed without director involvement | COO | \~0% → majority | Monthly | Monthly Business Review |
| Net margin | Lagging | Net profit ÷ revenue | CEO | 2.5% → 15–20% | Quarterly | Quarterly Strategy Review |
| Churn rate | Lagging | Customers lost ÷ opening customers | Head of CS | 16.7% → \<5% | Monthly | Monthly Business Review |
| SLA attainment | Lagging | % of service commitments met | Head of CS | 78% → ≥96% | Weekly | Weekly Ops Sync |

## **6.2  Functional Level — One Outcome \+ One Counter-Metric**

Every functional metric is paired with a counter-metric. This is deliberate: any single metric can be improved by damaging something else, and paired metrics make that trade visible rather than invisible.

| Function | Primary Outcome Metric | Counter-Metric (anti-gaming) | Target | Frequency | Corrective Action Trigger |
| ----- | ----- | ----- | ----- | ----- | ----- |
| **Customer Success** | SLA attainment | Churn rate — prevents closing tickets without resolving problems | ≥96% / \<5% | Weekly / Monthly | Two consecutive weeks below 90% → root-cause review at Ops Sync |
| **Delivery** | Implementation cycle time | Post-go-live defect rate in first 60 days — prevents rushing | ≤10 wks | Per project | Any project exceeding 12 weeks → written variance analysis |
| **Engineering** | Decision/approval turnaround time | Rework rate — prevents fast but wrong approvals | ≤3 days | Weekly | Median \>5 days for two weeks → capacity or authority review |
| **Product** | Standard-Scope Ratio (% of delivery from reusable assets) | Win rate — prevents standardizing so hard the product stops winning deals | Rising | Monthly | Ratio flat for a quarter → escalate to Quarterly Review |
| **Sales** | Qualified pipeline coverage vs. target | Churn of accounts sold in last 12 months — prevents selling bad-fit deals | ≥3× | Weekly | Coverage \<2× for a month → pipeline intervention |
| **People & BizOps** | Capacity forecast accuracy | Voluntary attrition — prevents fixing capacity by overworking people | ±15% | Monthly | Variance \>25% → planning process review |

## **6.3  Team and Individual Level**

| Level | Design Rule | Example (Delivery) | Review Mechanism | Corrective Action |
| ----- | ----- | ----- | ----- | ----- |
| Team | 2–3 metrics that are operational drivers of the functional outcome — things the team controls directly | On-time milestone completion; scope-change volume; resource utilization vs. plan | Weekly 15–30 min team check-in run by the Head or Lead | Blocker logged and either resolved by the Head or escalated once, with a named owner |
| Individual | 3–5 metrics covering output, quality, and reliability. Never attendance. Never activity volume alone. | Assigned deliverables completed to standard; defect rate on own work; commitment reliability (met vs. made) | Monthly 1:1 with direct manager — not with a director | Structured coaching first; documented improvement plan if unresolved after two cycles; role or exit decision after that |

## **6.4  Leading vs. Lagging — and Why the Split Matters**

| Leading Indicators (weekly, actionable) | Lagging Indicators (monthly/quarterly, confirmatory) |
| ----- | ----- |
| Decision/approval turnaround time | Employees per customer |
| Decisions resolved below director level | Net margin |
| Standard-Scope Ratio | Churn rate |
| Qualified pipeline coverage | Revenue per employee |
| On-time milestone completion | Revenue outside Jabodetabek |
| Capacity forecast accuracy | Recurring revenue mix |

**Why this split is enforced:** ServeNow currently manages exclusively on lagging data that arrives annually — by which point the year is decided. Every leading indicator above is observable weekly and is directly actionable by a named Head. The lagging indicators are for the board, not for management.

## **6.5  Metrics Deliberately Excluded**

| Rejected Metric | Why Rejected |
| ----- | ----- |
| Attendance / punctuality | Already tried; it failed. Presence was never the binding variable — the case attributes overtime to poor planning, not absence. |
| Hours worked / utilization as a performance measure | Rewards the overtime the company is trying to eliminate. Utilization is retained only as a capacity-planning input, never as an individual performance metric. |
| Number of tickets closed (unpaired) | Directly gameable — closing tickets without resolution improves it. Retained only when paired with churn and reopen rate. |
| Lines of code / features shipped | Measures activity, not leverage. Would actively reward the fragmentation the transformation is trying to end. |
| Revenue per employee as a north star | Improves by firing people or by taking more high-priced custom work — the exact behaviour that caused the margin problem. Retained as a guardrail only. |

# **Section 7 — Employee Discipline & Accountability**

## **7.1  Why the Attendance App Failed — Diagnostic**

This is the single most instructive fact in the case, because it is a controlled experiment the company already ran. A tool was deployed against the visible symptom, and the symptom persisted. That result eliminates several hypotheses.

| Candidate Cause | Verdict | Reasoning from the Case |
| ----- | ----- | ----- |
| Unclear expectations | **CONFIRMED — primary** | No system connects discipline, targets, work quality, and individual responsibility. Employees cannot meet a standard that has never been articulated. |
| Weak managerial accountability | **CONFIRMED — primary** | There are no managers. With \~26 staff per director across unrelated functions, no one is positioned to notice, coach, or correct. |
| Poor performance visibility | **CONFIRMED — primary** | Individual output is invisible; only attendance was ever measured. Invisible work cannot be managed. |
| Workload imbalance / planning failure | **CONFIRMED** | The case attributes overtime specifically to poor planning. Some "lateness" and missed deadlines are capacity failures misread as behaviour. |
| Unclear role ownership | **CONFIRMED** | Directors’ overlapping roles produce ambiguous responsibility; ambiguity at the top propagates downward. |
| Weak consequences | **PARTIAL** | True, but downstream — consequences cannot attach to standards that do not exist. Fixing consequences first would punish people for an unmanaged system. |
| Incentive design | **NOT SUPPORTED** | The case provides no evidence on compensation or incentive structure. Not asserted. |
| Culture | **REJECTED as primary** | Culture is the usual explanation and is almost certainly wrong here. The flexible culture worked at \~10 people and failed at 78 — the variable that changed is scale, not character. |

| Diagnostic conclusion The attendance app failed because it measured the one thing that was never the problem. It answered "was this person present?" when the unanswered questions were "what was this person supposed to deliver, to what standard, by when, and who noticed when they didn’t?" A second tool aimed at the same symptom would fail identically. |
| :---- |

## **7.2  The Six-Component Accountability System**

| Component | What It Is | Concrete Mechanism at ServeNow | Owner |
| ----- | ----- | ----- | ----- |
| **1\. Expectations** | Every role has a written statement of deliverables, quality standards, and decision authority | A one-page role charter per position — not a job description. Includes: outcomes owned, decisions authorised, standards applied, escalation path. | Head of People, with each Functional Head |
| **2\. Measurement** | 3–5 individual metrics covering output, quality, reliability | Drawn from the Section 6 cascade so individual metrics roll up to functional outcomes. No attendance metric at any level. | Functional Head |
| **3\. Manager Ownership** | One named manager responsible for each person’s performance | The Layer 2/3 structure. This is why the management layer is a prerequisite — accountability without a manager is a policy document nobody enforces. | Functional Head |
| **4\. Feedback** | Regular, structured, two-way — not annual | Monthly 1:1 with the direct manager. Weekly team check-in surfaces blockers. Feedback flows both ways: managers report upward what is blocking their teams. | Functional Head / Team Lead |
| **5\. Consequences** | Graduated, documented, predictable | Coaching → documented improvement plan after two unresolved cycles → role change or exit. Applied consistently, which requires the standard to exist first. | Functional Head; Head of People assures process |
| **6\. Recognition** | Visible reward for the behaviours the transformation needs | Explicitly recognise: decisions made well without escalation; customer issues resolved at Tier 1; work that becomes reusable by others. These reward the transformation, not just output. | Functional Head; Executive at quarterly forum |

## **7.3  Why This Beats Another Tool**

| Dimension | Attendance Tool | Accountability System |
| ----- | ----- | ----- |
| What it measures | Presence — a proxy that correlates weakly with contribution | Delivered outcomes against a defined standard |
| Addresses the real cause? | No — aimed at a symptom | Yes — aimed at unclear expectations, absent managers, invisible output |
| Handles the planning problem | No — records overtime, does not prevent it | Yes — capacity forecasting prevents the overload that generates it |
| Enables delegation | No | Yes — makes delegated outcomes visible, which is the precondition for founders letting go |
| Effect on the north-star metric | None | Direct — productivity becomes manageable, which is the only route to employees/customer falling |
| Failure mode | Employees comply with the metric and nothing improves — already observed | Metrics gamed if unpaired — mitigated by the counter-metric design in §6.2 |

**Sequencing note:** components 1–3 must be built before 4–6 can operate. Expectations without measurement are aspirations; measurement without a manager is a spreadsheet nobody reads. This is why the roadmap places role charters and the management layer in months 0–3, and consequences only from month 6 — applying consequences before standards exist would be both unfair and counterproductive.

# **Section 8 — Management Layer & Key Roles**

Six roles are proposed. Each is justified by a specific diagnosed failure, not by organizational convention. Roles considered and rejected appear in §8.3.

## **8.1  The Six Functional Owner Roles**

| Role | Why Needed | Problem Solved | Decisions Owned | KPIs | Timing / Source |
| ----- | ----- | ----- | ----- | ----- | ----- |
| **Head of Customer Success** | SLA at 78% with no owner; escalations reach the board; churn 16.7% consuming 44% of new logos | No one below director level owns retention or service reliability | Tier-2 escalation; SLA remediation within schedule; shift scheduling | SLA ≥96%; churn \<5% (counter-metric) | **Month 0–2 · Internal promotion (support lead)** |
| **Head of Delivery** | Implementation 16–22 wks; COO personally heads implementation; no capacity planning | Delivery has no owner; projects begin under-resourced because no forecast exists | Project kickoff & resourcing; change requests ≤5 person-days; vendor selection | Cycle time ≤10 wks; 60-day defect rate (counter) | **Month 0–2 · External hire** |
| **Head of Engineering** | CTO is simultaneously architect, reviewer, approver, security owner — single-point approval on all technical work | Approval queue is the mechanism behind long implementation | Applying approved architecture patterns; routine technical review; security containment | Approval turnaround ≤3 days; rework rate (counter) | **Month 2–4 · Internal promotion (senior engineer)** |
| **Head of Product** | 16 unprioritized directions; product management is 1 of 6 CTO roles; nobody decides what is standard | Scope is re-negotiated per deal because no boundary exists; custom work never becomes product | Customization tier approval; promotion of custom → standard; roadmap proposal | Standard-Scope Ratio rising; win rate (counter) | **Month 2–3 · Internal promotion (Senior Business Analyst / Senior Engineer) — see §8.2** |
| **Head of Sales** | CEO personally negotiates all pricing and handles major accounts; 3-person team with no process | Sales capacity is capped by the CEO’s calendar; no forecast means delivery cannot plan | Pricing to −15%; bid/no-bid; contract within template | Pipeline coverage ≥3×; 12-month churn on new accounts (counter) | **Month 2–4 · External hire** |
| **Head of People & Business Ops** | No performance system; no capacity planning; overtime from poor planning; COO handles scheduling and contract admin | The performance architecture and capacity forecasting have no owner — without one, §6 and §7 never get built | Non-managerial hiring within band; performance process assurance | Capacity forecast accuracy ±15%; attrition (counter) | **Month 0–3 · Internal, possibly part-time initially** |

## **8.2  Prioritization by Leverage**

Revised from three to four roles in the first quarter, after external review identified a chicken-and-egg problem in the original sequencing (detailed in the box below). All four are either free (internal promotion) or the single highest-leverage external hire, so cost discipline from §8.5–§8.7 is preserved.

| Priority | Role | Leverage Argument |
| ----- | ----- | ----- |
| **1** | Head of Customer Success | Attacks the fastest-moving damage. Churn compounds: every quarter at 16.7% raises the acquisition burden. Also produces the earliest visible win (SLA), which builds organizational confidence in the transformation. |
| **2** | Head of Delivery | Owns the metric with the largest single effect on employees-per-customer. Implementation duration is the primary consumer of delivery capacity. The one external hire in this cohort — see §8.5 for the staggered, performance-gated hiring design. |
| **3** | Head of Product | Added to the first cohort on revision. Internal promotion from Senior Business Analyst or Senior Engineer — zero net new cash cost. Without an owner from month 2–3, nobody drives product standardization through H1 and Task 2 has no counterpart to work with (see box below). |
| **4** | Head of People & Business Ops | The enabler. Without this role, the performance architecture and capacity planning are never built — and every other Head then manages without instruments. Cheapest of the four, and can start part-time. |

| Self-critique flagged after external review: the Head of Product chicken-and-egg problem The document originally deferred Head of Product to month 6–9, reasoning that Task 2 must define product boundaries before the role has substance. External review correctly identified the flaw: if nobody owns product from month 0–6, one of two things happens — either the CTO remains the de facto product manager, which is precisely the overload §4.4 exists to remove, or nobody drives it and Task 2 stalls for two full quarters. Corrected position: Head of Product is appointed in month 2–3, before boundaries are defined — not after. The role’s first mandate is not to arrive with authority over a finished catalogue, but to build it: inventory recurring customization requests (using the single source of truth from §10), and co-develop the standard/configurable/custom package tiers jointly with the Task 2 team through month 6\. This makes the Head of Product a driver of the boundary-definition work rather than a recipient waiting for it to finish. |
| :---- |

## **8.3  Roles Deliberately NOT Created**

| Role Considered | Rejected Because |
| ----- | ----- |
| Chief of Staff | Would absorb director workload without redistributing authority — it makes founder dependency more efficient rather than reducing it. Directly contradicts the transformation objective. |
| PMO function | Adds a coordination layer at a company whose problem is too much coordination through too few people. Project governance is embedded in the Head of Delivery role instead. |
| Separate Head of Support and Head of Customer Success | Splits a single outcome — service reliability and retention — across two owners, violating Principle 3\. Combined until scale forces separation (\~90+ customers). |
| Head of Marketing | Legitimate need, but sequenced under Task 3 and dependent on a documented sales process existing first. Creating it now would generate demand the company cannot capture or deliver. |
| Regional managers | Premature. Geographic expansion requires standardized remote delivery, which is a Task 2 dependency. Creating regional structure before deliverable standardization would export the current failure mode. |
| Quality Assurance Manager | Quality accountability is embedded in the counter-metric design (§6.2) rather than given a separate owner. A dedicated QA function at 78 people would violate Principle 6\. |

## **8.4  Hiring vs. Promotion — and the Cost Question**

| Consideration | Position Taken |
| ----- | ----- |
| Balance | Four of six roles filled by internal promotion; two by external hire (Delivery, Sales). Rationale: internal promotion preserves customer and product context and moves faster; external hiring is reserved for the two functions where the case shows no existing process discipline to promote from. |
| Cost discipline | Net new headcount is approximately 2 (the external hires); the other four are role redesignations plus a promotion premium. This is deliberately minimal at 2.5% net margin — but minimal headcount is not the same as affordable cash flow. See §8.5 for the Year-1 cash-flow risk this still creates and the remuneration design that manages it. |
| Funding source | Partly self-funding: the case attributes overtime to poor planning, and capacity forecasting reduces avoidable overtime cost. The exact figure is not disclosed in the case and is not estimated here. This is directional, not a guarantee — see §8.5. |
| Capability risk | **The largest risk in this document.** Internal promotees have never exercised decision authority — the case states subordinates depend on direction. Principle 7 (capability before authority) applies, operationalized as the Shadow-to-Solo Gate in §8.6. |

## **8.5  Stress-Test: Can ServeNow Actually Afford Two External Heads?**

| Self-critique flagged after external review §8.4 as originally drafted called the structure affordable and self-funding. That claim was under-stressed. At Rp395jt total net profit, two senior external hires (Head of Sales, Head of Delivery) in a Jakarta B2B SaaS market carry real cash-flow risk in Year 1, before overtime savings or sales uplift have had time to materialize. |
| :---- |

*The case discloses no salary data, so no case-derived figure is claimed here. As external market context — not a case fact — senior B2B SaaS Sales and Delivery leadership in Jakarta commonly command total compensation in the tens of millions of rupiah per month each. Two such hires, fully loaded, are a material fraction of ServeNow’s entire Year-3 net profit. Fixed-salary hiring of both roles simultaneously in months 0–2 would plausibly push Year-1 profit negative before the transformation has produced any offsetting benefit.*

| Design Response | Mechanism |
| ----- | ----- |
| **Variable-weighted compensation, not fixed salary** | Head of Sales: below-market fixed base, with the majority of target compensation delivered as commission on cash collected and gross margin — not contract value. This ties cost directly to realized cash, not booked revenue, so the role cannot generate fixed cost without generating cash first. |
| **Performance-gated bonus for Delivery** | Head of Delivery: below-market fixed base, with a material performance bonus released only when average implementation cycle time reaches the ≤10-week target. This links the single highest fixed-cost hire directly to the metric it exists to move. |
| **Transition budget from existing spend, not new spend** | Funded from vendor contract renegotiation and internal license consolidation rather than new capital — both within COO authority under §5.4 and requiring no external funding round. |
| **Staggered start, not simultaneous** | Head of Delivery starts month 0–2 (highest leverage on employees-per-customer). Head of Sales start is conditional on the Weekly Ops Sync and escalation tiers being live — hiring a sales leader into a company that cannot yet deliver reliably would only accelerate churn. |

***What this does not claim:** this design reduces but does not eliminate Year-1 cash-flow risk. If judges press on affordability, the honest answer is that this is the single most financially exposed decision in the plan, and variable-weighted compensation is a mitigation, not a guarantee.*

## **8.6  The Shadow-to-Solo Gate — Replacing "90-Day Coaching" With a Mechanism**

| Self-critique flagged after external review "90-day structured coaching" as originally stated did not answer who coaches. If founders coach, their calendar is not actually freed — the same problem relocated under a new name. If an external coach is hired, cost is unaddressed. The case is explicit that subordinates have three years of dependence on direction; 90 undifferentiated days of "coaching" will not reverse that alone. |
| :---- |

The coaching mechanism is replaced with a staged, dated authority transfer — the Shadow-to-Solo Gate — so founder time is a declining input on a fixed schedule, not an open-ended commitment.

| Weeks | Decision Pattern | Founder Time Required | Gate to Next Stage |
| ----- | ----- | ----- | ----- |
| **1–4** | Founder decides; new Head documents the rationale in the decision log | High — founder still deciding, but now narrating why, which is the actual teaching mechanism | Head correctly predicts the founder’s decision in writing, before being told, on 3 consecutive cases |
| **5–8** | Head proposes a decision with rationale; founder critiques and approves or redirects | Medium — review only, not origination. Founder time first begins to fall here | Head’s proposals are approved without material redirection on 3 consecutive cases |
| **9–12** | Head decides within the §5 thresholds; founder audits a sample after the fact via the live dashboard (§10) | Low — periodic audit, not real-time review | Audit finds no material error over the 4-week window → full authority transfers |

This directly answers "who coaches": founders coach, but their per-decision time is designed to fall by roughly two-thirds between weeks 1–4 and weeks 9–12 on a fixed 12-week clock — rather than an indefinite mentoring commitment competing with the rest of the turnaround.

| Additional Mechanism | Design |
| ----- | ----- |
| **Fractional external advisor** | For the two roles with the least internal precedent to promote from — Head of Customer Success and Head of Engineering — a part-time external advisor is engaged, compensated in advisory equity rather than cash. This adds an experienced second opinion without adding to the cash burden flagged in §8.5, and without consuming further founder time. |

# **Section 9 — Customer Trust Transfer**

The case states directly that some customers buy on the basis of a personal relationship with the owner and have not fully transferred trust to ServeNow as an institution. This is not a soft issue — it is a hard constraint on three transformation targets simultaneously.

## **9.1  Why This Is a Scalability Constraint, Not a Relationship Nicety**

| Constraint | Mechanism | Target Blocked |
| ----- | ----- | ----- |
| Sales capacity is capped by founder calendar | If the founder must be present to close, the acquisition ceiling is the founder’s available hours — not the size of the sales team | Customers 42 → 120 (requires \~29–38 gross adds/year vs. \~16 today) |
| Geographic expansion is physically bounded | Relationship-led origination requires presence. Founders cannot be present outside Jabodetabek at the required frequency | Revenue outside Jabodetabek 12% → 40% (a 9.5× increase) |
| Delegation is blocked at the customer interface | Directors cannot hand accounts to staff whom the customer does not know or trust | Director dependency: High → Low |
| Revenue is silently fragile | Relationship-based revenue survives only while founder attention persists — and that attention is precisely what growth is consuming | Churn 16.7% → \<5% |

## **9.2  Ten Transfer Mechanisms**

| Mechanism | How It Works | How It Reduces Founder Dependency | Phase |
| ----- | ----- | ----- | ----- |
| **1\. Named account ownership** | Every account is assigned a named institutional owner (CS for existing, Sales for new). Introduced formally to the customer by the founder. | Converts the customer’s day-to-day counterpart from a founder to an employee — the single highest-impact mechanism | 0–3 mo |
| **2\. Founder-sponsored handover** | The founder personally introduces the new owner and states publicly that this person now has authority to decide | Trust is transferred by the trusted party rather than asserted by the newcomer. Without this, handover reads as demotion of the relationship | 0–3 mo |
| **3\. Institutional customer record** | Every interaction, commitment, issue, and preference recorded in a shared system rather than in personal notes or WhatsApp | Removes the founder’s informational monopoly — currently the real reason only they can serve certain accounts | 0–6 mo |
| **4\. Published service commitments** | Written SLA, response times, and escalation paths given to every customer | Replaces "call the owner and it gets fixed" with a documented promise the organization keeps | 3–6 mo |
| **5\. Executive escalation protocol** | A defined path to a director — rare, triggered, and explicitly framed as exceptional | Preserves the customer’s sense of access while removing the founder from routine contact. Access is retained; dependency is not | 0–3 mo |
| **6\. Standardized QBR** | Quarterly business review per material account, run by the account owner using a standard pack | Institutionalizes the strategic conversation founders currently hold informally | 3–9 mo |
| **7\. Backup account ownership** | Every account has a documented secondary owner briefed on context | Removes single-person dependency at the employee level too — avoids recreating the founder problem one layer down | 6–12 mo |
| **8\. Relationship mapping** | Map which ServeNow person knows which customer stakeholder; deliberately broaden thin relationships | Makes founder-dependency measurable and targetable per account rather than a general anxiety | 3–6 mo |
| **9\. Proof points & case studies** | Documented outcomes by sector, usable by any salesperson | Lets a non-founder establish credibility with evidence rather than personal history. Directly enables Task 3 | 6–12 mo |
| **10\. Consistent communication standards** | Defined tone, response times, reporting formats across all customer touchpoints | Makes the experience feel institutional and predictable rather than dependent on who answers | 3–6 mo |

## **9.3  The Measurement**

| Founder Dependency Index — per account For each account, score: (a) does a named non-founder own it? (b) is the full history in the shared record? (c) has the customer had substantive contact with a non-founder in the last 90 days? (d) is there a documented backup owner? The proportion of revenue in accounts scoring 4/4 is the operational measure of "Ketergantungan direksi: Tinggi → Rendah." This converts the case’s qualitative target into something reviewable monthly. |
| :---- |

**Deliberate exception — see §15:** the top-10 accounts by revenue remain founder-sponsored. Removing the founder from the largest relationships during a period of service instability would be reckless. The objective is that founder involvement in these accounts becomes *strategic and periodic* rather than operational and constant — not that it disappears.

# **Section 10 — Information & Management System**

| Design objective A manager must be able to understand the state of the business without asking a founder. Today this is impossible — which is a substantial part of why founders cannot step back. |
| :---- |

## **10.1  The Governance of Information — Six Domains**

The emphasis is deliberately on governance rather than software selection. A tool without ownership rules reproduces the current fragmentation in a nicer interface.

| Domain | What Is Centralized | Owner | Updated By / Frequency | Access | Decisions That Depend On It |
| ----- | ----- | ----- | ----- | ----- | ----- |
| **Customer record** | Contacts, contract terms, service history, commitments made, open issues, relationship map, account owner \+ backup | Head of Customer Success | Account owner, at every material interaction | All customer-facing staff; Heads; Executive | Escalation handling; renewal risk; account reassignment; QBR content |
| **Sales pipeline** | Opportunities, stage, value, expected close, next action, owner — replacing spreadsheets, WhatsApp, email, personal notes | Head of Sales | Salesperson, weekly minimum | Sales; Delivery (for capacity); Executive | Forecast; delivery capacity planning; hiring timing; pricing exceptions |
| **Delivery & implementation** | Project status, milestones, scope changes, effort actual vs. planned, blockers, go-live date | Head of Delivery | Project owner, weekly | Delivery; CS; Sales; Executive | Resourcing; change approval; realistic commitments to new customers |
| **Service & SLA** | Tickets, response and resolution times, SLA attainment, escalation tier, recurring defect patterns | Head of Customer Success | Support staff, continuously | CS; Engineering; Product; Executive | Tier-2/3 escalation; remediation credits; product defect prioritization |
| **Product & scope** | Standard / configurable / custom catalogue; customization requests and frequency; roadmap status | Head of Product | Product owner, at each request and monthly review | All Heads; Executive | Customization approval; promotion of custom to standard; roadmap |
| **People & capacity** | Roles, role charters, individual metrics, capacity forecast vs. committed work, skills | Head of People & BizOps | Functional Heads, monthly | Heads (own function); Executive | Hiring; resourcing; performance action; overtime prevention |

## **10.2  Governance Rules**

* **Single-entry rule:** each fact is recorded in exactly one place. Where information lives in two systems, one is authoritative and the other is explicitly derivative. This directly attacks the fragmentation the case describes.

* **Owner-updates rule:** the person who owns the outcome updates the record. Information maintained by someone other than the accountable owner degrades within weeks.

* **Decision-linkage rule:** if no decision depends on a data field, it is not collected. This prevents the reporting bloat that Principle 6 forbids.

* **Default-open access:** all Heads see all domains. Restricting information to functional silos would recreate at Layer 2 exactly the informational monopoly the transformation is dismantling at Layer 1\.

* **Meeting-input rule:** no forum in §11 may require a status document prepared specially for it. Every review runs off the live record — otherwise the reporting burden becomes the new coordination cost.

| The dogfooding opportunity ServeNow sells ticketing, knowledge management, quality monitoring, SLA monitoring, and a Customer 360 view — while running its own operations on spreadsheets, WhatsApp, email, and personal notes. Running the service and customer domains on ServeNow’s own platform solves the information problem, requires no new vendor spend, and produces a credibility asset for Task 3\. It also gives the product team a permanent internal user — the fastest available feedback loop. |
| :---- |

# **Section 11 — Governance Cadence**

The purpose of cadence is to replace ad-hoc founder intervention with predictable institutional mechanisms. If a problem has a scheduled forum with a named owner, it does not need a founder to notice it.

## **11.1  The Four Rhythms**

| Forum | Frequency | Participants | Agenda | Metrics Reviewed | Decisions Made | Escalations | Output |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **Daily Standup** | Daily, 10 min | Within each team, run by Lead or Head | Today’s commitments; blockers only | Open blockers; at-risk SLA tickets | Task-level reallocation | Blocker unresolved \>24h → Weekly Ops | Blocker list with named owners |
| **Weekly Ops Sync** | Weekly, 45 min | 6 Functional Heads only. — NO DIRECTORS | Cross-functional delivery, service, and pipeline; capacity conflicts | SLA; implementation cycle time; approval turnaround; pipeline coverage | Resource reallocation across functions; Tier-2 resolution | Tier-3 items → named director, same day | Decisions logged; escalation list |
| **Monthly Business Review** | Monthly, 90 min | 6 Heads \+ 3 Directors | Performance vs. target by function; churn and retention; capacity vs. forecast | Churn; SLA trend; decisions below director level; capacity accuracy; margin trend | Corrective action on off-track metrics; hiring approvals | Structural issues → Quarterly | Action register with owners and dates |
| **Quarterly Strategy Review** | Quarterly, half day | 3 Directors \+ Heads as relevant | Progress on transformation targets; roadmap prioritization; resource allocation | Employees per customer; margin; recurring mix; Standard-Scope Ratio; Founder Dependency Index | Roadmap priorities; budget envelopes; structural changes | — | Quarterly priorities; updated targets |

## **11.2  The Design Decision That Matters Most**

| Directors are excluded from the Weekly Ops Sync. This is the mechanism, not an oversight. If directors attend the weekly operational forum, every operational decision will route to them inside that meeting — delegation will have been formally announced and practically reversed. The exclusion is what forces the six Heads to actually resolve cross-functional conflicts among themselves. Directors receive the decision log; they do not attend. *This single rule is the most reliable observable test of whether the transformation is real. If directors are attending Ops Sync in month 6, the delegation has failed regardless of what the org chart says.* |
| :---- |

## **11.3  Cadence Discipline Rules**

* **Every forum has a defined decision output.** A meeting that produces only information is replaced by a written update. This is Principle 6 applied to calendars.

* **Escalation carries a name and a deadline.** "Escalated to management" is not an outcome. "Escalated to COO, decision required by Thursday" is.

* **No forum requires bespoke preparation.** All reviews run off the live record from §10.

* **Total management meeting load:** approximately 45 minutes weekly plus 90 minutes monthly for each Head. Deliberately modest — the objective is to remove coordination cost, not relocate it into meetings.

# **Section 12 — Target Operating Model Integration**

This is the conceptual core of Task 1\. The six governance components are not parallel initiatives — each is the precondition for the next. Implemented out of order, the chain breaks.

| THE INTEGRATED OPERATING MODEL   \[1\] ORGANIZATIONAL STRUCTURE   — 6 Functional Owners created                  |  creates someone to receive authority                  v   \[2\] DECISION RIGHTS           — 22 decisions bounded & moved                  |  authority without measurement is unsafe                  v   \[3\] ACCOUNTABILITY            — one named owner per outcome                  |  ownership needs instruments                  v   \[4\] PERFORMANCE MANAGEMENT    — 4-tier cascade, paired metrics                  |  metrics need a source of truth                  v   \[5\] INFORMATION FLOW          — 6 domains, single-entry                  |  data needs a forum to be acted on                  v   \[6\] MANAGEMENT CADENCE        — daily/weekly/monthly/quarterly                  |                  v   \[7\] EXECUTION RELIABILITY     — SLA 78% → 96%                  v   \[8\] LOWER FOUNDER DEPENDENCY  — routine decisions stop escalating                  v   \[9\] LOWER HUMAN EFFORT/CUSTOMER — less rework, less waiting                  v  \[10\] OPERATING LEVERAGE        — employees/customer 1.86 → ≤1.41                  v  \[11\] SCALABLE GROWTH           — Rp45B at 15–20% margin  |
| ----- |

## **12.1  Explaining Every Link**

| Link | Why It Holds | What Breaks If Skipped |
| ----- | ----- | ----- |
| **\[1\] → \[2\]  Structure enables decision rights** | Authority requires a recipient. Six Functional Owners create the positions to which decisions can move. | Decision rights "delegated" with no manager layer default back to directors within weeks — the current state with new paperwork. |
| **\[2\] → \[3\]  Decision rights create accountability** | A person who cannot decide cannot be accountable. Bounded authority is what makes ownership meaningful rather than nominal. | Managers are blamed for outcomes they had no authority to influence — the fastest way to lose the first cohort of Heads. |
| **\[3\] → \[4\]  Accountability requires measurement** | Ownership without visible outcomes is unenforceable. The performance cascade gives each owner instruments. | Accountability becomes rhetorical. Directors re-intervene because they cannot see what is happening — rationally so. |
| **\[4\] → \[5\]  Measurement requires a single source of truth** | Metrics computed from fragmented spreadsheets are contestable, late, and manually assembled. | Every review becomes a debate about whose numbers are right. Reporting burden grows, violating Principle 6\. |
| **\[5\] → \[6\]  Information requires a forum** | Data that no forum acts on changes nothing. Cadence converts visibility into decisions. | A well-instrumented business that still waits for a founder to notice problems. |
| **\[6\] → \[7\]  Cadence produces execution reliability** | Problems surface at a predictable point with a named owner and a deadline, rather than when they become crises. | SLA remains dependent on whether a director happened to notice — which is why it sits at 78%. |
| **\[7\] → \[8\]  Reliability reduces founder dependency** | Founders are pulled in by unreliability. When Tier-1 and Tier-2 contain issues, the pull disappears. Reliability also builds the institutional trust that lets founders exit accounts. | Founders remain the safety net, and the safety net is load-bearing. |
| **\[8\] → \[9\]  Lower dependency lowers effort per customer** | Removes three specific costs: waiting time on approvals, rework from decisions made without context, and duplicated effort from fragmented information. | Effort per customer stays at 1.86 employees — which is precisely what three years of data show. |
| **\[9\] → \[10\]  Lower effort is operating leverage** | Operating leverage is definitionally the ability to serve more customers without proportional cost. Employees per customer is its direct measure. | Growth continues to require proportional headcount — reproducing the −0.2% incremental margin. |
| **\[10\] → \[11\]  Leverage makes the targets reachable** | At 1.86 employees/customer, 120 customers requires \~223 employees and yields \~2.2% margin. At ≤1.41, the same revenue supports the 15–20% target. | Rp45B is achieved at today’s margin — the growth targets are met and the financial targets are missed. |

| The honest limit of this chain Links \[1\] through \[8\] are fully within governance control. Link \[9\] is shared: governance removes waiting, rework, and duplication, but the largest single component of effort per customer — bespoke implementation scope — is removed by product standardization, which is Task 2\. Section 14 quantifies this division rather than claiming the whole improvement for governance. |
| :---- |

# **Section 13 — Implementation Roadmap (0–12 Months)**

Nine initiatives, not twenty. Each is either a prerequisite for others or directly attacks a ranked bottleneck from §2.2.

## **13.1  Challenging the Proposed Sequencing**

The brief proposes Stabilize (0–3) → Institutionalize (3–6) → Scale Governance (6–12). This is broadly right, with one correction and one addition.

| Issue | Correction Made |
| ----- | ----- |
| Role charters are placed in "Institutionalize" | Moved into 0–3. Appointing six Heads without written role charters means appointing people whose authority is undefined — which is how the current ambiguity was created. The charter must exist on day one of the appointment, not three months later. |
| Escalation tiering is treated as a later structural item | Moved to month 0–2, running parallel to appointments. It is the fastest available win (weeks, not quarters), it directly attacks SLA and churn which compound, and the early visible result builds the organizational confidence the harder changes require. |
| No capability-building track in the proposed sequencing | **Added as a parallel track.** The case states subordinates depend on direction — meaning the people receiving authority have never exercised it. A 90-day structured capability programme runs alongside Phase 1\. Omitting it is the highest-probability route to a failed delegation, which would harden director scepticism and set the transformation back further than a slower start would. |

## **13.2  Phase 1 — Stabilize (Months 0–3)**

Objective: stop the bleeding and create the recipients of authority. Nothing else can begin until a management layer exists. Revised on external review to include Head of Product from the outset — see §8.2.

| Timeline | Initiative | Root Cause | Owner | Dependency | KPI / Milestone | Expected Impact |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **Month 0–2** | Appoint Head of Customer Success and Head of People & BizOps (internal promotion) | F1 / E1 | CEO | None — entry point | 2 Heads in role with written charters | Creates the layer that receives authority |
| **Month 0–2** | Hire Head of Delivery externally, on staggered start and performance-gated bonus (§8.5) | F1 / E1 | CEO | None — entry point | Head of Delivery in role | Owns the largest single lever on employees-per-customer |
| **Month 0–2** | Design and launch 3-tier escalation protocol | E1 | Head of CS | Head of CS appointed | Tier-1/2 containment rate; SLA weekly visible | Fastest win: SLA begins moving; director interrupts fall |
| **Month 2–3** | Promote Head of Product internally; mandate is to inventory customization requests and begin the package catalogue jointly with Task 2 | F3 (enabling) | CTO | Head of CS live, single record started | Customization request log live; catalogue v0 drafted | Prevents the Task 2 stall an unstaffed H1 would cause — see §8.2 |
| **Month 1–3** | Publish Decision Rights Matrix v1 (§5) and activate Tier-1 authority | E1 | COO | Heads appointed | % decisions closed below director level | Directors exit routine approval volume |
| **Month 1–3** | Launch Shadow-to-Solo Gate (§8.6) for new Heads | Principle 7 | Head of People | Heads appointed | Gate stage completed on schedule per Head | De-risks the largest failure mode in this plan, on a dated founder-time budget |

## **13.3  Phase 2 — Institutionalize (Months 3–6)**

Objective: build the instruments that make delegation durable rather than temporary.

| Timeline | Initiative | Root Cause | Owner | Dependency | KPI / Milestone | Expected Impact |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **Month 2–4** | Appoint Head of Engineering; hire Head of Sales (conditional on escalation tiers being live — §8.5) | F1 / E1 | CEO / CTO | Phase 1 stable | 6 of 6 Heads in role | Removes CTO approval queue and CEO pricing bottleneck |
| **Month 3–6** | Build the performance cascade (§6) — functional, team, individual | E2 | Head of People | Heads in role | Every role has 3–5 metrics; monthly 1:1s running | Makes outcomes visible — the precondition for durable delegation |
| **Month 3–6** | Migrate service \+ customer domains onto ServeNow’s own platform | F2 | Head of CS | Escalation tiers live | Single record live for service & customer | Ends informational monopoly; enables managers to manage |
| **Month 3–6** | Named account ownership \+ founder-sponsored handovers | F1 | Head of CS / CEO | Customer record live | % revenue with named non-founder owner | Begins trust transfer — slowest-moving, so started early |
| **Month 3–6** | Head of Product finalizes package catalogue v1 (Starter/Growth/Enterprise) jointly with Task 2 | F3 (enabling) | Head of Product | Catalogue v0, 3+ months of request data | Catalogue v1 published; Standard-Scope Ratio baselined | Direct input to the 6–10-week implementation target |

## **13.4  Phase 3 — Scale Governance (Months 6–12)**

Objective: make the model self-sustaining and prepare the platform Tasks 2 and 3 will build on.

| Timeline | Initiative | Root Cause | Owner | Dependency | KPI / Milestone | Expected Impact |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **Month 6–9** | Migrate pipeline and delivery domains onto the single record | F2 | Head of Sales | Perf. cascade live | All 6 information domains live | Completes §10; managers see the business unaided |
| **Month 6–12** | Full governance cadence operating; directors exit Weekly Ops Sync | E1 | COO | All above | Directors absent from weekly ops for 3 consecutive months | The observable proof that delegation is real |
| **Month 9–12** | Activate consequences and recognition layer of accountability system | E2 | Head of People | Cascade running 2 quarters | Performance cycle completed once end-to-end | Closes the accountability loop; consequences now fair because standards exist |

## **13.5  Dependency Map**

| PREREQUISITE (must complete first)   Appoint Heads → everything else   Escalation tiers → service data → SLA measurement   Decision Rights Matrix → accountability → performance cascade PARALLEL (can run simultaneously)   Escalation tiering  ||  Head appointments  ||  Capability programme   Information migration  ||  Performance cascade design DOWNSTREAM (depends on this task, feeds others)   Head of Product co-leads (not waits for) TASK 2 boundary definition from month 2–3   Head of Sales \+ pipeline record → TASK 3 can build the sales engine   Named account ownership \+ SLA → TASK 3 geographic expansion |
| ----- |

# **Section 14 — Quantified Impact Logic**

| Discipline statement The case does not disclose cost structure by function, salary bands, rework rates, or the cost of overtime. No financial impact is therefore estimated here. What follows connects each intervention to an operational KPI the case actually measures, and then to the financial direction that KPI drives. Where governance cannot claim an improvement on its own, this is stated explicitly. |
| :---- |

## **14.1  Intervention → Mechanism → KPI → Impact**

| Intervention | Mechanism | Operational KPI | Financial / Strategic Impact |
| ----- | ----- | ----- | ----- |
| 3-tier escalation with named owner | Tier 1 and 2 contain issues; only material churn risk reaches a director | SLA 78% → ≥96%; director interrupts per week | Directly attacks churn — the single most expensive operational failure, consuming 44% of gross new logos |
| Decision Rights Matrix with thresholds | Routine approvals stop queueing behind three people | Approval turnaround ≤3 days; % decisions below director level | Compresses implementation duration → delivery capacity released → downward pressure on employees per customer |
| Six Functional Owners | Named accountability for each outcome; span of control becomes manageable | Each transformation target has one owner | Enables every other improvement; no direct financial claim on its own |
| Performance cascade with paired metrics | Individual output becomes visible and manageable for the first time | Role coverage of defined metrics; capacity forecast accuracy ±15% | Productivity becomes improvable — the case shows revenue/employee rose 11.2% while cost/employee rose 14.1%; closing that gap is where margin recovery begins |
| Capacity forecasting | Signed work is resourced before commitment rather than after | Avoidable overtime; on-time milestone rate | Reduces the cost inflation the case attributes to poor planning; magnitude undisclosed |
| Single source of truth | Ends duplicated effort and reconciliation; makes patterns visible | 6 domains live; reporting prepared specially for reviews → zero | Removes non-productive effort; enables Task 2 to see which customizations recur |
| Named account ownership | Customer’s counterpart becomes an employee, not a founder | Founder Dependency Index; % revenue with non-founder owner | Unlocks the Rp1.9B → Rp18.0B non-Jabodetabek target, which is unreachable while delivery requires founder presence |

## **14.2  How Governance Contributes to the 15–20% Margin Target**

The arithmetic from RCA v2 defines the mandate precisely. At 1.86 employees per customer, 120 customers requires \~223 employees, producing \~2.2% net margin — the growth targets met, the margin target missed. Reaching 17.5% margin at Rp45B caps total cost at \~Rp37.1B, supporting \~169 employees, which requires employees per customer to fall to \~1.41 (−24%).

Governance does not deliver that 24% alone. The honest attribution:

| Component of the −24% | Primary Owner | Governance Contribution | Why |
| ----- | ----- | ----- | ----- |
| Waiting time — effort lost to approval queues and director availability | **GOVERNANCE** | **Full** | Caused entirely by centralized decision rights. Decision Rights Matrix removes it directly. |
| Rework — effort repeated because decisions were made without context or standards | **GOVERNANCE** | **Full** | Caused by absent standards and invisible quality. Performance cascade and single record address it. |
| Duplicated effort — fragmented information forcing re-collection and reconciliation | **GOVERNANCE** | **Full** | Directly caused by data across spreadsheets, WhatsApp, email, personal notes. |
| Avoidable overtime — cost inflation from poor planning | **GOVERNANCE** | **Full** | The case attributes overtime specifically to poor planning. Capacity forecasting is a governance deliverable. |
| Bespoke implementation scope — the largest single effort component per customer | **TASK 2 — PRODUCT** | **Enabling only** | Governance creates the Head of Product and the authority to define boundaries. It cannot define them. This is the biggest single lever and it is not ours. |
| Acquisition efficiency — effort per new customer won | **TASK 3 — SALES** | **Enabling only** | Governance provides the pipeline record and delegated pricing authority; the repeatable commercial process is Task 3\. |
| Churn reduction — lowering the gross acquisition burden | **SHARED** | **Substantial** | Governance owns SLA and escalation — the direct churn drivers. Task 2 owns implementation duration, also a driver. |

| The defensible claim Governance & Organization does not deliver the margin target. It removes the four effort categories that are purely organizational in origin — waiting, rework, duplication, and avoidable overtime — and it creates the decision-making capacity and product ownership without which Tasks 2 and 3 cannot execute at all. Governance is the enabling condition for the margin target, and the direct owner of the SLA and churn targets. |
| :---- |

## **14.3  Target Ownership Map**

| Target | Governance Ownership |
| ----- | ----- |
| SLA 78% → ≥96% | **DIRECT OWNER** |
| Director dependency: High → Low | **DIRECT OWNER** |
| Churn 16.7% → \<5% | **PRIMARY OWNER (shared with Task 2 on implementation speed)** |
| Implementation 16–22 → 6–10 weeks | **SHARED — governance removes approval latency; Task 2 removes bespoke scope** |
| Employees per customer 1.86 → ≤1.41 | **SHARED — governance owns 4 of 6 effort components** |
| Margin 2.5% → 15–20% | **ENABLING — not a direct governance deliverable** |
| Revenue Rp15.8B → Rp45B | **ENABLING — owned by Task 3** |
| Non-Jabodetabek 12% → 40% | **ENABLING — trust transfer is necessary but not sufficient** |

# **Section 15 — What Should NOT Change**

A transformation that redesigns everything destroys the assets that made the company worth transforming. ServeNow has real strengths, and several are precisely the things a governance programme would instinctively bureaucratize.

## **15.1  Strengths to Protect**

| Asset | Evidence | Why It Must Be Protected | Protection Mechanism |
| ----- | ----- | ----- | ----- |
| Local adaptability as a differentiator | Case: customers rate ServeNow more flexible than global products because it adapts to local business processes — named as a genuine selling point | This is the wedge against global competitors. Governance that makes adaptation slow or bureaucratic destroys the core competitive advantage | Customization is tiered, not forbidden. Configurable-tier work is pre-approved by the Head of Product with no escalation. |
| Speed of response to customers | Implied by the flexibility advantage and by direct founder involvement | Local competitors are described as faster; slowing down would surrender the last remaining advantage | Decision thresholds are set so most decisions require no escalation at all. Speed is preserved by delegation, not by founder heroics. |
| Founder domain expertise | Three founders with combined IT, customer service, and business development experience | This expertise is genuine and scarce. The problem is its deployment on routine work, not its existence | Founders retain architecture standards, strategic pricing, partnerships, top-10 accounts — high-judgement, low-volume decisions. |
| Deep customer relationships | Some customers served 3+ years | Long-tenured relationships are a real asset and a defence against competitive displacement | Relationships are broadened, not transferred away. Founders remain sponsors of top accounts; the account owner is added, not substituted. |
| Cross-sector experience | Six sectors served: retail, education, healthcare, property, financial services, government | Sector knowledge is the raw material for the vertical templates Task 2 will build | Sector context captured in the customer record so it becomes institutional rather than personal. |

## **15.2  What ServeNow Must NOT Bureaucratize**

| Do NOT Bureaucratize | Why | What to Do Instead |
| ----- | ----- | ----- |
| **Customer responsiveness** | Adding approval steps between a customer request and a response would convert the company’s main advantage into its competitor’s | Delegate authority far enough down that the first responder can usually act. Escalation is the exception, not the workflow. |
| **Configurable-tier customization** | The case shows flexibility wins deals. A heavy approval gate on all customization would cost revenue immediately for a benefit that arrives later | Only custom-tier work above a defined effort threshold requires approval. Configurable work proceeds freely. |
| **Internal communication** | The case criticises excessive informal communication — but informality is also what makes a 78-person company fast | Formalize only what must be auditable: decisions, commitments, and customer facts. Everything else stays informal. |
| **Small-team coordination** | Sales has 3 people; Product will have \~2. Imposing full process on teams this size costs more than it saves | Team Leads created only where span exceeds 12\. Lightweight cadence for small functions. |
| **Experimentation and product ideas** | The case lists 16 innovation directions — evidence of genuine idea generation. Governance should prioritize ideas, not suppress them | Head of Product prioritizes at a quarterly rhythm. Ideas are collected continuously and decided periodically. |

## **15.3  Founder Responsibilities Deliberately Retained**

| Retained | Reason |
| ----- | ----- |
| Top-10 strategic account sponsorship | Removing founders from the largest relationships during a period of service instability would be reckless. Involvement becomes periodic and strategic rather than constant and operational. |
| Architecture standards and security accountability | Genuinely high-judgement, low-volume, and consequential. The CTO should set the standard once rather than approve each application of it. |
| Partnership and strategic pricing decisions | Low frequency, high consequence, requiring the full business context founders hold. Correctly retained at executive level in any company of this size. |
| Management-level hiring | The quality of the six Heads determines whether this entire transformation succeeds. This is not a decision to delegate in the first year. |
| External representation and vision | Founder credibility is a genuine asset in the Indonesian market and in tender processes. It should be deployed where it creates the most value, which is externally. |

# **Section 16 — Self-Critique & Revision**

Twelve challenges applied to the model above. Four produced material revisions, which are incorporated into the preceding sections.

### **1\. Does it create unnecessary bureaucracy?**

**Verdict: Partially — revised**

The original draft included a Weekly Ops Sync, Monthly Business Review, Quarterly Strategy Review, daily standups, monthly 1:1s, and a quarterly performance cycle. For a 78-person company that is a heavy calendar, and Principle 6 requires each mechanism to remove more coordination cost than it adds.

**Revision made:** Daily standups reduced to 10 minutes and made team-level only — not a management forum. Total management meeting load capped at \~45 min weekly plus 90 min monthly per Head. A separate PMO function, matrix reporting, and formal committees were all rejected outright (§8.3).

### **2\. Does it increase headcount too much?**

**Verdict: No — but the cost is real**

Six Heads plus \~6 Team Leads sounds substantial, but four of six Heads are internal promotions and team leads are created only where span exceeds 12\. Net new headcount is approximately 2\. At 2.5% net margin this still matters — which is why the structure is deliberately minimal and why external hiring is confined to the two functions with no internal process discipline to promote from.

**Revision made:** Roles were cut from an initial nine to six. Head of Marketing, PMO, Chief of Staff, and separate Support/CS leadership were all removed.

### **3\. Could managers become new bottlenecks?**

**Verdict: Yes — this is the second-largest risk**

A newly appointed Head who has never held authority may replicate exactly the behaviour being corrected: escalating upward when uncertain, or hoarding decisions to demonstrate control. Six new bottlenecks would be worse than three old ones, because the founders at least have full context.

**Revision made:** Three mitigations added: (a) written decision thresholds so authority is unambiguous rather than judgement-based; (b) the 90-day capability programme under Principle 7; (c) "% of decisions resolved at this level" tracked as a management KPI — a Head who escalates excessively is visible within one month.

### **4\. Does it slow decision-making?**

**Verdict: Temporarily yes, structurally no**

During months 0–6 decisions may genuinely slow while new owners build confidence and boundaries are tested. This is a real cost and should be expected rather than denied. Structurally, decisions accelerate because most stop queueing behind three overloaded people.

**Revision made:** Approval turnaround time added as a weekly-tracked leading indicator specifically so any sustained slowdown is detected within weeks rather than discovered at year-end.

### **5\. Does it weaken founder–customer relationships?**

**Verdict: Risk acknowledged and bounded**

Abruptly removing founders from accounts would damage the relationships the case identifies as a genuine asset, and could increase churn during precisely the period when churn is already the primary problem.

**Revision made:** Two protections: top-10 accounts remain founder-sponsored indefinitely (§15.3), and all handovers are founder-introduced rather than announced administratively (§9.2, mechanism 2). Founders are added to, not subtracted from, the relationship.

### **6\. Can employees game the KPI system?**

**Verdict: Yes — addressed by design**

Any single metric is gameable. SLA improves by closing tickets without resolving them. Implementation time improves by cutting quality. Revenue per employee improves by firing people.

**Revision made:** Every functional metric is paired with a counter-metric that degrades if the primary is gamed (§6.2). Revenue per employee was explicitly demoted from north-star to guardrail for exactly this reason.

### **7\. Does it create excessive reporting?**

**Verdict: No — rule added**

The risk is real: a performance cascade plus six information domains plus four forums could generate substantial reporting overhead, which would violate Principle 6 and consume the capacity the transformation is meant to release.

**Revision made:** A hard rule was added in §10.2 and §11.3: no forum may require a document prepared specially for it. All reviews run off the live record. Additionally, data fields are collected only where a named decision depends on them.

### **8\. Is ServeNow organizationally ready for this?**

**Verdict: Partially — the central risk**

The case states subordinates depend on direction. This is a company where nobody below director level has exercised meaningful authority. Handing six people substantial decision rights in month two is optimistic, and the model’s success depends heavily on the quality of six individuals who do not yet hold these roles.

**Revision made:** Principle 7 (sequence capability before authority) was added as a design principle rather than an implementation detail. Authority transfers in stages with a competence checkpoint, and §16.12 defines a minimum viable version if capability proves weaker than assumed.

### **9\. Which initiatives depend on Product & Innovation (Task 2)?**

**Verdict: Three material dependencies — revised twice**

The Head of Product role cannot be effective without a defined product boundary, which is a Task 2 deliverable. Implementation compression to 6–10 weeks requires standard packages, not just faster approvals. The Standard-Scope Ratio KPI cannot be baselined until product tiers exist. This document originally resolved that dependency by deferring the Head of Product appointment to months 6–9, reasoning the role needed Task 2 to finish first to have substance.

**Revision made:** External review correctly identified this as circular: with no owner from month 0–6, either the CTO remains the de facto product manager — the exact overload §4.4 removes — or nobody drives it and Task 2 stalls for two quarters. Revised position (§8.2, §13.2): Head of Product is promoted internally in month 2–3, with an explicit first mandate to build the boundary jointly with Task 2 rather than wait for it — turning a sequential dependency into a shared, parallel one.

### **10\. Which initiatives depend on Sales & Expansion (Task 3)?**

**Verdict: Two material dependencies**

The Head of Sales delegation model assumes a documented sales process exists to delegate within; without it, delegated pricing authority is authority without method. The pipeline information domain assumes defined stages. Both are Task 3 deliverables.

**Revision made:** Governance scope narrowed to what it can own alone: the pipeline record, delegated pricing thresholds, and forecast discipline. The commercial process itself is explicitly assigned to Task 3\.

### **11\. Which recommendations have the highest failure risk?**

**Verdict: Three identified**

Ranked by probability × consequence: (1) the six Heads underperform — highest probability, and the entire model depends on them; (2) founders fail to genuinely release authority — high probability given three years of habit, and it would silently nullify the whole programme; (3) trust transfer stalls because customers resist — moderate probability, high consequence for expansion.

**Revision made:** Countermeasures: capability programme and staged authority for (1); the directors-excluded-from-Ops-Sync rule as an objective test for (2); founder-introduced handovers plus retained top-10 sponsorship for (3).

### **12\. What is the minimum viable transformation?**

**Verdict: Defined below**

If ServeNow can execute only a fraction of this, the following is the irreducible core — the smallest set that still breaks the fundamental constraint.

| MINIMUM VIABLE TRANSFORMATION — if only four things can be done 1\.  Appoint Head of Customer Success and Head of Delivery. Two people, both promotable internally, covering the functions where damage compounds fastest. 2\.  Implement 3-tier escalation. Weeks to design, directly attacks the 78% SLA and the churn it drives. 3\.  Publish decision thresholds for the ten highest-frequency decisions. Not all 22 — the ten that consume the most director time. 4\.  Assign named account ownership for all non-top-10 accounts, with founder-led introductions. *This costs approximately one external hire, requires no new systems, and would still move SLA, churn, and founder dependency — the three targets governance owns most directly. Everything else in this document accelerates and sustains the change; these four begin it.* |
| :---- |

# **Section 17 — Final Consulting Synthesis**

## **17.1  Executive Summary**

| DIAGNOSIS ServeNow has no governance model — it has three individuals performing the work a governance model would do. With 78 staff reporting effectively to three directors holding 5–8 roles each, company throughput equals director bandwidth. This produces 16–22-week implementations, 78% SLA, 16.7% churn, and three years of flat employees-per-customer (1.86) with a −0.2% incremental margin. TARGET OPERATING MODEL Four layers, not five: Executive (3 existing directors, role redesigned) → six Functional Owners → conditional Team Leads where span exceeds 12 → staff. Net new headcount ≈ 2; four of six Heads promoted internally. TOP GOVERNANCE CHANGES (1) Create the missing management layer. (2) Bound and move 22 recurring decisions. (3) Replace attendance monitoring with a four-tier performance cascade using paired counter-metrics. (4) Contain escalation in three tiers. (5) Consolidate six information domains onto ServeNow’s own platform. (6) Transfer customer trust through named account ownership. ROADMAP 0–3 Stabilize: four Heads including Product (promoted early to co-lead Task 2 boundary-setting rather than wait for it), escalation tiers, decision matrix v1, Shadow-to-Solo Gate. 3–6 Institutionalize: remaining two Heads, performance cascade, information migration, account ownership, package catalogue v1. 6–12 Scale: full cadence live, directors exit weekly operations. EXPECTED IMPACT Direct ownership of SLA (78→96%), director dependency (High→Low), and churn (16.7→\<5%). Removes four of six effort components behind employees-per-customer — waiting, rework, duplication, avoidable overtime. Enabling condition for the margin target, which requires Task 2 product standardization to complete. |
| :---- |

## **17.2  Current → Transformation → Target**

| CURRENT                TRANSFORMATION              TARGET 3 directors,      →  6 Functional Owners    →  4 layers, span ≤12 5–8 roles each        with role charters         directors govern All decisions     →  22 decisions bounded   →  Majority resolved route to 3 people     with thresholds            below director level Attendance app    →  4-tier KPI cascade,    →  Outcomes managed, only                  paired counter-metrics     presence irrelevant Data in 4 places  →  6 domains, single-     →  Managers see the (sheets/WA/email)     entry, owner-updated       business unaided Ad-hoc founder    →  Daily/weekly/monthly/  →  Institutional intervention          quarterly cadence          management rhythm Trust in founders →  Named ownership \+      →  Trust in ServeNow personally            10 transfer mechanisms     as an institution SLA 78% · Churn 16.7% →→→ SLA ≥96% · Churn \<5% Employees/customer 1.86 →→→ ≤1.41 |
| ----- |

## **17.3  Top Five Governance Priorities, Ranked**

| \# | Priority | Why It Ranks Here | First Milestone |
| ----- | ----- | ----- | ----- |
| **1** | Create the management layer (6 Functional Owners) | Nothing can be delegated to a layer that does not exist. Every other initiative depends on this one. Fully within governance control. | 4 Heads appointed with charters by month 3, incl. Product |
| **2** | Publish and activate the Decision Rights Matrix | Converts titles into actual authority. Without written thresholds, decisions default upward and the new layer becomes decorative. | Matrix v1 live by month 3 |
| **3** | Implement 3-tier escalation containment | Fastest available win. Directly attacks SLA and churn, which compound every quarter they persist. Weeks to design. | Tier structure live by month 2 |
| **4** | Build the performance cascade | The precondition that makes delegation durable. Without visible outcomes, directors re-intervene — and would be right to. | Every role has 3–5 metrics by month 6 |
| **5** | Transfer customer trust to named owners | Slowest to move, so must start early. Unlocks geographic expansion and removes the founder ceiling on sales capacity. | Named owner on every non-top-10 account by month 6 |

## **17.4  Decision Rights Summary — The Delegations That Matter Most**

| Decision | From | To | Threshold Retained by Founder |
| ----- | ----- | ----- | ----- |
| Pricing | CEO | Head of Sales | Discounts beyond 15% |
| Technical approval | CTO | Head of Engineering | New architectural patterns; security-sensitive design |
| Customization approval | CTO | Head of Product | Custom work exceeding 2 weeks effort |
| Customer escalation | All to board | Head of CS (Tier 2\) | Material churn risk; systemic failure (Tier 3\) |
| Implementation resourcing | COO | Head of Delivery | Resource needs beyond planned capacity |
| Non-managerial hiring | CEO | Functional Head \+ Head of People | Outside band or unbudgeted |
| Operating spend | CEO / COO | Functional Head | Unbudgeted or beyond envelope |

## **17.5  Performance Architecture at a Glance**

| Level | Metric Focus | Example | Review |
| ----- | ----- | ----- | ----- |
| **Company** | Operating leverage & financial outcomes | Employees per customer 1.86 → ≤1.41 | Quarterly Strategy Review |
| **Function** | One outcome \+ one counter-metric | Head of CS: SLA ≥96%, countered by churn \<5% | Monthly Business Review |
| **Team** | Operational drivers within team control | On-time milestones; scope-change volume | Weekly team check-in |
| **Individual** | Output, quality, reliability — never attendance | Deliverables to standard; defect rate; commitment reliability | Monthly 1:1 with direct manager |

## **17.6  Strategic Contribution**

| GOVERNANCE ↓  removes routine decisions from three people LESS FOUNDER DEPENDENCY ↓  decisions stop queueing FASTER DECISIONS ↓  work proceeds without waiting; standards reduce rework MORE RELIABLE EXECUTION ↓  issues contained at Tier 1/2 with named owners BETTER SLA  (78% → ≥96%) ↓  service reliability is the primary churn driver LOWER CHURN  (16.7% → \<5%) ↓  \~9 fewer customers to replace each year LOWER HUMAN EFFORT PER CUSTOMER ↓  waiting \+ rework \+ duplication \+ overtime removed OPERATING LEVERAGE  (1.86 → ≤1.41) ↓  with Task 2 product standardization SCALABLE GROWTH  —  Rp45B at 15–20% margin |
| :---: |

## **17.7  Final Strategic Statement**

| ServeNow should transform from a founder-dependent organization into an institutionally governed operating model by creating six accountable Functional Owners beneath a redesigned executive team, moving twenty-two recurring decisions to bounded owners with explicit escalation thresholds, replacing attendance monitoring with a four-tier performance cascade built on paired counter-metrics, and transferring customer trust from founders to named institutional owners supported by a single source of truth — enabling SLA to rise from 78% to at least 96%, churn to fall from 16.7% to below 5%, implementation approval latency to compress from weeks to days, and directors to exit routine operations entirely — and ultimately decoupling revenue growth from proportional human effort by removing the waiting, rework, duplication, and avoidable overtime that currently make every additional customer cost 1.86 additional employees. |
| :---- |

*Task 1 complete. This document establishes the governance foundation on which the Product & Innovation Roadmap (Task 2\) and the Sales & Expansion Strategy (Task 3\) depend — specifically, the Head of Product role that Task 2 requires to define product boundaries, and the delegated commercial authority and pipeline record that Task 3 requires to build a repeatable sales engine.*

# **Section 18 — Response to External Stress-Test Review**

This document was stress-tested by an external reviewer against four specific failure modes before finalization. Three produced material revisions, incorporated directly into the sections above rather than left as unaddressed critique. This section consolidates them in one place — the form in which they are most likely to be asked back at Q\&A.

## **18.1  Summary of Findings and Disposition**

| \# | Finding | Verdict | Where Fixed |
| ----- | ----- | ----- | ----- |
| **1** | "Affordable and self-funding" understated Year-1 cash-flow risk from two senior external hires against Rp395jt total profit | **Accepted — revised** | §8.5: variable-weighted compensation, staggered hiring, transition budget from existing spend |
| **2** | "90-day coaching" did not specify who coaches or how founder time is actually freed | **Accepted — revised** | §8.6: Shadow-to-Solo Gate with a dated, three-stage decline in founder time; fractional external advisor for the two hardest-to-promote-into roles |
| **3** | Deferring Head of Product to month 6–9 created a circular dependency — Task 2 needs an owner that governance was withholding until Task 2 finished | **Accepted — revised** | §8.2, §13.2: Head of Product promoted internally in month 2–3 with a mandate to co-build the boundary alongside Task 2, not wait for it |
| **4** | A 50-page document risks cognitive overload against a 10-minute presentation format | **Accepted — deferred, not a document defect** | Noted below; addressed at slide-conversion, not by shortening the analytical record |

## **18.2  Why Finding 4 Is Deferred Rather Than Fixed Here**

Findings 1–3 were genuine flaws in the reasoning — claims that did not survive scrutiny, or a sequencing choice that contradicted the document’s own dependency logic. They were corrected at the source.

Finding 4 is a different kind of observation: it is correct about the presentation constraint but is not evidence that the underlying analysis is wrong or should be thinner. A 47–50-page master document and a 3-slide, 10-minute narrative are different artifacts serving different purposes — this document is the defensible analytical record; the slides are a distillation for a time-boxed format. Cutting the analysis to fit the slide count would remove exactly the material — the decision matrix, the counter-metrics, the dependency chain — that this section exists to demonstrate was stress-tested.

| Distillation plan for slide conversion (not executed in this document) Slide 1 — The Structural Mandate: the shift from a 3-person bottleneck (1.86 employees/customer) to a 4-layer, 6-Head distributed model (§4). Slide 2 — Decision Boundaries & Performance Engine: the 6–8 highest-leverage delegations from §5.5 with their thresholds, plus the paired counter-metric design from §6.2. Slide 3 — Trust Transfer & 12-Month Phasing: the Founder Dependency Index concept from §9.3, and the Stabilize → Institutionalize → Scale phasing from §13 with the corrected Head of Product timing. *This document remains the source those three slides are drawn from and the reference for any question that goes beneath them.* |
| :---- |

## **18.3  Points From the Review Explicitly Retained As-Is**

Not every observation required a change. Three points from the review are noted here because they identify genuine strengths worth defending at Q\&A rather than risks requiring revision.

| Retained Element | Why It Survives Scrutiny Unchanged |
| ----- | ----- |
| The 4-layer structure (rejecting the brief’s proposed 5-layer model) | The correction was already made in §4.1 before external review, for the reason the review independently confirms: Founders and Functional Directors are the same three people at ServeNow’s size, and inventing a redundant layer would either require three unneeded additional directors or produce a layer that exists on paper only. |
| Directors’ exclusion from the Weekly Ops Sync | Confirmed as the single most reliable observable test of whether delegation is real (§11.2). The anticipated Q\&A challenge — "what happens in a crisis?" — is already answered by the Tier-3 escalation protocol in §5 and §11.1: a named, dated escalation path, not standing director attendance. |
| Paired counter-metrics as the alternative to "implement KPIs" | This is the direct answer to why §6 is an architecture rather than a tool purchase, and it is the same discipline applied to the original attendance-app failure in §7.1 — internally consistent across the document. |
| Dogfooding ServeNow’s own platform as the single source of truth (§10.2) | Correctly identified as a double-purpose asset: it solves the internal fragmentation problem at zero incremental vendor cost, and it produces a live reference-customer demonstration Task 3 can use in sales conversations. |

## **18.4  Net Effect of This Revision**

| The document is more defensible after revision, not merely different. Three claims that would not have survived a sceptical judge’s follow-up question — "can you actually afford that," "who literally coaches them," and "who runs product for six months" — now have specific, named answers rather than assertions. The fourth finding correctly separates the analytical document from the presentation artifact, which is the distinction this section exists to make explicit. |
| :---- |

