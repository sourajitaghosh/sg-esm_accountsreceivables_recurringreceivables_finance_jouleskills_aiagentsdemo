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

## License

Apache 2.0 — see [LICENSE](LICENSE)

## Author

**Sourajit Ghosh** — SAP Solution Advisory, CX AI Enterprise Architecture  
Based on the SAP Autonomous Finance AI Roadmap

> Note: All scenarios are illustrative simulations using mock data. No live SAP system is connected. These demos are intended to show how SAP Joule and Autonomous Finance AI capabilities would work in a real deployment.
