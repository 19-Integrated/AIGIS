# Stack Version Map v2.0

**Status:** Built — v2.0 (Reconciliation with DEP, IMP, ICC-8, and all stack instruments)  
**Type:** Meta-Governance Instrument  
**Parent Stack:** DEP (Doctrine Extension Protocol)  
**Version:** 2.0 — Supersedes Stack Version Map v1.0

---

## PREAMBLE

The Stack Version Map is a living record maintained in IMP of the current canonical version of every instrument in the 19 Integrated governance stack. It answers: *What is the current version of every instrument, and what was the last change made to each?*

The Stack Version Map is updated upon every authorized DEP change. It is the reference document for governance version binding on all new IMP objects. Historical objects are read against the framework version that governed them—the Map preserves the version history so that objects created under prior versions remain auditable and interpretable.

**The core insight:** Versioning is governance. Without a version map, an institution cannot know what rules applied when. The Stack Version Map makes governance version binding real—ensuring that every institutional object carries the version of the framework that governed its creation.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

The Stack Version Map ensures that:

1. **Current versions are known** — Every instrument has a declared current version  
2. **Version history is preserved** — Historical versions remain accessible for audit  
3. **DEP changes are tracked** — Every DEP change updates the Map  
4. **Version binding is maintained** — Objects reference the version active at creation  
5. **Instrument relationships are visible** — Dependencies between instruments are documented  
6. **Layer classification is maintained** — Each instrument is classified by layer

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| All canonical stack instruments | Client engagement deliverables |
| Version numbers and history | Business strategy or marketing |
| DEP change tracking | Operational efficiency |
| Layer classification | Technical delivery execution |
| Instrument dependencies | Commercial decisions |

### Governing Relationships

| Instrument | Relationship to Stack Version Map |
| :---- | :---- |
| **DEP** | Parent instrument — Map updated upon every DEP change |
| **IMP** | Map stored as GAO; version binding referenced by all IMP objects |
| **ICC-8** | Constitutional ceiling — Map reflects ICC-8 versions |
| **All stack instruments** | Map records current version of each |

---

## SECTION 2: MAP STRUCTURE

### Fields

| \# | Field | Description |
| :---- | :---- | :---- |
| 1 | **Instrument** | Instrument name |
| 2 | **Current Version** | Current canonical version (semantic versioning) |
| 3 | **Previous Version** | Previous canonical version (if applicable) |
| 4 | **Layer** | Layer classification |
| 5 | **Last DEP Change Date** | Date of last DEP change |
| 6 | **Change Class** | I / II / III / IV |
| 7 | **Change Description** | Summary of change |
| 8 | **DEP Signal Reference** | Reference to signal that triggered change |
| 9 | **Dependencies** | Instruments this instrument depends on |
| 10 | **Dependents** | Instruments that depend on this instrument |
| 11 | **Status** | Active / Deprecated / Retired |

### Layer Classifications

| Layer | Description | Instruments |
| :---- | :---- | :---- |
| **Constitutional** | Non-negotiable constitutional invariants | ICC-8, HOF, HAN, HIS-12, CEN-1 to CEN-7 |
| **Primitive — Memory** | Institutional memory and state | IMP |
| **Primitive — Trust** | Trust and engagement architecture | EAF |
| **Meta-Governance** | Governance of governance | DEP, Stack Version Map |
| **Governance Stack** | Core governance instruments | AICA-5, AWOF, ADTEP, RGI-8, CAD-7, ILTP, CGF, ERDP, AIR |
| **Capability** | Capability taxonomy and authorization | CDT-7, CTAM, CAM-5 |
| **Workforce** | Workforce classification and governance | AWOF, Agent Classification System, Role Specification Schema, Trigger System, MVOS, Handoff Package |
| **Technical Enforcement** | Technical enforcement mechanisms | ADTEP, Session Initialization Checklist, Pre-Delivery Log Entry, Escalation Flag, Constitutional Suspension, Constitutional Refresh, AOBA, ABA |
| **Engagement** | Client engagement and operations | CEF |
| **Institutional Capital** | Institutional architecture | MICOS-25 |

---

## SECTION 3: CURRENT STACK VERSION MAP

| \# | Instrument | Current Version | Previous Version | Layer | Last DEP Change | Change Class | Status |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 1 | ICC-8 | v2.0 | v1.2 | Constitutional | 2026-08-31 | II | Active |
| 2 | HOF | v2.0 | v1.0 | Constitutional | 2026-08-31 | II | Active |
| 3 | HAN | v2.0 | v1.0 | Constitutional | 2026-08-31 | II | Active |
| 4 | HIS-12 | v2.0 | v1.0 | Constitutional | 2026-08-31 | II | Active |
| 5 | HAWI | v2.0 | v1.3 | Constitutional | 2026-08-31 | II | Active |
| 6 | CEN-1 to CEN-7 | v2.0 | v1.0 | Constitutional | 2026-08-31 | III | Active |
| 7 | IMP | v2.0 | v1.0 | Primitive — Memory | 2026-08-31 | II | Active |
| 8 | EAF | v2.0 | v1.0 | Primitive — Trust | 2026-08-31 | II | Active |
| 9 | DEP | v2.0 | v1.0 | Meta-Governance | 2026-08-31 | III | Active |
| 10 | Stack Version Map | v2.0 | v1.0 | Meta-Governance | 2026-08-31 | III | Active |
| 11 | AICA-5 | v2.0 | v1.1 | Governance Stack | 2026-08-31 | II | Active |
| 12 | AICA-5 Maturity Grid | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 13 | AICA-5 Operating Model | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 14 | AICA-5 Implementation Pathway | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 15 | AICA-5 Measurement Framework | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 16 | CDT-7 | v2.0 | v1.0 | Capability | 2026-08-31 | II | Active |
| 17 | CTAM | v2.0 | v1.0 | Capability | 2026-08-31 | II | Active |
| 18 | CAM-5 | v2.0 | v1.0 | Capability | 2026-08-31 | II | Active |
| 19 | AWOF | v2.0 | v1.1 | Workforce | 2026-08-31 | II | Active |
| 20 | Agent Classification System | v2.0 | v1.0 | Workforce | 2026-08-31 | II | Active |
| 21 | Role Specification Schema | v2.0 | v1.0 | Workforce | 2026-08-31 | II | Active |
| 22 | Trigger System | v2.0 | v1.0 | Workforce | 2026-08-31 | II | Active |
| 23 | MVOS | v2.0 | v1.0 | Workforce | 2026-08-31 | II | Active |
| 24 | Handoff Package | v2.0 | v1.0 | Workforce | 2026-08-31 | II | Active |
| 25 | ADTEP | v2.0 | v1.0 | Technical Enforcement | 2026-08-31 | II | Active |
| 26 | Session Initialization Checklist | v2.0 | v1.0 | Technical Enforcement | 2026-08-31 | II | Active |
| 27 | Pre-Delivery Log Entry | v2.0 | v1.0 | Technical Enforcement | 2026-08-31 | II | Active |
| 28 | Escalation Flag | v2.0 | v1.0 | Technical Enforcement | 2026-08-31 | II | Active |
| 29 | Constitutional Suspension | v2.0 | v1.0 | Technical Enforcement | 2026-08-31 | II | Active |
| 30 | Constitutional Refresh | v2.0 | v1.0 | Technical Enforcement | 2026-08-31 | II | Active |
| 31 | AOBA | v2.0 | v1.0 (Scoped) | Technical Enforcement | 2026-08-31 | II | Active |
| 32 | ABA | v2.0 | v1.0 (Proposed) | Technical Enforcement | 2026-08-31 | II | Active |
| 33 | CEF | v2.0 | v1.0 | Engagement | 2026-08-31 | II | Active |
| 34 | ILTP | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 35 | CGF | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 36 | Public Designation Register | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 37 | ERDP | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 38 | AIR | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 39 | RGI-8 | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 40 | CAD-7 | v2.0 | v1.0 | Governance Stack | 2026-08-31 | II | Active |
| 41 | MICOS-25 | v1.0 | — | Institutional Capital | Pre-DEP (founding) | — | Active |
| 42 | MAGOS-25 | v1.0 | — | Institutional Capital | Pre-DEP (founding) | — | Active |

---

## SECTION 4: VERSION BINDING

### Purpose

Governance version binding ensures that every institutional object is bound to the version of the governing framework active at the time of its creation. Subsequent framework updates do not retroactively alter historical objects.

### Implementation

| Field | Source | Description |
| :---- | :---- | :---- |
| **governing\_framework\_versions** | ECO, DRO, GAO, CRO, OEO, XOO | Key-value map of framework ID to version string active at object creation |
| **version\_binding\_timestamp** | All IMP objects | Timestamp of version binding |
| **stack\_version\_map\_reference** | All IMP objects | Reference to Stack Version Map version at creation |

### Binding Rules

| Rule | Description |
| :---- | :---- |
| **Creation Binding** | Objects are bound to the version active at creation |
| **Immutable** | Version binding is immutable; subsequent updates do not alter historical objects |
| **Audit Access** | Historical objects are read against the framework version that governed them |
| **Map Reference** | Stack Version Map version is referenced in each object |

### Binding Example

Object: GAO-ECO-2026-0a26cb-001  
governing\_framework\_versions:  
  ICC-8: "v2.0"  
  AICA-5: "v2.0"  
  AWOF: "v2.0"  
  IMP: "v2.0"  
version\_binding\_timestamp: "2026-08-31T10:00:00Z"  
stack\_version\_map\_reference: "SVM-2026-08-31"

---

## SECTION 5: MAP MAINTENANCE

### Update Triggers

| Trigger | Action | Responsible |
| :---- | :---- | :---- |
| **DEP Change Authorized** | Map updated with new version and change details | Node Steward (DEP) |
| **New Instrument Admitted** | Map updated with new instrument entry | Node Steward (DEP) |
| **Instrument Deprecated** | Map updated with Deprecated status | Node Steward (DEP) |
| **Instrument Retired** | Map updated with Retired status | Node Steward (DEP) |
| **Annual Review** | Map reviewed for accuracy | Node Steward (DEP) |

### Update Protocol

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | DEP change authorized | HAN | Upon authorization |
| 2 | Instrument version updated | Node Steward (DEP) | Within 24 hours |
| 3 | Map entry updated | Node Steward (DEP) | Within 24 hours |
| 4 | Change logged in IMP | Node Steward (DEP) | Within 48 hours |
| 5 | Active engagements notified | Node Steward (DEP) | Within 72 hours |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **GAO** | `artifact_type: "stack_version_map"` | Map document |
| **DRO** | `decision_type: "framework_selection"` | Map update recorded |

---

## SECTION 6: MAP RETRIEVAL

### Retrieval Modes

| Mode | Purpose | Output |
| :---- | :---- | :---- |
| **Current Version** | Get current version of an instrument | Version string and metadata |
| **Version History** | Get full version history of an instrument | List of versions with dates and changes |
| **Layer View** | Get all instruments in a layer | List of instruments with versions |
| **Dependency View** | Get dependencies of an instrument | List of dependencies and dependents |
| **Snapshot** | Get full map at a point in time | Complete map as of timestamp |
| **Change Log** | Get DEP change history | List of changes with details |

### Retrieval Rules

| Rule | Description |
| :---- | :---- |
| **IMP Storage** | Map is stored as GAO in IMP |
| **Version Awareness** | Retrieval respects version binding |
| **Audit Access** | Historical map versions are accessible for audit |
| **EAF Compliance** | Retrieval respects EAF trust tiers |

---

## SECTION 7: DEPENDENCY GRAPH

### Instrument Dependencies

| Instrument | Dependencies | Dependents |
| :---- | :---- | :---- |
| **ICC-8** | MICOS-25 | All instruments |
| **HOF** | ICC-8 | HAN, HIS-12, HAWI, ABA |
| **HAN** | HOF, HIS-12 | AWOF, ADTEP, CEF, EAF, ILTP, CGF, ERDP, DEP |
| **HIS-12** | HOF | HAN |
| **HAWI** | AWOF, HOF, AICA-5, CAM-5, EAF | — |
| **CDT-7** | — | CTAM, CAM-5 |
| **CTAM** | CDT-7 | CAM-5, RGI-8 |
| **CAM-5** | CTAM, CDT-7 | HAWI |
| **AICA-5** | ICC-8, CDT-7, CTAM, CAM-5 | AICA-5 Maturity Grid, AICA-5 Operating Model, AICA-5 Implementation Pathway, AICA-5 Measurement Framework, AWOF, ADTEP, CEF, EAF, ERDP |
| **AWOF** | HAN, HOF, AICA-5 | Agent Classification System, Role Specification Schema, Trigger System, MVOS, Handoff Package, ADTEP |
| **ADTEP** | AWOF, AICA-5 | Session Initialization Checklist, Pre-Delivery Log Entry, Escalation Flag, Constitutional Suspension, Constitutional Refresh, AOBA |
| **RGI-8** | CTAM, AICA-5 | — |
| **CAD-7** | CFL-F, AWOF | — |
| **CEF** | EAF, IMP, AWOF, HAN, ILTP, AICA-5, ICC-8 | — |
| **EAF** | ICC-8, IMP, AWOF, AICA-5, CEF, HOF, DEP | CEF |
| **IMP** | EAF | All instruments |
| **ILTP** | ICC-8, IMP, CEF, AWOF, HAN, CGF, ERDP, DEP | CEF, CGF |
| **CGF** | ICC-8, ILTP, AWOF, HAN, IMP, ERDP, DEP | Public Designation Register |
| **ERDP** | ICC-8, CEN-1 to CEN-7, IMP, AICA-5, ILTP, CGF, HAN, DEP | AIR |
| **DEP** | ICC-8, IMP, HAN | All instruments |

---

## SECTION 8: MAP TEMPLATE

Stack Version Map  
Generated: 2026-08-31T10:00:00Z  
Version: v2.0  
Status: Current  
Instruments:  
  \- Instrument: ICC-8  
    Current Version: v2.0  
    Previous Version: v1.2  
    Layer: Constitutional  
    Last DEP Change: 2026-08-31  
    Change Class: II  
    Change Description: "I9 Catastrophic Risk Invariant added; CEN-7 Public Contestation added"  
    DEP Signal Reference: "DEP-SIG-2026-001"  
    Dependencies: \["MICOS-25"\]  
    Dependents: \["All instruments"\]  
    Status: Active  
  \- Instrument: AICA-5  
    Current Version: v2.0  
    Previous Version: v1.1  
    Layer: Governance Stack  
    Last DEP Change: 2026-08-31  
    Change Class: II  
    Change Description: "Complete rebuild — reconciliation with CDT-7, CTAM, CAM-5, ICC-8, and RGI-8"  
    DEP Signal Reference: "DEP-SIG-2026-002"  
    Dependencies: \["ICC-8", "CDT-7", "CTAM", "CAM-5"\]  
    Dependents: \["AWOF", "ADTEP", "CEF", "EAF", "ERDP"\]  
    Status: Active  
  \# ... additional instruments

---

## SECTION 9: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship to Stack Version Map |
| :---- | :---- |
| **DEP** | Parent instrument — Map updated upon every DEP change |
| **IMP** | Map stored as GAO; version binding referenced by all IMP objects |
| **ICC-8** | Constitutional ceiling — Map reflects ICC-8 versions |
| **All stack instruments** | Map records current version of each |
| **ECO, DRO, GAO, CRO, OEO, XOO** | Version binding references Map |

---

## SECTION 10: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Instrument Completeness** | All stack instruments are represented in the Map. |
| **Version Currency** | Each instrument has a declared current version. |
| **DEP Tracking** | Each DEP change updates the Map with change details. |
| **Layer Classification** | Each instrument is classified by layer. |
| **Dependency Documentation** | Dependencies and dependents are documented. |
| **Version Binding** | IMP objects reference the Map for version binding. |
| **IMP Storage** | Map is stored as GAO in IMP. |
| **Retrieval Accessibility** | Map is retrievable by current version, history, layer, dependency, snapshot, and change log. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Stack Version Map v1.0 | Initial specification — current versions of all instruments |
| Stack Version Map v2.0 | Complete rebuild — reconciliation with DEP, IMP, ICC-8, and all stack instruments; expanded fields (previous version, dependencies, dependents, status); layer classifications; version binding; map maintenance; retrieval modes; dependency graph; CFL-V validation rules |

---

## The One-Sentence Summary

> *"The Stack Version Map v2.0 is a living record of the current canonical version of every instrument in the 19 Integrated governance stack — with 11 fields per instrument (name, current version, previous version, layer, last DEP change date, change class, change description, DEP signal reference, dependencies, dependents, status), layer classifications (Constitutional, Primitive — Memory, Primitive — Trust, Meta-Governance, Governance Stack, Capability, Workforce, Technical Enforcement, Engagement, Institutional Capital), version binding for all IMP objects, update-on-DEP-change maintenance, 6 retrieval modes, and CFL-V validation — ensuring that every institutional object is bound to the version of the framework that governed its creation."*
