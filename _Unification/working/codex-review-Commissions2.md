# Codex Review (Second Pass) — §3.07 Commissions

## Headline assessment
Needs further work before lock. The core recommendation is directionally sound, but the section still fails citation depth, source accuracy, and D-5 decision reconciliation. First-pass fixes were applied unevenly: D-1/D-5 body text improved, but summary/table/open questions still contradict those fixes. No new drift against HubSpot, SharePoint, or Workfront locks; there is division-taxonomy drift.

## Carry-through issues from first-pass review
- Source citation depth still fails all six divergences: `_Unification/10 - Commissions.md:48,62,76,90,104,121`; standards require REQ IDs plus file/section refs (`drafting-standards.md:155-160`).
- D-1 still conflicts: line 34 says commissions calculate on actual labor cost, while D-1 says commissionable GP / quoted labor at lines 52-56.
- Pivot rate-structure overclaim remains at line 66. Source supports role plan types and tiered IGP (`Commissions.md:185-189`, `281-288`), not designer rates, product mix, or order-type differentiation.
- Internal referral compensation is still sourced to Pivot Commissions at line 90, but source support is Pivot CRM REQ-3.06.01 (`CRM.md:401-403`).
- D-3 still implies Pivot supports header-level splits at line 82. Pivot supports percentage splits (`Commissions.md:446-466`), not specifically header-level assignment.
- Pivot invoice-date timing is fixed in D-5 body (`10 - Commissions.md:104-115`) but contradicted in summary/table/open questions (`:155`, `:170`, `:192`).

## New issues
- Division taxonomy drift: lines 16 and 66 use NBD / Venture / Public / Construction Solutions. CT-1 says downstream sections should cite “merged-company division taxonomy” rather than restating the four (`11 - Cross-Area Decisions Index.md:27-31`), and the CRM sample uses Enterprise / Venture / Public / Construction Solutions.
- Line 28 claims Customer Portal access for rep commission visibility. Source only supports sales-rep visibility into commission status/YTD (`Commissions.md:616-618`), not Customer Portal.
- Line 198 leaves historical commission data migration open, but Pivot source assumes no commission data migration (`Commissions.md:694`). Reconcile with System Setup D-5 (`07 - System Setup & Configuration.md:112-122`).
- D-6 misses CSM quarterly bonus. Draft mentions CS / Construction Solutions bonus tiers at line 125; source has separate CSM quarterly bonus (`Commissions.md:868-900`) and Construction Solutions tiers (`:902-926`).
- Decisions table reconciles arithmetically, but not logically: 5a adopts Pivot timing, 5b reopens timing (`10 - Commissions.md:169-173`).

## Cross-area drift
- CT-3 HubSpot, CT-14 SharePoint, CT-16 Workfront: no direct references, no drift.
- CT-1 division taxonomy: fail, as above.
- GP framework: line 34 should align to Financial Management D-5 actual-vs-quoted wording (`04 - Financial Management.md:133-137`), not “commissions calculate on actual labor cost.”

## Standards / tone
Fail. Citation standards fail across D-1 through D-6. Tone also needs cleanup: “larger sales organization” / “more complex” at line 16 and “at less detail” at line 62 violate the no-comparative-judgment rule (`drafting-standards.md:59-66`). Names, banned terms, § references, and em-dash usage otherwise look acceptable.

## Source accuracy
Fail. Unsupported or overstated claims remain at `_Unification/10 - Commissions.md:16,28,34,66,80,90,125,155,170,192,198`. Source-backed corrections are available from Pivot Commissions (`Commissions.md:185-189`, `281-286`, `364-367`, `446-466`, `520-546`, `592-620`, `694`, `714`, `868-926`) and KBM sources (`Requirements_Map_OrderManagement_v1.0.md:39,59-62`; `BRD_FinancialManagement_v2.0.md:872-887`, `1273-1298`).

## What's missing
- Pivot saved-search automation and manual commission records: `Commissions.md:364-367`, `420-424`.
- Pivot account-transition and leave-of-absence split rules: `Commissions.md:448-449`, `463-464`.
- CSM quarterly bonus structure: `Commissions.md:868-900`.
- Payroll-entry payment assumption: `Commissions.md:714`.
- Pivot no-commission-data-migration assumption: `Commissions.md:694`.
- Monthly/YTD commission statements, audit trail, true-up detail: `Commissions.md:592-620`.
- Assumptions that Pivot provides compensation plan documents and split examples: `Commissions.md:678-682`.

## Recommended edits before lock
1. Rewrite all D-1 through D-6 source lines with REQ IDs, file paths, and section refs.
2. Resolve D-5: either make invoice-date timing the decision or recast 5b as exception handling; then fix footer math.
3. Replace line 34 with commissionable GP / quoted labor wording.
4. Narrow unsupported Pivot claims around product mix, order type, SPIFs, portal access, and internal referral sourcing.
5. Fix CT-1 division taxonomy wording.
6. Reconcile historical commission data migration with Pivot’s no-migration assumption.
7. Add or explicitly defer the missing Pivot BRD items above.