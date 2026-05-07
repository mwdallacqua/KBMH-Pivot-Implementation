# 3.06 — Project Management

| Field | Value |
|---|---|
| **Decision density** | **High** — Workfront sunset to Orion-native project execution; Pivot has substantial Workfront-based project management infrastructure; KBM does not have a separate project-management platform. The merged-company decisions are transition shape and capability-replacement scope |
| **Source coverage** | Pivot Project Management BRD v2.0 (full BRD — Pivot operates Workfront for project management); KBM does not have a separate project-management BRD because project work has been coordinated through PMs without a dedicated platform |
| **KBM source** | No separate BRD; project-management-related capabilities surface in other KBM BRDs — PM workload management and resource visualization (Operations BRD §10, REQ-032 / REQ-033 / REQ-034, all DEFERRED to additional discovery), project request workflow (Marketing §3.01 D-8, Pre-Quote §3.03), project record references (CRM §3.02), and Operations work orders / time tracking (Operations BRD §5 / §6) |
| **Pivot BRD** | `Project Management/Pivot/4 BRD/10_Pivot Interiors BRD Project Management and Workfront Process Area_v2.0.docx` (markdown copy at `_Unification/working/pivot-brds-md/Project_Management.md`) |

---

## 3.06.1 How each company approaches Project Management today

**KBM Hogue** does not operate a dedicated project-management platform. Project coordination happens through PMs working in Asana (for RFP request management — see Marketing §3.01 D-8), Google Drive (for project documentation), email and meetings, and the Core ERP for transactional project tracking. KBM's BRDs do not include a separate Project Management process area because the function has been distributed across other tools and roles. KBM's PMs are involved in Operations (per §3.05), Pre-Quote (per §3.03), and customer-relationship coordination (per CRM §3.02) without a single platform that consolidates project execution.

**Pivot Interiors** operates Adobe Workfront as the dedicated project-management platform. Pivot's BRD documents Workfront-based activity including work-order scheduling against approved labor budgets (Pivot Project Management BRD §3.02, REQ-3.02.01 through REQ-3.02.06), PM time tracking with rate-card cost calculation and budget-to-actual alerting (§3.04, REQ-3.04.01 through REQ-3.04.07), project KPI reporting and forecasted utilization (§3.05, REQ-3.05.01 through REQ-3.05.07), and SharePoint-based document management with vendor portal access for external design partners (§3.06, REQ-3.06.01 through REQ-3.06.07). Pivot's BRD identifies Workfront as a tool the team relies on heavily; Pivot's stated direction (BRD §2.01) is that NetSuite Orion replaces Workfront. Pivot's BRD also names IPMs (Integrated Project Managers) as a role tier handling complex projects, with sales coordinators handling transactional work (Pre-Quote §3.03 D-8 cross-reference).

Pivot's Project Management BRD source-direction is that NetSuite Orion replaces Workfront, and the merged company carries that direction forward. Workfront sunsets; Pivot's project-management activity migrates into NetSuite Orion's native project record framework, augmented with custom enhancements as needed. The merged-company decisions at the working session concern transition shape — sunset timeline, capability-replacement scope (which Workfront features must be present in Orion at cutover vs. phased afterward), and Pivot PM team migration plan — not whether Workfront is retained.

## 3.06.2 Where the two companies align

**Explicit in both BRDs/source materials:**

- Project record as the aggregation layer for transactional data (per the approach document principle that operational data lives on transaction records and project records aggregate)
- Project-level financial tracking (revenue, cost, GP) with budget-vs-actual reporting
- Project documentation attachment via NetSuite File Cabinet or integrated external storage
- Time tracking against projects with project-GP impact

**KBM-implicit; standard NetSuite Orion capability carried forward:**

- NetSuite Orion's native project record (Pre-Quote §3.03 D-4 references this; Operations §3.05 D-7 references project-GP impact)
- Project-level KPI dashboards (per BI §3.09 D-4)

**Pivot-explicit; Workfront-attested capabilities being replaced in Orion native:**

- Work order scheduling against approved labor budgets with capacity display (Pivot BRD §3.02 REQ-3.02.01)
- Project-subproject numbering convention (6-digit project + 2-digit suffix) (Pivot BRD §3.02 REQ-3.02.02)
- PM time tracking with two-tier rate cards (General PM, Healthcare PM) and automated cost calculation (Pivot BRD §3.04 REQ-3.04.01 through REQ-3.04.05)
- Budget-to-actual reporting with 80% / 100% alert thresholds (Pivot BRD §3.04 REQ-3.04.06; §3.02 REQ-3.02.06)
- Forecasted utilization by PM and installation month (Pivot BRD §3.05 REQ-3.05.02)
- SharePoint document management with vendor portal access for external design partners (Pivot BRD §3.06 REQ-3.06.01 through REQ-3.06.07)
- IPM (Integrated Project Manager) role taxonomy (Pivot Pre-Quote BRD §3.03 D-8 cross-reference)

## 3.06.3 Where the two companies differ

Five in-area divergences. The first is the platform-architecture decision; the others depend on it.

---

### D-1. Project-management platform — Orion-native consolidation with Workfront sunset

**Source:** Pivot Project Management BRD §2.01 (NetSuite Orion will replace Workfront); §3.02, §3.04, §3.05, §3.06 (Workfront-attested capabilities being migrated); KBM source materials (no separate Project Management BRD)

**KBM's approach.** KBM does not operate a dedicated project-management platform. Project coordination happens through PMs working in Asana, Google Drive, email, and Core ERP. The merged-company project-management capability is therefore not constrained by an existing KBM platform.

**Pivot's approach.** Pivot operates Workfront for work-order scheduling, PM time tracking, budget-to-actual alerting, and forecasted utilization (Pivot BRD §3.02 REQ-3.02.01 through REQ-3.02.06; §3.04 REQ-3.04.01 through REQ-3.04.07; §3.05 REQ-3.05.01 through REQ-3.05.07). Pivot's PMs (including IPMs) work primarily in Workfront. Sherri Nuzum is named in the Pre-Quote BRD as a key Workfront knowledge-holder.

**Recommendation for the merged company.** Project management consolidates into NetSuite Orion's native project record framework, augmented with custom enhancements for work-order scheduling, time-and-rate-card tracking, budget-to-actual alerting, and forecasted utilization. Workfront is sunset on a defined transition timeline. Pivot's PM team migrates to Orion-native execution; KBM's PMs onboard into the same consolidated environment. The recommendation is grounded in Pivot's own Project Management BRD source-direction (NetSuite Orion replaces Workfront, BRD §2.01), the merged company's platform-consolidation goal, and the ongoing license and integration overhead that retaining Workfront would carry into a multi-platform architecture (Workfront + NetSuite + HubSpot per Marketing §3.01 D-1).

The merged-company decision at the working session is the **transition shape**, not the platform choice. Leadership confirms the sunset direction and decides on capability-replacement scope (which Workfront features must be present in Orion at cutover vs. phased after) and Workfront sunset timeline.

Risk: replicating Workfront's project-management depth in Orion native requires custom enhancement and a measured transition for Pivot's PM team. The transition plan front-loads the capabilities the team relies on most heavily and supports Pivot PM team continuity through cutover.

**Decisions for the leadership team.**

- (1a) Confirm: project management consolidates into NetSuite Orion native; Workfront sunsets on a defined transition timeline. *Recommended default: yes.*
- (1b) Decide: capability-replacement scope at cutover (which Workfront features must be present in Orion at go-live vs. phased afterward) and Workfront sunset timeline. *Recommended default: scope and timeline refined at the working session with Pivot PM team input.*

---

### D-2. Project record framework

**Source:** NetSuite Orion native project record (referenced in Pre-Quote §3.03 D-4, Operations §3.05 D-7, Financial Management §3.08 D-5, BI §3.09 D-4); Pivot Project Management BRD §3.02 (project-subproject numbering REQ-3.02.02), §3.04 (time tracking REQ-3.04.01 through REQ-3.04.07), §3.06 (document architecture REQ-3.06.01)

**KBM's approach.** KBM relies on NetSuite Orion's native project record as the financial-and-reporting aggregation layer for transactional data.

**Pivot's approach.** Pivot uses NetSuite Orion's project record for financial tracking with execution data currently residing in Workfront. Per D-1, execution data migrates to the Orion project record on the Workfront sunset timeline.

**Recommendation for the merged company.** Operate the merged company with NetSuite Orion's native project record as the financial-and-reporting aggregation layer and the system of record for project execution after the Workfront sunset. Project-level revenue and cost tracking, dual GP reporting (per Financial Management §3.08 D-5), project KPI dashboards (per BI §3.09 D-4), and project execution data (status, milestones, time, resource utilization) all operate from the Orion project record once consolidation completes. Pivot's existing project-subproject numbering convention (6-digit project + 2-digit suffix per Pivot BRD §3.02 REQ-3.02.02) carries forward as the merged-company numbering standard.

**Decision for the leadership team.** Confirm: NetSuite Orion native project record as merged-company financial-and-reporting aggregation layer and project-execution system of record. *Recommended default: yes.*

---

### D-3. IPM role and project-team taxonomy

**Source:** Pivot Pre-Quote BRD §3.03 D-8 (IPM-and-sales-coordinator routing model); Pivot Project Management BRD references IPMs in §3.04 (time tracking) and §3.05 (forecasted utilization by PM); KBM PMs not categorized into the same role tiers (KBM Operations BRD §10 deferred PM workload management)

**KBM's approach.** KBM's project coordination roles are PMs without the IPM-specific categorization; coordination work spans Operations, Pre-Quote, and customer relationship management.

**Pivot's approach.** Pivot articulates IPMs as a role tier handling complex projects, with sales coordinators handling transactional work. The IPM role is named in multiple BRDs.

**Recommendation for the merged company.** The IPM-and-sales-coordinator routing model is locked in Pre-Quote §3.03 D-8 as the merged-company default. Project Management inherits the locked routing model and applies it to project-team assignment. KBM's PM staff are categorized into IPM or sales-coordinator roles based on the work they handle; specific role assignments for KBM staff are determined during organizational alignment.

**No additional decision required at the leadership team for routing model itself.** The IPM-and-sales-coordinator routing model is already locked at Pre-Quote §3.03 D-8. Project Management uses the locked model; KBM staff role assignments occur during organizational alignment.

---

### D-4. PM workload planning and forecasted utilization

**Source:** Pivot Project Management BRD §3.05 REQ-3.05.02 (forecasted utilization by PM, workload by installation month); §3.04 REQ-3.04.06 (budget-to-actual reporting with 80%/100% alerts); KBM Operations BRD §10 REQ-032 (PM task list automation, ADAPT, deferred), REQ-033 (resource visualizer with calendar view of PM workloads, ACCOMMODATE, deferred), REQ-034 (task management sophistication level, ADAPT, deferred)

**KBM's approach.** KBM has articulated PM workload planning needs in Operations BRD §10 — Wendy's Google Sheets calendar tracks PM workloads today; REQ-032/033/034 ask for PM task automation, a resource visualizer with calendar view, and a decision on task-management sophistication. KBM deferred those decisions to a follow-up discovery session because the team has not aligned on rigor (10 phases vs. 300 tasks per Matt Denning's framing).

**Pivot's approach.** Pivot's BRD specifies PM-workload visibility in Workfront — forecasted utilization by PM and by installation month (REQ-3.05.02) and budget-to-actual reporting with 80% PM notification and 100% leadership escalation (REQ-3.04.06). The reporting feeds Pivot's PM assignment process and identifies over-allocation.

**Recommendation for the merged company.** Adopt Pivot's PM-workload-planning framework — forecasted utilization, budget-to-actual alerting at 80% / 100% thresholds, and assignment-by-capacity logic — built in Orion's project module with custom enhancements during the Workfront sunset transition. KBM's deferred PM-workload decisions (REQ-032/033/034) are resolved by adopting the Pivot framework as the merged-company starting point; the working session decides on task-management sophistication (the rigor question Matt raised in Operations BRD §10) and how the framework configures for KBM staff.

This decision is scoped to **PM workload planning** — assigning PMs to projects, tracking PM hours against project budgets, and forecasting PM capacity. It does not include field-installer scheduling, which is decided in Operations §3.05 D-8 (scheduling and resource management for field installers).

**Decision for the leadership team.** Confirm: Pivot's PM-workload-planning framework (forecasted utilization, budget-to-actual alerting, capacity-based assignment) adopted as merged-company default; task-management sophistication level (KBM REQ-034 / Operations BRD §10 question) decided at the working session. *Recommended default: yes; sophistication level decided at working session.*

---

### D-5. Project status visibility and dashboards

**Source:** Pivot Project Management BRD §3.05 REQ-3.05.01 through REQ-3.05.07 (real-time KPI dashboards, Job Status Report redesign, PM team self-service report creation, Power BI integration with Kevin Baugh's dashboards, three-month rolling-average calculations); cross-references BI §3.09 D-4 (360 dashboards including Project Performance 360)

**KBM's approach.** KBM articulates project-level KPI dashboards within BI §3.09 D-4 (Project Performance 360 dashboard).

**Pivot's approach.** Pivot articulates project-status dashboards in Workfront with status, milestone, timeline, and resource visibility, plus separate Project Performance 360 dashboard within NetSuite for financial KPIs (per BI §3.09 D-4).

**Recommendation for the merged company.** Operate the merged company with NetSuite Orion as the system of record for both project financial KPIs (Project Performance 360 dashboard per BI §3.09 D-4) and project execution status (timeline, milestones, resource utilization). Execution-status and financial-status dashboards both reside in Orion after the Workfront sunset. Custom enhancements deliver the execution-visibility depth Pivot's PMs rely on today.

**Decision for the leadership team.** Confirm: NetSuite Orion as system of record for project financial KPIs and project execution status. *Recommended default: yes.*

---

## 3.06.4 Cross-area dependencies

| Dependency | Where it surfaced in Project Management | Where it's decided |
|---|---|---|
| **Project record framework (Orion-native execution)** | D-2 | **Project Management (§3.06 D-2)** — decided here; project financial KPIs cross-reference **BI (§3.09 D-4)** — Project Performance 360 dashboard; project accounting cross-references **Financial Management (§3.08)** |
| **IPM and sales-coordinator routing** | D-3 | **Pre-Quote (§3.03 D-8)** — routing model locked; Project Management uses the model |
| **Field-installer scheduling and resource management** | D-4 PM-workload scope; field installers separate | **Operations (§3.05 D-8)** — field-installer scheduling decided there; PM workload planning decided here in D-4 |
| **Time tracking (project-GP impact)** | Time tracking against project tasks | **Operations (§3.05 D-7)** — time tracking framework decided; PM rate-card structure (General PM / Healthcare PM per Pivot REQ-3.04.04) configured here |
| **Document storage architecture (project documents)** | Project documentation, contracts, drawings, vendor portal access | **System Setup & Configuration (§3.10 D-3)** — CT-14 lock: SharePoint for collaboration documents (project drawings, design files, vendor portal — Pivot Vendor Portal per REQ-3.06.02 / REQ-3.06.03); File Cabinet for transactional documents; KBM Google Drive sunset |
| **Multi-company / multi-contact relationship model** | Project-level customer / vendor / influencer relationships | **CRM (§3.02 D-4)** — relationship model locked |
| **GP framework (actual vs. commissionable)** | Project profitability reporting | **CRM (§3.02 D-6)** — GP framework locked |
| **Division taxonomy** | Vendor portal permissions reference Pivot portfolios (Venture / Healthcare / Education / Enterprise) and studios (NorCal / Healthcare / SoCal) per REQ-3.06.03 | **CRM (§3.02 D-3b)** — final merged-company taxonomy; vendor portal permissions configure against confirmed taxonomy |
| **Workfront sunset and data migration** | Project, task, time, and capacity data migration from Workfront to Orion native | **System Setup & Configuration (§3.10 D-5)** — historical data migration scope; transition plan owned in Project Management D-1 |

## 3.06.5 Recommendation summary

The merged-company Project Management playbook in shorthand:

- **Platform architecture:** NetSuite Orion native project record consolidation; Workfront sunsets on a defined transition timeline (Pivot BRD §2.01 source-direction)
- **Project record:** NetSuite Orion native project record as financial-and-reporting aggregation layer and project-execution system of record; Pivot's 6-digit + 2-digit project-subproject numbering convention carried forward (Pivot BRD §3.02 REQ-3.02.02)
- **Role taxonomy:** IPM-and-sales-coordinator routing per Pivot framework (Pre-Quote §3.03 D-8); KBM staff role assignments during organizational alignment
- **PM workload planning:** Pivot framework adopted — forecasted utilization (REQ-3.05.02), budget-to-actual alerting at 80%/100% thresholds (REQ-3.04.06), capacity-based PM assignment; KBM REQ-032/033/034 resolved by adopting Pivot framework as starting point; task-management sophistication decided at working session
- **PM time tracking and rate cards:** Two-tier rate cards (General PM, Healthcare PM per Pivot REQ-3.04.04); automated cost calculation; project / admin time split (Pivot REQ-3.04.03)
- **Project status dashboards:** NetSuite Orion for both project financial KPIs (Project Performance 360 per BI §3.09 D-4) and project execution status; Pivot's Power BI integration (REQ-3.05.05) carried forward via data warehouse connectivity (REQ-3.06.05)
- **Document storage:** SharePoint for project drawings / design files / vendor portal documents (CT-14, Pivot REQ-3.06.01 through REQ-3.06.07); File Cabinet for transactional project documents
- **Time tracking:** Per Operations §3.05 D-7 framework; feeds dual GP and project profitability

Net read: project management is a substantial operational transition in the unification because Pivot's PMs work primarily in Workfront today. The recommendation commits to Orion-native consolidation in line with Pivot's own BRD direction (BRD §2.01); the working-session decisions are about transition shape — capability-replacement scope at cutover, sunset timeline, task-management sophistication level, and Pivot PM team migration plan — not about whether Workfront is retained.

## 3.06.6 Decisions for the leadership team

| # | Decision | Default | Reference |
|---|---|---|---|
| 1a | Project management consolidates into NetSuite Orion native; Workfront sunsets on a defined transition timeline | Yes | D-1 |
| 1b | Capability-replacement scope at cutover and Workfront sunset timeline | Refine at working session with Pivot PM team input | D-1 |
| 2 | NetSuite Orion native project record as merged-company financial-and-reporting aggregation layer and project-execution system of record (Pivot 6-digit + 2-digit project-subproject numbering carried forward) | Yes | D-2 |
| 3a | Pivot PM-workload-planning framework adopted (forecasted utilization, budget-to-actual alerting at 80%/100%, capacity-based PM assignment) — scoped to PM workload, not field installer scheduling | Yes | D-4 |
| 3b | Task-management sophistication level (10 phases vs. 300 tasks per KBM REQ-034 / Operations BRD §10) | Decided at working session | D-4 |
| 4 | NetSuite Orion as system of record for project financial KPIs and project execution status; Pivot Power BI integration carried forward via data warehouse connectivity | Yes | D-5 |

> 6 decisions: 4 with default-yes recommendations and 2 (decision 1b transition shape, decision 3b task-management sophistication) decided at the working session. The platform-consolidation direction is committed; the working-session focus is the transition plan and the task-management rigor question Matt Denning raised in KBM Operations BRD §10. (D-3 IPM-and-sales-coordinator routing is inherited from Pre-Quote §3.03 D-8 and does not require a separate decision here.)

## 3.06.7 Configuration carryover

| Item | KBM-side built? | Pivot-side built? | Action for merged company |
|---|---|---|---|
| Dedicated project-management platform | Not built (no platform) | Workfront in production | Sunset Workfront per D-1 transition plan; Orion native is the merged-company platform |
| NetSuite Orion native project record | In progress | In progress | Configure per D-2 as financial aggregation layer and execution system of record |
| Project-subproject numbering (6-digit + 2-digit) | Not built | Built (Pivot REQ-3.02.02) | Carry forward Pivot convention; configure validation rules for project-XX format |
| PM rate cards (General PM, Healthcare PM) | Not built | Built (Pivot REQ-3.04.04) | Build two-tier rate-card structure with PM-selected rate at time entry |
| Budget-to-actual reporting with alerts (80% / 100%) | Specified, deferred (KBM REQ-032) | Built (Pivot REQ-3.04.06) | Build per Pivot framework; alert routing decided during configuration |
| Forecasted utilization by PM and installation month | Specified, deferred (KBM REQ-033) | Built (Pivot REQ-3.05.02) | Build per Pivot framework |
| PM resource visualizer (calendar view of PM workloads) | Specified, deferred (KBM REQ-033) | Built (Pivot REQ-3.05.02) | Build per Pivot framework; visual format and views decided during configuration |
| Workfront sunset and data migration | N/A | Workfront in production | Plan migration of project, task, time, and capacity data per D-1; align with System Setup §3.10 D-5 |
| IPM role taxonomy | Not present | Present | Adopt per D-3 |
| Project documents (drawings, design files, vendor portal) | Currently in KBM Google Drive | Currently fragmented across IQ / Workfront / SharePoint / file shares (Pivot BRD §3.06.02) | Consolidate to SharePoint per CT-14 / System Setup §3.10 D-3; KBM Google Drive sunset; Pivot fragmented sources consolidated |
| Pivot Vendor Portal for external design partners (Riverstone / D3 / Azusa) | N/A | Built (Pivot REQ-3.06.02 / REQ-3.06.03) | Carry forward Vendor Portal with portfolio + studio permissions; configuration aligns with merged-company division taxonomy (CRM §3.02 D-3b) |
| Power BI integration (Kevin Baugh's dashboards) | N/A | Built (Pivot REQ-3.05.05) | Maintain via Azure data warehouse connectivity (Pivot REQ-3.06.05) |
| Project Performance 360 dashboard | Specified per BI §3.09 D-4 | Specified per BI §3.09 D-4 | Build per BI §3.09 |

## 3.06.8 Open questions / inputs needed

1. **Capability-replacement scope at cutover** (decision 1b) — which Workfront features must be present in Orion at go-live (work-order scheduling, time tracking with rate cards, budget alerting, forecasted utilization, document management, vendor portal) vs. phased afterward; refined at the working session with Pivot PM team input.
2. **Workfront sunset timeline** (decision 1b) — date for Workfront subscription wind-down and the transition shape that gets the Pivot PM team there without operational disruption; refined at the working session.
3. **Task-management sophistication level** (decision 3b) — 10 phases vs. 300 tasks question raised in KBM Operations BRD §10 REQ-034 and reflected in Pivot's Workfront-task framework; decided at the working session with Wendy (KBM PM Manager), Kimmy (KBM Account Manager), and Pivot PM team representation.
4. **Budget-to-actual alert routing** — Pivot REQ-3.04.06 specifies 80% PM notification and 100% leadership escalation; specific routing (which roles receive which alerts) and notification channels (email, in-app, dashboard) decided during configuration.
5. **PM rate-card configuration** — Pivot's two-tier structure (General PM, Healthcare PM per REQ-3.04.04) carries forward; merged-company application across both companies' project mix and PM-selection logic at time entry decided during configuration.
6. **Vendor Portal permissions for merged-company division taxonomy** — Pivot's portfolio (Venture / Healthcare / Education / Enterprise) and studio (NorCal / Healthcare / SoCal) permissions per REQ-3.06.03 reconfigure against the merged-company division taxonomy (CRM §3.02 D-3b) once that taxonomy is locked.
7. **SharePoint folder standards** — Pivot REQ-3.06.01 specifies SharePoint folder structure aligned to NetSuite hierarchy (Customer → Project → Sales Order → Documents); folder-naming conventions and migration of historical project documents decided during configuration.
8. **KBM staff role assignments** — IPM vs. sales-coordinator categorization for KBM PMs during organizational alignment.
9. **Sherri Nuzum knowledge transfer** — Pivot's Workfront knowledge-holder named in Pre-Quote BRD; knowledge-transfer plan during the Workfront sunset transition documented during change-management planning.
10. **Workfront historical data migration scope** — project, task, time, and capacity data extraction from Workfront and migration to Orion native; planned with System Setup §3.10 D-5.
11. **Custom enhancement design** — task management depth, dependency tracking, and capacity management enhancements documented during Realize-phase design.
12. **Pivot project management stakeholder review** — Pivot project-management leadership reviews merged-company recommendations and the transition plan before the working session.
