# Codex Review (Second Pass) — §3.06 Project Management

## Headline assessment
Ready with edits, not lock-ready. The major first-pass reversal on Workfront has been corrected: the section now commits to Orion-native consolidation and Workfront sunset. Remaining issues are citation depth, several overstated Workfront/KBM claims, and missed Pivot PM BRD items that should either appear or be explicitly cross-referenced.

## Carry-through issues from first-pass review
- REQ-level citations still missing on every divergence source line: `_Unification/09 - Project Management.md:51`, `72`, `86`, `100`, `114`; violates `_Unification/working/drafting-standards.md:155-162`.
- Pivot Workfront capability overstatement remains: `_Unification/09 - Project Management.md:55`, `104` say task dependencies, resource allocation, capacity management, dashboards are “built in Workfront.” Pivot PM BRD supports Workfront usage and time logging, but much of the capacity/dashboard future state is Orion-native: `_Unification/working/pivot-brds-md/Project_Management.md:547`, `561`, `658-685`.
- KBM resource/capacity under-reach remains: `_Unification/09 - Project Management.md:100-108` says KBM has not articulated dedicated capacity management, but KBM Operations has REQ-032 through REQ-034 for PM task automation, resource visualizer, and task sophistication: `Operations/KBMH/3 Output/BRD_Operations_v1.0.md:1959-1974`.
- D-4 still overlaps Operations D-8 instead of narrowing to PM workload planning: `_Unification/09 - Project Management.md:98-108`, `158`; Operations already decides scheduling/resource management at `_Unification/08 - Operations.md:158-168`, `215`.

## New issues
- Header cites KBM PM source coverage, but `Project Management/KBMH/3 Output/` has no BRD/requirements file. If KBM PM claims rely on Marketing, Pre-Quote, CRM, and Operations, the header should name those files/REQs instead of only saying “no separate BRD” (`_Unification/09 - Project Management.md:6-7`).
- Cross-area table misplaces the project-record framework decision. PM D-2 decides Orion project record as execution and aggregation system (`_Unification/09 - Project Management.md:70-80`), but the dependency table says BI/Financial Management decide it (`_Unification/09 - Project Management.md:130`). Pre-Quote correctly points project record structure to Project Management: `_Unification/05 - Pre-Quote.md:184`.
- Decision table math passes: `_Unification/09 - Project Management.md:153-161` reconciles 5 decisions, 4 default-yes, 1 working-session refinement.

## Cross-area drift
- Workfront sunset: pass. PM D-1 aligns with CT-16 and states transition shape, not platform choice: `_Unification/09 - Project Management.md:57-59`; `_Unification/11 - Cross-Area Decisions Index.md:231-241`.
- SharePoint / Google Drive: partial drift. PM names Google Drive as KBM current state (`_Unification/09 - Project Management.md:14`) and has a dependency row (`133`), but configuration carryover omits the locked CT-14 migration path: File Cabinet for transactional docs, SharePoint for collaboration docs, KBM Google Drive sunset (`_Unification/11 - Cross-Area Decisions Index.md:203-213`; System Setup lock at `_Unification/07 - System Setup & Configuration.md:81-95`).
- HubSpot: no material drift. The only PM mention frames HubSpot as part of retained platform architecture (`_Unification/09 - Project Management.md:57`), consistent with CT-3 bi-directional retention (`_Unification/11 - Cross-Area Decisions Index.md:49-60`).

## Standards / tone
Fail with edits.
- No banned “Doc Zero,” “spec’d,” R/Y/G, or bad name spelling found.
- New name “Sherri Nuzum” is source-backed in Pivot materials: `_Unification/working/pivot-brds-md/Project_Management.md:996`, `1074`, `1194`, `1202`; also Pre-Quote summary `_Unification/05 - Pre-Quote.md:248`.
- Tone issues: “substantial existing investment” (`_Unification/09 - Project Management.md:55`), “capacity visibility that KBM has not had previously” (`106`), and “most operationally significant transition” (`149`) read evaluative or over-assertive. Reframe as operational-context statements.

## Source accuracy
Fail.
- Pivot BRD does say Orion replaces Workfront: `_Unification/working/pivot-brds-md/Project_Management.md:129-131`; PM now aligns on that.
- PM overstates the BRD-backed Workfront feature set at `_Unification/09 - Project Management.md:16`, `55`, `104`. Dependency tracking appears in Workfront demo inputs, not in the cited Pivot BRD; either cite the demo transcript or soften.
- KBM “no formal resource/capacity framework” is inaccurate without qualification. KBM explicitly raised PM workload and task-management requirements, but deferred design: `Operations/KBMH/3 Output/BRD_Operations_v1.0.md:1959-1974`, `2042-2055`.

## What’s missing
- Pivot project-subproject numbering convention: `_Unification/working/pivot-brds-md/Project_Management.md:298-299`, `396`, `998-1000`.
- PM service pricing and rate cards: Pivot REQ-3.04.01 through REQ-3.04.07 and assumptions/open decisions at `_Unification/working/pivot-brds-md/Project_Management.md:535-541`, `639-645`, `1016-1026`, `1134-1148`.
- Budget-to-actual alert routing: `_Unification/working/pivot-brds-md/Project_Management.md:540`, `567`, `642-644`, `1158-1164`.
- Vendor Portal / external design partner workflow: `_Unification/working/pivot-brds-md/Project_Management.md:781-783`, `803`, `880`, `1080-1084`.
- Workfront document migration and SharePoint folder standards: `_Unification/working/pivot-brds-md/Project_Management.md:886`, `1208-1214`.

## Recommended edits before lock
1. Add REQ/file/section citations to every D-source line.
2. Rewrite D-4 with KBM REQ-032 through REQ-034 and narrow it against Operations D-8.
3. Soften Workfront capability claims or cite the Workfront demo transcript if using task/dependency/detail beyond the BRD.
4. Add CT-14 carryover row for project documents: KBM Google Drive to SharePoint; Workfront/IQ/D365 docs to SharePoint/File Cabinet by document type.
5. Add missing Pivot PM items as D-2/D-5 details or open questions: numbering convention, PM rate cards, budget alerts, vendor portal, SharePoint folder standards.
6. Fix the cross-area dependency row that says BI/Financial Management decide the project-record framework.