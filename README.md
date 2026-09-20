# SAP Autonomous Finance Receivables Demo — Joule Skill

**AI Agents | Enterprise Service Management (ESM) | Accounts Receivable (AR) | Recurring Receivables (RR)**

A Joule Work Desktop skill showcasing **SAP Autonomous Finance** ART OF THE POSSIBLE across four blended demo flows:

- Enterprise Service Management (ESM)
- Accounts Receivable (AR)
- Recurring Receivables (RR)
- Dispute Management

The demonstration features **20+ AI agents** coordinated across:

- SAP S/4HANA FI-AR
- SAP BRIM/FICA
- SAP ESM
- SAP FSCM Dispute Management

> **Demo Note:** No live SAP system is connected. All data is illustrative mock data. The demonstration is designed to show how SAP Joule and Autonomous Finance AI agents would work in a real deployment.

---

# 1. How to Start the Demo

Run the solution in **Joule Work Desktop as a skill**.

Launch the full menu or jump directly into any of the four flows.

### Full Demo

**Launch:**

`Start the Autonomous Finance demo`

**Starts:** Flow selection menu — pick any of the four.

### Flow 1 — ESM Standalone

**Launch:**

`Start the ESM demo`

**Starts:** Flow 1 — ESM Standalone (7 acts)

### Flow 2 — AR + ESM

**Launch:**

`Start the AR demo`

or

`Start the collections demo`

**Starts:** Flow 2 — AR + ESM (8 acts)

### Flow 3 — RR + ESM

**Launch:**

`Start the RR demo`

or

`Start the BRIM demo`

**Starts:** Flow 3 — RR + ESM (8 acts)

### Flow 4 — Dispute Management

**Launch:**

`Start the dispute demo`

or

`Show me dispute management`

**Starts:** Flow 4 — Dispute Management (6 acts)

---

# SAP Autonomous Finance Demo — Prompt Sheet

## Flow 1 — ESM Standalone

**Launch:** `Start the ESM demo`

1. "Joule, show me the latest service request that came in from Geoff Hill."

2. "Yes, go ahead and prepare the cases."

3. "What does our knowledge base say about parental leave in Germany, and have we handled similar cases before?"

4. "Investigate the payslip deduction — why did PEN-ADJ appear and is it correct?"

5. "Yes, flag the other employees and proceed with Geoff's adjustment."

6. "Draft the response email to Geoff covering both issues."

7. "Send it and close both cases."

---

## Flow 2 — AR + ESM

**Launch:** `Start the AR demo`

1. "Joule, give me the full receivables picture for CA Networks AG."

2. "Show me the full 360 — disputes, promises to pay, dunning history."

3. "Draft the collections outreach email to Thomas Weber."

4. "Send it. And what does Joule recommend on dunning — should we escalate?"

5. "Thomas just replied. He says they dispute invoice INV-2026-10077 — they received only 85 units, not 100. He wants a dispute case raised."

6. "Yes, route it to ESM and set up the case."

7. "Process the resolution — issue the credit memo."

8. "Yes, create the PTP and then show me what happens when the payment clears."

---

## Flow 3 — RR + ESM (BRIM)

**Launch:** `Start the RR demo`

1. "Joule, show me the risk profile for CloudTech Services."

2. "Open Mike's email and create the case."

3. "Yes — investigate the subscription and find out how this error happened."

4. "Process the correction — fix the PO reference and update the bill-to party."

5. "Reissue the corrected invoice."

6. "Create the PTP and confirm payment expectation with Mike."

7. "Yes — what's the BRIM convergent invoice dispute about?"

8. "Great — close the ESM case and show me the full outcome."

---

## Flow 4 — Dispute Management

**Launch:** `Start the dispute demo`

1. "Joule, give me my dispute queue for today."

2. "Let's start with DIS-2026-37737 — the invoice amount error."

3. "Yes — process the credit memo."

4. "Open DIS-2026-37821 — the wrong goods delivery for Meridian Engineering."

5. "Last one — DIS-2026-37901, the payment mismatch for Vortek Industries."

6. "Save the dispute findings and show me the session summary."

---

## Close Demo

`end session`

---

# 2. Demo at a Glance

## Flow 1 — ESM Standalone

**Persona:** Rachel Chen, HR & Finance Service Desk Lead

An employee submits a combined HR + payroll request. The **Case Preparation Agent** splits it into two workstreams, investigates a **€240 payroll deduction**, discovers a batch error affecting **four employees**, and resolves both cases in **22 minutes**.

### Agents

- Self-Service Assistant
- Case Preparation Agent
- Case Processing Agent
- Interaction Management Assistant
- HR Service Assistant
- Accounts Receivable Assistant
- Case Management Assistant
- Service Management Assistant

---

## Flow 2 — AR + ESM

**Persona:** Avery Kim, Collections Specialist

A full AR collections cycle for a high-risk account — **CA Networks AG, DSO 47 days**.

### The flow covers:

**Account Intelligence → Dunning → Collections Email Outreach → Email-to-Dispute Creation → AI Reason-Code Inference → ESM Case Routing → Credit Memo Processing → Payment Clearing**

**Outcome:** DSO drops by **8 days**.

### Agents

- Receivables Account Analysis Agent
- Collections Account Preparation Agent
- Collections Email Outreach Agent
- Dunning Insights Agent
- Dispute Creation Agent
- Dispute Resolution Agent
- Receivables & Payables Clearing Agent
- ESM Case Preparation & Processing Agents

---

## Flow 3 — RR + ESM (BRIM)

**Persona:** Maria Santos, Collections Specialist — BRIM

A **€97,900 subscription invoice** has been blocked for **35 days** because of a PO digit transposition in SAP FICA.

### Joule:

**Traces Root Cause → Corrects Contract Account Document → Updates Bill-to Party → Reprints Convergent Invoice → Auto-Resolves €7.14 Rounding Dispute**

**Outcome:** The entire issue is resolved in **12 minutes**.

### Agents

- Collection Insights Agent
- Contract Account Risk Insights Agent
- Subscription Lifecycle Agent
- Contract Accounting Payment Resolution Agent
- Convergent Invoicing Execution Agent
- Contract Accounting Dispute Resolution Agent
- Payment Matching Agent
- ESM Case Preparation Agent

---

## Flow 4 — Dispute Management

**Persona:** Jordan Lee, Dispute Case Processor

Three dispute types are handled sequentially:

**Invoice Amount Error → Wrong Goods Delivered → Payment Reference Mismatch**

Each dispute is resolved using **type-aware logic**, with **HITL confirmation before every write operation** and root-cause fixes flagged.

### Agents

- Dispute Creation Agent
- Dispute Resolution Agent
- Collections Account Preparation Agent
- Receivables & Payables Clearing Agent
- Case Processing Agent
- Case Management Assistant

---

# 3. Presenter Commands

- **`Flow 1` · `Flow 2` · `Flow 3` · `Flow 4`**  
  Jump directly to that flow.

- **`Act 1` – `Act 8`**  
  Jump to an act within the current flow.

- **`cheat sheet`**  
  Show all prompts + expected responses — presenter only.

- **`reset`**  
  Restart from opening menu.

- **`end session`**  
  Exit character and show combined KPI summary.

---

# 4. SAP Products Illustrated

- SAP S/4HANA FI-AR — Accounts Receivable
- SAP BRIM — FICA, Convergent Invoicing, Subscription Order Management
- SAP ESM — Enterprise Service Management
- SAP FSCM Dispute Management
- SAP Business AI Platform / SAP Joule

---

# 5. Key Metrics Demonstrated

- **ESM Standalone**
  - 22-minute handle time
  - Batch error affecting four employees discovered

- **AR + ESM**
  - DSO 47 → 39 days
  - €28,000 payment recovered

- **RR + ESM**
  - 35-day revenue block resolved in 12 minutes
  - €97,900 unblocked

- **Dispute Management**
  - Three dispute types
  - €11,100 resolved
  - 82% time saving vs. manual

---

# 6. Demo Script — Prompt Sequence + Expected Joule Responses

Use the following as the **presenter guide**. Each act shows exactly what to say, what Joule returns, and the corresponding WOW moment.

---

# FLOW 1 — ESM STANDALONE

**Launch:** `Start the ESM demo`

**Persona:** Rachel Chen, HR & Finance Service Desk Lead

## Act 1 — Intelligent Intake

### Say

> "Joule, show me the latest service request that came in from Geoff Hill."

### Joule Shows

Intake card **SR-2026-18841**:

- Two issues extracted: parental leave + €240 PEN-ADJ deduction
- Priority escalated to HIGH

### WOW Moment

> A single employee message is automatically split into HR + Finance workstreams.

---

## Act 2 — Case Preparation

### Say

> "Yes, go ahead and prepare the cases."

### Joule Shows

- **CS-ESM-2026-11841** — HR
- **CS-FIN-2026-29845** — Finance
- Cases created and routed
- SLA established
- Proactive flag: three other employees affected by the same payroll batch

### WOW Moment

> Nobody asked about the other employees — Joule independently found the batch pattern.

---

## Act 3 — Knowledge + Historical Case Intelligence

### Say

> "What does our knowledge base say about parental leave in Germany, and have we handled similar cases before?"

### Joule Shows

- Three KB articles — 98% / 91% / 87% match
- Five historical cases
- Historical resolution time: 12–31 minutes
- Entitlement confirmed: 14 weeks full pay

### WOW Moment

> 98% match — Rachel has the answer without conducting manual research.

---

## Act 4 — Payroll Investigation

### Say

> "Investigate the payslip deduction — why did PEN-ADJ appear and is it correct?"

### Joule Shows

**Root cause:**

- Pension batch **PRB-2026-08** wrongly hit **CC-MFG-040**
- Verdict: **INCORRECT**
- **PAJ-2026-3841** prepared
- €240 refund
- Three additional employees flagged: EMP-10044 / 52 / 63
- Total exposure: €960

### WOW Moment

> One complaint leads Joule to discover a €960 batch error affecting four people.

---

## Act 5 — Cross-System Action

### Say

> "Yes, flag the other employees and proceed with Geoff's adjustment."

### Joule Shows

Simultaneously:

- PAJ raised
- Batch escalation **ESC-FIN-2026-0091** sent
- Parental leave confirmed in HR record

### WOW Moment

> Three cross-system actions executed through one response.

---

## Act 6 — Unified Employee Communication

### Say

> "Draft the response email to Geoff covering both issues."

### Joule Shows

Complete email **EM-2026-ESM-11841** covering:

- Parental leave entitlement
- Payslip refund

### WOW Moment

> Two departments. One clean employee communication. Rachel only needs to approve.

---

## Act 7 — Close and Measure

### Say

> "Send it and close both cases."

### Joule Shows

- Both cases closed
- SLA met
- 22-minute handle time
- 4.8/5 CSAT
- Batch correction escalated

### WOW Moment

> **"22 minutes — employee didn't wait for inter-department handoffs."**

---

# FLOW 2 — AR + ESM

**Launch:** `Start the AR demo`

**Persona:** Avery Kim, Collections Specialist

## Act 1 — Receivables Intelligence

### Say

> "Joule, give me the full receivables picture for CA Networks AG."

### Joule Shows

- DSO: 47 days — +17 vs. benchmark
- Payment Rating: E
- €62K open
- Broken PTP
- Aging table
- Four overdue invoices

### WOW Moment

> CFO-level and invoice-level intelligence in one response.

---

## Act 2 — Customer 360

### Say

> "Show me the full 360 — disputes, promises to pay, dunning history."

### Joule Shows

- Four open disputes — €8,938
- Broken PTP-091
- Dunning at Level 3 Final Notice
- Recommendation: outreach before legal action

### WOW Moment

> Broken PTP + three ignored dunning notices allow the agent to build the escalation case.

---

## Act 3 — Collections Outreach

### Say

> "Draft the collections outreach email to Thomas Weber."

### Joule Shows

Email **CE-2026-CA001**:

- Three invoices cited — €27,400
- Broken PTP referenced
- Seven-day deadline
- Legal escalation warning

### WOW Moment

> CFO-appropriate communication with invoice-level specifics generated directly from account data.

---

## Act 4 — Dunning Intelligence

### Say

> "Send it. And what does Joule recommend on dunning — should we escalate?"

### Joule Shows

Balanced assessment of factors for and against escalation.

**Recommendation:**

- Seven-day window
- Soft order block
- **DUN-2026-7738** issued
- Level 4 + legal if no response by September 26

### WOW Moment

> The agent does not simply escalate — it weighs both sides.

---

## Act 5 — Email-to-Dispute

### Say

> "Thomas just replied. He says they dispute invoice INV-2026-10077 — they received only 85 units, not 100. He wants a dispute case raised."

### Joule Shows

- **DIS-2026-37737** created
- Reason code QUANT automatically inferred
- **DLN-2026-8847** cross-referenced
- Claim validated
- Overcharge = 15 × €128 = €1,920

### WOW Moment

> "85 units, not 100" becomes a structured dispute: Joule infers the reason code, finds the delivery note, validates the claim, and calculates the overcharge.

---

## Act 6 — AR-to-ESM Handoff

### Say

> "Yes, route it to ESM and set up the case."

### Joule Shows

**CS-AR-2026-44471** created with complete AR context pre-loaded:

- Customer
- Invoice
- Dispute
- Validated claim

### WOW Moment

> No re-investigation — AR context follows the case into ESM.

---

## Act 7 — Resolution

### Say

> "Process the resolution — issue the credit memo."

### Joule Shows

- **CM-2026-3318** — €1,920
- INV-10077 adjusted from €12,800 → €10,880
- Thomas notified
- Both cases closed
- S/4HANA updated

### WOW Moment

> Complete AR-to-ESM dispute cycle executed end to end.

---

## Act 8 — Payment Clearing

### Say

> "Yes, create the PTP and then show me what happens when the payment clears."

### Joule Shows

- €28,000 cleared against three invoices
- DSO: 47 → 39 days
- Improvement: 8 days
- PTP-097 covers remaining €34,600

### WOW Moment

> **"8-day DSO improvement from one collections cycle."**

---

# FLOW 3 — RR + ESM (BRIM)

**Launch:** `Start the RR demo`

**Persona:** Maria Santos, Collections Specialist — BRIM

## Act 1 — Risk Intelligence

### Say

> "Joule, show me the risk profile for CloudTech Services."

### Joule Shows

- BBI Risk Score: 84/100
- DSO: 61 days
- €97,900 blocked
- DSO trend worsening April → August
- Agent insight: **"process blocker, not credit risk"**

### WOW Moment

> The agent distinguishes a billing-process problem from a customer credit-risk problem.

---

## Act 2 — Email-to-Case

### Say

> "Open Mike's email and create the case."

### Joule Shows

- **CS-RR-2026-23251** created
- PO-2026-88712 vs. PO-2026-88731
- Digit transposition identified
- Customer intent: **"ready to pay"**

### WOW Moment

> Plain email becomes structured information and the exact error type is identified.

---

## Act 3 — Root-Cause Investigation

### Say

> "Yes — investigate the subscription and find out how this error happened."

### Joule Shows

Root cause traced to:

- Manual FICA entry — 2026-07-28
- Digits 3 ↔ 1 transposed
- Error inherited by billing run **BRN-2026-08**
- Payment blocked for 35 days

### WOW Moment

> **"Joule traced a 35-day revenue block to a single keypress from seven weeks ago."**

---

## Act 4 — Process Correction

### Say

> "Process the correction — fix the PO reference and update the bill-to party."

### Joule Shows

- PO corrected: 88712 → 88731
- **CAD-2026-50019**
- Bill-to updated to Sarah Mueller
- **SOM-2026-7749**
- Old invoice voided
- All actions logged

### WOW Moment

> Multiple BRIM system updates through one confirmation.

---

## Act 5 — Corrected Invoice

### Say

> "Reissue the corrected invoice."

### Joule Shows

**INV-2026-90050063**

- Correct PO
- Sarah Mueller
- Due September 26
- Total resolution time: **12 minutes**
- Manual equivalent: **3–5 days**

### WOW Moment

> **"12 minutes to resolve a 35-day payment block."**

---

## Act 6 — Promise to Pay

### Say

> "Create the PTP and confirm payment expectation with Mike."

### Joule Shows

- PTP-136 — €97,900
- BBI score: 84 → 71
- DSO: 61 → 57 projected
- Mike replies within two minutes: **"Sarah will pay by Friday."**

### WOW Moment

> The customer was waiting for the process issue to be corrected.

---

## Act 7 — Autonomous Micro-Dispute Resolution

### Say

> "Yes — what's the BRIM convergent invoice dispute about?"

### Joule Shows

- **DISP-2026-171**
- €7.14 rounding delta
- Below write-off threshold
- Automatically resolved
- No human action required

### WOW Moment

> **"Invisible value" — a dispute that could sit in a queue for days is resolved in seconds.**

---

## Act 8 — Close and Measure

### Say

> "Great — close the ESM case and show me the full outcome."

### Joule Shows

- €97,900 unblocked
- Resolution time: 12 minutes
- DSO: −4 days projected
- BBI: 84 → 71
- PTP-136 active

### WOW Moment

> **"35-day revenue block from a typo, resolved in 12 minutes."**

---

# FLOW 4 — DISPUTE MANAGEMENT

**Launch:** `Start the dispute demo`

**Persona:** Jordan Lee, Dispute Case Processor

## Act 1 — Dispute Queue Intelligence

### Say

> "Joule, give me my dispute queue for today."

### Joule Shows

- 14 open disputes
- Three high priority
- €47,800 exposure
- 87% on-time
- Top-three table with type + amount

### WOW Moment

> Full dispute-queue intelligence without opening FSCM.

---

## Act 2 — Invoice Amount Error

### Say

> "Let's start with DIS-2026-37737 — the invoice amount error."

### Joule Shows

**Root cause:**

- PR00 standard price: €40
- Contract CPC-PDG-2026: €35
- Standard price overrode contract price
- Claim: VALID
- Recommended credit memo **CM-2026-3400 — €500**

### WOW Moment

> The agent identifies the specific pricing-condition misconfiguration.

---

## Act 3 — Human-in-the-Loop Resolution

### Say

> "Yes — process the credit memo."

Then confirm HITL.

### Joule Shows

First:

**⚠️ HITL Confirmation Before Write**

After confirmation:

- CM-2026-3400 issued
- Invoice adjusted
- Pricing fix flagged to SD team

### WOW Moment

> **"Agents prepare, humans authorise."**

---

## Act 4 — Wrong Goods Delivery

### Say

> "Open DIS-2026-37821 — the wrong goods delivery for Meridian Engineering."

### Joule Shows

- DN-2026-4491 confirms wrong product shipped
- V-belt vs. timing belt
- Return **RT-2026-8841**
- Credit **CM-2026-3401 — €9,600**
- Replacement scheduled
- Warehouse SKU issue flagged

### WOW Moment

> The delivery-note cross-reference proves the claim, while a three-invoice batch is handled as one action.

---

## Act 5 — Payment Mismatch

### Say

> "Last one — DIS-2026-37901, the payment mismatch for Vortek Industries."

### Joule Shows

€1,400 shortfall caused by an expired discount being incorrectly deducted.

Clearing proposal **CLP-2026-14441**:

- Clear €21,400
- Write off €140 — within WT-003
- Request €1,260 through AR letter

### WOW Moment

> A three-way resolution — clear + write-off + request — is created from a single payment gap.

---

## Act 6 — Session Summary

### Say

> "Save the dispute findings and show me the session summary."

### Joule Shows

- Three disputes
- €11,100 resolved
- Eight-minute average
- Manual equivalent: 45 minutes
- 82% productivity gain
- Three HITL confirmations
- Two root-cause fixes flagged

### WOW Moment

> **"Three dispute types, 30 minutes, Jordan never opened a transaction code."**

---

# 7. Closing the Demonstration

Type:

`end session`

Joule exits character and renders the combined KPI summary across all four flows, along with all **20+ AI agents grouped by domain**.

## Combined Business Outcomes

- **Demo Flows:** 4
- **Total Acts:** 29
- **AI Agents Demonstrated:** 20+
- **Domains:** ESM · AR · BRIM/RR · FSCM Dispute Management
- **Total Receivables Resolved:** €127,900+
- **DSO Improvement:** Up to 8 days
- **FTE Productivity Gain:** 35–82%
- **HITL Confirmations:** All write operations

---

# 8. End-to-End Demonstration Story

Across the four flows, the demonstration illustrates an integrated Autonomous Finance operating model:

### 1. Understand the Request / Financial Situation

↓

### 2. Analyze Account, Customer, Case, Invoice, Contract and Transaction Context

↓

### 3. Detect Risk, Exceptions, Patterns and Root Causes

↓

### 4. Recommend the Next Best Financial or Service Action

↓

### 5. Coordinate Specialized AI Agents Across Finance + ESM

↓

### 6. Prepare Cases, Communications, Disputes, Adjustments and Transactions

↓

### 7. Apply Human-in-the-Loop Approval for Write Operations

↓

### 8. Execute Resolution Across Enterprise Systems

↓

### 9. Communicate with the Employee or Customer

↓

### 10. Close Cases and Financial Exceptions

↓

### 11. Measure DSO, Revenue Recovery, Resolution Time, Productivity and Customer Outcomes

The result is a shift from isolated AI assistance toward **coordinated, agent-enabled Autonomous Finance processes spanning ESM, Accounts Receivable, Recurring Receivables, BRIM and Dispute Management.**

---

# License

Apache 2.0 — see LICENSE.

---

# Author

**Sourajit Ghosh**

SAP Solution Advisory, CX AI Enterprise Architecture

Based on the SAP Autonomous Finance AI Roadmap.

> **Note:** All scenarios are illustrative simulations using mock data. No live SAP system is connected. These demos are intended to show how SAP Joule and Autonomous Finance AI capabilities would work in a real deployment.
