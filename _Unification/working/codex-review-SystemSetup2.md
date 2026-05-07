# Codex Review (Second Pass) — §3.10 System Setup & Configuration

## Headline assessment
Needs further work before lock. The structure is usable and the decisions table math reconciles, but several first-pass issues remain in substance: citation depth, migration scope, D-6 integration classification, and missing source coverage. New cross-area drift appeared after CT-14 and CT-16 were promoted: Workfront migration and Pivot document migration are not carried through. I would not circulate as lock-ready.

## Carry-through issues from first-pass review
- **Citation standard still fails.** Drafting standards require KBM and Pivot REQ IDs on every divergence (`_Unification/working/drafting-standards.md:155-160`). D-1 through D-6 still use partial or generic sources (`_Unification/07 - System Setup & Configuration.md:55`, `:69`, `:83`, `:100`, `:114`, `:128`).
- **D-2 still overstates Pivot cutover alignment.** The recommendation says soft cutover for both companies (`_Unification/07 - System Setup & Configuration.md:75-77`), but Pivot source says open orders will not be brought into Orion and D365 remains read-only post-go-live (`_Unification/working/pivot-brds-md/System_Setup_and_Configuration.md:1226-1230`, `:1266-1270`). KBM soft cutover is supported (`System Setup and Configuration/KBMH/3 Output/BRD_SystemSetupConfiguration_v1.0.md:563-580`).
- **D-5 remains too broad.** CT-6 was added to the dependency table (`_Unification/07 - System Setup & Configuration.md:154`), but D-5 narrative/decision still omits Zendesk/Core/HubSpot extraction detail required by CT-6 (`_Unification/11 - Cross-Area Decisions Index.md:91-99`).
- **D-6 still mixes confirmed integrations with evaluation/licensing items.** “All confirmed integrations” (`_Unification/07 - System Setup & Configuration.md:134`) overstates KBM pending items like Paylocity, Expensify, Google Drive vs SharePoint, and manufacturer expansion (`BRD_SystemSetupConfiguration_v1.0.md:313-328`, `:381-385`).
- **Prior missing-source items remain:** KBM COA setup (`BRD_SystemSetupConfiguration_v1.0.md:156-165`), Teams/status/change control (`:475-505`), transaction numbering/search (`:718-729`), and Pivot setup groups such as location/warehouse, system preferences, item master, and data migration are still absent or only implied.

## New issues
- **Pivot SharePoint current-state claim is wrong.** The draft says Pivot’s existing document management “uses SharePoint” (`_Unification/07 - System Setup & Configuration.md:87`, also `:188`). Pivot source says current documents are across IQ, Workfront, and likely file shares; SharePoint is the target integration/consolidation approach (`System_Setup_and_Configuration.md:1280-1287`, `:1291-1297`).
- **D-3 misses Pivot-side document migration.** CT-14 now includes consolidation of Pivot SharePoint/network drives/email/local storage into SharePoint/File Cabinet by document type (`_Unification/11 - Cross-Area Decisions Index.md:211`). D-3 only mentions KBM Google Drive migration (`_Unification/07 - System Setup & Configuration.md:89-94`).
- **Workfront migration is missing from D-5.** CT-16 explicitly carries Workfront historical project/task/time/capacity migration to System Setup D-5 (`_Unification/11 - Cross-Area Decisions Index.md:237-241`), but D-5 does not mention Workfront (`_Unification/07 - System Setup & Configuration.md:112-122`).
- **Division taxonomy is still over-committed.** D-4 restates Pivot’s four divisions (`_Unification/07 - System Setup & Configuration.md:104`), despite CT-1 saying to avoid restating them and keep final taxonomy open (`_Unification/11 - Cross-Area Decisions Index.md:28-31`).
- **Dependency table duplicates ownership.** Sales Locations/location taxonomy is shown as “decided here” (`_Unification/07 - System Setup & Configuration.md:152`), but CRM owns the two-dimensional model and division decision (`_Unification/01 - CRM (Sample).md:96-101`). System Setup should configure it, not re-decide it.

## Cross-area drift
- **CT-3 HubSpot:** Direction is consistent, but attribution is sloppy. Pivot System Setup says HubSpot integration would be explored after go-live (`System_Setup_and_Configuration.md:175`); locked bi-directional architecture comes from Marketing/CT-3 (`_Unification/03 - Marketing.md:65-69`, `_Unification/11 - Cross-Area Decisions Index.md:49-59`).
- **CT-14 SharePoint:** Direction is partially consistent, but Pivot document migration is under-specified and current-state wording is inaccurate.
- **CT-16 Workfront:** Fail. Workfront sunset/data migration does not appear in §3.10 D-5 despite being assigned there.
- **CRM hierarchy/taxonomy:** Partial fail. Configuration belongs here; model/taxonomy decision belongs to CRM.

## Standards / tone
Fail on citation depth and § reference hygiene. Malformed/nonstandard references remain at `_Unification/07 - System Setup & Configuration.md:114` and `:128` (`Financial Management §3.08.8 #8/#9`). No banned terminology or name-directory issues found. Tone risk: “preserves the document-management discipline Pivot’s teams already rely on” (`:89`) is unsupported and reads evaluative because the Pivot BRD frames the current state as fragmented (`System_Setup_and_Configuration.md:1291`).

## Source accuracy
Fail.
- Pivot current-state SharePoint claim is unsupported (`_Unification/07...:87`, source `System_Setup_and_Configuration.md:1291-1297`).
- Pivot soft-cutover posture is simplified past the source (`_Unification/07...:75-77`, source `System_Setup_and_Configuration.md:1226-1230`, `:1266-1270`).
- D-6 over-attributes cross-area integrations to System Setup source materials (`_Unification/07...:130-132`).
- D-5 omits required migration streams while claiming a complete historical migration recommendation (`_Unification/07...:120-122`).

## What's missing
- Workfront project/task/time/capacity historical migration scope and timing.
- Pivot IQ/Workfront/file-share/email/local document consolidation into SharePoint/File Cabinet.
- Pivot migration levels: Level 1 entities/financial history, Level 2 sales order history, Level 3A AP/AR, no open-order migration, D365 read-only.
- CRM migration details: Zendesk/Core/HubSpot extracts, dedupe, role/sector/territory classification.
- KBM archive system for pre-2017 and post-migration Core lookups.
- KBM Teams/status/session recording/change control requirements.
- KBM and Pivot transaction numbering/system preferences.
- Pivot item master/SIF/Smart Table setup and location/warehouse setup, unless intentionally cross-referenced elsewhere.

## Recommended edits before lock
1. Replace every D-source line with KBM and Pivot REQ IDs plus source sections.
2. Rewrite D-3 current state and recommendation to distinguish current Pivot fragmentation from target SharePoint consolidation.
3. Expand D-5 into a real migration-scope decision covering D365, Core, Zendesk, HubSpot, Workfront, documents, open AP/AR, open orders, and archive access.
4. Rework D-6 into confirmed integrations vs. evaluation/licensing decisions, with owning section citations.
5. Fix D-2 to reflect KBM soft cutover and Pivot’s “no open orders into Orion / D365 read-only” posture.
6. Remove hard-coded division names from D-4 and change “decided here” taxonomy language to “configured here.”
7. Add explicit carryover rows for Workfront migration, Pivot document migration, archive system, and transaction numbering.