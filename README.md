# SAP Autonomous Finance Demo — Joule Skill

[![REUSE compliant](https://api.reuse.software/badge/github.com/sourajitaghosh/sg-esm_accountsreceivables_recurringreceivables_finance_jouleskills_aiagentsdemo)](https://api.reuse.software/info/github.com/sourajitaghosh/sg-esm_accountsreceivables_recurringreceivables_finance_jouleskills_aiagentsdemo)

A Joule Work Desktop skill showcasing **SAP Autonomous Finance** across 4 blended demo flows — ESM, Accounts Receivables, Recurring Receivables, and Dispute Management — with 20+ AI agents coordinated across SAP S/4HANA FI-AR, SAP BRIM/FICA, SAP ESM, and FSCM Dispute Management.

No live SAP system is connected. All data is illustrative mock data. Built to show how SAP Joule and Autonomous Finance AI agents would work in a real deployment.

## Install

```bash
npx skills add sourajitaghosh/sg-esm_accountsreceivables_recurringreceivables_finance_jouleskills_aiagentsdemo

npx skills add sourajitaghosh/sg-esm_accountsreceivables_recurringreceivables_finance_jouleskills_aiagentsdemo --skill sap-autonomous-finance-esm-ar-rr-demo
```

## How to Start a Demo

Launch the full menu or jump directly into any of the 4 flows:

| Launch phrase | What starts |
|---|---|
| `Start the Autonomous Finance demo` | Flow selection menu — pick any of the 4 |
| `Start the ESM demo` | **Flow 1** — ESM Standalone (7 acts) |
| `Start the AR demo` · `Start the collections demo` | **Flow 2** — AR + ESM (8 acts) |
| `Start the RR demo` · `Start the BRIM demo` | **Flow 3** — RR + ESM (8 acts) |
| `Start the dispute demo` · `Show me dispute management` | **Flow 4** — Dispute Management (6 acts) |

## Demo Flows

### Flow 1 — ESM Standalone
**Persona:** Rachel Chen, HR & Finance Service Desk Lead

Employee submits a combined HR + payroll request. The Case Preparation Agent splits it into two workstreams, investigates a €240 payroll deduction, discovers a batch error affecting 4 employees, resolves both cases in 22 minutes.

**Agents:** Self-Service Assistant · Case Preparation Agent · Case Processing Agent · Interaction Management Assistant · HR Service Assistant · Accounts Receivable Assistant · Case Management Assistant · Service Management Assistant

---

### Flow 2 — AR + ESM
**Persona:** Avery Kim, Collections Specialist

Full AR collections cycle for a high-risk account (CA Networks AG, DSO 47 days). Covers account intelligence, dunning, collections email outreach, email-to-dispute creation with AI reason code inference, ESM case routing, credit memo processing, and payment clearing. DSO drops 8 days.

**Agents:** Receivables Account Analysis Agent · Collections Account Preparation Agent · Collections Email Outreach Agent · Dunning Insights Agent · Dispute Creation Agent · Dispute Resolution Agent · Receivables & Payables Clearing Agent + ESM Case Preparation & Processing Agents

---

### Flow 3 — RR + ESM (BRIM)
**Persona:** Maria Santos, Collections Specialist — BRIM

A €97,900 subscription invoice blocked for 35 days due to a PO digit transposition in SAP FICA. Joule traces the root cause through the BRIM billing run, corrects the contract account document, updates the bill-to party, reprints the Convergent Invoice, and auto-resolves a €7.14 rounding dispute — all in 12 minutes.

**Agents:** Collection Insights Agent · Contract Account Risk Insights Agent · Subscription Lifecycle Agent · Contract Accounting Payment Resolution Agent · Convergent Invoicing Execution Agent · Contract Accounting Dispute Resolution Agent · Payment Matching Agent + ESM Case Preparation Agent

---

### Flow 4 — Dispute Management
**Persona:** Jordan Lee, Dispute Case Processor

Three dispute types in sequence: invoice amount error (pricing condition misconfiguration), wrong goods delivered (logistics), and payment reference mismatch (expired discount). Each resolved with type-aware logic, HITL confirmation before every write operation, and root cause fixes flagged.

**Agents:** Dispute Creation Agent · Dispute Resolution Agent · Collections Account Preparation Agent · Receivables & Payables Clearing Agent · Case Processing Agent · Case Management Assistant

---

## Presenter Commands

| Command | Action |
|---|---|
| `Flow 1` · `Flow 2` · `Flow 3` · `Flow 4` | Jump to that flow |
| `Act 1` – `Act 8` | Jump to act within current flow |
| `cheat sheet` | Show all prompts + expected responses (presenter only) |
| `reset` | Restart from opening menu |
| `end session` | Exit character, show combined KPI summary |

## Repository Structure

```
skills/
└── sap-autonomous-finance-esm-ar-rr-demo/
    ├── SKILL.md
    └── references/
        ├── demo-data.md          # all locked reference numbers + master data
        ├── demo-script.md        # full 29-act script with AI Transparency blocks
        └── demo-cheat-sheet.md   # presenter prompt guide
```

## SAP Products Illustrated

- SAP S/4HANA FI-AR (Accounts Receivable)
- SAP BRIM — FICA, Convergent Invoicing, Subscription Order Management
- SAP ESM (Enterprise Service Management)
- SAP FSCM Dispute Management
- SAP Business AI Platform / SAP Joule

## Key Metrics Demonstrated

| Flow | Key outcome |
|---|---|
| ESM Standalone | 22 min handle time · batch error affecting 4 employees discovered |
| AR + ESM | DSO 47 → 39 days · €28,000 payment recovered |
| RR + ESM | 35-day revenue block resolved in 12 min · €97,900 unblocked |
| Dispute Mgmt | 3 dispute types · €11,100 resolved · 82% time saving vs manual |

---

## Demo Script — Prompt Sequence + Expected Joule Responses

Use this as a presenter guide. Each row shows the exact prompt to say and what Joule will return.

### Flow 1 — ESM Standalone

**Launch:** `"Start the ESM demo"` · **Persona:** Rachel Chen, HR & Finance Service Desk Lead

| Act | Say this | Joule shows | WOW moment |
|---|---|---|---|
| 1 | *"Joule, show me the latest service request that came in from Geoff Hill."* | Intake card SR-2026-18841: two issues extracted (parental leave + €240 PEN-ADJ deduction), priority escalated to HIGH | Single employee message split into HR + Finance workstreams automatically |
| 2 | *"Yes, go ahead and prepare the cases."* | Cases CS-ESM-2026-11841 (HR) + CS-FIN-2026-29845 (Finance) created, routed, SLA set — plus proactive flag: 3 other employees hit by same payroll batch | Nobody asked about other employees — Joule found the batch pattern |
| 3 | *"What does our knowledge base say about parental leave in Germany, and have we handled similar cases before?"* | 3 KB articles (98%/91%/87% match), 5 historical cases (12–31 min resolution), entitlement confirmed: 14 weeks full pay | 98% match = Rachel has the answer without any research |
| 4 | *"Investigate the payslip deduction — why did PEN-ADJ appear and is it correct?"* | Root cause: pension batch PRB-2026-08 wrongly hit CC-MFG-040. Verdict: INCORRECT. PAJ-2026-3841 prepared (€240 refund). 3 more employees flagged (EMP-10044/52/63, total €960) | One complaint → Joule found a €960 batch error affecting 4 people |
| 5 | *"Yes, flag the other employees and proceed with Geoff's adjustment."* | PAJ raised, batch escalation ESC-FIN-2026-0091 sent, parental leave confirmed in HR record — all simultaneously | Three cross-system actions in one response |
| 6 | *"Draft the response email to Geoff covering both issues."* | Complete email EM-2026-ESM-11841 covering both parental leave entitlement AND payslip refund in one message | Two departments, one clean email — Rachel just approves |
| 7 | *"Send it and close both cases."* | Both cases closed, SLA met, KPI card: 22 min handle time, 4.8/5 CSAT, batch correction escalated | *"22 minutes — employee didn't wait for inter-department handoffs"* |

---

### Flow 2 — AR + ESM

**Launch:** `"Start the AR demo"` · **Persona:** Avery Kim, Collections Specialist

| Act | Say this | Joule shows | WOW moment |
|---|---|---|---|
| 1 | *"Joule, give me the full receivables picture for CA Networks AG."* | KPI card: DSO 47d (+17 vs benchmark), Payment Rating E, €62K open, broken PTP. Aging table + 4 overdue invoices | Full CFO-level + invoice-level picture in one response |
| 2 | *"Show me the full 360 — disputes, promises to pay, dunning history."* | 4 open disputes (€8,938), broken PTP-091, dunning at Level 3 Final Notice, recommendation: outreach before legal | Broken PTP + 3 ignored dunning = agent builds the escalation case |
| 3 | *"Draft the collections outreach email to Thomas Weber."* | Full email CE-2026-CA001: 3 invoices cited (€27,400), broken PTP referenced, 7-day deadline, legal escalation warning | CFO-appropriate tone with invoice specifics, generated from account data |
| 4 | *"Send it. And what does Joule recommend on dunning — should we escalate?"* | Balanced assessment: factors for/against escalation. Recommendation: 7-day window, soft order block, DUN-2026-7738 issued, Level 4 + legal if no response by Sep 26 | Agent doesn't just escalate — it weighs both sides |
| 5 | *"Thomas just replied. He says they dispute invoice INV-2026-10077 — they received only 85 units, not 100. He wants a dispute case raised."* | Dispute DIS-2026-37737 created; reason code QUANT auto-inferred; DLN-2026-8847 cross-referenced and validates claim; overcharge = 15 × €128 = €1,920 | *"85 units not 100"* → inferred reason code, found delivery note, validated claim, calculated overcharge |
| 6 | *"Yes, route it to ESM and set up the case."* | CS-AR-2026-44471 created with full AR context pre-loaded (customer, invoice, dispute, validated claim) — Finance team inherits everything | No re-investigation — AR data follows the case into ESM |
| 7 | *"Process the resolution — issue the credit memo."* | CM-2026-3318 (€1,920) issued, INV-10077 adjusted €12,800→€10,880, Thomas notified, both cases closed, S/4HANA updated | Full AR-to-ESM dispute cycle completed |
| 8 | *"Yes, create the PTP and then show me what happens when the payment clears."* | €28,000 cleared against 3 invoices. DSO: 47→39 days (−8 days). PTP-097 covers remaining €34,600 | *"8-day DSO improvement from one collections cycle"* |

---

### Flow 3 — RR + ESM (BRIM)

**Launch:** `"Start the RR demo"` · **Persona:** Maria Santos, Collections Specialist — BRIM

| Act | Say this | Joule shows | WOW moment |
|---|---|---|---|
| 1 | *"Joule, show me the risk profile for CloudTech Services."* | BBI Risk Score 84/100, DSO 61d, €97,900 blocked. DSO trend table Apr→Aug worsening. Agent insight: *"process blocker, not credit risk"* | Agent makes a judgment call: differentiates billing error from credit problem |
| 2 | *"Open Mike's email and create the case."* | CS-RR-2026-23251 created. Email parsed: PO-2026-88712 vs PO-2026-88731 — digit transposition identified. Customer intent: *"ready to pay"* | Structured extraction from plain email — identifies the exact error type |
| 3 | *"Yes — investigate the subscription and find out how this error happened."* | Root cause traced: manual FICA entry 2026-07-28, digits 3↔1 transposed, inherited by billing run BRN-2026-08, 35 days blocked | *"Joule traced a 35-day revenue block to a single keypress from 7 weeks ago"* |
| 4 | *"Process the correction — fix the PO reference and update the bill-to party."* | PO corrected 88712→88731 (CAD-2026-50019), bill-to updated to Sarah Mueller (SOM-2026-7749), old invoice voided — all logged | Multiple BRIM system updates in one confirmation |
| 5 | *"Reissue the corrected invoice."* | INV-2026-90050063 issued: correct PO, Sarah Mueller, due Sep 26. **Total time: 12 minutes** (manual: 3–5 days) | *Pause here.* **"12 minutes to resolve a 35-day payment block."** |
| 6 | *"Create the PTP and confirm payment expectation with Mike."* | PTP-136 (€97,900), BBI score 84→71, DSO 61→57 projected. Mike replied in 2 min: *"Sarah will pay by Friday"* | Customer was waiting for this fix |
| 7 | *"Yes — what's the BRIM convergent invoice dispute about?"* | DISP-2026-171: €7.14 rounding delta. Below write-off threshold. Auto-resolved — no human action needed | *"Invisible value"* — dispute that would sit in a queue for days, resolved in seconds |
| 8 | *"Great — close the ESM case and show me the full outcome."* | KPI card: €97,900 unblocked, 12 min, DSO −4 days projected, BBI 84→71, PTP-136 active | *"35-day revenue block from a typo, resolved in 12 minutes"* |

---

### Flow 4 — Dispute Management

**Launch:** `"Start the dispute demo"` · **Persona:** Jordan Lee, Dispute Case Processor

| Act | Say this | Joule shows | WOW moment |
|---|---|---|---|
| 1 | *"Joule, give me my dispute queue for today."* | Queue KPI: 14 open, 3 high priority, €47,800 exposure, 87% on-time. Top 3 table with type + amount | Full queue intelligence without opening FSCM |
| 2 | *"Let's start with DIS-2026-37737 — the invoice amount error."* | Root cause: PR00 standard price (€40) overrode contract CPC-PDG-2026 (€35). Claim VALID. Credit memo CM-2026-3400 (€500) recommended | Agent found the specific pricing condition misconfiguration |
| 3 | *"Yes — process the credit memo."* then confirm HITL | HITL card first (⚠️ confirm before write). After confirm: CM-2026-3400 issued, invoice adjusted, pricing fix flagged to SD team | HITL is intentional — *"agents prepare, humans authorise"* |
| 4 | *"Open DIS-2026-37821 — the wrong goods delivery for Meridian Engineering."* | DN-2026-4491 confirms wrong product shipped (V-belt vs timing belt). Returns RT-2026-8841, credit CM-2026-3401 (€9,600), replacement scheduled, warehouse SKU issue flagged | Delivery note cross-reference proves the claim; 3-invoice batch as one action |
| 5 | *"Last one — DIS-2026-37901, the payment mismatch for Vortek Industries."* | €1,400 shortfall — expired discount wrongly deducted. Clearing proposal CLP-2026-14441: clear €21,400, write off €140 (within WT-003), request €1,260 via AR letter | Three-way resolution (clear + write-off + request) from one payment gap |
| 6 | *"Save the dispute findings and show me the session summary."* | KPI card: 3 disputes, €11,100 resolved, 8 min avg vs 45 min manual (82% gain), 3 HITL confirmations, 2 root cause fixes flagged | *"Three dispute types, 30 minutes, Jordan never opened a transaction code"* |

---

### Closing

Type `end session` to exit character. Joule renders the combined KPI summary across all 4 flows and lists all 20+ agents grouped by domain.

| Metric | Value |
|---|---|
| Demo flows | 4 |
| Total acts | 29 |
| AI agents demonstrated | 20+ |
| Domains | ESM · AR · BRIM/RR · FSCM Dispute Management |
| Total receivables resolved | €127,900+ |
| DSO improvement | Up to 8 days |
| FTE productivity gain | 35–82% |
| HITL confirmations | All write operations |

---

## License

Apache 2.0 — see [LICENSE](LICENSE)

## Author

**Sourajit Ghosh** — SAP Solution Advisory, CX AI Enterprise Architecture  
Based on the SAP Autonomous Finance AI Roadmap

> Note: All scenarios are illustrative simulations using mock data. No live SAP system is connected. These demos are intended to show how SAP Joule and Autonomous Finance AI capabilities would work in a real deployment.
