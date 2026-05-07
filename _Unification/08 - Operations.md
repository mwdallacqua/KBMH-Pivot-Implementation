# 3.05 — Operations

| Field | Value |
|---|---|
| **Decision density** | **High** — Pivot operates Operations primarily in-house (delivery, installation, warehousing, field service) with subcontractor and supplemental labor support; KBM has historically coordinated outsourced installation contractors. The merged company combines Pivot's primarily-internal operating model with KBM's outsourced-coordination capability for surge and geographic flexibility |
| **Source coverage** | KBM Operations BRD v1.0 (REQ-001 through REQ-034 across 11 sections covering coordination of outsourced installation, receiving, work orders, time tracking, field service, scheduling) + Pivot Operations BRD v2.0 (REQ-3.01.01 through REQ-3.07.06 across seven sections — receiving and warehouse, scheduling and resource management, work order management, vendor returns, time tracking, punch list, field operations) |
| **KBM BRD** | `Operations/KBMH/3 Output/BRD_Operations_v1.0.md` |
| **Pivot BRD** | `Operations/Pivot/4 BRD/06_Pivot Interiors BRD Operations  Process Area_v2.0.docx` (markdown copy at `_Unification/working/pivot-brds-md/Operations.md`); seven sub-sections — §3.01 Receiving & Warehouse Management, §3.02 Scheduling & Resource Management, §3.03 Work Order Management, §3.04 Vendor Returns Management, §3.05 Time Tracking & Project Management, §3.06 Punch List & Issue Management, §3.07 Field Operations |

---

## 3.05.1 How each company approaches Operations today

**KBM Hogue** approaches Operations through a coordination-of-outsourced-installation model. KBM's project-management and operations team coordinates third-party installation contractors who perform field work at their own warehouses. The model presents distinctive challenges that KBM's BRD documents in detail: receiving must occur at remote contractor locations (impacting WIP), contractors must access project information without email dependency, and PMs must coordinate work in the field using mobile tools without internal installation control. KBM's BRD addresses these through the Orion Operations Suite — Advanced Receiving Tool for warehouse receiving (REQ-002), Vendor Center for contractor communication (REQ-007), VRA process for damage claims with the 80/20 rule (REQ-010 / REQ-012), work orders for field coordination with soft-scheduling approach (REQ-013 / REQ-014 / REQ-015), time tracking for project-GP impact (REQ-016 through REQ-020), 15% labor markup formula line for external labor pricing discipline (REQ-021 / REQ-022 / REQ-023; eliminated per Financial Management §3.08 D-4), Field Service app replacing PlanGrid for punch lists with floor-plan location pinning (REQ-024 through REQ-027), Field Service app deployment with geolocation check-in, photo and signature collection, multi-resource time entry, and offline mode (REQ-028 through REQ-031), the deferred direct-receiving-by-contractor capability for future phase (REQ-008), and PM workload management deferred to additional discovery (REQ-032 / REQ-033 / REQ-034 — see Project Management §3.06 D-4). KBM's BRD also names roles for ownership of decisions: PM Manager / Operations Manager, IT Specialist / Former Controller, CFO / Controller, leadership, and Account Manager / Pre-Quote Manager.

**Pivot Interiors** approaches Operations as a primarily internal capability supplemented by subcontractor and supplemental labor where needed. Pivot's Time Tracking & Project Management section (Pivot REQ-3.05.02 / REQ-3.05.03) explicitly supports time tracking for employees, subcontractors, and temporary resources, and full-job subcontracting plus supplemental labor where internal teams need extension. Pivot's BRD covers operational depth at the section level:

- **§3.01 Receiving & Warehouse Management** — lot-numbered inventory tracking (REQ-3.01.01) eliminating 900,000+ D365 locations, multi-bin receiving (REQ-3.01.02), virtual locations for pre-sold / showroom / damaged-return / third-party warehouses (REQ-3.01.03), product-returning-from-client handling via inventory adjustments and dedicated Mystery Product location (REQ-3.01.04), manual receiving triggers approximately 7 days after vendor invoice for audit compliance (REQ-3.01.05), inventory valuation reporting by location with future CAM integration (REQ-3.01.06; SnapTracker not integrated with Orion; RF Smart License Plating probable solution), and drag-and-drop bin assignment (REQ-3.01.07).
- **§3.02 Scheduling & Resource Management** — badging/tagging for site access certifications including healthcare and government (REQ-3.02.01), skills matrix tracking for resource capabilities (REQ-3.02.02), daily route planning for delivery trucks in Northern and Southern California with tracking in Orion (REQ-3.02.03), resource assignment by job requirements (REQ-3.02.05), route-planning-to-work-order integration (REQ-3.02.06).
- **§3.03 Work Order Management** — streamlined work order creation from sales order lines (REQ-3.03.01), automated dashboard reminders when all POs acknowledged and ready for scheduling (REQ-3.03.02), custom Smart Table groupings for PO organization (REQ-3.03.03), work order creation based on PO groups rather than line items (REQ-3.03.04), phased installation support with 40%/40%/20% sequencing (REQ-3.03.05), multiple work order events per single work order (REQ-3.03.06), elimination of manual file transfer / duplication across Workfront / IQ / D365 (REQ-3.03.07), coordination workflow with installation managers (REQ-3.03.08), automated scheduling notifications (REQ-3.03.09).
- **§3.04 Vendor Returns Management** — formal VRA decision point, optional / Phase 2 (REQ-3.04.01); zero-cost replacement (REQ-3.04.02); replacement-tracking against original orders (REQ-3.04.03); vendor-managed return logistics with call tags (REQ-3.04.04); audit documentation (REQ-3.04.05). Pivot's Phase 1 assumption is informal VRA (no formal workflow).
- **§3.05 Time Tracking & Project Management** — budget-vs-actual reporting for design and PM (REQ-3.05.01); time tracking for employees, subcontractors, temporary resources (REQ-3.05.02); both full-job subcontracting and supplemental labor (REQ-3.05.03); warranty / service-revenue time tracking (REQ-3.05.04); project margin integration (REQ-3.05.05); UKG does not currently integrate with Orion (per Pivot Assumption).
- **§3.06 Punch List & Issue Management** — companion sales orders for punch resolution; $250 approval threshold per Pivot Assumption (configurable post-go-live); MillerKnoll "R" designation for replacement products preserved.
- **§3.07 Field Operations** — Field Service app with floor-plan management (REQ-3.07.01), document and image pinning to floor plans (REQ-3.07.02), photo documentation for CYA / site conditions / damage by others / progress (REQ-3.07.03), offline capability (REQ-3.07.04), signature capture and status reporting (REQ-3.07.05), integration with main project system (REQ-3.07.06), and PDF photo / punch reports with filtering by stamps (additional capability flagged in REQ-3.07 narrative). PlanGrid contract runs concurrent with Orion Field Service during transition; PlanGrid license expires 1/10/2027 per Pivot Assumption.

The two operating models differ in shape: KBM coordinates external resources; Pivot deploys primarily internal resources with subcontractor and supplemental labor support. The merged company operates from Pivot's in-house operating capability as the primary model — the existing infrastructure, the trained field service team, the warehousing and dispatch capability, and the operating norms — extended by KBM's outsourced-coordination capability for surge capacity, geographic gaps where Pivot doesn't have direct installation reach, and continued relationships with KBM's existing third-party contractor network where those relationships deliver value.

## 3.05.2 Where the two companies align

**Explicit in both BRDs:**

- Advanced Receiving Tool / receiving workflows (KBM REQ-002 — Advanced Receiving Tool with drag-and-drop bin; Pivot REQ-3.01.07 drag-and-drop bin assignment)
- Work order management (KBM REQ-013 / REQ-014 / REQ-015; Pivot REQ-3.03.01 through REQ-3.03.09)
- Time tracking with project-GP impact (KBM REQ-016 through REQ-020; Pivot REQ-3.05.01 through REQ-3.05.05)
- Mobile field service app for technicians and PMs (KBM REQ-028 through REQ-031; Pivot REQ-3.07.01 through REQ-3.07.06)
- Punch list management with photo and signature collection (KBM REQ-024 through REQ-027; Pivot REQ-3.06; REQ-3.07.05 signature capture)
- Project documentation attachment

**KBM-explicit; standard capability carried forward for the merged company:**

- Purchase requisition approval workflow with one-click conversion to PO (KBM REQ-001) — Pivot's procurement controls (per Order Management §3.04 D-8 PO generation framework — direct PO from SIF, draft PO, requisition workflows) cover this from a different angle
- Coordination of outsourced installation contractors via Vendor Center (KBM REQ-007)
- Receiving notification feature for contractor-initiated arrivals (KBM REQ-007)
- Soft-scheduling approach for work orders requesting approval rather than hard assignments (KBM REQ-013 / REQ-014 / REQ-015)
- 15% labor markup formula line for external labor pricing (KBM REQ-021 / REQ-022 / REQ-023) — eliminated per Financial Management §3.08 D-4
- Geolocation check-in for field workers (KBM REQ-028 — tablet/mobile, supports geolocation check-in)

**Pivot-explicit; standard capability carried forward for the merged company:**

- Lot-numbered inventory tracking, multi-bin receiving, virtual locations, drag-and-drop bin assignment (Pivot REQ-3.01.01 through REQ-3.01.07)
- Manual receiving triggers approximately 7 days after vendor invoice for audit compliance (Pivot REQ-3.01.05)
- Mystery Product location and inventory-adjustment workflow (Pivot REQ-3.01.04)
- Future CAM / RF Smart License Plating integration consideration (Pivot REQ-3.01.06; SnapTracker not integrated with Orion)
- Badging / tagging tracking for site access certifications (Pivot REQ-3.02.01)
- Skills matrix tracking for resource capabilities (Pivot REQ-3.02.02)
- Daily route planning for Northern and Southern California delivery trucks integrated with work-order system (Pivot REQ-3.02.03 / REQ-3.02.06)
- PO group-based work order creation with phased installation support (40%/40%/20%) and multiple work order events per work order (Pivot REQ-3.03.04 / REQ-3.03.05 / REQ-3.03.06)
- Custom Smart Table groupings for PO organization (Pivot REQ-3.03.03)
- Companion sales orders for punch resolution; MillerKnoll "R" designation for replacement product receiving streamlining (Pivot Assumption §3.06)
- $250 punch approval threshold (configurable; Pivot Assumption §3.06)
- PDF photo / punch reports with filtering by stamps (Pivot REQ-3.07 narrative)
- In-house dispatch and scheduling for installation crews
- Warehouse management with receiving, put-away, and inventory tracking
- Daily route planning for delivery trucks
- In-house field service with internal technicians

These are noted in the merged BRD; the merged-company operations function operates from Pivot's framework with KBM's outsourced-coordination capability layered in.

## 3.05.3 Where the two companies differ

Eight in-area divergences. Each is presented as: how each company approached it (with attribution to context), the recommendation for the merged company, and the decision the leadership team owns.

---

### D-1. Operating model — primarily internal with subcontractor support vs. coordination of outsourced contractors

**Source:** Pivot Operations BRD §3.05 REQ-3.05.02 / REQ-3.05.03 (`pivot-brds-md/Operations.md:836-840` / `:884-890`) — time tracking for employees / subcontractors / temporary resources; both full-job subcontracting and supplemental labor; KBM Operations BRD Executive Summary (`BRD_Operations_v1.0.md` Executive Summary) — outsourced installation model articulated explicitly

**KBM's approach.** KBM coordinates outsourced installation contractors. The model is explicit and KBM's BRD is built around it: receiving at remote contractor warehouses, Vendor Center for contractor communication, soft-scheduling work orders that request approval rather than hard-assign internal crews.

**Pivot's approach.** Pivot operates installation primarily in-house with its own field service team, dispatch, scheduling, warehousing, and vehicle management. Pivot's BRD explicitly supports subcontractor and supplemental labor through REQ-3.05.02 (time tracking for employees, subcontractors, and temporary resources) and REQ-3.05.03 (full-job subcontracting and supplemental labor).

**Recommendation for the merged company.** The merged-company Operations function operates from Pivot's primarily-internal model as the primary operating capability, augmented by Pivot's existing subcontractor / supplemental labor infrastructure (REQ-3.05.02 / REQ-3.05.03). The reasoning is contextual: Pivot has the existing infrastructure (field service team, warehouses, dispatch capability, vehicles, operating norms); KBM has historically coordinated external resources rather than deployed internal ones. KBM's outsourced-coordination capability (Vendor Center per REQ-007, soft-scheduling per REQ-013 / REQ-014 / REQ-015) is preserved as a complementary capability for surge capacity, geographic gaps where Pivot doesn't have installation reach, and continued relationships with KBM's third-party contractor network where those relationships deliver value. KBM's project-management and operations staff onboard into Pivot's operating model; the merged-company operations team is structured around Pivot's existing model with the addition of outsourced-coordination roles.

**Decision for the leadership team.** Confirm: Pivot's primarily-internal installation model (with subcontractor and supplemental labor support per REQ-3.05.02 / REQ-3.05.03) adopted as merged-company primary operating capability; KBM's outsourced-coordination capability preserved as complementary for surge and geographic flexibility. *Recommended default: yes.* (Specific operational org structure determined during organizational alignment.)

---

### D-2. Receiving — internal warehouse with audit-compliance triggers vs. contractor-remote

**Source:** KBM REQ-002, REQ-007, REQ-008 (`BRD_Operations_v1.0.md` §1-§2, lines 179, 372, 376); Pivot Operations BRD §3.01 REQ-3.01.01 through REQ-3.01.07 (`pivot-brds-md/Operations.md:239-251,280-298`)

**KBM's approach.** KBM articulates the Advanced Receiving Tool for receiving at remote third-party contractor warehouses (REQ-002), with a receiving notification feature where contractors notify KBM through the Vendor Center portal (REQ-007). Direct receiving by contractors is deferred to a future phase pending trust/process maturity (REQ-008).

**Pivot's approach.** Pivot operates internal warehouses with depth specified in REQ-3.01.01 through REQ-3.01.07: lot-numbered inventory tracking eliminating 900,000+ D365 locations (REQ-3.01.01), multi-bin receiving for items like conference tables with separate bases and tops (REQ-3.01.02), virtual locations for pre-sold inventory / showroom / damaged-return / third-party warehouses (REQ-3.01.03), product-returning-from-client handling via inventory adjustments and Mystery Product location with reconciliation flow (REQ-3.01.04), manual receiving triggers approximately 7 days after vendor invoice for audit compliance and liability tracking (REQ-3.01.05; applies to drop shipments only), inventory valuation reporting by location with planned RF Smart License Plating integration (REQ-3.01.06; SnapTracker explicitly not integrated with Orion per Pivot BRD), and drag-and-drop bin assignment (REQ-3.01.07).

**Recommendation for the merged company.** Operate the merged company with both receiving patterns supported. Pivot's internal warehouse receiving — including lot-numbered inventory, multi-bin assignment, virtual locations, Mystery Product handling, 7-day manual receiving trigger, and drag-and-drop assignment — is the primary pattern for operations Pivot performs. KBM's Advanced Receiving Tool (REQ-002) with contractor-remote receiving notification (REQ-007) is preserved for ongoing outsourced-installation relationships and for any geographic locations where the merged company continues to use contractor networks. The Vendor Center and contractor-notification workflow per KBM's framework remain available; direct receiving by contractors stays deferred consistent with KBM's framing (REQ-008). RF Smart License Plating evaluation is preserved as the Pivot-side path; CAM integration is Phase 2 per Pivot Assumption.

**Decision for the leadership team.** Confirm: dual receiving pattern — Pivot's internal warehouse receiving (REQ-3.01.01 through REQ-3.01.07) as primary; KBM's Advanced Receiving Tool with contractor-remote notification (REQ-002 / REQ-007) preserved for outsourced-installation work; direct receiving by contractors remains deferred (KBM REQ-008). *Recommended default: yes.*

---

### D-3. Work orders — soft scheduling vs. hard assignment, PO-group-based creation

**Source:** KBM REQ-013, REQ-014, REQ-015 (`BRD_Operations_v1.0.md` §5, lines 780, 784, 788); Pivot Operations BRD §3.03 REQ-3.03.01 through REQ-3.03.09 (`pivot-brds-md/Operations.md:525-543,581-590,616-692`)

**KBM's approach.** KBM articulates a soft-scheduling approach for work orders where requests are sent to contractors for approval rather than hard-assigned (REQ-013 / REQ-014 / REQ-015). This reflects the outsourced model where KBM doesn't directly control installation crews. Work order event types include site verification, delivery/install, site review, PM on-site, design meetings, and punch walks.

**Pivot's approach.** Pivot articulates work orders with depth across REQ-3.03.01 through REQ-3.03.09:

- Streamlined work order creation from sales order lines (REQ-3.03.01)
- Automated dashboard reminders when all POs acknowledged and ready for scheduling (REQ-3.03.02)
- Custom Smart Table groupings for PO organization by installation phase (REQ-3.03.03)
- Work order creation based on PO groups rather than line items, avoiding pallet splitting (REQ-3.03.04)
- Support for phased installations with 40%/40%/20% sequencing (Day 1, Day 3, Day 5) (REQ-3.03.05)
- Multiple work order events per single work order to accommodate phased installations without separate work orders per phase (REQ-3.03.06)
- Elimination of manual file transfer and duplication across Workfront / IQ / D365 (REQ-3.03.07) — cross-references CT-16 Workfront sunset
- Coordination workflow with installation managers replacing outside-system phone / email (REQ-3.03.08)
- Automated scheduling notifications to PC/PM upon work-order scheduling (REQ-3.03.09)

**Recommendation for the merged company.** Operate the merged company with both work-order patterns. Pivot's hard-assignment pattern with PO-group-based creation, phased installation support, dashboard reminders, custom Smart Table groupings, and multi-event work orders (REQ-3.03.01 through REQ-3.03.09) is the primary pattern for in-house installation work. KBM's soft-scheduling pattern (REQ-013 / REQ-014 / REQ-015) remains available for work orders directed to outsourced contractors. The work-order configuration supports both modes through assignment-type fields that drive the appropriate workflow. Pivot's manual-handoff elimination (REQ-3.03.07) operates against CT-16 Workfront sunset — file duplication across Workfront / IQ / D365 is removed by consolidating into Orion.

**Decision for the leadership team.** Confirm: dual work-order pattern — Pivot's hard assignment with PO-group-based creation, phased installation support, dashboard reminders, multi-event work orders for internal crews; KBM's soft scheduling for outsourced contractor coordination. *Recommended default: yes.*

---

### D-4. Field service — internal technicians vs. contractor coordination

**Source:** KBM REQ-024 through REQ-031 (`BRD_Operations_v1.0.md` §8-§9, lines 1184 onward); Pivot Operations BRD §3.07 REQ-3.07.01 through REQ-3.07.06 (`pivot-brds-md/Operations.md:1014-1100`)

**KBM's approach.** KBM articulates Field Service app deployment for PMs and contractor coordination, replacing PlanGrid (KBM REQ-024 through REQ-027 for punch list; REQ-028 through REQ-031 for broader Field Service app deployment). KBM's app supports tablet/mobile use, geolocation check-in (per REQ-028 narrative), photo and signature collection, multi-resource time entry, and offline mode with sync. KBM uses the app primarily for PM oversight of contractor work rather than for direct technician dispatch.

**Pivot's approach.** Pivot articulates Field Service app deployment for internal technicians performing installation work directly. Pivot's REQ-3.07.01 through REQ-3.07.06 cover floor plan management, document and image pinning to floor plans, photo documentation for CYA purposes, offline capability, signature capture and status reporting, and integration with main project system. Pivot's REQ-3.07 narrative also includes PDF photo / punch reports with filtering by stamps. Pivot's BRD does not specifically articulate geolocation check-in; the geolocation check-in capability is sourced from KBM REQ-028.

**Recommendation for the merged company.** Deploy the Field Service app for both internal technicians (Pivot operating model) and PM oversight of outsourced contractors (KBM operating model). The same app supports both use cases through role configuration. Internal technicians use the app for work-order receipt, time entry, photo capture, customer signature, and floor-plan management with document pinning per Pivot REQ-3.07.01 / REQ-3.07.02. PMs use the app for oversight of contractor work, punch list management, and field reporting. KBM's geolocation check-in capability (REQ-028) is added to the merged-company Field Service app deployment. PDF photo / punch reports with filtering (Pivot REQ-3.07 narrative) are configured per Pivot framework.

**Decision for the leadership team.** Confirm: Field Service app deployed for both internal technicians and PM oversight of outsourced contractor work; KBM geolocation check-in (REQ-028) and Pivot PDF photo / punch reports with filtering (REQ-3.07 narrative) carried forward. *Recommended default: yes.*

---

### D-5. Punch list management — Field Service app replacing PlanGrid; floor-plan pinning

**Source:** KBM REQ-024, REQ-025, REQ-026, REQ-027 (`BRD_Operations_v1.0.md` §8); Pivot Operations BRD §3.06 Punch List & Issue Management; §3.07 REQ-3.07.01 / REQ-3.07.02 (floor plan / pinning); Pivot Assumptions §3.06 ($250 approval threshold, MillerKnoll "R" designation) and §3.07 (PlanGrid contract concurrent with Orion Field Service during transition; license expires 1/10/2027)

**KBM's approach.** KBM articulates Field Service app punch-list capability replacing PlanGrid (a separate subscription, REQ-024 through REQ-027). The capability includes floor-plan location pinning identified as a critical feature, offline mode, and field report generation.

**Pivot's approach.** Pivot articulates punch-list capability within its broader Field Operations framework (REQ-3.07.01 floor plan management, REQ-3.07.02 document and image pinning to floor plans). Pivot's Punch List & Issue Management section (§3.06) includes companion sales orders for punch resolution, $250 approval threshold (configurable post-go-live), and MillerKnoll "R" designation for replacement-product receiving streamlining. Pivot's Assumption explicitly: PlanGrid contract runs concurrent with Orion Field Service during the transition period; PlanGrid license expires 1/10/2027.

**Recommendation for the merged company.** Adopt the Field Service app punch-list capability per KBM's framework as the merged-company default with floor-plan location pinning (KBM REQ-024 through REQ-027 + Pivot REQ-3.07.01 / REQ-3.07.02). PlanGrid runs in parallel during the transition; PlanGrid retirement is timed against contract expiration (current Pivot license date 1/10/2027 per Pivot Assumption). Pivot's Punch List management framework (companion sales orders, $250 approval threshold, MillerKnoll "R" designation) is integrated as part of the merged-company punch-list workflow.

**Decisions for the leadership team.**

- (5a) Confirm: Field Service app punch list as merged-company default with floor-plan location pinning (KBM REQ-024 through REQ-027; Pivot REQ-3.07.01 / REQ-3.07.02). *Recommended default: yes.*
- (5b) Confirm: PlanGrid retirement timed against contract expiration (1/10/2027) with parallel run during transition per Pivot Assumption. *Recommended default: yes.*
- (5c) Confirm: Pivot's punch list framework (companion sales orders, $250 approval threshold configurable post-go-live, MillerKnoll "R" designation) integrated with the merged-company punch-list workflow. *Recommended default: yes.*

---

### D-6. VRA (vendor return authorization) process — Pivot Phase 1 informal vs. KBM 80/20 formal framework

**Source:** KBM REQ-010, REQ-012 (`BRD_Operations_v1.0.md` §3, lines 550, 558); Pivot Operations BRD §3.04 REQ-3.04.01 through REQ-3.04.05 (`pivot-brds-md/Operations.md:704-714`); Pivot Assumption §3.04 (`pivot-brds-md/Operations.md:1164-1170`) — informal vendor return process to continue (no formal VRA workflow in Phase 1; revisit in Phase 2)

**KBM's approach.** KBM articulates VRA process for all damage scenarios using the 80/20 rule (REQ-010 / REQ-012) — track expected vendor credits even when product not returned. The framework solves a critical pain point of "lost" credits and provides systematic follow-up. KBM REQ-012 includes a custom Orion monthly credit aging report.

**Pivot's approach.** Pivot's BRD §3.04 identifies formal VRA as a decision point (REQ-3.04.01) and Pivot's Phase 1 Assumption explicitly states the informal vendor return process continues — no formal VRA workflow is implemented in Phase 1. Pivot may revisit formal VRA in Phase 2 based on business needs. Pivot's BRD does not articulate KBM's 80/20 rule.

**Recommendation for the merged company.** Adopt KBM's VRA process framework with the 80/20 rule (REQ-010 / REQ-012) as the merged-company default for Phase 1, **overriding** Pivot's Phase 1 informal VRA assumption. The reasoning is contextual: KBM has explicitly identified the lost-credits pain point and the 80/20 rule that solves it; the framework provides systematic follow-up via the custom Orion monthly credit aging report (KBM REQ-012); the merged-company combined damage-claim volume warrants a formal VRA workflow at Phase 1 rather than deferring it to Phase 2.

**Decision for the leadership team.** Confirm: VRA process with 80/20 rule (KBM REQ-010 / REQ-012 — track expected vendor credits even when product not returned; custom Orion monthly credit aging report) as merged-company Phase 1 default; this overrides Pivot's Phase 1 informal VRA Assumption. *Recommended default: yes.* (Pivot operations review confirms the override during the working session.)

---

### D-7. Time tracking — internal labor, subcontractors, and PM rate cards

**Source:** KBM REQ-016 through REQ-020 (`BRD_Operations_v1.0.md` §6, lines 973 onward); Pivot Operations BRD §3.05 REQ-3.05.01 through REQ-3.05.05 (`pivot-brds-md/Operations.md:834-842`); cross-references Financial Management §3.08 D-5 dual GP and Project Management §3.06 D-4 PM rate cards

**KBM's approach.** KBM articulates time tracking that impacts project GP only (not GL) per REQ-016 — payroll comes from Paylocity via CSV, time entries affect project profitability analysis, not general-ledger entries. KBM also articulates a PM flat rate structure (REQ-017 — internal cost and external billing), a design rate matrix with workshop vs. standard designer rates (REQ-018), negotiated client rates with standard internal costs (REQ-019), and external contractor time entry with reconciliation workflow (REQ-020).

**Pivot's approach.** Pivot articulates time tracking with REQ-3.05.01 through REQ-3.05.05: budget-vs-actual reporting for design and PM work (REQ-3.05.01); time tracking for employees, subcontractors, and temporary resources (REQ-3.05.02); both full-job subcontracting and supplemental labor (REQ-3.05.03); warranty / service-revenue time tracking with separate billable vs. cost-center categorization (REQ-3.05.04); project margin integration so time-tracking costs flow into project margin reports (REQ-3.05.05). Pivot's Assumption: UKG does not currently integrate with Orion.

**Recommendation for the merged company.** Operate the merged company with time tracking that feeds the dual GP framework (per Financial Management §3.08 D-5) and project profitability analysis. Time entries do not directly post to GL; payroll posts to GL via the merged-company payroll provider (cross-references Financial Management §3.08.8 #9 — provider decision). The framework supports internal technician time (Pivot model per REQ-3.05.02), subcontractor and temporary resource time (Pivot REQ-3.05.02 / REQ-3.05.03), full-job subcontracting and supplemental labor (Pivot REQ-3.05.03), warranty / service-revenue time tracking (Pivot REQ-3.05.04), and PM oversight time on outsourced contractor work (KBM model per REQ-016). PM rate-card structure (KBM REQ-017 / REQ-018 / REQ-019) — General PM, Healthcare PM, Design Workshop, Design Standard, negotiated client overrides — operates per Project Management §3.06 D-4 framework. External contractor time entry with reconciliation (KBM REQ-020) is preserved.

**Decision for the leadership team.** Confirm: time tracking feeds dual GP framework and project profitability; supports employees / subcontractors / temporary resources (Pivot REQ-3.05.02 / REQ-3.05.03), warranty / service-revenue separately (Pivot REQ-3.05.04), and PM rate-card structure (KBM REQ-017 / REQ-018 / REQ-019) per Project Management §3.06 D-4; time entries do not directly post to GL. *Recommended default: yes.*

---

### D-8. Scheduling and resource management — installation crew, route planning, badging, skills

**Source:** KBM REQ-032 through REQ-034 (`BRD_Operations_v1.0.md` §10, lines 1955 onward) — defers to additional discovery session; Pivot Operations BRD §3.02 REQ-3.02.01 through REQ-3.02.06 (`pivot-brds-md/Operations.md:382-392,483-511`)

**KBM's approach.** KBM defers PM-workload-management aspects of scheduling and resource management to an additional dedicated discovery session (REQ-032 / REQ-033 / REQ-034 — see Project Management §3.06 D-4 for PM-workload-planning decision). For installation-crew scheduling specifically, KBM does not have an internal installation crew today; the soft-scheduling approach to outsourced contractors is articulated in REQ-013 / REQ-014 / REQ-015.

**Pivot's approach.** Pivot articulates installation-crew scheduling with the depth its in-house operating model requires across REQ-3.02.01 through REQ-3.02.06: badging/tagging for site access certifications (healthcare, government per REQ-3.02.01); skills matrix tracking for resource capabilities and job-complexity matching (REQ-3.02.02); daily route planning for delivery trucks in Northern and Southern California with tracking in Orion (REQ-3.02.03 — note: scoped to Pivot's two California truck routes, not multi-day project scheduling or fleet-wide vehicle utilization KPIs); resource assignment by job requirements where complex jobs require experienced leads and field cuts require specific skilled workers (REQ-3.02.05); integration between route planning and work order system (REQ-3.02.06).

**Recommendation for the merged company.** Adopt Pivot's installation-crew scheduling and resource management framework (REQ-3.02.01 through REQ-3.02.06) as the merged-company default for in-house installation work. The reasoning is contextual: Pivot has the in-house operating model that requires this depth (badging for healthcare and government site access, skills matrix for installer capabilities, daily route planning for the existing California truck routes), and the merged company inherits the model. KBM's PM-workload-management decisions (REQ-032 / REQ-033 / REQ-034) are decided in Project Management §3.06 D-4, not here. KBM's soft-scheduling approach (REQ-013 / REQ-014 / REQ-015) for outsourced contractor work is preserved per D-3.

This decision is scoped to **field-installer scheduling and route planning**. PM workload planning is decided in Project Management §3.06 D-4.

**Decision for the leadership team.** Confirm: Pivot's installation-crew scheduling framework (REQ-3.02.01 through REQ-3.02.06 — badging, skills matrix, daily route planning for Northern and Southern California trucks, route-to-work-order integration) adopted as merged-company default for field-installer scheduling; KBM PM-workload-management decisions (REQ-032 / REQ-033 / REQ-034) decided in Project Management §3.06 D-4. *Recommended default: yes.* (Specific configuration finalized during Realize phase with Pivot's operations leadership.)

---

## 3.05.4 Cross-area dependencies

| Dependency | Where it surfaced in Operations | Where it's decided |
|---|---|---|
| **15% labor markup elimination** | KBM REQ-021, REQ-022, REQ-023 (formula line for external labor) | **Financial Management (§3.08 D-4)** — labor markup eliminated |
| **Dual GP framework (actual vs. commissionable)** | Time tracking impact on project profitability (D-7) | **CRM (§3.02 D-6)** — GP framework locked; **Financial Management (§3.08 D-5)** — operationalized |
| **Project record framework** | Work order coupling, project-level financial tracking | **Project Management (§3.06 D-2)** — project record decided there |
| **PM workload planning, forecasted utilization, budget alerts** | KBM REQ-032 through REQ-034 deferred to additional discovery; Pivot REQ-3.04 / REQ-3.05 PM time tracking | **Project Management (§3.06 D-4)** — PM workload planning decided there; Operations §3.05 D-8 scoped to field-installer scheduling |
| **Document storage architecture (field reports, signed photos, completion certificates, site-condition documentation, floor plans)** | Field Service app outputs (REQ-3.07.03 / REQ-3.07.05) and KBM Field Service app field-report generation (REQ-024 through REQ-027) | **System Setup & Configuration (§3.10 D-3)** — CT-14 lock: SharePoint for collaboration documents (floor plans, design files, site-condition photos, completion documentation); File Cabinet for transactional documents; KBM Google Drive sunset |
| **Workfront / IQ / D365 sunset and historical work-order migration** | Pivot REQ-3.03.07 — elimination of manual file transfer and duplication across Workfront / IQ / D365; Pivot Assumption §3.03 (Workfront and IQ retired after Orion go-live; only active/open work orders migrated) | **Project Management (§3.06 D-1)** — Workfront sunset / CT-16; **System Setup & Configuration (§3.10 D-5)** — historical data migration scope |
| **Approval workflow framework** | Purchase requisition approval (KBM REQ-001); $250 punch approval threshold (Pivot Assumption §3.06) | **Order Management (§3.04 D-1)** |
| **Acknowledgement workflow** | Work-order scheduling depends on PO acknowledgements (Pivot REQ-3.03.02 dashboard reminders); KBM REQ-039 ServiceNet acknowledgements | **Order Management (§3.04)** — acknowledgement framework owned there (PO acknowledgement processing, MillerKnoll Order Manager); Operations references for receiving / work-order operational handoff |
| **PO generation framework — direct PO from SIF, draft PO, requisition workflows** | Purchase requisition approval (KBM REQ-001) overlaps with Pivot's PO generation depth | **Order Management (§3.04 D-8)** — PO generation framework owned there |
| **Vendor management** | Outsourced installation contractor records, vendor credits, VRA | **Financial Management (§3.08)** — vendor master; cross-references CRM §3.02 D-4 multi-company model; **Pre-Quote (§3.03 D-3)** — vendor management for service providers (union / location / parent-child / intermarket filtering) |
| **Vendor credit limit framework (90% threshold, hard-stop with override)** | Cross-reference to procurement controls | **Order Management (§3.04 D-8b)** — owned in Order Management per CT-12; **Financial Management (§3.08 D-9)** — credit-policy governance cross-reference |
| **Payroll provider** | Time-entry-to-payroll integration; Pivot Assumption — UKG does not currently integrate with Orion | **Financial Management §3.08.8 #9** — merged-company payroll provider decision |
| **Multi-Design-Center / multi-warehouse configuration** | Pivot's California Design Centers (Santa Clara, Fremont, San Francisco, Costa Mesa, Los Angeles, La Mirada) + KBM's territories | **System Setup & Configuration (§3.10 D-4)** — Sales Locations / location taxonomy; **CRM (§3.02 D-3a)** — geographic dimension |
| **RFP coordination — task / resource and project / folder timing (CT-8)** | Operations is one of the candidate owners per CT-8 | **CT-8** — Pre-Quote and/or Operations decide task/resource and folder timing |
| **Delivery / installation contact attribution (CT-11)** | Field service app captures customer signatures and contact information at delivery / installation events | **CT-11** — multi-company / multi-contact relationship model: delivery contact captured per event with source attribution |

## 3.05.5 Recommendation summary

The merged-company Operations playbook in shorthand:

- **Operating model:** Pivot's primarily-internal installation model (with subcontractor / supplemental labor support per REQ-3.05.02 / REQ-3.05.03) as primary; KBM's outsourced-coordination capability preserved for surge and geographic flexibility
- **Receiving:** Dual pattern — Pivot's internal warehouse receiving (REQ-3.01.01 through REQ-3.01.07 — lot inventory, multi-bin, virtual locations, Mystery Product, 7-day manual trigger, drag-and-drop) as primary; KBM's Advanced Receiving Tool (REQ-002) with contractor-remote notification (REQ-007) preserved for outsourced installation work
- **Work orders:** Dual pattern — Pivot's hard assignment with PO-group-based creation, phased installation 40%/40%/20%, dashboard reminders, multi-event work orders (REQ-3.03.01 through REQ-3.03.09) for internal crews; KBM's soft scheduling (REQ-013 / REQ-014 / REQ-015) for outsourced contractor coordination
- **Field Service app:** Deployed for both internal technicians and PM oversight; KBM geolocation check-in (REQ-028); Pivot floor-plan management with document pinning, PDF photo / punch reports with filtering (REQ-3.07.01 through REQ-3.07.06)
- **Punch list:** Field Service app punch list with floor-plan location pinning; companion sales orders, $250 approval threshold (configurable), MillerKnoll "R" designation per Pivot Assumption; PlanGrid retired against 1/10/2027 contract expiration
- **VRA process:** KBM 80/20 framework (REQ-010 / REQ-012) overrides Pivot Phase 1 informal VRA Assumption; custom Orion monthly credit aging report
- **Time tracking:** Feeds dual GP framework and project profitability; supports employees / subcontractors / temporary resources / supplemental labor (Pivot REQ-3.05.02 / REQ-3.05.03), warranty / service-revenue separately (Pivot REQ-3.05.04), PM rate-card structure (KBM REQ-017 / REQ-018 / REQ-019); not directly to GL
- **Scheduling and resource management:** Pivot framework (REQ-3.02.01 through REQ-3.02.06 — badging, skills matrix, daily route planning for Northern and Southern California trucks) for field-installer scheduling; PM workload planning decided in Project Management §3.06 D-4
- **Vendor Center:** Standard NetSuite for contractor communication
- **Receiving notification:** Custom Orion enhancement per KBM framework (REQ-007)
- **Document storage:** SharePoint for floor plans / design / collaboration; File Cabinet for transactional documents per CT-14 / System Setup §3.10 D-3
- **Workfront / IQ / D365 sunset:** Operations cooperates with CT-16 by eliminating manual handoffs (Pivot REQ-3.03.07); historical data migration scope per System Setup §3.10 D-5

Net read: the merged-company Operations function operates primarily from Pivot's framework because Pivot has the existing infrastructure and operational depth (REQ-3.01 through REQ-3.07 across seven sections). KBM's outsourced-coordination capability is preserved and integrated as a complementary capability for the merged-company operating model; KBM's specific contributions include the VRA 80/20 rule (overriding Pivot Phase 1 informal Assumption), soft-scheduling for outsourced contractor coordination, contractor-remote receiving notification, geolocation check-in on the Field Service app, and the PM rate-card structure for time tracking.

## 3.05.6 Decisions for the leadership team

| # | Decision | Default | Reference |
|---|---|---|---|
| 1 | Pivot's primarily-internal installation model (with subcontractor / supplemental labor support per REQ-3.05.02 / REQ-3.05.03) as primary; KBM's outsourced-coordination preserved as complementary | Yes | D-1 |
| 2 | Dual receiving pattern (Pivot REQ-3.01.01 through REQ-3.01.07 + KBM REQ-002 / REQ-007 contractor-remote notification; KBM REQ-008 contractor direct receiving deferred) | Yes | D-2 |
| 3 | Dual work-order pattern (Pivot REQ-3.03.01 through REQ-3.03.09 hard assignment for internal; KBM REQ-013 / REQ-014 / REQ-015 soft scheduling for outsourced) | Yes | D-3 |
| 4 | Field Service app for internal technicians and PM oversight; KBM geolocation check-in (REQ-028) and Pivot PDF photo / punch reports with filtering (REQ-3.07 narrative) carried forward | Yes | D-4 |
| 5a | Field Service app punch list with floor-plan pinning (KBM REQ-024 through REQ-027; Pivot REQ-3.07.01 / REQ-3.07.02) | Yes | D-5 |
| 5b | PlanGrid retirement timed against contract expiration (1/10/2027) with parallel run | Yes | D-5 |
| 5c | Pivot punch list framework (companion sales orders, $250 approval threshold configurable, MillerKnoll "R" designation) integrated | Yes | D-5 |
| 6 | VRA process with KBM 80/20 framework (REQ-010 / REQ-012) overrides Pivot Phase 1 informal VRA Assumption; custom Orion monthly credit aging report | Yes | D-6 |
| 7 | Time tracking feeds dual GP framework and project profitability; supports Pivot REQ-3.05.02 / REQ-3.05.03 / REQ-3.05.04 plus KBM REQ-017 / REQ-018 / REQ-019 PM rate-card structure | Yes | D-7 |
| 8 | Pivot installation-crew scheduling framework (REQ-3.02.01 through REQ-3.02.06) for field-installer scheduling; PM workload planning decided in Project Management §3.06 D-4 | Yes | D-8 |

> 11 decisions across 8 divergences, all with default-yes recommendations. Specific configurations and operational org structure (org structure for the merged operations function, PlanGrid transition, scheduling depth, payroll integration mechanics, VRA Phase 1 override confirmation) are determined during organizational alignment and Realize phase.

## 3.05.7 Configuration carryover

| Item | KBM-side built? | Pivot-side built? | Action for merged company |
|---|---|---|---|
| In-house installation operating model | Not built (KBM uses outsourced contractors) | Existing infrastructure | Operate per Pivot model per D-1 |
| Subcontractor / supplemental labor support | Not articulated | Specified (Pivot REQ-3.05.02 / REQ-3.05.03) | Configure per D-1 / D-7 |
| Outsourced-contractor coordination via Vendor Center | Specified (REQ-007) | Not specified | Configure per D-1 (preserved capability) |
| Lot-numbered inventory / multi-bin / virtual locations / Mystery Product | Not specified | Specified (REQ-3.01.01 through REQ-3.01.04) | Build per D-2 |
| Drag-and-drop bin assignment | Specified (REQ-002 — Advanced Receiving Tool) | Specified (REQ-3.01.07) | Configure per common-ground |
| 7-day manual receiving trigger for audit compliance | Not specified | Specified (REQ-3.01.05) | Configure per D-2 |
| RF Smart License Plating evaluation | Not specified | Specified (REQ-3.01.06; SnapTracker not integrated; CAM Phase 2) | Configure per D-2 |
| Receiving notification feature (contractor-initiated arrivals) | Specified (REQ-007 — Custom Orion Enhancement) | Not specified | Configure per D-2 (preserved for outsourced) |
| Direct receiving by contractors | Deferred to future phase (REQ-008) | Not articulated | Remain deferred per D-2 |
| Work orders — soft scheduling | Specified (REQ-013 / REQ-014 / REQ-015) | Not specified | Configure per D-3 (preserved for outsourced) |
| Work orders — hard scheduling with PO-group-based creation | Not specified | Specified (REQ-3.03.01 through REQ-3.03.09) | Configure per D-3 (primary for internal) |
| Phased installation support (40%/40%/20%) | Not specified | Specified (REQ-3.03.05) | Build per D-3 |
| Multiple work order events per work order | Not specified | Specified (REQ-3.03.06) | Build per D-3 |
| Dashboard reminders when POs acknowledged | Not specified | Specified (REQ-3.03.02) | Build per D-3 |
| Custom Smart Table groupings for PO organization | Implicit (KBM REQ-008 SIF Smart Table grouping) | Specified (REQ-3.03.03) | Build per D-3 |
| Field Service app | Specified (Custom Orion Solution; replaces PlanGrid; REQ-024 through REQ-031) | Specified (REQ-3.07.01 through REQ-3.07.06) | Build per D-4, D-5 |
| Geolocation check-in | Specified (KBM REQ-028) | Not specified | Configure per D-4 |
| Floor-plan management with document and image pinning | Specified (KBM REQ-024 through REQ-027 — floor-plan location pinning critical) | Specified (REQ-3.07.01 / REQ-3.07.02) | Build per D-4, D-5 |
| PDF photo / punch reports with filtering by stamps | Not specified | Specified (REQ-3.07 narrative) | Configure per D-4 |
| Companion sales orders for punch | Not specified | Specified (Pivot Assumption §3.06) | Configure per D-5c |
| $250 punch approval threshold (configurable) | Not specified | Specified (Pivot Assumption §3.06) | Configure per D-5c |
| MillerKnoll "R" designation for replacement product | Not specified | Specified (Pivot Assumption §3.06) | Configure per D-5c |
| PlanGrid retirement | Specified | Specified (1/10/2027 expiration; parallel run during transition) | Time per D-5b |
| VRA process with 80/20 rule | Specified (REQ-010 / REQ-012) — formal VRA + custom Orion monthly credit aging report | Phase 1 informal VRA Assumption | Configure per D-6 (overrides Pivot Phase 1 Assumption) |
| Time tracking with project-GP impact | Specified (REQ-016 through REQ-020) | Specified (REQ-3.05.01 through REQ-3.05.05) | Configure per D-7 |
| PM rate-card structure (General / Healthcare / Workshop / Standard / Negotiated) | Specified (KBM REQ-017 / REQ-018 / REQ-019) | Specified at PM level (Pivot Project Management §3.06 D-4) | Configure per D-7 / Project Management §3.06 D-4 |
| External contractor time entry with reconciliation | Specified (KBM REQ-020) | Not specified | Configure per D-7 |
| Warranty / service-revenue time tracking | Not specified | Specified (REQ-3.05.04) | Configure per D-7 |
| UKG payroll integration | KBM uses Paylocity (REQ-016 — CSV) | Not currently integrated (Pivot Assumption §3.05) | Decide merged-company payroll provider per Financial Management §3.08.8 #9 |
| Installation-crew scheduling — badging, skills matrix, daily route planning | Not built (no in-house crews) | Specified (REQ-3.02.01 through REQ-3.02.06) | Build per D-8 |
| 15% labor markup formula line | Specified (REQ-021 / REQ-022 / REQ-023) | Not present | Eliminate per Financial Management §3.08 D-4 |
| Manual handoff elimination across Workfront / IQ / D365 | Not specified | Specified (REQ-3.03.07) | Cooperate with CT-16 Workfront sunset |

## 3.05.8 Open questions / inputs needed

1. **Operational org structure for the merged company** (decision 1) — determined during organizational alignment with both leadership teams' input.
2. **VRA Phase 1 override confirmation** (decision 6) — Pivot operations leadership confirms the override of Pivot's Phase 1 informal VRA Assumption during the working session.
3. **KBM staff onboarding into Pivot's operating model** — change-management plan and timing finalized during organizational alignment.
4. **Continuing third-party contractor relationships** (decision 1) — which KBM contractor relationships continue post-merger, surge-capacity arrangements, geographic-coverage gaps determined operationally.
5. **Geolocation check-in and offline-mode field service requirements** — specific configuration details finalized during Realize phase.
6. **Floor-plan location pinning** (decision 5a) — technical configuration and any custom Orion enhancement details documented during Realize phase.
7. **Receiving-notification workflow specifics** (decision 2) — alert recipients, response procedures, and contractor-portal access patterns finalized during Realize phase.
8. **Pivot operations stakeholder review** — Pivot operations leadership reviews merged-company recommendations before the working session.
9. **KBM unresolved Operations inputs** (`BRD_Operations_v1.0.md:2111-2128`) — work-order final confirmation, rate matrix, contractor access / time-entry lists, warehouse locations, damaged-product accounting, PlanGrid report examples, floor-plan formats; collected during configuration.
10. **Merged-company payroll provider** (decision 7) — UKG vs. Paylocity vs. other for the merged company; decision per Financial Management §3.08.8 #9.
11. **CAM integration / RF Smart License Plating** (decision 2) — Phase 2 evaluation per Pivot Assumption §3.01.
12. **Delivery / installation contact attribution per CT-11** — confirm field-service-app capture pattern aligns with multi-company / multi-contact relationship model.
