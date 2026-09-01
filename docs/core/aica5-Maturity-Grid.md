# AICA-5 Maturity Grid v2.0

**Status:** Built — v2.0 (Reconciliation with AICA-5, AITOS, and Measurement Framework) **Type:** Diagnostic Instrument **Parent Stack:** AICA-5 (Control Architecture) **Version:** 2.0 — Supersedes AICA-5 Maturity Grid v1.0

---

## PREAMBLE

The AICA-5 Maturity Grid is a 25-node, five-level diagnostic instrument assessing intelligence governance maturity across all control nodes. It answers: *How mature is each control node in the AICA-5 architecture?*

The Maturity Grid is the foundation of the AICA-5 Implementation Pathway. It provides the baseline from which an organization's governance journey begins. It is not a performance metric — it is a structural diagnostic. A high score does not mean "good governance." It means "the governance architecture exists and is operational."

The Maturity Grid is built from the validity conditions of each AICA-5 node. Each node's maturity is assessed independently across five levels. No averaging across nodes. No averaging across layers. The lowest-scored node determines the layer's entry point in the implementation pathway.

---

## SECTION 1: MATURITY LEVEL DEFINITIONS

| Level | Name | Definition |
| :---- | :---- | :---- |
| **0** | Absent | Governance mechanism does not exist. No evidence of implementation. |
| **1** | Initial | Governance mechanism exists in documentation but is not operational. Policy statements without enforcement. |
| **2** | Defined | Governance mechanism is defined and operational in some areas but not consistently enforced. Partial coverage. |
| **3** | Operational | Governance mechanism is fully operational and enforced across all relevant areas. Documentation and enforcement match. |
| **4** | Measured | Governance mechanism is operational, enforced, and its effectiveness is measured and tracked over time. |
| **5** | Adaptive | Governance mechanism self-updates based on its own telemetry — not when a practitioner updates it manually. |

---

## SECTION 2: SCORING PRINCIPLES

| Principle | Definition |
| :---- | :---- |
| **Node Independence** | Each of the 25 nodes is scored independently. A high score on one node does not compensate for a low score on another. |
| **Layer Entry** | An organization's implementation phase is determined by the lowest-scored upstream layer. A Level 4 Accountability layer built on a Level 1 Authority layer does not enter at Phase 4\. It enters at Phase 2\. |
| **Evidence-Based** | Scoring is based on evidence, not documentation. A policy document is evidence of intent, not evidence of function. A trigger rights map in a policy document that is not enforced operationally scores Level 2 — not Level 3\. |
| **Behavioral vs. Document-Based** | Documentation of intent is not evidence of maturity. The mechanism must act on its own telemetry for Level 5 — not when a practitioner updates it manually. |

---

## SECTION 3: LAYER 1 — COGNITIVE LAYER (C-N1 TO C-N5)

### C-N1 — Intelligence Sourcing

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No source credentialing process | No source registry |
| 1 | Source credentialing documented | Policy document exists |
| 2 | Source credentialing defined for some sources | Partial registry |
| 3 | All sources credentialed before ingestion | Complete registry; refresh cycle defined |
| 4 | Credential status tracked and reported | Metrics on source currency |
| 5 | Source registry self-updates based on contamination flags | Automated source validation |

---

### C-N2 — Inference Architecture

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No reasoning chain logging | No inference records |
| 1 | Reasoning chains documented in some cases | Ad-hoc logging |
| 2 | Reasoning chains logged for some output types | Partial logging |
| 3 | All inference outputs have complete reasoning chains | Complete logging; confidence differentiation |
| 4 | Reasoning chain quality measured and tracked | Metrics on chain completeness |
| 5 | Inference architecture self-adjusts based on quality metrics | Automated inference improvement |

---

### C-N3 — Signal Validation

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No validation gate | Outputs reach downstream without validation |
| 1 | Validation gate documented | Policy document exists |
| 2 | Validation gate defined but logs without blocking | Partial enforcement |
| 3 | Validation gate blocks outputs below threshold | Full enforcement |
| 4 | Validation gate performance measured | Metrics on pass rate, false positives |
| 5 | Validation thresholds self-adjust based on downstream outcomes | Adaptive thresholds |

---

### C-N4 — Output Calibration

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No calibration process | All outputs treated identically |
| 1 | Calibration documented | Policy document exists |
| 2 | Calibration defined for some contexts | Partial calibration |
| 3 | Calibration applied to all outputs for context | Full calibration |
| 4 | Calibration distortion measured | Metrics on calibration fidelity |
| 5 | Calibration self-adjusts based on consumption feedback | Adaptive calibration |

---

### C-N5 — Knowledge Boundary Management

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No knowledge boundaries | Domains active without boundaries |
| 1 | Boundaries documented | Policy document exists |
| 2 | Boundaries defined for some domains | Partial boundaries |
| 3 | All active domains have declared boundaries | Complete boundaries; overreach detection |
| 4 | Boundary adherence measured | Metrics on overreach events |
| 5 | Boundaries self-adjust based on overreach patterns | Adaptive boundaries |

---

## SECTION 4: LAYER 2 — EXECUTION LAYER (E-N1 TO E-N5)

### E-N1 — Task Decomposition

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No task decomposition process | Pipelines activated without clearance |
| 1 | Decomposition documented | Policy document exists |
| 2 | Decomposition defined for some pipelines | Partial clearance |
| 3 | All pipelines have clearance records | Full clearance; completion criteria defined |
| 4 | Decomposition quality measured | Metrics on clearance completeness |
| 5 | Decomposition self-optimizes based on pipeline outcomes | Adaptive decomposition |

---

### E-N2 — Pipeline Orchestration

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No orchestration ownership | Pipelines without owners |
| 1 | Orchestration documented | Policy document exists |
| 2 | Orchestration defined for some pipelines | Partial ownership |
| 3 | All pipelines have declared owners and state reconciliation | Full orchestration |
| 4 | Orchestration effectiveness measured | Metrics on deadlocks, handoff failures |
| 5 | Orchestration self-adjusts based on pipeline performance | Adaptive orchestration |

---

### E-N3 — Concurrency Governance

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No concurrency governance | Parallel sets active without authorization |
| 1 | Concurrency documented | Policy document exists |
| 2 | Concurrency defined for some parallel sets | Partial authorization |
| 3 | All parallel sets have authorization records | Full concurrency governance |
| 4 | Concurrency effectiveness measured | Metrics on collision events |
| 5 | Concurrency self-adjusts based on conflict patterns | Adaptive concurrency |

---

### E-N4 — Monitoring Loops

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No monitoring | Pipelines active without coverage |
| 1 | Monitoring documented | Policy document exists |
| 2 | Monitoring defined for some pipelines | Partial coverage |
| 3 | All pipelines have monitoring coverage | Full coverage; blind spots assigned |
| 4 | Monitoring effectiveness measured | Metrics on coverage completeness |
| 5 | Monitoring self-adjusts based on detection patterns | Adaptive monitoring |

---

### E-N5 — Exception Handling

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No exception handling | Exceptions propagate without classification |
| 1 | Exception handling documented | Policy document exists |
| 2 | Exception handling defined for some exceptions | Partial classification |
| 3 | All exceptions classified and contained | Full exception handling |
| 4 | Exception handling effectiveness measured | Metrics on classification latency |
| 5 | Exception handling self-adjusts based on exception patterns | Adaptive exception handling |

---

## SECTION 5: LAYER 3 — AUTHORITY LAYER (A-N1 TO A-N5)

### A-N1 — Trigger Rights

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No trigger rights | Action classes active without declarations |
| 1 | Trigger rights documented | Policy document exists |
| 2 | Trigger rights defined for some action classes | Partial declarations |
| 3 | All action classes have declared trigger rights | Full declarations; enforcement active |
| 4 | Trigger rights coverage measured | Metrics on coverage completeness |
| 5 | Trigger rights self-audit for coverage gaps | Adaptive trigger rights |

★ **Keystone Node:** A-N1 is the authorization origin point. Its failure cascades into every downstream layer simultaneously.

---

### A-N2 — Binding Thresholds

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No binding thresholds | Outputs produced without declarations |
| 1 | Binding thresholds documented | Policy document exists |
| 2 | Binding thresholds defined for some output classes | Partial declarations |
| 3 | All output classes have declared binding thresholds | Full declarations; external fitness declaration |
| 4 | Binding threshold coverage measured | Metrics on declaration completeness |
| 5 | Binding thresholds self-audit for coverage gaps | Adaptive binding thresholds |

---

### A-N3 — Override Protocols

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No override mechanisms | Override unreachable |
| 1 | Override documented | Policy document exists |
| 2 | Override defined but not tested | Partial readiness |
| 3 | Override tested by non-technical principal | Full readiness |
| 4 | Override effectiveness measured | Metrics on override invocation |
| 5 | Override self-tests on schedule | Adaptive override testing |

---

### A-N4 — Escalation Paths

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No escalation paths | Escalations untested |
| 1 | Escalation paths documented | Policy document exists |
| 2 | Escalation paths defined but not tested | Partial readiness |
| 3 | Escalation paths tested; default actions declared | Full readiness |
| 4 | Escalation effectiveness measured | Metrics on escalation resolution |
| 5 | Escalation self-adjusts based on resolution patterns | Adaptive escalation |

---

### A-N5 — Delegation Boundaries

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No delegation boundaries | Delegations without scope |
| 1 | Delegation boundaries documented | Policy document exists |
| 2 | Delegation boundaries defined for some delegations | Partial boundaries |
| 3 | All delegations have declared scope, duration, revocation | Full boundaries; creep detection active |
| 4 | Delegation creep measured | Metrics on creep events |
| 5 | Delegation boundaries self-adjust based on creep patterns | Adaptive boundaries |

---

## SECTION 6: LAYER 4 — CONTINUITY LAYER (Co-N1 TO Co-N5)

### Co-N1 — State Establishment

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No state baselines | Workflows without baselines |
| 1 | State baselines documented | Policy document exists |
| 2 | State baselines defined for some workflows | Partial baselines |
| 3 | All workflows have valid baseline records | Full baselines |
| 4 | Baseline completeness measured | Metrics on baseline coverage |
| 5 | Baselines self-establish on workflow initiation | Adaptive baselines |

★ **Keystone Node:** Co-N1 is the only node whose valid state is required by all four subsequent layers. Without a declared baseline, drift detection, approval expiry, handoff integrity, and context restoration have no reference frame.

---

### Co-N2 — Drift Detection

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No drift detection | Workflows unenrolled; drift undetected |
| 1 | Drift detection documented | Policy document exists |
| 2 | Drift detection defined for some workflows | Partial enrollment |
| 3 | All workflows enrolled in drift surveillance | Full enrollment; cumulative tracking |
| 4 | Drift detection effectiveness measured | Metrics on detection rate |
| 5 | Drift detection self-adjusts based on drift patterns | Adaptive drift detection |

---

### Co-N3 — Approval Expiry

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No approval expiry | Approvals never expire |
| 1 | Approval expiry documented | Policy document exists |
| 2 | Approval expiry defined for some approvals | Partial expiry |
| 3 | All approvals have declared expiry windows | Full expiry; proximity alerts |
| 4 | Approval expiry effectiveness measured | Metrics on lapsed approvals |
| 5 | Approval expiry self-adjusts based on reauthorization patterns | Adaptive expiry |

---

### Co-N4 — Handoff Integrity

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No handoff integrity | Truncated handoffs accepted |
| 1 | Handoff integrity documented | Policy document exists |
| 2 | Handoff integrity defined for some handoffs | Partial integrity |
| 3 | All handoffs have complete state transfer and confirmation | Full integrity |
| 4 | Handoff integrity effectiveness measured | Metrics on truncated handoffs |
| 5 | Handoff integrity self-adjusts based on handoff patterns | Adaptive handoff integrity |

---

### Co-N5 — Context Restoration

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No context restoration | False resumptions proceed |
| 1 | Context restoration documented | Policy document exists |
| 2 | Context restoration defined for some resumptions | Partial restoration |
| 3 | All resumptions have restoration clearance | Full restoration |
| 4 | Context restoration effectiveness measured | Metrics on false resumptions |
| 5 | Context restoration self-adjusts based on resumption patterns | Adaptive restoration |

---

## SECTION 7: LAYER 5 — ACCOUNTABILITY LAYER (Ac-N1 TO Ac-N5)

### Ac-N1 — Decision Lineage

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No decision lineage | Decisions without records |
| 1 | Decision lineage documented | Policy document exists |
| 2 | Decision lineage defined for some decisions | Partial lineage |
| 3 | All decisions have complete lineage records | Full lineage; gap detection |
| 4 | Lineage completeness measured | Metrics on lineage coverage |
| 5 | Lineage self-audits for gaps | Adaptive lineage |

---

### Ac-N2 — Responsibility Attribution

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No attribution | Decisions without attribution |
| 1 | Attribution documented | Policy document exists |
| 2 | Attribution defined for some decisions | Partial attribution |
| 3 | All decisions have complete attribution | Full attribution; external fitness declaration |
| 4 | Attribution completeness measured | Metrics on attribution coverage |
| 5 | Attribution self-audits for ambiguity | Adaptive attribution |

---

### Ac-N3 — Outcome Validation

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No outcome validation | Validation cycles absent |
| 1 | Outcome validation documented | Policy document exists |
| 2 | Outcome validation defined for some decision classes | Partial validation |
| 3 | All decisions have declared validation criteria and cycles | Full validation |
| 4 | Validation effectiveness measured | Metrics on validation adherence |
| 5 | Validation self-adjusts based on outcome patterns | Adaptive validation |

---

### Ac-N4 — Rollback Pathways

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No rollback pathways | Rollbacks untested |
| 1 | Rollback pathways documented | Policy document exists |
| 2 | Rollback pathways defined but not tested | Partial readiness |
| 3 | Rollback pathways pre-defined and tested | Full readiness; continuity impact assessment |
| 4 | Rollback effectiveness measured | Metrics on rollback success |
| 5 | Rollback self-tests on schedule | Adaptive rollback testing |

---

### Ac-N5 — Learning Integration

| Level | Definition | Evidence |
| :---- | :---- | :---- |
| 0 | No learning integration | Findings unintegrated |
| 1 | Learning integration documented | Policy document exists |
| 2 | Learning integration defined for some findings | Partial integration |
| 3 | All above-threshold findings have learning artifacts and updates | Full integration; Cognitive Layer corrections |
| 4 | Learning integration effectiveness measured | Metrics on integration latency |
| 5 | Learning integration self-executes on validation findings | Adaptive learning integration |

★ **Keystone Node:** Ac-N5 is the only bidirectional node in the architecture. It is the architecture's only self-correction mechanism.

---

## SECTION 8: SCORING RULES

| Rule | Definition |
| :---- | :---- |
| **No Averaging** | Each node is scored independently. No averaging across nodes. No averaging across layers. |
| **Lowest-Score Entry** | An organization's implementation phase is determined by the lowest-scored upstream layer. |
| **Evidence Required** | Scoring is based on evidence, not documentation. A policy document is evidence of intent, not evidence of function. |
| **Documentation ≠ Function** | A trigger rights map in a policy document that is not enforced operationally scores Level 2 — not Level 3\. |
| **Level 5 Requirement** | The mechanism must act on its own telemetry — not when a practitioner updates it manually. |

---

## SECTION 9: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| AICA-5 | Provides the nodes being assessed |
| AITOS | Provides the implementation pathway |
| AICA-5 Measurement Framework | Provides continuous tracking of maturity |
| AICA-5 Implementation Pathway | Uses Maturity Grid as entry point |

---

## SECTION 10: CFL-V VALIDATION RULES

**Rule 1 — No Averaging:** Each node is scored independently.

**Rule 2 — Lowest-Score Entry:** Implementation phase determined by lowest-scored upstream layer.

**Rule 3 — Evidence Required:** Scoring based on evidence, not documentation.

**Rule 4 — Level 5 Autonomy:** Mechanism must self-update based on its own telemetry.

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| AICA-5 Maturity Grid v1.0 | Initial 25-node, five-level diagnostic |
| AICA-5 Maturity Grid v2.0 | Complete rebuild — reconciliation with AICA-5, AITOS, and Measurement Framework; expanded maturity level definitions; keystone node status; CFL-V validation rules |

---

## The One-Sentence Summary

> *"The AICA-5 Maturity Grid v2.0 assesses each of the 25 control nodes across five levels — Absent, Initial, Defined, Operational, Measured, Adaptive — with no averaging across nodes, evidence-based scoring, and the principle that documentation of intent is not evidence of function, determining an organization's entry point into the AICA-5 Implementation Pathway."*
