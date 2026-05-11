# 3.08 — Financial Management

| Field | Value |
|---|---|
| **Decision density** | **Medium** — both BRDs mature; sequencing of foundational decisions (COA design, revenue recognition rules, labor markup) drives the work; many specific items require working-session confirmation |
| **Source coverage** | KBM Financial Management BRD v2.0 (38 requirements across 15 functional areas) + Pivot Financial Management BRD v1.0 (58 requirements across 16 sub-sections) |
| **KBM BRD** | `Financial Management/KBMH/3 Output/BRD_FinancialManagement_v2.0.md` |
| **Pivot BRD** | `Financial Management/Pivot/4 BRD/Pivot Interiors BRD Financial Management Process Area_v2.0.docx` (markdown copy at `_Unification/working/pivot-brds-md/Financial_Management.md`) |

---

## 3.08.1 How each company approaches Financial Management today

**KBM Hogue** approaches Financial Management as a modernization opportunity, migrating from NetSuite Core into Orion. Its BRD reflects a 10-day Excel-driven period close, a chart of accounts that has grown to 40-plus pages across the merged KB and Hogue history, manual bank-portal payment uploads (sometimes processing $3M payment runs), a Bloomberg third-party fixed-asset tool, an Expensify expense platform under evaluation against RAMP, and a 15% labor markup with dual GP metrics (Project GP vs. Commissionable GP) tied to commission structure. KBM's BRD identifies three critical decision gates — revenue recognition rules (compliance-critical; ASC 606), 15% labor markup continuation (impacts commissions and custom development scope), and chart-of-accounts consolidation (foundational to all transactions) — and an eight-session follow-up discovery framework to finalize requirements before configuration. KBM's stakeholders are named: Lorraine (CFO/Controller), Kipp (hybrid Finance/IT), Celine and Kevin (GL specialists), Guada and Michael (AP team), Shannon (Product Coordinator Manager, vendor management), with Matt and Mark holding leadership decision authority on labor markup.

**Pivot Interiors** approaches Financial Management as a platform migration from Microsoft Dynamics 365 into NetSuite Orion. Its BRD reflects a 7-day period close, 42 manual ACH/wire journal entries to be eliminated through automation, banking integration with Comerica, an articulated dual GP structure (actual GP with time-tracked labor costs vs. commissionable GP with quoted labor rates) consistent with its CRM-area framework, project accounting with furniture-dealer-specific KPIs, dedicated treatment of collections management and AR management as separate sub-sections, document numbering and dynamic terms-and-conditions handling, and accrued revenue journal entries with approval workflow. Pivot's BRD covers 16 financial sub-areas (revenue/cost recognition, project accounting, banking, collections, AP, tax, fixed assets, document numbering and T&C, expense management, payroll, COA, period close, budgeting, AR, vendor management, implementation strategy) and articulates 58 validated requirements with 60% standard NetSuite functionality alignment.

Both companies share the same end-state goals: integrated GL with project-level visibility, automated bank reconciliation and electronic payments, real-time financial dashboards replacing Excel-based reporting, automated revenue and cost recognition, period close automation, and integrated tax management. Where they differ is largely in starting-state context (NetSuite Core for KBM, D365 for Pivot), in operational cadence (Pivot's 7-day close vs. KBM's 10-day with a 5-7 day target), in specific historical configuration choices (KBM's 15% labor markup and 13-period calendar), and in the breadth of sub-area coverage (Pivot's separate Collections and AR sections; KBM's eight-session follow-up framework with named decision gates).

## 3.08.2 Where the two companies align

The following capabilities are common ground across both BRDs and require no merged-company decision:

**Explicit in both BRDs:**

- Bank-feed integration with automatic transaction matching
- Advanced Electronic Bill Payments for ACH directly from NetSuite
- Cash360 dashboard for cash-flow forecasting and visibility
- Period close checklist replacing manual / Excel-based close workbook
- Project-level revenue and cost tracking with linked transactions
- Real-time financial dashboards replacing manual reporting
- Automated reversal journal entries
- Tax-exemption certificate management with expiration tracking

**KBM-explicit; standard capability carried forward for the merged company:**

- Single subsidiary structure (KBM REQ-001)
- USD-only currency (KBM REQ-003)
- 13-period calendar configuration (KBM's preference; carried forward as the merged-company calendar)
- Pro forma invoice for customer deposit management (KBM REQ-032)
- Credit-card reconciliation as a bank account (KBM REQ-012)
- Stripe integration for credit-card acceptance (KBM REQ-029)
- Wire-transfer processing capability (KBM REQ-030)
- Finance-charge capability (off by default, available as deterrent) (KBM REQ-031)
- Vendor and customer dual setup for intermarket transactions (KBM REQ-033)

**Pivot-explicit; standard capability carried forward for the merged company:**

- Accrued revenue journal entries for delivered-but-not-invoiced items (Pivot REQ-3.01.02, REQ-3.01.03)
- Dedicated collections management framework (Pivot REQ-3.04.01)
- Dedicated AR management framework (Pivot REQ-3.14.01, REQ-3.14.02)
- Budgeting and planning module (Pivot §3.13)
- Dynamic terms-and-conditions and document numbering (Pivot REQ-3.08.01 through REQ-3.08.03)
- AP automation framework (Pivot REQ-3.05.01 through REQ-3.05.05)
- Multi-location operating model (existing California Design Centers + KBM's California territories)

These are noted in the merged BRD, and configuration proceeds against standard NetSuite Orion capability.

## 3.08.3 Where the two companies differ

Ten in-area divergences. Each is presented as: how each company approached it (with attribution to context), the recommendation for the merged company, and the decision the leadership team owns.

---

### D-1. Chart of Accounts consolidation and design

**Source:** KBM REQ-016, REQ-017 (`BRD_FinancialManagement_v2.0.md` §5; KBM SESSION 2 critical-path); Pivot §3.11 Chart of Accounts (`Financial_Management.md` §3.11)

**KBM's approach.** KBM's BRD treats COA consolidation as the single biggest structural change in the implementation. The current Core COA spans 40+ pages with significant redundancy across the merged KB and Hogue legacy structures; users have memorized many account numbers; the target is a rationalized few-hundred-account structure using NetSuite's Classes, Departments, and Projects to reduce account proliferation. KBM names this as critical-path requiring SESSION 2 (2-3 hours, Lorraine, Celine, Kevin) before data-migration planning can proceed. Decision-makers: Lorraine (CFO/Controller), Celine and Kevin (GL team).

**Pivot's approach.** Pivot's BRD treats COA design as part of the platform migration from D365 to NetSuite — a fresh-start opportunity rather than a consolidation problem. Pivot's BRD does not flag COA as a critical decision gate at the same level KBM does; the migration from D365 doesn't carry the same legacy-redundancy burden.

**Recommendation for the merged company.** Design the merged-company COA from a clean foundation rather than consolidating either legacy structure. The reasoning is contextual: the merged company will operate from KBM's prepaid NetSuite account, but the data starting fresh from migration means neither KBM's 40+ page Core COA nor Pivot's D365 COA carries forward intact. The COA design session (KBM's SESSION 2) is expanded to include Pivot's GL leadership alongside KBM's, jointly establishing a merged-company COA structure that supports both companies' reporting needs. The design uses NetSuite's Classes, Departments, Projects, and Locations dimensions to reduce account proliferation rather than encoding business segmentation in account numbers. The merged-company target is a rationalized few-hundred-account structure with merged-company business segmentation expressed through dimensional fields (division per CRM §3.02 D-3b, geography per CRM §3.02 D-3a, Projects, and Departments).

**Decision for the leadership team.** Confirm: merged-company COA designed from a clean foundation through a joint design session, using NetSuite dimensional fields (Classes, Departments, Projects, Locations) for business segmentation rather than account proliferation. *Recommended default: yes.*

---

### D-2. Period close cadence and process

**Source:** KBM REQ-020, REQ-021, REQ-022 (`BRD_FinancialManagement_v2.0.md` §7; KBM SESSION 4); Pivot §3.12 Period Close (`Financial_Management.md` §3.12)

**KBM's approach.** KBM operates a 10-day Excel-based period close with the goal of reducing it to 5-7 days through the NetSuite Period Close Checklist module. KBM's BRD identifies SESSION 4 (Lorraine, Celine, Kevin, AP team) as the optimization-opportunity session to walk through the current 10-day process, identify bottlenecks, and design the checklist. KBM also articulates a 13-period calendar preference and the practice of opening all 13 periods at year-start.

**Pivot's approach.** Pivot already operates a 7-day period close — at or near the merged-company target. Pivot's BRD frames period close as maintaining current performance through automation rather than a major optimization opportunity.

**Recommendation for the merged company.** Adopt the NetSuite Period Close Checklist for the merged company with a working target of 7 days (matching Pivot's current cadence). KBM's existing 10-day cadence improves through the same checklist, automated reconciliations, and pre-configured recurring journal entries — KBM's SESSION 4 walkthrough informs the merged-company close design. The 13-period calendar (KBM's preference) is adopted as the merged-company calendar; Pivot's team adapts to the 13-period structure during configuration. Open-all-periods-at-year-start best practice is adopted.

**Decisions for the leadership team.**

- (2a) Confirm: NetSuite Period Close Checklist with 7-day working target. *Recommended default: yes.*
- (2b) Confirm: 13-period calendar adopted as merged-company calendar. *Recommended default: yes.*

---

### D-3. Revenue recognition rules and timing

**Source:** KBM REQ-035, REQ-036 (`BRD_FinancialManagement_v2.0.md` §14; KBM SESSION 1 critical-path, compliance-critical); Pivot §3.01 Revenue & Cost Recognition (`Financial_Management.md` §3.01)

**KBM's approach.** KBM's BRD identifies revenue recognition as compliance-critical and pending. The decision involves recognition timing (at sales order or invoice), special scenarios requiring different rules (mockup, direct bill, government, E-commerce orders), ASC 606 compliance validation, and potential external auditor engagement. KBM names SESSION 1 (Lorraine, Kipp, Marcus, possibly external auditor) as required before detailed design phase. Implementation complexity is HIGH and may require custom solution design.

**Pivot's approach.** Pivot's BRD articulates accrued revenue journal entries for delivered-but-not-invoiced items, with an approval workflow before posting. The framework is more focused on the operational mechanics (preventing invoicing before fulfillment, accrued revenue automation) than on the rules-design problem KBM is solving. Pivot's BRD does not surface ASC 606 compliance review as an open question at the same level.

**Recommendation for the merged company.** Treat revenue recognition rules as a foundational merged-company decision and run KBM's SESSION 1 expanded to include Pivot's finance leadership. The session jointly establishes recognition timing, special-scenario handling, and ASC 606 compliance for the merged company. Pivot's accrued-revenue journal-entry framework with approval workflow is adopted as the merged-company operational mechanism — it preserves the controls Pivot has and addresses KBM's stated need for proper matching of revenue and costs. External auditor engagement for compliance validation is recommended.

**Decisions for the leadership team.**

- (3a) Confirm: joint revenue-recognition-rules design session including KBM and Pivot finance leadership, with recognition timing and special-scenario handling defined for the merged company. *Recommended default: yes.* (Specific rules confirmed during the session; ASC 606 compliance validated with auditor.)
- (3b) Confirm: accrued revenue journal entries with approval workflow adopted as merged-company operational mechanism. *Recommended default: yes.*

---

### D-4. 15% labor markup continuation

**Source:** KBM REQ-023 (`BRD_FinancialManagement_v2.0.md` §8; KBM SESSION 3 critical decision)

**KBM's approach.** KBM's BRD identifies the 15% labor markup as a strategic decision pending leadership input. The current Core practice adds 15% contingency to labor costs, which affects commission calculations and creates the difference between Project GP (actual cost) and Commissionable GP (cost + markup). The decision is owned by Matt and Mark and is required before configuration. If continued, custom script development may be required; if eliminated, sales-team communication is required. KBM's BRD names this as HIGH impact on commission structure and downstream KPI reporting.

**Pivot's approach.** Pivot does not have a 15% labor markup. Pivot's dual GP structure (per CRM §3.02 D-6, locked) is built on actual labor costs vs. quoted labor costs — a different mechanism that doesn't add a contingency markup. Pivot's BRD does not articulate a labor-markup question because the practice doesn't exist in its operating model.

**Recommendation for the merged company.** The 15% labor markup is a long-established KBM pattern (Order Management REQ-038; Operations REQ-021 / REQ-022 / REQ-023; Pre-Quote v2.0 REQ-LQ-006) and a KBM-named decision gate (Matt and Mark hold leadership authority). The merged-company GP framework is already locked at the CRM level (§3.02 D-6) using Pivot's structural baseline (actual GP with time-tracked labor vs. commissionable GP with quoted labor rates) — a different mechanism than KBM's markup-contingency approach. GSI's instinct is that the commissionable-GP-on-quoted-labor framework renders the 15% markup formula line unnecessary, simplifying custom development scope and aligning the merged company on a single GP definition. **However, because the pattern is KBM's and the change materially affects KBM staff's commission experience, the retention vs. elimination decision belongs to KBM leadership.** The working session is where this decision lands. If retained, the formula-line pattern (cost-only, no revenue; positioned at bottom, uneditable, non-printing per KBM REQ-021 / REQ-022 / REQ-023) is configured in Orion. If eliminated, sales-team communication is required and the commission framework operates on commissionable GP directly per Commissions §3.07 D-1.

**Decision for the leadership team.** **Decide: retain or eliminate the 15% labor markup formula-line pattern for the merged company.** *Decided at working session with KBM leadership input (Matt and Mark per KBM BRD framing); GSI's instinct is elimination but we follow KBM's lead. Commission framework impact addressed in Commissions §3.07 D-1.*

---

### D-5. Project GP vs. Commissionable GP reporting

**Source:** KBM REQ-024, REQ-025, REQ-038 (`BRD_FinancialManagement_v2.0.md` §8, §15); cross-references CRM §3.02 D-6 (locked GP framework) and BI §3.09 D-4b (dual GP tracking as merged-company KPI)

**KBM's approach.** KBM's BRD ties the dual GP framework (Project GP vs. Commissionable GP) directly to the 15% labor markup. The two metrics serve different audiences: management sees true Project GP for actual profitability; sales team sees Commissionable GP (which includes the 15% markup) for commission purposes. Role-based permissions enforce the visibility separation.

**Pivot's approach.** Pivot's dual GP framework (locked in CRM §3.02 D-6) tracks actual GP (with time-tracked labor costs) vs. commissionable GP (with quoted labor rates) — a different conceptual basis than KBM's markup-driven approach. Pivot's framework reflects the operational reality that quoted labor and actual labor diverge, and both GP views serve different purposes (commissionable GP for commission consistency, actual GP for true profitability).

**Recommendation for the merged company.** Operate the merged company on Pivot's dual GP framework as locked in CRM §3.02 D-6 and confirmed in BI §3.09 D-4b — actual GP with time-tracked labor vs. commissionable GP with quoted labor rates. KBM's markup-driven dual GP framework is replaced by Pivot's quote-vs-actual framework when D-4 (markup elimination) is confirmed. Role-based visibility (sales sees commissionable GP, management sees actual GP) is preserved per KBM's framing. The merged-company KPI dashboards display both GP metrics with appropriate role-based access.

**Decision for the leadership team.** Confirm: dual GP framework operates per Pivot's actual-vs-quoted model (locked in CRM §3.02 D-6), with role-based visibility per KBM's framing. *Recommended default: yes.*

---

### D-6. Banking partners and electronic payment automation

**Source:** KBM REQ-008, REQ-009, REQ-010, REQ-011, REQ-012 (`BRD_FinancialManagement_v2.0.md` §3; KBM SESSION 5); Pivot §3.03 Banking & Electronic Payments (`Financial_Management.md` §3.03)

**KBM's approach.** KBM's BRD names West Coast Community Bank as the primary banking partner (confirmed in the NetSuite Bank Feeds program), articulates Advanced Electronic Bill Payments for ACH directly from NetSuite (eliminating manual bank-portal upload for $3M payment runs), positive pay process with West Coast Community Bank, and a bill-payment approval workflow with Lorraine as approver. KBM identifies SESSION 5 to clarify approval-workflow specifics (in-system removal of items vs. communication to AP) and remittance process (automatic vs. manual trigger).

**Pivot's approach.** Pivot's BRD identifies 42 manual ACH/wire journal entries to eliminate through banking automation, articulates Advanced Electronic Bill Payments for direct ACH processing, names Comerica as the banking partner with bank-feeds integration confirmed, and supports the same automated reconciliation and cash-flow visibility goals.

**Recommendation for the merged company.** Operate the merged company with multi-bank capability: West Coast Community Bank (KBM's partner, confirmed in NetSuite Bank Feeds) and Comerica (Pivot's partner, integration confirmed) both maintained as merged-company bank accounts. Bank-feeds integration, Advanced Electronic Bill Payments, and Cash360 dashboard span both banks. Bill-payment approval workflow design — including approver assignments, in-system removal-vs-communication patterns, and approval-routing rules — is decided in Order Management §3.04 as part of the merged-company approval framework. Positive pay processes are configured per each bank's capabilities. Specific bank consolidation decisions (whether to consolidate to a single bank for the merged company) are operational decisions outside the unification recommendation; the system supports either path.

**Decisions for the leadership team.**

- (6a) Confirm: multi-bank capability with West Coast Community Bank (KBM) and Comerica (Pivot) as merged-company bank accounts. *Recommended default: yes.*
- (6b) Confirm: Advanced Electronic Bill Payments configured for direct ACH from NetSuite, replacing manual bank-portal uploads. *Recommended default: yes.* (Bill-payment approval workflow design is decided in Order Management §3.04.)

---

### D-7. Expense management platform

**Source:** KBM REQ-013, REQ-014, REQ-015 (`BRD_FinancialManagement_v2.0.md` §4; KBM SESSION 6 decision required); Pivot §3.09 Expense Management (`Financial_Management.md` §3.09)

**KBM's approach.** KBM's BRD frames expense management as a platform-evaluation decision: continue Expensify (current platform) or switch to RAMP (KBM-considered alternative). The drivers are user adoption (current resistance to expense submission) and integration capability with NetSuite. KBM identifies SESSION 6 (Lorraine, AP team, sample expense submitters) for evaluation.

**Pivot's approach.** Pivot's BRD frames expense management as a decision between continuing Expensify (current platform) and migrating to NetSuite native expense functionality, with the integration-and-user-experience considerations evaluated during configuration.

**Recommendation for the merged company.** Run the merged-company expense-platform evaluation jointly across both finance teams during SESSION 6, expanded to include Pivot's expense team. Three platforms are in scope: Expensify (current at both companies), RAMP (KBM's considered alternative), and NetSuite native expense functionality (Pivot's considered alternative). Each is evaluated against merged-company requirements: project vs. G&A allocation at line level, integration with NetSuite GL, mobile receipt capture, approval workflow, and corporate-card auto-import. The decision is made at the working session with leadership input. Whichever platform is selected becomes the merged-company expense system; users from non-selected legacy platforms receive change-management support during transition.

**Decision for the leadership team.** Confirm: merged-company expense platform selected at working session through joint evaluation (Expensify, RAMP, or NetSuite native); platform decision and migration plan finalized during configuration. *Recommended default: confirm at session.*

---

### D-8. Fixed asset management

**Source:** KBM REQ-026 (`BRD_FinancialManagement_v2.0.md` §9; KBM SESSION 7 decision required); Pivot §3.07 Fixed Asset Management (`Financial_Management.md` §3.07)

**KBM's approach.** KBM's BRD frames fixed asset management as a decision between continuing Bloomberg (current third-party tool) or migrating to NetSuite's Fixed Asset module. KBM identifies SESSION 7 (Lorraine, Marcus) for cost-benefit analysis and capability comparison.

**Pivot's approach.** Pivot's BRD addresses fixed asset management as part of the comprehensive financial management capability inside NetSuite. Pivot's framing assumes NetSuite Fixed Asset module rather than a third-party tool.

**Recommendation for the merged company.** Adopt NetSuite's Fixed Asset module for the merged company. The reasoning is contextual: Pivot's BRD already frames NetSuite FA as the assumed approach, and the merged company benefits from a single integrated system rather than a third-party Bloomberg dependency. KBM's existing assets in Bloomberg migrate to NetSuite FA during data migration; depreciation methods (straight-line, declining balance, MACRS, Section 179) are configured per merged-company requirements. SESSION 7 confirms the migration approach and depreciation specifications. Bloomberg is sunset.

**Decision for the leadership team.** Confirm: NetSuite Fixed Asset module adopted; Bloomberg sunset; existing KBM assets migrated. *Recommended default: yes.*

---

### D-9. Vendor credit limit tracking and alerts

**Source:** KBM REQ-034 (`BRD_FinancialManagement_v2.0.md` §13; KBM SESSION 8); Pivot §3.15 Vendor Management (`Financial_Management.md` §3.15); cross-references CRM §3.02.4 cross-area dependencies

**KBM's approach.** KBM's BRD specifies vendor credit limit tracking as a custom development requirement: 90% warning threshold, alert mechanism (email, dashboard, hard PO block, or combination), credit utilization calculation (open POs + unpaid bills vs. limit), and proactive monitoring to prevent reactive payment disruptions when limits are unexpectedly reached. KBM identifies SESSION 8 (Lorraine, Purchasing Team, Shannon) for detailed requirements. Shannon is the named stakeholder.

**Pivot's approach.** Pivot's BRD addresses vendor management within its broader framework. The specific vendor-credit-limit-tracking requirement is not articulated at the same level of custom development detail as KBM's framing.

**Recommendation for the merged company.** Adopt KBM's vendor credit limit tracking framework as merged-company default. The reasoning is contextual: the merged company's vendor footprint will be larger than either legacy company's (KBM's vendor base + Pivot's vendor base + the merged-company growth path), making proactive credit-limit monitoring more valuable. The custom alert workflow (90% warning threshold, alert recipients, credit-utilization calculation including open POs and unpaid bills) is built per KBM's specification. Specific thresholds and alert recipients are finalized during configuration with merged-company purchasing leadership.

**Decision for the leadership team.** Confirm: vendor credit limit tracking with 90% warning threshold and custom alert workflow, configured per KBM framework. *Recommended default: yes.*

---

### D-10. Collections management and AR framework

**Source:** Pivot §3.04 Collections Management, §3.14 Accounts Receivable Management (`Financial_Management.md` §3.04, §3.14); KBM addresses AR within broader CRM and customer financial management context

**KBM's approach.** KBM's BRD addresses customer financial management through pro forma invoices for deposits, finance charge capability (off by default), and customer portal access for self-service. KBM does not have a dedicated collections-management framework as a separate sub-area; collections are addressed within the operational AR processes.

**Pivot's approach.** Pivot's BRD has dedicated sections for Collections Management (§3.04) and AR Management (§3.14), articulating systematic collections workflows, customer aging analysis, automated dunning, and unified AR dashboards (locked in BI §3.09 D-4 as part of the AR Collections 360 dashboard).

**Recommendation for the merged company.** Adopt Pivot's collections management and AR framework as merged-company baseline. The reasoning is contextual: the merged company's AR volume across both companies' customer bases benefits from the systematic collections framework Pivot articulates, and the AR Collections 360 dashboard already locked in BI §3.09 D-4 is operationalized through this framework. KBM's customer-portal capability and finance-charge configuration carry forward as part of the merged-company AR setup. Specific dunning workflows, collections cadence, and approval thresholds are finalized during configuration.

**Decision for the leadership team.** Confirm: Pivot's collections management and AR framework adopted as merged-company baseline; KBM's customer-portal and finance-charge capabilities carry forward. *Recommended default: yes.*

---

## 3.08.4 Cross-area dependencies

The following surfaced in Financial Management discovery but are decided in other process areas. They are flagged here so the working session understands the connections; the decisions themselves live in their proper home area.

| Dependency | Where it surfaced in Financial Management | Where it's decided |
|---|---|---|
| **Dual GP framework (actual vs. commissionable)** | Project accounting, KPI dashboards, commission reporting | **CRM (§3.02 D-6)** — GP framework is locked; Financial Management operationalizes the locked framework |
| **Approval workflow framework** | Bill-payment approval workflow (D-6c), erosion approvals, expense approvals | **Order Management (§3.04)** — approval framework design lives there |
| **Commission structure** | Labor markup decision (D-4) impacts commission calculations | **Commissions (§3.07)** — commission framework design lives there |
| **Division taxonomy for COA design** | Merged-company business segmentation in COA dimensions (D-1) | **CRM (§3.02 D-3b)** — division taxonomy pending working-session confirmation |
| **Geography / location taxonomy for COA** | Sales Locations as COA dimension (D-1) | **CRM (§3.02 D-3a)** — two-dimensional model locked |
| **Project record framework** | Project-level revenue/cost tracking (D-3, D-5) | **Project Management (§3.06)** — project record structure decided there |
| **Document storage architecture** | Document management for AP, AR, financial records | **System Setup & Configuration (§3.10 D-3)** — SharePoint as merged-company collaboration platform with KBM Google Drive content migrating on transition timeline |
| **Historical data migration scope** | Historical financial data back to 2017 (KBM REQ-017); D365 historical migration (Pivot) | **System Setup & Configuration (§3.10)** — overall data migration plan |
| **Vendor credit limits** | KBM's framework (D-9) cross-references CRM §3.02.4 dependency table | **Order Management (§3.04)** if procurement-led, or here in Financial Management if finance-led; cross-area linkage |
| **Multi-company / multi-contact for billing** | Intermarket dealer transactions (KBM REQ-033) | **CRM (§3.02 D-4)** — relationship model locked; Financial Management uses the model for billing and payment |

## 3.08.5 Recommendation summary

The merged-company Financial Management playbook in shorthand:

- **Foundation:** Single subsidiary, USD-only, 13-period calendar, merged-company COA designed from clean foundation using NetSuite dimensional fields
- **Period close:** NetSuite Period Close Checklist with 7-day working target (Pivot's current cadence)
- **Revenue recognition:** Joint design session for merged-company recognition rules with ASC 606 compliance validation; Pivot's accrued revenue journal-entry framework with approval workflow as operational mechanism
- **Labor markup:** 15% markup retention vs. elimination is open at the working session — GSI follows KBM's lead since the pattern is theirs (Matt and Mark hold authority per KBM BRD framing). Merged-company GP operates on the locked CRM §3.02 D-6 dual GP framework regardless
- **GP reporting:** Dual GP framework per Pivot's actual-vs-quoted model, with role-based visibility (sales sees commissionable GP, management sees actual GP)
- **Banking:** Multi-bank capability; Advanced Electronic Bill Payments for ACH; Cash360 dashboard; positive pay configured per bank capabilities
- **Expense management:** Joint platform evaluation (Expensify or RAMP); platform decision at working session
- **Fixed assets:** NetSuite Fixed Asset module adopted; Bloomberg sunset
- **Vendor credit limits:** KBM's custom alert workflow framework adopted (90% warning threshold)
- **Collections / AR:** Pivot's collections management and AR framework adopted; KBM's customer-portal and finance-charge capabilities carry forward
- **Tax management:** Native SuiteTax for nexus management (KBM's 48-state nexus + Pivot's California focus = merged-company nexus footprint)
- **Reporting:** Real-time financial dashboards replacing Excel-based reporting; project-level KPI dashboards per locked BI §3.09 framework

Net read: the merged-company Financial Management combines design choices that fit the merged-company's situation. Pivot's contributions reflect its documented 7-day close cadence, accrued-revenue framework, dedicated collections and AR sub-areas, dual GP actual-vs-quoted model, AP automation, dynamic terms-and-conditions handling, and the breadth of its 16-section coverage. KBM's contributions reflect its eight-session follow-up framework, three critical decision gates (revenue recognition, COA, labor markup), named stakeholder roles, vendor credit-limit detail, and banking-partner specificity. The merged company benefits from both — Pivot's process documentation provides operational depth; KBM's decision-gate framework provides implementation sequencing.

## 3.08.6 Decisions for the leadership team

| # | Decision | Default | Reference |
|---|---|---|---|
| 1 | Merged-company COA designed from clean foundation through joint design session, using NetSuite dimensional fields | Yes | D-1 |
| 2a | NetSuite Period Close Checklist with 7-day working target | Yes | D-2 |
| 2b | 13-period calendar adopted as merged-company calendar | Yes | D-2 |
| 3a | Joint revenue-recognition-rules design session with ASC 606 compliance validation | Yes (rules confirmed during session) | D-3 |
| 3b | Accrued revenue journal entries with approval workflow adopted as operational mechanism | Yes | D-3 |
| 4 | 15% labor markup retention vs. elimination for the merged company (KBM REQ-038 / Operations REQ-021-023 / Pre-Quote v2.0 REQ-LQ-006) | Decided at working session | D-4 |
| 5 | Dual GP framework per Pivot's actual-vs-quoted model with role-based visibility | Yes | D-5 |
| 6a | Multi-bank capability — West Coast Community Bank (KBM) and Comerica (Pivot) as merged-company bank accounts | Yes | D-6 |
| 6b | Advanced Electronic Bill Payments for direct ACH from NetSuite | Yes | D-6 |
| 7 | Merged-company expense platform selected at working session (Expensify or RAMP) | Confirm at session | D-7 |
| 8 | NetSuite Fixed Asset module adopted; Bloomberg sunset | Yes | D-8 |
| 9 | Vendor credit limit tracking with 90% warning threshold per KBM framework | Yes | D-9 |
| 10 | Pivot's collections management and AR framework adopted; KBM's customer-portal and finance-charge capabilities carry forward | Yes | D-10 |

> 13 decisions: 12 with default-yes recommendations and 1 (decision 7, expense platform) requiring leadership-team selection during the working session.

## 3.08.7 Configuration carryover

| Item | KBM-side built? | Pivot-side built? | Action for merged company |
|---|---|---|---|
| Subsidiary structure | Single subsidiary in Core | D365-based; migrating | Configure single subsidiary in merged-company NetSuite |
| Chart of accounts | Current Core COA (40+ pages) | Current D365 COA | Design fresh per D-1 |
| Period close framework | Excel-based 10-day | 7-day cadence | Build NetSuite Period Close Checklist per D-2 |
| Revenue recognition rules | Currently at order creation | Accrued revenue framework specified | Joint design session per D-3 |
| 15% labor markup | In Core (REQ-038 / Operations REQ-021-023 / Pre-Quote v2.0 REQ-LQ-006) | Not present | Retain or eliminate per D-4 (working session decision) |
| Dual GP framework | Project GP + Commissionable GP (markup-driven) | Actual vs. quoted (locked CRM §3.02 D-6) | Reconfigure per D-5 |
| Banking integration | West Coast Community Bank specified, in progress | Pivot's bank specified, in progress | Multi-bank per D-6 |
| Advanced Electronic Bill Payments | Specified | Specified (eliminating 42 manual ACH/wires) | Configure per D-6b |
| Expense management platform | Expensify currently | Specified, not finalized | Joint decision per D-7 |
| Fixed asset management | Bloomberg currently | NetSuite FA assumed | NetSuite FA per D-8; sunset Bloomberg |
| Vendor credit limit alerts | Specified (custom workflow) | Not specified | Build per D-9 |
| Collections management framework | Within broader AR processes | Dedicated framework specified | Adopt Pivot framework per D-10 |
| Tax management (SuiteTax) | Specified | Specified | Configure for merged-company nexus footprint |
| Period close: 13 vs. 12 periods | 13 periods | 12 periods (standard) | 13 periods per D-2b; Pivot adapts |
| Real-time financial dashboards | Specified | Specified | Build per BI §3.09 |
| Stripe credit card integration | Specified (low volume) | Not specified | Maintain per KBM framing |
| Wire transfer processing | Specified | Specified | Configure per merged-company need |

Configuration is in early enough state on both sides that the merged direction is achievable. The COA design is the largest foundational task; Pivot's D365 migration provides a fresh-start opportunity that aligns well with KBM's consolidation goal.

## 3.08.8 Open questions / inputs needed

1. **COA design specifics** (decision 1) — joint design session establishes account structure, dimensions, and mapping; specific account count and hierarchy finalized during configuration.
2. **Revenue recognition rules** (decision 3a) — recognition timing, special-scenario handling (mockup, direct bill, government, E-commerce), ASC 606 compliance validation, and external auditor engagement determined during joint design session.
3. **Bank consolidation operational decision** (decision 6a) — whether the merged company eventually consolidates to a single bank is an operational decision outside the unification recommendation; the system supports either path.
4. **Expense platform decision** (decision 7) — Expensify vs. RAMP joint evaluation completed during working session; specific platform selected.
5. **Vendor credit limit thresholds and alert recipients** (decision 9) — specific thresholds (90% working default), alert recipients, and credit-utilization calculation details finalized during configuration with merged-company purchasing leadership.
6. **Pivot finance leadership input** — Pivot's CFO equivalent and finance team participate in the joint COA design session, revenue-recognition-rules session, and expense-platform evaluation. Pivot leadership participation is confirmed before the working session.
7. **External auditor engagement** — recommended for revenue recognition rules (decision 3a); engagement letter and timeline confirmed during working session.
8. **Historical data migration scope** (cross-references System Setup §3.10) — KBM's 2017 historical data + Pivot's D365 historical data migration scope and cutover sequencing finalized during data-migration planning.
9. **Payroll provider for the merged company** — KBM uses Paylocity; Pivot uses UKG. Merged-company payroll provider decision (consolidate to one or maintain both) and CSV import configuration finalized during configuration.
10. **Tax management — SuiteTax vs. Avalara and filing approach** — Pivot REQ-3.06.01 and REQ-3.06.08 raise SuiteTax vs. Avalara as a decision and identify a filing-approach question. Joint design session confirms merged-company tax-management approach including KBM's 48-state nexus and Pivot's California focus.
11. **Pivot AP automation specifics** (Pivot REQ-3.05.01 through REQ-3.05.05) — AP automation framework details (vendor onboarding, invoice processing, approval routing, payment runs) configured per Pivot framework with KBM's bill-payment approval pattern integrated via Order Management §3.04.
12. **Pivot dynamic terms-and-conditions and document numbering** (Pivot REQ-3.08.01 through REQ-3.08.03) — dynamic T&C handling and document-numbering rules configured per Pivot framework during Realize phase.
13. **KBM REQ-019 automated allocations decision** — leadership decision (Matt and Mark) on automated allocation transactions before configuration, per KBM SESSION 3 context.
14. **Pivot vendor returns / VRA / FedEx integration** (Pivot REQ-3.15.01, REQ-3.15.02) — vendor return-authorization and FedEx integration scope finalized during Realize phase.
