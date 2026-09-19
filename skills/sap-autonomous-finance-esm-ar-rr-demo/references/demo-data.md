# SAP Autonomous Finance Demo — All Mock Data

All locked reference numbers and master data for all 4 demo flows.
**Never invent numbers not listed here. Reference this file for every response.**

---

## Global Personas

| Persona | Role | Flow |
|---|---|---|
| Rachel Chen | HR & Finance Service Desk Lead | Flow 1 — ESM Standalone |
| Avery Kim | Collections Specialist | Flow 2 — AR + ESM |
| Maria Santos | Collections Specialist, BRIM | Flow 3 — RR + ESM |
| Jordan Lee | Dispute Case Processor | Flow 4 — Dispute Management |

---

## FLOW 1 — ESM Standalone

### Service Agent
- **Name:** Rachel Chen — HR & Finance Service Desk Lead, Acme Global
- **Company:** Acme Global (internal IT + HR service desk)

### Employee Raising Request
- **Name:** Geoff Hill
- **Title:** Production Director
- **Employee ID:** EMP-10041
- **Department:** Manufacturing Operations
- **Location:** Hamburg, DE
- **Manager:** Sandra Brandt

### Service Request
| Field | Value |
|---|---|
| Service Request ID | SR-2026-18841 |
| Channel | Employee Self-Service Portal |
| Date submitted | 2026-09-10 |
| Request type | HR Policy Inquiry |
| Subject | Parental leave entitlement + payslip discrepancy |
| Description | "I'm planning to take parental leave from November. I need to know my entitlement and whether the additional childcare allowance will appear on my payslip. My August payslip shows a €240 deduction I don't recognise." |
| Priority (initial) | Medium |
| Priority (after AI triage) | High (financial impact identified) |
| SLA | 48 hours |

### Case Records
| Reference | Value |
|---|---|
| HR Case ID | CS-ESM-2026-11841 |
| Finance Case ID | CS-FIN-2026-29845 |
| Case type (HR) | HR Policy Inquiry — Parental Leave |
| Case type (Finance) | Payroll Adjustment — Incorrect Deduction |
| Assigned team (HR) | HR Services — Benefits & Leave |
| Assigned team (Finance) | Finance Services — Payroll |
| Status at close | Resolved |
| Handle time | 22 minutes |
| CSAT | 4.8 / 5 |

### Knowledge Articles
| Article ID | Title | Relevance |
|---|---|---|
| KB-HR-2026-003 | Parental Leave Entitlement Guide — Germany | 98% match |
| KB-HR-2026-019 | Childcare Allowance Policy — EEA Employees | 91% match |
| KB-FIN-2026-041 | Payroll Adjustment Request Workflow | 87% match |

### Similar Cases (Last 12 Months)
| Case ID | Issue | Resolution | Time |
|---|---|---|---|
| CS-ESM-2026-09817 | Parental leave + bonus timing | Policy clarification | 18 min |
| CS-ESM-2026-07433 | Incorrect deduction on payslip | €180 adjustment | 31 min |
| CS-ESM-2026-06201 | Leave entitlement query | Email response + KB link | 12 min |
| CS-ESM-2026-11124 | Childcare allowance not showing | Payroll correction issued | 24 min |
| CS-ESM-2026-10488 | Parental leave start date error | HR records updated | 19 min |

### Resolution Details
| Field | Value |
|---|---|
| HR resolution | Parental leave entitlement confirmed: 14 weeks full pay, 4 weeks 75%. Childcare allowance (€180/month) confirmed eligible from November. |
| Finance resolution | €240 deduction identified as incorrect pension recalculation (code PEN-ADJ). Payroll adjustment PAJ-2026-3841 raised for €240 refund on October payslip. |
| Communication sent | Draft email to Geoff Hill confirming both resolutions |
| Case closed by | Rachel Chen + Case Management Assistant |

### Locked Reference Numbers — Flow 1
| Reference | Number |
|---|---|
| Service request | SR-2026-18841 |
| HR case | CS-ESM-2026-11841 |
| Finance case | CS-FIN-2026-29845 |
| Payroll adjustment | PAJ-2026-3841 |
| Resolution email | EM-2026-ESM-11841 |

---

## FLOW 2 — AR + ESM

### AR Persona
- **Name:** Avery Kim — Collections Specialist
- **Company:** Acme Global (seller)
- **System:** SAP S/4HANA FI-AR + ESM

### Customer Account
| Field | Value |
|---|---|
| Company name | CA Networks AG |
| Business Partner | BPCA00001 |
| Company Code | 1010 |
| Collection Segment | S_LOC_1010 (Local — Critical) |
| Payment Behavior Rating | E (Critical) |
| Account type | B2B Enterprise |
| Primary contact | Thomas Weber, CFO |
| Account status | Active — Collections watch list |
| Credit limit | €150,000 |
| Credit utilized | €62,000 (41%) |
| Last payment | €15,200 — received 45 days ago |
| Relationship manager | Anna Becker |

### DSO & Aging
| Metric | Value |
|---|---|
| Current DSO | 47 days |
| Industry benchmark | 30 days |
| DSO trend | Worsening (was 38 days in Q1 2026) |
| Total open receivables | €62,000 |

| Aging Bucket | Amount |
|---|---|
| 0–30 days | €8,400 |
| 31–60 days | €12,800 |
| 61–90 days | €6,200 |
| 90+ days | €34,600 |

### Open Invoices
| Invoice | Issue Date | Due Date | Amount | Days Overdue | Flag |
|---|---|---|---|---|---|
| INV-2026-10077 | 2026-06-01 | 2026-07-01 | €12,800 | 79 days | Dispute flagged |
| INV-2026-10091 | 2026-06-15 | 2026-07-15 | €8,400 | 65 days | Promise broken |
| INV-2026-10103 | 2026-07-01 | 2026-08-01 | €6,200 | 48 days | Clean |
| INV-2026-10118 | 2026-07-15 | 2026-08-15 | €34,600 | 34 days | Clean |

### Promises to Pay
| PTP ID | Invoice | Amount | Committed Date | Status |
|---|---|---|---|---|
| PTP-091 | INV-2026-10091 | €12,800 | 2026-08-01 | BROKEN — 48 days ago |
| PTP-094 | INV-2026-10103 | €6,200 | 2026-09-30 | Active |

### Open Disputes
| Dispute ID | Invoice | Reason Code | Amount | Status |
|---|---|---|---|---|
| DIS-2026-37737 | INV-2026-10077 | Wrong quantity billed | €5,000 | Open |
| DIS-2026-37739 | INV-2026-10091 | Pricing discrepancy | €2,400 | In Review |
| DIS-2026-37727 | INV-2026-10103 | Late delivery penalty | €1,200 | Escalated |
| DIS-2026-37736 | INV-2026-10118 | Wrong goods delivered | €338 | New |

### Collections Email — CA Networks AG (Avery's outreach)
- **To:** Thomas Weber (t.weber@canetworks.de)
- **Subject:** Outstanding Receivables — Action Required | CA Networks AG
- **Invoices referenced:** INV-2026-10077, INV-2026-10091, INV-2026-10103
- **Total referenced:** €27,400
- **Tone:** Professional, firm
- **Action requested:** Payment or written dispute rationale within 7 days
- **Escalation note:** Account will be forwarded to legal if no response
- **Email log ID:** CE-2026-CA001

### Dunning Record
| Field | Value |
|---|---|
| Dunning notice ID | DUN-2026-7738 |
| Dunning level | Level 3 (Final notice) |
| Dunning block recommendation | Block new orders > €5,000 until €28,000 cleared |
| Prior dunning dates | 2026-07-15, 2026-08-01, 2026-08-20 |

### Dispute → ESM Escalation (email from customer)
- **Received from:** Thomas Weber, CA Networks AG
- **Email subject:** "RE: Outstanding Receivables — Formal Dispute Notice"
- **Email content (parsed):** "We formally dispute invoice INV-2026-10077. Our receiving records show 85 units delivered, not 100 as billed. We will not pay the €12,800 until this is corrected. Please raise a dispute case."
- **AI inference:** Reason code = Wrong Quantity, invoiced quantity 100, received quantity 85, unit price €128 → overcharge = €1,920
- **Delivery Note cross-reference:** DLN-2026-8847 (confirms 85 units shipped)
- **ESM Case created:** CS-AR-2026-44471 (AR-integrated billing dispute)
- **Case type:** Billing Dispute — AR Integration
- **Priority:** High (>€5,000 threshold)

### Dispute Resolution — CS-AR-2026-44471
| Field | Value |
|---|---|
| Root cause | Quantity discrepancy: 100 billed, 85 delivered |
| Verification source | Delivery note DLN-2026-8847 |
| Unit price | €128/unit |
| Overcharge | 15 units × €128 = €1,920 |
| Adjustment type | Credit memo |
| Credit memo | CM-2026-3318 (€1,920) |
| Applied to | INV-2026-10077 (adjusted from €12,800 to €10,880) |
| Case status | Resolved |

### Post-Resolution Payment
| Field | Value |
|---|---|
| Payment received | €28,000 |
| Payment date | 2026-09-15 |
| Invoices cleared | INV-2026-10077 (adjusted), INV-2026-10091, INV-2026-10103 |
| New DSO | 39 days (−8 days) |
| New PTP | PTP-097 — €34,600 — committed 2026-10-01 |

### Locked Reference Numbers — Flow 2
| Reference | Number |
|---|---|
| Collections email log | CE-2026-CA001 |
| Dunning notice | DUN-2026-7738 |
| ESM case (AR dispute) | CS-AR-2026-44471 |
| Credit memo | CM-2026-3318 |
| Delivery note (verified) | DLN-2026-8847 |
| Promise to Pay (new) | PTP-097 |

---

## FLOW 3 — RR + ESM

### RR Persona
- **Name:** Maria Santos — Collections Specialist, BRIM
- **Company:** TeleServ B.V. (seller — subscription business)
- **System:** SAP BRIM (FICA + Convergent Invoicing + SOM) + ESM

### Customer Account
| Field | Value |
|---|---|
| Company name | CloudTech Services GmbH |
| Business Partner | BPCT00079 |
| Contract Account | 4897375 |
| Company Code | 2010 |
| Collection Segment | S_BRIM_2010 (BRIM — High Priority) |
| BBI Risk Score | 84 / 100 (High) |
| Credit limit | €200,000 |
| Credit utilized | €114,000 (57%) |
| Current DSO | 61 days |
| Last payment | €48,500 — received 62 days ago |
| Primary contact | Mike Ross, CFO |
| Account manager | Laura Kessler |

### Subscription Contract
| Field | Value |
|---|---|
| Contract ID | SUB-2026-19543 |
| Description | SAP Cloud Platform License — Enterprise Tier |
| Billing cycle | Monthly |
| Monthly recurring revenue | €97,900 |
| Contract start | 2026-01-01 |
| Contract end | 2027-12-31 |
| Status | Active |
| Bill-to party | CloudTech Services GmbH (address update pending) |
| Subscription Object ID | SOM-2026-7749 |

### Blocked Invoice
| Field | Value |
|---|---|
| Invoice ID | INV-2026-90050062 |
| Amount | €97,900 |
| Due date | 2026-08-15 |
| Status | BLOCKED — PO reference mismatch |
| PO on invoice (incorrect) | PO-2026-88712 |
| Customer's actual PO | PO-2026-88731 |
| Discrepancy | Digit transposition: 88712 vs 88731 |
| Days overdue | 35 days |

### ESM Case — Intake Channel
| Field | Value |
|---|---|
| Email from | Mike Ross (mike.ross@cloudtech.de) |
| Email subject | "Invoice INV-2026-90050062 — PO Reference Error" |
| Email content (parsed) | "Our AP system is blocking payment on your invoice because the PO number is wrong. You've used PO-2026-88712 but our PO is PO-2026-88731. Please correct and reissue. We're ready to pay once this is resolved." |
| ESM Case created | CS-RR-2026-23251 |
| Case type | Billing Inquiry — BRIM Integration |
| Priority | High (>€50,000 revenue blocked) |
| Assigned to | Maria Santos |
| SLA | 24 hours |

### Contract Correction Workflow
| Step | Reference | Detail |
|---|---|---|
| PO update in FICA | CAD-2026-50019 | Contract Account Document recording PO change |
| Bill-to party update | SOM-2026-7749 | New billing contact: Sarah Mueller (Finance Director) |
| Invoice voided | INV-2026-90050062 | Original blocked invoice cancelled |
| Corrected invoice | INV-2026-90050063 | Reprinted with correct PO-2026-88731 |
| Correction time | 12 minutes | vs. 3–5 business days manual |

### Convergent Invoice Dispute
| Field | Value |
|---|---|
| Dispute ID | DISP-2026-171 |
| Type | Convergent Invoice Rounding Difference |
| Disputed amount | €7.14 |
| Line item | CI-LINE-2026-9901 |
| Root cause | Rounding delta between FICA and CI line aggregation |
| Resolution | System-generated credit note applied |
| Status | Auto-resolved |

### Payment Resolution
| Field | Value |
|---|---|
| Promise to Pay | PTP-136 |
| Amount | €97,900 |
| Committed date | 2026-09-22 (7-day window from correction) |
| Payment received | €97,900 |
| DSO impact | −3.5 days |
| Revenue recovered | €97,900 |
| Case closed | CS-RR-2026-23251 — Resolved |
| Resolution email | EM-2026-RR-23251 |

### DSO Trend — CloudTech Services
| Month | DSO |
|---|---|
| Apr 2026 | 44 days |
| May 2026 | 49 days |
| Jun 2026 | 53 days |
| Jul 2026 | 58 days |
| Aug 2026 | 61 days (current — blocked invoice) |
| Sep 2026 (projected) | 57 days (after resolution) |

### Locked Reference Numbers — Flow 3
| Reference | Number |
|---|---|
| ESM case (RR intake) | CS-RR-2026-23251 |
| Subscription contract | SUB-2026-19543 |
| Blocked invoice | INV-2026-90050062 |
| Corrected invoice | INV-2026-90050063 |
| Contract account document | CAD-2026-50019 |
| Convergent invoice dispute | DISP-2026-171 |
| Promise to Pay | PTP-136 |
| Resolution email | EM-2026-RR-23251 |

---

## FLOW 4 — Dispute Management

### Dispute Persona
- **Name:** Jordan Lee — Dispute Case Processor
- **Company:** Precision Dynamics GmbH (Company Code 1010)
- **System:** SAP S/4HANA FSCM Dispute Management + ESM

### Jordan's Queue Dashboard
| Metric | Value |
|---|---|
| Total open disputes | 14 |
| High priority | 3 |
| Average resolution time | 4.2 days |
| Total exposure | €47,800 |
| Processed this week | 8 |
| On-time resolution rate | 87% |
| Oldest unresolved | 21 days |

### Dispute 1 — Invoice Amount Error
| Field | Value |
|---|---|
| Dispute ID | DIS-2026-37737 |
| Customer | Precision Dynamics GmbH |
| Invoice | INV-2026-100891 |
| Billed amount | €4,000 |
| Customer-claimed correct amount | €3,500 |
| Discrepancy | €500 |
| Reason code | AMOUNT — Price calculation error |
| Root cause | Pricing condition PR00 used list price €40/unit instead of contract price CPC-PDG-2026 (€35/unit), 100 units |
| Contract reference | CPC-PDG-2026 (customer-specific contract, valid since 2025-01-01) |
| Supporting document | Price agreement email chain PDG-2026-EMC-003 |
| Resolution | Credit memo €500 applied against INV-2026-100891 |
| Credit memo | CM-2026-3400 |
| Status at close | Resolved — Billing Adjustment |
| Type | Billing Dispute |

### Dispute 2 — Wrong Goods Delivered
| Field | Value |
|---|---|
| Dispute ID | DIS-2026-37821 |
| Customer | Meridian Engineering Ltd |
| Invoices | INV-2026-101045 (€3,200), INV-2026-101046 (€3,200), INV-2026-101047 (€3,200) |
| Total disputed | €9,600 |
| Delivery note | DN-2026-4491 |
| Ordered product | ADX-14M-1750-40 (SyncPro 14M Timing Belt) |
| Shipped product | ADX-BX65-STD (ClassicV BX65 V-Belt) — wrong product code |
| Root cause | Warehouse picking error — similar SKU shelf adjacency |
| Resolution | Returns order RT-2026-8841, credit memo CM-2026-3401 for €9,600, replacement shipment scheduled |
| Credit memo | CM-2026-3401 |
| Returns order | RT-2026-8841 |
| Status | Resolved — Returns + Credit |
| Type | Logistics Dispute |

### Dispute 3 — Payment Mismatch
| Field | Value |
|---|---|
| Dispute ID | DIS-2026-37901 |
| Customer | Vortek Industries AG |
| Invoices in scope | INV-2026-102001 (€8,000), INV-2026-102002 (€6,400), INV-2026-102003 (€5,200), INV-2026-102004 (€3,200) — Total €22,800 |
| Payment received | €21,400 |
| Payment reference | PAY-2026-VT-0091 |
| Unmatched amount | €1,400 |
| Root cause | Customer deducted 2% early-pay discount on INV-2026-102001 (€8,000 × 2% = €160 was the intended deduction, but customer calculated €1,400 incorrectly; discount window expired 2026-08-01) |
| Clearing proposal | Clear €21,400 against 4 invoices, write off €140 within threshold WT-003, request remaining €1,260 from customer via AR letter |
| Write-off threshold | WT-003 (max €200 per transaction) |
| Clearing proposal ID | CLP-2026-14441 |
| Status | Resolved — Partial clearing + write-off + customer request |
| Type | Payment Dispute |

### Supporting Contacts
| Customer | Contact | Email |
|---|---|---|
| Precision Dynamics GmbH | Karl Schmidt, AP Manager | k.schmidt@precisiondynamics.de |
| Meridian Engineering Ltd | Claire Foster, Procurement | c.foster@meridianeng.co.uk |
| Vortek Industries AG | Hans Vetter, Finance | h.vetter@vortek.de |

### Locked Reference Numbers — Flow 4
| Reference | Number |
|---|---|
| Dispute 1 | DIS-2026-37737 |
| Dispute 2 | DIS-2026-37821 |
| Dispute 3 | DIS-2026-37901 |
| Credit memo 1 (amount error) | CM-2026-3400 |
| Credit memo 2 (wrong goods) | CM-2026-3401 |
| Returns order | RT-2026-8841 |
| Payment reference | PAY-2026-VT-0091 |
| Clearing proposal | CLP-2026-14441 |
| Contract reference | CPC-PDG-2026 |
| Delivery note | DN-2026-4491 |

---

## Combined Demo KPI Summary (end session)

| Metric | Value |
|---|---|
| Demo flows | 4 |
| Total acts | 29 |
| AI agents demonstrated | 20+ |
| Personas | 4 |
| Customer accounts | 4 |
| Domains covered | AR · RR · ESM · FSCM Dispute Mgmt |
| Systems simulated | S/4HANA FI-AR · BRIM/FICA · SAP ESM · FSCM |
| Total receivables resolved | €127,900+ |
| DSO improvement demonstrated | Up to 8 days |
| FTE productivity gain | 35–50% |
| Email drafting time saved | 80% |
