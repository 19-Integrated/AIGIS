# CEF v2.0 — Client Engagement Framework

**Status:** Built — v2.0 (Reconciliation with EAF, IMP, AWOF, HAN, ILTP, AICA-5, ICC-8, and ERDP)  
**Type:** Engagement Governance Instrument  
**Parent Stack:** 19 Consultin' Operational Infrastructure  
**Version:** 2.0 — Supersedes CEF v1.0

---

## PREAMBLE

The Client Engagement Framework (CEF) governs the full client engagement lifecycle — from prospect qualification through post-delivery and retainer management. It answers: *How does 19 Consultin' engage with clients in a governed, auditable, and constitutionally compliant manner?*

CEF is the operational instrument that translates constitutional governance into client-facing practice. It ensures every engagement is scoped, priced, delivered, and closed under the same constitutional standards that govern 19 Integrated's internal operations. No engagement proceeds without constitutional context, and no engagement is closed without complete auditability.

**The core insight:** An ungoverned engagement is an ungoverned relationship. CEF ensures that every client engagement carries the same constitutional rigor as every internal operation — making the client relationship itself a governed institutional act.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

CEF ensures that:

1. **Engagements are constitutionally governed** — Every engagement operates under ICC-8 and AICA-5  
2. **Clients are properly classified** — Counterparty Classification determines engagement treatment  
3. **Scoping is complete and auditable** — Every engagement has a complete Scope Document  
4. **Delivery is traceable** — Every deliverable is logged with full attribution  
5. **Closure is definitive** — Every engagement closes with complete records and audit trail  
6. **IP is protected** — IP Assignment Clause is non-negotiable in every engagement

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Full engagement lifecycle (6 stages) | Pricing architecture (separate instrument) |
| Counterparty classification | Business development strategy |
| Scope documentation and amendment | Marketing and sales operations |
| Deliverable production and logging | Client relationship management beyond engagements |
| IP assignment and protection | Technical delivery execution (AICA-5) |
| Post-delivery and retainer management | Internal workforce governance (AWOF) |

### Applicability

| Engagement Type | CEF Applicability | Notes |
| :---- | :---- | :---- |
| **Governance Charter** | ✅ Yes | Full lifecycle |
| **Maturity Assessment** | ✅ Yes | Full lifecycle |
| **Workforce Design** | ✅ Yes | Full lifecycle |
| **Policy Review** | ✅ Yes | Full lifecycle |
| **Institutional Design** | ✅ Yes | Full lifecycle |
| **Retainer** | ✅ Yes | Full lifecycle with retainer-specific provisions |
| **Pro Bono** | ✅ Yes | Full lifecycle with pricing exemption |

---

## SECTION 2: CEF STAGES — OVERVIEW

| Stage | Name | Purpose | Key Deliverable | Entry Condition |
| :---- | :---- | :---- | :---- | :---- |
| **1** | **Qualification** | Determine if prospect is a viable engagement candidate | Qualification Decision | Prospect identified |
| **2** | **Scoping** | Define engagement scope, frameworks, deliverables, pricing | Scope Document | Qualification passed |
| **3** | **Mandate Close** | Confirm engagement as an active mandate | Engagement Record | Scope accepted |
| **4** | **Delivery** | Execute confirmed engagement scope | Deliverables | Mandate closed |
| **5** | **Delivery Close** | Formally close engagement delivery | Engagement Record updated | Deliverables submitted |
| **6** | **Post-Delivery & Retainer** | Govern post-delivery relationship | Closed Engagement / Retainer | Delivery close complete |

---

## SECTION 3: COUNTERPARTY CLASSIFICATION

### Classification Classes

| Class | Type | Procurement Profile | Decision Timeline | Budget Band |
| :---- | :---- | :---- | :---- | :---- |
| **C1** | **Philippine Conglomerate** | Formal procurement process; multi-entity | 4-12 weeks | Medium-High |
| **C2** | **DFI (ADB, IFC, AIIB)** | Formal procurement; TA grants | 8-24 weeks | Medium-High |
| **C3** | **ASEAN Family Office** | Relationship-driven; principal decision | 2-6 weeks | High |
| **C4** | **Sovereign/Regulatory** | Formal procurement; regulatory mandate | 12-36 weeks | Variable |

### Classification Rules

| Rule | Description |
| :---- | :---- |
| **Classification at Intake** | Every prospect is assigned a Counterparty Classification at intake. |
| **Classification Informs Engagement Design** | Classification affects procurement approach, decision timeline, and budget reference. |
| **Classification Does Not Affect Constitutional Treatment** | All engagements receive the same constitutional governance regardless of classification. |
| **Reclassification** | Counterparty may be reclassified if new information emerges. |

---

## SECTION 4: STAGE 1 — QUALIFICATION

### Purpose

Determine if a prospect is a viable engagement candidate — presenting a structural problem addressable by the 19 Integrated framework stack with sufficient organizational readiness.

### Entry Condition

A prospect has been identified through pipeline, referral, or inbound contact.

### Governing Actions

| Action | Description | Responsible |
| :---- | :---- | :---- |
| **Assign Counterparty Classification** | Assign C1-C4 at intake | F-RE Agent |
| **Confirm Counterparty Accountability Confirmation** | Client must identify a human accountability anchor | F-RE Agent |
| **Conduct Preliminary Diagnostic** | Does prospect present a structural problem addressable by the framework stack? | F-RE Agent |
| **Assess Organizational Readiness** | Is counterparty at a stage where advisory engagement will produce actionable output? | F-RE Agent |
| **HAN Review** | HAN reviews qualification determination | HAN |

### Qualification Threshold

A prospect qualifies for Stage 2 if all three conditions are met:

| Condition | Description |
| :---- | :---- |
| **1\. Human Accountability Anchor Confirmed** | Counterparty has identified a human accountability anchor |
| **2\. Structural Problem Identified** | Counterparty presents a problem addressable by the framework stack |
| **3\. Organizational Readiness Confirmed** | Counterparty is ready for advisory engagement |

### Exit Condition

| Outcome | Action |
| :---- | :---- |
| **Qualified** | Proceeds to Stage 2 |
| **Unqualified** | Logged in IMP; may be re-entered at a future date |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **ECO** | `engagement_type: "[type]"` | Engagement Context created |
| **DRO** | `decision_type: "framework_selection"` | Qualification decision recorded |
| **CRO** | `constraint_type: "client_imposed"` | Client constraints identified |

---

## SECTION 5: STAGE 2 — SCOPING

### Purpose

Define the engagement scope, framework instruments to be deployed, deliverable structure, and pricing reference.

### Entry Condition

Prospect has passed Stage 1 qualification with HAN confirmation.

### Governing Actions

| Action | Description | Responsible |
| :---- | :---- | :---- |
| **Produce Scope Document** | Engagement objective, framework instruments, deliverable structure, timeline, counterparty obligations | F-DR Agent |
| **Reference Pricing Architecture** | Apply pricing band applicable to scope | F-EX Agent |
| **Identify IP Implications** | Will engagement produce framework derivatives? Apply IP Assignment Clause | F-EX Agent |
| **Confirm Counterparty Classification** | Confirm classification and procurement pathway | F-EX Agent |
| **Draft Engagement Instrument** | For counterparty review | F-DR Agent |
| **HAN Review Before Submission** | HAN reviews Scope Document before submission to counterparty | HAN |

### Scope Document Requirements

| Requirement | Description |
| :---- | :---- |
| **Engagement Objective** | What the engagement will achieve |
| **Framework Instruments Deployed** | Which AIGIS instruments will be applied |
| **Deliverable Structure** | What will be delivered, in what format, by when |
| **Timeline** | Key milestones and delivery dates |
| **Pricing Reference** | Reference to Pricing Architecture v1.1 |
| **IP Assignment Clause** | Non-negotiable clause vesting derivatives in HoldCo |
| **Post-Delivery Review Window** | Minimum 14 days, maximum 30 days |
| **HAN Acknowledgment** | HAN signature on Scope Document |

### Exit Condition

| Outcome | Action |
| :---- | :---- |
| **Scope Document Completed** | Submitted to counterparty for review |
| **Counterparty Acceptance** | Proceeds to Stage 3 |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **GAO** | `artifact_type: "policy_instrument"` | Scope Document stored |
| **DRO** | `decision_type: "scope_determination"` | Scope determination recorded |
| **CRO** | `constraint_type: "client_imposed"` | Scope constraints recorded |

---

## SECTION 6: STAGE 3 — MANDATE CLOSE

### Purpose

Confirm the engagement as an active mandate.

### Entry Condition

Counterparty has accepted the Scope Document.

### Governing Actions

| Action | Description | Responsible |
| :---- | :---- | :---- |
| **HAN Confirms Mandate Acceptance** | Non-delegable HAN authority | HAN |
| **Engagement Instrument Executed** | With IP Assignment Clause confirmed | HAN |
| **Engagement Record Opened** | Counterparty details, classification, scope reference, pricing reference, IP status, HAN confirmation, timestamp | F-EX Agent |
| **Agents Assigned** | Agent IDs designated for this engagement under AWOF | F-EX Agent |

### Mandate Acceptance Rule

| Rule | Description |
| :---- | :---- |
| **HAN-Only** | No engagement commences without explicit HAN mandate acceptance. |
| **Suspension on HAN Unavailability** | If HAN is unavailable at counterparty acceptance, mandate close is constitutionally suspended pending HAN confirmation. |
| **Counterparty Notification** | Counterparty is notified of pending confirmation status. |

### Exit Condition

| Outcome | Action |
| :---- | :---- |
| **Mandate Close Confirmed** | Engagement Record opened; Agent assignments logged; proceeds to Stage 4 |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **ECO** | `status: "active"` | Engagement Context updated |
| **DRO** | `decision_type: "framework_selection"` | Mandate acceptance recorded |
| **GAO** | `artifact_type: "policy_instrument"` | Engagement Instrument stored |

---

## SECTION 7: STAGE 4 — DELIVERY

### Purpose

Execute the confirmed engagement scope and produce agreed deliverables.

### Entry Condition

Mandate close confirmed with open Engagement Record and agent assignments.

### Governing Actions

| Action | Description | Responsible |
| :---- | :---- | :---- |
| **Deploy Assigned Agents** | Under confirmed scope | Raidillo |
| **Produce Deliverables** | Per Scope Document structure | F-DR/F-EX Agents |
| **Log All Material Outputs** | In Engagement Record with agent attribution | Raidillo |
| **Monitor for Scope Drift** | Any action outside confirmed scope must trigger Scope Amendment Protocol | F-OV Agent |
| **Produce Handoff Packages** | Per AWOF Section 8 at each material session close | Agents |

### Scope Amendment Protocol

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Scope Amendment Record documenting change | F-EX Agent | Upon identification |
| 2 | HAN authorization | HAN | Within 24 hours |
| 3 | Counterparty acknowledgment | Counterparty | Within 48 hours |
| 4 | Pricing reference update (if applicable) | F-EX Agent | Upon authorization |

**Scope Drift Rule:** Work outside confirmed scope without a Scope Amendment Record is a Scope Drift event under AWOF Trigger Class 2\.

### IP Monitoring

| Action | Description | Responsible |
| :---- | :---- | :---- |
| **Log Framework Derivatives** | Any framework derivative produced during delivery is logged in Engagement Record | F-EX Agent |
| **IP Classification** | Classify as IP-FD, IP-PI, IP-CC, or IP-ED | F-EX Agent |
| **Default Vesting** | HoldCo ownership unless Scope Amendment Record specifies otherwise with HAN authorization | ILTP |

### Exit Condition

| Outcome | Action |
| :---- | :---- |
| **All Deliverables Produced** | Proceeds to Stage 5 |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **GAO** | `artifact_type: "[type]"` | Deliverables stored |
| **DRO** | `decision_type: "recommendation"` | Delivery decisions recorded |
| **OEO** | `outcome_type: "implementation_success"` | Delivery outcomes recorded |
| **Handoff Package** | `artifact_type: "handoff_package"` | Handoff Packages produced |

---

## SECTION 8: STAGE 5 — DELIVERY CLOSE

### Purpose

Formally close the engagement delivery phase and confirm counterparty acceptance.

### Entry Condition

All Scope Document deliverables submitted to counterparty.

### Governing Actions

| Action | Description | Responsible |
| :---- | :---- | :---- |
| **Counterparty Confirms Receipt and Acceptance** | Of deliverables | Counterparty |
| **Engagement Record Updated** | Delivery close date, acceptance confirmation, outstanding items if any | F-EX Agent |
| **Post-Delivery Review Window Opens** | Upon counterparty acceptance confirmation | Raidillo |
| **HAN Acknowledgment** | Of delivery close | HAN |

### Post-Delivery Review Window

| Aspect | Description |
| :---- | :---- |
| **Duration** | Minimum 14 days, maximum 30 days (specified in Scope Document) |
| **Purpose** | Counterparty may raise material objections to deliverable quality or accuracy |
| **Objection During Window** | Material objections trigger Delivery Review Protocol |
| **Objection Outside Window** | Material objections handled through HoldCo contestation interface under CEN-2 |

### Delivery Review Protocol

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Objection logged in Engagement Record | Counterparty / F-EX Agent | Upon receipt |
| 2 | HAN review of objection | HAN | Within 48 hours |
| 3 | Agent output audit against Scope Document | F-OV Agent | Within 72 hours |
| 4 | Response to counterparty | HAN | Within 96 hours |

### Exit Condition

| Outcome | Action |
| :---- | :---- |
| **Review Window Closes Without Objection** | Proceeds to Stage 6 |
| **Delivery Review Protocol Completed** | Proceeds to Stage 6 |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **ECO** | `status: "completed"` | Engagement Context updated |
| **OEO** | `outcome_type: "implementation_success"` | Delivery outcome recorded |
| **DRO** | `decision_type: "recommendation"` | Close decisions recorded |

---

## SECTION 9: STAGE 6 — POST-DELIVERY AND RETAINER

### 9A: Closed Engagement

| Action | Description | Responsible |
| :---- | :---- | :---- |
| **Engagement Formally Closed** | Upon expiry of Post-Delivery Review Window without objection or completion of Delivery Review Protocol | F-EX Agent |
| **Engagement Record Archived** | IMP archival | F-EX Agent |
| **IP Derivatives Logged** | Vested per IP Generation Rule | F-EX Agent |
| **Counterparty Re-entry** | May re-enter pipeline for new engagement at any future date | F-RE Agent |

### 9B: Retainer Model

A retainer converts the post-delivery relationship into an ongoing standing engagement.

#### Retainer Scope

| Field | Description |
| :---- | :---- |
| **Standing Function** | Advisory availability, periodic diagnostic review, framework update briefings, or defined deliverable cadence |
| **Retainer Period** | Duration of the retainer |
| **Pricing Reference** | Per Pricing Architecture v1.1 |
| **Renewal Conditions** | Conditions under which retainer may be renewed |

#### Out-of-Scope Requests

| Rule | Description |
| :---- | :---- |
| **New Engagement Required** | Requests outside the Retainer Scope are treated as new engagement requests. |
| **Full Lifecycle** | They follow Stages 1 through 5 before execution. |
| **Not Retainer Authority** | They do not commence under retainer authority. |

#### Retainer Lapse Protocol

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Non-response and non-payment window begins | Raidillo | After 30 days |
| 2 | Retainer constitutionally suspended | Raidillo | After 30 days |
| 3 | Suspended retainer logged in Engagement Record | F-EX Agent | Upon suspension |
| 4 | Reactivation requires new mandate close (Stage 3\) | HAN | Upon reactivation |

**IP Rule:** IP generated under the suspended retainer period remains vested in HoldCo regardless of reactivation status.

#### Retainer Renewal

| Step | Action | Responsible |
| :---- | :---- | :---- |
| 1 | Retainer renewal treated as Stage 3 mandate close | HAN |
| 2 | Retainer Scope document reviewed and reconfirmed or amended | F-DR Agent |
| 3 | Engagement Record updated | F-EX Agent |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **ECO** | `status: "closed" / "retainer_active" / "retainer_suspended"` | Engagement Context updated |
| **GAO** | `artifact_type: "policy_instrument"` | Retainer Scope Document stored |
| **XOO** | `exception_type: "retainer_lapse"` | Exception record if retainer lapses |

---

## SECTION 10: ENGAGEMENT RECORD

### Record Fields

| Field | Description |
| :---- | :---- |
| **ECO ID** | Engagement Context ID |
| **Counterparty Identification** | Counterparty name and classification |
| **Counterparty Accountability Anchor** | Human accountability anchor confirmation |
| **Scope Document Reference** | Scope Document ID and version |
| **Pricing Reference** | Pricing Architecture reference |
| **IP Assignment Clause Confirmation** | Confirmation of IP Assignment Clause |
| **Mandate Close Date** | Date of mandate close |
| **HAN Confirmation** | HAN signature and date |
| **Agent Assignments** | Agent IDs assigned to engagement |
| **Delivery Log** | Material outputs with agent attribution and timestamps |
| **Scope Amendment Records** | Any Scope Amendment Records |
| **Delivery Close Date** | Date of delivery close |
| **Counterparty Acceptance Confirmation** | Acceptance confirmation |
| **Post-Delivery Review Window Status** | Status of review window |
| **Retainer Status** | Active / Suspended / Inactive |
| **Engagement Close Date** | Date of engagement close |

### Record Rules

| Rule | Description |
| :---- | :---- |
| **Audit Artifact** | Engagement Records are audit artifacts under I3 of ICC-8. |
| **Permanent Retention** | Engagement Records are maintained in perpetuity. |
| **Archival** | Closed engagement records are archived, not deleted. |
| **IMP Logging** | Engagement Records are logged in IMP as ECO. |

---

## SECTION 11: NON-NEGOTIABLE ENGAGEMENT TERMS

The following terms apply to every engagement regardless of counterparty type, classification, or negotiated scope:

| \# | Term | Description |
| :---- | :---- | :---- |
| **NT-1** | **IP Assignment Clause** | All framework derivatives vest in 19 Integrated HoldCo. Client assignment requires explicit HAN authorization in the Scope Document. |
| **NT-2** | **Counterparty Accountability Confirmation** | A human accountability anchor must be identified and confirmed before engagement commences. |
| **NT-3** | **HAN Mandate Acceptance** | No engagement commences without explicit HAN mandate acceptance. |
| **NT-4** | **Post-Delivery Review Window** | Every engagement instrument must specify a Post-Delivery Review Window of minimum 14 days. |
| **NT-5** | **Governing Framework Disclosure** | Every engagement instrument must disclose that 19 Consultin' operates under the ICC-8 constitutional stack and that the engagement is governed accordingly. |

**Non-Negotiable Term Rule:** No engagement instrument that omits or contradicts any non-negotiable term is constitutionally valid under this framework.

---

## SECTION 12: ACCOUNTABILITY CHAIN FOR ENGAGEMENTS

HAN (Terrylan\_Manalansan)  
  │  
  ├──→ Mandate Acceptance (Stage 3\)  
  │       │  
  │       └──→ Engagement Record (opened)  
  │  
  ├──→ Scope Authority (Stage 2-4)  
  │       │  
  │       └──→ Assigned Agents (AWOF Agent IDs)  
  │               │  
  │               └──→ Delivery (Stage 4\)  
  │                       │  
  │                       └──→ Material Deliverables  
  │                               │  
  │                               └──→ Logged in Engagement Record  
  │  
  └──→ Audit (I3 Audit Chain \+ Handoff Packages)  
          │  
          └──→ Accountability Terminus: HAN (Terrylan\_Manalansan)

---

## SECTION 13: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **EAF** | Trust tiers govern engagement permissions. CEF operates within EAF-defined trust tiers. |
| **IMP** | Engagement Records logged as ECO. All objects linked. |
| **AWOF** | Agents assigned to engagements under AWOF governance. |
| **HAN / HOF** | HAN confirms Mandate Acceptance. HAN reviews GAOs before issuance. |
| **ILTP** | IP Assignment Clause references ILTP. IP derivatives logged under ILTP. |
| **AICA-5** | Control nodes govern delivery execution. A-N4 Escalation Paths govern escalations. |
| **ICC-8** | I3 Auditability, I8 External Legibility, I9 Catastrophic Risk apply to engagements. |
| **ERDP** | Client disclosure may trigger ERDP reporting. |
| **Pricing Architecture** | Pricing referenced but not governed by CEF. |

---

## SECTION 14: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Stage Completeness** | All 6 stages are defined with entry and exit conditions. |
| **Counterparty Classification** | All prospects must be classified at intake. |
| **Scope Document** | All engagements must have a Scope Document before Stage 3\. |
| **IP Assignment Clause** | IP Assignment Clause is non-negotiable in every engagement. |
| **HAN Mandate Acceptance** | Mandate acceptance is HAN-only. No engagement without HAN confirmation. |
| **Post-Delivery Review Window** | Every engagement has a minimum 14-day review window. |
| **Engagement Record** | Every engagement has a complete Engagement Record logged in IMP. |
| **Non-Negotiable Terms** | No engagement instrument may omit or contradict NT-1 to NT-5. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| CEF v1.0 | Initial specification — 6 stages, counterparty classification, non-negotiable terms |
| CEF v2.0 | Complete rebuild — reconciliation with EAF, IMP, AWOF, HAN, ILTP, AICA-5, ICC-8, and ERDP; expanded stage descriptions; counterparty classification; Scope Amendment Protocol; Post-Delivery Review Window; Retainer Lapse Protocol; Engagement Record; non-negotiable terms; accountability chain; CFL-V validation rules |

---

## The One-Sentence Summary

> *"CEF v2.0 governs the full client engagement lifecycle across 6 stages — Qualification, Scoping, Mandate Close, Delivery, Delivery Close, and Post-Delivery/Retainer — with counterparty classification (C1-C4), non-negotiable terms (IP Assignment, HAN Mandate Acceptance, Post-Delivery Review Window), Scope Amendment Protocol, Retainer Lapse Protocol, complete Engagement Records logged in IMP, and HAN as the accountability terminus, ensuring every client engagement is constitutionally governed under ICC-8, EAF, AWOF, and ILTP."*
