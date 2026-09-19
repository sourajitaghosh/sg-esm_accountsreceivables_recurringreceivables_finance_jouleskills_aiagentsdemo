# Presenter Cheat Sheet — SAP Autonomous Finance Demo
## Prompt sequence + expected Joule output for all 4 flows

---

# FLOW 1 — ESM STANDALONE
**Launch phrase:** `"Start the ESM demo"`
**Persona:** Rachel Chen, HR & Finance Service Desk Lead

---

### Act 1 — Service Request Intake

**You say:**
> "Joule, show me the latest service request that came in from Geoff Hill."

**Joule shows:**
- AI Transparency: Self-Service Assistant + Case Preparation Agent
- Intake card for SR-2026-18841: Geoff Hill, Production Director, two issues — parental leave inquiry + unrecognised €240 payslip deduction (code PEN-ADJ)
- Priority escalated to HIGH because financial impact found
- Asks: "Shall I prepare both cases and route to the right teams?"

**WOW moment:** Joule split a single free-text employee message into two distinct workstreams (HR + Finance) and escalated priority automatically.

---

### Act 2 — Case Preparation & Classification

**You say:**
> "Yes, go ahead and prepare the cases."

**Joule shows:**
- AI Transparency: Case Preparation Agent + Interaction Management Assistant
- Case 1: CS-ESM-2026-11841 → HR Services — Benefits & Leave (48h SLA, Medium)
- Case 2: CS-FIN-2026-29845 → Finance Services — Payroll (24h SLA, HIGH)
- **Proactive flag:** PEN-ADJ code matched to pension recalculation batch — 3 other employees also affected

**WOW moment:** Nobody asked about other employees — Joule found the batch pattern and surfaced it proactively.

---

### Act 3 — Knowledge Retrieval & Similar Cases

**You say:**
> "What does our knowledge base say about parental leave in Germany, and have we handled similar cases before?"

**Joule shows:**
- AI Transparency: Case Processing Agent + Service Management Assistant
- 3 KB articles: KB-HR-2026-003 (98% match — parental leave entitlement), KB-HR-2026-019 (91% — childcare allowance), KB-FIN-2026-041 (87% — payroll adjustment workflow)
- 5 similar historical cases, all resolved in 12–31 minutes
- Entitlement confirmed: 14 weeks full pay, 4 weeks 75%, childcare allowance €180/month from November

**WOW moment:** 98% knowledge match — Rachel has the answer without any research. 5 similar cases give the resolution blueprint.

---

### Act 4 — Case Processing & Investigation

**You say:**
> "Investigate the payslip deduction — why did PEN-ADJ appear and is it correct?"

**Joule shows:**
- AI Transparency: Case Processing Agent + Accounts Receivable Assistant
- Root cause: Pension batch PRB-2026-08 ran 2026-08-28, incorrectly applied to Manufacturing Operations cost centre CC-MFG-040
- Geoff was wrongly included — his pension tier was already correct
- Verdict: INCORRECT — €240 should not have been deducted
- Payroll adjustment PAJ-2026-3841 prepared (€240 refund, October payslip)
- 3 other employees in CC-MFG-040 also affected: EMP-10044, EMP-10052, EMP-10063 (total €960 error)

**WOW moment:** One employee complaint → Joule found a batch error affecting 4 people and €960 total overpayment.

---

### Act 5 — Specialised Finance Support

**You say:**
> "Yes, flag the other employees and proceed with Geoff's adjustment."

**Joule shows:**
- AI Transparency: Accounts Receivable Assistant + HR Service Assistant
- ✅ PAJ-2026-3841 raised — €240 refund on October payslip
- ✅ Batch escalation ESC-FIN-2026-0091 raised — 3 other employees flagged to Payroll team
- ✅ Parental leave entitlement confirmed and logged in HR records

**WOW moment:** Three separate actions across HR and Finance completed simultaneously in one response.

---

### Act 6 — Communication & Resolution

**You say:**
> "Draft the response email to Geoff covering both issues."

**Joule shows:**
- AI Transparency: Interaction Management Assistant + Case Management Assistant
- Complete email EM-2026-ESM-11841 to Geoff Hill covering BOTH issues in one message:
  - Parental leave entitlement (14 weeks, childcare allowance, HR record flagged)
  - €240 deduction explained + PAJ-2026-3841 refund confirmed for October payslip
- Professional, clear, with case references

**WOW moment:** Two departments, two case resolutions, one clean employee email — Rachel just reviews and sends.

---

### Act 7 — Case Closure & Learning

**You say:**
> "Send it and close both cases."

**Joule shows:**
- AI Transparency: Case Management Assistant + Service Management Assistant
- Both cases closed with SLA met
- KPI card: 22 min handle time, 4.8/5 predicted CSAT, €240 adjustment raised, €960 batch correction escalated, 3 KB articles used, 5 similar cases matched
- Proactive suggestion: tag KB-FIN-2026-041 with PEN-ADJ pattern for faster future recognition

**Close with:** *"SAP ESM — from a single employee message to a payroll batch correction, resolved in 22 minutes."*

---
---

# FLOW 2 — AR + ESM
**Launch phrase:** `"Start the AR demo"`
**Persona:** Avery Kim, Collections Specialist

---

### Act 1 — Account Intelligence & DSO Analysis

**You say:**
> "Joule, give me the full receivables picture for CA Networks AG."

**Joule shows:**
- AI Transparency: Receivables Account Analysis Agent + Collections Account Preparation Agent
- KPI card: DSO 47 days (benchmark 30, +17 ⚠️), trend worsening since Q1, Payment Behaviour E (Critical), €62K open, broken PTP from 48 days ago
- Aging table: 0–30: €8,400 | 31–60: €12,800 | 61–90: €6,200 | 90+: €34,600
- Invoice table: 4 overdue invoices, oldest 79 days, dispute flags, broken promise highlighted

**WOW moment:** Full CFO-level picture + invoice-level detail in one response. No SAP GUI navigation.

---

### Act 2 — Collection Preparation & 360° View

**You say:**
> "Show me the full 360 — disputes, promises to pay, dunning history."

**Joule shows:**
- AI Transparency: Collections Account Preparation Agent + Dunning Insights Agent
- 4 open disputes (DIS-37737 to DIS-37736), total exposure €8,938
- PTP history: PTP-091 BROKEN (€12,800, committed 2026-08-01), PTP-094 active
- Dunning: Level 1 → 2 → 3, all ignored, currently at Final Notice
- Recommendation: Immediate CFO outreach before escalating to legal; soft order block >€5,000

**WOW moment:** Broken PTP + 3 ignored dunning notices = the agent builds the escalation case automatically.

---

### Act 3 — Customer Outreach Email

**You say:**
> "Draft the collections outreach email to Thomas Weber."

**Joule shows:**
- AI Transparency: Collections Email Outreach Agent + Interaction Management Assistant
- Complete email CE-2026-CA001 to Thomas Weber (CFO):
  - 3 specific invoices cited (INV-10077, INV-10091, INV-10103), total €27,400
  - References broken PTP-091
  - 7-day deadline for payment or written dispute rationale
  - Escalation warning (legal + order hold)
  - Payment portal link
  - Avery's direct contact

**WOW moment:** CFO-appropriate tone, invoice specifics, legal escalation path — all generated from account data.

---

### Act 4 — Dunning Insights

**You say:**
> "Send it. And what does Joule recommend on dunning — should we escalate?"

**Joule shows:**
- AI Transparency: Collections Email Outreach Agent + Dunning Insights Agent
- Email logged as CE-2026-CA001
- Balanced dunning assessment:
  - Arguments FOR escalation: 3 ignored notices, 1 broken PTP, Rating E, 45 days silence, DIS-37727 at legal threshold
  - Arguments AGAINST: Active PTP-094 still valid, email just sent (allow 7 days), DIS-37737 under review
- Recommendation: 7-day response window, soft order block, DUN-2026-7738 issued in parallel, Level 4 + legal if no response by 2026-09-26

**WOW moment:** Joule doesn't just escalate — it weighs both sides and gives a reasoned recommendation.

---

### Act 5 — Dispute Creation from Email

**You say:**
> "Thomas just replied. He says they dispute invoice INV-2026-10077 — they received only 85 units, not 100. He wants a dispute case raised."

**Joule shows:**
- AI Transparency: Dispute Creation Agent + Collections Account Preparation Agent
- Dispute DIS-2026-37737 created
- Reason code QUANT inferred from natural language ("received only 85 units, not 100")
- Delivery note DLN-2026-8847 automatically cross-referenced → confirms 85 units shipped
- Claim status: VALIDATED
- Overcharge calculated: 15 units × €128 = €1,920
- Recommended action: Credit memo for €1,920, adjust INV-10077 from €12,800 → €10,880

**WOW moment:** "85 units, not 100" → agent inferred QUANT reason code, found the delivery note, validated the claim, calculated the overcharge. No dropdown, no manual lookup.

---

### Act 6 — ESM Case Intake & Routing

**You say:**
> "Yes, route it to ESM and set up the case."

**Joule shows:**
- AI Transparency: Case Preparation Agent + Interaction Management Assistant
- ESM case CS-AR-2026-44471 created:
  - Type: Billing Dispute — AR Integration
  - Priority: HIGH (>€5,000 threshold)
  - Assigned: Finance Services — Billing Adjustments
  - SLA: 24 hours
  - AR context pre-loaded: customer, invoice, dispute ID, delivery note, validated claim, contact details

**WOW moment:** The Finance team inherits the full AR investigation — they don't re-investigate from scratch.

---

### Act 7 — Dispute Resolution & Credit Memo

**You say:**
> "Process the resolution — issue the credit memo."

**Joule shows:**
- AI Transparency: Dispute Resolution Agent + Case Processing Agent
- ✅ CM-2026-3318 issued — €1,920
- ✅ INV-2026-10077 adjusted: €12,800 → €10,880
- ✅ Thomas Weber notified
- ✅ DIS-2026-37737 closed — Resolved: Credit Memo
- ✅ CS-AR-2026-44471 closed
- ✅ S/4HANA FI-AR updated
- Remaining open balance: €60,080
- Thomas confirmed payment of €28,000 incoming

---

### Act 8 — Payment Clearing & DSO Impact

**You say:**
> "Yes, create the PTP and then show me what happens when the payment clears."

**Joule shows:**
- AI Transparency: Receivables & Payables Clearing Agent + Receivables Account Analysis Agent
- PTP-097 created: €28,000 committed 2026-09-22
- €28,000 cleared against INV-10077 (adjusted), INV-10091, INV-10103, partial INV-10118
- KPI impact card:
  - DSO: 47 → 39 days (−8 days ✅)
  - Open balance: €32,080 (was €62,000)
  - PTP-097 covers remaining €34,600 due October 1st
  - Dunning level reset to 1

**Close with:** *"SAP AR with ESM integration — Avery handled the full collections cycle without leaving Joule. DSO down 8 days."*

---
---

# FLOW 3 — RR + ESM (BRIM)
**Launch phrase:** `"Start the RR demo"`
**Persona:** Maria Santos, Collections Specialist — BRIM

---

### Act 1 — Collection Risk Insights

**You say:**
> "Joule, show me the risk profile for CloudTech Services."

**Joule shows:**
- AI Transparency: Collection Insights Agent + Contract Account Risk Insights Agent
- KPI card: BBI Risk Score 84/100 (HIGH), DSO 61 days (+31 vs benchmark), credit 57% utilised
- DSO trend table: Apr 44 → May 49 → Jun 53 → Aug 61 (consistent worsening)
- €97,900 blocked on invoice INV-90050062 (PO mismatch, 35 days)
- Key insight from agent: "This is a process blocker, not a credit risk — healthy subscription customer unable to pay due to data error"

**WOW moment:** The agent distinguishes a billing process error from a genuine credit risk. That's judgment, not just data retrieval.

---

### Act 2 — ESM Case Intake

**You say:**
> "Open Mike's email and create the case."

**Joule shows:**
- AI Transparency: Self-Service Assistant + Case Preparation Agent
- ESM case CS-RR-2026-23251 created
- Email from Mike Ross parsed: "PO on invoice PO-2026-88712, our PO is PO-2026-88731"
- AI extraction:
  - Invoice: INV-2026-90050062 · €97,900
  - PO on invoice: PO-2026-88712 (incorrect)
  - Customer PO: PO-2026-88731 (correct)
  - Issue type: PO reference mismatch — digit transposition
  - Customer intent: Ready to pay, process blocker only
- Priority HIGH (>€50K blocked)

**WOW moment:** Joule read "PO-2026-88712 vs PO-2026-88731" and identified it as a digit transposition. Structured extraction from a plain email.

---

### Act 3 — Subscription Context & Root Cause

**You say:**
> "Yes — investigate the subscription and find out how this error happened."

**Joule shows:**
- AI Transparency: Subscription Lifecycle Agent + Convergent Invoicing Execution Agent
- Subscription SUB-2026-19543 retrieved (€97,900/month, Enterprise tier)
- Root cause traced:
  - 2026-07-28: Manual PO update in Contract Account Document
  - Data entry error: PO-2026-88731 entered as PO-2026-88712 (digits 3↔1 transposed)
  - August billing run BRN-2026-08 inherited the incorrect PO
  - Invoice INV-90050062 generated with wrong PO → auto-rejected by CloudTech's AP system
  - 35 days blocked
- Fix required: Correct PO in FICA, void invoice, reissue

**WOW moment:** "Joule traced a 35-day revenue block to a single keypress from 7 weeks ago." This is the BRIM integration depth.

---

### Act 4 — Contract Correction

**You say:**
> "Process the correction — fix the PO reference and update the bill-to party."

**Joule shows:**
- AI Transparency: Contract Accounting Payment Resolution Agent + Subscription Lifecycle Agent
- ✅ PO reference corrected in FICA: PO-88712 → PO-88731 (CAD-2026-50019 created)
- ✅ Bill-to party updated: Mike Ross → Sarah Mueller, Finance Director (SOM-2026-7749)
- ✅ INV-90050062 voided
- All corrections logged with audit trail

---

### Act 5 — Convergent Invoice Reissue

**You say:**
> "Reissue the corrected invoice."

**Joule shows:**
- AI Transparency: Convergent Invoicing Execution Agent
- INV-2026-90050063 issued:
  - Amount: €97,900 (unchanged)
  - PO reference: PO-2026-88731 ✓ (corrected)
  - Bill-to: Sarah Mueller, Finance Director
  - Due date: 2026-09-26 (7-day window)
  - Sent to sarah.mueller@cloudtech.de
- **Total time to correct: 12 minutes** (manual equivalent: 3–5 business days)

**WOW moment:** "12 minutes to resolve a 35-day payment block." Pause here for effect.

---

### Act 6 — Payment Resolution

**You say:**
> "Create the PTP and confirm payment expectation with Mike."

**Joule shows:**
- AI Transparency: Contract Accounting Payment Resolution Agent + Collection Insights Agent
- ✅ PTP-136 created: €97,900, due 2026-09-26, auto-reminder set for day 5
- ✅ Confirmation email to Mike Ross sent
- ✅ BBI Risk Score updated: 84 → 71 (blocked invoice resolved)
- ✅ DSO projection: 61 → 57 days after payment
- Mike's reply (2 minutes): "Perfect — Sarah will process payment by Friday."

**WOW moment:** Mike replied in 2 minutes — customer was waiting for this fix.

---

### Act 7 — Convergent Invoice Dispute

**You say:**
> "Yes — what's the BRIM convergent invoice dispute about?"

**Joule shows:**
- AI Transparency: Contract Accounting Dispute Resolution Agent + Payment Matching Agent
- DISP-2026-171: €7.14 rounding delta between FICA aggregation and Convergent Invoice line total
- Root cause: Standard BRIM rounding behaviour at aggregation boundary
- Assessment: Below write-off threshold WT-003 (max €200)
- Resolution: ✅ System credit note applied automatically — no customer action needed — DISP-2026-171 closed

**WOW moment:** A dispute that would normally sit in a queue for days — auto-resolved by the agent in seconds. "Invisible value."

---

### Act 8 — Case Closure & Accelerated Cash

**You say:**
> "Great — close the ESM case and show me the full outcome."

**Joule shows:**
- AI Transparency: Case Management Assistant + Collection Insights Agent
- KPI summary card:
  - ESM case CS-RR-2026-23251: closed, 12 min handle time, SLA met
  - Revenue unblocked: €97,900
  - Time to resolve: 12 min (manual: 3–5 days)
  - DISP-2026-171: auto-resolved
  - DSO projected: 61 → 57 days
  - BBI risk: 84 → 71
  - PTP-136 active: €97,900 due 2026-09-26

**Close with:** *"SAP BRIM and ESM — a 35-day revenue block from a single digit transposition, resolved in 12 minutes."*

---
---

# FLOW 4 — DISPUTE MANAGEMENT
**Launch phrase:** `"Start the dispute demo"`
**Persona:** Jordan Lee, Dispute Case Processor

---

### Act 1 — Dispute Queue Dashboard

**You say:**
> "Joule, give me my dispute queue for today."

**Joule shows:**
- AI Transparency: Dispute Creation Agent + Receivables Account Analysis Agent
- Queue KPI card: 14 open disputes, 3 high priority, €47,800 total exposure, 87% on-time resolution rate, 4.2 days average
- Priority table of top 3:
  - DIS-2026-37737 · Precision Dynamics · AMOUNT · €500 · Invoice price error
  - DIS-2026-37821 · Meridian Engineering · DELIVERY · €9,600 · Wrong goods shipped
  - DIS-2026-37901 · Vortek Industries · PAYMENT · €1,400 · Payment mismatch

**WOW moment:** Jordan sees her full queue, exposure, and velocity in one card — no FSCM transaction codes.

---

### Act 2 — Invoice Dispute: Root Cause Analysis

**You say:**
> "Let's start with DIS-2026-37737 — the invoice amount error."

**Joule shows:**
- AI Transparency: Dispute Resolution Agent + Collections Account Preparation Agent
- DIS-2026-37737 analysis:
  - Invoice INV-2026-100891: billed €4,000 (100 × €40 standard list price PR00)
  - Customer claim: €3,500 (100 × €35 per contract CPC-PDG-2026)
  - Root cause: PR00 pricing condition overrode customer-specific contract price
  - Evidence: Contract CPC-PDG-2026 (valid since 2025-01-01), email chain PDG-2026-EMC-003
  - Verdict: CUSTOMER CLAIM VALID — overcharge €500
  - Recommended action: Credit memo CM-2026-3400 (€500), pricing condition fix flagged to SD team

**WOW moment:** Agent found the specific pricing condition misconfiguration (PR00 vs CPC-PDG-2026) as the root cause.

---

### Act 3 — HITL Confirmation & Credit Memo

**You say:**
> "Yes — process the credit memo."

**Joule shows (step 1 — HITL card):**
- Confirmation required card:
  - Action: Issue CM-2026-3400 · €500
  - Applied to: INV-2026-100891
  - Effect: Balance €4,000 → €3,500
  - Posted to: S/4HANA FI-AR Company Code 1010
  - ⚠️ "This action will post a credit memo in the live system. Confirm to proceed."

*[You confirm / say "confirm" or "yes"]*

**Joule shows (step 2 — completion):**
- ✅ CM-2026-3400 issued · €500
- ✅ INV-100891 adjusted · €4,000 → €3,500
- ✅ Karl Schmidt (AP Manager) notified
- ✅ DIS-2026-37737 closed — Resolved: Billing Adjustment
- ✅ Pricing condition fix: Ticket raised for SD config team

**WOW moment:** HITL is deliberate — write operations always need human approval. "Agents advise and prepare; humans authorise."

---

### Act 4 — Logistics Dispute: Wrong Goods

**You say:**
> "Open DIS-2026-37821 — the wrong goods delivery for Meridian Engineering."

**Joule shows:**
- AI Transparency: Dispute Resolution Agent + Case Processing Agent
- DIS-2026-37821 across 3 invoices (€3,200 each = €9,600 total):
  - Ordered: ADX-14M-1750-40 (SyncPro Timing Belt)
  - Shipped: ADX-BX65-STD (ClassicV V-Belt) ← wrong product
  - DN-2026-4491 confirms: wrong product shipped
  - Root cause: Warehouse picking error — similar SKU, adjacent shelf
  - Verdict: CUSTOMER CLAIM FULLY VALID
  - Resolution: Returns order RT-2026-8841, credit memo CM-2026-3401 (€9,600), replacement shipment scheduled, apology to Claire Foster

*[Confirm to execute]*

- ✅ RT-2026-8841 created
- ✅ CM-2026-3401 issued · €9,600
- ✅ Replacement of ADX-14M-1750-40 scheduled
- ✅ Warehouse SKU adjacency issue flagged to operations

**WOW moment:** Delivery note cross-reference proved the claim instantly. Three-invoice batch handled as one action.

---

### Act 5 — Payment Dispute: Clearing Proposal

**You say:**
> "Last one — DIS-2026-37901, the payment mismatch for Vortek Industries."

**Joule shows:**
- AI Transparency: Dispute Creation Agent + Receivables & Payables Clearing Agent
- DIS-2026-37901:
  - 4 invoices totalling €22,800 · Payment received: €21,400 · Shortfall: €1,400
  - Root cause: Customer deducted 2% early payment discount on INV-102001 (€8,000) but discount window expired 2026-08-01 — paid 22 days late; also miscalculated (deducted €1,400 not €160)
  - Clearing proposal CLP-2026-14441:
    - Clear: €21,400 against 4 invoices ✓
    - Write off: €140 within threshold WT-003
    - Request: €1,260 from Vortek via AR letter (expired discount)
  - Confidence: 97%

*[Confirm to execute]*

- ✅ €21,400 cleared · CLP-2026-14441
- ✅ €140 written off · threshold WT-003
- ✅ AR collection letter sent to Hans Vetter · €1,260 due in 14 days
- ✅ DIS-2026-37901 closed

**WOW moment:** Agent calculated exactly what to clear, what to write off (within threshold), and what to request — three-way resolution from a single payment discrepancy.

---

### Act 6 — Session Summary & Audit Notes

**You say:**
> "Save the dispute findings and show me the session summary."

**Joule shows:**
- AI Transparency: Case Management Assistant + Receivables Account Analysis Agent
- All audit notes saved to all 3 dispute records
- Session KPI card:
  - 3 disputes processed
  - €11,100 total resolved (€500 + €9,600 + €1,000)
  - 2 credit memos, 1 returns order, 1 write-off
  - 3 HITL confirmations (all write ops approved by Jordan)
  - 8 min avg handle time (vs ~45 min manual baseline)
  - Productivity gain: ~82%
  - Root cause fixes flagged: 2 (pricing condition + warehouse SKU)

**Close with:** *"Three dispute types, three resolution paths, 30 minutes. That's SAP FSCM Dispute Management with Joule — Jordan didn't open a single SAP transaction."*

---
---

# FULL DEMO CLOSE
**Command:** `end session`

Joule steps out of character and renders the combined KPI summary:

```
4 flows · 29 acts · 20+ agents · 4 personas · 4 customer accounts
Domains: ESM · AR · BRIM/RR · FSCM Dispute Management
Systems: S/4HANA FI-AR · SAP BRIM/FICA · SAP ESM · FSCM
Receivables resolved: €127,900+  ·  DSO improvement: up to 8 days
FTE productivity gain: 35–82%  ·  All write operations: HITL confirmed
```

**Closing line from Joule:**
*"This is SAP Joule — one AI, one surface, four business domains. SAP Autonomous Finance in action: from employee service requests to subscription billing disputes, all in natural language, all with human oversight where it matters."*

---

# QUICK REFERENCE — ALL PROMPTS

| Flow | Act | Prompt |
|---|---|---|
| **F1** | 1 | "Joule, show me the latest service request that came in from Geoff Hill." |
| **F1** | 2 | "Yes, go ahead and prepare the cases." |
| **F1** | 3 | "What does our knowledge base say about parental leave in Germany, and have we handled similar cases before?" |
| **F1** | 4 | "Investigate the payslip deduction — why did PEN-ADJ appear and is it correct?" |
| **F1** | 5 | "Yes, flag the other employees and proceed with Geoff's adjustment." |
| **F1** | 6 | "Draft the response email to Geoff covering both issues." |
| **F1** | 7 | "Send it and close both cases." |
| **F2** | 1 | "Joule, give me the full receivables picture for CA Networks AG." |
| **F2** | 2 | "Show me the full 360 — disputes, promises to pay, dunning history." |
| **F2** | 3 | "Draft the collections outreach email to Thomas Weber." |
| **F2** | 4 | "Send it. And what does Joule recommend on dunning — should we escalate?" |
| **F2** | 5 | "Thomas just replied. He says they dispute invoice INV-2026-10077 — they received only 85 units, not 100. He wants a dispute case raised." |
| **F2** | 6 | "Yes, route it to ESM and set up the case." |
| **F2** | 7 | "Process the resolution — issue the credit memo." |
| **F2** | 8 | "Yes, create the PTP and then show me what happens when the payment clears." |
| **F3** | 1 | "Joule, show me the risk profile for CloudTech Services." |
| **F3** | 2 | "Open Mike's email and create the case." |
| **F3** | 3 | "Yes — investigate the subscription and find out how this error happened." |
| **F3** | 4 | "Process the correction — fix the PO reference and update the bill-to party." |
| **F3** | 5 | "Reissue the corrected invoice." |
| **F3** | 6 | "Create the PTP and confirm payment expectation with Mike." |
| **F3** | 7 | "Yes — what's the BRIM convergent invoice dispute about?" |
| **F3** | 8 | "Great — close the ESM case and show me the full outcome." |
| **F4** | 1 | "Joule, give me my dispute queue for today." |
| **F4** | 2 | "Let's start with DIS-2026-37737 — the invoice amount error." |
| **F4** | 3 | "Yes — process the credit memo." *(then confirm the HITL card)* |
| **F4** | 4 | "Open DIS-2026-37821 — the wrong goods delivery for Meridian Engineering." |
| **F4** | 5 | "Last one — DIS-2026-37901, the payment mismatch for Vortek Industries." |
| **F4** | 6 | "Save the dispute findings and show me the session summary." |
| **—** | END | `end session` |
