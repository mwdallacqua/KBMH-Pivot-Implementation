# Codex Review (Second Pass) — §3.04 Order Management

## Headline assessment
Needs further work before lock. The first-pass edits improved D-1 and removed the worst tone issue, but the section still misses several material Pivot Order Management capabilities and has unresolved cross-area ownership drift. Biggest risks: source-citation depth, D-1 attribution, and under-representation of Pivot’s client approval / PO / deposit / PDF Composer detail.

## Carry-through issues from first-pass review
- D-1 preserved the no-separate-SO-approval nuance, but misattributes it to Pivot: `_Unification/06 - Order Management.md:77`. Source is KBM REQ-010: `Order Management/KBMH/3 Output/Requirements_Map_OrderManagement_v1.0.md:34`.
- D-1 still does not reconcile cleanly to the decisions table. Narrative includes Pivot low-margin SVP / margin-based rules at `_Unification/06 - Order Management.md:75-77`, but table rows only name KBM thresholds / double-order query: `_Unification/06 - Order Management.md:233-235`.
- Vendor-credit ownership is still unresolved. OM points to Financial Management: `_Unification/06 - Order Management.md:197`; BI and CT-12 still point to OM: `_Unification/02 - Business Intelligence.md:200`, `_Unification/11 - Cross-Area Decisions Index.md:180`.
- Specialized order-type ownership remains circular. Pre-Quote says OM owns taxonomy: `_Unification/05 - Pre-Quote.md:185`; OM says Pre-Quote decides specialized types: `_Unification/06 - Order Management.md:203`.
- `Matt` still appears instead of `Matt Denning`: `_Unification/06 - Order Management.md:272`, `_Unification/06 - Order Management.md:278`.

## New issues
- Source citation depth fails standards. D source lines generally omit section references / full source depth required by `drafting-standards.md:104`, `drafting-standards.md:157-160`. Example: D-1 omits KBM REQ-025 even though double-order detection is in D-1: `_Unification/06 - Order Management.md:71`, `_Unification/06 - Order Management.md:73`; source is `Requirements_Map_OrderManagement_v1.0.md:49`.
- D-2 underplays Pivot’s customer PO exposure. Pivot has a critical outstanding item for customer PO limits for Oracle, Apple, Google: `_Unification/working/pivot-brds-md/Order_Management.md:1288`. Current section frames Pivot as only standard PO-on-invoice fields: `_Unification/06 - Order Management.md:89-93`.
- “XML import with JSON conversion” is listed under standard carry-forward capability, but KBM marks REQ-007 as ACCOMMODATE / solution design: `_Unification/06 - Order Management.md:44`, `Requirements_Map_OrderManagement_v1.0.md:31`.
- Draft PO is treated mainly as a KBM open gap: `_Unification/06 - Order Management.md:280`. Pivot’s BRD explicitly validates draft PO, mass PO updates, requisitions, and direct PO from SIF: `_Unification/working/pivot-brds-md/Order_Management.md:993-999`.
- The statement “without significant rework” is too strong given custom/customer-PO work and remaining gaps: `_Unification/06 - Order Management.md:268`; KBM v1.1 still lists critical/high gaps at `GapAnalysis_OrderManagement_v1.1.md:41-50`.

## Cross-area drift
- HubSpot: pass. No OM references conflict with Marketing §3.01 D-1 / CT-3.
- Workfront: needs wording cleanup. Pivot OM source says approval routing replaces email and Workfront routing with integrated approval: `_Unification/working/pivot-brds-md/Order_Management.md:258`; CT-16 locks Workfront sunset: `_Unification/11 - Cross-Area Decisions Index.md:231-241`. OM’s “Pivot’s broader workflow-routing infrastructure” should say Orion workflow infrastructure: `_Unification/06 - Order Management.md:77`.
- SharePoint / File Cabinet: no direct conflict, but OM’s document-storage dependency is too generic: `_Unification/06 - Order Management.md:206`. CT-14 locks File Cabinet for transactional documents and SharePoint for collaboration: `_Unification/11 - Cross-Area Decisions Index.md:203-213`.
- Acknowledgements are circular. OM says Operations decides acknowledgement detail: `_Unification/06 - Order Management.md:205`; Operations says OM decides acknowledgements: `_Unification/08 - Operations.md:182`.

## Standards / tone
Fail, but fixable.
- Casual source quote remains: “Sales order means donezo” at `_Unification/06 - Order Management.md:77`; standards warn against surfacing colorful source quotes: `drafting-standards.md:65`.
- Name standard fail on `Matt`: `_Unification/06 - Order Management.md:272`, `_Unification/06 - Order Management.md:278`; verified name is `Matt Denning`: `drafting-standards.md:15`.
- Decisions footer count is mathematically right, but not in required format: `_Unification/06 - Order Management.md:246`; standard footer pattern is `drafting-standards.md:137-141`.
- Tone watch: “Pivot’s process infrastructure becomes the operational baseline; KBM’s operational specifics become the implementation detail” may read reductively to Matt Denning and understates how many OM controls are KBM-led: `_Unification/06 - Order Management.md:227`.

## Source accuracy
Fail.
- D-1 has a material attribution error: no-separate-SO-approval is KBM, not Pivot. Current: `_Unification/06 - Order Management.md:77`; source: `Questionnaire_OrderManagement_v1.1.md:1114-1119`.
- D-2 misses Pivot’s own customer PO limit documentation need: `_Unification/working/pivot-brds-md/Order_Management.md:1288`.
- Pivot PDF Composer is materially underrepresented. Source includes dynamic field selection, 10 templates, GSA/client-specific formats: `_Unification/working/pivot-brds-md/Order_Management.md:627-630`; current D-5 only cites line/detail summary and template ownership: `_Unification/06 - Order Management.md:131-137`.
- Pivot deposit/pre-payment is underrepresented: quote-level deposits and vendor pre-payments are explicit: `_Unification/working/pivot-brds-md/Order_Management.md:531-535`; current D-4 focuses invoice schedules: `_Unification/06 - Order Management.md:115-125`.
- Pivot client quote approval is missing as a decision/carryover item: `_Unification/working/pivot-brds-md/Order_Management.md:723-727`.
- Budget locking / time tracking at SO conversion is missing or too light: `_Unification/working/pivot-brds-md/Order_Management.md:818-823`, `_Unification/working/pivot-brds-md/Order_Management.md:879`.

## What's missing
- Pivot client quote approval portal / Docentric replacement.
- Pivot purchase-order generation depth: direct PO from SIF, draft PO, mass PO updates, requisitions, line constitution, transmission methods.
- Pivot PDF Composer depth: 10 templates, dynamic field selection, GSA / budgetary / client-specific formats, terms control.
- Pivot deposit and pre-payment depth: quote-level deposit, vendor pre-payment, payment gateway decision, partial-payment handling.
- Pivot SIF import performance / exception-handling claims.
- Smart Table multi-grouping, bulk editing, aliases/tags, PO vs invoicing grouping.
- KBM deposit-management detail remains open: deposit percentages, application process, milestone scenarios: `Questionnaire_OrderManagement_v1.1.md:354-358`.

## Recommended edits before lock
1. Fix D-1 attribution, remove “donezo,” add REQ-025 and Pivot Feb review / CRM low-margin citations, and make decisions table explicitly include Pivot margin / low-margin approval.
2. Add a Pivot capability divergence or carryover block for client quote approval, PO generation, deposit/pre-payment, PDF Composer, and budget locking.
3. Resolve ownership loops: vendor credit, specialized order types, acknowledgements.
4. Bring every D source line up to drafting-standard citation depth.
5. Replace `Matt` with `Matt Denning`; consider role-based wording for Shannon/Kipp unless they are intentionally named.
6. Revise the net read so Pivot and KBM contributions are balanced without “baseline vs implementation detail” phrasing.