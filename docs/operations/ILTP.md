# ILTP v2.0 — IP Licensing & Transfer Protocol

**Status:** Built — v2.0 (Reconciliation with ICC-8, IMP, CEF, AWOF, HAN, CGF, ERDP, and DEP)  
**Type:** IP Governance Instrument  
**Parent Stack:** 19 Integrated Operational Infrastructure  
**Version:** 2.0 — Supersedes ILTP v1.0

---

## PREAMBLE

The IP Licensing & Transfer Protocol (ILTP) governs the classification, licensing, transfer, version management, and inter-entity deployment of all 19 Integrated intellectual property. It answers: *How is IP classified, licensed, transferred, and version-managed across all 19 Integrated entities?*

ILTP is the IP governance instrument of 19 Integrated HoldCo, governing all IP classes across 19 Consultin', 19 Publishin', and 19 Institute. It governs licensing, inter-entity deployment, derivative classification, transfer, and version management. It ensures that IP is protected, traceable, and properly attributed across all entities and engagements.

**The core insight:** IP is institutional capital. Without governance, IP leaks, drifts, and loses value. ILTP ensures that every IP asset is classified, licensed, transferred, and versioned under constitutional governance, preserving institutional value and enabling sovereign/DFI engagement.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

ILTP ensures that:

1. **IP is classified** — Four IP classes define ownership and deployment authority  
2. **IP is registered** — IP Register is the authoritative record of all IP  
3. **IP is licensed** — Four licensing models define how IP may be used  
4. **IP is transferred** — Standard and Sovereign Transfer Protocols govern transfer  
5. **IP is versioned** — Version management ensures traceability  
6. **Inter-entity IP is governed** — Standing grants and Specific Deployment Instruments govern inter-entity IP flows

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| IP classification (4 classes) | Pricing of IP licenses (Pricing Architecture) |
| IP Register | Publication decisions (Publishin' Charter) |
| Licensing models (4 models) | Client engagement scoping (CEF) |
| Inter-entity governance | Business strategy or marketing |
| Sovereign Transfer Protocol | Operational efficiency |
| Version management | Technical delivery execution |

### Governing Relationships

| Instrument | Relationship to ILTP |
| :---- | :---- |
| **ICC-8** | Constitutional ceiling — ILTP may not permit what ICC-8 prohibits |
| **IMP** | IP Register entries logged as GAO; derivatives logged as ECO-linked objects |
| **CEF** | Engagement instruments reference ILTP IP Assignment Clause |
| **AWOF** | Agent IP actions governed by standing grant scope |
| **HAN** | IP transfer authorization is a non-delegable HAN authority |
| **CGF** | Certification curricula are IP-CC assets under ILTP |
| **ERDP** | IP Register status may be disclosed under ERDP |
| **DEP** | ILTP amendments require DEP process |

---

## SECTION 2: IP CLASSES

| Class | Code | Description | Primary Entity | Ownership |
| :---- | :---- | :---- | :---- | :---- |
| **Frameworks and Doctrine** | IP-FD | Constitutive frameworks, doctrine instruments, and governance systems (MICOS-25, AICA-5, ICC-8, COF, etc.) | HoldCo | HoldCo |
| **Published Instruments** | IP-PI | White papers, explainers, research instruments, public-facing doctrine (BAIGO-7, GAA Scrolls, etc.) | Publishin' | HoldCo (distribution rights to Publishin') |
| **Certification Curricula** | IP-CC | Certification program content, assessment instruments, designation criteria (AICA-5 CA/CI/CGO, etc.) | Institute | HoldCo (delivery rights to Institute) |
| **Engagement Derivatives** | IP-ED | Framework derivatives, diagnostic instruments, governance outputs produced during client engagements | HoldCo (default) | HoldCo (deployment rights to Consultin') |

### Ownership Rule

| Rule | Description |
| :---- | :---- |
| **Default Vesting** | All IP classes vest in 19 Integrated HoldCo by default. |
| **Entity Assignment** | Entity-level primary assignment denotes deployment authority, not ownership. |
| **Transfer** | Ownership transfer requires a specific instrument under Section 6\. |
| **IP-ED Vesting** | IP-ED derivatives vest in HoldCo by default per CEF IP Assignment Clause. |

---

## SECTION 3: IP REGISTER

### Purpose

The IP Register is the authoritative record of all intellectual property under ILTP governance.

### Entry Requirements

| \# | Field | Description |
| :---- | :---- | :---- |
| 1 | **Asset Name and Version** | Name and current version of the IP asset |
| 2 | **IP Class** | IP-FD / IP-PI / IP-CC / IP-ED |
| 3 | **Creation Date** | Creation Date Registry entry (point of creation, not point of dispute) |
| 4 | **Authorship Attribution** | Auctor designation (Terrylan Manalansan / 19 Integrated) |
| 5 | **Parent Framework References** | References to parent frameworks |
| 6 | **Boundary Definition** | If incorporates elements of another registered framework, specifies native vs. incorporated elements |
| 7 | **Current Licensing Status** | Commercial / Open-Source / Sovereign / Restricted |
| 8 | **Dual-Status Classification** | If applicable (doctrine layer open-source; application layer commercial) |
| 9 | **Active License Instruments** | References to active license instruments |
| 10 | **Version History** | Version log with dates and changes |
| 11 | **HAN Acknowledgment Date** | HAN signature and date |
| 12 | **Supply Chain Reference** | Reference to supply chain provenance (v2.0) |
| 13 | **Model Provenance Record** | Reference to model provenance if AI-generated (v2.0) |
| 14 | **MCP Server Reference** | Reference to MCP server used in creation (v2.0) |

### Creation Date Registry

| Rule | Description |
| :---- | :---- |
| **Point of Creation** | All IP assets — including engagement derivatives under CEF — are logged at point of creation, not point of dispute. |
| **CEF Integration** | CEF Engagement Records feed directly into the IP Register for IP-ED entries. |
| **Primary Evidence** | Creation Date Registry entries are primary evidence of origination. |

### Boundary Definition

| Rule | Description |
| :---- | :---- |
| **Parent Framework References** | Every IP-FD asset that incorporates elements of another registered framework must carry a Boundary Definition. |
| **Native vs. Incorporated** | Boundary Definition specifies native elements versus elements incorporated by reference. |
| **Licensing** | Licensing a derivative framework does not confer rights to parent frameworks unless explicitly stated in the license instrument. |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **GAO** | `artifact_type: "policy_instrument"` | IP Register entry stored as GAO |
| **DRO** | `decision_type: "framework_selection"` | IP Register acknowledgment recorded |

---

## SECTION 4: LICENSING MODELS

| Model | Code | Description | Sublicensing | Ownership Transfer |
| :---- | :---- | :---- | :---- | :---- |
| **Commercial License** | LM-1 | Grants a defined counterparty the right to use a specified IP asset for defined commercial purposes within a defined scope and term | Not by default; requires explicit HAN authorization | No |
| **Open-Source License** | LM-2 | Grants public access to a specified IP asset under defined attribution and use conditions | Yes (per open-source terms) | No |
| **Sovereign/DFI License** | LM-3 | Distinct license class for engagements with sovereign bodies, DFIs, and regulatory counterparties where standard commercial terms are structurally incompatible | Per Sovereign Transfer terms | Conditional (Sovereign Transfer Protocol) |
| **Internal Use License** | LM-4 | Governs IP flows between 19 Integrated entities. Structured as a standing grant with defined scope. | Per standing grant | No |

### Licensing Rules

| Rule | Description |
| :---- | :---- |
| **Commercial License** | Sublicensing requires explicit HAN authorization in the license instrument. |
| **Open-Source License** | Attribution Requirements are mandatory in all open-source instruments. Violation of attribution terms is referred to the HoldCo contestation interface under CEN-2. |
| **Sovereign/DFI License** | All Sovereign/DFI license terms must be scoped before mandate close — not negotiated post-delivery. |
| **Internal Use License** | Scope defined by standing grants; Specific Deployment Instruments required for out-of-scope use. |

---

## SECTION 5: INTER-ENTITY IP GOVERNANCE

### 5.1 Standing Grants

The following standing grants are issued by HoldCo to each entity at the time of charter compilation and remain in force unless amended by HAN authorization:

| Entity | Standing Grant Scope | Exclusions |
| :---- | :---- | :---- |
| **19 Consultin'** | Commercial deployment of all IP-FD assets within confirmed engagement scope under CEF. Deployment of IP-PI assets cleared for commercial use by Publishin'. | Does not include sublicensing, sovereign transfer, or open-source publication. |
| **19 Publishin'** | Publication and distribution of IP-PI assets under confirmed publication scope. Drafting and distribution of IP-FD assets under confirmed publication clearance. | Does not include commercial licensing or certification use. |
| **19 Institute** | Curriculum development and certification delivery using IP-FD and IP-CC assets within confirmed program scope. | Does not include commercial deployment or publication. |

### 5.2 Specific Deployment Instruments

Required for any inter-entity IP use outside standing grant scope:

| Use Case | Description | Authorization |
| :---- | :---- | :---- |
| Sublicensing of any IP asset by any entity | Sub-licensing to third parties | HAN authorization |
| Cross-entity deployment of IP-ED engagement derivatives | Consultin' derivatives used by Institute or Publishin' | HAN authorization |
| Institute use of IP-ED assets for curriculum development | Engagement derivatives in certification programs | HAN authorization |
| Publishin' publication of IP assets under active Consultin' commercial deployment | Publication Clearance Rule | HAN authorization \+ HoldCo alignment |
| Any use not explicitly covered by the standing grant scope | Out-of-scope use | HAN authorization |

### 5.3 Publication Clearance Rule

| Rule | Description |
| :---- | :---- |
| **IP Status Check** | Any IP-FD or IP-ED asset scheduled for open-source publication under LM-2 must clear a HoldCo IP status check before release. |
| **Dual-Status Classification** | If the asset is under active commercial deployment by Consultin', publication terms must be aligned before release — specifically, a Dual-Status Classification must be established defining the doctrine/application boundary. |
| **HoldCo Authorization** | Publication clearance requires HoldCo authorization. |

### 5.4 Standing Grant Scope Creep

| Rule | Description |
| :---- | :---- |
| **Scope Drift** | Any deployment action outside the standing grant scope definition requires a Specific Deployment Instrument. |
| **Trigger** | Scope creep in standing grant usage is a Scope Drift event under AWOF Trigger Class 2\. |
| **Detection** | F-OV agents monitor standing grant scope adherence. |

---

## SECTION 6: IP TRANSFER

### 6.1 Standard Transfer Protocol

Applies to commercial counterparty IP transfer requests.

| Condition | Description |
| :---- | :---- |
| **Scope and Pricing** | Transfer is scoped and priced in the engagement instrument before mandate close. |
| **Transfer Instrument** | Specifies: asset, scope of transfer, retained HoldCo rights (if any), consideration, and effective date. |
| **HAN Authorization** | IP transfer is a non-delegable HAN authority. |
| **IMP Logging** | Transfer is logged in the IP Register with effective date and counterparty identification. |
| **No Valid Transfer Without HAN** | No transfer instrument is valid without HAN signature. |

### 6.2 Sovereign Transfer Protocol

Applies to sovereign/DFI engagements where counterparty procurement requirements include public goods dedication or equivalent IP dedication conditions.

| Condition | Description |
| :---- | :---- |
| **Pre-Mandate Scoping** | Sovereign Transfer terms must be established in the engagement instrument before mandate close — not negotiated post-delivery. |
| **Transfer Instrument** | Specifies: asset, public dedication scope, retained HoldCo attribution rights, and effective date. |
| **HAN Authorization** | Sovereign Transfer is a non-delegable HAN authority. |
| **Attribution Retention** | Sovereign Transfer does not extinguish HoldCo attribution rights unless explicitly stated. |
| **IMP Logging** | Sovereign Transfer is logged in the IP Register as a distinct transfer class. |
| **Suspension on HAN Unavailability** | Active negotiations for Sovereign Transfer are constitutionally suspended upon HAN unavailability and resume upon HAN restoration. |

### 6.3 Transfer Rules

| Rule | Description |
| :---- | :---- |
| **HAN-Only** | All IP transfer authorizations (Standard and Sovereign) are non-delegable HAN authorities. |
| **Pre-Mandate Scoping** | Sovereign Transfer terms must be scoped before mandate close. |
| **IMP Logging** | All transfers are logged in the IP Register. |
| **ERDP Disclosure** | Sovereign Transfer instruments may trigger ERDP event-triggered disclosure. |

---

## SECTION 7: DUAL-STATUS CLASSIFICATION

### Definition

A framework may carry simultaneous commercial and open-source licensing status.

### Conditions

| Condition | Description |
| :---- | :---- |
| **Dual-Status Flag** | The IP Register entry carries a Dual-Status Classification flag. |
| **Boundary Definition** | The Boundary Definition explicitly defines the doctrine layer (open-source eligible) and the application/deployment layer (commercial license required). |
| **Doctrine Publication** | Publication of the doctrine layer under LM-2 does not constitute a license for the application layer. |
| **License Specificity** | Commercial license instruments referencing a Dual-Status asset must specify which layer is licensed. |
| **HAN Authorization** | Dual-Status Classification requires HAN authorization and is logged in the IP Register. |

---

## SECTION 8: VERSION MANAGEMENT

### 8.1 Framework Versioning

| Rule | Description |
| :---- | :---- |
| **Versioning** | All IP-FD assets are versioned. Version increments require HAN authorization. |
| **Version Entry** | Each version is a distinct IP Register entry carrying: version number, change description, effective date, and relationship to prior versions (superseding, supplementing, or parallel). |
| **License Version Binding** | Active license instruments specify the version licensed. Version upgrades are not automatically included in existing licenses unless the license instrument explicitly provides for version following. |

### 8.2 Curriculum Version Binding

| Rule | Description |
| :---- | :---- |
| **Version Binding** | IP-CC assets are bound to a specific IP-FD version at program launch. The IP Register entry for each IP-CC asset carries the bound IP-FD version reference. |
| **Curriculum Review Protocol** | Version transitions in IP-FD assets trigger a Curriculum Review Protocol: |
|  | \- Institute reviews whether the version change materially affects certification content |
|  | \- If material: determines whether existing designation holders require revalidation |
|  | \- If non-material: existing designations remain valid under the bound version; curriculum updated at next program cycle |
| **IMP Logging** | Curriculum Review Protocol findings are logged in the IP Register. |

### 8.3 Retired Versions

| Rule | Description |
| :---- | :---- |
| **Archival** | Retired IP versions are archived in the IP Register, not deleted. |
| **Audit Availability** | They remain available for audit reconstructability under I3 of ICC-8. |
| **License Validity** | Active license instruments referencing a retired version remain valid under the retired version terms unless renegotiated. |

---

## SECTION 9: ATTRIBUTION REQUIREMENTS

### Open-Source Attribution (LM-2)

| Requirement | Description |
| :---- | :---- |
| **Asset Name and Version** | Full asset name and version |
| **Auctor Designation** | Terrylan Manalansan / 19 Integrated |
| **Governing Framework Reference** | 19-IPAS v1.1 |
| **Publication Date** | Date of publication |
| **License Terms** | Applicable open-source license terms |

### Sovereign/DFI Attribution (LM-3)

| Requirement | Description |
| :---- | :---- |
| **Defined in Transfer Instrument** | Attribution requirements for LM-3 are defined in the Sovereign Transfer instrument. |
| **HAN Modification** | Attribution may be modified by HAN authorization. |

### Commercial Attribution (LM-1)

| Requirement | Description |
| :---- | :---- |
| **Governed by License Instrument** | Attribution for LM-1 is governed by the license instrument terms. |

### Attribution Rules

| Rule | Description |
| :---- | :---- |
| **Mandatory Attribution** | All IP assets released under LM-2 (open-source) carry mandatory attribution requirements. |
| **Enforcement** | Violation of attribution requirements for LM-2 assets is referred to the HoldCo contestation interface under CEN-2 of ICC-8. |
| **ILTP Establishes Terms** | ILTP establishes the attribution terms. Enforcement is a contestation matter. |

---

## SECTION 10: NON-DELEGABLE IP AUTHORITIES

The following IP actions are non-delegable HAN authorities:

| \# | Authority | Description |
| :---- | :---- | :---- |
| 1 | **All IP Transfer Authorizations** | Standard and Sovereign transfer authorization |
| 2 | **Dual-Status Classification Authorization** | Authorization of Dual-Status Classification |
| 3 | **New IP Register Entry Acknowledgment** | Acknowledgment of new IP-FD assets |
| 4 | **Sublicensing Authorization** | Authorization of sublicensing |
| 5 | **Standing Grant Amendment** | Amendment of standing grants |
| 6 | **Curriculum Review Protocol Determination** | Revalidation determination |
| 7 | **Any License Instrument Execution** | Execution of any license instrument |
| 8 | **MCP Server Registration** | Registration, modification, or deregistration of MCP servers (v2.0) |

### Non-Delegable Rules

| Rule | Description |
| :---- | :---- |
| **HAN-Only** | No agent — AI or otherwise — may execute these actions. |
| **Suspension on HAN Unavailability** | All are suspended upon HAN unavailability and resume upon HAN restoration. |
| **IMP Logging** | All actions are logged in IMP as DRO. |

---

## SECTION 11: ACCOUNTABILITY CHAIN FOR IP ACTIONS

HAN (Terrylan\_Manalansan)  
  │  
  ├──→ IP Register Acknowledgment  
  │       │  
  │       └──→ IP Asset (registered, versioned, classified)  
  │  
  ├──→ Standing Grant or Specific Instrument  
  │       │  
  │       └──→ Entity Deployment (Consultin' / Publishin' / Institute)  
  │               │  
  │               └──→ License Instrument or Publication Instrument  
  │                       │  
  │                       └──→ External Counterparty or Public Domain  
  │  
  └──→ Audit (IP Register \+ CEF Engagement Records \+ I3 Audit Chain)  
          │  
          └──→ Accountability Terminus: HAN (Terrylan\_Manalansan)

---

## SECTION 12: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship to ILTP |
| :---- | :---- |
| **ICC-8** | Constitutional parent — ILTP operates under ICC-8 invariants |
| **19-IPAS** | IP portfolio standards — ILTP operationalizes 19-IPAS governance |
| **Consultin' Charter** | Standing grant scope for commercial deployment |
| **Publishin' Charter** | Standing grant scope for publication; Publication Clearance Rule |
| **Institute Charter** | Standing grant scope for certification; Curriculum Version Binding |
| **CEF** | Engagement instrument — IP-ED derivatives logged through CEF into IP Register |
| **AWOF** | Workforce instrument — agent IP actions governed by standing grant scope |
| **Pricing Architecture** | Pricing instrument — IP license pricing governed separately |
| **IMP** | IP Register entries logged as GAO; derivatives logged as ECO-linked objects |
| **HAN** | IP transfer authorization is a non-delegable HAN authority |
| **ERDP** | IP Register status may be disclosed under ERDP |
| **DEP** | ILTP amendments require DEP process |

---

## SECTION 13: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **IP Class Completeness** | All 4 IP classes are defined with ownership and deployment authority. |
| **IP Register Completeness** | All IP assets must be entered in the IP Register with all 14 fields. |
| **Licensing Model Completeness** | All 4 licensing models are defined with scope and limitations. |
| **Inter-Entity Governance** | Standing grants and Specific Deployment Instruments are defined. |
| **Transfer Protocol** | Standard and Sovereign Transfer Protocols are defined with HAN authorization requirements. |
| **Version Management** | Framework versioning and Curriculum Version Binding are defined. |
| **Attribution Requirements** | Attribution requirements are defined for all licensing models. |
| **Non-Delegable Authorities** | Non-delegable IP authorities are reserved for HAN. |
| **Dual-Status Classification** | Dual-Status Classification requires HAN authorization. |
| **MCP Server Registration** | MCP Server Registration is a Non-Delegable Authority — HAN-only (v2.0). |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| ILTP v1.0 | Initial specification — 4 IP classes, IP Register, 4 licensing models, inter-entity governance, transfer protocols, dual-status classification |
| ILTP v2.0 | Complete rebuild — reconciliation with ICC-8, IMP, CEF, AWOF, HAN, CGF, ERDP, and DEP; expanded IP Register fields (Supply Chain, Model Provenance, MCP Server); MCP Server Registration as Non-Delegable Authority; CFL-V validation rules |

---

## The One-Sentence Summary

> *"ILTP v2.0 governs IP classification (IP-FD, IP-PI, IP-CC, IP-ED), licensing (Commercial, Open-Source, Sovereign/DFI, Internal Use), transfer (Standard and Sovereign Transfer Protocols), version management (Framework Versioning, Curriculum Version Binding, Retired Versions), and inter-entity IP flows (Standing Grants, Specific Deployment Instruments, Publication Clearance Rule) — with the IP Register as the authoritative record, attribution requirements for all licensing models, non-delegable IP authorities reserved for HAN (including MCP Server Registration), and CFL-V validation, ensuring that all IP assets are protected, traceable, and properly attributed under ICC-8 constitutional constraints."*
