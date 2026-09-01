# RGI-8 v2.0 — Runtime Governance Interpretation

**Status:** Built — v2.0 (Reconciliation with CTAM, CDT-7, CAM-5, AICA-5, ICC-8, AWOF, ADTEP, and CAD-7)  
**Type:** Operational Interpretation Instrument  
**Parent Stack:** CTAM (Capability-Tier Authorization Matrix) — Execution Mode Attribute  
**Version:** 2.0 — Supersedes RGI-8 v1.0

---

## PREAMBLE

Runtime Governance Interpretation (RGI-8) is the operational instrument of CTAM's Execution Mode attribute. It answers: *Does this declared boundary operate as a checkpoint or as a continuous influence?*

RGI-8 defines whether a declared boundary operates as a **Gate** (checkpoint) or **Steer** (continuous influence) — the distinction between a binary allowed/blocked control and a continuous shaping influence. Every CTAM cell carries an Execution Mode attribute (Gate or Steer), and RGI-8 is the operational instrument that consumes the Steer flag.

**The core insight:** A boundary that acts as a checkpoint (Gate) is governed differently than a boundary that acts as a continuous influence (Steer). Gate is auditable as a discrete event; Steer is auditable as a continuous trace. RGI-8 operationalizes this distinction, providing the runtime mechanisms for drift detection, fidelity-to-declaration tracing, constraint supremacy, adaptation firewall, fail-safe reversion, and observability premium.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

RGI-8 ensures that:

1. **Declaration binding is maintained** — RGI-8 compiles declared bounds; does not originate them  
2. **Execution mode is defined** — Gate vs. Steer distinction is operationalized  
3. **Fidelity-to-declaration trace is maintained** — For contested output, the trace reveals which boundary steered reasoning  
4. **Drift is detected** — Continuous monitoring with mandatory human escalation on threshold breach  
5. **Constraint supremacy is enforced** — Gate overrides Steer  
6. **Adaptation firewall is enforced** — Steer output cannot feed live Adaptation without fresh Declaration Binding  
7. **Fail-safe reversion is active** — Steer reverts to Gate if infrastructure fails  
8. **Observability premium is enforced** — Steer requires Observability one tier above Gate

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Gate vs. Steer execution mode interpretation | Capability taxonomy (CDT-7) |
| Fidelity-to-declaration tracing | Authorization grants (CTAM) |
| Drift detection and escalation | Capability tiering (CAM-5) |
| Constraint supremacy enforcement | Human authority (HAN/HOF) |
| Adaptation firewall enforcement | Workforce governance (AWOF) |
| Fail-safe reversion | Technical enforcement (ADTEP) |
| Steer observability premium | Institutional memory (IMP) |

### Governing Relationships

| Instrument | Relationship to RGI-8 |
| :---- | :---- |
| **CTAM** | Parent instrument — Execution Mode attribute consumed by RGI-8 |
| **CDT-7** | Capability domains — RGI-8 applies to each domain |
| **CAM-5** | Capability tiers — RGI-8 mode is per cell |
| **AICA-5** | Control architecture — RGI-8 operationalizes Steer detection |
| **ICC-8** | Constitutional ceiling — RGI-8 may not violate ICC-8 invariants |
| **AWOF** | Workforce governance — RGI-8 applies to AWOF-governed agents |
| **ADTEP** | Technical enforcement — RGI-8 feeds into ADTEP enforcement |
| **CAD-7** | Coalition accountability — RGI-8 applies to coalitions |

---

## SECTION 2: DECLARATION BINDING

### Statement

RGI-8 does not originate boundaries; it compiles an already-declared CDT-7 / AICA-5 / ICC-8 object into computable form.

### Requirements

| Requirement | Description |
| :---- | :---- |
| **Compilation** | RGI-8 compiles declared boundaries into computable form |
| **No Origination** | RGI-8 does not originate boundaries |
| **No Reinterpretation** | A binding that reinterprets or expands what it compiles is a CDT-7 Constraint violation |
| **No Expansion** | RGI-8 does not expand boundaries |

### Implementation

| Aspect | Implementation |
| :---- | :---- |
| **CTAM Cell Reading** | RGI-8 reads CTAM cell grants per domain and tier |
| **Role Specification Reading** | RGI-8 reads Role Specification Schema fields |
| **ICC-8 Reading** | RGI-8 reads ICC-8 invariants |
| **AICA-5 Reading** | RGI-8 reads AICA-5 node constraints |

### RGI-8 Violation

| Violation | Response |
| :---- | :---- |
| **Boundary Reinterpretation** | Flagged; escalated to HAN; XOO created |
| **Boundary Expansion** | Flagged; escalated to HAN; XOO created |

---

## SECTION 3: EXECUTION MODE — GATE VS. STEER

### Definitions

| Mode | Definition | Auditing | Default |
| :---- | :---- | :---- | :---- |
| **Gate** | A checkpoint — you either pass or you don't. Binary: allowed or blocked. Auditable as a discrete event. | Discrete event | Default for all cells |
| **Steer** | A continuous influence — shapes reasoning throughout. Graduated: nudged, guided, weighted. Auditable as a continuous trace. | Continuous trace | Requires qualification event |

### Steer Qualification

| Requirement | Description |
| :---- | :---- |
| **Qualification Event** | Steer flag requires a passed qualification event — a demonstrated, working trace mechanism |
| **Default to Gate** | Absent demonstration, the cell defaults to Gate |
| **CTAM Recording** | CTAM records Steer only after qualification event passed |

### Mode Assignment Rules

| Rule | Description |
| :---- | :---- |
| **Per Domain** | Mode is assigned per domain, not per system |
| **Per Tier** | Mode is assigned per domain-tier cell |
| **Default Gate** | Default mode is Gate |
| **Steer Requires Qualification** | Steer requires demonstrated trace mechanism |

---

## SECTION 4: FIDELITY-TO-DECLARATION TRACE

### Statement

For any contested output, it must be possible to retrieve which declared boundary, authored by whom, on what date, was steering the reasoning — not probabilistically.

### Requirements

| Requirement | Description |
| :---- | :---- |
| **Retrievability** | For any contested output, retrieve the boundary that steered reasoning |
| **Attribution** | Identify who authored the boundary and on what date |
| **Deterministic** | Not probabilistic — the trace must be deterministic |
| **Qualification Event** | This is the qualification event referenced in Section 3 |

### Implementation

| Aspect | Implementation |
| :---- | :---- |
| **Trace Logging** | Every Steer-mode action logs the boundary that steered reasoning |
| **Boundary Reference** | Log references the specific declared boundary |
| **Attribution** | Log includes author and date of boundary |
| **Timestamp** | Log includes timestamp of action |

### Trace Fields

| \# | Field | Description |
| :---- | :---- | :---- |
| 1 | **Action ID** | Unique identifier for the action |
| 2 | **Steering Boundary** | The declared boundary that steered reasoning |
| 3 | **Boundary Author** | Who authored the boundary |
| 4 | **Boundary Date** | Date the boundary was declared |
| 5 | **Timestamp** | Action timestamp |
| 6 | **Agent ID** | Agent that performed the action |
| 7 | **Domain** | Capability domain of the action |
| 8 | **Output Hash** | Hash of output for verification |

### Trace Violation

| Violation | Response |
| :---- | :---- |
| **No Trace Available** | Output flagged; Escalation Flag issued; HAN review |
| **Probabilistic Trace Only** | Output flagged; Escalation Flag issued; HAN review |

---

## SECTION 5: DRIFT DETECTION AND ESCALATION THRESHOLD

### Statement

Drift detection compares realized steering against declared intent continuously, not just on-demand. For Perception-domain Steer grants specifically, this must monitor source-fidelity, not only output-fidelity.

### Requirements

| Requirement | Description |
| :---- | :---- |
| **Continuous Monitoring** | Drift detection runs continuously, not on-demand |
| **Threshold Declared** | Drift threshold is declared at the time the Steer flag is set |
| **Source-Fidelity Monitoring** | Perception-domain Steer grants monitor source-fidelity, not only output-fidelity |
| **Mandatory Human Escalation** | Crossing the drift threshold triggers mandatory human review |

### Implementation

| Aspect | Implementation |
| :---- | :---- |
| **Continuous Surveillance** | Drift detection runs continuously for Steer-mode domains |
| **Threshold Declaration** | Drift threshold declared at Steer flag qualification |
| **Source-Fidelity** | Perception-domain Steer monitors source-fidelity |
| **Human Escalation** | Threshold breach triggers mandatory human review |

### Drift Threshold

| Aspect | Description |
| :---- | :---- |
| **Declared at Steer Qualification** | Threshold declared at qualification event |
| **Per Domain/Tier** | Threshold may vary by domain and tier |
| **Human-Legible** | Threshold must be human-legible and enforceable |
| **Escalation Path** | Crossing threshold triggers HAN review |

### Escalation Flow

Drift Detected  
  │  
  ├──→ Below Threshold → Logged (OEO)  
  │  
  └──→ Above Threshold → HAN Review  
          │  
          ├──→ Approved → Continue  
          ├──→ Modified → Adjust Steering  
          └──→ Rejected → Halt; Escalation Flag

### Drift Detection Rules

| Rule | Description |
| :---- | :---- |
| **Continuous** | Detection runs continuously, not on-demand |
| **Source-Fidelity** | Perception-domain monitors source-fidelity |
| **Threshold Declared** | Threshold declared at qualification |
| **Human Escalation** | Threshold breach triggers mandatory human review |
| **IMP Logging** | Drift events logged as OEO in IMP |

---

## SECTION 6: CONSTRAINT SUPREMACY OVER STEERING

### Statement

Gate is absolute; Steer can never override a Gate boundary. A conflict between a Gate and a Steer signal on the same domain resolves to the Gate, and that resolution event is itself logged.

### Requirements

| Requirement | Description |
| :---- | :---- |
| **Gate is Absolute** | Gate overrides Steer; no exceptions |
| **Conflict Resolution** | Gate wins in any conflict |
| **Resolution Logging** | Conflict resolution event is logged |

### Implementation

| Aspect | Implementation |
| :---- | :---- |
| **Gate Priority** | Gate boundaries have priority over Steer |
| **Conflict Detection** | Conflicts between Gate and Steer are detected |
| **Resolution Logging** | Resolution events are logged as DRO |
| **No Override** | Steer cannot override Gate |

### Conflict Resolution Flow

Gate Boundary and Steer Signal Conflict  
  │  
  └──→ Resolve to Gate  
          │  
          ├──→ Action Blocked (if Gate says block)  
          ├──→ Action Allowed (if Gate says allow)  
          └──→ Resolution Event Logged

### Constraint Supremacy Rules

| Rule | Description |
| :---- | :---- |
| **Gate is Absolute** | Gate overrides Steer |
| **No Steer Override** | Steer cannot override Gate |
| **Resolution Logging** | Resolution events logged as DRO |

---

## SECTION 7: ADAPTATION FIREWALL

### Statement

A Steer-mode signal's output may not be used as input to a live Adaptation-domain grant (CDT-7 Tier 4+) without passing through a fresh Declaration Binding event, authorized separately from the original Steer grant.

### Requirements

| Requirement | Description |
| :---- | :---- |
| **No Direct Feed** | Steer output cannot feed live Adaptation without fresh Declaration Binding |
| **Fresh Declaration Binding** | Fresh Declaration Binding event is required |
| **Separate Authorization** | Fresh binding is authorized separately from original Steer grant |

### Implementation

| Aspect | Implementation |
| :---- | :---- |
| **Adaptation Firewall Check** | RGI-8 checks for Steer-to-Adaptation feed |
| **Fresh Declaration Required** | Fresh Declaration Binding required for Steer → Adaptation |
| **Separate Authorization** | Authorization is separate from original Steer grant |
| **Firewall Enforcement** | Unauthorized feed is blocked |

### Adaptation Firewall Flow

Steer Output  
  │  
  ├──→ Not to Adaptation → Continue  
  │  
  └──→ To Adaptation  
          │  
          ├──→ Fresh Declaration Binding Present → Allowed  
          └──→ No Fresh Declaration Binding → Blocked; Escalation Flag

### Adaptation Firewall Rules

| Rule | Description |
| :---- | :---- |
| **No Direct Feed** | Steer output cannot feed Adaptation without fresh Declaration |
| **Fresh Declaration Required** | Fresh Declaration Binding required |
| **Separate Authorization** | Authorization separate from original Steer grant |
| **Block on Violation** | Unauthorized feed is blocked |

---

## SECTION 8: FAIL-SAFE REVERSION

### Statement

If the infrastructure a Steer grant depends on for trace and drift detection becomes unavailable, the grant reverts automatically to Gate-only operation until restored. Reversion is per-cell — it does not take down CTAM or CDT-7 grants generally.

### Requirements

| Requirement | Description |
| :---- | :---- |
| **Infrastructure Failure** | If trace/drift infrastructure fails, Steer reverts to Gate |
| **Automatic Reversion** | Reversion is automatic; no human action required |
| **Per-Cell** | Reversion is per-cell, not system-wide |
| **Restoration** | Reverts back to Steer when infrastructure is restored |

### Implementation

| Aspect | Implementation |
| :---- | :---- |
| **Infrastructure Health Check** | RGI-8 monitors trace/drift infrastructure health |
| **Automatic Reversion** | Reverts to Gate automatically on failure |
| **Per-Cell Reversion** | Reversion applies only to affected cells |
| **Restoration Detection** | Detects infrastructure restoration; reverts to Steer |

### Fail-Safe Flow

Steer Infrastructure Available  
  │  
  ├──→ Yes → Steer Mode Active  
  │  
  └──→ No → Automatic Reversion to Gate  
          │  
          ├──→ Gate Mode Active (per-cell)  
          └──→ Infrastructure Restored → Revert to Steer

### Fail-Safe Rules

| Rule | Description |
| :---- | :---- |
| **Automatic** | Reversion is automatic |
| **Per-Cell** | Reversion is per-cell |
| **Restoration Detection** | Detects and reverts on restoration |
| **IMP Logging** | Reversion events logged as DRO |

---

## SECTION 9: STEER OBSERVABILITY PREMIUM

### Statement

A Steer-mode flag on any cell requires Observability at minimum one tier above what the same domain/tier combination would require under Gate mode.

### Requirements

| Requirement | Description |
| :---- | :---- |
| **Observability Premium** | Steer requires Observability one tier above Gate |
| **Minimum One Tier** | Observability must be at least one tier higher |
| **Per Cell** | Premium applies per domain-tier cell |

### Implementation

| Aspect | Implementation |
| :---- | :---- |
| **Observability Tier Check** | RGI-8 checks Observability tier against Steer requirement |
| **Premium Enforcement** | Steer not allowed if Observability tier is too low |
| **CTAM Recording** | CTAM records Observability premium compliance |

### Observability Tier Mapping

| Gate Observability Tier | Required Steer Observability Tier |
| :---- | :---- |
| Tier 1 | Tier 2 minimum |
| Tier 2 | Tier 3 minimum |
| Tier 3 | Tier 4 minimum |
| Tier 4 | Tier 5 minimum |
| Tier 5 | Tier 5 (no higher tier) |

### Steer Observability Rules

| Rule | Description |
| :---- | :---- |
| **Premium Required** | Steer requires Observability one tier above Gate |
| **Minimum One Tier** | Observability must be at least one tier higher |
| **No Exceptions** | No exceptions to the premium requirement |
| **CTAM Recording** | CTAM records Observability premium compliance |

---

## SECTION 10: RGI-8 AND AICA-5 CONTROL NODES

| AICA-5 Node | RGI-8 Integration |
| :---- | :---- |
| **C-N3 Signal Validation** | Steer-mode outputs require continuous validation; Gate-mode outputs require discrete validation |
| **E-N4 Monitoring Loops** | Steer-mode requires continuous monitoring loops; Gate-mode requires discrete monitoring |
| **Co-N2 Drift Detection** | Steer-mode drift detection is continuous; Gate-mode drift detection is discrete |
| **Ac-N1 Decision Lineage** | Steer-mode lineage is continuous trace; Gate-mode lineage is discrete event |
| **Ac-N3 Outcome Validation** | Steer-mode validation is continuous; Gate-mode validation is discrete |

---

## SECTION 11: RGI-8 AND ADTEP

| ADTEP Component | RGI-8 Integration |
| :---- | :---- |
| **Role Specification Schema** | Execution Modes field specifies Gate/Steer per domain |
| **Pre-Delivery Log Entry** | RGI-8 mode captured in Pre-Delivery Log Entry |
| **Escalation Flag** | Drift detection may trigger Escalation Flag |
| **Constitutional Suspension** | Fail-safe reversion may trigger Constitutional Suspension |

---

## SECTION 12: RGI-8 AND CAD-7

| CAD-7 Aspect | RGI-8 Integration |
| :---- | :---- |
| **Coalition Steer** | Steer-mode coalitions require continuous trace across all members |
| **Coalition Drift** | Drift detection applies to coalition outputs collectively |
| **Coalition Observability Premium** | Coalition Steer requires Observability premium across all members |

---

## SECTION 13: RGI-8 LOGGING

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **DRO** | `decision_type: "framework_selection"` | RGI-8 mode assignment, drift detection, fail-safe reversion |
| **OEO** | `outcome_type: "drift_detection"` | Drift detection events |
| **XOO** | `exception_type: "rgi8_violation"` | RGI-8 violations |

### Mode Assignment Template

RGI-8 Mode Assignment  
Domain: "Perception"  
Tier: 3  
Execution Mode: "Steer"  
Qualification Event: "2026-08-31T10:00:00Z"  
Trace Mechanism: "Available"  
Drift Threshold: "0.05"  
Observability Tier: "4"  
Gate Observability Tier: "3"  
Status: "Active"

---

## SECTION 14: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship to RGI-8 |
| :---- | :---- |
| **CTAM** | Parent instrument — Execution Mode attribute consumed by RGI-8 |
| **CDT-7** | Capability domains — RGI-8 applies to each domain |
| **CAM-5** | Capability tiers — RGI-8 mode is per cell |
| **AICA-5** | Control architecture — RGI-8 operationalizes Steer detection |
| **ICC-8** | Constitutional ceiling — RGI-8 may not violate ICC-8 invariants |
| **AWOF** | Workforce governance — RGI-8 applies to AWOF-governed agents |
| **ADTEP** | Technical enforcement — RGI-8 feeds into ADTEP enforcement |
| **CAD-7** | Coalition accountability — RGI-8 applies to coalitions |
| **IMP** | RGI-8 logs to IMP as DRO, OEO, XOO |

---

## SECTION 15: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Declaration Binding** | RGI-8 compiles declared bounds; does not originate or reinterpret them |
| **Steer Qualification** | Steer flag requires qualification event (working trace mechanism). Defaults to Gate absent demonstration. |
| **Fidelity Trace** | For contested output, trace must be retrievable deterministically |
| **Drift Detection** | Continuous monitoring with declared drift threshold; threshold breach triggers mandatory human review |
| **Constraint Supremacy** | Gate is absolute; Steer cannot override Gate |
| **Adaptation Firewall** | Steer output cannot feed live Adaptation without fresh Declaration Binding |
| **Fail-Safe Reversion** | Steer reverts to Gate if infrastructure fails; reversion per-cell |
| **Steer Observability Premium** | Steer requires Observability one tier above Gate |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| RGI-8 v1.0 | Initial specification — 8 components: Declaration Binding, Execution Mode, Fidelity Trace, Drift Detection, Constraint Supremacy, Adaptation Firewall, Fail-Safe Reversion, Observability Premium |
| RGI-8 v2.0 | Complete rebuild — reconciliation with CTAM, CDT-7, CAM-5, AICA-5, ICC-8, AWOF, ADTEP, and CAD-7; expanded implementation details; AICA-5 node mapping; ADTEP integration; CAD-7 integration; CFL-V validation rules |

---

## The One-Sentence Summary

> *"RGI-8 v2.0 operationalizes CTAM's Execution Mode attribute across 8 components — Declaration Binding, Gate vs. Steer execution mode, Fidelity-to-Declaration Trace, Drift Detection and Escalation Threshold, Constraint Supremacy Over Steering, Adaptation Firewall, Fail-Safe Reversion, and Steer Observability Premium — defining whether a declared boundary operates as a checkpoint (Gate) or a continuous influence (Steer), with Steer requiring a qualification event, continuous drift detection with mandatory human escalation, and Observability one tier above Gate, under AICA-5, ICC-8, AWOF, ADTEP, and CAD-7 governance."*
