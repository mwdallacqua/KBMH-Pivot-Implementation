# 3.04 — Order Management

| Field | Value |
|---|---|
| **Decision density** | **Medium-High** — approval framework, customer-PO tracking, order-type taxonomy, document workflow, deposit and pre-payment management, client quote approval, PO generation depth, MillerKnoll integrations, and tiered-pricing escalation |
| **Source coverage** | Pivot Order Management BRD v2.0 (12 sub-sections, narrative bullet requirements rather than numbered REQ IDs) + KBM Order Management requirements map (43 numbered requirements; gap analysis identifies follow-up sessions for draft PO, customer PO tracking, e-portals, complete order type list) |
| **KBM source** | `Order Management/KBMH/3 Output/Requirements_Map_OrderManagement_v1.0.md` plus `GapAnalysis_OrderManagement_v1.1.md` and `Questionnaire_OrderManagement_v1.1.md` |
| **Pivot BRD** | `Order Management/Pivot/4 BRD/05_Pivot Interiors BRD Order Processing_v2.0.docx` (markdown copy at `_Unification/working/pivot-brds-md/Order_Management.md`); 12 sub-sections — Invoice Schedules and Deposits, Quote Approval Workflows, SIF Import & BOM Processing, Smart Table Grouping, Deposit and Pre-Payment Management, PDF Composer, Client Quote Approval, Budget Setting at Sales Order Conversion, Pro Forma Invoice Management, Purchase Order Generation, MillerKnoll Order Manager Integration, and Acknowledgements |

---

## 3.04.1 How each company approaches Order Management today

**KBM Hogue** approaches Order Management through 43 numbered requirements covering transaction structure (REQ-001 through REQ-005), SIF / Smart Table / approval mechanics (REQ-006 through REQ-010, including REQ-010 — no separate SO approval workflow beyond proposal approval, "approval done at proposal stage"), tax management (REQ-011 through REQ-014), commissions (REQ-015 through REQ-018, REQ-031, REQ-035 through REQ-038), customer PO tracking (REQ-016 through REQ-019), approval workflow (REQ-020 through REQ-026, including the $25K Shannon completeness check, missing-requirements escalation to Matt Denning, $1,500 cumulative-erosion approval to Matt Denning, up-to-10 rule capacity, approval-time tracking, and double-order detection), template ownership (REQ-027 through REQ-030, including Kipp's self-service modification of customer-facing and vendor-facing templates), order types (REQ-031 through REQ-034 — Direct Bill ~$1M annually, Intermarket inbound ~40 / outbound thousands, "Intuit Work from Home" renamed from e-commerce, Government ~20% of business), and integrations (REQ-039 through REQ-043 — ServiceNet, Coupa email-parsing, ServiceTime, MillerKnoll Quote Tool, plus the FUTURE escalation REQ-043 for project-level tiered-pricing recognition). KBM's source flags a critical change-management item: the move from a single transaction with status changes to separate linked transactions (Opportunity → Proposal → Sales Order with prefixes OP / PROP / SO / DPO / VPO / INV).

**Pivot Interiors** approaches Order Management through 12 BRD sub-sections (narrative bullet requirements rather than numbered REQ IDs). Coverage includes invoice schedule templates with pro forma invoice generation (Invoice Schedules and Deposits, BRD lines 157-249), comprehensive quote approval workflows with margin-based and dollar-threshold rules (Quote Approval Workflows, lines 251-334), SIF Import with demonstrated 1,000-line / 10-second performance and BOM processing (SIF Import & BOM Processing, lines 336-432), Smart Table grouping with multi-grouping support and bulk editing (Smart Table Grouping, lines 434-525), quote-level deposits and vendor pre-payments with automatic application to invoices and vendor bills (Deposit and Pre-Payment Management, lines 527-621), PDF Composer with 10 templates and dynamic field selection (GSA / budgetary / formal / client-specific, lines 623-717), web-based client quote approval system replacing Docentric (Client Quote Approval, lines 719-812), budget locking at sales-order conversion with time tracking against budgets (Budget Setting at Sales Order Conversion, lines 814-891), pro forma invoice management without GL impact (Pro Forma Invoice Management, lines 893-987), purchase order generation depth — direct PO from SIF, draft PO with line constitution, mass PO updates, requisition workflows (Purchase Order Generation, lines 989-1095), MillerKnoll Order Manager integration with vendor splitting and acknowledgement processing (lines 1097-1172), and acknowledgements automation (lines 1174-end). Pivot's BRD also flags a critical outstanding item: customer PO limit documentation for Oracle, Apple, Google (BRD line 1288).

Both companies share end-state goals: a clean Opportunity → Quote → Sales Order → Project flow with separate linked transactions, configurable approval workflows for quotes (KBM REQ-010 — no separate SO approval), SIF and BOM import via Smart Table, deposit and invoice schedule management, automated purchase order generation, MillerKnoll integration capabilities, acknowledgement automation, and tax automation through SuiteTax. Where they differ is in the specificity of approval-rule thresholds (KBM articulates explicit dollar thresholds and approver assignments; Pivot articulates the framework with margin-based and low-margin SVP rules but without KBM's named thresholds), the depth of customer-PO tracking (KBM articulates a custom record / transaction with KPI dashboard; Pivot raises customer PO limit documentation as an open need for specific accounts), the order-type taxonomy detail (KBM names specific types and volumes; Pivot uses a category framework cross-referenced from Pre-Quote §3.03 D-7), the deposit / pre-payment depth (Pivot articulates quote-level deposits and vendor pre-payments at depth; KBM addresses deposits through pro forma invoice), the PO generation depth (Pivot articulates direct PO from SIF, draft PO with line constitution, mass updates, requisitions; KBM has identified draft PO as a gap-analysis open item), the PDF Composer depth (Pivot articulates 10 templates with dynamic field selection; KBM emphasizes self-service ownership via Kipp without specifying the same template inventory), and the client quote approval mechanism (Pivot specifies a web-based portal replacing Docentric; KBM does not articulate the same).

## 3.04.2 Where the two companies align

The following capabilities are common ground across both BRDs/source materials and require no merged-company decision:

**Explicit in both:**

- Separate linked transactions: Opportunity → Proposal/Quote → Sales Order with one-click conversion (KBM REQ-001 through REQ-005)
- Project number as primary reference key across all related transactions (KBM REQ-002)
- Hyperlinked relationships between related transactions (KBM REQ-005)
- SIF import with Smart Table integration (KBM REQ-006 / REQ-008; Pivot SIF Import & BOM Processing section)
- Smart Table grouping for PO planning, with multi-grouping support and bulk editing (KBM REQ-008; Pivot Smart Table Grouping section)
- BOM processing for vendor purchase orders (Pivot SIF Import & BOM Processing section)
- Tax automation through SuiteTax with ship-to-address-based calculation (KBM REQ-011)
- Tax-exemption certificate management with expiration tracking (KBM REQ-012)
- Pro forma invoice for deposits, no GL impact until payment received (Pivot Pro Forma Invoice Management section; KBM REQ-014 finance-charge framework)
- Configurable approval workflow framework for quotes (KBM REQ-023 — up to 10 rules; Pivot Quote Approval Workflows section)
- No separate SO approval beyond proposal approval (KBM REQ-010)
- Acknowledgements with automated workflow (Pivot Acknowledgements section)
- MillerKnoll Order Manager integration / Quote Tool integration (KBM REQ-042; Pivot Miller-Knoll Order Manager Integration section)
- Header-level commission with split-percentage assignment (KBM REQ-035; Pivot Commissions §3.04.01)
- Line-level commissionable flag (KBM REQ-036)

**KBM-explicit; standard capability carried forward for the merged company:**

- Transaction-prefix scheme (OP / PROP / SO / DPO / VPO / INV) per KBM REQ-003
- Storage fees always commissionable, billed back to client (KBM REQ-015)
- 15% labor markup formula lines (KBM REQ-038) — see Financial Management §3.08 D-4 for merged-company decision (eliminated)
- Self-service template management via Kipp's ownership pattern (KBM REQ-027, REQ-028)
- ServiceNet integration for MillerKnoll intermarket orders (KBM REQ-039)
- ServiceTime integration for high-volume intermarket orders (KBM REQ-041)
- Coupa email-parsing automation evaluation pending ROI (KBM REQ-040)
- Direct Bill order-type commission gross-up (KBM REQ-031)

**Pivot-explicit; standard capability carried forward for the merged company:**

- Invoice schedule templates (50/40/10, 30/40/30, 100% prepay, custom variations) with up to 5 standard templates (Pivot Invoice Schedules and Deposits section)
- Deposit visibility at quote, sales order, and project levels (Pivot Invoice Schedules and Deposits section; Pivot Deposit and Pre-Payment Management section)
- SIF import performance (1,000 lines in ~10 seconds per Pivot demonstration) with exception view for problematic lines (Pivot SIF Import & BOM Processing section)
- Smart Table multi-grouping (different grouping methods for PO creation vs. invoicing), bulk editing across grouped items, named groups by aliases / tags / vendors (Pivot Smart Table Grouping section)

These are noted in the merged BRD; configuration proceeds against standard NetSuite Orion order-management capability.

**Items KBM marked as ACCOMMODATE / requires solution design (not standard carry-forward):**

- XML import with JSON conversion (KBM REQ-007 — ACCOMMODATE; Matt Denning to provide template example for design)
- Customer PO tracking (KBM REQ-016 through REQ-018 — ACCOMMODATE; see D-2)
- Up-to-10 approval rules capacity (KBM REQ-023 — ACCOMMODATE)
- Double-order detection query (KBM REQ-025 — ACCOMMODATE)
- Vendor credit limit warnings (KBM REQ-026 — ACCOMMODATE; see D-2 vendor-credit cross-reference)

## 3.04.3 Where the two companies differ

Eight in-area divergences. Each is presented as: how each company approached it (with attribution to context), the recommendation for the merged company, and the decision the leadership team owns.

---

### D-1. Approval workflow framework — thresholds, approvers, and rule capacity

**Source:** KBM REQ-010, REQ-020 through REQ-025 (`Requirements_Map_OrderManagement_v1.0.md:34,55-60`); KBM Questionnaire (`Questionnaire_OrderManagement_v1.1.md:1114-1119` for the no-SO-approval framework); Pivot Quote Approval Workflows section (`Order_Management.md:251-334`); Pivot Feb 2026 BRD review (low-margin SVP approval pattern); cross-references CRM §3.02 D-6 (GP framework)

**KBM's approach.** KBM's source material articulates explicit approval rules: orders over $25,000 route to Shannon (Project Coordinator Manager) for completeness check (REQ-020); orders missing any of four required items (deposit, signed proposal, signed drawings, signed lookbook) route to Matt Denning for exception (REQ-021); cumulative erosion exceeding $1,500 routes to Matt Denning with the philosophy that approval is a coaching opportunity rather than punitive (REQ-022). KBM allocates capacity for up to 10 approval rules (REQ-023) and articulates approval-time tracking and reporting (REQ-024). KBM's framework also includes a double-order detection query (same dollar amount within 30 days flagged for manual review, REQ-025). KBM explicitly specifies REQ-010 — no separate sales-order approval workflow beyond proposal approval; the rationale captured in the KBM transcript is that proposal approval already covers the spec check and other requirements, so by the time the sales order is created, the underlying approvals have all completed.

**Pivot's approach.** Pivot's BRD articulates quote approval workflows as a comprehensive framework with email-based status tracking eliminated through automated workflow routing and real-time approval visibility (Pivot Quote Approval Workflows section, lines 251-334). Pivot's framework includes margin-based and dollar-threshold approval rules with audit trails and approval visibility, plus a low-margin SVP approval pattern surfaced in the Pivot Feb 2026 BRD review (cross-references CRM §3.02 D-6 GP framework). Pivot's BRD does not name specific dollar thresholds or specific KBM-style approver roles.

**Recommendation for the merged company.** Combine the two frameworks into a unified merged-company approval framework with multiple rule classes: KBM's order-value thresholds (e.g., $25K) and missing-requirements rules; KBM's cumulative-erosion approval; Pivot's low-margin SVP approval pattern; Pivot's margin-based and dollar-threshold rules with audit trails. The framework operates within Orion's workflow-routing infrastructure with KBM's specific thresholds as working defaults. KBM REQ-010 — no separate sales-order approval workflow beyond proposal approval — is preserved as the merged-company default; reapproval triggers on the proposal (significant scope change, dollar-amount delta beyond a threshold) are configured during Realize. Specific merged-company role assignments for the approver positions (currently Shannon and Matt Denning at KBM Hogue; SVPs at Pivot for low-margin approval) are determined during organizational alignment. Approval-time tracking surfaces in BI dashboards (per BI §3.09).

**Decisions for the leadership team.**

- (1a) Confirm: KBM's approval-rule framework (specific thresholds, named-role approvers, up-to-10 rules, approval-time tracking) integrated within Orion workflow-routing infrastructure that also supports Pivot's margin-based and low-margin SVP rules. *Recommended default: yes.*
- (1b) Confirm: $25K order-approval threshold (KBM REQ-020), missing-requirements exception threshold (KBM REQ-021), $1,500 cumulative erosion threshold (KBM REQ-022), Pivot low-margin SVP approval, and Pivot margin-based / dollar-threshold rules as merged-company working defaults. *Recommended default: yes.* (Specific merged-company role assignments determined during organizational alignment.)
- (1c) Confirm: double-order detection query — same dollar amount within 30 days flagged for manual review (KBM REQ-025). *Recommended default: yes.*
- (1d) Confirm: no separate sales-order approval workflow beyond proposal approval (KBM REQ-010); reapproval triggers on the proposal configured during Realize. *Recommended default: yes.*

---

### D-2. Customer PO tracking and KPI dashboard

**Source:** KBM REQ-016, REQ-017, REQ-018, REQ-019 (`Requirements_Map_OrderManagement_v1.0.md:49-52`); Pivot BRD customer PO limit documentation need (`Order_Management.md:1288` — "Customer PO limit documentation for Oracle, Apple, Google"); KBM Questionnaire (`Questionnaire_OrderManagement_v1.1.md:354-358` — deposit-management open detail items)

**KBM's approach.** KBM's source material articulates a custom transaction or record for customer PO tracking (REQ-016), with PO value aggregated at the project level (REQ-017) and a KPI dashboard showing PO utilization, amount billed, and remaining balance with alerts when approaching the limit (REQ-018). The framework supports complex scenarios (multiple POs per project, change orders, blanket POs) and is identified as bank-reporting-driven and competitive-advantage-relevant. KBM identifies a separate design session as required.

**Pivot's approach.** Pivot's BRD addresses customer PO information through standard quote-to-invoice flow — customer PO number as a field on invoices and proposals — without a dedicated custom record for tracking PO utilization across multiple orders. However, Pivot's BRD also identifies a critical outstanding item (BRD line 1288): customer PO limit documentation for major customers Oracle, Apple, and Google, where blanket-PO-style consumption tracking is operationally needed.

**Recommendation for the merged company.** Adopt KBM's customer PO tracking framework as a merged-company capability — custom record/transaction for tracking, project-level aggregation, KPI dashboard with utilization and remaining balance, and threshold alerts. The reasoning is contextual: the merged company's customer base includes large customers with project-level POs spanning multiple orders (KBM's project-PO patterns and Pivot's Oracle / Apple / Google blanket-PO scenarios), and the bank-reporting and competitive-advantage value KBM articulates applies to the merged operation. The framework also addresses Pivot's outstanding customer PO limit documentation need by extending the same record / dashboard / alert capability to Pivot's named accounts. The detailed design session KBM identified runs jointly with Pivot's order-processing leads and uses Pivot's named accounts as test cases.

**Decision for the leadership team.** Confirm: customer PO tracking framework adopted from KBM source (custom record, project-level aggregation, KPI dashboard, threshold alerts); extended to address Pivot's customer PO limit documentation need for Oracle, Apple, Google. *Recommended default: yes.* (Detailed design completed during Realize phase joint design session.)

---

### D-3. Order-type taxonomy

**Source:** KBM REQ-031 through REQ-034 (`Requirements_Map_OrderManagement_v1.0.md:55-58`); Pivot order types addressed across Pre-Quote BRD (cross-reference Pre-Quote §3.03 D-7 specialized order types — WIX, ServiceNet, DUR, GSA, mockup, lease/third-party billing, storage agreements)

**KBM's approach.** KBM's source material names specific order types with associated volumes: Direct Bill (~$1M annually, gross up for commission, separate reporting, REQ-031), Intermarket (inbound ~40/year; outbound thousands handled by Shannon at 8-10/day with ServiceTime integration, REQ-032 / REQ-033), "Intuit Work from Home" (renamed from e-commerce, separate reporting visibility, REQ-034), Government (~20% of business, special tax handling tied to KBM REQ-013). KBM's BRD identifies the dealer-as-vendor-and-customer dual setup as the first-time pain point for intermarket orders.

**Pivot's approach.** Pivot's broader specialized-order-type framework lives in the Pivot Pre-Quote BRD (cross-reference Pre-Quote §3.03 D-7), which includes specialized types like WIX, ServiceNet, DUR (Delivery Upon Receipt), GSA (government), mockup, lease/third-party billing, and storage agreements. The order-type field drives automation; the typing structure is broader than KBM's named set.

**Recommendation for the merged company.** Pre-Quote §3.03 D-7 is the **owner** for the merged-company specialized-order-type taxonomy. Order Management uses the taxonomy decided there. KBM's named order types (Direct Bill, Intermarket, "Intuit Work from Home", Government) are integrated into Pre-Quote's broader specialized-order-type framework. The order-type field drives automation across both Order Management and Pre-Quote; volumes and reporting cuts reflect the merged-company business. Intermarket order processing leverages the ServiceTime and ServiceNet integrations (KBM framework) for high-volume order handling. Specific naming convention reconciliation (e.g., whether to use "Intuit Work from Home" vs. a more generic name) is finalized during configuration coordinated with Pre-Quote.

**Decision for the leadership team.** Confirm: combined order-type taxonomy decided in Pre-Quote §3.03 D-7 with KBM's named types integrated; Order Management uses the taxonomy and applies order-type-driven automation. *Recommended default: yes.* (Naming convention finalized during configuration.)

---

### D-4. Invoice schedule templates, deposit and pre-payment management, budget locking

**Source:** Pivot Invoice Schedules and Deposits section (`Order_Management.md:157-249`); Pivot Deposit and Pre-Payment Management section (`Order_Management.md:527-621`); Pivot Budget Setting at Sales Order Conversion section (`Order_Management.md:814-891`); Pivot Pro Forma Invoice Management section (`Order_Management.md:893-987`); KBM Financial Management REQ-032 (pro forma invoice for deposits); KBM Questionnaire (`Questionnaire_OrderManagement_v1.1.md:354-358` — deposit management open items)

**KBM's approach.** KBM's source materials cover deposits through the pro forma invoice mechanism (KBM Financial Management REQ-032) but do not articulate complex invoice schedule templates with predefined patterns. KBM's gap analysis flags deposit-percentage rules, application process, and milestone-billing scenarios as open for further design.

**Pivot's approach.** Pivot's BRD articulates four interlocking capabilities at depth:

- **Invoice schedule templates** (Invoice Schedules and Deposits section) — supporting common patterns (50/40/10, 30/40/30, 100% prepay) plus custom variations, with up to 5 standard templates configured. Pro forma invoices generate with full project details while remaining outside the GL until payment is received. The framework supports invoice-amount-vs-payment-received reporting via saved search.
- **Quote-level deposits** (Deposit and Pre-Payment Management section) — deposits taken at the quote stage before sales-order conversion, with automatic association upon conversion. NetSuite does not natively support quote-level deposits; this is custom Quote Deposit functionality. Payment processing gateway decision pending.
- **Vendor pre-payments** — captured against draft purchase orders, with automatic application to vendor bills.
- **Budget locking at sales-order conversion** (Budget Setting at Sales Order Conversion section) — budget locked at SO conversion with time tracking against the locked budget; supports the Pivot PM time-tracking framework (cross-reference Project Management §3.06 D-4).

**Recommendation for the merged company.** Adopt Pivot's complete invoice / deposit / budget framework as the merged-company default. The reasoning is contextual: Pivot's framework supports the complex billing scenarios common to commercial furniture projects (deposits, milestone billing, prepay arrangements, quote-level deposits, vendor pre-payments, budget locking), and KBM's pro forma invoice approach integrates as one billing pattern within the broader framework. The 5-template starting point covers the merged company's typical billing cadence, with custom variations available for specific customer arrangements. Quote-level deposits and vendor pre-payments are configured as part of the Realize phase.

**Decisions for the leadership team.**

- (4a) Confirm: Pivot's invoice schedule template framework (50/40/10, 30/40/30, 100% prepay, custom variations; up to 5 standard templates). *Recommended default: yes.*
- (4b) Confirm: quote-level deposits with automatic association on SO conversion, plus vendor pre-payments against draft POs. *Recommended default: yes.* (Payment processing gateway decision finalized during Realize.)
- (4c) Confirm: budget locking at sales-order conversion with time tracking against locked budget. *Recommended default: yes.* (Cross-references Project Management §3.06 D-4.)

---

### D-5. PDF Composer, template management, and client quote approval

**Source:** KBM REQ-027 through REQ-030 (`Requirements_Map_OrderManagement_v1.0.md:64-67`); Pivot PDF Composer section (`Order_Management.md:623-717`) — 10 templates with dynamic field selection (budgetary / formal / GSA / client-specific); Pivot Client Quote Approval section (`Order_Management.md:719-812`) — web-based portal replacing Docentric

**KBM's approach.** KBM's source material articulates self-service template management as a major value driver (REQ-027) — Kipp and the team can modify templates without GSI billable hours; Kipp owns the design ownership for customer-facing templates (proposals, invoices, order confirmations, REQ-029) and vendor-facing templates (purchase orders, REQ-030). KBM specifically identifies vendor PO redesign as a priority — vendor PO content and organization require redesign per KBM REQ-030, called out explicitly: "Our current POs are a shitstorm of information." KBM articulates template version control and change documentation as a process requirement (REQ-028). KBM does not address client quote approval / portal mechanics.

**Pivot's approach.** Pivot's BRD articulates PDF Composer at depth (lines 623-717) — 10 configured templates supporting budgetary, formal, GSA, and client-specific formats, with dynamic field selection at generation time (sales coordinators turn fields on / off through interface checkboxes), GSA templates pre-configured to exclude terms and conditions, and consistent logo / branding across templates. The framework eliminates the manual PDF editing currently required after generation from D365 or CAP. Pivot also articulates a client quote approval system (lines 719-812) — web-based customer portal replacing Docentric email system, with desktop and mobile access, attachment support beyond proposal PDF, real-time dashboard notifications when customers act in the portal, and timestamped audit trail.

**Recommendation for the merged company.** Adopt the combined framework: Pivot's PDF Composer infrastructure with the 10-template inventory and dynamic field selection (budgetary / formal / GSA / client-specific) as the merged-company default; KBM's self-service template management framework with Kipp-pattern ownership for the merged-company team, including version control and change documentation; KBM's customer-facing and vendor-facing templates recreated using PDF Composer during configuration, with vendor PO redesign as an explicit configuration deliverable; Pivot's web-based client quote approval portal adopted as merged-company default replacing email-based approval tracking and Docentric.

**Decisions for the leadership team.**

- (5a) Confirm: PDF Composer with the 10-template inventory and dynamic field selection (budgetary / formal / GSA / client-specific) per Pivot framework. *Recommended default: yes.*
- (5b) Confirm: self-service template management with merged-company design ownership (KBM's Kipp-pattern ownership extended to the merged-company team), with template version control and change documentation. *Recommended default: yes.*
- (5c) Confirm: customer-facing templates (proposals, invoices, order confirmations) and vendor-facing templates (purchase orders) recreated via PDF Composer during configuration; vendor PO redesign as explicit deliverable. *Recommended default: yes.*
- (5d) Confirm: web-based client quote approval portal adopted as merged-company default, replacing Docentric email system. *Recommended default: yes.*

---

### D-6. Tax management — government tax overrides

**Source:** KBM REQ-013 (`Requirements_Map_OrderManagement_v1.0.md:44`); KBM Questionnaire (`Questionnaire_OrderManagement_v1.1.md` — government order tax handling); cross-references Financial Management §3.08 (SuiteTax framework)

**KBM's approach.** KBM's source material flags government order tax handling as a specific pain point (REQ-013). KBM has historically taxed to final destination, while MillerKnoll's policy directs tax to warehouse location for direct bill orders. The mismatch creates government-customer dissatisfaction. Government work represents approximately 20% of KBM's business; direct-bill orders represent approximately $1M annually (~1% of revenue) and are the specific intersection where the tax-handling conflict applies. KBM REQ-013 documents the tax override capability as ALIGNS — "Tax override capability available. Not elegant but workable."

**Pivot's approach.** Pivot's BRD addresses tax through SuiteTax framework (covered in Financial Management §3.08); the BRD does not articulate the same MillerKnoll-policy-vs-final-destination conflict KBM names.

**Recommendation for the merged company.** Adopt the manual tax-override capability for government and MillerKnoll-direct-bill orders per KBM's framework. The merged company maintains the operational pattern KBM has used — escalation path documented; manual override applied per merged-company tax policy. The broader SuiteTax framework lives in Financial Management §3.08; this divergence flags the override-specific operational pattern. Communication with affected government customers about the tax-handling approach is part of the merged-company customer-relationship governance.

**Decision for the leadership team.** Confirm: manual tax-override capability for government and MillerKnoll-direct-bill orders adopted from KBM framework. *Recommended default: yes.* (Broader SuiteTax framework decided in Financial Management §3.08.)

---

### D-7. MillerKnoll integrations — ServiceNet, ServiceTime, Coupa, Quote Tool, Order Manager

**Source:** KBM REQ-039 through REQ-042 (`Requirements_Map_OrderManagement_v1.0.md`); Pivot Miller-Knoll Order Manager Integration section (`Order_Management.md:1097-1172`)

**KBM's approach.** KBM's source material articulates four MillerKnoll-related integrations: ServiceNet for intermarket orders (REQ-039); ServiceTime for high-volume intermarket order handling (~thousands annually, Shannon's primary workload at 8-10/day, REQ-041); Coupa email-parsing automation for order creation (REQ-040, evaluation pending based on ROI); the MillerKnoll Quote Tool at proposal and PO level (REQ-042). KBM identifies Shannon as a potential bottleneck risk for thousands of intermarket orders.

**Pivot's approach.** Pivot's BRD identifies MillerKnoll Order Manager as a primary integration with vendor splitting, acknowledgement processing, and transmission through appropriate channels (Pivot Miller-Knoll Order Manager Integration section). The integration framework addresses PO generation and vendor coordination but does not specifically articulate ServiceNet, ServiceTime, or Coupa.

**Recommendation for the merged company.** Combine the integration suite. ServiceNet, ServiceTime, MillerKnoll Quote Tool, and the broader MillerKnoll Order Manager integration are all configured for the merged company. Coupa email-parsing automation evaluation is preserved as a Phase-1-or-Phase-2 decision based on the merged-company's combined intermarket volume and ROI analysis. KBM staff (including Shannon) and Pivot order-processing staff jointly inherit the integrated MillerKnoll integration suite. Shannon's intermarket-order workload pattern is preserved through the same ServiceTime integration; merged-company role assignment for the high-volume intermarket position is part of the organizational alignment.

**Decisions for the leadership team.**

- (7a) Confirm: combined MillerKnoll integration suite (ServiceNet, ServiceTime, Quote Tool, Order Manager). *Recommended default: yes.*
- (7b) Confirm: Coupa email-parsing automation evaluation preserved as Phase-1-or-Phase-2 decision based on merged-company intermarket volume and ROI. *Recommended default: yes (evaluate during Realize).*

---

### D-8. Purchase order generation depth — direct PO from SIF, draft PO, mass updates, requisitions, line constitution

**Source:** Pivot Purchase Order Generation section (`Order_Management.md:989-1095`) — direct PO from SIF, draft PO with line constitution, mass PO updates, requisition workflow; KBM Gap Analysis (`GapAnalysis_OrderManagement_v1.1.md:41-50`) — draft PO concept identified as open input requiring follow-up session; KBM REQ-026 vendor credit limit warnings (`Requirements_Map_OrderManagement_v1.0.md`)

**KBM's approach.** KBM's gap analysis explicitly flags draft PO concept as a critical/high gap requiring a follow-up session — KBM has not articulated a draft PO workflow at depth. KBM addresses vendor credit limits via REQ-026 (warning threshold ~90%, prevent PO creation if over limit, with override).

**Pivot's approach.** Pivot's BRD articulates PO generation depth that addresses several merged-company needs:

- **Direct PO from SIF** (line 1027) — PO generation directly from SIF imports without requiring sales-order intermediation in cases where it is appropriate (e.g., showroom orders).
- **Draft PO with line constitution** (line 1011) — line constitution functionality defers transaction lines being constituted in order to enable PO editing and draft PO editing before finalization, supporting editing needed after receiving an acknowledgment.
- **Mass PO updates** (line 1011) — header information applied across unlimited POs simultaneously through a single form.
- **Requisition workflows** (line 998) — purchase requisition system for showroom and special approvals; built-in approval-routing for special purchases (e.g., showroom, corporate expenses) replacing email-based approvals.
- **Intelligent splitting rules** — automatic vendor / alias / custom-criteria splitting on PO generation.

**Recommendation for the merged company.** Adopt Pivot's PO generation depth as the merged-company default — direct PO from SIF, draft PO with line constitution, mass PO updates, and requisition workflows. KBM's draft PO gap is resolved by adopting Pivot's framework. KBM's vendor credit limit warning framework (REQ-026 — 90% warning, hard-stop with override) is integrated with the PO generation flow as a pre-creation check; vendor credit framework is owned in this section (Order Management) per CT-12, with cross-reference to Financial Management §3.08 D-9 for credit-policy governance.

**Decisions for the leadership team.**

- (8a) Confirm: Pivot's PO generation framework (direct PO from SIF, draft PO with line constitution, mass PO updates, requisition workflows, intelligent splitting). *Recommended default: yes.*
- (8b) Confirm: vendor credit limit warning framework adopted from KBM (REQ-026) integrated with PO generation flow; framework owned in Order Management per CT-12, governance cross-referenced to Financial Management §3.08 D-9. *Recommended default: yes.*

---

### D-9. Tiered pricing recognition at project level (FUTURE / escalation)

**Source:** KBM REQ-043 (`Requirements_Map_OrderManagement_v1.0.md`); not addressed in Pivot BRD

**KBM's approach.** KBM's source material flags a major future business issue: MillerKnoll's tiered-pricing program does not currently recognize project-level discount accumulation when orders are split across multiple vendor POs. The result is GP erosion on large multi-order projects, creating an installation-strategy-vs-pricing-optimization trade-off. KBM identifies an escalation path to Dustin Doucette (referenced in the source as the MillerKnoll product owner) to request project-number plus contract-number acceptance for tiered pricing.

**Pivot's approach.** Pivot's BRD does not address this issue at the requirements level.

**Recommendation for the merged company.** Carry KBM's escalation path forward as a merged-company business issue. The merged company's increased combined volume strengthens the case for MillerKnoll policy change. The escalation is owned by the merged-company commercial team in coordination with GSI's MillerKnoll relationship, with the goal of project-level tiered-pricing recognition for the merged company.

**Decision for the leadership team.** Confirm: escalation to MillerKnoll for project-level tiered-pricing recognition retained as a merged-company business issue with cross-organization commercial ownership. *Recommended default: yes.* (Resolution timing dependent on MillerKnoll response; not gating implementation.)

---

## 3.04.4 Cross-area dependencies

The following surfaced in Order Management discovery but are decided in other process areas. They are flagged here so the working session understands the connections; the decisions themselves live in their proper home area.

| Dependency | Where it surfaced in Order Management | Where it's decided |
|---|---|---|
| **Vendor credit limit tracking and alerts** | KBM REQ-026 vendor credit limit warnings at threshold; integrated with PO generation per D-8 | **Order Management (§3.04 D-8)** — framework owned here per CT-12; **Financial Management (§3.08 D-9)** — credit-policy governance cross-reference; **BI (§3.09)** — dashboard portlets surface warnings |
| **15% labor markup formula lines** | KBM REQ-038 | **Financial Management (§3.08 D-4)** — labor markup eliminated for the merged company |
| **Project GP vs. Commissionable GP** | KBM REQ-037 | **Financial Management (§3.08 D-5)** — dual GP framework operationalized; **CRM (§3.02 D-6)** — GP framework locked |
| **Pipeline stage model and forecasting** | Quote-to-Sales-Order conversion triggers | **CRM (§3.02 D-1)** — pipeline model is locked |
| **Multi-company / multi-contact relationship model** | Customer PO tracking with multiple companies on opportunity; vendor coordination | **CRM (§3.02 D-4)** — relationship model is locked |
| **RFP coordination workflow** | Pre-Quote-to-Order transitions for RFP-driven opportunities | **Marketing (§3.01 D-8)** — RFP coordination workflow lives there |
| **Specialized order-type taxonomy** | Combined taxonomy used by Order Management per D-3 | **Pre-Quote (§3.03 D-7)** — specialized order types decided there; Order Management uses them |
| **Tax management framework (SuiteTax, certificate management)** | Tax automation for orders | **Financial Management (§3.08)** — broader tax framework lives there |
| **Acknowledgements (vendor PO acknowledgements)** | Acknowledgements section in Pivot BRD; KBM REQ-039 ServiceNet acknowledgements | **Order Management (§3.04)** — acknowledgement framework owned here (PO acknowledgement processing, MillerKnoll Order Manager integration); **Operations (§3.05)** — acknowledgement-driven receiving / work-order operational handoff |
| **Document storage architecture** | Customer PO documents, signed proposals, drawings, lookbooks | **System Setup & Configuration (§3.10 D-3)** — CT-14 lock: File Cabinet for transactional documents (POs, invoices, signed proposals); SharePoint for collaboration documents; KBM Google Drive sunset |
| **Approval routing in Financial Management** | Bill-payment approval workflow integrates with order-approval framework | **Financial Management (§3.08 D-6)** — banking approval cross-reference |
| **PM rate cards and time tracking** | Budget locking at SO conversion (D-4c) feeds PM time tracking | **Project Management (§3.06 D-4)** — PM rate-card and time-tracking framework |

## 3.04.5 Recommendation summary

The merged-company Order Management playbook in shorthand:

- **Transaction structure:** Separate linked transactions (Opportunity → Proposal/Quote → Sales Order → DPO/VPO/Invoice) with project number as primary reference and KBM's transaction-prefix scheme (REQ-003)
- **Approval framework:** KBM's rule framework (specific thresholds, named-role approvers, up-to-10 rules, approval-time tracking, double-order detection) integrated with Pivot's margin-based and low-margin SVP rules within Orion workflow infrastructure; no separate SO approval beyond proposal approval (KBM REQ-010)
- **Customer PO tracking:** Custom record / transaction with project-level aggregation, KPI dashboard, threshold alerts (KBM framework); extended to address Pivot's named customer PO limit needs (Oracle, Apple, Google)
- **Order types:** Combined taxonomy decided in Pre-Quote §3.03 D-7; KBM's named types integrated; Order Management uses
- **Invoice schedule, deposit, and budget framework:** Pivot's framework — invoice schedule templates (50/40/10, 30/40/30, 100% prepay, custom; up to 5), quote-level deposits with automatic SO association, vendor pre-payments against draft POs, budget locking at SO conversion with time tracking
- **PDF Composer and template management:** Pivot's PDF Composer (10 templates with dynamic field selection — budgetary / formal / GSA / client-specific); KBM's self-service ownership and version control framework; vendor PO redesign as explicit deliverable
- **Client quote approval:** Pivot's web-based portal replacing Docentric email system
- **Tax overrides:** Manual override capability for government and MillerKnoll-direct-bill orders (KBM REQ-013)
- **MillerKnoll integrations:** Combined suite (ServiceNet, ServiceTime, Quote Tool, Order Manager); Coupa evaluation deferred to Realize-phase ROI analysis
- **PO generation depth:** Pivot's framework — direct PO from SIF, draft PO with line constitution, mass PO updates, requisition workflows, intelligent splitting; KBM's vendor credit limit warning integrated as pre-creation check
- **Tiered pricing escalation:** Retained as merged-company business issue with cross-organization commercial ownership (KBM REQ-043)
- **Commission:** Header-level with split-percentage (CRM-locked); line-level commissionable flag; storage fees always commissionable
- **SIF/BOM import:** Pivot's demonstrated 1,000-line / 10-second performance with Smart Table multi-grouping
- **Acknowledgements:** Owned in Order Management; operational handoff to Operations §3.05

Net read: the merged-company Order Management combines design choices that fit the merged-company's situation. KBM's contributions reflect its operational specifics — named approval thresholds, customer PO tracking framework, order-type taxonomy with volumes, self-service template ownership pattern, ServiceNet/ServiceTime/Coupa integration paths, vendor credit limit warning, tiered-pricing escalation, and the no-separate-SO-approval pattern (REQ-010). Pivot's contributions reflect its BRD depth on invoice / deposit / budget frameworks, PDF Composer with the 10-template inventory and dynamic field selection, web-based client quote approval replacing Docentric, PO generation depth (direct PO from SIF, draft PO with line constitution, mass updates, requisitions), customer PO limit needs for major accounts (Oracle, Apple, Google), and MillerKnoll Order Manager integration. Both companies' inputs land in the merged BRD; configuration combines them.

## 3.04.6 Decisions for the leadership team

| # | Decision | Default | Reference |
|---|---|---|---|
| 1a | KBM's approval-rule framework integrated within Orion workflow infrastructure that also supports Pivot's margin-based and low-margin SVP rules | Yes | D-1 |
| 1b | $25K, missing-requirements, $1,500 erosion thresholds; Pivot low-margin SVP and margin-based rules as merged-company working defaults | Yes | D-1 |
| 1c | Double-order detection query (same dollar amount within 30 days) | Yes | D-1 |
| 1d | No separate SO approval beyond proposal approval (KBM REQ-010); reapproval triggers configured during Realize | Yes | D-1 |
| 2 | Customer PO tracking framework adopted from KBM source; extended to address Pivot's customer PO limit needs (Oracle, Apple, Google) | Yes | D-2 |
| 3 | Combined order-type taxonomy decided in Pre-Quote §3.03 D-7; Order Management uses | Yes | D-3 |
| 4a | Pivot's invoice schedule template framework (50/40/10, 30/40/30, 100% prepay, custom; up to 5 standard templates) | Yes | D-4 |
| 4b | Quote-level deposits with auto-association on SO conversion; vendor pre-payments against draft POs | Yes | D-4 |
| 4c | Budget locking at SO conversion with time tracking against locked budget | Yes | D-4 |
| 5a | PDF Composer with the 10-template inventory and dynamic field selection (budgetary / formal / GSA / client-specific) | Yes | D-5 |
| 5b | Self-service template management with merged-company design ownership; template version control and change documentation | Yes | D-5 |
| 5c | Customer-facing and vendor-facing templates recreated via PDF Composer; vendor PO redesign as explicit deliverable | Yes | D-5 |
| 5d | Web-based client quote approval portal adopted, replacing Docentric email system | Yes | D-5 |
| 6 | Manual tax-override capability for government and MillerKnoll-direct-bill orders | Yes | D-6 |
| 7a | Combined MillerKnoll integration suite (ServiceNet, ServiceTime, Quote Tool, Order Manager) | Yes | D-7 |
| 7b | Coupa email-parsing automation evaluation preserved as Phase-1-or-Phase-2 decision | Yes (evaluate during Realize) | D-7 |
| 8a | Pivot's PO generation framework (direct PO from SIF, draft PO with line constitution, mass PO updates, requisition workflows, intelligent splitting) | Yes | D-8 |
| 8b | Vendor credit limit warning framework adopted from KBM (REQ-026); framework owned here per CT-12 | Yes | D-8 |
| 9 | MillerKnoll tiered-pricing escalation retained as merged-company business issue | Yes | D-9 |

> 19 decisions across 9 divergences, all with default-yes recommendations. Specific merged-company role assignments (Shannon and Matt Denning approver positions, Pivot SVP low-margin approver positions) and threshold values are operational decisions during configuration; framework confirmations occur at the working session.

## 3.04.7 Configuration carryover

| Item | KBM-side built? | Pivot-side built? | Action for merged company |
|---|---|---|---|
| Transaction structure (separate linked transactions) | Specified, in progress (REQ-001 through REQ-005) | In progress | Configure unified per common-ground items |
| Transaction prefixes (OP/PROP/SO/DPO/VPO/INV) | Specified (REQ-003) | Not specified | Apply per KBM framework |
| Approval rules (thresholds, approvers, up to 10 rules) | Specified (REQ-020 through REQ-024) | Workflow framework specified, not yet thresholds | Build per D-1 |
| No separate SO approval | Specified (REQ-010) | Implicit | Configure per D-1d |
| Customer PO tracking (custom record + KPI dashboard) | Specified (REQ-016 through REQ-018), design session pending | Customer PO limit need raised for Oracle / Apple / Google | Build per D-2 |
| Order types (Direct Bill, Intermarket, IWFH, Government, plus Pivot specialized) | Specified (REQ-031 through REQ-034) | Specified (specialized types in Pre-Quote BRD) | Build merged taxonomy per D-3; owner is Pre-Quote §3.03 D-7 |
| Invoice schedule templates (50/40/10, 30/40/30, 100% prepay) | Not specified | Specified | Build per D-4a |
| Quote-level deposits with auto-association on SO | Not specified | Specified (custom Quote Deposit functionality) | Build per D-4b |
| Vendor pre-payments against draft POs | Not specified | Specified | Build per D-4b |
| Budget locking at SO conversion | Not specified | Specified | Build per D-4c |
| Pro forma invoice (no GL impact) | Specified (KBM FM REQ-032) | Specified | Configure shared infrastructure |
| PDF Composer with 10 templates and dynamic field selection | Specified at framework level (Kipp self-service) | Specified at depth (10 templates, dynamic fields) | Build per D-5a |
| Self-service template ownership | Specified (Kipp pattern) | Not specified at the same level | Adopt Kipp-pattern ownership per D-5b |
| Customer-facing and vendor-facing templates recreated | Specified (REQ-029, REQ-030) | Implicit | Configure per D-5c; vendor PO redesign explicit |
| Web-based client quote approval portal (Docentric replacement) | Not specified | Specified | Build per D-5d |
| Tax-override capability (government, MK direct bill) | Specified (REQ-013) | Not articulated | Configure per D-6 |
| MillerKnoll integrations (ServiceNet, ServiceTime, Quote Tool, Order Manager) | Specified (REQ-039 through REQ-042) | Specified (Order Manager) | Build combined suite per D-7 |
| Coupa email-parsing automation | Evaluation pending (REQ-040) | Not specified | Defer per D-7b |
| Direct PO from SIF | Not specified | Specified | Build per D-8a |
| Draft PO with line constitution | Not specified (KBM gap-analysis open) | Specified | Build per D-8a |
| Mass PO updates | Not specified | Specified | Build per D-8a |
| Requisition workflows | Not specified | Specified (showroom and special-approval requisitions) | Build per D-8a |
| Intelligent PO splitting (vendor / alias / custom criteria) | Not specified | Specified | Build per D-8a |
| Vendor credit limit warnings (90% threshold, hard-stop with override) | Specified (REQ-026) | Not specified | Build per D-8b; owned in Order Management per CT-12 |
| Tiered pricing escalation to MillerKnoll | Specified (KBM REQ-043 FUTURE) | Not specified | Carry per D-9 |
| Double-order detection query | Specified (REQ-025) | Not specified | Build per D-1c |
| 15% labor markup formula lines | Specified (REQ-038) | Not present | Eliminate per Financial Management §3.08 D-4 |
| Storage fees always commissionable | Specified (REQ-015) | Not specified | Configure per common-ground |
| XML import with JSON conversion | Specified (REQ-007 ACCOMMODATE — Matt Denning to provide template) | Not specified | Build per common-ground (ACCOMMODATE) when KBM template provided |
| SIF performance (1,000 lines / ~10 seconds) | Implicit | Specified (Pivot demonstration) | Configure per common-ground; carry Pivot performance |
| Smart Table multi-grouping (PO vs. invoicing groupings) | Implicit (REQ-008) | Specified | Build per common-ground |

Configuration is in progress on both sides. The merged direction combines the two BRDs; vendor PO redesign, customer PO tracking detailed design, and several operational decisions remain.

## 3.04.8 Open questions / inputs needed

1. **Specific merged-company role assignments for approver positions** — currently Shannon ($25K) and Matt Denning (missing requirements, erosion) at KBM Hogue; SVP low-margin approver positions at Pivot; merged-company role assignments determined during organizational alignment.
2. **Customer PO tracking detailed design** (decision 2) — joint design session with Pivot's order-processing leads completed during Realize phase; Pivot's named accounts (Oracle, Apple, Google) used as test cases for blanket-PO-style consumption tracking.
3. **Order type naming convention** — particularly whether "Intuit Work from Home" remains as a merged-company order type name or is renamed; decided during configuration coordinated with Pre-Quote §3.03 D-7.
4. **Coupa email-parsing automation ROI analysis** (decision 7b) — merged-company combined intermarket volume analysis and ROI evaluation completed during Realize phase.
5. **MillerKnoll tiered-pricing escalation timing** (decision 9) — escalation sequencing with Dustin Doucette and MillerKnoll commercial team coordinated outside implementation timeline.
6. **Vendor PO redesign specifications** (decision 5c) — KBM's identified pain point (vendor PO content and organization require redesign per REQ-030); detailed redesign specifications collected during template recreation phase.
7. **XML import template** (KBM REQ-007 — ACCOMMODATE) — Matt Denning to provide template example; rare-use case.
8. **E-Portals discovery** (KBM gap analysis flag) — Coupa and other portal requirements explored during Realize phase.
9. **Quote-level deposit payment processing gateway** (decision 4b) — payment gateway decision finalized during Realize phase; Pivot's BRD calls this out as pending.
10. **Complete order type list** — KBM v1.1 gap analysis flags this as outstanding; merged-company complete order type list (combining KBM's named types and Pivot's specialized types) finalized during configuration with Pre-Quote.
11. **Quote versioning** — KBM v1.1 gap analysis identifies quote versioning as an open input; configuration approach (version field, version history, approval re-trigger on version change) decided during Realize.
12. **Sales order form fields** — KBM v1.1 gap analysis identifies additional SO form fields as an open input; specific field set finalized during configuration.
13. **Finance-charge capability** (KBM REQ-014) — finance-charge configuration cross-references Financial Management AR/collections framework; on/off setting and trigger conditions decided as part of merged-company AR governance.
14. **Deposit-management open detail items** (KBM Questionnaire `Questionnaire_OrderManagement_v1.1.md:354-358`) — deposit percentages, application process, milestone scenarios; resolved by adopting Pivot's framework per D-4 with specific configuration during Realize.
