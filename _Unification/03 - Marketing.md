# 3.01 — Marketing

| Field | Value |
|---|---|
| **Decision density** | **Low** — both companies relationship-led at the senior end; HubSpot retention and integration architecture is the primary decision, with downstream choices largely flowing from it |
| **Source coverage** | KBM Marketing BRD v1.0 (27 requirements across 7 solution areas) + Pivot Marketing BRD v1.0 (35 requirements across 5 sections; source includes a duplicated/misnumbered REQ-3.05.07 carried for completeness) |
| **KBM BRD** | `Marketing/KBMH/3 Output/BRD_Marketing_v1.0.md` |
| **Pivot BRD** | `Marketing/Pivot/4 BRD/02_Pivot Interiors BRD Marketing Process Area_v1.0.docx` (markdown copy at `_Unification/working/pivot-brds-md/Marketing.md`) |

---

## 3.01.1 How each company approaches Marketing today

**KBM Hogue** approaches Marketing as a relationship-led, RFP-coordination-centered function. Its BRD describes a small team that supports sales through targeted communications to specific influencer roles (brokers, A&D firms, project managers, general contractors), coordinates RFP responses, and runs occasional showroom events. Email volume is intentionally low — fewer than six campaigns per year — and current tooling is MailChimp for the limited campaigns it does run, alongside Asana for RFP request workflow and Google Drive for file collaboration. KBM's emphasis is on multi-dimensional contact segmentation (role × sector × geography) so the few communications that do go out reach the right audience, on early visibility into the sales pipeline so marketing can prepare RFP responses and content proactively, and on market-intelligence dashboards that surface sector trends to inform proactive content strategy.

**Pivot Interiors** approaches Marketing as a marketing-automation-and-attribution operation supporting a divisional sales organization (per the merged-company division taxonomy decided in CRM §3.02 D-3b). Its BRD describes a marketing team that operates HubSpot for marketing automation, lead capture across multiple channels, lead qualification and scoring, automated nurture workflows, and event management at scale (Pivotal Insights events, A&D events, showroom tours, MillerKnoll events). Pivot's emphasis is on closed-loop reporting from lead source through closed revenue, attribution across complex buying committees (architects, designers, brokers, GCs influence deals), and ROI measurement on marketing investment. Pivot's BRD notes that HubSpot is the marketing platform of record and proposes NetSuite Orion as the system of record for campaign ROI tracking and the unified data hub.

Both companies share the same end-state goals at a high level: clean contact data, segmentation that supports targeted outreach, integration between marketing activity and sales pipeline, and ROI visibility on campaign and event spend. Where they differ meaningfully is the scale and shape of the marketing function, the platform architecture (HubSpot retained or sunset), the role of events, and whether marketing's primary day-to-day function is RFP coordination, marketing-automation-and-attribution, or both.

## 3.01.2 Where the two companies align

The following capabilities are common ground across both BRDs and require no merged-company decision:

**Explicit in both BRDs:**

- Web-to-lead capture from website forms with automatic lead creation
- Multi-source lead capture (web forms, events, referrals, manual entry)
- Duplicate detection and merge for contacts and leads
- Document attachment to opportunities and projects
- Email performance tracking (opens, clicks, bounces, unsubscribes)
- Closed-loop reporting from lead source through closed revenue
- Marketing-influenced pipeline reporting

*(Multiple contacts per opportunity with role designations — architects, designers, brokers, GCs — is the merged-company relationship model locked in CRM §3.02 D-4 and is referenced here as a Marketing-relevant capability without re-deciding.)*

**KBM-explicit; standard capability carried forward for the merged company:**

- Multi-dimensional contact segmentation by role × sector × geography (KBM REQ-M004)
- Custom contact role taxonomy depth (KBM REQ-M006)
- Sector classifications (KBM REQ-M007)
- Transactional vs. marketing email distinction with automatic subscription management (KBM REQ-M009)
- Personalized email sending from individual user accounts (KBM REQ-M011)

**Pivot-explicit; standard capability carried forward for the merged company:**

- Campaign cost tracking with expected vs. actual fields (Pivot REQ-3.01.04)
- Multi-location campaign coordination (Pivot REQ-3.01.05)
- Lead status tracking through qualification stages (Pivot REQ-3.04.08)
- Segment-specific performance analysis (Pivot REQ-3.05.06)

These are noted in the merged BRD, and configuration proceeds against standard NetSuite Orion capability.

## 3.01.3 Where the two companies differ

Nine in-area divergences. Each is presented as: how each company approached it (with attribution to context), the recommendation for the merged company, and the decision the leadership team owns.

---

### D-1. HubSpot retention and integration architecture

**Source:** KBM REQ-M002, REQ-M012 (`BRD_Marketing_v1.0.md` Solution Area 2); Pivot REQ-3.01.01 through REQ-3.01.06 and §4.01 SuiteApp Summary (`Marketing.md` §3.01, §4.01); cross-reference CRM §3.02.4 cross-area dependencies (HubSpot deferred from CRM)

**KBM's approach.** KBM's BRD positions MailChimp for retirement and NetSuite native email marketing as the consolidated replacement. The reasoning reflects KBM's low marketing volume (fewer than six campaigns per year), the operational pain MailChimp's spam-protection logic creates around Excel uploads, and KBM's preference for fewer tools. KBM's BRD does not contemplate HubSpot retention because HubSpot is not part of KBM's current stack.

**Pivot's approach.** Pivot's BRD positions HubSpot as the primary marketing automation platform (campaign execution, sophisticated workflows, lead capture, nurture sequences) with NetSuite Orion as the system of record for campaign ROI and unified customer data. The HubSpot ↔ NetSuite integration is bi-directional: HubSpot drives marketing execution, NetSuite holds the closed-loop attribution. Pivot's BRD reflects current platform investment, the marketing team's familiarity with HubSpot's WYSIWYG interface (Prity Lee's stated preference), and the operational scale of Pivot's marketing function.

**Recommendation for the merged company.** Retain HubSpot as the merged-company marketing platform with bi-directional integration to NetSuite Orion. The reasoning is contextual: the merged company inherits Pivot's scale of marketing operations (regular nurture campaigns, event management, lead scoring across multiple segments), and Pivot's marketing team is already operating proficiently in HubSpot. Standing up an equivalent marketing-automation capability inside NetSuite native at this point in the project would re-create work Pivot has already done and would extend the implementation timeline. KBM's marketing team adopts HubSpot for the merged company; KBM's prior MailChimp campaigns either retire or transition to HubSpot. NetSuite Orion is the system of record for the unified customer database, opportunity and revenue data, and campaign ROI attribution — consistent with both BRDs.

The integration architecture is bi-directional: contact and lead data sync between platforms (with NetSuite as the system of record); campaign membership and engagement signals flow from HubSpot to NetSuite for ROI attribution; opportunity and revenue data flow from NetSuite to HubSpot for closed-loop visibility. Specific field mappings, sync triggers, source-of-truth rules per object, and error handling are finalized during the technical design phase. (Cross-Area Decisions Index CT-3 owns the locked direction; CRM §3.02.4 should be read against this section as the home for HubSpot integration.)

**Decisions for the leadership team.**

- (1a) Confirm: HubSpot retained as the merged-company marketing platform. *Recommended default: yes.*
- (1b) Confirm: bi-directional HubSpot ↔ NetSuite Orion integration with NetSuite as system of record for campaign ROI and customer data. *Recommended default: yes.*

---

### D-2. Marketing function scope and operating model

**Source:** KBM REQ-M001, REQ-M003 (`BRD_Marketing_v1.0.md` Solution Areas 6); Pivot's marketing function characterized across all five Pivot Marketing sections; KBM REQ-M015, REQ-M017 on RFP coordination role

**KBM's approach.** KBM's BRD frames the marketing function as a relationship-coordination and RFP-response role rather than a demand-generation operation. Marketing's primary responsibilities are RFP response coordination (replacing the current Asana workflow), targeted relationship communications to specific influencer roles, and showroom event coordination. KBM's BRD explicitly notes the function is "kind of unique because your marketing department is actually doing like some sales process."

**Pivot's approach.** Pivot's BRD describes a more traditional B2B marketing operation: multi-channel lead capture, lead qualification and scoring, automated nurture workflows, comprehensive event campaigns with QR-badge attendance tracking, and closed-loop attribution reporting. Pivot's marketing team is structured around campaign execution, event management, and ROI measurement.

**Recommendation for the merged company.** Operate the merged-company marketing function with both shapes intact, recognizing that they serve different parts of the organization. Pivot's traditional marketing operations (campaigns, events, nurture, attribution) continue at scale for the divisional sales motion; KBM's RFP-coordination role continues for opportunities flowing through the merged-company RFP workflow (cross-references CRM §3.02 D-8 RFP management). The two are complementary: traditional marketing generates and nurtures broader pipeline, RFP coordination supports the response process when formal RFPs are received. Marketing team capacity and structure are determined by the merged-company's operational scale; the system supports both functions through the same Orion + HubSpot configuration.

**Decision for the leadership team.** Confirm: merged-company marketing function combines traditional B2B marketing operations (campaign execution, events, nurture, attribution) with RFP coordination role for formal RFP responses. *Recommended default: yes.*

---

### D-3. Event management

**Source:** KBM REQ-M013, REQ-M014 (`BRD_Marketing_v1.0.md` Solution Area 7); Pivot REQ-3.02.01 through REQ-3.02.07 (`Marketing.md` §3.02)

**KBM's approach.** KBM's BRD positions event management as minimal in Phase 1 and deferred for post-launch evaluation. Showroom tours occur approximately twice per month with personal invitations, occasional showroom events use Google Forms for RSVPs, and major events are handled ad hoc. KBM's BRD does not articulate a need for QR-badge attendance tracking, automated post-event follow-up, or event ROI measurement at the level of capability investment.

**Pivot's approach.** Pivot's BRD articulates comprehensive event management including QR-code badges, custom attendance-tracking dashboard (planned development), automated post-event email sequences, event cost approval workflows (sales-leader approval required), event-ROI measurement linking costs to influenced revenue, and multiple event types (Pivotal Insights events, A&D events, showroom tours, MillerKnoll events). Pivot's BRD names specific stakeholders driving the requirement: Lisa Wuller (event coordination), Yuridia Silvas (Sales Operations, current manual tracking), Roy Stark (SVP Sales, ROI measurement), and Prity Lee (Marketing Director, event strategy).

**Recommendation for the merged company.** Adopt Pivot's comprehensive event management framework as the merged-company baseline. The reasoning is contextual: the merged company's event volume reflects Pivot's existing event cadence (Pivotal Insights, A&D events, showroom tours across multiple California Design Centers, MillerKnoll-Certified events). Manual Excel-based attendance tracking does not scale to that cadence; the custom attendance dashboard and QR-badge generation are appropriate investments. KBM's smaller showroom-event cadence integrates into the same framework. Event-cost approval workflows are configured per Pivot's framework; the actual approval routing follows the merged-company approval framework decided in Order Management §3.04.

**Decisions for the leadership team.**

- (3a) Confirm: comprehensive event management framework adopted (registration, custom attendance dashboard, QR-badge generation, automated post-event follow-up, event-ROI tracking). *Recommended default: yes.*
- (3b) Confirm: event-cost approvals are required prior to event commitment. *Recommended default: yes.* (Approver assignments and routing decided in Order Management §3.04 as part of the merged-company approval framework.)

---

### D-4. Email marketing volume, templates, and creation methodology

**Source:** KBM REQ-M002, REQ-M010 (`BRD_Marketing_v1.0.md` Solution Area 2); Pivot REQ-3.03.01 through REQ-3.03.06 (`Marketing.md` §3.03)

**KBM's approach.** KBM's BRD frames email marketing as low-volume (fewer than six campaigns per year), focused on quarterly market-rate communications to specific segments (brokers, PM firms, CM firms), and intentionally minimal. The team uses Google Slides for image creation and is satisfied with simple templates rather than sophisticated automation. KBM's emphasis is on segmentation accuracy (hitting the right audience) rather than volume or sophistication.

**Pivot's approach.** Pivot's BRD frames email marketing as a regular operating capability supporting nurture campaigns, segmented outreach across the merged-company divisions (per CRM §3.02 D-3b), event invitations, and follow-up sequences. The volume is intentionally regional rather than national. Pivot's BRD also flags a current operating constraint: only approximately 3,400 marketable contacts out of approximately 20,000 total HubSpot records due to opt-in restrictions, which has led to email campaigns being paused while the opt-in posture is addressed. Template creation uses an AI-assisted methodology — marketing staff prompt generative AI tools with brand guidelines and content requirements, then paste the generated HTML into the platform. Pivot's BRD notes Prity Lee's stated preference for WYSIWYG interfaces and the importance of accessibility for non-technical marketing staff.

**Recommendation for the merged company.** Operate the merged-company email function from Pivot's framework — regular cadence supporting nurture, segmented outreach, and event campaigns — using HubSpot as the primary execution platform per D-1. AI-assisted template creation (Pivot's methodology) is adopted for the merged-company marketing team because it lowers the technical barrier to producing branded templates and works with HubSpot's existing tooling. KBM's quarterly market-rate communications to broker / PM / CM firm segments continue as a recurring campaign type alongside Pivot's nurture and event campaigns. Email capacity in NetSuite Orion is sufficient for the merged company at the cadence both BRDs anticipate; specific monthly capacity (KBM's BRD references 120,000/month, Pivot's BRD references both 100,000 and 120,000/month) is confirmed during configuration. Pivot's contact opt-in constraint is addressed during the unified data migration: the merged-company contact base receives an opt-in re-permissioning workflow before regular email campaigns resume, restoring marketable-contact volume.

**Decisions for the leadership team.**

- (4a) Confirm: regular email-marketing cadence supporting nurture, segmented outreach, event campaigns, and quarterly market-rate communications. *Recommended default: yes.*
- (4b) Confirm: AI-assisted template creation methodology adopted for merged-company marketing team. *Recommended default: yes.*

---

### D-5. Lead capture, scoring, and nurturing

**Source:** KBM REQ-M024 (`BRD_Marketing_v1.0.md` Solution Area 3); Pivot REQ-3.04.01 through REQ-3.04.08 (`Marketing.md` §3.04)

**KBM's approach.** KBM's BRD focuses lead capture on the website contact form with auto-routing to an admin role for qualification. KBM's BRD acknowledges that most web form submissions are low-quality (cleaning quotes, consumer requests) and that the most valuable leads come through relationships, not web forms. KBM's BRD does not articulate lead scoring or automated nurturing as Phase 1 capabilities.

**Pivot's approach.** Pivot's BRD articulates a more comprehensive lead-management framework: multi-source lead capture (website forms, events, referrals, manual entry), lead qualification with configurable statuses (Targeting, Unqualified, Qualified, Nurturing), lead scoring to prioritize sales follow-up, automated routing to sales reps based on geography or segment, and 12-week nurture workflows for long sales cycles. Pivot's BRD notes Roy Stark's comment that nurture capability has been a five-year ask.

**Recommendation for the merged company.** Adopt Pivot's lead-management framework as the merged-company baseline. The reasoning is contextual: the merged company's lead volume — Pivot's multi-source channels (website, events, trade shows, A&D events, referrals) plus KBM's web form — benefits from automated qualification, scoring, and routing as standard infrastructure. KBM's qualification process (admin review for ambiguous web-form leads where automated scoring is insufficient) integrates as one path within the broader framework. The 12-week nurture campaigns are built per merged-company segment (per CRM §3.02 D-3b division taxonomy, plus broker / PM / CM segments inherited from KBM's quarterly communications). Specific lead-scoring criteria, routing rules, and nurture-campaign content are defined during configuration with marketing and sales leadership input.

**Decisions for the leadership team.**

- (5a) Confirm: comprehensive lead-management framework (multi-source capture, scoring, automated routing, nurture workflows). *Recommended default: yes.*
- (5b) Confirm: lead-scoring criteria, routing rules, and nurture-campaign designs developed during configuration with marketing and sales leadership. *Recommended default: yes (criteria confirmed during configuration).*

---

### D-6. Multi-dimensional contact segmentation and data quality

**Source:** KBM REQ-M004 through REQ-M008 (`BRD_Marketing_v1.0.md` Solution Area 1); Pivot REQ-3.03.03, REQ-3.05.06 (`Marketing.md` §3.03, §3.05)

**KBM's approach.** KBM's BRD articulates multi-dimensional contact segmentation as a foundational capability — segment by role AND sector AND geography simultaneously, with required-field validation rules to maintain data quality. KBM's BRD names a specific role taxonomy (GC, Broker, A&D Firm, Project Manager, Construction Manager, Finance, Procurement, Facilities, Decision Maker, Executive Sponsor, Manufacturer Rep, Vendor Contact, Office Manager, HR) and a specific sector list (Healthcare, Technology, Corporate Office, Government, Education, Financial Services, Legal, Creative/Agency, Hospitality, Other).

**Pivot's approach.** Pivot's BRD articulates segmentation by market segment (NBD, Venture, Public) and supports targeting through saved searches, with influencer roles (architect, designer, broker, GC, end client) tracked on related contact records. Pivot's BRD does not articulate a comprehensive role-and-sector taxonomy at the level KBM specifies; segmentation is more focused on the divisional dimension than the role × sector × geography matrix.

**Recommendation for the merged company.** Combine both frameworks: adopt KBM's multi-dimensional segmentation model (role × sector × geography) as the contact data foundation, and layer the merged-company division dimension (per CRM §3.02 D-3b) as an additional segmentation axis. Required-field validation, duplicate detection, and contact role taxonomy are configured per KBM's specification. Sector classifications follow KBM's list. This combination gives the merged company precise targeting across both how the merged-company sales organization is structured (by division) and how influencer relationships are organized (role × sector × geography).

**Decision for the leadership team.** Confirm: multi-dimensional segmentation combining role × sector × geography (KBM framework) + market division (Pivot framework, taxonomy per CRM D-3b). *Recommended default: yes.*

---

### D-7. Influencer attribution model

**Source:** Pivot REQ-3.04.06, REQ-3.05.05, REQ-3.05.08 (`Marketing.md` §3.04, §3.05); KBM does not articulate this scope

**KBM's approach.** KBM's BRD captures influencer roles through the contact role taxonomy (Broker, A&D, GC, etc.) and uses segmentation for targeting, but does not articulate an attribution model that quantifies how each influencer contributed to a closed deal. KBM's BRD references "ROI of an investment on a relationship" as an aspirational future capability rather than a Phase 1 requirement.

**Pivot's approach.** Pivot's BRD articulates a custom attribution solution — modifying NetSuite's order-team-assignment utilities to enable assigning influence percentages to different contributors (architects, designers, brokers, GCs) on opportunities. The framework supports closed-loop reporting that quantifies how various influencer relationships drive revenue, justifying relationship-investment decisions. Pivot's BRD positions this as a planned custom development (Accommodate approach).

**Recommendation for the merged company.** Adopt Pivot's custom influencer-attribution framework as a merged-company capability. The reasoning is contextual: the merged company's deal flow involves complex buying committees (Pivot's "our buyer technically isn't our client" reality and KBM's rich influencer-role taxonomy point to the same underlying truth — multiple parties influence each deal). The custom attribution solution gives leadership visibility into which influencer relationships drive revenue, supporting both KBM's stated aspirational ROI question and Pivot's established attribution use case. The attribution capability ties into the multi-company / multi-contact model already locked in CRM §3.02 D-4 and the internal-referral attribution locked at CRM §3.02 D-3c.

**Decision for the leadership team.** Confirm: custom influencer-attribution model adopted (modified order-team-assignment utility with influence-percentage assignment). *Recommended default: yes.* (Specific attribution-model technical design completed during Realize phase.)

---

### D-8. RFP coordination workflow

**Source:** KBM REQ-M015, REQ-M016, REQ-M017, REQ-M018 (`BRD_Marketing_v1.0.md` Solution Area 4); cross-reference CRM §3.02.3 D-8 RFP management

**KBM's approach.** KBM's BRD articulates the RFP coordination workflow in detail because it is the primary marketing function. The workflow includes early opportunity visibility (marketing sees pipeline before formal RFP request submitted), an NetSuite-native RFP request form (replacing Asana), automated workflow routing to assigned Marketing PM, document management on the project record, and projected-vs-actual volume tracking by submitter. KBM's BRD also articulates Philippines team integration for resource-intensive RFP work.

**Pivot's approach.** Pivot's BRD does not articulate the RFP-coordination role within Marketing as KBM does. RFP-related capabilities surface in Pivot's CRM BRD (RFP opportunity type, Kanban Work Board) and are addressed at the CRM-area level. Pivot's marketing team is not structured around RFP coordination as a primary function.

**Recommendation for the merged company.** Adopt KBM's RFP coordination workflow as a merged-company capability for opportunities flowing through the formal RFP process. The reasoning is contextual: the merged company has KBM staff trained in the RFP-coordination role, the workflow has been articulated in detail, and the underlying capability (early-opportunity visibility, request form, workflow routing, volume tracking, project-record document management, Philippines team integration) is valuable independent of which sales function drives the opportunity. Pivot's CRM-area RFP framework (Kanban Work Board with RFP opportunity type, locked in CRM §3.02 D-8) is preserved; the marketing-side workflow this section describes is the request-and-resource-coordination layer that sits alongside it. KBM's existing RFP-coordination role and team structure carry forward; Pivot's marketing team learns the workflow as part of the merged operation.

**Decision for the leadership team.** Confirm: KBM's RFP coordination workflow adopted (early visibility, NetSuite-native request form replacing Asana, workflow routing to Marketing PM, projected-vs-actual volume tracking, Philippines team integration). *Recommended default: yes.*

---

### D-9. Market intelligence dashboards and content planning

**Source:** KBM REQ-M019, REQ-M020, REQ-M021 (`BRD_Marketing_v1.0.md` Solution Area 5); KBM REQ-M026 content library; KBM REQ-M022, REQ-M023 customer surveys (deferred to future phase per source); cross-references BI §3.09 D-1 (governance) and BI §3.09 D-4 (360 dashboards)

**KBM's approach.** KBM articulates a market-intelligence dashboard as a Phase 1 marketing capability: visualize opportunity trends by sector, RFP volume by territory, win/loss by sector, and pipeline by stage and sector. The dashboard supports proactive content planning — when healthcare sector opportunities trend up, marketing allocates time to healthcare-focused content rather than waiting for the next RFP. KBM also articulates a content library management requirement (REQ-M026) for organizing marketing collateral, and customer satisfaction surveys (REQ-M022, REQ-M023) deferred to a post-launch phase.

**Pivot's approach.** Pivot's BRD addresses analytics through marketing performance dashboards, segment-specific performance analysis, and influencer attribution (covered in D-7), but does not articulate a sector-trend market-intelligence dashboard as a separate concept. Pivot's BRD does not articulate a content library or customer satisfaction survey requirement at the same level.

**Recommendation for the merged company.** Build the market-intelligence dashboard as a merged-company Phase 1 capability per KBM's framework, surfaced inside the BI role centers and dashboard governance locked in BI §3.09. The sector-trend visibility supports proactive content planning across the merged-company marketing function. Content library management is configured using NetSuite's standard document-management capabilities (cross-references System Setup §3.10). Customer satisfaction surveys remain deferred to a post-go-live phase consistent with KBM's framing, and are evaluated in coordination with Customer Service.

**Decisions for the leadership team.**

- (9a) Confirm: market-intelligence dashboard built per KBM framework (sector trends, RFP volume by territory, win/loss by sector, pipeline by stage and sector). *Recommended default: yes.*
- (9b) Confirm: customer satisfaction surveys deferred to a post-go-live phase, evaluated in coordination with Customer Service. *Recommended default: yes.*

---

## 3.01.4 Cross-area dependencies

The following surfaced in Marketing discovery but are decided in other process areas. They are flagged here so the working session understands the connections; the decisions themselves live in their proper home area.

| Dependency | Where it surfaced in Marketing | Where it's decided |
|---|---|---|
| **Multi-company / multi-contact relationship model** | Influencer tracking, complex buying-committee management | **CRM (§3.02 D-4)** — relationship model is locked; Marketing surfaces the influencer-role data within that model |
| **Pipeline stage model** | Closed-loop reporting, marketing-influenced pipeline visibility | **CRM (§3.02 D-1)** — 4-stage weighted model is locked; Marketing reports against the locked stages |
| **Division taxonomy** | Market-segment targeting (NBD / Venture / Public / Construction Solutions) | **CRM (§3.02 D-3b)** — division taxonomy pending working-session confirmation; Marketing segmentation aligns to whatever lands |
| **Geography / territory taxonomy** | Geographic segmentation in role × sector × geography model | **CRM (§3.02 D-3a)** — two-dimensional model (geography + division) is locked; Marketing geographic segmentation uses the locked Sales Locations |
| **Internal referral attribution** | Marketing influence in internal cross-division referrals | **CRM (§3.02 D-3c)** — capability locked in CRM; **Commissions (§3.07)** — compensation logic |
| **Approval workflow integration for event costs** | Event-cost approval (D-3b) | **Order Management (§3.04)** — approval framework lives there |
| **Document storage architecture** | RFP documents, event materials, marketing collateral | **System Setup & Configuration (§3.10)** — document migration plan; Pivot SharePoint integration consideration |
| **Historical marketing data migration** | Campaign history, lead source attribution baseline | **System Setup & Configuration (§3.10)** — overall data migration plan; HubSpot historical data migration scope |
| **HubSpot integration field mapping** | Bi-directional sync configuration (D-1b) | **System Setup & Configuration (§3.10)** — integration architecture and field-mapping specifications during technical design |
| **ZoomInfo data enrichment** | Lead and contact enrichment evaluation | Pivot SuiteApp summary lists this as "Under Evaluation"; **deferred to Realize-phase decision** with documented business case before Phase 2 |

## 3.01.5 Recommendation summary

The merged-company Marketing playbook in shorthand:

- **Platform architecture:** HubSpot retained as primary marketing automation platform; NetSuite Orion as system of record for campaign ROI, lead/opportunity, and unified customer data; bi-directional integration
- **Marketing function scope:** Combined — traditional B2B marketing (campaigns, events, nurture, attribution) for the divisional sales motion + RFP coordination role (KBM's framework) for formal RFP responses
- **Event management:** Comprehensive — registration, custom attendance dashboard with QR-badge generation, automated post-event follow-up, event-ROI tracking, multiple event types
- **Email marketing:** Regular cadence (nurture, segmented outreach, event campaigns, quarterly market-rate communications) with AI-assisted template creation methodology
- **Lead management:** Multi-source capture, lead qualification with scoring, automated routing, 12-week nurture workflows
- **Contact segmentation:** Multi-dimensional (role × sector × geography from KBM) + division (per CRM §3.02 D-3b)
- **Influencer attribution:** Custom modified order-team-assignment utility with influence-percentage assignment
- **RFP coordination:** KBM's framework adopted (early visibility, NetSuite-native request form replacing Asana, workflow routing, volume tracking, Philippines team integration)
- **Web-to-lead:** Standard NetSuite capability with auto-routing to admin queue or assigned sales rep
- **Market intelligence:** Sector-trend dashboard built per KBM framework, surfaced through BI §3.09 governance
- **Document management:** Document storage architecture decided in System Setup §3.10 (KBM Google Drive vs. Pivot SharePoint reconciliation)

Net read: the merged-company Marketing function combines design choices that fit the merged-company's situation. Pivot's contributions reflect its operational scale and divisional structure (HubSpot platform, comprehensive event management, lead scoring and nurture, influencer attribution, AI-assisted templates). KBM's contributions reflect its data-discipline orientation and RFP-coordination experience (multi-dimensional segmentation, contact role and sector taxonomy depth, RFP request-and-resource workflow, Philippines team integration). The merged company benefits from both.

## 3.01.6 Decisions for the leadership team

| # | Decision | Default | Reference |
|---|---|---|---|
| 1a | HubSpot retained as merged-company marketing platform | Yes | D-1 |
| 1b | Bi-directional HubSpot ↔ NetSuite Orion integration with NetSuite as system of record for campaign ROI and customer data | Yes | D-1 |
| 2 | Combined marketing function scope (traditional B2B marketing + RFP coordination) | Yes | D-2 |
| 3a | Comprehensive event management framework (registration, custom attendance dashboard, QR badges, follow-up, ROI tracking) | Yes | D-3 |
| 3b | Event-cost approval workflow with sales-leader approval, integrated with merged approval framework | Yes | D-3 |
| 4a | Regular email-marketing cadence supporting nurture, segmented outreach, event campaigns, and quarterly communications | Yes | D-4 |
| 4b | AI-assisted template creation methodology adopted for marketing team | Yes | D-4 |
| 5a | Comprehensive lead-management framework (multi-source capture, scoring, automated routing, nurture workflows) | Yes | D-5 |
| 5b | Lead-scoring criteria, routing rules, and nurture-campaign designs developed during configuration | Yes | D-5 |
| 6 | Multi-dimensional segmentation combining role × sector × geography + market division | Yes | D-6 |
| 7 | Custom influencer-attribution model (modified order-team-assignment utility with influence percentages) | Yes | D-7 |
| 8 | RFP coordination workflow adopted from KBM framework | Yes | D-8 |
| 9a | Market-intelligence dashboard built per KBM framework | Yes | D-9 |
| 9b | Customer satisfaction surveys deferred to post-go-live phase | Yes | D-9 |

> 14 decisions, all with default-yes recommendations. None require leadership-team input during the working session beyond confirmation.

## 3.01.7 Configuration carryover

| Item | KBM-side built? | Pivot-side built? | Action for merged company |
|---|---|---|---|
| HubSpot integration | Not specified (no HubSpot at KBM) | Specified | Build per D-1 |
| Email marketing platform | MailChimp in use; specified to retire | HubSpot in use | Retire MailChimp; consolidate on HubSpot per D-1 |
| Event management capability | Minimal (Google Forms RSVP) | Custom attendance dashboard specified, not yet built | Build per D-3 |
| Lead scoring and routing | Not specified | Specified, not yet built | Build per D-5 |
| Nurture workflows (12-week) | Not specified | Specified, not yet built | Build per D-5 |
| Multi-dimensional contact segmentation | Specified (custom role + sector + territory fields) | Specified for division-level segmentation | Build combined per D-6 |
| Custom contact role taxonomy | Specified (14-role list) | Specified (architect, designer, broker, GC, end client) | Configure merged taxonomy per D-6 |
| Influencer attribution (custom) | Not specified | Specified (modified order-team-assignment utility) | Build per D-7 |
| RFP request workflow | Specified (replaces Asana) | Not specified | Build per D-8 |
| Web-to-lead forms | Specified | Specified | Configure per common-ground items |
| Google Drive integration | Specified | Not specified (Pivot uses SharePoint) | Decided in System Setup §3.10 |
| Philippines team integration | Specified (RFP resource time tracking) | Not specified | Configure per D-8 |
| Quarterly market-rate communications campaigns | Specified | Not specified directly | Build as recurring campaign type per D-4 |

Configuration is in early enough state on both sides that the merged direction is achievable without significant rework. Pivot's HubSpot integration and event-management capability are partially specified but not yet built; KBM's RFP workflow and segmentation framework are specified but not yet configured.

## 3.01.8 Open questions / inputs needed

1. **HubSpot integration field mapping** — bi-directional sync configuration, source-of-truth rules, and error handling are finalized during the technical design phase (cross-references System Setup §3.10).
2. **Lead-scoring criteria** (decision 5b) — demographic and behavioral factors, score thresholds, and weighting are defined during configuration with marketing and sales leadership.
3. **Routing rules** — automated lead-routing criteria (geography, segment, project size) defined during configuration.
4. **Nurture workflow content** — specific 12-week nurture-campaign content, segment-specific messaging, and trigger criteria defined during configuration.
5. **Custom contact role taxonomy reconciliation** — the 14-role KBM taxonomy and Pivot's role list (architect, designer, broker, GC, end client) reconcile during configuration with both leadership teams.
6. **Custom attendance dashboard specifications** — check-in workflow, badge-printing integration, and real-time-update technical design developed during Realize phase.
7. **Influencer-attribution model technical design** — data structure for influence percentages, reporting requirements, and integration with order-team-assignment utility defined during Realize phase.
8. **Online lead-form standardization** — specific form fields, current-form consolidation, and 2-3 form-template designs defined during configuration.
9. **Email-template count** — number of initial branded email templates to create defined during implementation planning, with brand guidelines provided.
10. **Historical data migration scope** — campaign history, lead source attribution baseline, and HubSpot historical data migration timeline (12 months / 24 months / full history) defined as part of the merged-company data migration plan in System Setup §3.10.
11. **ZoomInfo evaluation** — data enrichment service business case and Phase 2 decision documented during Realize phase.
12. **Email capacity discrepancy** — KBM BRD references 120,000/month NetSuite Orion email capacity; Pivot BRD references both 120,000 and 100,000/month in different sections. Specific monthly capacity for the merged company confirmed during configuration.
13. **Opt-in re-permissioning workflow** — Pivot's current marketable-contact-volume constraint (~3,400 of ~20,000 records) addressed through merged-company opt-in re-permissioning workflow during data migration; specific approach and messaging defined during configuration.
14. **Market-intelligence dashboard component design** — sector-trend visualizations, RFP volume by territory, win/loss by sector, and pipeline by stage and sector dashboard designs developed during BI §3.09 dashboard configuration.
15. **Content library structure** — KBM REQ-M026 content library management organized using standard NetSuite document-management capabilities; specific folder structure and access permissions defined during configuration in coordination with System Setup §3.10.
