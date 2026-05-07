# June Resume Plan

**Purpose:** Workstream sequencing, decision gates, on-site session agenda, and ownership for the merged-company NetSuite Orion implementation resuming in June 2026.

---

## Path from this document to June

The resume plan has four sequential phases, each with named owners and dependency gates:

```
Phase 1 — Document review and on-site working session       (Mid-May → late May 2026)
Phase 2 — Merged BRD drafting and sign-off                  (Late May → mid-June 2026)
Phase 3 — Realize-phase configuration kickoff               (June 2026)
Phase 4 — Realize, Educate, Activate, Maintain              (June 2026 → go-live)
```

Each phase has named gates that must close before the next phase begins. The gates are designed to surface dependency issues early rather than late, and to give both companies' leadership the visibility to make trade-off decisions before configuration locks them in.

---

## Phase 1 — Document review and on-site working session

### Pre-session preparation

| Item | Owner | Target |
|---|---|---|
| Recommendation document circulated to Matt Denning, Sandra Rudloff, Dustin Doucette, Jennifer Trask | Marcus Dallacqua, Chris Trumble | T - 5 business days from session |
| Companion PowerPoint deck (mirrors document; one slide per area projecting decisions) | Chris Trumble | T - 3 business days from session |
| Stakeholder pre-read confirmation | All four primary readers | T - 2 business days from session |
| On-site logistics confirmed (location, attendees, materials) | Marcus Dallacqua | T - 5 business days from session |

### Session agenda (single day, ~5 hours)

| Block | Duration | Content |
|---|---|---|
| Welcome and approach | 15 min | Reconciliation principle; how decisions are captured; what happens after |
| §3.01 Marketing | 30 min | HubSpot retention; market intelligence; merged-company segmentation |
| §3.02 CRM | 60 min | Pipeline model, hierarchy, GP framework, multi-company relationship, RFP combined model |
| §3.03 Pre-Quote | 45 min | 24-request-type taxonomy, labor quote depth, vendor management for service providers |
| Break | 15 min | |
| §3.04 Order Management | 45 min | Approval framework integration, customer PO tracking, order-type taxonomy |
| §3.05 Operations | 60 min | In-house operating model adoption, dual receiving / work-order patterns, transition for KBM coordination team |
| §3.06 Project Management | 45 min | Workfront sunset transition shape, capability-replacement scope, Pivot PM team migration plan |
| Break | 15 min | |
| §3.07 Commissions | 30 min | Commission basis, rate structure, timing, bonus programs |
| §3.08 Financial Management | 45 min | COA design, revenue recognition, expense platform, banking |
| §3.09 Business Intelligence | 20 min | Governance, 360 dashboards, reporting consolidation |
| §3.10 System Setup | 20 min | Soft-cutover, role taxonomy, integration architecture, document migration |
| Recap and next steps | 15 min | Decision summary, Merged BRD timeline, organizational alignment items |

The working session is the test of the recommendation, not its ratification. The document's job is to make every decision legible; the room's job is to confirm, modify, or defer each.

### Session output

Each decision is captured live with a yes / no / modified / deferred outcome. The capture file becomes the input to Phase 2 Merged BRD drafting. Decisions deferred to organizational alignment are routed to the appropriate operational owner with a target date.

---

## Phase 2 — Merged BRD drafting and sign-off

### Drafting (10 business days post-session)

| Item | Owner | Notes |
|---|---|---|
| Per-area Merged BRD drafts (10 documents) | GSI implementation team (Debbie Herbert lead; Jeanine Post, functional consultants) | One per process area, drafted from the captured decisions |
| Cross-area decisions integrated | GSI implementation team | Decisions that span multiple sections (per the Cross-Area Decisions Index) reflected consistently across all relevant Merged BRDs |
| Drafts circulated for sign-off | GSI implementation team | Sent to Matt Denning, Sandra Rudloff, and the appropriate process-area leads |

### Sign-off (5 business days post-drafts)

| Item | Owner | Notes |
|---|---|---|
| Per-area sign-off | Matt Denning (executive sponsor); Sandra Rudloff (Pivot leadership confirmation); process-area leads | Per the BRD signature blocks in each Merged BRD |
| Outstanding-question resolution | Process-area leads | Items deferred to organizational alignment confirmed by named owners with target dates |
| Final Merged BRDs locked | GSI implementation team | Signed and filed; configuration baseline established |

### Decision gates before Phase 3 begins

- Three foundational decisions confirmed: revenue recognition rules, COA design, expense management platform
- Workfront sunset transition shape locked with timeline
- Merged-company organizational alignment items resolved sufficiently to inform role assignments and approval routing

---

## Phase 3 — Realize-phase configuration kickoff (June 2026)

### Foundation work (Weeks 1-2 of June)

| Workstream | Owner | Notes |
|---|---|---|
| Subsidiary structure, currency, 13-period calendar | GSI configuration team | KBM's prepaid NetSuite Orion account is the surviving environment |
| Custom Orion roles configured against the merged-company role taxonomy | GSI configuration team | Two-dimensional hierarchy (geography + division) supported |
| Manager hierarchy configured for "me and my team" filters | HR + GSI | Foundational for dashboards and scorecards |
| Sales Locations defined per geography taxonomy | Sales operations + GSI | KBM's California territories + Pivot's Design Centers |
| Sales Divisions defined per division taxonomy | Sales operations + GSI | Per CRM §3.02 D-3b confirmation |

### Integration architecture (Weeks 1-4 of June)

| Integration | Owner | Notes |
|---|---|---|
| HubSpot ↔ NetSuite bi-directional sync | GSI integration team | Field mappings, source-of-truth rules per object, error handling |
| Banking integrations (West Coast Community Bank + Comerica) | GSI integration team | NetSuite Bank Feeds program for both |
| Advanced Electronic Bill Payments | GSI integration team | Replaces manual bank-portal uploads; eliminates 42 manual ACH/wires (Pivot) |
| Payroll integrations (Paylocity + UKG) | GSI integration team | CSV import; merged-company payroll provider decision pending |
| MillerKnoll integrations (ServiceNet, ServiceTime, Quote Tool, Order Manager, Exemplis) | GSI integration team | Full suite |
| SharePoint integration | GSI integration team | Collaboration platform; KBM Google Drive transition |
| Expense platform integration | GSI integration team | Per working-session selection |

### Process-area configuration (Weeks 3-12 of June and beyond)

Configuration follows the process areas in document order:

1. CRM (foundation for all opportunity and customer data)
2. Pre-Quote (request engine and labor-quote workflow)
3. Order Management (approval framework, order types, customer PO tracking)
4. Operations (Field Service app, work orders, receiving, VRA)
5. Project Management (NetSuite Orion native project consolidation; Workfront sunset transition)
6. Commissions (rate structure, eligibility, timing, bonus programs)
7. Financial Management (COA, period close, AP automation, expense platform)
8. Business Intelligence (dashboards, governance, reporting)
9. Marketing (HubSpot integration, campaigns, market intelligence dashboard)
10. System Setup (final integration testing, role refinement)

### Decision gates before Phase 4 begins

- Foundation work complete (subsidiary, calendar, currency, roles, hierarchy, locations, divisions)
- Critical integrations live and tested (banking, HubSpot, MillerKnoll Order Manager)
- Process-area configuration validated against the Merged BRDs
- User acceptance testing (UAT) scope defined per process area

---

## Phase 4 — Realize, Educate, Activate, Maintain

### Realize (configuration completion through UAT)

Configuration of all process areas is completed and validated through user acceptance testing. The Workfront sunset transition runs in parallel — capability-replacement scope is built in Orion native; Pivot PM team migrates per the transition plan; Workfront subscription winds down on the agreed timeline.

### Educate (training and adoption)

Role-specific training is delivered:
- **Sales / BD** — pipeline, opportunities, multi-company relationships, scorecards
- **Pre-Quote / IPM** — request engine, labor quotes, project request workflow
- **Order Management / Sales Coordinators** — order types, customer PO tracking, approval workflow
- **Operations / Field Service** — Field Service app, work orders, VRA, time tracking
- **Project Management** — Orion-native project record, resource allocation, capacity management (Pivot PM team transition focus)
- **Commissions / Finance** — commission structure, payout timing, reporting
- **Finance** — period close, banking, expense management, AP automation, fixed assets
- **BI / Power Users** — dashboards, saved searches, SuiteQL
- **Marketing** — HubSpot integration, campaigns, market intelligence dashboard
- **Admin / IT** — system administration, integration monitoring, user management

### Activate (go-live)

Soft cutover for both legacy systems: new business in NetSuite Orion; in-flight work in legacy systems completes there or migrates per the cutover sequencing. Process-area sequencing is determined by dependency — typically CRM, Pre-Quote, and Order Management activate together as the front-of-house workflow; Operations and Project Management follow; Financial Management and BI close out the cutover.

### Maintain (post-go-live support)

Standard post-go-live support cadence (30-day intensive support, then monthly steady-state). Continuous improvement items captured against the Merged BRDs; future-phase items (event management, customer satisfaction surveys, ZoomInfo evaluation, Power BI evaluation, accelerator/SPIF activation, Coupa email-parsing automation) addressed on the post-go-live roadmap.

---

## Cross-cutting workstreams

### Organizational alignment

Several decisions reference "organizational alignment" — they depend on the merged-company organizational structure being settled. The unification document scopes these decisions; the merged-company HR and operational leadership scopes the structure itself. Items in this category include:

- Specific approver assignments for $25K orders, missing-requirements approvals, erosion approvals, low-margin SVP approvals
- IPM vs. sales-coordinator role assignments for KBM staff
- Operations org structure for the merged operations function
- Merged-company commission rate structure
- Merged-company payroll provider decision
- Sales-team transition communication for the labor markup elimination

### Change management

KBM and Pivot staff onboard into a single operating model that combines elements of both legacy companies. Change management is not centralized in a single workstream — it is named in each process area's recommendation. The merged-company Change Management Lead (named per System Setup §3.10 D-1) owns the cross-cutting plan, with process-area-specific support from each functional workstream lead.

Highest-impact change-management items:

- KBM staff onboarding into Pivot's in-house operations model (§3.05)
- Pivot PM team transition from Workfront to Orion native (§3.06)
- KBM users transitioning from Google Drive to SharePoint (§3.10 D-3)
- Sales-team communication on commission framework changes (§3.07 D-1)
- KBM staff onboarding into selective activity-logging tiered model (§3.02 D-2b)
- Pivot users adapting to 13-period calendar (§3.08 D-2b)

### Data migration

A single coordinated data-migration plan covers all process areas. Owned by System Setup §3.10 D-5; cross-references to each process area's data inputs:

- KBM CRM data: Zendesk + Core extracts with deduplication; classification by role / sector / territory during import
- Pivot CRM data: HubSpot extract; classification per merged-company segmentation
- KBM financial data: 2017 historical baseline from Core
- Pivot financial data: D365 historical baseline
- Workfront execution data: project, task, time, capacity data per the Workfront sunset transition plan
- Document migration: KBM Google Drive content to SharePoint per §3.10 D-3 timeline
- Vendor and customer master data: combined merged-company master from both legacy systems

The merged-company data-migration cutover dates are sequenced against process-area activation per §3.10 D-2.
