# AICA-5 v2.0 — AI Control Architecture

**Status:** Built — v2.0 (Reconciliation with CDT-7, CTAM, CAM-5, ICC-8, and RGI-8) **Type:** Control Architecture Instrument **Parent Stack:** AIGIS Constitutional Layer **Version:** 2.0 — Supersedes AICA-5 v1.1

---

## PREAMBLE

The AI Control Architecture (AICA-5) is a 5-layer, 25-node control architecture that governs intelligence generation, workflow execution, decision rights, state continuity, and accountability. AICA-5 answers: *How do we make every AI decision traceable, attributable, and correctable?*

AICA-5 is the operational engine of AIGIS. It operationalizes ICC-8 invariants, CDT-7/CTAM/CAM-5 capability grants, and RGI-8 execution modes. It is the bridge between constitutional rules and runtime enforcement.

**The cascade failure argument:** AICA-5's five layers form a dependency chain. Each layer's validity is a precondition for the next layer's function. A failure at any layer does not stay contained — it cascades forward through the architecture until it surfaces as an institutional failure at the accountability boundary. This is the central diagnostic insight of AICA-5.

**Central Claim:** Most AI scaling failures are not capability failures. They are control-architecture failures — specifically, the absence of authority mapping, continuity governance, and accountability lineage operating as a single integrated system.

---

## SECTION 1: THE FIVE-LAYER ARCHITECTURE

| Layer | Function | Nodes | Failure Mode |
| :---- | :---- | :---- | :---- |
| **1\. Cognitive** | Intelligence Generation | C-N1 to C-N5 | Epistemic Drift |
| **2\. Execution** | Workflow Orchestration | E-N1 to E-N5 | Pipeline Fragmentation |
| **3\. Authority** | Decision Rights Architecture | A-N1 to A-N5 | Ungoverned Execution State |
| **4\. Continuity** | State Validity and Drift Control | Co-N1 to Co-N5 | Agentic Divergence |
| **5\. Accountability** | Audit, Liability, and Learning | Ac-N1 to Ac-N5 | Lineage Collapse |

---

## SECTION 2: LAYER 1 — COGNITIVE LAYER (INTELLIGENCE GENERATION)

### Function

Produces continuous, validated intelligence streams from agent-based sourcing, inference, and output calibration. The raw epistemic input to the entire architecture.

### Failure Mode — Epistemic Drift

Agents generate plausible but unvalidated outputs that propagate downstream as authoritative intelligence. The system acts on corrupted inference without detection.

### Validity Condition

Every intelligence output carries a source trace, confidence boundary, and validation status before it is consumed by the Execution Layer.

### Nodes

| Node | Function | Validity Condition | Failure Mode |
| :---- | :---- | :---- | :---- |
| **C-N1 — Intelligence Sourcing** | Governs the selection, activation, and credentialing of intelligence sources | Every source is credentialed before ingestion; credentials refreshed per declared cycle | Uncredentialed sources feeding active pipelines |
| **C-N2 — Inference Architecture** | Governs reasoning chain design, confidence assignment, and output typing | Every inference output has a complete reasoning chain and differentiated confidence assignment | Uniform confidence assignments; reasoning chains absent |
| **C-N3 — Signal Validation** | Validates inference outputs against confidence thresholds before downstream release | Every output passes validation gate before downstream release; failed validations never suppressed | Outputs reaching Execution Layer without validation status |
| **C-N4 — Output Calibration** | Calibrates validated outputs for consumption context without altering inference integrity | Calibration preserves inference integrity; distortion events logged and corrected | Calibration alters inference record without logging |
| **C-N5 — Knowledge Boundary Management** | Declares and enforces the limits of reliable knowledge across active domains | Every active domain has declared boundaries; overreach events flagged and quarantined | Domains active without declared boundaries |

### RGI-8 Applicability

Perception-domain and Synthesis-domain Steer grants must monitor source-fidelity and output-fidelity, respectively. A continuously-reweighted Perception or Synthesis grant can drift toward unauthorized sources or output classes gradually.

### CDT-7 / CTAM / CAM-5 Mapping

| Domain | AICA-5 Nodes | CTAM Tier Example |
| :---- | :---- | :---- |
| Perception | C-N1, C-N3, C-N5 | Tier 3: All sources authorized |
| Synthesis | C-N2, C-N4 | Tier 3: All generation types |

---

## SECTION 3: LAYER 2 — EXECUTION LAYER (WORKFLOW ORCHESTRATION)

### Function

Decomposes tasks, orchestrates multi-agent pipelines, governs concurrency, and maintains continuous monitoring loops across all active workflows.

### Failure Mode — Pipeline Fragmentation

Parallelized execution produces conflicting intermediate states that cannot be reconciled downstream. Monitoring loops fail to detect divergence until a terminal conflict surfaces.

### Validity Condition

All active pipelines have a declared orchestration owner, reconcilable intermediate states, and active monitoring coverage. No pipeline runs without exception handling assigned.

### Nodes

| Node | Function | Validity Condition | Failure Mode |
| :---- | :---- | :---- | :---- |
| **E-N1 — Task Decomposition** | Breaks objectives into discrete, assignable, and trackable execution units | Every pipeline has declared scope boundaries, dependency maps, assignment owners, and completion criteria | Pipelines activated without clearance records |
| **E-N2 — Pipeline Orchestration** | Governs sequencing, handoff logic, and state reconciliation across pipelines | Every active pipeline has declared orchestration owner; state reconciliation events logged | Pipelines without owners; deadlocks unresolved |
| **E-N3 — Concurrency Governance** | Governs parallel execution eligibility, conflict detection, and merge protocols | Every parallel set has authorization record; state isolation declared; merge protocol assigned | Parallel sets active without authorization |
| **E-N4 — Monitoring Loops** | Maintains real-time visibility across all active pipelines | Every active pipeline has declared monitoring coverage; blind spots named and assigned | Pipeline types active without monitoring coverage |
| **E-N5 — Exception Handling** | Governs classification, containment, and escalation of execution anomalies | Every exception classified within threshold; no exception propagates without classification | Exceptions propagating to Authority Layer without classification records |

### Boundary to Authority Layer (E-N5 → A-N1)

This is the highest-consequence boundary in the architecture. E-N5's exception propagation failure is precisely what A-N1's trigger rights should reject as unauthorized initiation. This is the boundary where most enterprise AI scaling failures enter the cascade.

**Dual Custody:** E-N5 (exit node) and A-N1 (entry node) jointly govern this boundary. E-N5 must classify and contain; A-N1 must reject triggers from uncontained exceptions.

---

## SECTION 4: LAYER 3 — AUTHORITY LAYER (DECISION RIGHTS ARCHITECTURE)

### Function

Governs who can trigger actions, which outputs are binding, where human override is required, how authority is escalated, and the boundaries of delegated decision rights across the system.

### Failure Mode — Ungoverned Execution State

Actions are triggered without valid authority mapping. Binding thresholds are absent or ambiguous, producing execution that no human principal has authorized and no override protocol can intercept.

### Validity Condition

Every executable action has a declared trigger right, binding status, and escalation path. No action proceeds without traceable authority assignment.

### Nodes

| Node | Function | Validity Condition | Failure Mode |
| :---- | :---- | :---- | :---- |
| **A-N1 — Trigger Rights** | Declares and enforces who or what may initiate executable actions | Every action class has declared trigger rights; enforcement mechanism active | Action classes active without trigger rights declarations |
| **A-N2 — Binding Thresholds** | Declares which outputs carry enforceable downstream consequence | Every output class has declared binding status, consequence scope, and external fitness declaration | Output classes produced without binding declarations |
| **A-N3 — Override Protocols** | Governs conditions and mechanisms for human override of agent outputs | Override mechanisms tested and reachable by non-technical principal; state preservation functional | Override mechanisms untested or unreachable |
| **A-N4 — Escalation Paths** | Governs routing of decisions and exceptions exceeding current authority levels | Escalation paths tested; authority chain available; default actions declared | Escalation paths untested; default actions absent |
| **A-N5 — Delegation Boundaries** | Governs scope, duration, and revocation of delegated authority | Every active delegation has declared scope, duration, and revocation triggers; creep detection active | Delegations without scope or duration; creep detection unresolved |

### RGI-8 Applicability

Decision-domain Steer grants are the highest-risk category. Continuous monitoring of decision-character drift is mandatory. Drift detection thresholds must be declared and enforced. A Steer-mode signal's output may not be used as input to a live Adaptation-domain grant (Tier 4+) without passing through a fresh Declaration Binding event (RGI-8 1.6 Adaptation Firewall).

### CDT-7 / CTAM / CAM-5 Mapping

| Domain | AICA-5 Nodes | CTAM Tier Example |
| :---- | :---- | :---- |
| Decision | A-N1, A-N2, A-N3, A-N4, A-N5 | Tier 3: Autonomous (guardrails) |
| Constraint | A-N1, A-N2, A-N3 | Tier 3: Permission enforcement \+ abort |

---

## SECTION 5: LAYER 4 — CONTINUITY LAYER (STATE VALIDITY AND DRIFT CONTROL)

### Function

Establishes and maintains valid system state across agent handoffs, approval cycles, and workflow transitions. Prevents agentic divergence through drift detection, expiry logic, and context restoration.

### Failure Mode — Agentic Divergence

System state becomes invalid between handoffs — through context drift, expired approvals, or corrupted state transfer — and execution continues on a false continuity assumption without detection.

### Validity Condition

Every active workflow has a declared state, a current approval validity window, and a confirmed handoff integrity record. Drift detection is live across all agent transitions.

### Nodes

| Node | Function | Validity Condition | Failure Mode |
| :---- | :---- | :---- | :---- |
| **Co-N1 — State Establishment** | Governs formal baseline declaration at workflow initiation | Every workflow has valid baseline record before first execution step | Workflows initiated without baseline records |
| **Co-N2 — Drift Detection** | Monitors active state against declared baselines continuously | Every active workflow enrolled in drift surveillance; cumulative deviation tracked | Workflows not enrolled in surveillance; silent drift undetected |
| **Co-N3 — Approval Expiry** | Governs time-bounded validity of authorizations and approvals | Every active approval has valid expiry window; proximity alerts trigger reauthorization | Workflows continuing under lapsed approvals |
| **Co-N4 — Handoff Integrity** | Governs completeness of state transfer at every transition point | Every handoff has complete state transfer records and receiving party confirmation | Decisions made under truncated handoff state |
| **Co-N5 — Context Restoration** | Governs recovery of valid operational context after disruption | Every resumption has restoration clearance; false resumption detection active | Workflows resuming without clearance records |

### Boundary to Accountability Layer (Co-N5 → Ac-N1)

Co-N5 must detect false resumption and halt; Ac-N1 must record detection event in decision lineage.

**Dual Custody:** Co-N5 (exit node) and Ac-N1 (entry node) jointly govern this boundary. Co-N5 must detect and halt false resumption; Ac-N1 must record the detection event.

### RGI-8 Applicability

A Steer-mode flag on any cell requires Observability at minimum one tier above what the same domain/tier combination would require under Gate mode (RGI-8 1.8 Steer Observability Premium). Drift detection is the primary mechanism for Steer-mode continuous monitoring.

---

## SECTION 6: LAYER 5 — ACCOUNTABILITY LAYER (AUDIT, LIABILITY, AND LEARNING)

### Function

Maintains traceable decision lineage, attributes responsibility across agent and human actors, validates outcomes against intent, and integrates learning back into the architecture through structured correction pathways.

### Failure Mode — Lineage Collapse

A decision chain cannot be reconstructed after the fact — because attribution was never recorded, rollback pathways were absent, or outcome validation was never triggered. The system cannot learn from or correct its own failures.

### Validity Condition

Every decision has a traceable lineage record, a responsible actor attribution, and a declared outcome validation trigger. Rollback pathways are pre-defined before execution begins, not after failure occurs.

### Nodes

| Node | Function | Validity Condition | Failure Mode |
| :---- | :---- | :---- | :---- |
| **Ac-N1 — Decision Lineage** | Maintains immutable causal record of every decision | Every decision has complete lineage record (inputs, authority, executor, state context, timestamp) | Gap alerts suppressed; binding decisions without lineage |
| **Ac-N2 — Responsibility Attribution** | Assigns responsibility across agent and human actors by accountability dimension | Every decision has complete attribution (authorization, execution, oversight) | Ambiguous multi-actor assignments; external disclosures without attribution |
| **Ac-N3 — Outcome Validation** | Governs systematic comparison of outcomes against declared intent | Validation criteria declared at workflow initiation; cycles completed on schedule | Validation cycles deferred; criteria declared after outcome known |
| **Ac-N4 — Rollback Pathways** | Governs pre-defined correction and reversal protocols for binding decisions | Rollback pathways pre-defined before execution; continuity impact assessed before execution | Rollback triggered without continuity impact assessment |
| **Ac-N5 — Learning Integration** | Governs integration of validation findings back into architecture evolution | All above-threshold findings have learning artifacts; artifacts integrated within declared window | Learning artifacts unintegrated; architecture updates untraceable |

### Keystone Node Status

| Node | Status | Why |
| :---- | :---- | :---- |
| **Ac-N5 — Learning Integration** | ★ Keystone | The only bidirectional node in the architecture. Every other node's downstream effects move forward through the cascade. Learning Integration feeds back upstream into the Cognitive Layer. It is the architecture's only self-correction mechanism. |

---

## SECTION 7: THE THREE KEYSTONE NODES

Across the 25-node architecture, three nodes carry disproportionate cross-layer consequence:

| Keystone Node | Function | Why It Is Keystone |
| :---- | :---- | :---- |
| **A-N1 — Trigger Rights** | Authorization origin point | Its failure cascades into every downstream layer simultaneously. There is no recovery pathway for any layer that does not trace back through A-N1. |
| **Co-N1 — State Establishment** | Baseline declaration | The only node whose valid state is required by all four subsequent layers before they can establish their own baselines. Without a declared baseline, drift detection, approval expiry, handoff integrity, and context restoration have no reference frame. |
| **Ac-N5 — Learning Integration** | Self-correction mechanism | The only bidirectional node in the architecture. Feeds back upstream into the Cognitive Layer. A system with Ac-N5 at its lowest maturity state is not just ungoverned; it is ungovernable over time. |

---

## SECTION 8: THE CASCADE FAILURE ARGUMENT

### The Entry Point That Produces the Most Consequential Cascade

The Authority Layer. An organization that has invested heavily in Cognitive and Execution capability — and neglected Authority mapping — has built the most dangerous configuration: high-speed execution with no institutional intercept capacity.

### The Cascade

1. Cognitive Layer failure (unvalidated output) → Execution consumes it  
2. Execution Layer failure (unclassified exception) → Authority cannot authorize unclassified actions  
3. Authority Layer failure (A-N1 missing) → Continuity has no baseline  
4. Continuity Layer failure (baseline missing) → Accountability inherits corrupted state  
5. Accountability Layer failure (Ac-N5 missing) → No learning → Cognitive layer doesn't improve → the cascade repeats

### The Cascade Entry Map

Each layer transition has a declared exit node and entry node under "dual custody":

| Boundary | Exit Node | Entry Node |
| :---- | :---- | :---- |
| Cognitive → Execution | C-N3 (Signal Validation) | E-N1 (Task Decomposition) |
| Execution → Authority | E-N5 (Exception Handling) | A-N1 (Trigger Rights) |
| Authority → Continuity | A-N5 (Delegation Boundaries) | Co-N1 (State Establishment) |
| Continuity → Accountability | Co-N5 (Context Restoration) | Ac-N1 (Decision Lineage) |

**The Execution → Authority boundary (E-N5 → A-N1) is the highest-consequence boundary.** E-N5's exception propagation failure is precisely what A-N1's trigger rights should reject as unauthorized initiation. This is the boundary where most enterprise AI scaling failures enter the cascade.

---

## SECTION 9: EXTERNAL BOUNDARY MULTI-TYPE CUSTODY

AICA-5's external boundary governance model is output-class specific. Each output class has a declared terminal node, binding category, and consequence of failure. All external outputs carry a fitness declaration from their terminal node before crossing the boundary.

| External Boundary | Terminal Node | Binding Category | Consequence of Failure |
| :---- | :---- | :---- | :---- |
| Capital decision | A-N2 Binding Thresholds | Commitment binding | Unauthorized resource deployment |
| Regulatory / audit | Ac-N1 Decision Lineage | Evidentiary binding | Non-compliance, enforcement exposure |
| Client disclosure | Ac-N2 Responsibility Attribution | Informational binding | Misrepresentation, trust failure |
| Holdco governance | A-N2 \+ Ac-N2 jointly | Commitment \+ attribution | Unauthorized commitment without accountability |
| Crisis / emergency | A-N4 Escalation Paths | Authority binding | Uncontrolled failure without principal intercept |

**Scope:** The terminal node map is extensible by output class. New output classes require a declared terminal node, binding category, and consequence-of-failure specification before activation. Undesignated output classes default to Ac-N3 (Outcome Validation) with provisional binding status, expiring after three governance cycles.

---

## SECTION 10: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| ICC-8 | Constitutional parent — AICA-5 operationalizes I1-I8 |
| CDT-7/CTAM/CAM-5 | Capability taxonomy — AICA-5 operationalizes grants |
| RGI-8 | Runtime execution mode — consumes Steer flag |
| AWOF | Workforce governance — agents operate under AICA-5 control nodes |
| ADTEP | Technical enforcement — enforces AICA-5 constraints at session level |
| HAN/HOF/HIS-12 | Human authority — AICA-5 defines control nodes; HAN holds authority |
| HAWI | Workforce integration — AICA-5 control nodes map to role competencies |
| IMP | Memory — AICA-5 nodes log to IMP objects |
| DEP | Evolution — AICA-5 amendments require DEP process |

---

## SECTION 11: CFL-V VALIDATION RULES

**Rule 1 — Cognitive Validity:** C-N3 blocks outputs below confidence threshold. No output reaches Execution without validation status.

**Rule 2 — Execution Validity:** E-N1 clearance records for all pipelines. No pipeline runs without exception handling assigned.

**Rule 3 — Authority Validity:** A-N1 trigger rights for all action classes. No action proceeds without traceable authority assignment.

**Rule 4 — Continuity Validity:** Co-N1 baseline records for all workflows. Every active workflow enrolled in drift surveillance.

**Rule 5 — Accountability Validity:** Ac-N1 lineage records for all decisions. Ac-N5 learning integration active.

**Rule 6 — Keystone Node Validity:** A-N1, Co-N1, Ac-N5 at minimum Level 3 maturity.

**Rule 7 — Boundary Validity:** All four internal boundaries have dual custody operational (C-N3→E-N1, E-N5→A-N1, A-N5→Co-N1, Co-N5→Ac-N1).

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| AICA-5 v1.0 | Initial 5-layer, 25-node architecture |
| AICA-5 v1.1 | Maturity Grid, Operating Model, Implementation Pathway, Measurement Framework |
| AICA-5 v2.0 | Complete rebuild — reconciliation with CDT-7, CTAM, CAM-5, ICC-8, and RGI-8; expanded cascade argument; keystone node status; boundary dual custody; CFL-V validation rules |

---

## The One-Sentence Summary

> *"AICA-5 v2.0 is a 5-layer, 25-node control architecture — Cognitive (C-N1–5), Execution (E-N1–5), Authority (A-N1–5), Continuity (Co-N1–5), and Accountability (Ac-N1–5) — with three keystone nodes (A-N1, Co-N1, Ac-N5), four internal boundary dual-custody pairs, explicit RGI-8 mapping, and CFL-V validation rules that ensure no layer is granted without the governance capability of the layer below it."*
