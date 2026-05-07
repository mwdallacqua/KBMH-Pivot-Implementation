# Codex Review (Second Pass) — §3.05 Operations

## Headline assessment
Needs further work. The recommendation direction is plausible, but the section is not lock-ready because first-pass source/citation defects remain and newer cross-area decisions are not carried through cleanly. The biggest risks are Pivot overstatement, missing Pivot REQ IDs, and unresolved Operations ownership for Workfront-adjacent work orders, document storage, acknowledgements, and RFP mechanics.

## Carry-through issues from first-pass review
- Pivot citations are still generic in every divergence source line: `_Unification/08 - Operations.md:59,73,87,101,115,132,146,160`. Drafting standards require Pivot REQ IDs and file/section refs (`drafting-standards.md:155-160`).
- KBM section refs are also off: D-3 cites §6, but work orders are KBM §5 (`BRD_Operations_v1.0.md:776`); D-7 cites §7, but time tracking is §6 (`BRD_Operations_v1.0.md:969`); D-8 cites §11, but scheduling is §10 (`BRD_Operations_v1.0.md:1955`).
- Pivot is still framed too cleanly as in-house-only at `_Unification/08 - Operations.md:5,63,65,190`; Pivot source includes employees, subcontractors, temporary resources, full job subcontracting, and supplemental labor (`Operations.md:832-840,876-890`).
- D-2 still under-represents Pivot receiving: lot inventory, multi-bin receiving, virtual locations, 7-day manual trigger, SnapTracker/CAM/RF Smart are absent (`Operations.md:237-251,280-298,1128-1140`).
- D-3 still compresses Pivot work orders into “hard assignment” and misses PO grouping, phased installs, PO-ack readiness reminders, notifications, and Workfront/IQ handoff removal (`Operations.md:525-543,581-590,616-692`).
- D-8 still contains unsupported Pivot claims: “vehicle utilization,” “multi-day project scheduling,” and “resource utilization KPIs” at `_Unification/08 - Operations.md:164`; Pivot source supports skills/badging and daily route planning for two trucks, not those claims (`Operations.md:382-392,483-511`).
- PlanGrid retirement is improved in D-5 but still absolute in summary/config carryover: `_Unification/08 - Operations.md:194,229`. Pivot source says parallel run, license 1/10/2027, migration strategy, and Q3 2026 deadline (`Operations.md:1190-1194,1248-1256`).
- Acknowledgement ownership still conflicts: Operations says Order Management decides it (`_Unification/08 - Operations.md:182`); Order Management says Operations owns acknowledgement processing detail (`_Unification/06 - Order Management.md:205`).

## New issues
- `_Unification/08 - Operations.md:16` cites Pivot subcontractor/supplemental labor to REQ-3.07; correct source is Pivot REQ-3.05.02/3.05.03 (`Operations.md:832-840,876-890`). REQ-3.07 is field operations / PlanGrid (`Operations.md:1014-1028`).
- `_Unification/08 - Operations.md:24` lists purchase requisitions as “explicit in both BRDs”; Pivot Operations has no purchase-requisition requirement. Pivot Operations requirements begin with receiving/warehouse REQ-3.01.01 (`Operations.md:237-251`).
- `_Unification/08 - Operations.md:28` lists VRA as aligned in both; Pivot treats formal VRA as optional/Phase 2 and assumes informal Phase 1 (`Operations.md:704-714,1164-1167,1230-1236`).
- `_Unification/08 - Operations.md:46,105` imply Pivot supports geolocation/geological check-in. Pivot field ops REQ-3.07.01-.06 omit GPS/check-in (`Operations.md:1014-1028,1052-1100`); KBM is the source for that capability.
- `_Unification/08 - Operations.md:230` says Pivot-side VRA 80/20 is “Specified”; inaccurate. Pivot specified optional formal VRA, not KBM’s 80/20 rule.
- `_Unification/08 - Operations.md:183` has malformed reference: `Financial Management (§3.08 §3.08.8 #9)`.

## Cross-area drift
- Workfront sunset is locked, but Operations does not explicitly carry CT-16 into D-3/D-8. Pivot Operations source has Workfront/IQ handoffs (`Operations.md:547-556,569-570`); PM locks Orion-native consolidation and Workfront sunset (`_Unification/09 - Project Management.md:49-66`).
- SharePoint is locked as collaboration platform with File Cabinet for transactional docs, but Operations only says “Document storage architecture” generically (`_Unification/08 - Operations.md:179`). It should map field reports/photos/completion certs to CT-14 / System Setup D-3 (`_Unification/07 - System Setup & Configuration.md:81-94`; `_Unification/11 - Cross-Area Decisions Index.md:203-213`).
- CT-8 still missing: RFP task/resource and folder/project timing are explicitly deferred to Pre-Quote and/or Operations (`_Unification/11 - Cross-Area Decisions Index.md:119-127`; CRM sample `_Unification/01 - CRM (Sample).md:166-176`).
- HubSpot: no direct drift found in Operations.

## Standards / tone
Fail. Unverified first names remain at `_Unification/08 - Operations.md:14` against the names rule (`drafting-standards.md:7-20`). “Geological check-in” remains at `_Unification/08 - Operations.md:46,241`. Footer format still fails the required math wording at `_Unification/08 - Operations.md:217`. Tone still leans comparative at `_Unification/08 - Operations.md:18,65,201` (“inherits,” “multi-quarter business build,” “operational backbone”).

## Source accuracy
Fail. The section still makes material Pivot claims beyond the Operations BRD: purchase requisitions, geolocation check-in, vehicle management/utilization, resource KPIs, and VRA 80/20. The cited Pivot subcontractor REQ series is wrong. KBM source refs need corrected section numbers.

## What's missing
- Pivot receiving detail: lot-numbered inventory, multiple bins, virtual locations, mystery product, 7-day manual trigger, CAM/SnapTracker/RF Smart/ASN.
- Pivot scheduling detail: badging/tagging, skills matrix, DUR route planning, route/work-order integration.
- Pivot work-order detail: PO groupings, phased installs, readiness reminders, custom groupings, scheduled notifications.
- Pivot punch detail: companion sales orders, $250 approval threshold, MillerKnoll “R” designation, punch issue/reason/resolution lists.
- Pivot PlanGrid reporting detail: PDF photo/punch reports and filtering from pinned photos/punches.
- KBM unresolved inputs: work-order final confirmation, rate matrix, contractor access/time-entry lists, warehouse locations, damaged-product accounting, PlanGrid report examples, floor-plan formats (`BRD_Operations_v1.0.md:2111-2128`).
- Delivery/installation contact attribution from CT-11 is not addressed (`_Unification/11 - Cross-Area Decisions Index.md:161-170`).

## Recommended edits before lock
1. Replace every generic Pivot source label with Pivot REQ IDs and correct KBM section refs.
2. Reframe D-1 as “Pivot-led internal operations with subcontractor/supplemental labor support.”
3. Expand D-2, D-3, and D-8 with actual Pivot requirements; remove unsupported vehicle/KPI/geolocation claims.
4. Reconcile CT-16, CT-14, CT-8, and acknowledgement ownership.
5. Fix D-5/PlanGrid wording, D-6 carryover, open questions, names, “geological,” and the decisions footer.