# CGF v2.0 — Certification Governance Framework

**Status:** Built — v2.0 (Reconciliation with ICC-8, ILTP, AWOF, HAN/HOF, IMP, ERDP, and DEP)  
**Type:** Certification Governance Instrument  
**Parent Stack:** 19 Institute Operational Infrastructure  
**Version:** 2.0 — Supersedes CGF v1.0

---

## PREAMBLE

The Certification Governance Framework (CGF) governs the full certification lifecycle — designation registration, candidate assessment, award, maintenance, revalidation, and revocation — across all current and future 19 Institute designations. It answers: *How are 19 Institute designations created, awarded, maintained, revalidated, and revoked under constitutional governance?*

CGF establishes the constitutional basis for the certification function and the operational standards through which that function is executed. It applies to all current designations and all future designations registered under this framework. It does not govern curriculum content — that is governed under IP-CC assets registered in ILTP. It governs the rights, obligations, and governance architecture of the certification function itself.

**The core insight:** A certification without governance is a credential without credibility. CGF ensures that every designation issued by 19 Institute carries constitutional validity, external legibility, and a governed lifecycle — making the certification function an institutional asset rather than a reputational claim.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

CGF ensures that:

1. **Designations are governed** — All designations are registered, assessed, awarded, maintained, and revoked under defined governance  
2. **Assessment is rigorous** — Examination \+ Portfolio model tests both comprehension and applied judgment  
3. **Maintenance is continuous** — Periodic renewal \+ Event-triggered revalidation ensure designations remain current  
4. **External legibility is maintained** — Public Designation Register provides verification of status  
5. **Due process is preserved** — Candidate contestation and revocation proceedings follow defined protocols  
6. **Constitutional validity is established** — All designations derive validity from ICC-8 constitutional stack

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Designation Register (Active \+ Placeholder) | Curriculum content (IP-CC assets) |
| Assessment Model (Examination \+ Portfolio) | Program marketing or sales |
| Maintenance Model (Periodic Renewal \+ Event-Triggered Revalidation) | External accreditation (constitutional basis established) |
| Public Designation Register | Business strategy |
| Candidate Contestation Protocol | Operational efficiency |
| Revocation Proceedings | Technical delivery execution |

### Governing Relationships

| Instrument | Relationship to CGF |
| :---- | :---- |
| **ICC-8** | Constitutional ceiling — CGF operates under ICC-8 invariants |
| **ILTP** | IP instrument — IP-CC assets, Curriculum Version Binding, placeholder registration |
| **AWOF** | Workforce instrument — agent roles in assessment and administration |
| **HAN/HOF** | Human authority — non-delegable certification authorities reserved for HAN |
| **IMP** | Certification records logged as GAO, DRO, OEO, XOO |
| **ERDP** | Designation activity feeds ERDP reporting |
| **DEP** | CGF amendments require DEP process |

---

## SECTION 2: DESIGNATION REGISTER

### Purpose

The Designation Register is the authoritative record of all certification programs under CGF governance.

### Entry Requirements

| \# | Field | Description |
| :---- | :---- | :---- |
| 1 | **Designation Name and Post-Nominal** | Formal name and post-nominal letters |
| 2 | **Designation Class** | Practitioner — Foundation / Practitioner — Applied / Practitioner — Senior / Specialist / Fellowship |
| 3 | **Governing Framework Reference** | IP-CC asset under ILTP |
| 4 | **Bound IP-FD Version Reference** | IP-FD version bound to curriculum at program launch |
| 5 | **Assessment Model** | Examination, Portfolio, or both |
| 6 | **Maintenance Model** | Periodic renewal cycle, event-triggered revalidation, or both |
| 7 | **Launch Status** | Active / Placeholder / Retired |
| 8 | **IP Register Cross-Reference** | ILTP registration date — establishes priority |
| 9 | **HAN Acknowledgment Date** | HAN signature and date |
| 10 | **Target Launch Date** | For Placeholder designations |
| 11 | **Revalidation Trigger History** | Record of event-triggered revalidations |

### Placeholder Designations

| Rule | Description |
| :---- | :---- |
| **Creation Date Priority** | Placeholder registration in the Designation Register and IP Register establishes creation date priority before program launch. |
| **Full Fields** | Placeholder entries carry all required fields with a target launch date where known. |
| **No Program Delivery** | Placeholder designations are not active delivery programs until launched. |
| **IP-CC Asset** | Placeholder designations are registered in ILTP as IP-CC assets. |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **GAO** | `artifact_type: "policy_instrument"` | Designation Register entry stored as GAO |
| **DRO** | `decision_type: "framework_selection"` | Designation registration recorded |

---

## SECTION 3: CURRENT DESIGNATION REGISTER

### Active Designations

| Designation | Post-Nominal | Class | Governing Framework | Assessment Model | Maintenance Model | Status |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| AICA-5 Certified Associate | CA | Practitioner — Foundation | AICA-5 v2.0 | Examination \+ Portfolio | Periodic renewal (2-year) \+ Event-triggered | Active |
| AICA-5 Certified Implementer | CI | Practitioner — Applied | AICA-5 v2.0 | Examination \+ Portfolio | Periodic renewal (2-year) \+ Event-triggered | Active |
| AICA-5 Certified Governance Officer | CGO | Practitioner — Senior | AICA-5 v2.0 | Examination \+ Portfolio | Periodic renewal (2-year) \+ Event-triggered | Active |

### Placeholder Designations

| Designation | Post-Nominal | Class | Governing Framework | Status |
| :---- | :---- | :---- | :---- | :---- |
| MICOS-25 Certified Practitioner | MCP | Practitioner — Foundation | MICOS-25 | Placeholder |
| MICOS-25 Certified Architect | MCA | Practitioner — Senior | MICOS-25 | Placeholder |
| ICC-8 Certified Constitutional Officer | CCO | Specialist | ICC-8 | Placeholder |
| 19 Integrated Fellow | FI19 | Fellowship | Full stack | Placeholder |

### Designation Class Definitions

| Class | Description | Assessment Focus |
| :---- | :---- | :---- |
| **Practitioner — Foundation** | Entry-level competence in governing framework. Demonstrates comprehension and basic application. | Framework comprehension, basic application |
| **Practitioner — Applied** | Mid-level competence. Demonstrates applied deployment of framework in institutional contexts. | Applied deployment, institutional context |
| **Practitioner — Senior** | Senior competence. Demonstrates governance leadership and institutional design capability. | Governance leadership, institutional design |
| **Specialist** | Narrow deep competence in a specific instrument or system within the stack. | Deep specialization |
| **Fellowship** | Recognition of sustained contribution to 19 Integrated framework development. HAN-adjudicated, no fixed assessment model. | Sustained contribution, HAN adjudication |

---

## SECTION 4: ASSESSMENT MODEL

### Overview

All active designations use an Examination \+ Portfolio assessment model.

### 4.1 Examination

| Aspect | Description |
| :---- | :---- |
| **Purpose** | Tests framework comprehension — knowledge of governing framework principles, invariants, control nodes, and application logic |
| **Format** | Defined per designation in program curriculum (IP-CC asset) |
| **Passing Threshold** | Defined per designation in program curriculum |
| **AI Tool Use** | Permitted for study and preparation; not permitted during examination |
| **Result** | Pass / Fail with score record |
| **IMP Logging** | Examination result is logged in the Candidate Record |

### 4.2 Portfolio Submission

| Aspect | Description |
| :---- | :---- |
| **Purpose** | Tests applied judgment — demonstration of framework application in a real or simulated institutional context |
| **Format** | Structured submission defined per designation in program curriculum |
| **Content** | Candidate's applied work demonstrating framework deployment, governance design, or institutional analysis |
| **Candidate Attestation** | Every portfolio submission must include a signed Candidate Attestation |
| **Preliminary Review** | F-DR and F-OV agents under E-IN assignment conduct structural completeness check and framework alignment assessment. Preliminary review is advisory input only — not determination. |
| **Final Adjudication** | HAN only. Portfolio adjudication is a non-delegable HAN authority. |
| **Result** | Pass / Fail with adjudication notes |
| **IMP Logging** | Portfolio result is logged in the Candidate Record |

### Candidate Attestation

| Requirement | Description |
| :---- | :---- |
| **Signed Statement** | Candidate attests that the portfolio represents the candidate's own applied judgment |
| **AI Tool Disclosure** | Candidate discloses any AI tools used in preparation |
| **Effect of Disclosure** | AI tool disclosure does not disqualify a submission |
| **Undisclosed AI Generation** | Undisclosed AI generation producing a submission substantially indistinguishable from another candidate's submission is grounds for revocation proceeding |

### 4.3 Designation Award

| Step | Action | Responsible |
| :---- | :---- | :---- |
| 1 | Both examination and portfolio results are Pass | Assessment Administrator |
| 2 | HAN issues designation confirmation | HAN |
| 3 | Designation Instrument issued to candidate | 19 Institute |
| 4 | Candidate Record updated | IMP |
| 5 | Public Designation Register updated | 19 Institute |

### Designation Instrument

| Field | Description |
| :---- | :---- |
| **Candidate Name** | Full name of the designation holder |
| **Designation Name and Post-Nominal** | CA / CI / CGO / etc. |
| **Governing Framework Version** | IP-FD version bound at program launch |
| **Award Date** | Date of designation award |
| **Maintenance Requirements** | Periodic renewal cycle and event-triggered revalidation requirements |
| **HAN Confirmation** | HAN signature and date |

### Designation Award Rules

| Rule | Description |
| :---- | :---- |
| **HAN-Only** | Designation award confirmation is a non-delegable HAN authority. |
| **Individual Award** | Designations are awarded to individuals, not institutions. |
| **Unconditional Portability** | Designation portability is unconditional. |
| **IMP Logging** | Designation award is logged in Candidate Record and Public Designation Register. |

---

## SECTION 5: CANDIDATE CONTESTATION PROTOCOL

### Purpose

Candidates may contest examination results or portfolio adjudication findings through a defined due process protocol.

### Protocol Steps

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Contest submission | Candidate | Within 14 days of result notification |
| 2 | Contest specifies grounds for dispute with supporting evidence | Candidate | Within 14 days of result notification |
| 3 | Independent review: F-OV agent from non-Institute entity conducts review of examination marking or portfolio adjudication against curriculum standards | F-OV Agent (cross-review) | Within 14 days of contest submission |
| 4 | HAN makes final determination based on independent review finding | HAN | Within 7 days of independent review |
| 5 | Candidate receives the finding and HAN determination | 19 Institute | Within 3 days of HAN determination |
| 6 | Review is logged as an audit artifact under I3 of ICC-8 | IMP | Upon completion |

### Contestation Rules

| Rule | Description |
| :---- | :---- |
| **Due Process** | Candidates have the right to contest examination results or portfolio adjudication findings. |
| **Independent Review** | Review is conducted by an F-OV agent from a non-Institute entity (cross-review under AWOF v1.1 Section 12). |
| **HAN Final Determination** | HAN makes the final determination based on the independent review finding. |
| **IMP Logging** | Review is logged as an audit artifact under I3 of ICC-8. |
| **Finality** | HAN determination is final. |

---

## SECTION 6: PUBLIC DESIGNATION REGISTER

### Purpose

The Public Designation Register is the external legibility instrument of the certification function under I8 of ICC-8. It is a canonical list of all designation holders with current status.

### Status Classifications

| Status | Meaning |
| :---- | :---- |
| **Active** | Designation is current and in good standing |
| **Under Revalidation** | Designation holder is within a revalidation window or approved extension period |
| **Proceeding Suspended** | Revocation proceeding is active but suspended due to HAN unavailability |
| **Lapsed** | Periodic renewal not completed within required window |
| **Revoked** | Designation permanently withdrawn by HAN determination |

### Register Contents

| Field | Description |
| :---- | :---- |
| **Candidate Name** | Full name of designation holder |
| **Designation Post-Nominal** | CA / CI / CGO / etc. |
| **Award Date** | Date of designation award |
| **Current Status** | Active / Under Revalidation / Proceeding Suspended / Lapsed / Revoked |
| **Last Renewal or Revalidation Date** | Date of most recent renewal or revalidation |

### Confidentiality

| Rule | Description |
| :---- | :---- |
| **Public Information** | Public Designation Register contains: candidate name, designation post-nominal, award date, current status, last renewal/revalidation date. |
| **Confidential Information** | Public Designation Register does not contain: examination scores, portfolio content, contestation records, or other confidential information. |
| **Confidential Storage** | Confidential information is held in the Candidate Record under I6 restricted classification. |

### Verification

| Party | Verification Purpose |
| :---- | :---- |
| **Employers** | Verify designation status of employees or applicants |
| **DFIs** | Verify designation status of practitioners |
| **Regulatory Bodies** | Verify designation status for regulatory compliance |
| **Public** | Verify designation status of any holder |

### Misrepresentation

| Rule | Description |
| :---- | :---- |
| **Lapsed or Revoked Representation** | Misrepresentation of a Lapsed or Revoked designation as Active is a violation of 19 Institute designation holder conduct standards. |
| **Enforcement** | Misrepresentation is referred to the HoldCo contestation interface under CEN-2 of ICC-8. |
| **Revocation Ground** | Misrepresentation is grounds for revocation proceeding. |

---

## SECTION 7: DESIGNATION MAINTENANCE

### 7.1 Periodic Renewal

| Aspect | Description |
| :---- | :---- |
| **Cycle** | 2 years from award date, then 2 years from each prior renewal date |
| **Renewal Requirement** | Completion of a defined continuing education requirement specified in program curriculum, or demonstration of active framework deployment in professional practice |
| **IMP Logging** | Renewal is logged in Candidate Record and Public Designation Register updated |
| **Failure to Complete** | Failure to complete renewal within the 2-year window: designation status changes to Lapsed |

### Lapse and Reinstatement

| Aspect | Description |
| :---- | :---- |
| **Lapse** | Designation status changes to Lapsed upon failure to complete renewal within the 2-year window |
| **Reinstatement (within 12 months)** | Lapsed designations may be reinstated within 12 months of lapse date by completing renewal requirements plus a reinstatement assessment defined in program curriculum |
| **Reinstatement (beyond 12 months)** | Reinstatement beyond 12 months requires full reassessment under current program curriculum |
| **IMP Logging** | Reinstatement is logged in Candidate Record and Public Designation Register updated |

### 7.2 Event-Triggered Revalidation

| Aspect | Description |
| :---- | :---- |
| **Trigger** | Material change to the governing framework version bound to the designation curriculum (Curriculum Review Protocol under ILTP v2.0 Section 8.2) |
| **Trigger Determination** | HAN determination under Curriculum Review Protocol that the framework version change is material and requires revalidation |
| **Revalidation Window** | Defined per trigger event, minimum 90 days from notification |
| **Revalidation Requirement** | Defined per trigger event in Curriculum Review Protocol finding — may be targeted assessment, portfolio supplement, or full reassessment depending on materiality of change |
| **Designation Status** | Designation status during revalidation window: Under Revalidation |

### Revalidation Extension Protocol

| Aspect | Description |
| :---- | :---- |
| **Extension Request** | Candidates may request extension with documented cause |
| **Extension Authorization** | Extension is HAN-authorized |
| **Maximum Extension** | 90 additional days |
| **Designation Status** | Designation status remains Under Revalidation during extension |
| **Suspension** | Designation is not suspended during extension period |

### Revalidation Failure

| Aspect | Description |
| :---- | :---- |
| **Failure to Complete** | Failure to complete revalidation within window plus any authorized extension: designation status changes to Lapsed under standard Lapse provisions |
| **IMP Logging** | Revalidation failure is logged in Candidate Record and Public Designation Register updated |

---

## SECTION 8: REVOCATION

### Purpose

Designation revocation is the permanent withdrawal of a designation by HAN determination.

### Revocation Grounds

| \# | Ground | Description |
| :---- | :---- | :---- |
| **RG-1** | **Candidate Attestation Violation** | Undisclosed AI generation producing submission substantially indistinguishable from another candidate's submission |
| **RG-2** | **Material Misrepresentation** | Material misrepresentation in portfolio submission or examination |
| **RG-3** | **Code of Conduct Violation** | Breach of 19 Institute designation holder conduct standards (defined in program curriculum) |
| **RG-4** | **Status Misrepresentation** | Material misrepresentation of designation status to external counterparties |
| **RG-5** | **Constitutional Integrity** | HAN determination that continued designation holding is inconsistent with the integrity of the certification function |
| **RG-6** | **I9 Catastrophic Risk Violation** | Designation holder's actions violate I9 Catastrophic Risk Invariant (v2.0) |

### Revocation Proceeding

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Revocation proceeding initiated by HAN or by complaint received through HoldCo contestation interface | HAN / Complainant | Upon detection |
| 2 | Candidate notified of proceeding initiation and grounds | 19 Institute | Within 7 days |
| 3 | Candidate has 21 days to submit a response | Candidate | Within 21 days |
| 4 | HAN reviews grounds and candidate response | HAN | Within 30 days of response |
| 5 | HAN issues determination: revocation confirmed or proceeding closed | HAN | Within 30 days of response |
| 6 | Revocation is logged in Candidate Record and Public Designation Register updated to Revoked status | IMP | Upon determination |

### HAN Unavailability During Revocation Proceeding

| Rule | Description |
| :---- | :---- |
| **Proceeding Suspended** | Proceeding is suspended. |
| **Designation Status** | Designation status is updated to Proceeding Suspended in the Public Designation Register. |
| **Resumption** | Proceeding resumes upon HAN restoration. |

### Revocation Consequences

| Consequence | Description |
| :---- | :---- |
| **Permanent** | Revocation is permanent. |
| **Fresh Assessment** | Revoked designation holders may apply for fresh assessment under current program curriculum after a minimum 2-year period from revocation date, at HAN discretion. |
| **Public Designation Register** | Status remains Revoked permanently. |

---

## SECTION 9: FELLOWSHIP DESIGNATION

### Purpose

The 19 Integrated Fellow (FI19) designation is a distinct class governed by special rules.

### Governance

| Aspect | Description |
| :---- | :---- |
| **Assessment Model** | No fixed assessment model — HAN-adjudicated based on demonstrated contribution to 19 Integrated framework development, institutional adoption, or thought leadership |
| **Periodic Renewal** | No periodic renewal requirement — Fellowship is permanent once awarded unless revoked |
| **Event-Triggered Revalidation** | Subject to event-triggered revalidation only if HAN determines that a material framework change affects the basis of the original award |
| **Nomination** | Fellowship award requires HAN nomination and confirmation — no candidate application process |
| **Public Designation Register** | Fellowship is listed in the Public Designation Register as a distinct designation class |

### Revocation

| Aspect | Description |
| :---- | :---- |
| **Grounds** | Same as Section 8 (RG-1 through RG-6) |
| **Proceeding** | Same as Section 8 |
| **Consequences** | Same as Section 8 |

---

## SECTION 10: NON-DELEGABLE CERTIFICATION AUTHORITIES

The following certification actions are non-delegable HAN authorities:

| \# | Authority | Description |
| :---- | :---- | :---- |
| 1 | **Portfolio Adjudication** | Final determination of portfolio submission |
| 2 | **Designation Award Confirmation** | Confirmation of designation award |
| 3 | **Revalidation Extension Protocol Authorization** | Authorization of revalidation extension |
| 4 | **Candidate Contestation Protocol Final Determination** | Final determination of candidate contestation |
| 5 | **Revocation Proceeding Initiation** | Initiation of revocation proceeding |
| 6 | **Revocation Proceeding Determination** | Final determination of revocation proceeding |
| 7 | **Fellowship Nomination and Award** | Nomination and award of Fellowship |
| 8 | **New Designation Registration** | Registration of new designation (Active or Placeholder) |
| 9 | **Curriculum Review Protocol Revalidation Determination** | Determination of revalidation requirement |
| 10 | **Public Designation Register Status Changes** | Any certification action affecting Public Designation Register status |

### Non-Delegable Rules

| Rule | Description |
| :---- | :---- |
| **HAN-Only** | All non-delegable certification authorities are reserved exclusively for HAN. |
| **Suspension on HAN Unavailability** | All are suspended upon HAN unavailability and resume upon HAN restoration. |
| **IMP Logging** | All actions are logged in IMP as DRO. |

---

## SECTION 11: ACCOUNTABILITY CHAIN FOR CERTIFICATION ACTIONS

HAN (Terrylan\_Manalansan)  
  │  
  ├──→ Designation Registration  
  │       │  
  │       └──→ Designation Register \+ IP Register (ILTP)  
  │  
  ├──→ Program Delivery  
  │       │  
  │       └──→ Assigned Agents (AWOF Agent IDs under E-IN)  
  │               │  
  │               └──→ Candidate Assessment  
  │                       │  
  │                       ├──→ Examination Result  
  │                       └──→ Portfolio Preliminary Review (advisory only)  
  │  
  ├──→ HAN Adjudication  
  │       │  
  │       └──→ Designation Award / Non-Award Determination  
  │  
  └──→ Audit (Candidate Record \+ Public Designation Register \+ I3 Audit Chain)  
          │  
          └──→ Accountability Terminus: HAN (Terrylan\_Manalansan)

---

## SECTION 12: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship to CGF |
| :---- | :---- |
| **ICC-8** | Constitutional parent — CGF operates under ICC-8 invariants |
| **ILTP** | IP instrument — IP-CC assets, Curriculum Version Binding, placeholder registration |
| **AWOF** | Workforce instrument — agent roles in assessment and administration |
| **HAN/HOF** | Human authority — non-delegable certification authorities reserved for HAN |
| **IMP** | Certification records logged as GAO, DRO, OEO, XOO |
| **ERDP** | Designation activity feeds ERDP reporting |
| **CEF** | Engagement instrument — no direct dependency; certification and advisory are distinct functions |
| **DEP** | CGF amendments require DEP process |

---

## SECTION 13: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Designation Register Completeness** | All active and placeholder designations are registered with all required fields. |
| **Assessment Model** | Examination \+ Portfolio model is defined for all active designations. |
| **Maintenance Model** | Periodic renewal (2-year) \+ Event-triggered revalidation are defined. |
| **Public Designation Register** | Public Designation Register is maintained with current status classifications. |
| **Candidate Contestation Protocol** | Due process protocol is defined with timelines and independent review. |
| **Revocation Grounds** | All revocation grounds (RG-1 through RG-6) are defined with due process. |
| **Non-Delegable Authorities** | Non-delegable certification authorities are reserved for HAN. |
| **Fellowship Designation** | Fellowship designation is defined as a distinct class with special governance. |
| **I9 Application** | I9 Catastrophic Risk Violation is a revocation ground (v2.0). |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| CGF v1.0 | Initial specification — Designation Register, Examination \+ Portfolio, Periodic Renewal \+ Event-Triggered Revalidation, Public Designation Register |
| CGF v2.0 | Complete rebuild — reconciliation with ICC-8, ILTP, AWOF, HAN/HOF, IMP, ERDP, and DEP; expanded Designation Register (Active \+ Placeholder); Candidate Contestation Protocol; Public Designation Register; Revocation grounds expanded to include I9 (RG-6); Fellowship designation; Non-Delegable Certification Authorities; CFL-V validation rules |

---

## The One-Sentence Summary

> *"CGF v2.0 governs the full certification lifecycle — Designation Register (Active \+ Placeholder), Examination \+ Portfolio assessment model, Periodic Renewal (2-year) \+ Event-Triggered Revalidation, Public Designation Register, Candidate Contestation Protocol, Revocation Proceedings (RG-1 through RG-6, including I9), and Fellowship designation — with non-delegable certification authorities reserved for HAN, constitutional validity derived from ICC-8, and external legibility through the Public Designation Register under I8 of ICC-8."*
