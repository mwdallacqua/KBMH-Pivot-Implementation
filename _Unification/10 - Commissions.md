# 3.07 — Commissions

| Field | Value |
|---|---|
| **Decision density** | **Medium** — Pivot-only BRD; compensation-model design for the merged company; KBM's commission framework lived inside Order Management and Financial Management without a separate BRD |
| **Source coverage** | Pivot Commissions BRD v1.0 (Pivot-only); KBM commission-related requirements within Order Management and Financial Management source materials |
| **KBM source** | KBM commission structure addressed in Order Management REQ-015 (storage fees commissionable), REQ-031 (Direct Bill order type / commission gross-up), REQ-035 (header-level commission with split capability), REQ-036 (line-level commissionable flag), REQ-037 (Project GP vs. Commissionable GP), REQ-038 (15% labor markup via formula lines) — all in `Order Management/KBMH/3 Output/Requirements_Map_OrderManagement_v1.0.md`. Commission timing question raised in `BRD_FinancialManagement_v2.0.md` §8 |
| **Pivot BRD** | `Commissions/Pivot/4 BRD/09_Pivot Interiors BRD Commissions Process Area_v1.0.docx` (markdown copy at `_Unification/working/pivot-brds-md/Commissions.md`); covers §3.01 plan configuration, §3.02 tiered calculation, §3.03 triggers and manual maintenance, §3.04 splits and allocations, §3.06 deposit bonus, §3.07 reporting and reconciliation, plus Appendix CSM quarterly bonus and Construction Solutions tiers |

---

## 3.07.1 How each company approaches Commissions today

**KBM Hogue** addresses commissions within its broader Order Management and Financial Management source materials rather than as a separate process area. The framework includes header-level commission assignment with split-percentage capability across multiple sales reps (Order Management REQ-035), a line-level commissionable flag for marking individual lines as commission-eligible (REQ-036), the Project GP vs. Commissionable GP framework (REQ-037), and the 15% labor markup via formula lines that has been eliminated per Financial Management §3.08 D-4 (KBM REQ-038). KBM's framework also includes specific business rules: storage fees are always commissionable and billed back to client (REQ-015); Direct Bill order type at ~$1M/year is grossed up for commission and tracked separately for reporting (REQ-031). KBM's Financial Management materials raise commission timing (booking vs. invoicing vs. payment collection) as an open question.

**Pivot Interiors** has a dedicated Commissions BRD (v1.0). Pivot's framework specifies cumulative annual commission calculation tied to calendar year with invoice-date trigger (REQ-3.01.01 / REQ-3.01.02), tiered commission rates from 4% to 12% based on cumulative Invoiced Gross Profit (REQ-3.02.01 / REQ-3.02.02), web-vendor exclusion (REQ-3.02.03), adjustments for storage / margin splits / cost variances (REQ-3.02.04), saved-search and Map/Reduce-based automated triggers with manual-record capability (REQ-3.03.01 through REQ-3.03.04), commission splits with percentage allocations and teamed-account / account-transition / leave-of-absence rules (REQ-3.04.01 through REQ-3.04.04), the deposit bonus at 0.5% on cash deposits ≥ $10,000 received within 7 days of order entry (REQ-3.06.01 through REQ-3.06.05), and commission statements / year-end reconciliation with audit trail (REQ-3.07.01 through REQ-3.07.03). Pivot's BRD Appendix specifies the published rate ladder (4% / 6% / 8% / 10% / 12%), CSM quarterly bonus ($1,000 per $150K of IGP per quarter), and Construction Solutions sales rep bonus tiers ($1,000 at $501K–$999K, $2,000 at $1.00M–$1.49M, $3,000 at $1.50M–$1.99M, +$1,000 per $500K above $2.00M).

The merged company needs a unified compensation framework. The merged-company commission decisions span: commission basis (commissionable GP per CRM §3.02 D-6 — quoted labor rates — with the 15% markup eliminated per Financial Management §3.08 D-4), rate structure, split mechanics, eligibility rules, payout timing, internal-referral compensation, tiered rates and bonus programs, and reporting. Both companies' inputs contribute, and several decisions belong to merged-company sales and finance leadership rather than the system itself.

## 3.07.2 Where the two companies align

**Common ground across both companies' source materials:**

- Header-level commission assignment with split allocations across multiple sales reps (KBM REQ-035; Pivot REQ-3.04.01)
- Line-level commissionable flag for individual lines (KBM REQ-036)
- Commission calculation on Invoiced Gross Profit (Pivot REQ-3.02.02; KBM REQ-037 Commissionable GP)
- Commission statements and reporting on commission accruals by sales rep and period (Pivot REQ-3.07.01)
- Sales-rep visibility into their own commission status and YTD progress (Pivot REQ-3.07.04 / future-state — sales reps view in NetSuite Orion at any time; not a Customer Portal feature)

**Aligned via locked decisions in other areas:**

- Dual GP framework (actual GP with time-tracked labor vs. commissionable GP with quoted labor) per CRM §3.02 D-6 / Financial Management §3.08 D-5 — commission calculation operates on this framework; commissions calculate on commissionable GP
- Internal referral attribution captured on opportunities per CRM §3.02 D-3c / Pivot CRM BRD REQ-3.06.01 — referring person is captured at the CRM layer; compensation logic decided here in D-4
- 15% labor markup eliminated per Financial Management §3.08 D-4 — commissions calculate on commissionable GP per the dual GP framework
- 2.5x pipeline multiplier as coaching metric per CRM §3.02 D-9 — separate from commission calculation but provides leading-indicator context
- Sales rep scorecards as BI dashboard component per BI §3.09 D-9 — provides commission-position visibility

These are noted in the merged BRD; configuration proceeds against standard NetSuite Orion commission capabilities and the locked decisions above.

## 3.07.3 Where the two companies differ

Six in-area divergences. Each is presented as: how each company approached it (with attribution to context), the recommendation for the merged company, and the decision the leadership team owns.

---

### D-1. Commission basis — commissionable GP

**Source:** KBM Order Management `Requirements_Map_OrderManagement_v1.0.md:39,59-62` (REQ-015, REQ-035 through REQ-038 — Project GP vs. Commissionable GP, 15% labor markup formula); KBM Financial Management `BRD_FinancialManagement_v2.0.md:872-887,1273-1298` (commission timing open question, GP framework); Pivot Commissions BRD §3.02 REQ-3.02.02 (`Commissions.md:282`) and §3.02.06 (Internal Services Cost Basis configurable on commission plan, `Commissions.md:286`); cross-references Financial Management §3.08 D-4 (labor markup eliminated) and CRM §3.02 D-6 (locked dual GP framework)

**KBM's approach.** KBM's historical framework used the 15% labor markup formula line (REQ-038) to make commissions calculate on cost-plus-markup. The Project GP vs. Commissionable GP distinction (REQ-037) reflected the markup difference; storage fees were commissionable per REQ-015.

**Pivot's approach.** Pivot's commission framework calculates on Invoiced Gross Profit (REQ-3.02.02). Pivot's framework supports the dual GP basis (per CRM §3.02 D-6) — commissionable GP uses quoted labor rates; actual GP uses time-tracked labor costs. Commissions calculate against commissionable GP, with the Internal Services Cost Basis configurable on the commission plan (Actual / Quoted) per Pivot Commissions §3.02.06.

**Recommendation for the merged company.** Operate the merged company with commissions calculating on commissionable GP per the locked CRM §3.02 D-6 framework (quoted labor rates). The 15% labor markup is eliminated per Financial Management §3.08 D-4; commissions therefore calculate on the commissionable GP basis (quoted labor) rather than the prior cost-plus-markup pattern. Actual labor cost (time-tracked) feeds the actual GP view per the same dual GP framework, but commissions calculate against commissionable GP. The Internal Services Cost Basis field on each commission plan record allows configuration of Actual vs. Quoted for cases where that flexibility is needed (per Pivot §3.02.06). Sales-team communication is required to set expectations on commission impact for KBM staff transitioning from the markup-driven framework.

**Decision for the leadership team.** Confirm: commissions calculate on commissionable GP (quoted labor rates) per CRM §3.02 D-6 framework, with Internal Services Cost Basis configurable on each commission plan record. *Recommended default: yes.* (Sales-team communication required for KBM staff.)

---

### D-2. Commission rate structure

**Source:** Pivot Commissions BRD §3.02 REQ-3.02.01 / REQ-3.02.02 (`Commissions.md:281-282`) and Appendix rate schedule (`Commissions.md:778-828`) — published 4% / 6% / 8% / 10% / 12% tiers for Account Managers and Sales Executives based on cumulative IGP; KBM Order Management `Requirements_Map_OrderManagement_v1.0.md:59-62` (REQ-035 through REQ-038); CRM §3.02 D-3 / D-3b (sales hierarchy and division taxonomy)

**KBM's approach.** KBM's source materials reference commission rates within the broader framework (REQ-035 through REQ-038). KBM has not articulated a multi-tier rate ladder at the level of detail Pivot has published.

**Pivot's approach.** Pivot's BRD specifies plan-type variation across sales roles (REQ-3.01.03) and a published five-tier IGP-based rate schedule (4% / 6% / 8% / 10% / 12% tiers per cumulative IGP thresholds in the Appendix). Pivot's BRD does not itself differentiate rates by designer, product mix (MillerKnoll vs. non-MillerKnoll), or order-type (standard vs. specialized) — those are merged-company design decisions, not Pivot-current-state.

**Recommendation for the merged company.** Design the merged-company commission rate structure as a leadership-team decision during the merged-company organizational alignment. The rate structure reflects the merged-company sales motion (per CRM §3.02 D-3 two-dimensional hierarchy), incorporates the merged-company division taxonomy (per CRM §3.02 D-3b), and accommodates both KBM's existing rate patterns and Pivot's published tiered ladder. Specific rates are not within the unification document's scope; the framework — tier-based on cumulative IGP, plan-type variation by role — is.

**Decision for the leadership team.** Confirm: merged-company commission rate structure designed during organizational alignment with rates differentiated by role and by division (per CRM §3.02 D-3b); Pivot's tiered IGP-based ladder is the working starting point for tier shape and threshold logic. *Recommended default: confirm framework at session; specific rates determined during organizational alignment.*

---

### D-3. Commission split mechanics

**Source:** KBM Order Management `Requirements_Map_OrderManagement_v1.0.md:59` (REQ-035 — header-level commission with split capability); Pivot Commissions BRD §3.04 REQ-3.04.01 through REQ-3.04.04 (`Commissions.md:446-449`) — percentage splits, teamed-account splits with 4% Teamed Bonus, 30-day account-transition splits (50/50), leave-of-absence splits (50/50 for quotes converting within 30 days); REQ-3.03.05 (`Commissions.md:430`) — true margin-dollar splits where each rep's share runs through their own individual plan

**KBM's approach.** KBM articulates header-level commission assignment with split-percentage capability across multiple sales reps (REQ-035). Splits are typically pre-defined at order entry.

**Pivot's approach.** Pivot articulates commission splits as percentage allocations between representatives (REQ-3.04.01) with documented patterns: teamed-account splits with a 4% Teamed Bonus calculation (REQ-3.04.02), account-transition splits at 50/50 for 30 days (REQ-3.04.03), leave-of-absence splits at 50/50 for quotes converting within 30 days of leave (REQ-3.04.04), and true margin-dollar splits where each rep's share runs through their own individual plan (REQ-3.03.05). Pivot's framework does not specifically articulate header-level vs. line-level split; both percentage splits and true margin-dollar splits are supported.

**Recommendation for the merged company.** Adopt commission splits with percentage-allocation capability per both companies' frameworks (KBM REQ-035, Pivot REQ-3.04.01), plus Pivot's specific patterns (teamed account, account transition, leave of absence) and true-margin-dollar split capability where each rep's share runs through their own plan (Pivot REQ-3.03.05). Splits integrate with the internal referral attribution capability (per CRM §3.02 D-3c / Pivot CRM REQ-3.06.01) to support cross-division referral compensation (cross-references D-4). Specific split-percentage rules and approval requirements are configured during Realize phase.

**Decision for the leadership team.** Confirm: commission splits with percentage-allocation and true-margin-dollar split capability; Pivot's teamed-account / account-transition / leave-of-absence patterns adopted; integrated with internal referral attribution for cross-division compensation. *Recommended default: yes.*

---

### D-4. Internal cross-division referral compensation

**Source:** Pivot CRM BRD REQ-3.06.01 (internal referral attribution capability — referring person captured at CRM layer); cross-references CRM §3.02 D-3c (locked); Pivot Commissions BRD does not separately articulate cross-division referral compensation rules — those are designed during organizational alignment as part of D-2 rate structure

**KBM's approach.** KBM does not have multiple sales divisions in its current framework; cross-division referral is therefore not articulated.

**Pivot's approach.** Pivot's CRM BRD REQ-3.06.01 captures the referring person on opportunities at the CRM layer. The compensation rules — what the referring person earns when furniture sales refers Construction Solutions, or vice versa — are not separately specified in the Pivot Commissions BRD; they are operational decisions Pivot makes on a deal-by-deal or plan-by-plan basis today.

**Recommendation for the merged company.** Adopt the internal referral attribution capability locked in CRM §3.02 D-3c as the merged-company default. Specific cross-division referral compensation rates, eligibility rules, and timing are determined during organizational alignment as part of the merged-company commission rate structure design (D-2). Compensation can be configured as a percentage of the referring rep's commission plan, a flat-dollar SPIF, or a separate plan tier; the framework supports each approach.

**Decision for the leadership team.** Confirm: internal cross-division referral attribution capability (per CRM §3.02 D-3c) operationalized in Commissions; specific compensation rates determined during organizational alignment. *Recommended default: yes.*

---

### D-5. Commission eligibility rules and timing

**Source:** Pivot Commissions BRD §3.01 REQ-3.01.01 / REQ-3.01.02 (`Commissions.md:185-186`) — cumulative annual calculation tied to calendar year with invoice-date trigger; REQ-3.02.03 (`Commissions.md:283`) — web-vendor exclusion; REQ-3.02.04 / REQ-3.02.05 (`Commissions.md:284-285`) — adjustments and year-end reconciliation; KBM Financial Management `BRD_FinancialManagement_v2.0.md:872-887` — commission timing open question (booking vs. invoicing vs. payment); KBM Order Management REQ-015 (`Requirements_Map_OrderManagement_v1.0.md:39`) — storage fees commissionable; Pivot Assumption 10 (`Commissions.md:714`) — commissions paid through payroll entry

**KBM's approach.** KBM addresses commission eligibility within Order Management decisions: storage fees always commissionable (REQ-015), line-level commissionable flag for individual lines (REQ-036), header-level multi-rep split (REQ-035), Direct Bill order type grossed up for commission (REQ-031). KBM's Financial Management materials raise commission timing (booking vs. invoicing vs. payment collection) as an open question for organizational decision-making.

**Pivot's approach.** Pivot's Commissions BRD specifies invoice-date trigger with cumulative annual calculation tied to calendar year (REQ-3.01.01 / REQ-3.01.02). Web-vendor orders are excluded (REQ-3.02.03). Adjustments support storage costs, margin splits, and cost variances (REQ-3.02.04). Year-end reconciliation compares advanced vs. earned commissions with true-up at the Reconciliation Date (last day of fiscal year, REQ-3.02.05 / REQ-3.07.02). Commission payments are processed through payroll entry per Assumption 10.

**Recommendation for the merged company.** Adopt Pivot's invoice-date trigger with cumulative annual calculation as the merged-company commission timing. The reasoning is contextual: Pivot has the established pattern with year-end reconciliation, and the invoice-date trigger aligns commissions with revenue recognition (per Financial Management §3.08 D-3). KBM's Financial Management open question on timing is resolved by adopting this framework. Web-vendor exclusions (per Pivot REQ-3.02.03), storage-fee commissionability (per KBM REQ-015), and year-end reconciliation / true-up (per Pivot REQ-3.07.02) are configured per the combined framework. Commission payment is processed through payroll entry (per Pivot Assumption 10).

**Decisions for the leadership team.**

- (5a) Confirm: invoice-date commission trigger with cumulative annual calculation tied to calendar year, per Pivot REQ-3.01.01 / REQ-3.01.02. *Recommended default: yes.*
- (5b) Confirm: web-vendor exclusion (Pivot REQ-3.02.03), KBM storage-fee commissionability (REQ-015), and year-end reconciliation / true-up at fiscal-year close (Pivot REQ-3.07.02). *Recommended default: yes.*

---

### D-6. Tiered rates, deposit bonus, and bonus programs

**Source:** Pivot Commissions BRD §3.06 REQ-3.06.01 through REQ-3.06.05 (`Commissions.md:520-524`) — deposit bonus 0.5% within 7 days of order entry, $10,000 minimum threshold, project-value relativity, split-supported, configurable thresholds; REQ-3.04.02 (`Commissions.md:447`) — 4% Teamed Bonus; Appendix CSM Quarterly Bonus Structure (`Commissions.md:868-900`) — $1,000 per $150K of IGP per quarter, separately scheduled; Appendix Construction Solutions Sales Rep Bonus Tiers (`Commissions.md:902-926`) — bonus by project order amount ($1K at $501K-$999K, $2K at $1.00M-$1.49M, $3K at $1.50M-$1.99M, +$1K per $500K above $2.00M); KBM source materials do not specifically articulate bonus programs

**KBM's approach.** KBM's source materials reference commission rate structure but do not specifically articulate tiered-rate accelerators or named bonus programs.

**Pivot's approach.** Pivot's BRD articulates four distinct bonus programs:

- **Tiered IGP-based rates** — the published 4% / 6% / 8% / 10% / 12% rate ladder advances by cumulative IGP attainment (Appendix rate schedule)
- **Deposit bonus** — 0.5% of cash deposit received by check, credit card, or wire within 7 days of order entry; $10,000 minimum threshold; relative to total project value; split-supported (REQ-3.06.01 through REQ-3.06.04); thresholds and days are admin-configurable (REQ-3.06.05)
- **CSM quarterly bonus** — $1,000 per $150,000 of IGP per quarter, separately scheduled across Q1 / Q2 / Q3 / Q4 (Appendix CSM table); rate cards and goals stored as separate effective-dated records
- **Construction Solutions sales rep bonus tiers** — bonus by project order amount with $1,000 starting at $501K, $2,000 at $1.00M, $3,000 at $1.50M, and +$1,000 per $500K above $2.00M (Appendix CS table)

**Recommendation for the merged company.** Adopt Pivot's tiered IGP rate ladder (or its merged-company successor per D-2) as the foundational structure. Configure the deposit bonus, the 4% Teamed Bonus (per D-3), the CSM quarterly bonus, and the Construction Solutions sales rep bonus tiers as separate effective-dated bonus programs that the merged company can activate or adjust through admin configuration (per Pivot REQ-3.06.05 — thresholds and days are not hard-coded). Whether the merged company carries each specific program into Phase 1 is a leadership-team decision during organizational alignment; the capability is configured to support each program when activated.

**Decision for the leadership team.** Confirm: tiered IGP rate ladder, deposit bonus, teamed-account bonus, CSM quarterly bonus, and Construction Solutions sales rep bonus tiers configured for the merged company per Pivot framework; specific program activation determined during organizational alignment. *Recommended default: yes.*

---

## 3.07.4 Cross-area dependencies

| Dependency | Where it surfaced in Commissions | Where it's decided |
|---|---|---|
| **Dual GP framework (actual vs. commissionable)** | Commission basis (D-1) | **CRM (§3.02 D-6)** — GP framework locked; **Financial Management (§3.08 D-5)** — operationalized |
| **15% labor markup elimination** | Commission basis on actual vs. cost-plus-markup (D-1) | **Financial Management (§3.08 D-4)** — labor markup eliminated |
| **Internal referral attribution capability** | Cross-division referral compensation (D-4) | **CRM (§3.02 D-3c)** — capability locked (Pivot CRM BRD REQ-3.06.01); compensation logic decided here |
| **Division taxonomy** | Rate differentiation by division (D-2); CSM and Construction Solutions tier targeting (D-6) | **CRM (§3.02 D-3b)** — merged-company division taxonomy decided at working session |
| **Sales rep scorecards** | Commission-position visibility on rep dashboards | **BI (§3.09 D-9)** — scorecards as BI dashboard component |
| **Pipeline multiplier (2.5x)** | Coaching metric separate from commission calculation | **CRM (§3.02 D-9)** — multiplier locked |
| **Approval workflow framework** | Commission approval / adjustments | **Order Management (§3.04 D-1)** — approval framework |
| **Payroll-entry payment** | Commission payouts processed through payroll entry (Pivot Assumption 10) | **Financial Management §3.08.8 #9** — merged-company payroll provider; payment mechanism configured here |
| **Sales hierarchy** | Manager visibility into team commission performance | **CRM (§3.02 D-3a, D-3b)** — two-dimensional hierarchy |
| **Historical commission data migration** | Per Pivot Assumption 5, no commission data migration; reports kept in Crystal | **System Setup & Configuration (§3.10 D-5)** — confirms no commission-data migration in scope |

## 3.07.5 Recommendation summary

The merged-company Commissions playbook in shorthand:

- **Commission basis:** Commissionable GP per CRM §3.02 D-6 framework (quoted labor rates); 15% labor markup eliminated per Financial Management §3.08 D-4; Internal Services Cost Basis configurable on commission plan record (Actual / Quoted) per Pivot REQ-3.02.06
- **Rate structure:** Pivot's tiered IGP rate ladder is the working starting point; merged-company rates designed during organizational alignment, differentiated by role and division (per CRM §3.02 D-3b)
- **Splits:** Percentage-allocation (KBM REQ-035, Pivot REQ-3.04.01) plus true-margin-dollar split capability (Pivot REQ-3.03.05); Pivot's teamed-account / account-transition / leave-of-absence patterns adopted; integrated with internal referral attribution
- **Internal cross-division referral compensation:** CRM-locked attribution operationalized; specific compensation rates during organizational alignment
- **Eligibility and timing:** Invoice-date trigger with cumulative annual calculation (Pivot REQ-3.01.01 / REQ-3.01.02); web-vendor exclusion (REQ-3.02.03); KBM storage-fee commissionability (REQ-015); year-end reconciliation / true-up (Pivot REQ-3.07.02); commission payment via payroll entry (Pivot Assumption 10)
- **Tiered rates and bonus programs:** Tiered IGP ladder, deposit bonus (0.5% / 7-day / $10K threshold / configurable), 4% Teamed Bonus, CSM quarterly bonus, Construction Solutions sales rep bonus tiers — each as a separately effective-dated, admin-configurable program
- **Reporting:** Monthly and YTD commission statements (Pivot REQ-3.07.01); sales-rep self-service visibility into commission status and YTD progress (Pivot REQ-3.07.04 / future-state); complete audit trail for calculations and adjustments (Pivot REQ-3.07.03); commission accruals visible on rep dashboards (per BI §3.09 D-9 sales scorecards) and on manager dashboards via two-dimensional hierarchy (per CRM §3.02 D-3a, D-3b)
- **Data migration:** No commission data migration (per Pivot Assumption 5); historical commission reports remain in Crystal; carryover confirmed in System Setup §3.10 D-5

Net read: the merged-company Commissions function builds on Pivot's articulated commission framework and incorporates KBM's specific rules (storage fees commissionable, line-level commissionable flag, Direct Bill gross-up, header-level multi-rep splits). The biggest operational decisions — specific rates, division-based differentiation, and which bonus programs to activate at go-live — are leadership-team decisions during the merged-company organizational alignment, not within the unification document's scope. The system supports the framework regardless of those operational choices.

## 3.07.6 Decisions for the leadership team

| # | Decision | Default | Reference |
|---|---|---|---|
| 1 | Commissions calculate on commissionable GP per CRM §3.02 D-6 (quoted labor rates); Internal Services Cost Basis configurable on commission plan record | Yes | D-1 |
| 2 | Merged-company commission rate structure designed during organizational alignment; Pivot's tiered IGP ladder is the working starting point | Confirm framework at session | D-2 |
| 3 | Commission splits with percentage-allocation and true-margin-dollar split capability; Pivot teamed-account / account-transition / leave-of-absence patterns adopted; integrated with internal referral attribution | Yes | D-3 |
| 4 | Internal cross-division referral attribution operationalized in Commissions; specific compensation rates during organizational alignment | Yes | D-4 |
| 5a | Invoice-date commission trigger with cumulative annual calculation tied to calendar year (Pivot REQ-3.01.01 / REQ-3.01.02) | Yes | D-5 |
| 5b | Web-vendor exclusion, storage-fee commissionability, year-end reconciliation / true-up at fiscal-year close | Yes | D-5 |
| 6 | Tiered IGP ladder, deposit bonus, teamed-account bonus, CSM quarterly bonus, Construction Solutions sales rep bonus tiers configured; specific program activation during organizational alignment | Yes | D-6 |

> 7 decisions: 6 with default-yes recommendations and 1 (decision 2 — rate-structure framework) requiring leadership-team confirmation at the working session with specific rates determined during organizational alignment.

## 3.07.7 Configuration carryover

| Item | KBM-side built? | Pivot-side built? | Action for merged company |
|---|---|---|---|
| Header-level commission with split-percentage | Specified (REQ-035) | Specified (REQ-3.04.01) | Configure per common-ground items |
| Line-level commissionable flag | Specified (REQ-036) | Implicit (per IGP calculation rules) | Configure per common-ground |
| 15% labor markup formula line | Specified (REQ-038) | Not present | Eliminate per Financial Management §3.08 D-4 |
| Dual GP framework (commission basis) | Specified (REQ-037 — markup-driven) | Specified (REQ-3.02.02 — IGP / quoted labor) | Operate on commissionable-GP framework per D-1; Internal Services Cost Basis configurable on plan |
| Tiered IGP rate ladder (4% / 6% / 8% / 10% / 12%) | Not specified | Specified (Appendix rate schedule, REQ-3.02.01) | Build per D-2 as working starting point; merged-company rates during organizational alignment |
| Cumulative annual calculation tied to calendar year | Not specified | Specified (REQ-3.01.01) | Build per Pivot framework |
| Invoice-date trigger | Not specified | Specified (REQ-3.01.02) | Build per Pivot framework |
| Web-vendor exclusion | Not specified | Specified (REQ-3.02.03; Assumption 8) | Configure per Pivot framework |
| Storage fees commissionable | Specified (REQ-015) | Implicit | Configure per common-ground |
| Direct Bill order-type commission gross-up | Specified (REQ-031) | Not specified | Configure per KBM framework |
| Saved-search-driven commission record creation | Not specified | Specified (REQ-3.03.01); GSI to develop saved-search templates per Assumption 7 | Build per Pivot framework |
| Map/Reduce-based automated triggers | Not specified | Specified (REQ-3.03.02) | Build per Pivot framework |
| Manual commission record creation | Not specified | Specified (REQ-3.03.04) | Configure per Pivot framework |
| Account-transition split (50/50 / 30 days) | Not specified | Specified (REQ-3.04.03) | Configure per Pivot framework |
| Leave-of-absence split (50/50 / 30 days) | Not specified | Specified (REQ-3.04.04) | Configure per Pivot framework |
| True margin-dollar split (each rep through own plan) | Not specified | Specified (REQ-3.03.05) | Build per Pivot framework |
| Deposit bonus (0.5% / 7-day / $10K / configurable) | Not specified | Specified (REQ-3.06.01 through REQ-3.06.05) | Build per D-6 |
| Teamed Bonus (4%) | Not specified | Specified (REQ-3.04.02) | Build per D-6 |
| CSM quarterly bonus ($1K per $150K IGP) | Not specified | Specified (Appendix) | Build per D-6 |
| Construction Solutions sales rep bonus tiers | Not specified | Specified (Appendix) | Build per D-6 |
| Year-end reconciliation / true-up | Not specified | Specified (REQ-3.02.05 / REQ-3.07.02) | Build per Pivot framework |
| Monthly / YTD commission statements | Not specified | Specified (REQ-3.07.01) | Build per Pivot framework |
| Sales-rep self-service commission visibility (in NetSuite Orion) | Not specified | Specified (REQ-3.07.04 / future-state) | Configure per Pivot framework |
| Audit trail for commission calculations | Not specified | Specified (REQ-3.07.03) | Configure per Pivot framework |
| Payroll-entry commission payment | Not specified | Specified (Assumption 10) | Configure per Pivot framework; align with merged-company payroll provider (Financial Management §3.08.8 #9) |
| Commission data migration | Not specified | Out of scope (Assumption 5 — no migration; historical reports remain in Crystal) | Confirm no migration in System Setup §3.10 D-5 |

## 3.07.8 Open questions / inputs needed

1. **Merged-company commission rate structure** (decision 2) — specific rates by role and division determined during organizational alignment with sales and finance leadership; Pivot's tiered IGP ladder is the starting point.
2. **KBM staff transition communication** (decision 1) — sales-team communication plan for KBM staff moving from markup-driven commission framework to commissionable-GP-on-quoted-labor framework.
3. **Specific cross-division referral rates** (decision 4) — internal referral compensation rates determined during organizational alignment; framework supports percentage of plan, flat-dollar SPIF, or separate tier.
4. **Bonus-program Phase 1 activation** (decision 6) — which Pivot bonus programs (tiered ladder, deposit bonus, teamed account, CSM quarterly, Construction Solutions tiers) are active at go-live for the merged company; leadership-team decision during organizational alignment.
5. **Commission approval and adjustment workflow** — specific approval thresholds and approver roles for commission adjustments; determined during organizational alignment in coordination with Order Management §3.04 D-1 approval framework.
6. **Compensation-plan documents and split examples** (per Pivot Assumptions 1 and 2) — Pivot to provide all current compensation plan documents and example calculation sheets illustrating split scenarios for configuration input.
7. **Commission plan timing confirmation** (per Pivot Unresolved Requirement 1) — Marcus Dallacqua to confirm when commission plans are applied in workflow.
8. **Deposit bonus % of total project value workflow** (per Pivot Unresolved Requirement 2) — Marcus Dallacqua to validate and demonstrate the detailed workflow for deposit bonus relative to percentage of total project value.
9. **Pivot Commissions stakeholder review** — Pivot Commissions BRD stakeholders review merged-company recommendations before the working session.
