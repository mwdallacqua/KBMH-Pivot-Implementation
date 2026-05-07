# Cross-Area Decisions Index

A single-source-of-truth index of decisions and capabilities that span more than one process area. Used to ensure consistency when sections are drafted in different sessions or by different authors.

**Maintenance rule:** When a section surfaces a dependency on another area, add a row here *before* moving on. When a section locks a decision that other sections will inherit, mark it locked here so downstream sections cite it correctly.

---

## How to read this file

- **Surface** — where the dependency was first identified
- **Decided in** — where the decision is owned (the "home" section)
- **Carries to** — every section that must reflect or cite the decision
- **Status** — Open / Locked / Deferred to working session
- **Working default** — the recommended position when a default is named

---

## Active threads

### CT-1. Division taxonomy (merged-company segment structure)

| Field | Value |
|---|---|
| Surface | CRM §3.02.3 D-3 |
| Decided in | CRM §3.02.3 D-3b |
| Carries to | Cross-Division Referrals (CRM D-7), Operations §3.05, Project Management §3.06, Commissions §3.07, Business Intelligence §3.09 (reporting cuts) |
| Status | **Open — confirm at working session** |
| Working default | Pivot's existing four divisions (Enterprise, Venture, Public, Construction Solutions). The working session can confirm, expand, or refine. |

When drafting downstream sections, refer to the divisional structure as "the merged-company division taxonomy (per CRM D-3b)" rather than restating the four. Avoid creating an apparent commitment in a later section that constrains the working-session decision.

---

### CT-2. Internal referral attribution (referring person captured on opportunity)

| Field | Value |
|---|---|
| Surface | CRM §3.02.3 D-3c |
| Decided in | CRM (capability built); Commissions §3.07 (compensation logic) |
| Carries to | Commissions §3.07 (compensation rules), Business Intelligence §3.09 (referral-source reporting) |
| Status | **Locked** (capability) — recommended default yes per CRM D-3c |
| Working default | Capture the referring person on the opportunity record |

Commissions §3.07 owns the compensation question (whether referrers receive credit, at what rate, on what events). BI §3.09 inherits the referral-source dimension for reporting.

---

### CT-3. HubSpot retention and integration

| Field | Value |
|---|---|
| Surface | CRM §3.02.3 D-10 (deferred); CRM §3.02.4 (cross-area dependencies table) |
| Decided in | Marketing §3.01 D-1 |
| Carries to | CRM §3.02 (lead sync), Business Intelligence §3.09 (campaign attribution), System Setup §3.10 (integration architecture and field mapping) |
| Status | **Locked** at Marketing §3.01 D-1 — recommended default yes |
| Working default | HubSpot retained as the merged-company marketing platform with bi-directional integration to NetSuite Orion. NetSuite is the system of record for the unified customer database, opportunity and revenue data, and campaign ROI attribution. Specific field mappings, sync triggers, source-of-truth rules per object, and error handling finalized during the technical design phase. |

Marketing §3.01 D-1 owns the platform retention decision and the integration architecture. The working default updated from "one-directional Orion → HubSpot, sunset CRM/forecasting role" (initial CRM-area working default) to "bi-directional integration with NetSuite as system of record" after Marketing-area review. Pivot's existing HubSpot proficiency and the merged-company scale of marketing operations support the platform retention.

---

### CT-4. Approval workflow specifics ($25K orders, document approvals, erosion approvals, low-margin SVP approvals)

| Field | Value |
|---|---|
| Surface | CRM §3.02.3 D-6 (erosion threshold $1,500 working default); CRM §3.02.4 (cross-area dependencies) |
| Decided in | Order Management §3.04 |
| Carries to | CRM §3.02 (erosion approval routing), Financial Management §3.08 (approval governance) |
| Status | **Deferred to Order Management §3.04** |
| Working default | KBM's framework as the structural starting point: $25K orders to a Project Coordinator role, missing-document approvals to executive review, erosion >$1,500 to executive review (KBM's coaching philosophy carried), Pivot's low-margin SVP approval pattern integrated. Specific role assignments confirmed during configuration with both leadership teams. |

CRM does not lock the routing of approvals. The merged-company role assignments are an Order Management decision that may also touch Financial Management.

---

### CT-5. Vendor credit limits and PO blocks

| Field | Value |
|---|---|
| Surface | CRM §3.02.4 (cross-area dependencies) |
| Decided in | **Order Management §3.04 D-8b** — vendor credit limit warning framework owned here as a procurement control integrated with the PO generation flow |
| Carries to | Financial Management §3.08 D-9 (credit-policy governance cross-reference); BI §3.09 (dashboard portlets surface warnings) per CT-12 |
| Status | **Resolved** — owned in Order Management per CT-12 |
| Working default | KBM's framework adopted as merged-company default: vendor credit limit field, 90% warning threshold, hard-stop on PO creation when over limit (with override), proactive dashboard visibility |

KBM articulated this; Pivot did not raise it. The capability is valuable for the merged company. The framework is owned in Order Management as a procurement control integrated with PO generation; Financial Management cross-references for credit-policy governance.

---

### CT-6. CRM data migration approach (Zendesk, Core, HubSpot extracts and consolidation)

| Field | Value |
|---|---|
| Surface | CRM §3.02.4 (cross-area dependencies) |
| Decided in | System Setup & Configuration §3.10 |
| Carries to | CRM §3.02 (data migration timing, deduplication, classification) |
| Status | **Deferred to System Setup §3.10** |
| Working default | Migrate Zendesk and Core extracts (KBM-side) and HubSpot extract (Pivot-side); deduplicate during migration; classify contacts by role, sector, and territory during import |

CRM §3.02.7 lists the carryover items that depend on this; System Setup §3.10 owns the consolidated migration plan.

---

### CT-7. Sales Goals dashboard (KBM's Excel-replacement requirement)

| Field | Value |
|---|---|
| Surface | CRM §3.02.3 D-9 |
| Decided in | CRM §3.02.3 D-9 (recommendation: satisfied by 2.5x pipeline multiplier dashboard) |
| Carries to | Business Intelligence §3.09 (dashboard governance) |
| Status | **Locked** — recommended default yes per CRM D-9a |
| Working default | The 2.5x multiplier dashboard provides the goal-vs-pipeline visibility KBM was asking for; no separate Sales Goals dashboard needed |

BI §3.09 inherits the multiplier dashboard as the goal-tracking artifact, not a Sales Goals dashboard built separately.

---

### CT-8. RFP mechanics — task/resource assignment and project/folder creation timing

| Field | Value |
|---|---|
| Surface | CRM §3.02.3 D-8 (recommendation defers); Pivot Feb 2026 BRD review session |
| Decided in | Pre-Quote §3.03 and/or Operations §3.05 |
| Carries to | CRM §3.02 (RFP opportunity type config) |
| Status | **Deferred to Pre-Quote §3.03 and Operations §3.05** |
| Working default | TBD — Pivot's transcript raised these as open at v2 review; no working default assumed |

CRM has the RFP opportunity type and Kanban board landed; the pre-quote / operations sequencing is downstream.

---

### CT-9. Outlook SuperSync (email-to-record logging)

| Field | Value |
|---|---|
| Surface | CRM §3.02.2 (alignment); CRM §3.02.3 D-2b |
| Decided in | CRM §3.02.3 D-2b (capability adopted) |
| Carries to | All sections where email-to-record logging is relevant (Order Management for vendor communications, Operations for delivery coordination, etc.) |
| Status | **Locked** — capability adopted per CRM D-2b |
| Working default | First email in a thread logged manually to the record; subsequent thread messages auto-log |

This is a CRM-locked capability that downstream sections can assume is in place when they discuss email logging.

---

### CT-10. Pipeline model (4-stage weighted)

| Field | Value |
|---|---|
| Surface | CRM §3.02.3 D-1 |
| Decided in | CRM §3.02.3 D-1 |
| Carries to | Business Intelligence §3.09 (pipeline reporting structure), Financial Management §3.08 (forecast feed) |
| Status | **Locked** — recommended default yes |
| Working default | 4-stage pipeline (Analysis 25%, Qualified 50%, Quote 80%, Closing 95%, Win/Loss); Commit Forecast view filtering to Quote+ stages |

BI dashboards and Financial reporting build on this model.

---

### CT-11. Multi-company / multi-contact relationship model

| Field | Value |
|---|---|
| Surface | CRM §3.02.3 D-4 |
| Decided in | CRM §3.02.3 D-4 |
| Carries to | Order Management §3.04 (alt bill-to / ship-to per opportunity), Operations §3.05 (delivery / installation contact attribution), Financial Management §3.08 (intermarket billing) |
| Status | **Locked** — recommended default yes |
| Working default | Multi-company per opportunity with primary/secondary designation; multi-contact with role taxonomy; soft reminders for missing influencer roles |

Downstream order/delivery/billing sections inherit this relationship model and reference it rather than re-litigating.

---

### CT-12. Vendor credit dashboard visibility

| Field | Value |
|---|---|
| Surface | BI §3.09.4 (cross-area dependencies) |
| Decided in | Order Management §3.04 (vendor credit framework) |
| Carries to | BI §3.09 (dashboard portlets surfacing vendor credit warnings and proactive monitoring) |
| Status | **Deferred to Order Management §3.04** |
| Working default | Vendor credit limit framework adopted from KBM (per CT-5); BI surfaces warning portlets for vendors approaching the 90% threshold and large-dollar payment authorization context |

This is a downstream dependency from CT-5. BI surfaces the dashboards; the credit framework itself is decided in Order Management or Financial Management.

---

### CT-13. Historical data migration supporting BI and predictive analytics

| Field | Value |
|---|---|
| Surface | BI §3.09 (predictive analytics, historical reporting); Pivot BRD assumptions §5; KBM BRD on Zendesk and Core extracts |
| Decided in | System Setup & Configuration §3.10 |
| Carries to | BI §3.09 (depth of historical data available for trend analysis, period-over-period comparisons, predictive analytics model training) |
| Status | **Deferred to System Setup §3.10** |
| Working default | Historical data migration scope and depth determined during data-migration planning. Pivot's BRD assumes D365 historical data is migrated to support historical reporting and predictive analytics; KBM's BRD assumes Zendesk and Core history is migrated with deduplication. |

The merged-company predictive analytics capability (BI D-7) depends on the depth of historical data migrated. BI flags the dependency; System Setup owns the scope and execution decision.

---

### CT-14. Document storage architecture and existing document migration

| Field | Value |
|---|---|
| Surface | BI §3.09 D-5 (document management); System Setup §3.10 D-3 (collaboration platform decision) |
| Decided in | System Setup & Configuration §3.10 D-3 |
| Carries to | Marketing §3.01, BI §3.09, Operations §3.05, Project Management §3.06, Financial Management §3.08 (any section storing project, customer, vendor, or transactional documents) |
| Status | **Locked** — recommended default yes per System Setup §3.10 D-3 |
| Working default | NetSuite File Cabinet is the merged-company primary repository for transactional documents (invoices, POs, contracts, signed proposals). SharePoint is the merged-company collaboration-document platform for project, design, and operational documents that benefit from external collaboration. KBM's Google Drive content migrates to SharePoint on a defined transition timeline; the Google Drive integration is sunset once migration completes. Existing project, customer, and vendor documents in Pivot's SharePoint, network drives, email attachments, and local storage are consolidated into the merged-company SharePoint footprint or migrated to NetSuite File Cabinet based on document type. KBM users onboard into SharePoint as part of the Discovery → Activate transition. Version control applies prospectively; historical versions may not be preserved per Pivot BRD assumption. |

Document management capability (BI D-5, Marketing references, Project Management documentation) is foundational; the merged-company architecture is locked at System Setup §3.10 D-3 with SharePoint as the collaboration platform and NetSuite File Cabinet as the transactional-document repository.

---

### CT-15. Sales rep and manager scorecards (composition decision)

| Field | Value |
|---|---|
| Surface | BI §3.09 D-9 |
| Decided in | BI §3.09 D-9 |
| Carries to | CRM §3.02 (scorecard incorporates 2.5x multiplier from CRM D-9 as one component); System Setup §3.10 (manager hierarchy enables "me and my team" scorecard view) |
| Status | **Locked** — recommended default yes per BI D-9 |
| Working default | Sales rep and manager scorecards built as a BI dashboard component combining KBM's metric structure (revenue, GP, YTD, period comparison, pipeline value, deals closed) with the CRM-locked 2.5x pipeline multiplier as one of the components. Individual view uses rep-level "owned opportunities" filter (CRM D-5); manager view uses "me and my team" via employee hierarchy (System Setup §3.10). |

The scorecard composition is a BI decision. The metric inputs come from CRM-locked decisions (multiplier, visibility model) and System Setup (hierarchy).

---

### CT-16. Workfront sunset and project-management platform consolidation

| Field | Value |
|---|---|
| Surface | Project Management §3.06 D-1 |
| Decided in | Project Management §3.06 D-1 |
| Carries to | Operations §3.05 (time tracking against project tasks; resource utilization), BI §3.09 (project-status dashboards now reside in Orion), System Setup & Configuration §3.10 D-5 (Workfront historical data migration scope and timing), Pre-Quote §3.03 (IPM routing executes against the Orion project record) |
| Status | **Locked** — recommended default yes per Project Management §3.06 D-1 |
| Working default | Project management consolidates into NetSuite Orion's native project record framework, augmented with custom enhancements for task management, resource allocation, dependency tracking, and capacity planning. Workfront is sunset on a defined transition timeline. Pivot's PM team migrates to Orion-native execution; KBM's PMs onboard into the same consolidated environment. The merged-company decision at the working session is **transition shape** — capability-replacement scope at cutover (which Workfront features must be present in Orion at go-live vs. phased afterward) and Workfront sunset timeline — not platform choice. The transition plan front-loads the capabilities Pivot's PM team relies on most heavily and protects PM productivity through cutover. |

Workfront retention is not on the table; the source-backed direction (Pivot's Project Management BRD specifies Orion replaces Workfront) is committed. Downstream sections cite Project Management §3.06 D-1 as the home for the platform decision and System Setup §3.10 D-5 for the historical data-migration plan.

---

## Adding new threads

When a section drafts surfaces a new cross-area dependency, append a `CT-N` entry below following the same shape. Increment N. Do not reuse retired numbers.

When a thread closes (decision locked in its home section, no further dependency), update the **Status** to **Locked** with a date. Do not delete the thread — it remains a citation reference for downstream sections.

---

*Last updated: May 7, 2026 — promoted to deliverable as `11 - Cross-Area Decisions Index.md`; CT-3 (HubSpot bi-directional integration) and CT-14 (SharePoint as collaboration platform with Google Drive sunset) updated to locked status; CT-16 (Workfront sunset to Orion-native project execution) added.*
