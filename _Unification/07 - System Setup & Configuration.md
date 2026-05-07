# 3.10 — System Setup & Configuration

| Field | Value |
|---|---|
| **Decision density** | **Low-Medium** — foundation-level decisions tied to other areas; governance, integrations, migration scope, identity infrastructure, and document management |
| **Source coverage** | KBM System Setup BRD v1.0 (REQ-001 through REQ-020+ across 8 sections — governance, discovery, system configuration, data migration, integrations) + Pivot System Setup & Configuration BRD v2.0 (REQ-3.01 through REQ-3.12 covering subsidiary structure, multi-currency, role-based security, item master, location/warehouse setup, system preferences, transaction numbering, taxes, integration architecture, data migration, document management) |
| **KBM BRD** | `System Setup and Configuration/KBMH/3 Output/BRD_SystemSetupConfiguration_v1.0.md` |
| **Pivot BRD** | `System Setup and Configuration/Pivot/4 BRD/01_Pivot Interiors BRD Setup & Configuration Process Area_v2.0.docx` (markdown copy at `_Unification/working/pivot-brds-md/System_Setup_and_Configuration.md`) |

---

## 3.10.1 How each company approaches System Setup today

**KBM Hogue** approaches System Setup as the implementation-governance and configuration-foundation layer for the merged-company project. Its BRD articulates dual executive sponsorship (Sean Scanlon at GSI; Matt Denning at the merged company per REQ-001), program-management leadership (Lorraine Guzman as Program Manager per REQ-002), change-management leadership (Kimmy Katsuyoshi as Change Management Lead per REQ-003), functional workstream leads from department SMEs (REQ-004), and the DREAM methodology framework (REQ-005). The BRD covers Orion Suite App installation (5 apps), 25+ custom Orion roles with deactivation of standard NetSuite roles (REQ-010), soft-cutover transition strategy, and the structured 8-process-area BRD framework. KBM's BRD also articulates Teams collaboration / status / change control requirements (BRD §3-§4), transaction numbering and saved-search configuration (BRD §6), MillerKnoll Exemplis manufacturer integration (REQ-020), and historical data migration back to 2017 baseline.

**Pivot Interiors** approaches System Setup as the platform-foundation layer for migration from D365 and HubSpot into NetSuite Orion. Its BRD covers (across §3.01 through §3.12): subsidiary structure, multi-currency, role-based security, item master and SIF, location and warehouse setup, system preferences, transaction numbering and saved-search configuration, taxes, integration architecture (HubSpot post-go-live integration consideration; Comerica banking per Financial Management §3.08 D-6; UKG payroll per Financial Management §3.08), data migration with Levels 1 / 2 / 3A staged approach, and document management. Pivot's data migration assumptions: Pivot will not bring open orders into Orion (`pivot-brds-md/System_Setup_and_Configuration.md:1226-1230`); D365 remains read-only post-go-live for historical reference (REQ-3.11.07 / `:1266-1270`). Pivot's document-management current state is fragmented across IQ (receiving), Workfront (project documents), and likely file shares (`:1280-1287, :1291-1297`); SharePoint is the target consolidation platform via REQ-1.12.01 through REQ-1.12.08, not the current state.

Both companies share the same end-state goals: a single NetSuite Orion environment configured for the merged-company operating model, integrated with the platforms that remain (HubSpot for marketing, banking partners, payroll providers, document management), with role-based access supporting the merged-company organizational structure. Where they differ is largely in starting-state context (KBM coming from NetSuite Core; Pivot coming from D365 + HubSpot + multiple specialty platforms including IQ Coordinator and Workfront), in the breadth of integration architecture, and in the migration posture (KBM soft cutover supporting open work in legacy; Pivot no-open-order migration with D365 read-only post-cutover).

## 3.10.2 Where the two companies align

**Explicit in both BRDs:**

- Single NetSuite Orion environment configured for the merged-company operating model
- Custom Orion roles supporting the merged-company organizational structure
- Standard Orion Suite App installation
- Document migration to NetSuite File Cabinet and / or integrated document storage
- Pre-migration data cleansing process (KBM source materials; Pivot REQ-3.11.05 dedupe / standardize)
- Reconciliation reports and validation scripts for migrated data accuracy (Pivot REQ-3.11.06)

**KBM-explicit; standard capability carried forward:**

- DREAM methodology framework (Discovery → Realize → Educate → Activate / Naturalize → Maintain) per KBM REQ-005
- Dual executive sponsorship per KBM REQ-001 (Sean Scanlon at GSI; Matt Denning at the merged company)
- Named Program Manager per KBM REQ-002 (Lorraine Guzman); named Change Management Lead per KBM REQ-003 (Kimmy Katsuyoshi); functional workstream leads from department SMEs per KBM REQ-004
- Soft-cutover transition strategy (new business in NetSuite while completing legacy work in original systems)
- 6-8 week Discovery phase with validation focus
- 1.5-2 hour discovery sessions with two-part format (capability overview + requirements analysis)
- Teams collaboration / status / change control requirements (KBM BRD §3-§4)
- Transaction numbering and saved-search configuration (KBM BRD §6)
- MillerKnoll Exemplis manufacturer integration (KBM REQ-020)

**Pivot-explicit; standard capability carried forward:**

- Multi-Design-Center configuration supporting Pivot's existing California locations (Santa Clara, Fremont, San Francisco, Costa Mesa, Los Angeles, La Mirada) + KBM's California territories
- Multi-currency framework per Pivot subsidiary structure
- Item master and SIF configuration
- Location and warehouse setup configuration (Pivot §3.05 — supports D-4)
- System preferences configuration (Pivot §3.06)
- Transaction numbering and saved-search configuration (Pivot §3.07)
- Pre-migration data cleansing (REQ-3.11.05) and reconciliation validation (REQ-3.11.06)
- D365 read-only access maintained post-go-live for historical reference (REQ-3.11.07)
- Native NetSuite SharePoint connector integration (Pivot REQ-1.12.01 through REQ-1.12.08 — folder structure aligned to customer / project / document type, role-based access, automated folder creation, version control, document templates auto-saving to SharePoint)

These are noted in the merged BRD; configuration proceeds against standard NetSuite Orion implementation patterns and the DREAM methodology.

## 3.10.3 Where the two companies differ

Six in-area divergences.

---

### D-1. Project governance and program management roles

**Source:** KBM REQ-001 through REQ-005 (`BRD_SystemSetupConfiguration_v1.0.md:35-50`); Pivot Project Overview / governance sections — Pivot's BRD addresses governance via the standard DREAM methodology framework but does not name specific role assignments at the same level

**KBM's approach.** KBM's BRD articulates dual executive sponsorship (Sean Scanlon at GSI; Matt Denning at KBM Hogue per REQ-001), Lorraine Guzman as Program Manager (REQ-002), Kimmy Katsuyoshi as Change Management Lead (REQ-003), functional workstream leads from department SMEs (REQ-004), and the DREAM methodology framework (REQ-005).

**Pivot's approach.** Pivot's BRD addresses governance through the standard DREAM methodology framework but does not name specific role assignments at the same level KBM does.

**Recommendation for the merged company.** Adopt KBM's named-role governance framework as the merged-company default, with Pivot leadership additions: Sean Scanlon as GSI executive sponsor; Matt Denning as merged-company executive sponsor; merged-company Program Manager and Change Management Lead determined during organizational alignment with both leadership teams' input. Functional workstream leads include both KBM and Pivot department SMEs for each process area.

**Decision for the leadership team.** Confirm: named-role governance framework with merged-company assignments determined during organizational alignment. *Recommended default: yes.*

---

### D-2. Migration sequencing and posture — KBM soft cutover vs. Pivot no-open-order migration

**Source:** KBM BRD §4 Data Migration Strategy (`BRD_SystemSetupConfiguration_v1.0.md:563-580` — soft cutover with 6-month parallel completion of in-flight work in legacy Core); Pivot BRD §3.11 Data Migration (`pivot-brds-md/System_Setup_and_Configuration.md:1226-1230` — Pivot won't bring open orders into Orion; `:1266-1270` — D365 remains accessible read-only post-go-live for historical reference per REQ-3.11.07)

**KBM's approach.** KBM's BRD articulates a soft-cutover approach: new business starts in NetSuite while existing projects complete in legacy Core over approximately 6 months.

**Pivot's approach.** Pivot's BRD articulates a different posture: open orders will not be brought into Orion (`:1226-1230`); D365 remains accessible read-only post-go-live for historical reference (REQ-3.11.07 / `:1266-1270`); Pivot's intent (per Operations Assumption §3.03) is to run all D365 orders through IQ until September and manually recreate in Orion. Levels 1 (entities and financial history), 2 (sales order history), 3A (AP / AR) migrate; Level 3 (open orders and POs) decision is pending based on complexity and cost — Pivot is opting against bringing open orders forward.

**Recommendation for the merged company.** Operate the merged company with both legacy-system postures supported. KBM Hogue follows soft-cutover: new business in Orion while in-flight Core work completes there or migrates as scope permits. Pivot follows the no-open-order migration posture: new business and migrated active records in Orion; D365 remains read-only for historical reference per REQ-3.11.07; open orders complete in IQ / D365 / Workfront through the agreed run-out window before transitioning to Orion. The merged company manages the dual posture during the cutover window and standardizes on Orion as soon as both legacy systems' run-out completes. Process-area cutover sequencing is finalized during implementation timeline confirmation.

**Decisions for the leadership team.**

- (2a) Confirm: KBM soft-cutover posture (new business in Orion; in-flight Core work completes there or migrates as scope permits) for the KBM Hogue side. *Recommended default: yes.*
- (2b) Confirm: Pivot no-open-order migration posture (new business in Orion; D365 read-only post-go-live per REQ-3.11.07; open orders complete in IQ / D365 / Workfront through agreed run-out before standardizing on Orion). *Recommended default: yes.*
- (2c) Confirm: process-area cutover sequencing determined during implementation planning. *Recommended default: yes.*

---

### D-3. Document management and storage architecture

**Source:** KBM Google Drive integration (Marketing §3.01); Pivot BRD §3.12 Document Management REQ-1.12.01 through REQ-1.12.08 (`pivot-brds-md/System_Setup_and_Configuration.md:1280-1287`) — SharePoint as target consolidation platform; Pivot current state fragmented across IQ / Workfront / file shares (`:1291-1297`); cross-references CT-14

**KBM's approach.** KBM's existing document collaboration uses Google Drive, integrated with NetSuite via the Google Drive connector for opportunity, project, and RFP documents. KBM has named Google Drive sunset and migration to SharePoint as the merged-company collaboration platform per CT-14.

**Pivot's approach.** Pivot's current document management is fragmented across IQ Coordinator (receiving documents), Workfront (project documents and tasks), and likely file shares (per Pivot BRD §3.12.02 / `:1291-1297`). Pivot's stated current-state pain is that "fragmentation creates challenges finding correct document versions and ensuring team access to current information." Workfront expires July 2026 creating a hard deadline for document migration. SharePoint is the **target** consolidation platform via Pivot REQ-1.12.01 through REQ-1.12.08 (centralized SharePoint integration; folder structure aligned to customer and project hierarchy; document access from NetSuite customer / project / transaction records; replace IQ and Workfront document storage by consolidating to SharePoint; role-based access; automated folder creation; version control; document templates auto-saving to SharePoint).

**Recommendation for the merged company.** Operate the merged company with NetSuite File Cabinet as the primary document repository for transactional documents (invoices, POs, contracts, signed proposals, financial records) and SharePoint as the merged-company collaboration-document platform per CT-14. The recommendation aligns with Pivot's existing target architecture (SharePoint connector integration via REQ-1.12.01 through REQ-1.12.08) and resolves both companies' fragmentation:

- **KBM Google Drive content** migrates to SharePoint on a defined transition timeline; the Google Drive integration sunsets once migration completes
- **Pivot fragmented sources** (IQ Coordinator receiving documents, Workfront project documents, file shares, email attachments, local storage) consolidate to SharePoint and File Cabinet by document type during the IQ / Workfront sunset
- **Folder structure** follows Pivot REQ-1.12.02 — customer / project / document-type hierarchy with folder-naming conventions decided during configuration
- **Automated folder creation** at lead, opportunity, and project stages per Pivot REQ-1.12.06
- **Role-based access** aligned with NetSuite user roles per Pivot REQ-1.12.05
- **Document templates** for quotes, orders, and invoices auto-save to SharePoint per Pivot REQ-1.12.08

KBM users onboard into SharePoint as part of the Discovery → Activate transition. Workfront's July 2026 expiration creates the hard deadline for Pivot-side document migration.

**Decisions for the leadership team.**

- (3a) Confirm: NetSuite File Cabinet as primary repository for transactional documents (invoices, POs, contracts, signed proposals, financial records). *Recommended default: yes.*
- (3b) Confirm: SharePoint as merged-company collaboration-document platform per Pivot REQ-1.12.01 through REQ-1.12.08. *Recommended default: yes.*
- (3c) Confirm: KBM Google Drive content migrates to SharePoint on a defined transition timeline; Pivot fragmented document sources (IQ, Workfront, file shares, email, local storage) consolidate to SharePoint and File Cabinet by document type during IQ / Workfront sunset. *Recommended default: yes.*

---

### D-4. Identity and access management — merged-company role taxonomy

**Source:** KBM REQ-010 (`BRD_SystemSetupConfiguration_v1.0.md:146` — 25+ custom Orion roles; deactivate standard NetSuite roles); Pivot role-based security configuration (Pivot BRD §3.03)

**KBM's approach.** KBM's BRD specifies 25+ custom Orion roles deactivating standard NetSuite roles to reduce confusion (REQ-010).

**Pivot's approach.** Pivot's BRD articulates role-based access aligned with its divisional sales structure (per CRM §3.02 D-3b — final merged-company division taxonomy decided at the working session) and its in-house operations footprint.

**Recommendation for the merged company.** Adopt the standard Orion 25+ custom role taxonomy with merged-company adaptations (KBM REQ-010): roles support both Pivot's divisional structure and KBM's geographic territories per the two-dimensional model locked in CRM §3.02 D-3a. Sales Locations per geography taxonomy are **configured here** in System Setup; the geographic dimension and division taxonomy are **decided in CRM §3.02 D-3a / D-3b**. Operations-specific roles reflect Pivot's primarily-internal operations team plus KBM's outsourced-operations coordination roles (per Operations §3.05).

**Decision for the leadership team.** Confirm: standard Orion 25+ custom role taxonomy adapted for the merged-company operating model; Sales Locations and division-based role configuration align with CRM §3.02 D-3a / D-3b decisions. *Recommended default: yes.* (Specific role configurations finalized during configuration; CRM §3.02 owns the model decision, System Setup configures.)

---

### D-5. Historical data migration scope — combined Workfront, D365, Core, Zendesk, HubSpot, archive, and document migration

**Source:** KBM REQ-017 (Financial Management — 2017 historical baseline); Pivot REQ-3.11.01 through REQ-3.11.07 (`pivot-brds-md/System_Setup_and_Configuration.md:1226-1274`); cross-references CT-6 (CRM data migration approach), CT-13 (BI predictive analytics dependency), CT-16 (Workfront sunset and project / task / time / capacity migration), Financial Management §3.08.8 #8

**KBM's approach.** KBM's source materials reference historical data migration back to 2017 for KBM Financial Management trend analysis (Financial Management REQ-017), Zendesk and Core extracts for CRM with deduplication and classification by role / sector / territory per CT-6, and KBM archive system for pre-2017 records and post-migration Core lookups.

**Pivot's approach.** Pivot's BRD §3.11 articulates staged migration:

- **Level 1** — entities (customers, vendors, items) and financial history
- **Level 2** — sales order history (no open orders per `:1226-1230`)
- **Level 3A** — AP / AR
- **Level 3** — open orders and POs *not migrated* (Pivot opts against per `:1230`)
- **REQ-3.11.04** — 2-5 years of historical financial trial balances via journal entry import
- **REQ-3.11.05** — pre-migration data cleansing (dedupe, standardize)
- **REQ-3.11.06** — reconciliation reports and validation scripts
- **REQ-3.11.07** — D365 remains accessible read-only post-go-live for historical reference

Pivot's BRD assumes historical data is migrated to support historical reporting and predictive analytics.

**Recommendation for the merged company.** Combine the migration scope:

- **KBM Financial Management** — 2017 historical baseline trial balances per KBM REQ-017
- **Pivot Financial Management** — 2-5 years of historical trial balances per Pivot REQ-3.11.04
- **CRM data migration** — Zendesk and Core extracts (KBM) plus HubSpot extract (Pivot) consolidated per CT-6 with deduplication and classification by role / sector / territory
- **Operational history** — KBM Core sales order history; Pivot D365 sales order history (Level 2 — closed orders only; no open orders per Pivot `:1230`)
- **AP / AR** — Pivot Level 3A; KBM equivalent
- **Workfront historical data** — project, task, time, and capacity data migration per CT-16 / Project Management §3.06 D-1
- **Document migration** — KBM Google Drive content to SharePoint per CT-14; Pivot fragmented document sources (IQ, Workfront, file shares) to SharePoint and File Cabinet by document type per CT-14 / D-3
- **Archive systems** — KBM archive system for pre-2017 records and post-migration Core lookups maintained; Pivot D365 read-only access per REQ-3.11.07 maintained
- **Pre-migration data cleansing** — dedupe, standardize per Pivot REQ-3.11.05; reconciliation validation per REQ-3.11.06

The specific cutover-back date and per-stream depth are determined during data-migration planning with finance, BI, and process-area leadership input.

**Decision for the leadership team.** Confirm: combined historical data migration scope covering Workfront (per CT-16), D365 (Levels 1 / 2 / 3A; no open orders; D365 read-only post-go-live per Pivot REQ-3.11.07), KBM Core (with archive system maintained for pre-2017 records and post-migration lookups), Zendesk, HubSpot, and document migration per CT-14; pre-migration data cleansing and reconciliation per Pivot REQ-3.11.05 / REQ-3.11.06. *Recommended default: yes.* (Specific date back-cutoff and per-stream depth finalized during data-migration planning.)

---

### D-6. Integration architecture — confirmed integrations vs. evaluation / licensing

**Source:** Cross-references multiple sections — HubSpot (Marketing §3.01 D-1), banking (Financial Management §3.08 D-6), payroll (Financial Management §3.08.8 #9), MillerKnoll integrations (Order Management §3.04 D-7), expense platform (Financial Management §3.08 D-7), KBM REQ-020 Exemplis manufacturer integration (`BRD_SystemSetupConfiguration_v1.0.md:296`); Pivot integration sections; KBM `BRD_SystemSetupConfiguration_v1.0.md:313-328, 381-385` for KBM-side pending items

**KBM's approach.** KBM's source materials specify integration patterns for ServiceNet, ServiceTime, Coupa (evaluation pending), MillerKnoll Quote Tool, MillerKnoll Exemplis manufacturer integration (REQ-020), Stripe, Paylocity (with merged-company payroll provider decision pending), West Coast Community Bank, Google Drive (sunsetting per CT-14), Expensify (KBM-side; merged-company expense platform decision pending per Financial Management §3.08 D-7), and additional manufacturer expansion.

**Pivot's approach.** Pivot's source materials specify HubSpot bi-directional sync (Marketing §3.01 D-1 / CT-3), Comerica banking, UKG payroll (with merged-company payroll provider decision pending), MillerKnoll Order Manager, SharePoint native connector (Pivot REQ-1.12.01 through REQ-1.12.08; CT-14), ZoomInfo (evaluation pending; cross-reference Marketing §3.01 D-9), and SuiteAnalytics Connect (per BI §3.09 D-7b).

**Recommendation for the merged company.** Split the integration architecture into two classes:

**Confirmed integrations** (locked in their owning sections; configured here):

- HubSpot bi-directional sync — owned in Marketing §3.01 D-1 / CT-3
- Banking — West Coast Community Bank (KBM) and Comerica (Pivot) — owned in Financial Management §3.08 D-6
- MillerKnoll Order Manager, Quote Tool, ServiceNet, ServiceTime — owned in Order Management §3.04 D-7; Coupa email-parsing automation evaluation deferred to Realize per Order Management §3.04 D-7b
- MillerKnoll Exemplis manufacturer integration — KBM REQ-020
- SharePoint via NetSuite native SharePoint connector — owned in System Setup §3.10 D-3 / Pivot REQ-1.12.01 through REQ-1.12.08 / CT-14
- SuiteAnalytics Connect — licensed per BI §3.09 D-7b decision (technical setup here if licensed)
- Stripe — KBM-side payment processing

**Evaluation / licensing decisions pending:**

- Merged-company payroll provider (Paylocity vs. UKG vs. other) — Financial Management §3.08.8 #9
- Merged-company expense platform (Expensify vs. NetSuite native) — Financial Management §3.08 D-7
- ZoomInfo evaluation — Marketing §3.01 D-9
- Manufacturer integration expansion beyond MillerKnoll Exemplis — KBM-side pending items per `BRD_SystemSetupConfiguration_v1.0.md:381-385`

NetSuite Orion is the system of record for the unified customer database, opportunity and revenue data, and project records; integrated platforms (HubSpot for marketing, banking platforms, payroll providers, MillerKnoll integrations, SharePoint for collaboration documents) maintain their domain-specific roles. Field mappings, sync triggers, source-of-truth rules per object, and error handling are finalized during the technical design phase.

**Decisions for the leadership team.**

- (6a) Confirm: combined confirmed-integrations architecture (HubSpot, banking, MillerKnoll suite, MillerKnoll Exemplis, SharePoint via native connector, SuiteAnalytics Connect if licensed, Stripe) with NetSuite Orion as system of record. *Recommended default: yes.* (Technical design finalized during Realize phase.)
- (6b) Confirm: evaluation / licensing decisions (merged-company payroll provider, merged-company expense platform, ZoomInfo, manufacturer integration expansion) addressed in their owning sections (Financial Management §3.08, Marketing §3.01) with technical setup here once decisions land. *Recommended default: yes.*

---

## 3.10.4 Cross-area dependencies

| Dependency | Where it surfaced in System Setup | Where it's decided |
|---|---|---|
| **HubSpot integration architecture and field mapping** | D-6 | **Marketing (§3.01 D-1)** — platform decision (CT-3); technical design here (Pivot's own SharePoint section flags HubSpot as post-go-live integration consideration) |
| **Banking integration (West Coast Community Bank, Comerica)** | D-6 | **Financial Management (§3.08 D-6)** — bank decision; technical setup here |
| **Payroll provider (Paylocity, UKG, other)** | D-6 (evaluation pending) | **Financial Management (§3.08.8 #9)** — provider decision; CSV import setup here once decided |
| **Expense platform (Expensify, NetSuite native)** | D-6 (evaluation pending) | **Financial Management (§3.08 D-7)** — platform decision; technical setup here once decided |
| **MillerKnoll integrations (ServiceNet, ServiceTime, Quote Tool, Order Manager)** | D-6 | **Order Management (§3.04 D-7)** — integration suite decision; technical setup here |
| **SuiteAnalytics Connect licensing** | D-6 | **BI (§3.09 D-7b)** — licensing decision; technical setup here if licensed |
| **CRM data migration approach (Zendesk, Core, HubSpot extracts and consolidation)** | D-5; cross-references CT-6 | **Decided here in System Setup §3.10 D-5** — CRM-specific extraction and classification approach detailed during configuration |
| **Workfront historical data migration (project, task, time, capacity)** | D-5; cross-references CT-16 | **Decided here in System Setup §3.10 D-5** in coordination with **Project Management (§3.06 D-1)** transition plan |
| **Document storage architecture (Google Drive, SharePoint, IQ, Workfront, file shares)** | D-3; cross-references CT-14 | **Decided here in System Setup §3.10 D-3** |
| **Manager hierarchy configuration for "Me and My Team" filters** | D-4 | **Configured here in System Setup §3.10**; depends on org-chart finalization |
| **Sales Locations / location taxonomy** | D-4 | **Configured here in System Setup §3.10**; geographic dimension and division taxonomy **decided in CRM §3.02 D-3a / D-3b** |
| **Historical data migration scope** | D-5 | **Decided here in System Setup §3.10 D-5** |
| **Division taxonomy** | D-4 (role configuration); D-5 (data classification) | **CRM §3.02 D-3b** — final merged-company taxonomy decided at working session; System Setup configures against the confirmed taxonomy |
| **Pivot Vendor Portal for external design partners (Riverstone / D3 / Azusa)** | D-3 (collaboration platform); D-4 (role-based access) | **Project Management (§3.06)** — vendor-portal capability owned there per Pivot REQ-3.06.02; permissions configured here |

## 3.10.5 Recommendation summary

The merged-company System Setup playbook in shorthand:

- **Governance:** DREAM methodology with named-role assignments per KBM REQ-001 through REQ-005; Sean Scanlon (GSI) and Matt Denning (merged-company) executive sponsorship; merged-company Program Manager, Change Management Lead, and workstream leads determined during organizational alignment
- **Cutover strategy:** Dual posture per legacy — KBM soft cutover; Pivot no-open-order migration with D365 read-only post-go-live (REQ-3.11.07); process-area sequencing during implementation planning
- **Document management:** NetSuite File Cabinet as primary for transactional documents; SharePoint via native connector (Pivot REQ-1.12.01 through REQ-1.12.08) as merged-company collaboration platform; KBM Google Drive content migrates to SharePoint; Pivot fragmented sources (IQ / Workfront / file shares) consolidate to SharePoint and File Cabinet by document type per CT-14; Workfront's July 2026 expiration is the migration deadline
- **Roles:** 25+ custom Orion roles (KBM REQ-010) adapted for two-dimensional hierarchy (geography + division per CRM §3.02 D-3a / D-3b); Sales Locations configured here against CRM-decided taxonomy
- **Historical data migration:** Combined scope — Workfront (CT-16), D365 Levels 1 / 2 / 3A, KBM Core with archive maintained, Zendesk, HubSpot, document migration (CT-14); pre-migration cleansing (REQ-3.11.05) and reconciliation validation (REQ-3.11.06)
- **Integration architecture:** Confirmed integrations (HubSpot, banking, MillerKnoll suite, MillerKnoll Exemplis, SharePoint, SuiteAnalytics Connect if licensed, Stripe) configured here against owning-section decisions; evaluation / licensing decisions (payroll provider, expense platform, ZoomInfo, manufacturer expansion) decided in owning sections, configured here once decisions land

## 3.10.6 Decisions for the leadership team

| # | Decision | Default | Reference |
|---|---|---|---|
| 1 | Named-role governance framework with merged-company assignments per KBM REQ-001 through REQ-005 | Yes | D-1 |
| 2a | KBM soft-cutover posture (in-flight Core work completes there or migrates) | Yes | D-2 |
| 2b | Pivot no-open-order migration posture (D365 read-only post-go-live per REQ-3.11.07) | Yes | D-2 |
| 2c | Process-area cutover sequencing during implementation planning | Yes | D-2 |
| 3a | NetSuite File Cabinet as primary transactional document repository | Yes | D-3 |
| 3b | SharePoint as merged-company collaboration-document platform via native connector (Pivot REQ-1.12.01 through REQ-1.12.08) | Yes | D-3 |
| 3c | KBM Google Drive content migrates to SharePoint; Pivot fragmented sources (IQ / Workfront / file shares) consolidate to SharePoint and File Cabinet by document type | Yes | D-3 |
| 4 | Standard Orion 25+ custom role taxonomy (KBM REQ-010) configured against CRM §3.02 D-3a / D-3b decisions | Yes | D-4 |
| 5 | Combined historical data migration scope (Workfront / D365 / KBM Core + archive / Zendesk / HubSpot / documents); pre-migration cleansing and reconciliation per Pivot REQ-3.11.05 / REQ-3.11.06 | Yes | D-5 |
| 6a | Combined confirmed-integrations architecture with NetSuite Orion as system of record | Yes | D-6 |
| 6b | Evaluation / licensing decisions (payroll provider, expense platform, ZoomInfo, manufacturer expansion) addressed in owning sections; technical setup here once decided | Yes | D-6 |

> 11 decisions across 6 divergences, all with default-yes recommendations. The merged-company configuration direction is committed; the working session focus is confirmation and transition-timeline detail per area.

## 3.10.7 Configuration carryover

| Item | KBM-side built? | Pivot-side built? | Action for merged company |
|---|---|---|---|
| NetSuite Orion environment | KBM prepaid account (operating account) | Pivot D365 in use; migrating | Configure merged-company environment in KBM's prepaid account |
| Orion Suite Apps | Specified, in progress | Specified | Install per common-ground items |
| DREAM methodology framework | Specified (REQ-005) | Implicit | Operate per common-ground |
| Named-role governance (executive sponsor, Program Manager, Change Management Lead, workstream leads) | Specified (REQ-001 through REQ-004) | Not specified at same level | Configure per D-1; merged-company assignments during organizational alignment |
| Custom Orion roles (25+) | Specified (REQ-010) | Specified at framework level | Build merged role taxonomy per D-4; configure against CRM §3.02 D-3a / D-3b |
| Sales Locations configuration | Implicit (KBM territories) | Specified (Pivot Design Centers) | Configure per D-4; geography taxonomy decided in CRM §3.02 D-3a |
| Subsidiary / multi-currency / 13-period calendar | Implicit | Specified | Configure per Pivot framework |
| Item master / SIF | Implicit | Specified (Pivot §3.04) | Configure per Pivot framework |
| Location / warehouse setup | Implicit | Specified (Pivot §3.05) | Configure per Pivot framework |
| System preferences | Implicit | Specified (Pivot §3.06) | Configure per Pivot framework |
| Transaction numbering and saved-search configuration | Specified (KBM BRD §6) | Specified (Pivot §3.07) | Configure per common-ground |
| Document management — File Cabinet for transactional | Implicit | Implicit | Configure per D-3 |
| Document management — SharePoint via native connector for collaboration | Google Drive in use; sunset planned per CT-14 | SharePoint as target consolidation platform per REQ-1.12.01 through REQ-1.12.08 | Configure per D-3 |
| KBM Google Drive content migration to SharePoint | Specified (sunset) | N/A | Migrate per D-3c on defined transition timeline |
| Pivot fragmented document sources (IQ / Workfront / file shares / email / local storage) consolidation to SharePoint / File Cabinet | N/A | Specified as current-state pain (`:1291`) | Consolidate per D-3c during IQ / Workfront sunset; Workfront July 2026 expiration is hard deadline |
| Integration architecture — confirmed integrations | Multiple specified (ServiceNet, ServiceTime, MillerKnoll Exemplis, Stripe, West Coast Community Bank, Quote Tool) | Multiple specified (HubSpot, Comerica, MillerKnoll Order Manager, SharePoint native connector) | Build combined per D-6a |
| Integration architecture — evaluation / licensing | Paylocity, Coupa, additional manufacturer expansion pending | UKG, ZoomInfo, SuiteAnalytics Connect pending | Configure per D-6b once owning-section decisions land |
| Historical data migration — Workfront (project / task / time / capacity) | N/A | Specified (Workfront sunset per CT-16) | Plan per D-5 in coordination with Project Management §3.06 D-1 |
| Historical data migration — D365 (Levels 1 / 2 / 3A; no open orders; D365 read-only) | N/A | Specified (REQ-3.11.01 through REQ-3.11.07) | Plan per D-5 |
| Historical data migration — KBM Core (2017+ baseline; archive maintained for pre-2017 and post-migration lookups) | Specified | N/A | Plan per D-5 |
| Historical data migration — CRM (Zendesk, HubSpot, Core extracts) | Specified | Specified | Plan per D-5 / CT-6 |
| Pre-migration data cleansing and reconciliation | Implicit | Specified (REQ-3.11.05 / REQ-3.11.06) | Configure per D-5 |
| Teams collaboration / status / change control | Specified (KBM BRD §3-§4) | Implicit | Configure per common-ground |

## 3.10.8 Open questions / inputs needed

1. **Merged-company role assignments** (decision 1) — Program Manager, Change Management Lead, and other named roles determined during organizational alignment.
2. **KBM Google Drive content migration timeline** (decision 3c) — schedule for migrating KBM's existing Google Drive collaboration content into SharePoint and sunsetting the Google Drive integration; finalized during change-management planning.
3. **Pivot fragmented document migration timeline** (decision 3c) — schedule for consolidating Pivot's IQ / Workfront / file shares / email / local storage into SharePoint / File Cabinet; Workfront July 2026 expiration is the hard deadline; finalized during change-management planning in coordination with Project Management §3.06 D-1.
4. **Historical data migration back-cutoff date and per-stream depth** (decision 5) — finalized during data-migration planning with finance, BI, and process-area leadership input.
5. **Workfront historical data migration scope** (decision 5; CT-16) — project, task, time, and capacity data extraction from Workfront and migration to Orion native; scope finalized with Project Management §3.06 D-1 transition plan.
6. **Integration field mappings, sync triggers, source-of-truth rules, error handling** (decision 6a) — completed during Realize-phase technical design.
7. **Merged-company payroll provider decision** (decision 6b) — Paylocity vs. UKG vs. other; decided in Financial Management §3.08.8 #9.
8. **Merged-company expense platform decision** (decision 6b) — Expensify vs. NetSuite native; decided in Financial Management §3.08 D-7.
9. **Manager hierarchy configuration** — depends on merged-company org-chart finalization.
10. **Workstream lead assignments** (decision 1) — KBM and Pivot department SMEs paired for each process area.
11. **KBM archive system** (decision 5) — confirm pre-2017 archive system access continues; configure post-migration Core lookups.
12. **SharePoint folder structure conventions** (decision 3b) — Pivot REQ-1.12.02 / REQ-1.12.06 specify customer / project / document-type alignment with automated folder creation; specific naming conventions decided during configuration.
13. **Pivot Vendor Portal permissions configuration** — vendor-portal permissions (per Pivot Project Management REQ-3.06.02 / REQ-3.06.03) configured against merged-company division taxonomy once CRM §3.02 D-3b lands.
