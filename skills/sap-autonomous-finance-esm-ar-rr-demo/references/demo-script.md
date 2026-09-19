# SAP Autonomous Finance Demo — Full Script

All 4 flows × 29 acts. Each act: presenter prompt, AI Transparency block, Joule response, render_ui spec, and presenter note (internal only — never shown to audience).

---

# FLOW 1: ESM STANDALONE

**Persona:** Rachel Chen, HR & Finance Service Desk Lead, Acme Global
**Trigger:** "Start the ESM demo" or presenter command `Flow 1`

**Context bridge (auto-play on activation):**
> *"Rachel, a new service request just came in from Geoff Hill in Manufacturing. I've triaged it and flagged it as High priority. Would you like the full intake summary?"*

---

## Flow 1 · Act 1 — Service Request Intake

**Presenter prompt (say this):**
> "Joule, show me the latest service request that came in from Geoff Hill."

**AI Transparency:**
> **AI Transparency**
> *• Self-Service Assistant — captured and parsed the employee's free-text request from the portal*
> *• Case Preparation Agent — extracted intent, classified request type, and flagged financial impact*

**Joule response:**

Geoff Hill submitted a service request at 09:14 this morning through the Employee Self-Service portal. I've already triaged it — here's the intake summary:

```
render_ui hint:detail size:M
Title: Service Request SR-2026-18841
Employee: Geoff Hill · EMP-10041 · Production Director · Manufacturing Operations
Date: 2026-09-10 · Channel: Self-Service Portal
Priority: HIGH (financial impact identified)
SLA: 48 hours · Status: Open

Summary:
Geoff is planning parental leave from November and needs to confirm his entitlement.
He also reports an unrecognised €240 deduction on his August payslip — code PEN-ADJ.

Two distinct issues identified:
  1. HR Policy Inquiry — Parental Leave entitlement
  2. Finance / Payroll — Incorrect deduction requiring investigation
```

I've flagged this as High priority because the payslip discrepancy has a financial impact. Shall I prepare both cases and route them to the right teams?

*📣 Presenter note: Notice Joule immediately split the single employee message into two distinct workstreams — HR and Finance. That's the Case Preparation Agent inferring intent from natural language.*

---

## Flow 1 · Act 2 — Case Preparation & Classification

**Presenter prompt (say this):**
> "Yes, go ahead and prepare the cases."

**AI Transparency:**
> **AI Transparency**
> *• Case Preparation Agent — created and classified both cases, enriched with employee history and SLA rules*
> *• Interaction Management Assistant — determined optimal routing for each case based on team capacity and expertise*

**Joule response:**

Both cases are prepared and routed:

```
render_ui hint:object-list size:M
Case 1 of 2:
  Case ID: CS-ESM-2026-11841
  Type: HR Policy Inquiry — Parental Leave
  Assigned to: HR Services — Benefits & Leave
  SLA: 48 hours · Priority: Medium
  Context loaded: Employment record, leave balance, Germany parental leave policy

Case 2 of 2:
  Case ID: CS-FIN-2026-29845
  Type: Payroll Adjustment — Incorrect Deduction
  Assigned to: Finance Services — Payroll
  SLA: 24 hours · Priority: HIGH
  Context loaded: August payslip, deduction code PEN-ADJ, payroll history
  Flag: Deduction code PEN-ADJ matched to pension recalculation batch — 3 other employees affected
```

The finance case is on a faster SLA because the payslip error is time-sensitive. The PEN-ADJ flag is important — this may not be isolated to Geoff.

*📣 Presenter note: Highlight the proactive flag — Joule found 3 other affected employees from the same pension batch. That's operational intelligence the agent surfaced without being asked.*

---

## Flow 1 · Act 3 — Knowledge Retrieval & Similar Cases

**Presenter prompt (say this):**
> "What does our knowledge base say about parental leave in Germany, and have we handled similar cases before?"

**AI Transparency:**
> **AI Transparency**
> *• Case Processing Agent — queried the knowledge base and retrieved ranked articles based on case context*
> *• Service Management Assistant — analysed historical cases for pattern matching and resolution benchmarks*

**Joule response:**

Here's what I found:

```
render_ui hint:object-list size:M
Knowledge Articles — CS-ESM-2026-11841:
  KB-HR-2026-003 · Parental Leave Entitlement Guide — Germany · Match: 98%
    → 14 weeks full pay, 4 weeks at 75% for eligible employees
    → Childcare allowance (€180/month) available from start of leave
  KB-HR-2026-019 · Childcare Allowance Policy — EEA Employees · Match: 91%
    → Eligibility: continuous employment > 12 months ✓ (Geoff: 6 years)
  KB-FIN-2026-041 · Payroll Adjustment Request Workflow · Match: 87%
    → Incorrect deductions: raise PAJ request, processed on next payroll run

Similar Cases — Last 12 Months (parental leave + payroll):
  CS-ESM-2026-11124 · Childcare allowance missing → Payroll correction · 24 min
  CS-ESM-2026-07433 · Incorrect deduction on payslip → €180 adjustment · 31 min
  CS-ESM-2026-09817 · Parental leave + bonus timing → Policy clarification · 18 min

Average resolution time: 24 minutes
Recommended approach: Confirm entitlement via KB-HR-2026-003, raise PAJ for €240 deduction
```

Geoff is fully eligible. The parental leave answer is straightforward from policy. The €240 deduction needs a PAJ request — should I draft the response and raise the adjustment?

*📣 Presenter note: 98% knowledge match means the agent is confident — Rachel doesn't need to research anything. And 5 similar cases give a clear resolution pattern.*

---

## Flow 1 · Act 4 — Case Processing & Investigation

**Presenter prompt (say this):**
> "Investigate the payslip deduction — why did PEN-ADJ appear and is it correct?"

**AI Transparency:**
> **AI Transparency**
> *• Case Processing Agent — cross-referenced payslip data with payroll records and pension configuration*
> *• Accounts Receivable Assistant — validated the deduction code against the active payroll batch*

**Joule response:**

I've investigated the PEN-ADJ deduction on Geoff's August payslip:

```
render_ui hint:detail size:M
Investigation: Deduction Code PEN-ADJ · Employee EMP-10041 · August 2026 Payslip

Finding: INCORRECT — Deduction should not have been applied

Root cause:
  Pension recalculation batch PRB-2026-08 ran on 2026-08-28
  Batch incorrectly applied a one-time pension adjustment to employees in
  cost centre CC-MFG-040 (Manufacturing Operations)
  Geoff Hill is in CC-MFG-040 → incorrectly included

Deduction: €240 (one-time pension adjustment)
Correct deduction: €0 — Geoff's pension tier was already correctly set
Payroll adjustment required: PAJ-2026-3841 · €240 refund on October payslip

Additional finding:
  3 other employees in CC-MFG-040 also incorrectly deducted
  Batch correction recommended for: EMP-10044, EMP-10052, EMP-10063
  Total overpayment to recover from company: €960
```

The €240 deduction was a payroll batch error. I've prepared PAJ-2026-3841 — ready to raise. Should I also flag the 3 other affected employees to the Payroll team?

*📣 Presenter note: Joule found the root cause AND identified a wider issue affecting 3 other employees. This is the "system of intelligence" value prop — one employee request exposed a batch error.*

---

## Flow 1 · Act 5 — Specialised Finance Support

**Presenter prompt (say this):**
> "Yes, flag the other employees and proceed with Geoff's adjustment."

**AI Transparency:**
> **AI Transparency**
> *• Accounts Receivable Assistant — raised payroll adjustment PAJ-2026-3841 and escalated batch issue*
> *• HR Service Assistant — confirmed parental leave entitlement data from HR master records*

**Joule response:**

Done. Here's what I've actioned:

```
render_ui hint:object-list size:M
Actions completed:

  ✅ Payroll adjustment PAJ-2026-3841 raised
     Amount: €240 refund to Geoff Hill
     Effective: October 2026 payslip
     Status: Submitted to Payroll for approval

  ✅ Batch issue escalated to Payroll team
     Employees affected: EMP-10044, EMP-10052, EMP-10063
     Recommended: Batch correction PRB-2026-08 rerun for CC-MFG-040
     Escalation reference: ESC-FIN-2026-0091

  ✅ Parental leave entitlement confirmed for CS-ESM-2026-11841
     Entitlement: 14 weeks full pay, 4 weeks at 75%
     Childcare allowance: €180/month — eligible from 2026-11-01
     HR records: Updated with planned leave start flag
```

All three actions are logged against their respective cases. Ready to draft Geoff's response email?

---

## Flow 1 · Act 6 — Communication & Resolution

**Presenter prompt (say this):**
> "Draft the response email to Geoff covering both issues."

**AI Transparency:**
> **AI Transparency**
> *• Interaction Management Assistant — composed personalised response integrating HR and Finance resolutions*
> *• Case Management Assistant — structured the communication for clarity and SLA compliance*

**Joule response:**

Email drafted for your review:

```
render_ui hint:detail size:M
Email Draft — EM-2026-ESM-11841
To: Geoff Hill (g.hill@acmeglobal.com)
Subject: Your Service Request SR-2026-18841 — Resolved

Hi Geoff,

Thank you for reaching out. I'm pleased to confirm both matters are resolved.

PARENTAL LEAVE ENTITLEMENT
Your entitlement as a permanent employee (6 years' service) is:
  • 14 weeks at full pay
  • 4 weeks at 75% pay
  • Childcare allowance of €180/month, effective from your leave start date
Your planned leave from November 2026 has been noted in your HR record.
Your manager Sandra Brandt has been notified.

AUGUST PAYSLIP DEDUCTION (€240 — Code PEN-ADJ)
This deduction was applied in error as part of a pension recalculation batch.
It should not have been applied to your account.
A payroll adjustment of €240 will appear as a credit on your October payslip.
Reference: PAJ-2026-3841

If you have any further questions, please don't hesitate to reply to this ticket.

Best regards,
HR & Finance Service Desk | Acme Global
Case: CS-ESM-2026-11841 | CS-FIN-2026-29845
```

Ready to send. Shall I close both cases once sent?

*📣 Presenter note: Both HR and Finance resolution threads are wrapped into a single, clean employee email. Joule handled the cross-department coordination — Rachel just reviews and sends.*

---

## Flow 1 · Act 7 — Case Closure & Learning

**Presenter prompt (say this):**
> "Send it and close both cases."

**AI Transparency:**
> **AI Transparency**
> *• Case Management Assistant — closed both cases, recorded resolution notes, updated SLA compliance status*
> *• Service Management Assistant — logged resolution patterns for future knowledge enrichment*

**Joule response:**

Email sent. Both cases closed.

```
render_ui hint:kpi size:S
ESM Session Summary — Rachel Chen · 2026-09-10

Cases resolved:          2   (CS-ESM-2026-11841 · CS-FIN-2026-29845)
Handle time:             22 minutes
SLA status:              Met (48h HR · 24h Finance)
CSAT predicted:          4.8 / 5
Additional issue found:  Batch error — 3 other employees flagged
Payroll adjustment:      PAJ-2026-3841 · €240 refund
Proactive escalation:    ESC-FIN-2026-0091 (€960 total batch correction)
Knowledge articles used: 3
Similar cases matched:   5
```

One more thing — based on the PEN-ADJ batch pattern, I recommend we tag KB-FIN-2026-041 with this incident so future agents can recognise this deduction code faster. Shall I add a case note?

*📣 Presenter note: This is the "learn and improve" moment. Joule is suggesting a knowledge update proactively. Close with: "That's SAP ESM — from a single employee request to a payroll batch correction, fully handled in 22 minutes."*

---
---

# FLOW 2: AR + ESM

**Persona:** Avery Kim, Collections Specialist, Acme Global
**Trigger:** "Start the AR demo" or presenter command `Flow 2`

**Context bridge (auto-play on activation):**
> *"Good morning, Avery. CA Networks AG has moved to your high-priority collections queue. DSO is at 47 days — 17 above benchmark — with €62,000 open and a broken promise to pay from last month. Want me to pull the full account picture?"*

---

## Flow 2 · Act 1 — Account Intelligence & DSO Analysis

**Presenter prompt (say this):**
> "Joule, give me the full receivables picture for CA Networks AG."

**AI Transparency:**
> **AI Transparency**
> *• Receivables Account Analysis Agent — aggregated aging data, DSO trend, payment behaviour score, and credit exposure*
> *• Collections Account Preparation Agent — flagged dispute exposure and broken promise to pay*

**Joule response:**

Here's the complete receivables intelligence for CA Networks AG:

```
render_ui hint:kpi size:S
CA Networks AG · BPCA00001 · Company Code 1010

DSO:                  47 days  (benchmark: 30 days · +17 days ⚠️)
DSO Trend:            Worsening — was 38 days in Q1 2026
Payment Behaviour:    E — Critical
Total open:           €62,000
Credit limit:         €150,000 · Utilised: 41%
Last payment:         €15,200 · 45 days ago
Open disputes:        4 · Total exposure: €8,938
Broken PTP:           PTP-091 · €12,800 · committed 2026-08-01
```

```
render_ui hint:table size:L
Aging Buckets — CA Networks AG:
  0–30 days:    €8,400
  31–60 days:   €12,800
  61–90 days:   €6,200
  90+ days:     €34,600
  Total:        €62,000

Top overdue invoices:
  INV-2026-10077  |  Due 2026-07-01  |  €12,800  |  79 days overdue  |  Dispute DIS-2026-37737
  INV-2026-10091  |  Due 2026-07-15  |  €8,400   |  65 days overdue  |  Broken PTP
  INV-2026-10103  |  Due 2026-08-01  |  €6,200   |  48 days overdue  |  Clean
  INV-2026-10118  |  Due 2026-08-15  |  €34,600  |  34 days overdue  |  Clean
```

Shall I prepare the collections package — email, dunning recommendation, and dispute summary?

*📣 Presenter note: The KPI card and table together give the CFO-level picture and the invoice-level detail in one Joule response. No SAP GUI navigation required.*

---

## Flow 2 · Act 2 — Collection Preparation & 360° View

**Presenter prompt (say this):**
> "Show me the full 360 — disputes, promises to pay, dunning history."

**AI Transparency:**
> **AI Transparency**
> *• Collections Account Preparation Agent — compiled dispute register, promise-to-pay history, and dunning stage*
> *• Dunning Insights Agent — analysed dunning history and recommended next action*

**Joule response:**

Full 360° collection profile for CA Networks AG:

```
render_ui hint:object-list size:M
Open Disputes:
  DIS-2026-37737  |  INV-2026-10077  |  Wrong quantity  |  €5,000    |  Open
  DIS-2026-37739  |  INV-2026-10091  |  Pricing error   |  €2,400    |  In Review
  DIS-2026-37727  |  INV-2026-10103  |  Late delivery   |  €1,200    |  Escalated
  DIS-2026-37736  |  INV-2026-10118  |  Wrong goods     |  €338      |  New

Promises to Pay:
  PTP-091  |  €12,800  |  Committed 2026-08-01  |  BROKEN — 48 days ago
  PTP-094  |  €6,200   |  Committed 2026-09-30  |  Active

Dunning History:
  Level 1 · 2026-07-15 · No response
  Level 2 · 2026-08-01 · No response
  Level 3 · 2026-08-20 · Customer acknowledged, no payment
  Current: Level 3 — Final Notice

Recommendation:
  Immediate collections outreach to Thomas Weber (CFO)
  Block new orders > €5,000 until €28,000 cleared
  Escalate DIS-2026-37727 (late delivery — already at legal threshold)
```

This is a high-exposure account with a pattern of non-engagement. Recommend a direct outreach email to Thomas Weber before escalating to legal. Shall I draft it?

*📣 Presenter note: Broken PTP + 3 unanswered dunning letters + 4 disputes = the agent is building the case for either resolution or escalation. This is the "Collections Account Preparation" intelligence.*

---

## Flow 2 · Act 3 — Customer Outreach Email

**Presenter prompt (say this):**
> "Draft the collections outreach email to Thomas Weber."

**AI Transparency:**
> **AI Transparency**
> *• Collections Email Outreach Agent — drafted a personalised, assertive collections email referencing specific invoices and dispute context*
> *• Interaction Management Assistant — tuned tone for CFO-level direct communication*

**Joule response:**

Collections email drafted:

```
render_ui hint:detail size:M
Email Draft — CE-2026-CA001
To: Thomas Weber, CFO · t.weber@canetworks.de
CC: Anna Becker (Relationship Manager)
Subject: Outstanding Receivables — Formal Notice | CA Networks AG | Ref: BPCA00001

Dear Mr Weber,

I am writing regarding outstanding invoices totalling €27,400, now significantly
overdue on your CA Networks AG account.

OVERDUE INVOICES:
  INV-2026-10077  |  €12,800  |  79 days overdue  (due 2026-07-01)
  INV-2026-10091  |  €8,400   |  65 days overdue  (due 2026-07-15)
  INV-2026-10103  |  €6,200   |  48 days overdue  (due 2026-08-01)

We note that a payment commitment of €12,800 (reference PTP-091) made on
2026-08-01 was not fulfilled.

We have 4 open dispute cases on your account totalling €8,938. Our team is
actively reviewing these and will respond within 5 business days.

ACTION REQUIRED by 2026-09-26:
  1. Payment of undisputed amount: €18,462
  2. Written confirmation of disputed items with supporting documentation

If we do not receive a response, this account will be escalated to our legal
collections team and new orders may be placed on hold.

To pay immediately: [Payment Portal Link]
To discuss: Contact me directly at avery.kim@acmeglobal.com

Regards,
Avery Kim | Collections Specialist | Acme Global
```

Shall I log this and send, or would you like to adjust the tone?

---

## Flow 2 · Act 4 — Dunning Insights

**Presenter prompt (say this):**
> "Send it. And what does Joule recommend on dunning — should we escalate?"

**AI Transparency:**
> **AI Transparency**
> *• Collections Email Outreach Agent — logged CE-2026-CA001 to the account activity*
> *• Dunning Insights Agent — evaluated dunning history, payment behaviour, and account risk to recommend next step*

**Joule response:**

Email sent and logged against BPCA00001.

On dunning — here's my assessment:

```
render_ui hint:detail size:M
Dunning Recommendation — CA Networks AG

Current level:    Level 3 (Final Notice) — sent 2026-08-20
Next action:      Escalate to Level 4 OR place order block

Factors supporting escalation:
  ✗ 3 dunning notices — all ignored
  ✗ 1 broken promise to pay (PTP-091, €12,800)
  ✗ Payment Behaviour Rating: E (Critical)
  ✗ No inbound contact in 45+ days
  ✗ Dispute DIS-2026-37727 crossed legal escalation threshold

Factors supporting hold:
  ✓ Active PTP-094 (€6,200) due 2026-09-30 — not yet broken
  ✓ Collections email CE-2026-CA001 just sent — allow 7-day response window
  ✓ Dispute DIS-2026-37737 (€5,000) still under review — may unlock payment

Recommendation:
  Wait 7 days for response to CE-2026-CA001
  Place soft order block: new orders > €5,000 require CFO approval
  Issue DUN-2026-7738 (Level 3 formal dunning notice) in parallel
  Trigger Level 4 + legal referral if no response by 2026-09-26
```

I've pre-drafted DUN-2026-7738. Confirm to issue?

---

## Flow 2 · Act 5 — Dispute Creation from Email

**Presenter prompt (say this):**
> "Thomas just replied. He says they dispute invoice INV-2026-10077 — they received only 85 units, not 100. He wants a dispute case raised."

**AI Transparency:**
> **AI Transparency**
> *• Dispute Creation Agent — parsed the inbound email, inferred reason code from natural language, and created the dispute record in FSCM*
> *• Collections Account Preparation Agent — cross-referenced delivery notes to validate the quantity claim*

**Joule response:**

Dispute created from Thomas's email:

```
render_ui hint:detail size:M
Dispute Created — DIS-2026-37737 (updated)

Invoice:          INV-2026-10077
Disputed amount:  €1,920 (15 units × €128/unit)
Reason code:      QUANT — Quantity discrepancy (AI-inferred from email text)

Customer claim:   85 units received · 100 units billed
Delivery note:    DLN-2026-8847 cross-referenced
  → DN confirms: 85 units shipped · 100 units invoiced ✓ CLAIM VALIDATED

Recommended resolution:
  Credit memo for 15 units × €128 = €1,920
  Adjust INV-2026-10077 from €12,800 → €10,880

Next step:
  Route to ESM for case handling and credit memo processing
  Contact: Thomas Weber — acknowledge receipt of dispute
```

The delivery note validates Thomas's claim. The overage is €1,920. I'm routing this to ESM for case handling — shall I proceed?

*📣 Presenter note: The agent read "85 units received, not 100" and inferred reason code QUANT without any dropdown selection. Then it auto-validated against the delivery note. That's the AI extraction value.*

---

## Flow 2 · Act 6 — ESM Case Intake & Routing

**Presenter prompt (say this):**
> "Yes, route it to ESM and set up the case."

**AI Transparency:**
> **AI Transparency**
> *• Case Preparation Agent — created ESM case CS-AR-2026-44471 with full AR context pre-populated*
> *• Interaction Management Assistant — routed to Finance Services team with high-priority classification*

**Joule response:**

ESM case created and routed:

```
render_ui hint:detail size:M
ESM Case — CS-AR-2026-44471

Type:           Billing Dispute — AR Integration
Priority:       HIGH (>€5,000 threshold)
Assigned to:    Finance Services — Billing Adjustments
SLA:            24 hours

Context pre-loaded from AR:
  Customer:     CA Networks AG · BPCA00001
  Invoice:      INV-2026-10077 · €12,800
  Dispute:      DIS-2026-37737 · €1,920 (quantity overage)
  Delivery note: DLN-2026-8847 (claim validated)
  Contact:      Thomas Weber · t.weber@canetworks.de

Recommended action:
  Issue credit memo CM for €1,920
  Notify Thomas Weber within 24 hours
  Update INV-2026-10077 balance to €10,880
```

The AR dispute data is already inside the ESM case — the Finance team has everything they need to process without re-investigating. Ready to move to resolution?

---

## Flow 2 · Act 7 — Dispute Resolution & Credit Memo

**Presenter prompt (say this):**
> "Process the resolution — issue the credit memo."

**AI Transparency:**
> **AI Transparency**
> *• Dispute Resolution Agent — evaluated dispute evidence, approved resolution path, triggered billing adjustment*
> *• Case Processing Agent — processed the credit memo workflow in S/4HANA and updated the dispute record*

**Joule response:**

Dispute resolved. Here's what was processed:

```
render_ui hint:object-list size:M
Dispute Resolution — DIS-2026-37737 / CS-AR-2026-44471

✅ Credit memo CM-2026-3318 issued
   Amount: €1,920 (15 units × €128)
   Applied to: INV-2026-10077

✅ Invoice adjusted
   INV-2026-10077: €12,800 → €10,880 (net after credit)

✅ Customer notified
   Email to Thomas Weber confirming credit and adjusted balance

✅ Dispute DIS-2026-37737 closed — Resolved: Credit Memo
✅ ESM case CS-AR-2026-44471 closed — Resolved
✅ AR system updated in S/4HANA FI-AR
```

Remaining open balance on account: €60,080 (adjusted from €62,000).
Thomas has confirmed he'll process payment of €28,000 this week. Shall I create a promise to pay?

---

## Flow 2 · Act 8 — Payment Clearing & DSO Impact

**Presenter prompt (say this):**
> "Yes, create the PTP and then show me what happens when the payment clears."

**AI Transparency:**
> **AI Transparency**
> *• Receivables & Payables Clearing Agent — matched the incoming payment against open items and proposed clearing*
> *• Receivables Account Analysis Agent — recalculated DSO and account risk rating post-clearing*

**Joule response:**

PTP created and payment cleared:

```
render_ui hint:object-list size:M
Payment & Clearing — CA Networks AG

✅ Promise to Pay created
   PTP-097 · €28,000 · Committed: 2026-09-22

✅ Payment received: €28,000 · 2026-09-15
   Cleared against:
     INV-2026-10077 (adjusted): €10,880  ✓
     INV-2026-10091:            €8,400   ✓
     INV-2026-10103:            €6,200   ✓
     Partial: INV-2026-10118:   €2,520   (partial)

✅ Remaining open balance: €32,080
```

```
render_ui hint:kpi size:S
Post-Clearing Impact — CA Networks AG

DSO before:        47 days
DSO after:         39 days  (−8 days ✅)
Open balance:      €32,080 (was €62,000)
Payment Behaviour: Improving — watch for 30 days
New PTP active:    PTP-097 · €34,600 · due 2026-10-01
Dunning level:     Reset to Level 1
```

DSO dropped 8 days from this single collection action. The remaining €32,080 is covered by PTP-097 due October 1st. That's the AR cycle closed — from 47-day DSO and broken promises to payment in hand.

*📣 Presenter note: Close Flow 2 here. "That's SAP AR with ESM integration — Avery handled the full collections cycle, dispute resolution, and payment clearing without leaving Joule."*

---
---

# FLOW 3: RR + ESM

**Persona:** Maria Santos, Collections Specialist — BRIM, TeleServ B.V.
**Trigger:** "Start the RR demo" or presenter command `Flow 3`

**Context bridge (auto-play on activation):**
> *"Good morning, Maria. CloudTech Services GmbH is on your high-priority BRIM queue. Contract account 4897375 has €97,900 blocked on a PO reference error — invoice has been sitting for 35 days. Mike Ross, their CFO, just emailed. Shall I pull the full picture?"*

---

## Flow 3 · Act 1 — Collection Risk Insights

**Presenter prompt (say this):**
> "Joule, show me the risk profile for CloudTech Services."

**AI Transparency:**
> **AI Transparency**
> *• Collection Insights Agent — aggregated BRIM contract account data, BBI risk score, DSO trend, and payment behaviour*
> *• Contract Account Risk Insights Agent — evaluated subscription health and revenue risk across the account*

**Joule response:**

Here's the CloudTech Services BRIM risk profile:

```
render_ui hint:kpi size:S
CloudTech Services GmbH · BPCT00079 · Contract Account 4897375

BBI Risk Score:     84 / 100  ⚠️ HIGH RISK
DSO:                61 days (benchmark: 30 days · +31 days)
DSO Trend:          Consistently worsening — Apr: 44d · May: 49d · Jun: 53d · Aug: 61d
Credit utilised:    57% (€114,000 of €200,000)
Blocked revenue:    €97,900 (35 days overdue · PO mismatch)
Last payment:       €48,500 · 62 days ago
Subscription:       SUB-2026-19543 · SAP Cloud Platform Enterprise · €97,900/month
```

The blocked invoice is the main risk driver. CloudTech is a healthy €97,900/month subscription but they haven't been able to pay because of a PO reference error — this is a process issue, not a credit risk. Shall I open Mike's email and investigate?

*📣 Presenter note: The distinction is important — this isn't a bad customer, it's a blocked invoice from a data entry error. The agents are making that judgment from the account context.*

---

## Flow 3 · Act 2 — ESM Case Intake

**Presenter prompt (say this):**
> "Open Mike's email and create the case."

**AI Transparency:**
> **AI Transparency**
> *• Self-Service Assistant — parsed Mike Ross's inbound email and extracted the dispute detail*
> *• Case Preparation Agent — created ESM case CS-RR-2026-23251 with BRIM context pre-loaded*

**Joule response:**

Email parsed. Case created:

```
render_ui hint:detail size:M
ESM Case — CS-RR-2026-23251

Source:       Inbound email from Mike Ross · mike.ross@cloudtech.de
Subject:      Invoice INV-2026-90050062 — PO Reference Error
Type:         Billing Inquiry — BRIM Integration
Priority:     HIGH (€97,900 revenue blocked)
SLA:          24 hours
Assigned to:  Maria Santos

Email content (extracted):
  "Our AP system is blocking payment. PO on invoice is PO-2026-88712.
   Our PO is PO-2026-88731. Please correct and reissue.
   We are ready to pay as soon as this is fixed."

AI extraction:
  Invoice in dispute:   INV-2026-90050062 · €97,900
  PO on invoice:        PO-2026-88712  ← incorrect
  Customer's PO:        PO-2026-88731  ← correct
  Issue type:           PO reference mismatch (digit transposition: 88712 vs 88731)
  Customer intent:      Ready to pay — process blocker only
```

The fix is a PO reference correction — not a billing dispute. Shall I route this to the Subscription Lifecycle Agent to investigate the subscription contract and initiate the correction?

---

## Flow 3 · Act 3 — Subscription Context & Root Cause

**Presenter prompt (say this):**
> "Yes — investigate the subscription and find out how this error happened."

**AI Transparency:**
> **AI Transparency**
> *• Subscription Lifecycle Agent — retrieved contract SUB-2026-19543 and traced the PO reference through the BRIM billing run*
> *• Convergent Invoicing Execution Agent — identified the specific field error in the convergent invoice header*

**Joule response:**

Root cause found:

```
render_ui hint:detail size:M
Root Cause Analysis — INV-2026-90050062

Subscription:       SUB-2026-19543 · SAP Cloud Platform Enterprise · TeleServ B.V.
Monthly billing:    €97,900 (auto-generated via Convergent Invoicing)
Invoice generated:  2026-08-15 · Billing run BRN-2026-08

Root cause:
  PO reference field in Contract Account Document (CAD) was manually updated
  on 2026-07-28 after the customer changed their PO.
  Data entry error: PO-2026-88731 was entered as PO-2026-88712 (digits 3↔1 transposed)
  The August billing run inherited the incorrect PO reference.

Impact:
  Invoice INV-2026-90050062 generated with PO-2026-88712
  CloudTech's AP system auto-rejected: PO not in their system
  Invoice blocked for 35 days · €97,900 uncollected

Fix required:
  1. Correct PO reference in FICA: PO-2026-88712 → PO-2026-88731
  2. Void invoice INV-2026-90050062
  3. Reissue corrected invoice INV-2026-90050063
  4. Update bill-to party contact (Sarah Mueller, Finance Director — new contact)
```

Clear root cause — a single digit transposition. Ready to process the correction?

*📣 Presenter note: Joule traced a 35-day payment delay back to a typo from 7 weeks ago. That cross-system traceability — from customer email to billing run to data entry — is the BRIM integration value.*

---

## Flow 3 · Act 4 — Contract Correction

**Presenter prompt (say this):**
> "Process the correction — fix the PO reference and update the bill-to party."

**AI Transparency:**
> **AI Transparency**
> *• Contract Accounting Payment Resolution Agent — updated the PO reference in FICA and recorded the contract account document*
> *• Subscription Lifecycle Agent — updated the bill-to party to Sarah Mueller and validated subscription continuity*

**Joule response:**

Contract corrections processed:

```
render_ui hint:object-list size:M
Contract Account Corrections — CloudTech Services · 4897375

✅ PO reference corrected in FICA
   Contract Account Document: CAD-2026-50019
   PO updated: PO-2026-88712 → PO-2026-88731

✅ Bill-to party updated
   From: Mike Ross (outgoing CFO)
   To: Sarah Mueller, Finance Director
   Subscription Object: SOM-2026-7749 · Updated

✅ Invoice INV-2026-90050062 voided
   Reason: Incorrect PO reference · superseded by corrected invoice

All corrections logged against ESM case CS-RR-2026-23251
Audit trail: CAD-2026-50019
```

PO is corrected and the old invoice is voided. Ready to reissue the corrected invoice?

---

## Flow 3 · Act 5 — Convergent Invoice Reissue

**Presenter prompt (say this):**
> "Reissue the corrected invoice."

**AI Transparency:**
> **AI Transparency**
> *• Convergent Invoicing Execution Agent — generated the corrected invoice with updated PO reference and new bill-to party*

**Joule response:**

Corrected invoice issued:

```
render_ui hint:detail size:M
Invoice Reissued — INV-2026-90050063

Customer:         CloudTech Services GmbH · BPCT00079
Contract:         SUB-2026-19543 (SAP Cloud Platform Enterprise)
Amount:           €97,900 (unchanged)
PO reference:     PO-2026-88731  ✓ (corrected)
Bill-to:          Sarah Mueller, Finance Director
Invoice date:     2026-09-19
Due date:         2026-09-26 (7-day agreed window)
Format:           PDF generated · Sent to sarah.mueller@cloudtech.de

Replacing:        INV-2026-90050062 (voided)
Total time to correct: 12 minutes
Manual equivalent: 3–5 business days
```

Invoice delivered to Sarah Mueller. Mike Ross has also been cc'd per his request. Shall I create a Promise to Pay and set the payment follow-up?

*📣 Presenter note: "12 minutes to resolve a 35-day payment block." That's the headline. The manual process would involve AP emails, ticket creation, FICA data entry, CI billing run — all manual handoffs.*

---

## Flow 3 · Act 6 — Payment Resolution

**Presenter prompt (say this):**
> "Create the PTP and confirm payment expectation with Mike."

**AI Transparency:**
> **AI Transparency**
> *• Contract Accounting Payment Resolution Agent — created promise to pay and set automated follow-up trigger*
> *• Collection Insights Agent — updated risk score and DSO projection based on expected payment*

**Joule response:**

PTP created and Mike notified:

```
render_ui hint:object-list size:M
Payment Resolution — CloudTech Services

✅ Promise to Pay created
   PTP-136 · €97,900 · Due: 2026-09-26 (7-day window)
   Auto-reminder: Day 5 (2026-09-24) if no payment received

✅ Confirmation email sent to Mike Ross
   Subject: "Invoice INV-2026-90050063 issued — PO reference corrected"
   Message: Corrected invoice attached, PO-2026-88731 confirmed, due 2026-09-26

✅ Risk score updated
   BBI Risk Score: 84 → 71 (improvement — blocked invoice resolved)
   DSO projection: 61 days → 57 days (post-payment)
   ESM case CS-RR-2026-23251: Status = Awaiting Payment
```

Mike replied within 2 minutes: *"Perfect — thank you for the quick resolution. Sarah will process payment by Friday."* Ready to handle the convergent invoice rounding dispute that came up on a separate line item?

---

## Flow 3 · Act 7 — Convergent Invoice Dispute

**Presenter prompt (say this):**
> "Yes — what's the BRIM convergent invoice dispute about?"

**AI Transparency:**
> **AI Transparency**
> *• Contract Accounting Dispute Resolution Agent — retrieved and evaluated the convergent invoice rounding dispute DISP-2026-171*
> *• Payment Matching Agent — assessed the €7.14 discrepancy against write-off thresholds*

**Joule response:**

The convergent invoice dispute is a minor system-level issue:

```
render_ui hint:detail size:M
Convergent Invoice Dispute — DISP-2026-171

Type:           Rounding Difference — FICA / Convergent Invoicing
Line item:      CI-LINE-2026-9901
Amount:         €7.14
Root cause:     Rounding delta between FICA aggregation and CI line total
                (FICA: €97,907.14 · CI invoice total: €97,900.00)

Assessment:
  Below write-off threshold (WT-003: max €200)
  No customer action required
  No billing adjustment needed

Resolution:
  ✅ System credit note applied automatically — €7.14
  ✅ DISP-2026-171 closed — Auto-resolved
  ✅ Audit log: reconciliation note added to contract account 4897375
```

DISP-2026-171 is closed. This type of rounding delta is common in high-volume BRIM environments — the agent handles these automatically without manual intervention.

*📣 Presenter note: This is a great "invisible value" moment — a dispute that would normally sit in someone's queue for days is auto-resolved by the agent in seconds.*

---

## Flow 3 · Act 8 — Case Closure & Accelerated Cash

**Presenter prompt (say this):**
> "Great — close the ESM case and show me the full outcome."

**AI Transparency:**
> **AI Transparency**
> *• Case Management Assistant — closed ESM case CS-RR-2026-23251 with full audit trail*
> *• Collection Insights Agent — generated session impact summary and updated the account standing*

**Joule response:**

Case closed. Here's the full session outcome:

```
render_ui hint:kpi size:S
RR + ESM Session Summary — Maria Santos · 2026-09-19

ESM case resolved:       CS-RR-2026-23251 (12 min handle time · SLA Met)
Invoice corrected:       INV-2026-90050062 → INV-2026-90050063
Revenue unblocked:       €97,900
Time to resolve:         12 minutes  (manual: 3–5 business days)
Convergent dispute:      DISP-2026-171 · €7.14 · Auto-resolved
DSO projected:           61 → 57 days  (−4 days on payment receipt)
BBI risk score:          84 → 71  (improved)
Bill-to party updated:   SOM-2026-7749 · Sarah Mueller
PTP active:              PTP-136 · €97,900 · Due 2026-09-26
```

*📣 Presenter note: Close Flow 3 here. "SAP BRIM plus ESM — a 35-day revenue block resolved in 12 minutes. Maria didn't touch FICA, she didn't run a billing job, she didn't send a manual email chain. Joule handled everything end to end."*

---
---

# FLOW 4: DISPUTE MANAGEMENT

**Persona:** Jordan Lee, Dispute Case Processor, Precision Dynamics GmbH
**Trigger:** "Start the dispute demo" or presenter command `Flow 4`

**Context bridge (auto-play on activation):**
> *"Good morning, Jordan. You have 14 open disputes in your queue — 3 flagged high priority. Total exposure: €47,800. Want me to walk you through the top three?"*

---

## Flow 4 · Act 1 — Dispute Dashboard

**Presenter prompt (say this):**
> "Joule, give me my dispute queue for today."

**AI Transparency:**
> **AI Transparency**
> *• Dispute Creation Agent — retrieved all open disputes, categorised by type and priority*
> *• Receivables Account Analysis Agent — calculated total exposure and resolution velocity*

**Joule response:**

Here's your dispute queue:

```
render_ui hint:kpi size:S
Dispute Queue — Jordan Lee · 2026-09-19

Open disputes:          14
High priority:          3
Total exposure:         €47,800
Avg resolution time:    4.2 days
Processed this week:    8
On-time resolution:     87%
Oldest unresolved:      21 days
```

```
render_ui hint:table size:L
Top 3 Priority Disputes:

  DIS-2026-37737  |  Precision Dynamics GmbH   |  AMOUNT    |  €500    |  High  |  Invoice price error
  DIS-2026-37821  |  Meridian Engineering Ltd   |  DELIVERY  |  €9,600  |  High  |  Wrong goods shipped
  DIS-2026-37901  |  Vortek Industries AG       |  PAYMENT   |  €1,400  |  High  |  Payment mismatch
```

I recommend starting with DIS-2026-37821 — highest financial exposure at €9,600 across 3 invoices. Or we can work through them type by type. Which would you prefer?

*📣 Presenter note: Jordan sees her full queue, exposure, and velocity metrics at a glance — no FSCM transaction codes needed.*

---

## Flow 4 · Act 2 — Invoice Dispute: Root Cause Analysis

**Presenter prompt (say this):**
> "Let's start with DIS-2026-37737 — the invoice amount error."

**AI Transparency:**
> **AI Transparency**
> *• Dispute Resolution Agent — analysed the dispute, cross-referenced pricing conditions, and identified root cause*
> *• Collections Account Preparation Agent — retrieved the customer contract to validate the correct price*

**Joule response:**

Here's the full investigation on DIS-2026-37737:

```
render_ui hint:detail size:M
Dispute Analysis — DIS-2026-37737

Customer:         Precision Dynamics GmbH
Invoice:          INV-2026-100891
Billed amount:    €4,000  (100 units × €40 — standard list price PR00)
Customer claim:   €3,500  (100 units × €35 — contract price)
Discrepancy:      €500

Root cause found:
  Pricing condition PR00 applied standard list price (€40/unit)
  Customer contract CPC-PDG-2026 specifies €35/unit (valid since 2025-01-01)
  Contract price was not inherited by the billing document

Supporting evidence:
  Contract: CPC-PDG-2026 — customer-specific agreement
  Email chain: PDG-2026-EMC-003 — confirms €35/unit agreed
  Billing doc: INV-2026-100891 — PR00 condition overrode contract price

Assessment: CUSTOMER CLAIM VALID
Recommended action:
  Issue credit memo CM-2026-3400 for €500
  Apply to INV-2026-100891 (adjusted: €4,000 → €3,500)
  Fix pricing condition assignment for CPC-PDG-2026 to prevent recurrence
```

Customer is correct. The contract price should have been €35 not €40. Shall I issue the credit memo?

---

## Flow 4 · Act 3 — HITL Confirmation & Credit Memo

**Presenter prompt (say this):**
> "Yes — process the credit memo."

**AI Transparency:**
> **AI Transparency**
> *• Dispute Resolution Agent — raised credit memo request in FSCM with audit trail*
> *• Case Processing Agent — applied the credit memo to the invoice and closed the dispute record*

**Joule response:**

```
render_ui hint:detail size:M
Confirmation Required — Credit Memo Action

Action:         Issue credit memo CM-2026-3400 · €500
Applied to:     INV-2026-100891 (Precision Dynamics GmbH)
Effect:         Invoice balance adjusted €4,000 → €3,500
Posted to:      S/4HANA FI-AR under Company Code 1010
Authorised by:  Jordan Lee (HITL confirmation)

⚠️  This action will post a credit memo in the live system.
    Confirm to proceed.
```

*[Jordan confirms]*

```
render_ui hint:object-list size:M
Completed — DIS-2026-37737

✅ Credit memo CM-2026-3400 issued · €500
✅ INV-2026-100891 adjusted · €4,000 → €3,500
✅ Dispute DIS-2026-37737 closed — Resolved: Billing Adjustment
✅ Karl Schmidt (AP Manager) notified — email sent
✅ Pricing condition fix recommended → Ticket raised for SD config team
✅ Audit note saved to dispute record
```

Done. One more action — I've flagged the pricing configuration gap so the same error doesn't happen again on future invoices for Precision Dynamics. Ready for DIS-2026-37821?

*📣 Presenter note: The HITL confirmation step is deliberate — write operations always require human approval. This is the trust-and-control layer built into the Dispute Resolution Agent.*

---

## Flow 4 · Act 4 — Logistics Dispute: Wrong Goods

**Presenter prompt (say this):**
> "Open DIS-2026-37821 — the wrong goods delivery for Meridian Engineering."

**AI Transparency:**
> **AI Transparency**
> *• Dispute Resolution Agent — analysed the logistics dispute across 3 invoices and cross-referenced the delivery note*
> *• Case Processing Agent — identified the warehouse root cause and generated the returns and credit workflow*

**Joule response:**

```
render_ui hint:detail size:M
Dispute Analysis — DIS-2026-37821

Customer:         Meridian Engineering Ltd
Contact:          Claire Foster, Procurement
Delivery note:    DN-2026-4491
Total disputed:   €9,600 (3 invoices × €3,200 each)

Invoices:
  INV-2026-101045  |  €3,200  |  Ordered: ADX-14M-1750-40
  INV-2026-101046  |  €3,200  |  Ordered: ADX-14M-1750-40
  INV-2026-101047  |  €3,200  |  Ordered: ADX-14M-1750-40

Delivery note DN-2026-4491 confirms:
  Shipped: ADX-BX65-STD (ClassicV BX65 V-Belt)  ← WRONG PRODUCT
  Ordered: ADX-14M-1750-40 (SyncPro 14M Timing Belt)

Root cause:       Warehouse picking error — shelf adjacency (similar SKU location)
Assessment:       CUSTOMER CLAIM FULLY VALID

Recommended resolution:
  1. Issue returns order RT-2026-8841 for all 3 shipments
  2. Issue credit memo CM-2026-3401 for €9,600
  3. Schedule replacement shipment of ADX-14M-1750-40 (3× qty)
  4. Notify Claire Foster with apology and resolution timeline
```

This is a clean logistics fault — wrong product shipped. Full credit and returns are the right call. Process?

---

*[Jordan confirms]*

```
render_ui hint:object-list size:M
Completed — DIS-2026-37821

✅ Returns order RT-2026-8841 raised · 3 shipments
✅ Credit memo CM-2026-3401 issued · €9,600
✅ Replacement order scheduled for ADX-14M-1750-40 (qty 3)
✅ Claire Foster notified with apology and 5-day replacement timeline
✅ Dispute DIS-2026-37821 closed — Resolved: Returns + Credit
✅ Warehouse SKU adjacency issue flagged to operations team
```

---

## Flow 4 · Act 5 — Payment Dispute: Clearing Proposal

**Presenter prompt (say this):**
> "Last one — DIS-2026-37901, the payment mismatch for Vortek Industries."

**AI Transparency:**
> **AI Transparency**
> *• Dispute Creation Agent — analysed the payment shortfall, cross-referenced invoices, and calculated the discrepancy root cause*
> *• Receivables & Payables Clearing Agent — generated an optimised clearing proposal with write-off recommendation*

**Joule response:**

Payment dispute analysed:

```
render_ui hint:detail size:M
Dispute Analysis — DIS-2026-37901

Customer:           Vortek Industries AG
Contact:            Hans Vetter, Finance · h.vetter@vortek.de
Payment received:   €21,400  (ref: PAY-2026-VT-0091)
Expected:           €22,800  (4 invoices)
Shortfall:          €1,400

4 invoices in scope:
  INV-2026-102001  |  €8,000   |  2% discount deducted by customer = €160 claimed
  INV-2026-102002  |  €6,400   |  Fully covered by payment
  INV-2026-102003  |  €5,200   |  Fully covered by payment
  INV-2026-102004  |  €3,200   |  Fully covered by payment

Root cause:
  Vortek claimed 2% early payment discount on INV-2026-102001 (€8,000 × 2% = €160)
  However: discount window expired 2026-08-01 — invoice paid 22 days late
  Vortek deducted €1,400 (incorrect calculation — they used 17.5% not 2%)
  Actual discount entitlement: €0 (discount window closed)

Clearing proposal:
  Clear €21,400 against 4 invoices (full match possible)
  Write off €140 (within threshold WT-003 · max €200) — administrative efficiency
  Request €1,260 remaining balance from Vortek via AR letter
  Confidence: 97%
```

```
render_ui hint:detail size:M
Clearing Proposal — CLP-2026-14441

Clear:      €21,400 against INV-2026-102001 to INV-2026-102004
Write off:  €140 (within WT-003 threshold)
Request:    €1,260 from Vortek via AR collection letter
Letter:     Pre-drafted — explains expired discount window, requests payment in 14 days
```

Ready to execute the clearing and send the AR letter?

---

*[Jordan confirms]*

```
render_ui hint:object-list size:M
Completed — DIS-2026-37901

✅ €21,400 cleared against 4 invoices · CLP-2026-14441
✅ €140 written off within threshold WT-003
✅ AR collection letter sent to Hans Vetter · €1,260 due in 14 days
✅ Dispute DIS-2026-37901 closed — Resolved: Partial clearing + write-off
✅ Audit trail saved · write-off approved per threshold WT-003
```

---

## Flow 4 · Act 6 — Dispute Notes & Session Analytics

**Presenter prompt (say this):**
> "Save the dispute findings and show me the session summary."

**AI Transparency:**
> **AI Transparency**
> *• Case Management Assistant — saved resolution notes and audit records to all 3 dispute cases*
> *• Receivables Account Analysis Agent — compiled session productivity and dispute resolution metrics*

**Joule response:**

All findings saved. Here's your session summary:

```
render_ui hint:kpi size:S
Dispute Session Summary — Jordan Lee · 2026-09-19

Disputes processed:     3   (DIS-37737 · DIS-37821 · DIS-37901)
Total resolved:         €11,100  (€500 + €9,600 + €1,000)
Credit memos issued:    2   (CM-2026-3400 · CM-2026-3401)
Returns orders raised:  1   (RT-2026-8841)
Write-off applied:      €140 (within threshold)
Customer letters sent:  3
Pricing fix flagged:    1   (CPC-PDG-2026 condition error)
HITL confirmations:     3   (all write operations confirmed)
Average handle time:    8 minutes per dispute
Vs manual baseline:     ~45 minutes per dispute
Productivity gain:      ~82%
```

Three high-priority disputes resolved in under 30 minutes. All with full audit trails, HITL confirmation on every write operation, and root cause fixes flagged to prevent recurrence.

*📣 Presenter note: Close Flow 4 here. "That's SAP FSCM Dispute Management with Joule — Jordan didn't open a single SAP transaction. Three dispute types, three resolution paths, all handled in the same conversation."*

---
---

# COMBINED END SESSION

**Trigger:** presenter command `end session`

Step out of character and render the full demo KPI summary.

```
render_ui hint:kpi size:S
SAP Autonomous Finance Demo — Session Complete

Demo flows:              4
Total acts:              29
AI agents demonstrated:  20+
Personas:                4  (Rachel · Avery · Maria · Jordan)
Customer accounts:       4
Domains:                 ESM · AR · BRIM/RR · FSCM Dispute Management
Systems simulated:       S/4HANA FI-AR · SAP BRIM/FICA · SAP ESM · FSCM
Receivables resolved:    €127,900+
DSO improvement:         Up to 8 days per account
FTE productivity gain:   35–82%
HITL confirmations:      All write operations
```

**Flow-by-flow summary:**

**Flow 1 — ESM Standalone:** Employee request triaged, 2 cases prepared, payroll batch error discovered (affecting 4 employees), €240 adjustment raised, case closed in 22 minutes. *Agents: Self-Service Assistant, Case Preparation Agent, Case Processing Agent, Interaction Management Assistant, HR Service Assistant, Accounts Receivable Assistant, Case Management Assistant, Service Management Assistant.*

**Flow 2 — AR + ESM:** CA Networks AG collections cycle — DSO 47→39 days, €28,000 payment recovered, dispute DIS-2026-37737 resolved via ESM integration with €1,920 credit memo. *Agents: Receivables Account Analysis Agent, Collections Account Preparation Agent, Collections Email Outreach Agent, Dunning Insights Agent, Dispute Creation Agent, Dispute Resolution Agent, Receivables & Payables Clearing Agent + ESM Case Preparation + Case Processing Agents.*

**Flow 3 — RR + ESM:** CloudTech 35-day payment block from PO typo resolved in 12 minutes — €97,900 unblocked, BRIM convergent dispute auto-resolved, DSO projected -4 days. *Agents: Collection Insights Agent, Contract Account Risk Insights Agent, Subscription Lifecycle Agent, Contract Accounting Payment Resolution Agent, Convergent Invoicing Execution Agent, Contract Accounting Dispute Resolution Agent, Payment Matching Agent + ESM Case Preparation Agent.*

**Flow 4 — Dispute Management:** 3 dispute types in 30 minutes — invoice pricing error, logistics wrong goods, payment mismatch — all resolved with credit memos, returns, clearing and full audit trails. *Agents: Dispute Creation Agent, Dispute Resolution Agent, Collections Account Preparation Agent, Receivables & Payables Clearing Agent, Case Processing Agent, Case Management Assistant.*

---

*"This is SAP Joule — one AI surface, four business domains, twenty agents coordinated across SAP S/4HANA, BRIM, ESM, and FSCM. Built on the SAP Autonomous Finance roadmap. From service requests to subscription billing to dispute resolution — all in natural language."*
