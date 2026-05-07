# 3.03 — Pre-Quote

| Field | Value |
|---|---|
| **Decision density** | **Medium** — labor quotes (KBM emphasis) and request types (Pivot emphasis) anchor the section; the merged-company request engine consolidates the two source patterns |
| **Source coverage** | Pivot Pre-Quote BRD v2.0 (full BRD with 57 → 24 request type consolidation across 10 categories) + KBM Pre-Quote requirements map and v2.0 comprehensive gap analysis (REQ-LQ-001 through REQ-LQ-008 plus 17-requirement map; final BRD not separately produced — the v2.0 gap analysis and requirements map are the synthesized source) |
| **KBM source** | `Pre-Quote/KBMH/3 Output/Requirements_Map_PreQuote_v1.0.md` plus `Pre-Quote/KBMH/3 Output/GapAnalysis_PreQuote_Labor_Quotes_v2.0_COMPREHENSIVE.md` (REQ-LQ-001 through REQ-LQ-008) and supporting files |
| **Pivot BRD** | `Pre-Quote/Pivot/4 BRD/04_Pivot Interiors BRD Pre-Quote Process Area_v2.0.docx` (markdown copy at `_Unification/working/pivot-brds-md/Pre-Quote.md`); v2.0 includes client responses (`pivot-brds-md/Pre-Quote.md:91`) |

---

## 3.03.1 How each company approaches Pre-Quote today

**KBM Hogue** approaches Pre-Quote primarily through the lens of labor quote management and vendor coordination. Its v1.0 requirements map articulates 17 requirements; the v2.0 comprehensive gap analysis replaces those with REQ-LQ-001 through REQ-LQ-008 covering active labor quote types (Third Party and Intermarket; Internal and Long-Term Storage marked inactive in current operations per `GapAnalysis_PreQuote_Labor_Quotes_v2.0_COMPREHENSIVE.md:88-96`), decentralized labor-quote initiation by PMs and Account Managers (REQ-LQ-002), multi-pathway labor cost entry (REQ-LQ-003 — Excel ROM, Project Spec, Core SIF import or manual), multi-line labor quote itemization with hold-back strategy for drip charges (REQ-LQ-004), external pre-quote work linkage from Opportunities (REQ-LQ-005), the 15% labor GP deduction business rule (REQ-LQ-006), labor quote dashboard with filtering as a Phase 2 capability (REQ-LQ-007 — `GapAnalysis v2.0:396`), and quote acceptance via vendor PO issuance (REQ-LQ-008 — confirmed acceptance pattern at `GapAnalysis v2.0:404`). KBM also articulates vendor-management requirements for service providers including union/non-union classification, location-based filtering, and parent-child structures for multi-location vendors. KBM's Pre-Quote material identifies a process change confirmed at `GapAnalysis v2.0:52`: launch labor quote requests from the Opportunity record, aligning with Orion's design philosophy that operational data lives on transaction records and project records serve as reporting/aggregation layers.

**Pivot Interiors** approaches Pre-Quote as a request-engine consolidation problem. Its BRD documents 57 distinct issue types currently managed in Adobe Workfront across 10 categories (Design Related, Finance, General, Labor Quote, Order Entry, Other, Pre-Sale, Proposal/Quote, Punch, Service). Pivot's BRD maps these 57 issue types to 24 Orion request types (`pivot-brds-md/Pre-Quote.md:189`) — 33 of the legacy types resolve to existing standard Orion processes (orders, quotes, change orders, etc.) without needing a dedicated request type, and the remaining 24 types are configured in the Orion request engine. Pivot's emphasis is on consolidating manual coordination across Workfront, IQ Coordinator, and D365 into a single platform. The BRD names Sherri Nuzum's Workfront knowledge as a key dependency the consolidation reduces, and articulates IPM (Integrated Project Manager) routing for complex projects with sales-coordinator routing for transactional work.

Both companies share the same end-state goals at a high level: a unified request engine inside Orion, automated routing based on request type and team assignment, conditional logic in request forms, document attachment, status tracking with audit trails, and elimination of manual coordination across multiple systems. Where they differ is the volume and breadth of request types (Pivot's 57 → 24 framework spans 10 categories; KBM's labor-quote-centered set is narrower), the level of detail in vendor-management requirements (KBM articulates union / location / parent-child specificity; Pivot's Pre-Quote BRD does not), and the source-system migration paths (Pivot from Workfront, IQ Coordinator, D365; KBM from the legacy Bridge platform).

## 3.03.2 Where the two companies align

The following capabilities are common ground across both BRDs/source materials and require no merged-company decision:

**Explicit in both:**

- Configurable request engine with multiple request types
- Automated routing based on request type and team assignment
- Conditional logic in request forms (dynamic fields based on user responses)
- Request approval workflows and status tracking with audit trails
- Document attachment to requests
- Vendor coordination through request workflows
- Replacement of legacy Pre-Quote tools (Pivot's Workfront + IQ Coordinator; KBM's Bridge) with the Orion request engine
- Job site analysis / site conditions record attached to address (KBM REQ-012 in v1.0 map; Pivot §3.02 Requirements Management)

**KBM-explicit; standard capability carried forward for the merged company:**

- CAM reservation number field on labor quote form (KBM REQ-006 / v1.0 map)
- CAP/SIF file attachment support for project documentation (KBM REQ-015 / v1.0 map)
- Branded RFQ form for vendor communications (KBM REQ-016 / v1.0 map)
- External pre-quote work URL linkage on Opportunity (KBM REQ-LQ-005 / v2.0 gap analysis)

**Pivot-explicit; standard capability carried forward for the merged company:**

- 33 of Pivot's legacy 57 issue types resolve to standard Orion processes without dedicated request types (orders, quotes, change orders, etc.)
- Quick Quote functionality for rapid transactional quotes
- Demo request workflow with delivery coordination
- GSA (government sales) order type and proposal workflow
- Mockup order type with approval workflow

These are noted in the merged BRD, and configuration proceeds against standard Orion request engine and process capability.

## 3.03.3 Where the two companies differ

Eight in-area divergences. Each is presented as: how each company approached it (with attribution to context), the recommendation for the merged company, and the decision the leadership team owns.

---

### D-1. Request engine scope and request type taxonomy

**Source:** Pivot §3.01 Request Management (`pivot-brds-md/Pre-Quote.md:189` — 57 → 24 mapping); KBM REQ-001, REQ-002, REQ-014 (`Requirements_Map_PreQuote_v1.0.md`); KBM v2.0 gap analysis Q1 (`GapAnalysis_PreQuote_Labor_Quotes_v2.0_COMPREHENSIVE.md:42`)

**KBM's approach.** KBM's source material focuses on a focused set of request types: active labor quote categories (Third Party, Intermarket; Internal and Long-Term Storage marked inactive per v2.0 gap analysis Q1), a project request form with service-type checkboxes (Estimating needed, Design needed, PM needed) triggering appropriate notifications, and the migration from Bridge to the Orion request engine. The breadth is narrower than Pivot's because KBM's pre-quote operations focus on labor quoting and project initiation.

**Pivot's approach.** Pivot's BRD documents a broader request engine consolidation: 57 distinct Workfront issue types across 10 categories (Design Related, Finance, General, Labor Quote, Order Entry, Other, Pre-Sale, Proposal/Quote, Punch, Service) mapped to 24 Orion request types, with 33 of the legacy types resolving to standard Orion processes. The breadth reflects Pivot's existing operational scope (in-house operations, divisional sales structure, government and specialty workflows).

**Recommendation for the merged company.** Adopt Pivot's request type taxonomy as the merged-company baseline (24 Orion request types organized across the 10 categories). KBM's active labor-quote categories (Third Party, Intermarket per REQ-LQ-001) are configured as **subtypes or values inside the Labor Quote request type** rather than as additional top-level request types — preserving Pivot's 24-type math while supporting KBM's labor-quote operational specificity. The reasoning is contextual: the merged company inherits Pivot's operational scope (in-house operations, GSA workflows, design support, demo coordination, punch, service) and benefits from a comprehensive request engine that covers all those activities at the request-type level. KBM's labor categories add depth at the subtype/value level. The 33 issue types Pivot maps to standard Orion processes carry forward as standard processes for the merged company.

**Decisions for the leadership team.**

- (1a) Confirm: Pivot's 24-request-type taxonomy adopted as merged-company baseline. *Recommended default: yes.*
- (1b) Confirm: KBM's active labor-quote categories (Third Party, Intermarket per REQ-LQ-001) configured as subtypes/values inside the Labor Quote request type rather than as additional top-level request types. *Recommended default: yes.*

---

### D-2. Labor quote workflow depth

**Source:** KBM v2.0 gap analysis REQ-LQ-001 through REQ-LQ-008 (`GapAnalysis_PreQuote_Labor_Quotes_v2.0_COMPREHENSIVE.md:354-409`); Pivot Labor Quote category (`pivot-brds-md/Pre-Quote.md:271-283`)

**KBM's approach.** KBM's v2.0 gap analysis articulates a labor-quote workflow at depth:

- **REQ-LQ-001** — minimum two active labor quote types (Third Party, Intermarket); Internal and LTS inactive (`:354-359`)
- **REQ-LQ-002** — decentralized initiation by multiple authorized roles (PM, Account Manager); supports multi-vendor bidding (`:361-367`)
- **REQ-LQ-003** — multi-pathway labor cost entry (Excel ROM, Project Spec, Core SIF import or manual) (`:369-373`)
- **REQ-LQ-004** — multi-line labor quote itemization with hold-back strategy for drip charges, contingencies, phased work (`:375-380`)
- **REQ-LQ-005** — URL/link fields on Opportunity for external pre-quote work (Google Slides, Sheets, drawings) (`:382-386`)
- **REQ-LQ-006** — automated 15% labor GP deduction business rule (cross-references Financial Management §3.08 D-4 — labor markup eliminated for the merged company) (`:388-394`)
- **REQ-LQ-007** — labor quote dashboard with filtering (location, division, team member, quote status, vendor); confirmed as Phase 2 / post-initial go-live (`:396-402`)
- **REQ-LQ-008** — quote acceptance workflow: vendor PO issuance with vendor-quote-number reference is the official acceptance event; no formal rejection needed (future enhancement) (`:404-409`)

**Pivot's approach.** Pivot's BRD treats labor quote as one category within the broader 24-request-type taxonomy. Pivot articulates Quick Quote functionality for simple transactional quotes and notes a discussion-needed item for HealthCare/CSHDP labor quotes (where one person communicates with the customer and another does the work).

**Recommendation for the merged company.** Adopt KBM's labor-quote workflow depth as the merged-company labor-quote framework, integrated within Pivot's broader request engine. The reasoning is contextual: KBM's labor-quote workflow specificity (REQ-LQ-001 through REQ-LQ-008) is operationally valuable for the merged company's labor-quote volume across both legacy companies, and the framework slots cleanly into Pivot's Labor Quote category. The HealthCare/CSHDP customer-communicator-vs-worker scenario Pivot raised is addressed during configuration as a labor-quote sub-workflow. The 15% labor GP deduction (REQ-LQ-006) is eliminated per Financial Management §3.08 D-4 (labor markup eliminated). The Phase 2 dashboard (REQ-LQ-007) is targeted for post-initial-go-live.

**Decision for the leadership team.** Confirm: KBM's labor-quote workflow depth (REQ-LQ-001 through REQ-LQ-008, with REQ-LQ-006 / 15% labor markup eliminated per Financial Management §3.08 D-4 and REQ-LQ-007 dashboard targeted for Phase 2) adopted as merged-company labor-quote framework, integrated within the 24-request-type taxonomy. *Recommended default: yes.*

---

### D-3. Vendor management for service providers

**Source:** KBM REQ-003, REQ-004, REQ-005, REQ-017 (`Requirements_Map_PreQuote_v1.0.md`); Pivot vendor management addressed primarily in Financial Management §3.15

**KBM's approach.** KBM's source material articulates detailed vendor-management requirements for Pre-Quote service providers: union/non-union status tracking on vendor records (with dropdown values for filtering), location-based identification using a custom field sourced from the COR location list, parent-child vendor relationships for multi-location service providers, and vendor filtering by union status, intermarket classification, and location. The cluster is identified as tightly coupled and requires a technical design session.

**Pivot's approach.** Pivot's Pre-Quote BRD does not articulate vendor-management requirements at the same level of detail; vendor management is addressed primarily in Financial Management §3.15 with a focus on vendor-customer dual setup and vendor credit limit tracking.

**Recommendation for the merged company.** Adopt KBM's vendor-management framework for Pre-Quote service providers as the merged-company default. Custom fields for union status, location (sourced from the merged-company location list per the System Setup §3.10 location taxonomy and CRM §3.02 D-3a / D-3b), and parent-child structure for multi-location vendors are configured per KBM's specification. Vendor filtering by union status, intermarket classification, and location is enabled in labor-quote creation workflows. The merged company's vendor-coordination capability across labor-quote operations benefits from this depth, and Pivot's vendor base is incorporated into the same vendor-record model.

**Decision for the leadership team.** Confirm: vendor-management framework for Pre-Quote service providers adopted from KBM source (union/non-union, location, parent-child, intermarket filtering). *Recommended default: yes.* (Specific dropdown values and field configuration finalized during Realize phase; technical confirmations on NetSuite native union-status tracking and multi-select-vs-parent-child for location confirmed during Realize.)

---

### D-4. Request initiation point — labor quote launch from Opportunity

**Source:** KBM v2.0 gap analysis Q11 (`GapAnalysis_PreQuote_Labor_Quotes_v2.0_COMPREHENSIVE.md:52` — "Yes - labor quote can be launched from Opportunity record"); Q12 (`:53` — Opportunity as scope source of truth, pending Matt Denning / Kimi Katsuyoshi decision); Pivot's BRD assumes standard Orion request initiation patterns

**KBM's approach.** KBM's v2.0 gap analysis Q11 confirms labor-quote launch from the Opportunity record (decision is made; pending only Orion technical capability confirmation). Q12 raises a related but distinct decision — Opportunity as the single source of truth for scope vs. multiple sources — pending leadership input from Matt Denning and Kimi Katsuyoshi. The launch-point change reflects Orion's design philosophy that operational data lives on transaction records and project records serve as reporting/aggregation layers. KBM's framing applies specifically to **labor quotes** at this stage; design-request and PM-request workflows are not yet validated (KBM v2.0 gap analysis Q18 / Q19 are unanswered and require additional discovery sessions).

**Pivot's approach.** Pivot's BRD does not articulate this specifically because Pivot's Workfront-driven workflows have a different launch-point pattern. Pivot's BRD treats request initiation through the broader Orion request engine without specifying Opportunity/Quote vs. Project as a distinct decision.

**Recommendation for the merged company.** Adopt the Opportunity launch-point pattern (KBM's framing per REQ-LQ-001 / Q11) as the merged-company default for **labor quote requests**, consistent with Orion's design philosophy. The reasoning is contextual: the merged company operates from Orion's record model where transaction records (Opportunities, Quotes, Sales Orders) are the operational surface and Project records are the aggregation layer. KBM's framing aligns with this architecture; Pivot's team adopts the same pattern as part of the Workfront-to-Orion transition. Design-request and PM-request workflows remain open for additional discovery (per KBM v2.0 gap analysis Q18 / Q19) — those launch-point decisions are made when those workflows are designed.

**Decisions for the leadership team.**

- (4a) Confirm: labor quote requests launched from Opportunity records (KBM REQ-LQ-001 / v2.0 Q11). *Recommended default: yes.*
- (4b) Confirm: Opportunity as scope single source of truth (KBM v2.0 Q12). *Decided at working session* with Matt Denning / Kimi Katsuyoshi input.

---

### D-5. Project request form — service-type triggers

**Source:** KBM REQ-014 (`Requirements_Map_PreQuote_v1.0.md`); Pivot Design Related category (`pivot-brds-md/Pre-Quote.md` §3.01) — eight design-related issue types (Design Double Check, Design Support External, Design Support Internal, Design Production Support, Design Fee per Contract, Design Sub Contract Contract, Design Sub Contract Support, Design Invoice Submittal) consolidated to a single design-support request record using a type field

**KBM's approach.** KBM's source material articulates a project request form with service-type checkboxes (Estimating needed, Design needed, PM needed) triggering appropriate notifications and workflows. KBM also flags that Design and PM request workflows are currently undocumented and need additional discovery (v2.0 gap analysis Q18 / Q19).

**Pivot's approach.** Pivot's BRD addresses design-related requests through eight issue types in the Design Related category (Design Double Check, Design Support External, Design Support Internal, Design Production Support, Design Fee per Contract, Design Sub Contract Contract, Design Sub Contract Support, Design Invoice Submittal), consolidated to a single design-support request record using a type field. PM routing is addressed through IPM assignment for complex projects.

**Recommendation for the merged company.** Combine: KBM's service-type-trigger pattern (Estimating, Design, PM checkboxes on project request forms) provides a clean entry point that automatically triggers the appropriate downstream workflow; Pivot's design-related request consolidation provides the depth in design-support workflows. The merged-company project request form uses service-type triggers as the user-facing entry, with the downstream workflows mapped to Pivot's consolidated request types and IPM-vs-sales-coordinator routing pattern. The Design and PM workflows that KBM flagged as undocumented (Q18 / Q19) are addressed through Pivot's existing design-related request structure during configuration with KBM and Pivot design and PM leads.

**Decision for the leadership team.** Confirm: project request form with service-type triggers (KBM pattern) routing to Pivot's consolidated downstream request types (design-support, IPM assignment). *Recommended default: yes.*

---

### D-6. Request rejection / send-back workflow

**Source:** KBM REQ-009 (`Requirements_Map_PreQuote_v1.0.md`); KBM v2.0 gap analysis Q9 (`GapAnalysis v2.0:50` — concept proposed; needs scope-based logic and exception design); Pivot's BRD addresses request approval workflows broadly (`pivot-brds-md/Pre-Quote.md` §3.01)

**KBM's approach.** KBM's source material articulates a request rejection / send-back-for-more-information workflow as a custom requirement, with KBM v2.0 gap analysis Q9 noting that scope-based logic and exception handling design is needed. REQ-LQ-008 confirms that PO issuance is the official acceptance event today; formal rejection is identified as a future enhancement.

**Pivot's approach.** Pivot's BRD articulates request approval workflows broadly within the request engine framework but does not specifically articulate the rejection/send-back pattern at the same level.

**Recommendation for the merged company.** Adopt the rejection/send-back workflow as a merged-company capability, configured via the Orion request engine's approval routing. Whether this is built as a dedicated rejection action or addressed through mandatory-field validation is finalized during the configuration phase based on Orion request-engine capabilities. KBM's framing flags the requirement; the configuration approach is determined during Realize.

**Decision for the leadership team.** Confirm: rejection/send-back workflow is a merged-company request-engine capability. *Recommended default: yes.* (Specific configuration approach — dedicated rejection action vs. mandatory-field validation — determined during Realize phase.)

---

### D-7. Specialized order types — WIX, ServiceNet, DUR, GSA, Mockup, Storage

**Source:** Pivot §3.01 Request Management (`pivot-brds-md/Pre-Quote.md` §3.01); KBM source material does not articulate these as specific specialized types

**KBM's approach.** KBM's source material does not specifically articulate WIX, ServiceNet, DUR (Delivery Upon Receipt), or GSA-specific specialized order types or quote-bypass processes.

**Pivot's approach.** Pivot's BRD documents specialized order types and quote-bypass processes for WIX, ServiceNet, DUR, Quick Quotes, warranty claims, GSA proposals, mockup orders, lease/third-party/direct billing, and storage agreements. These reflect Pivot's existing operational scope (government work, specialty fulfillment patterns, multi-channel order flows).

**Recommendation for the merged company.** Adopt Pivot's specialized order types and quote-bypass processes as merged-company capabilities. The reasoning is contextual: the merged company inherits Pivot's operational scope including government workflows (GSA), specialty fulfillment patterns (DUR, WIX, ServiceNet), and lease/third-party billing. KBM's team learns these specialized order types as part of onboarding into the merged-company operational scope. Specific configuration of each specialized type follows Pivot's BRD mapping (order-type field driving automation; vendor-type field for GSA; etc.). Pre-Quote owns the **taxonomy decision**; Order Management §3.04 D-3 uses the taxonomy.

**Decision for the leadership team.** Confirm: Pivot's specialized order types and quote-bypass processes (WIX, ServiceNet, DUR, GSA, mockup, lease/third-party billing, storage agreements) adopted as merged-company capabilities; Pre-Quote owns the taxonomy and Order Management §3.04 D-3 uses it. *Recommended default: yes.*

---

### D-8. IPM and sales-coordinator routing model

**Source:** Pivot §3.01 Request Management (`pivot-brds-md/Pre-Quote.md` §3.01); KBM source material addresses routing through service-type checkboxes (REQ-014); CRM §3.02 D-3 (two-dimensional sales hierarchy — geography + division)

**KBM's approach.** KBM's source material addresses routing through the service-type-trigger pattern on the project request form (Estimating, Design, PM checkboxes), with downstream notification and workflow assignment. KBM does not articulate a specific IPM (Integrated Project Manager) role.

**Pivot's approach.** Pivot's BRD articulates a routing model where IPMs receive complex projects while sales coordinators handle transactional work directly. The routing logic is built into the request engine's automated assignment rules. Routing operates within Pivot's divisional sales motion (cross-references CRM §3.02 D-3b division taxonomy).

**Recommendation for the merged company.** Adopt Pivot's IPM-and-sales-coordinator routing model as the merged-company default for Pre-Quote request routing. The reasoning is contextual: the merged company's project complexity spans the divisional sales motion (where Pivot's IPM model fits) and KBM's transactional patterns. The routing model assigns complex projects to IPMs and transactional work to sales coordinators, with both KBM's service-type-trigger pattern and Pivot's existing IPM assignments preserved through configuration. The specific IPM role assignment for KBM staff is part of the merged-company organizational alignment. Routing rules incorporate the merged-company division taxonomy decided at CRM §3.02 D-3b.

**Decision for the leadership team.** Confirm: IPM-and-sales-coordinator routing model adopted from Pivot framework as merged-company default; routing rules incorporate the merged-company division taxonomy (CRM §3.02 D-3b). *Recommended default: yes.* (Specific IPM role assignments for KBM staff finalized during organizational alignment.)

---

## 3.03.4 Cross-area dependencies

The following surfaced in Pre-Quote discovery but are decided in other process areas. They are flagged here so the working session understands the connections; the decisions themselves live in their proper home area.

| Dependency | Where it surfaced in Pre-Quote | Where it's decided |
|---|---|---|
| **Multi-company / multi-contact relationship model for vendor coordination** | Vendor management for service providers (D-3) | **CRM (§3.02 D-4)** — relationship model is locked; Pre-Quote uses the model for vendor and contact coordination |
| **Approval workflow framework for request approvals** | Request rejection / send-back workflow (D-6); approval routing for Pre-Quote requests | **Order Management (§3.04 D-1)** — approval framework design lives there |
| **Document storage architecture (CAP/SIF files, project documentation, drawings, presentations)** | Document attachment support (KBM REQ-015); KBM v2.0 gap analysis OQ3 file management strategy | **System Setup & Configuration (§3.10 D-3)** — CT-14 lock: SharePoint for collaboration documents (drawings, presentations, design files); File Cabinet for transactional documents (proposals, POs); KBM Google Drive sunset |
| **Workfront sunset and Pivot PM team transition** | Sherri Nuzum's Workfront knowledge as a key dependency Pre-Quote consolidation reduces | **Project Management (§3.06 D-1)** — Workfront sunset and transition plan (CT-16) |
| **Location taxonomy for vendor location field (KBM REQ-004)** | Vendor location-based filtering (D-3) | **CRM (§3.02 D-3a)** — geographic dimension; **System Setup & Configuration (§3.10)** — Sales Locations configuration |
| **Division taxonomy** | IPM-and-sales-coordinator routing (D-8) operates within divisional sales motion | **CRM (§3.02 D-3b)** — final merged-company division taxonomy |
| **RFP coordination workflow** | RFP requests are a Pre-Quote-adjacent activity; CT-8 places task/resource and project/folder timing here or Operations | **Marketing (§3.01 D-8)** — RFP coordination workflow lives there; **CT-8** — Pre-Quote and/or Operations decide task/resource and folder timing |
| **Pipeline stage model** | Quote stage triggers, Pre-Quote-to-Quote transitions | **CRM (§3.02 D-1)** — pipeline model is locked |
| **Project record framework** | Pre-Quote-to-Project transitions; project request workflows | **Project Management (§3.06 D-2)** — project record structure decided there |
| **Order-type taxonomy** | Specialized order types (D-7) — Pre-Quote owns taxonomy | **Pre-Quote (§3.03 D-7)** — owned here; **Order Management (§3.04 D-3)** uses |
| **GP and margin discipline (15% labor markup elimination)** | KBM REQ-LQ-006 (15% labor GP deduction) | **CRM (§3.02 D-6)** — GP framework is locked; **Financial Management (§3.08 D-4 / D-5)** — labor markup eliminated, dual GP framework operationalized |

## 3.03.5 Recommendation summary

The merged-company Pre-Quote playbook in shorthand:

- **Request engine:** Pivot's 24-request-type taxonomy across 10 categories adopted as the merged-company baseline; KBM's active labor-quote categories (Third Party, Intermarket per REQ-LQ-001) integrated into the Labor Quote category as subtypes
- **Labor quotes:** KBM's labor-quote workflow depth (REQ-LQ-001 through REQ-LQ-008) adopted as merged-company framework; 15% labor GP deduction (REQ-LQ-006) eliminated per Financial Management §3.08 D-4; dashboard (REQ-LQ-007) targeted for Phase 2
- **Vendor management for service providers:** KBM's framework adopted (union/non-union status, location field, parent-child structure, intermarket filtering)
- **Request initiation:** Labor quote requests launched from Opportunity records (KBM REQ-LQ-001 / Q11); design and PM workflow launch points decided when those workflows are designed (Q18 / Q19 open)
- **Project request form:** Service-type triggers (Estimating / Design / PM checkboxes from KBM) routing to Pivot's consolidated downstream request types (design-related category with eight types consolidated via type field)
- **Rejection / send-back workflow:** Merged-company request-engine capability; specific configuration approach determined during Realize
- **Specialized order types:** Pivot's framework adopted (WIX, ServiceNet, DUR, GSA, mockup, lease/third-party billing, storage agreements); Pre-Quote owns taxonomy, Order Management uses
- **Routing model:** IPM and sales-coordinator routing per Pivot framework; rules incorporate merged-company division taxonomy (CRM §3.02 D-3b)
- **Job site analysis / site conditions:** KBM's standard Orion record framework
- **Document attachment:** SharePoint for collaboration documents, File Cabinet for transactional documents per CT-14 / System Setup §3.10 D-3
- **15% labor GP deduction:** Eliminated per Financial Management §3.08 D-4

Net read: the merged-company Pre-Quote function combines design choices that fit the merged-company's situation. Pivot's contributions reflect its operational scope (24-request-type taxonomy across 10 categories, specialized order types for government and specialty workflows, IPM routing model). KBM's contributions reflect its labor-quote operational depth and vendor-management specificity (REQ-LQ-001 through REQ-LQ-008, vendor union/location/parent-child framework, RFQ branding, Opportunity launch-point discipline). The merged company's Pre-Quote operating model uses Pivot's request-engine breadth as the operational baseline and KBM's labor-quote and vendor-management depth as operational specifics.

## 3.03.6 Decisions for the leadership team

| # | Decision | Default | Reference |
|---|---|---|---|
| 1a | Pivot's 24-request-type taxonomy adopted as merged-company baseline | Yes | D-1 |
| 1b | KBM's active labor-quote categories (REQ-LQ-001 — Third Party, Intermarket) integrated into the Labor Quote category | Yes | D-1 |
| 2 | KBM's labor-quote workflow depth (REQ-LQ-001 through REQ-LQ-008) adopted as merged-company framework; REQ-LQ-006 / 15% markup eliminated; REQ-LQ-007 dashboard Phase 2 | Yes | D-2 |
| 3 | Vendor-management framework for service providers (union/non-union, location, parent-child, intermarket filtering) | Yes | D-3 |
| 4a | Labor quote requests launched from Opportunity records (KBM REQ-LQ-001 / v2.0 Q11) | Yes | D-4 |
| 4b | Opportunity as scope single source of truth (KBM v2.0 Q12) | Decided at working session | D-4 |
| 5 | Project request form with service-type triggers routing to Pivot's consolidated downstream request types | Yes | D-5 |
| 6 | Rejection / send-back workflow as merged-company request-engine capability | Yes (configuration approach during Realize) | D-6 |
| 7 | Pivot's specialized order types and quote-bypass processes adopted; Pre-Quote owns taxonomy, Order Management §3.04 D-3 uses | Yes | D-7 |
| 8 | IPM-and-sales-coordinator routing model adopted from Pivot framework; rules incorporate merged-company division taxonomy (CRM §3.02 D-3b) | Yes | D-8 |

> 10 decisions: 9 with default-yes recommendations and 1 (decision 4b — Opportunity as scope single source of truth) decided at the working session with Matt Denning / Kimi Katsuyoshi input.

## 3.03.7 Configuration carryover

| Item | KBM-side built? | Pivot-side built? | Action for merged company |
|---|---|---|---|
| Request engine | Bridge in use; specified migration to Orion | Workfront in use; specified migration to Orion | Configure unified Orion request engine per D-1 |
| Request type taxonomy | Labor-quote-focused subset (REQ-LQ-001 active types) | 24 types across 10 categories specified | Build Pivot taxonomy with KBM labor-quote integration per D-1 |
| Labor quote workflow (REQ-LQ-001 through REQ-LQ-008) | Specified | Lighter framing; integrated into Labor Quote category | Build per D-2; eliminate 15% markup per Financial Management §3.08 D-4; Phase 2 dashboard per REQ-LQ-007 |
| Vendor management for Pre-Quote (union, location, parent-child) | Specified | Not specified at same depth | Build per D-3 |
| Project request form (service-type triggers) | Specified | Addressed via design-related category (eight types consolidated) | Build merged form per D-5 |
| Specialized order types (WIX, ServiceNet, DUR, GSA, mockup, lease/3rd-party, storage) | Not specified | Specified | Build per D-7 |
| IPM-and-sales-coordinator routing | Not specified | Specified | Configure per D-8; rules incorporate division taxonomy |
| Branded RFQ form | Specified (KBM REQ-016) | Not specified | Build per D-2 |
| Job site analysis / site conditions record | Specified (KBM REQ-012) | Specified (Pivot §3.02 Requirements Management) | Configure standard Orion record |
| Rejection / send-back workflow | Specified (custom; KBM REQ-009; v2.0 Q9) | Not specified | Configure per D-6 |
| External pre-quote URL linkage on Opportunity | Specified (REQ-LQ-005) | Not specified | Configure standard URL field |
| Document architecture (SharePoint / File Cabinet) | KBM Google Drive sunset | Currently fragmented | Configure per CT-14 / System Setup §3.10 D-3 |

Configuration is in early enough state on both sides that the merged direction is achievable. Pivot's Workfront-to-Orion mapping work and KBM's Bridge-to-Orion migration provide the framework; the merged-company configuration combines them.

## 3.03.8 Open questions / inputs needed

1. **Labor quote rate-table calculations** — KBM identifies rate-table calculations as a future enhancement (multiple dealers requesting). Decision on Phase 1 vs. post-go-live evaluation finalized during configuration.
2. **HealthCare/CSHDP labor quote sub-workflow** — Pivot flagged this scenario where one person communicates with the customer and another does the work. Specific sub-workflow design completed during configuration.
3. **Design and PM request workflow detail** — KBM v2.0 gap analysis Q18 (design request workflow) and Q19 (PM request workflow) are unanswered. Pivot's design-related request consolidation provides a baseline; specific workflow steps confirmed during configuration with both companies' design and PM leads in additional discovery sessions.
4. **Vendor-management technical confirmations** — KBM's source material lists technical confirmations needed (does NetSuite track union status natively? multi-select vs. parent-child for location?). Confirmed during Realize phase technical design session.
5. **CAP/SIF file handling** — KBM flags that PDF vs. SIF import handling needs clarification. Specific file-handling approach decided during configuration in coordination with System Setup §3.10.
6. **IPM role assignment for KBM staff** — operational decision finalized during the merged-company organizational alignment.
7. **GSA workflow detail** — Pivot's GSA-specific workflows (Order - GSA System, Proposal - GSA, Proposal - Standard GSA) configured per Pivot framework; KBM staff training on government-sales workflows during onboarding.
8. **Specialized order type details** — WIX, ServiceNet, DUR specifics documented during configuration based on Pivot's existing operating norms.
9. **Sherri Nuzum's Workfront knowledge transfer** — Pivot's BRD names this as a key dependency. Knowledge transfer plan during the Workfront-to-Orion transition documented during change-management planning (cross-references Project Management §3.06 D-1 / CT-16).
10. **Multiple labor quote acceptance for different scopes** (KBM v2.0 gap analysis Q10) — can multiple labor quotes be accepted on the same project under different scopes? Critical technical validation needed with Orion technical team (per A4 in v2.0 gap analysis); Matt Denning's RFP scenario at `GapAnalysis v2.0:255` describes the operational case.
11. **Auto-rejection logic for unselected labor quotes** (KBM v2.0 gap analysis Q9) — when one labor quote is accepted on a scope, what happens to competing quotes still pending? Scope-based logic and exception handling design needed during Realize.
12. **External pre-quote URL linkage configuration** (REQ-LQ-005) — confirm Orion field configuration during Realize.
13. **15% labor markup elimination communication** — sales-team communication for KBM staff transitioning from REQ-LQ-006 markup pattern to merged-company commissionable-GP framework (cross-references Commissions §3.07 D-1).
