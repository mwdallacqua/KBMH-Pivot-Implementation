# Executive Summary

**Document:** NetSuite Orion Unification Recommendation
**Audience:** Matt Denning (merged-company COO), Sandra Rudloff (Pivot leadership), Dustin Doucette and Jennifer Trask (GSI leadership)
**Authors:** Marcus Dallacqua (Proprio), Chris Trumble (GSI)
**Date:** May 7, 2026

---

## What this document is

KBM Hogue and Pivot Interiors are merging into a single MillerKnoll dealer under Matt Denning's leadership. Both companies completed independent NetSuite/Orion BRD discovery during 2025 and started implementation work shortly after. This document recommends how the merged company operates inside NetSuite/Orion, process area by process area, and identifies the leadership-team decisions required before configuration resumes in June.

This is not a Business Requirements Document. It is the synthesis that drives the on-site working session, where the merged company's leadership confirms or refines each recommendation. The output of that session is a new Merged BRD per process area — the actual configuration blueprint.

## How the recommendation was built

Each process area is reconciled against a single principle:

> Where the two companies converge, the path is clear. Where they diverge, the recommendation leans toward the approach whose context — operational footprint, customer mix, organizational scale, or strategic priorities — most closely matches the merged company's situation. The recommendation is never about which approach is "better"; it is about which direction the merged company is best positioned to operate from.

Each section follows the same format: how each company approaches the area today, where the two companies converge, where they differ, the recommendation for the merged company with context-attributed reasoning, the cross-area dependencies that resolve elsewhere, and the explicit decisions the leadership team owns.

## Where the merged company lands, in shorthand

The merged company's NetSuite Orion configuration combines design choices from both organizations. The recommendations attribute every direction to context — never to which company "got it right":

- **Pivot's contributions** reflect its larger operational scale, divisional sales structure, in-house operations footprint, MillerKnoll-Certified position, and platform investments (HubSpot for marketing, Comerica banking, UKG payroll, comprehensive request engine, internal field service, Workfront for project management with a documented Orion-replacement direction).
- **KBM's contributions** reflect its data-discipline orientation, granular approval framework, named decision gates (revenue recognition, COA, labor markup), specific operational patterns (vendor credit alerts, branded RFQ forms, customer PO tracking, soft-scheduling for outsourced labor), and the tax-and-banking specifics of an established California operation.

## Decisions already committed

Several material decisions are committed in the recommendation and confirmed by the joint authoring team:

| Area | Committed direction |
|---|---|
| Pipeline model | Pivot's 4-stage weighted (Analysis 25 / Qualified 50 / Quote 80 / Closing 95 / Win-Loss) with KBM's high-confidence "Commit Forecast" view at Quote+ |
| Sales hierarchy | Two-dimensional model: division (Pivot's structure) + geography (KBM's territories), with internal referral attribution captured |
| Relationship model | Multi-company / multi-contact per opportunity (Pivot framework) with rich contact role taxonomy (KBM framework) |
| GP framework | Pivot's actual-vs-quoted dual GP model; 15% labor markup eliminated |
| Marketing platform | HubSpot retained for marketing automation; bi-directional integration with NetSuite Orion as the system of record |
| Project management | NetSuite Orion native consolidation; Workfront sunsets on a defined transition timeline |
| Document collaboration | SharePoint locked as the merged-company collaboration platform; KBM Google Drive content migrates |
| Operations | Pivot's in-house installation model as primary operating capability; KBM's outsourced-coordination muscle preserved for surge and geographic flexibility |
| Customer PO tracking | KBM's framework adopted (custom record + project-level KPI dashboard) |
| Period close | NetSuite Period Close Checklist with Pivot's 7-day cadence as the working target |
| Tax management | Native SuiteTax for the merged-company nexus footprint (KBM's 48-state nexus + Pivot's California focus) |

## Decisions reserved for the working session

A smaller set of decisions are surfaced for joint leadership review at the on-site working session:

| Area | Decision pending |
|---|---|
| Sales hierarchy | Final division taxonomy for the merged company (Pivot's existing four divisions are the working starting point) |
| CRM | Merged-company default GP target |
| CRM / coaching | Pipeline-multiplier coaching threshold tier definitions for the 2.5x metric |
| Pre-Quote | Opportunity as scope single source of truth (KBM v2.0 Q12) |
| Project Management | Capability-replacement scope at cutover (which Workfront features must be present in Orion at go-live vs. phased) and Workfront sunset timeline |
| Project Management | Task-management sophistication level (10 phases vs. 300 tasks per KBM REQ-034 / Operations BRD §10) |
| Commissions | Merged-company commission rate structure framework (Pivot tiered IGP ladder is the working starting point; specific rates during organizational alignment) |
| Financial Management | Expense management platform (Expensify, RAMP, or NetSuite native) |

## What the working session looks like

The recommendation is circulated five business days in advance. The on-site session is structured as a linear walkthrough of all 10 process areas in document order — roughly 30 minutes per area, ~5 hours total. A companion PowerPoint mirrors the document and projects each area's decisions for the room. Each decision gets a yes / no / modified / deferred outcome captured in real time. Within 10 business days of the session, GSI drafts a Merged BRD per area from the captured decisions and circulates it for sign-off. Configuration resumes from the merged BRDs in June.

The working session is the test of the recommendation, not its ratification. The document's job is to make every decision legible and to recommend a direction; the room's job is to confirm, modify, or defer.

## What we are asking from this audience

Two questions for the readers of this document:

1. **Is the approach right?** Reconciliation principle, decision framing, source-coverage transparency, working-session format.
2. **Are the recommendations defensible?** Each section's recommendations are articulated with reasoning attributed to the merged-company context. Where any reasoning falls short, the working session is where it gets corrected.

Feedback turnaround target: **5 business days.** After approval, the document is the basis for the on-site working session.

## How the document is organized

| Section | Purpose |
|---|---|
| **§1** Executive Summary | This document |
| **§2** At-a-Glance Index | Single-page traffic-light summary of all 10 process areas |
| **§3** Process Area Sections (3.01-3.10) | The recommendations themselves; one section per area; same template for each |
| **§4** Cross-Area Dependencies | Decisions that span multiple sections — the index resolves them |
| **§5** June Resume Plan | Workstream sequencing, decision gates, on-site session agenda, owners |
| **§6** Decisions Register | Consolidated list of every leadership-team decision across the document |

Companion files: `00 - Approach.md` (the original approach proposal that defined the format), `11 - Cross-Area Decisions Index.md` (the full cross-area decision threads).
