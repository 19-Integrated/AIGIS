# Public Designation Register v2.0

**Status:** Built — v2.0 (Reconciliation with CGF, ICC-8, ERDP, IMP, and HAN/HOF)  
**Type:** Certification Governance Instrument  
**Parent Stack:** CGF (Certification Governance Framework)  
**Version:** 2.0 — Supersedes Public Designation Register v1.0

---

## PREAMBLE

The Public Designation Register is the external legibility instrument of the certification function under I8 of ICC-8. It answers: *Who holds a 19 Institute designation, what is their current status, and how can external parties verify that status?*

The Public Designation Register is a canonical list of all designation holders with their current status. It provides external legibility of certification status—satisfying I8 External Legibility requirement by making the certification function auditable, verifiable, and contestable from outside the institution.

**The core insight:** A certification that cannot be verified externally is not a certification—it is a claim. The Public Designation Register transforms certification from an institutional assertion into an externally verifiable fact, enabling employers, regulators, DFIs, and the public to trust the designation.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

The Public Designation Register ensures that:

1. **Designation status is externally verifiable** — Employers, regulators, DFIs, and the public can verify status  
2. **Status is current** — The Register reflects real-time status changes (Active, Under Revalidation, Lapsed, Revoked, Proceeding Suspended)  
3. **Confidentiality is maintained** — The Register contains only public information; confidential records remain restricted  
4. **I8 External Legibility is satisfied** — The certification function is externally legible, auditable, and contestable  
5. **Misrepresentation is detectable** — Lapsed or Revoked designations are visible to prevent misrepresentation

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Designation holder names and post-nominals | Examination scores |
| Current status classifications | Portfolio content |
| Award and renewal dates | Contestation records |
| Verification by external parties | Candidate contact information |
| External legibility under I8 | Confidential candidate records |

### Governing Relationships

| Instrument | Relationship to Public Designation Register |
| :---- | :---- |
| **CGF** | Parent instrument — Public Designation Register is a component of CGF |
| **ICC-8** | Constitutional parent — I8 External Legibility requirement |
| **ERDP** | Disclosure and reporting — Register status feeds ERDP |
| **IMP** | Certification records logged as GAO, DRO, OEO |
| **HAN/HOF** | Status changes require HAN authorization |

---

## SECTION 2: REGISTER STRUCTURE

### 2.1 Register Schema

| \# | Field | Type | Description | Publicly Visible |
| :---- | :---- | :---- | :---- | :---- |
| 1 | **Registration ID** | String | Unique identifier. Format: `PDR-[SEQ]` | No |
| 2 | **Candidate Name** | String | Full name of the designation holder | Yes |
| 3 | **Designation Post-Nominal** | String | CA / CI / CGO / MCP / MCA / CCO / FI19 | Yes |
| 4 | **Designation Class** | Enum | Practitioner — Foundation / Practitioner — Applied / Practitioner — Senior / Specialist / Fellowship | Yes |
| 5 | **Award Date** | ISO 8601 | Date of designation award | Yes |
| 6 | **Current Status** | Enum | Active / Under Revalidation / Proceeding Suspended / Lapsed / Revoked | Yes |
| 7 | **Last Renewal or Revalidation Date** | ISO 8601 | Date of most recent renewal or revalidation | Yes |
| 8 | **Next Renewal Due Date** | ISO 8601 | Date by which next renewal is due | Yes |
| 9 | **Governing Framework Version** | String | IP-FD version bound at program launch | Yes |
| 10 | **Status Change History** | Array | Log of all status changes with timestamps | No (audit only) |
| 11 | **HAN Acknowledgment** | Object | HAN signature and date for each status change | No (audit only) |
| 12 | **Verification Count** | Integer | Number of external verification requests | No (internal metric) |

### 2.2 Status Classifications

| Status | Meaning | Public Display | Transition To |
| :---- | :---- | :---- | :---- |
| **Active** | Designation is current and in good standing | ✅ Active | Under Revalidation, Lapsed, Revoked |
| **Under Revalidation** | Designation holder is within a revalidation window or approved extension period | ⚠️ Under Revalidation | Active, Lapsed, Revoked |
| **Proceeding Suspended** | Revocation proceeding is active but suspended due to HAN unavailability | ⏸️ Proceeding Suspended | Active, Revoked |
| **Lapsed** | Periodic renewal not completed within required window | ❌ Lapsed | Active (reinstatement within 12 months), Revoked |
| **Revoked** | Designation permanently withdrawn by HAN determination | ❌ Revoked | — (terminal state) |

### 2.3 Status Display Rules

| Rule | Description |
| :---- | :---- |
| **Active** | Displayed as "Active" with green indicator |
| **Under Revalidation** | Displayed as "Under Revalidation" with yellow indicator; shows revalidation window end date if applicable |
| **Proceeding Suspended** | Displayed as "Proceeding Suspended" with orange indicator; shows suspension reason (HAN unavailable) |
| **Lapsed** | Displayed as "Lapsed" with red indicator; shows lapse date |
| **Revoked** | Displayed as "Revoked" with red indicator; shows revocation date; permanent |

---

## SECTION 3: REGISTER MAINTENANCE

### 3.1 Status Update Triggers

| Trigger | New Status | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| Designation awarded | Active | 19 Institute | Upon HAN confirmation |
| Renewal completed | Active | 19 Institute | Upon renewal confirmation |
| Renewal not completed within window | Lapsed | 19 Institute | Immediately upon window expiration |
| Revalidation triggered | Under Revalidation | 19 Institute | Upon trigger determination |
| Revalidation completed | Active | 19 Institute | Upon revalidation confirmation |
| Revalidation not completed within window | Lapsed | 19 Institute | Immediately upon window expiration |
| Revalidation extension granted | Under Revalidation | 19 Institute | Upon HAN authorization |
| Revocation proceeding initiated | Active (with flag) | 19 Institute | Upon HAN initiation |
| Revocation confirmed | Revoked | 19 Institute | Upon HAN determination |
| Proceeding suspended (HAN unavailable) | Proceeding Suspended | 19 Institute | Upon HAN unavailability |
| Proceeding resumed | Active (with flag) | 19 Institute | Upon HAN restoration |
| Lapsed reinstatement within 12 months | Active | 19 Institute | Upon reinstatement completion |
| Lapsed reinstatement beyond 12 months | Requires full reassessment | 19 Institute | Upon program re-entry |

### 3.2 Status Update Authorization

| Action | Authorization Required | Authorization Type |
| :---- | :---- | :---- |
| Active → Under Revalidation | HAN | Non-delegable |
| Under Revalidation → Active | HAN | Non-delegable |
| Under Revalidation → Lapsed | Automatic | System |
| Active → Lapsed | Automatic | System |
| Lapsed → Active (reinstatement) | HAN | Non-delegable |
| Any status → Revoked | HAN | Non-delegable |
| Active → Proceeding Suspended | Automatic | System (HAN unavailability) |
| Proceeding Suspended → Active | HAN | Non-delegable |

### 3.3 Status Change Rules

| Rule | Description |
| :---- | :---- |
| **Immediate Update** | Status changes are reflected in the Register immediately upon trigger. |
| **HAN Authorization** | Status changes requiring HAN authorization are held pending HAN confirmation. |
| **Audit Trail** | All status changes are logged with timestamp, authorizer, and basis. |
| **No Retroactive Changes** | Status changes are not retroactive. The Register reflects current status at all times. |
| **Public Notification** | Status changes affecting public display are reflected immediately. |

---

## SECTION 4: EXTERNAL VERIFICATION

### 4.1 Verification Methods

| Method | Description | Access |
| :---- | :---- | :---- |
| **Public Web Interface** | Web-based lookup by name and/or post-nominal | Public |
| **API Verification** | Programmatic verification via authenticated API | Registered users |
| **Manual Verification Request** | Written request for verification | Employers, DFIs, Regulators |
| **QR Code Verification** | QR code on designation certificate | Any |

### 4.2 Verification Response

| Field | Included in Response |
| :---- | :---- |
| **Candidate Name** | Yes |
| **Designation Post-Nominal** | Yes |
| **Designation Class** | Yes |
| **Current Status** | Yes |
| **Award Date** | Yes |
| **Last Renewal Date** | Yes |
| **Governing Framework Version** | Yes |
| **Verification Timestamp** | Yes |

### 4.3 Verification Rules

| Rule | Description |
| :---- | :---- |
| **Public Access** | The Register is publicly accessible for verification purposes. |
| **Privacy Protection** | No confidential information (examination scores, portfolio content, contestation records) is disclosed. |
| **Verification Logging** | All verification requests are logged for audit purposes. |
| **Rate Limiting** | Rate limiting is applied to prevent automated scraping. |
| **Fraud Detection** | Anomalous verification patterns are flagged for review. |

### 4.4 API Verification

| Endpoint | Method | Purpose |
| :---- | :---- | :---- |
| `/api/v1/verify` | POST | Verify a single designation holder |
| `/api/v1/verify/batch` | POST | Batch verify multiple designation holders |
| `/api/v1/status` | GET | Get current status of a designation holder |
| `/api/v1/designations` | GET | List all active designations (pagination) |

---

## SECTION 5: MISREPRESENTATION DETECTION

### 5.1 Misrepresentation Types

| Type | Description | Detection Method |
| :---- | :---- | :---- |
| **Status Misrepresentation** | Claiming Active status when Lapsed or Revoked | Register verification |
| **Designation Misrepresentation** | Claiming a designation not held | Register verification |
| **Expired Designation** | Claiming a designation after revocation | Register verification |
| **Unauthorized Post-Nominal Use** | Using post-nominal without valid designation | Register verification |
| **Counterfeit Certificate** | Falsifying designation certificate | Certificate verification |

### 5.2 Misrepresentation Response

| Response | Description | Responsible |
| :---- | :---- | :---- |
| **Verification Failure** | Verification request returns "Not Verified" | Public Designation Register |
| **Investigation** | Misrepresentation reported to HAN | Any |
| **Revocation** | Misrepresentation is grounds for revocation proceeding | HAN |
| **Public Notification** | Notification of revocation due to misrepresentation | 19 Institute |
| **Legal Action** | Legal action for fraudulent misrepresentation | 19 Integrated Legal |

---

## SECTION 6: REGISTER INTEGRITY

### 6.1 Integrity Requirements

| Requirement | Description |
| :---- | :---- |
| **Immutability** | Historical records are immutable; no deletion |
| **Audit Trail** | All changes are logged with timestamp, authorizer, and basis |
| **Verification** | Register is verified against Candidate Records periodically |
| **Backup** | Register is backed up with disaster recovery |
| **Security** | Access controls prevent unauthorized modification |

### 6.2 Audit Trail

| Field | Description |
| :---- | :---- |
| **Change ID** | Unique identifier for the change |
| **Candidate ID** | Affected candidate |
| **Previous Status** | Status before change |
| **New Status** | Status after change |
| **Change Timestamp** | When the change was made |
| **Authorizer** | HAN or system |
| **Authorization Basis** | Reason for the change |
| **Reference** | Reference to CGF proceeding or trigger |

### 6.3 Periodic Verification

| Activity | Frequency | Responsible |
| :---- | :---- | :---- |
| **Register vs. Candidate Records Reconciliation** | Quarterly | 19 Institute |
| **HAN Audit** | Annually | HAN |
| **External Audit** | Annually | Independent Auditor |
| **I8 Compliance Review** | Annually | 19 Integrated Governance |

---

## SECTION 7: REGISTER AND ICC-8

### 7.1 I8 External Legibility

The Public Designation Register satisfies I8 External Legibility by providing:

| Requirement | How It Is Satisfied |
| :---- | :---- |
| **CEN-1: Interpretability** | Register entries are described in plain language, intelligible to external parties |
| **CEN-2: Accessibility** | Public web interface and API provide defined pathways for verification |
| **CEN-3: Traceability** | Register entries connect to audit chain under I3 |
| **CEN-4: Confidentiality** | Confidential information is not disclosed; restricted information handled by independent review |
| **CEN-5: Independence** | Register is administered by 19 Institute, not the originating authority (HAN) |
| **CEN-6: Redress and Remediation** | Misrepresentation is a revocation ground with defined corrective pathway |

### 7.2 Register and I6 Transparency Gradient

| Disclosure Tier | Content | Publicly Visible |
| :---- | :---- | :---- |
| **T-PB (Public)** | Candidate name, designation post-nominal, current status, award date, last renewal date, governing framework version | Yes |
| **T-SH (Stakeholder)** | Verification history, renewal history | No (available to designation holder) |
| **T-RG (Regulator)** | Full Candidate Record upon lawful request | No |
| **T-DS (DFI/Sovereign)** | Full Candidate Record upon lawful request | No |

---

## SECTION 8: REGISTER AND ERDP

| ERDP Reporting | Content | Frequency |
| :---- | :---- | :---- |
| **AIR Section 3: Certification Activity** | Designation Register status, active/placeholder programs, holder counts by designation class | Annual |
| **Event-Triggered Reporting** | Designation revocation (aggregate — no individual identification) | Next QOU cycle |
| **New Designation Launch** | Active program launch | Within 14 days |

### 8.1 Annual Institutional Report (AIR)

| Field | Source | Description |
| :---- | :---- | :---- |
| **Active Designations** | Public Designation Register | Total active designation holders by class |
| **Placeholder Programs** | Designation Register | Placeholder programs with target launch dates |
| **Revalidation Events** | Public Designation Register | Count of revalidation events during reporting period |
| **Revocation Count** | Public Designation Register | Total revocations during reporting period (aggregate) |

---

## SECTION 9: REGISTER TEMPLATE

### 9.1 Entry Template

Registration ID: PDR-000001  
Candidate Name: "John Q. Practitioner"  
Designation Post-Nominal: "CGO"  
Designation Class: "Practitioner — Senior"  
Award Date: "2026-01-15T00:00:00Z"  
Current Status: "Active"  
Last Renewal or Revalidation Date: "2026-07-15T00:00:00Z"  
Next Renewal Due Date: "2028-01-15T00:00:00Z"  
Governing Framework Version: "AICA-5 v2.0"  
Status Change History:  
  \- timestamp: "2026-01-15T00:00:00Z"  
    previous\_status: null  
    new\_status: "Active"  
    authorizer: "HAN-Terrylan\_Manalansan"  
    basis: "Designation awarded"  
  \- timestamp: "2026-07-15T00:00:00Z"  
    previous\_status: "Active"  
    new\_status: "Under Revalidation"  
    authorizer: "System"  
    basis: "Event-triggered revalidation triggered"  
  \- timestamp: "2026-07-15T12:00:00Z"  
    previous\_status: "Under Revalidation"  
    new\_status: "Active"  
    authorizer: "HAN-Terrylan\_Manalansan"  
    basis: "Revalidation completed"  
HAN Acknowledgment:  
  HAN: "Terrylan\_Manalansan"  
  Date: "2026-01-15T00:00:00Z"  
Verification Count: 15

### 9.2 Public Display Template

Candidate: John Q. Practitioner  
Designation: CGO — AICA-5 Certified Governance Officer  
Class: Practitioner — Senior  
Status: ✅ Active  
Award Date: 2026-01-15  
Last Renewal: 2026-07-15  
Governing Framework: AICA-5 v2.0  
Verification Timestamp: 2026-08-31T10:00:00Z

---

## SECTION 10: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship to Public Designation Register |
| :---- | :---- |
| **CGF** | Parent instrument — Public Designation Register is a component of CGF |
| **ICC-8** | Constitutional parent — I8 External Legibility requirement |
| **ERDP** | Disclosure and reporting — Register status feeds ERDP |
| **IMP** | Certification records logged as GAO, DRO, OEO |
| **HAN/HOF** | Status changes require HAN authorization |
| **ILTP** | IP-CC assets referenced in Register entries |

---

## SECTION 11: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Register Completeness** | All active and placeholder designations are represented in the Public Designation Register. |
| **Status Classification** | All five status classifications (Active, Under Revalidation, Proceeding Suspended, Lapsed, Revoked) are defined and displayed. |
| **External Verification** | Public web interface and API provide defined pathways for verification. |
| **Confidentiality** | No confidential information (examination scores, portfolio content, contestation records) is publicly visible. |
| **Audit Trail** | All status changes are logged with timestamp, authorizer, and basis. |
| **I8 Compliance** | The Register satisfies CEN-1 through CEN-6 requirements. |
| **I6 Transparency** | Information is classified into defined disclosure tiers. |
| **Misrepresentation Detection** | Misrepresentation is a revocation ground with defined corrective pathway. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Public Designation Register v1.0 | Initial specification — Register structure, status classifications, external verification |
| Public Designation Register v2.0 | Complete rebuild — reconciliation with CGF, ICC-8, ERDP, IMP, and HAN/HOF; expanded Register schema (12 fields); status display rules; external verification methods (API, QR code); misrepresentation detection; integrity requirements; I8 and I6 mapping; ERDP integration; template; CFL-V validation rules |

---

## The One-Sentence Summary

> *"The Public Designation Register v2.0 is the external legibility instrument of the certification function under I8 of ICC-8 — a canonical list of all designation holders with 12 fields including candidate name, designation post-nominal, current status (Active/Under Revalidation/Proceeding Suspended/Lapsed/Revoked), award and renewal dates, and governing framework version — providing public verification via web interface and API, satisfying CEN-1 through CEN-6, maintaining confidentiality under I6, and enabling misrepresentation detection and redress under CGF governance."*
