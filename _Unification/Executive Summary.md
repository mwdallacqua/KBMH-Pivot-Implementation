# Executive Summary

**Document:** NetSuite Orion Unification Recommendation
**Audience:** Matt Denning (merged-company COO), Sandra Rudloff (Pivot leadership), Dustin Doucette and Jennifer Trask (MillerKnoll)
**Authors:** Marcus Dallacqua (GSI), Chris Trumble (GSI)
**Date:** May 11, 2026

---

## Where we're at

KBM Hogue and Pivot Interiors each independently purchased NetSuite Orion and completed BRD discovery in 2025. Both companies are now merging into a single MillerKnoll dealer, operating under a unified leadership team with Matt Denning as Chief Operating Officer. End-of-discovery is the appropriate moment to step back, reconcile the two implementations against the merged-company operating reality, and propose a go-forward strategy before configuration resumes. This document is GSI's perspective and recommendation at that decision point; we anticipate additional conversations with the new leadership team to confirm direction, refine details, and align on operational specifics.

## What we're recommending

The unification recommendation has two parts. **Part 1 — NetSuite contracts:** stay on the KBM Orion instance (already prepaid through Leaf Financing); wind down the Pivot instance over a negotiated transition window; add merged-company user licenses to the KBM account. **Part 2 — implementation:** carry forward a single Merged BRD per process area, building from both companies' existing BRDs, with 121 decisions across 10 process areas. 112 are committed by the GSI authoring team for leadership confirmation; 8 are reserved for working-session leadership selection. The detail follows below.

## On the NetSuite contracts

Both companies bought Orion on strong discounts through deliberate strategy: KBM secured 55% through Leaf Financing and prepaid all five years up front; Pivot secured 55% by closing before the MillerKnoll buy-in agreement (which is set at 45%) and the end of the calendar year. GSI's recommendation, developed in conversation with our NetSuite representatives, is to keep the merged company on the prepaid KBM instance and negotiate the Pivot contract down with NetSuite corporate. KBM has been instructed not to pay their current renewal so that negotiation room remains. Our working expectation is that NetSuite will likely require Pivot to pay for one additional year — possibly a lesser amount if the Pivot account converts to a maintenance posture (minimal user licenses, retained access through wind-down). User licenses then expand on the KBM account to support the merged organization. Leaf Financing has indicated that rolling additional user licenses into the existing financing structure is doable; **whether the merged company elects to do that is a decision point.** Final terms depend on NetSuite corporate; our representatives are positioned to advocate for the merged company through that conversation.

---

## The merged company operating shape

The merged company's operating shape, in shorthand:

- **One ERP**: NetSuite Orion as system of record on the prepaid KBM instance. Pivot's D365 sunsets to read-only post-go-live; KBM's Core sunsets via soft cutover with archive maintained.
- **One marketing engine**: HubSpot retained for marketing automation, with bi-directional integration to Orion. NetSuite is the system of record; HubSpot is the marketing surface.
- **One sales motion**: 4-stage weighted pipeline (25/50/80/95) with a high-confidence "Commit Forecast" view; two-dimensional sales hierarchy (geography + division); multi-company / multi-contact opportunity model with internal cross-division referral attribution.
- **One request engine**: Pivot's 24-request-type taxonomy across 10 categories — labor quote, design, project request, GSA, mockup, DUR, ServiceNet, WIX, lease/third-party, storage agreements, and others — replacing Pivot's Workfront-and-IQ Coordinator coordination and KBM's legacy Bridge platform.
- **One operations function**: Pivot's primarily-internal installation model (with subcontractor and supplemental labor support) as the merged-company operating capability, extended by KBM's outsourced-contractor-coordination capability for surge and geographic flexibility. Receiving, work orders, and field service support both patterns through assignment-type configuration.
- **One project execution platform**: NetSuite Orion native project record. Workfront sunsets; Pivot's PM team migrates to Orion-native execution with custom enhancements that protect work-order scheduling, time-and-rate-card tracking, budget-to-actual alerting, and forecasted utilization. **Workfront's July 2026 contract expiration is a consideration for transition sequencing — not a hard go-live deadline.** Ken has acknowledged the merged company will likely not be live before that date; whether to negotiate a shorter Workfront extension is part of the transition conversation.
- **One financial close**: Clean COA designed in joint session; 13-period calendar; 7-day close cadence as the working target; dual GP framework (actual vs. commissionable); native SuiteTax across the merged-company nexus footprint; multi-bank capability (West Coast Community Bank + Comerica); **Advanced Electronic Bill Payments replacing manual ACH portals** for direct ACH from NetSuite.
- **One collaboration platform**: SharePoint via the native NetSuite connector for collaboration documents (drawings, design files, project documents, vendor portal). NetSuite File Cabinet for transactional documents (invoices, POs, contracts, signed proposals). KBM's Google Drive sunsets; Pivot's fragmented sources (IQ Coordinator, Workfront, file shares, email, local storage) consolidate to SharePoint and File Cabinet by document type.
- **One commission framework — configured pre-go-live, cut over post-go-live**: The Commission Module is configured and running in Orion at go-live, but the merged company continues to operate its existing commission processes in parallel. Cut-over to using the Module's calculations for live commission payment happens **after go-live**, once parallel runs validate the configuration. Commissions calculate on commissionable GP per the dual GP framework; Pivot's tiered IGP ladder (4% / 6% / 8% / 10% / 12%) is the working starting point; invoice-date trigger with cumulative annual calculation; web-vendor exclusion; year-end true-up; deposit bonus, teamed-account bonus, CSM quarterly bonus, and Construction Solutions tiers configured as separate effective-dated programs. Specific merged-company rates are designed during organizational alignment.

The merged-company decision load: **121 decisions across 10 process areas. 112 are committed by the GSI authoring team and require leadership confirmation. 8 require leadership selection at the working session.** The eight selections concentrate on division taxonomy, default GP target, coaching threshold tiers (for Pivot's 2.5× pipeline multiplier), scope-source-of-truth, task-management sophistication, commission rate structure framework, merged-company expense platform, and the 15% labor markup retention question.

This document is the synthesis that drives the on-site working session. The output of that session is a Merged BRD per process area — the actual configuration blueprint. Configuration resumes in June.

---

## Why this approach

Two companies completed independent BRD discovery before knowing they would merge. Each BRD is internally consistent against its own context — KBM Hogue's against an outsourced-installation model and a focused labor-quote and project-request operation; Pivot Interiors' against a primarily-internal operations model with divisional sales structure, comprehensive request engine, and multi-platform legacy stack. The merged company is not the average of the two. It is a new operating model that takes context from both.

The recommendation is reconciled against a single principle:

> Where the two companies converge, the path is clear. Where they diverge, the recommendation leans toward the approach whose context — operational footprint, customer mix, organizational scale, or strategic priorities — most closely matches the merged company's situation. The recommendation is never about which approach is "better"; it is about which direction the merged company is best positioned to operate from.

The principle has three operating consequences worth surfacing:

1. **Convergence does not require a decision.** Where both BRDs commit to the same direction (the dual GP framework, the SuiteTax tax framework, the 4-stage pipeline structure, the SharePoint-as-collaboration target, MillerKnoll Order Manager integration, etc.), the recommendation carries the convergence forward and the working session confirms.

2. **Divergence is reconciled by context, not by source.** Where the BRDs differ, the recommendation explains the operating reality the merged company is moving into — divisional sales motion plus geographic territory coverage, primarily-internal installation plus continuing relationships with KBM's contractor network, KBM's named approval thresholds plus Pivot's margin-based and low-margin-SVP rules — and chooses the direction that fits that reality. Each divergence carries explicit reasoning attributed to context, never to source.

3. **Some decisions are organizational, not technical.** Specific approval thresholds for the merged company, IPM-vs-sales-coordinator role assignments for KBM staff, the merged-company operations org structure, specific commission rates per role and division, the merged-company payroll provider — these depend on how the merged company organizes itself, not on what NetSuite Orion supports. The unification document scopes the framework; the merged-company HR and operational leadership scopes the structure itself.

Each of the 10 process area sections follows the same template — how each company approaches the area today, where the two companies converge, where they differ (with KBM/Pivot/Recommendation/Decision pattern per divergence), the cross-area dependencies that resolve elsewhere, and the explicit decisions the leadership team owns.

---

## What's converging, what's transforming, what's transitioning, what's preserving

The merged company's design choices fall into four operating categories. Reading the document at this level — rather than decision-by-decision — is the fastest way to understand the operational shape:

**Converging** — both BRDs already point the same direction; the merged company gets the benefit of two independent validations of the same operating choice:

- Dual GP framework (actual labor cost vs. quoted labor cost)
- 4-stage weighted pipeline structure with one-click conversion
- SuiteTax for tax automation across the combined nexus footprint
- SharePoint as collaboration target (Pivot already targeting; KBM transitioning from Google Drive)
- MillerKnoll Order Manager integration as a primary integration point — **both companies use ServiceNet, the MillerKnoll Quote Tool, and MillerKnoll Order Manager**
- Field Service app deployment for both internal technicians and PM oversight
- Quote-level deposits and invoice schedule frameworks — *both companies have deposit needs; depth and patterns combine from both BRDs*
- Acknowledgement automation, invoice schedule templates, multi-currency support
- Custom Orion role taxonomy — *role names will likely require merged-company-specific renaming, which is a decision point*

**Transforming** — the merged company adopts a direction that neither legacy company is operating in today:

- Pivot's PMs migrate from Workfront to Orion-native project execution; Workfront sunsets
- Pivot's document management transforms from fragmented (IQ Coordinator, Workfront, file shares, email, local) to consolidated (SharePoint via native connector for collaboration; File Cabinet for transactional)
- KBM transitions from coordinated-outsourced-installation to a model where Pivot's primarily-internal installation is the merged-company operating capability and KBM's contractor-coordination is preserved as complementary
- Advanced Electronic Bill Payments replace manual bank-portal ACH workflows
- Commissions configured in the Commission Module pre-go-live with cut-over post-go-live after parallel validation

**Transitioning** — both legacy systems wind down; the merged company manages the dual posture during cutover:

- KBM's Core ERP follows soft cutover (new business in Orion; in-flight Core work completes there or migrates as scope permits)
- Pivot's D365 follows no-open-order migration (D365 read-only post-go-live; open orders complete in IQ / Workfront / D365 through the agreed run-out window)
- Workfront's July 2026 contract expiration is a consideration; the merged company will likely not be live by that date; Workfront sunset sequencing and any contract extension are part of the transition conversation

**Preserving** — operational specifics from each legacy company carry forward because they reflect operating discipline the merged company depends on:

- KBM's named approval framework ($25K Shannon completeness check, missing-requirements escalation, $1,500 cumulative erosion threshold) integrated within Orion workflow infrastructure that also supports Pivot's margin-based and low-margin SVP rules
- KBM's customer PO tracking framework (custom record, project-level aggregation, KPI dashboard, threshold alerts) extended to address Pivot's customer PO limit needs for Oracle, Apple, Google
- KBM's VRA process with the 80/20 rule (track expected vendor credits even when product not returned; custom Orion monthly credit aging report) overrides Pivot's Phase 1 informal-VRA Assumption
- KBM's vendor credit limit framework (90% warning threshold; hard-stop on PO creation when over limit; with override) integrated with Pivot's PO generation flow as a pre-creation check
- Both companies' MillerKnoll integration suite — ServiceNet, MillerKnoll Quote Tool, MillerKnoll Order Manager
- KBM's 15% labor markup pattern (Order Management REQ-038; Operations REQ-021 / REQ-022 / REQ-023; Pre-Quote v2.0 REQ-LQ-006) — **retention or elimination is open; we follow KBM's lead since the pattern is theirs**
- Pivot's PO generation depth (direct PO from SIF, draft PO with line constitution, mass updates, requisition workflows, intelligent splitting)
- Pivot's web-based client quote approval portal replacing email-and-Docentric workflows
- Pivot's PDF Composer with the 10-template inventory and dynamic field selection (budgetary, formal, GSA, client-specific) — KBM's customer-facing and vendor-facing templates recreated using PDF Composer with vendor PO redesign as an explicit configuration deliverable
- Pivot's invoice schedule templates (50/40/10, 30/40/30, 100% prepay, custom variations) — **deposit strategy going forward is a decision point**
- Pivot's installation-crew scheduling depth (badging for healthcare and government site access, skills matrix, daily route planning for Northern and Southern California trucks)

Reading the document at this level — converge / transform / transition / preserve — captures the merged company's shape. The 121 decisions are the implementation; the four categories are the operating reality.

---

## The decisions reserved for the working session

The recommendation commits 112 decisions and surfaces a smaller set for leadership selection at the on-site working session. These are not "remaining work" — they are decisions the GSI authoring team intentionally left open because they require leadership-team selection rather than authoring-team commitment.

**Where the framework is committed and the working session selects the value:**

| # | Decision | What's committed | What the session selects | Notes |
|---|---|---|---|---|
| 1 | **Division taxonomy** (§3.02 D-3b) | Two-dimensional sales hierarchy: division + geography. Pivot's existing four divisions (Enterprise, Venture, Public, Construction Solutions) are the working starting point. | Whether the merged company carries Pivot's four divisions, expands them, refines them, or replaces them with a different segment cut. | Division taxonomy threads across CRM, Commissions, Operations (vendor portal permissions), and System Setup (role configuration). |
| 2 | **Default GP target** (§3.02 D-6b) | The merged-company GP framework (dual GP — actual vs. commissionable). | The numeric default GP target for the merged company. | Pivot and KBM operated different GP norms. The merged-company target informs erosion approval routing. |
| 3 | **Coaching threshold tiers** (§3.02 D-9b) | The 2.5× pipeline multiplier as a coaching metric (Pivot REQ-3.07.01 — annual sales goals with 2.5× pipeline multiplier visibility and coaching indicators; red / yellow / green status on rep dashboards aggregated to leadership). Separate from commission calculation. | The threshold tier definitions that determine when each coaching status fires. | Pivot uses the multiplier in 15:5 reviews and Power BI today; thresholds for the merged company need leadership input. |
| 4 | **Opportunity as scope single source of truth** (§3.03 D-4b) | Labor quote requests launch from the Opportunity record (KBM v2.0 Q11 confirmed). | Whether the Opportunity record is the single source of truth for scope across all related transactions. | KBM v2.0 gap analysis Q12 documents this as pending Matt Denning / Kimi Katsuyoshi input. |
| 5 | **Task-management sophistication** (§3.06 D-3b) | Pivot's PM-workload-planning framework adopted as default. | Task-management sophistication level — the question raised in KBM Operations BRD §10 REQ-034: "is it the 10 phases or is it the 300 things that happen in each one of those phases?" | The session decides with KBM PM and Account Manager leadership and Pivot PM team input. *Confirm role / name references during the working session.* |
| 6 | **Commission rate structure framework** (§3.07 D-2) | Commissions calculate on commissionable GP. Pivot's tiered IGP ladder is the working starting point. Plan-type variation by role. | The framework confirmed at session; specific rates per role and division during organizational alignment with sales and finance leadership. | Definitely open. Compensation design depends on the merged-company sales motion. |
| 7 | **Merged-company expense platform** (§3.08 D-7) | A merged-company expense platform integrated with NetSuite Orion. | Expensify, RAMP, or NetSuite native — joint evaluation across both finance teams during the working session. | Both companies have expense-platform decisions in flight. |
| 8 | **15% labor markup retention or elimination** (§3.07 D-1 / §3.08 D-4) | KBM's existing pattern (Order Management REQ-038; Operations REQ-021 / REQ-022 / REQ-023; Pre-Quote v2.0 REQ-LQ-006). | Whether to retain the 15% labor markup formula-line pattern or eliminate it in favor of commissionable GP on quoted labor directly. | The pattern is KBM's. GSI's elimination recommendation should be validated with KBM leadership before committing. |

The Workfront sunset transition shape is **not** in this list. Workfront is going away; NetSuite Orion will cover the workload. Capability-replacement scope and sunset timeline are configuration questions, not leadership-team decisions.

Custom Orion role names will likely require some merged-company-specific renaming (e.g., KBM-named roles, Pivot-named roles) — a configuration decision point flagged in §3.10 D-4 rather than a separate working-session decision.

---

## Organizational alignment items

Several decisions reference "organizational alignment" — they depend on how the merged-company organization is structured, not on what NetSuite Orion supports. The unification document scopes the framework; the merged-company HR and operational leadership scopes the structure itself. These items are not at the working session; they resolve during organizational alignment with named owners and target dates:

- Specific approver assignments for $25K orders, missing-requirements approvals, cumulative erosion approvals, and Pivot low-margin SVP approvals (§3.04 D-1)
- IPM vs. sales-coordinator role assignments for KBM staff (§3.03 D-8; §3.06 D-3)
- Operations org structure for the merged operations function (§3.05 D-1)
- Specific commission rates per role and division (§3.07 D-2)
- Specific cross-division referral compensation rates (§3.07 D-4)
- Bonus-program Phase 1 activation (deposit bonus, teamed-account bonus, CSM quarterly bonus, Construction Solutions tiers) (§3.07 D-6)
- Merged-company payroll provider (Paylocity, UKG, or other) (§3.08.8 #9)
- Sales-team transition communication for the commission framework change (§3.07 D-1)
- Merged-company Program Manager and Change Management Lead assignments (§3.10 D-1)
- Whether merged-company user licenses on the KBM Orion account roll into the existing Leaf Financing structure

---

## Decisions already committed

The recommendation closes 112 decisions through reconciliation against the principle. These are committed by the GSI authoring team and require leadership-team confirmation rather than open debate. Material highlights:

| Area | Committed direction |
|---|---|
| Pipeline model | Pivot's 4-stage weighted (Analysis 25 / Qualified 50 / Quote 80 / Closing 95 / Win-Loss) with KBM's high-confidence "Commit Forecast" view at Quote+ |
| Sales hierarchy | Two-dimensional model: division (Pivot's structure) + geography (KBM's territories), with internal referral attribution captured |
| Relationship model | Multi-company / multi-contact per opportunity (Pivot framework) with rich contact role taxonomy (KBM framework) |
| GP framework | Pivot's actual-vs-quoted dual GP model |
| Marketing platform | HubSpot retained for marketing automation; bi-directional integration with NetSuite Orion as the system of record |
| Project management | NetSuite Orion native consolidation; Workfront sunsets on a defined transition timeline (Pivot BRD §2.01 source-direction) |
| Document collaboration | SharePoint via native NetSuite connector locked as the merged-company collaboration platform; KBM Google Drive sunsets; Pivot fragmented sources (IQ / Workfront / file shares) consolidate; Workfront contract end is a consideration |
| Operations | Pivot's primarily-internal installation model (with subcontractor / supplemental labor per REQ-3.05.02 / REQ-3.05.03) as primary; KBM's outsourced-coordination preserved as complementary |
| Customer PO tracking | KBM's framework adopted (custom record + project-level KPI dashboard); extended to address Pivot's customer PO limit needs for Oracle, Apple, Google |
| VRA process | KBM 80/20 framework (track expected vendor credits even when product not returned; custom Orion monthly credit aging report); overrides Pivot's Phase 1 informal-VRA Assumption |
| Vendor credit limits | KBM framework (90% warning threshold; hard-stop on PO creation when over limit; with override) integrated with Pivot's PO generation flow |
| Commissions | Module configured pre-go-live; cut-over post-go-live after parallel validation. Commissionable GP per dual GP framework; invoice-date trigger; cumulative annual calculation; web-vendor exclusion; year-end true-up; tiered IGP ladder; deposit bonus, teamed-account bonus, CSM quarterly bonus, Construction Solutions tiers configured |
| Period close | NetSuite Period Close Checklist with 7-day cadence as the working target; 13-period calendar |
| Tax management | Native SuiteTax for the merged-company nexus footprint (KBM's 48-state nexus + Pivot's California focus); manual tax-override capability for government and MillerKnoll-direct-bill orders |
| MillerKnoll integrations | ServiceNet, MillerKnoll Quote Tool, MillerKnoll Order Manager — both companies use them. Coupa email-parsing automation evaluation deferred to Realize ROI analysis |
| Field Service | App deployed for both internal technicians and PM oversight; KBM geolocation check-in carried forward; Pivot PDF photo / punch reports with filtering carried forward; PlanGrid retired against 1/10/2027 contract expiration |
| Banking | Multi-bank capability — West Coast Community Bank (KBM) and Comerica (Pivot); **Advanced Electronic Bill Payments replacing manual ACH portals** |
| Fixed Assets | NetSuite Fixed Asset module adopted; Bloomberg sunsets |

The full list of 121 decisions across all 10 process areas, with default and reference per decision, lives in the Decisions Register.

---

## Path to June

| Phase | Window | Scope |
|---|---|---|
| **1. Document review and on-site working session** | Mid-May → late May 2026 | This recommendation circulates 5 business days before the session. The session is a linear walkthrough of all 10 process areas in document order — ~30 minutes per area, ~5 hours total. A companion PowerPoint mirrors the document and projects each area's decisions for the room. Each decision gets a yes / no / modified / deferred outcome captured live. |
| **2. Merged BRD drafting and sign-off** | Late May → mid-June 2026 | Within 10 business days of the session, GSI drafts a Merged BRD per area from the captured decisions. Sign-off cadence: 5 business days for per-area review; named signatories per the BRD signature blocks. Final Merged BRDs locked. |
| **3. Realize-phase configuration kickoff** | June 2026 | Foundation work (subsidiary structure, currency, 13-period calendar, custom Orion roles, manager hierarchy, Sales Locations, divisions); critical integrations (HubSpot bi-directional, banking with Advanced Electronic Bill Payments, MillerKnoll integration suite); process-area configuration in document order. |
| **4. Realize, Educate, Activate, Maintain** | June 2026 → go-live | Configuration, UAT, role-specific training, soft cutover for both legacy systems, post-go-live support cadence. Workfront sunset transition runs in parallel. Commission Module cut-over occurs **post-go-live** after parallel validation. |

Decision gates between phases:
- **Before Phase 2 begins**: working session completes; all 121 decisions captured.
- **Before Phase 3 begins**: revenue recognition rules, COA design, expense management platform, and 15% labor markup retention decision confirmed; merged-company organizational alignment items resolved sufficiently to inform role assignments and approval routing.
- **Before Phase 4 begins**: foundation work complete; critical integrations live and tested; process-area configuration validated against the Merged BRDs.

The June Resume Plan (§5) details workstream sequencing, owners, and gate criteria.

---

## What we are asking from this audience

This document is GSI's recommendation at end-of-discovery and the starting point for the merged-company conversation, not a final position. Two questions for the readers:

1. **Is the approach right?** Reconciliation principle, decision framing, source-coverage transparency (KBM and Pivot REQ IDs cited per divergence), working-session format.
2. **Are the recommendations defensible?** Each section's recommendations are articulated with reasoning attributed to the merged-company context. Where any reasoning falls short, the working session and the conversations that follow are where it gets corrected.

Feedback turnaround target: **5 business days**. After feedback, the document is the basis for the on-site working session. We anticipate additional conversations with the new leadership team before, during, and after that session to confirm direction, refine details, and align on operational specifics — including the NetSuite contract recommendation and how it lands with NetSuite corporate.

The working session is the test of the recommendation, not its ratification. The document's job is to make every decision legible and to recommend a direction; the room's job — and the broader conversation's job — is to confirm, modify, or defer.

---

## How the document is organized

The full recommendation spans this Executive Summary plus five companion documents — roughly 150 pages of decision-attributed analysis with KBM and Pivot REQ-level citations throughout. Each process area follows the same template (how each company approaches today / where they converge / where they differ with KBM-Pivot-Recommendation-Decision pattern per divergence / cross-area dependencies / leadership-team decisions / configuration carryover / open questions). GSI is prepared to walk the full document section-by-section at the on-site working session and answer detail-level questions in the room.

| Section | Purpose | Approximate length |
|---|---|---|
| **§1** Executive Summary | This document | ~6 pages |
| **§2** At-a-Glance Index | Single-page summary of all 10 process areas with decision density and source coverage | ~3 pages |
| **§3** Process Area Sections (3.01-3.10) | The recommendations themselves; ten sections; same template for each | ~120 pages (10-15 pages per area) |
| **§4** Cross-Area Decisions Index | The 16 cross-area decision threads that span multiple sections | ~10 pages |
| **§5** June Resume Plan | Workstream sequencing, decision gates, on-site session agenda, owners | ~7 pages |
| **§6** Decisions Register | Consolidated list of every leadership-team decision across the document — 121 decisions total | ~10 pages |
