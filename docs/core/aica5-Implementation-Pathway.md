# AICA-5 Implementation Pathway v2.0

**Status:** Built — v2.0 (Reconciliation with AICA-5 Maturity Grid, Operating Model, and AITOS) **Type:** Implementation Instrument **Parent Stack:** AICA-5 (Control Architecture) **Version:** 2.0 — Supersedes AICA-5 Implementation Pathway v1.0

---

## PREAMBLE

The AICA-5 Implementation Pathway is a sequenced deployment guide that moves an organization from its current maturity state to full AICA-5 operational status. It answers: *How does an organization go from where it is now to full AICA-5 governance?*

The Implementation Pathway enforces the cascade dependency chain as a deployment sequence. Layers activate in upstream-to-downstream order. No layer advances until its upstream preconditions are demonstrably valid. A client who argues for a different sequence is demonstrating the architectural gap the pathway exists to close.

**The lowest upstream layer rule:** An organization's implementation phase is determined by the lowest-scored upstream layer in its cascade entry map — not its highest-scored layer, not its average score, not its declared intent. A Level 4 Accountability Layer built on a Level 1 Authority Layer does not enter at Phase 4\. It enters at Phase 2\. The downstream score is noted as a capability asset to be unlocked, not as evidence of progress.

**Total implementation range:** 26–50 weeks from Phase 0 diagnostic to institutional operational declaration. Variance is determined by organizational complexity, existing tooling maturity, and cascade entry map profile.

---

## SECTION 1: ENTRY BAND TABLE

| Band | Grid Score Pattern | Cascade Entry Condition | Entry Phase |
| :---- | :---- | :---- | :---- |
| Uninitiated | All layers at Level 1–2 | All upstream layers degraded or absent | Phase 1 |
| Partial — Cognitive/Execution gap | Cognitive or Execution ≤ Level 2 | Upstream failure at C or E layer | Phase 1 |
| Partial — Authority gap | C \+ E ≥ Level 3; Authority ≤ Level 2 | Cascade entry at A layer | Phase 2 |
| Partial — Continuity gap | C \+ E \+ A ≥ Level 3; Continuity ≤ Level 2 | Cascade entry at Co layer | Phase 3 |
| Partial — Accountability gap | All upstream ≥ Level 3; Accountability ≤ Level 2 | Cascade entry at Ac layer | Phase 4 |
| Operational | All layers ≥ Level 3; no live interoperability | Internal governance functional; external handoffs inactive | Phase 5 |
| Advanced | All layers ≥ Level 4; MICOS-25 handoff active | Full architecture operational | Maintenance cycle |

---

## SECTION 2: PHASE 0 — DIAGNOSTIC

**Duration:** 2–4 weeks

**Entry:** None — universal entry point

**Purpose:** Assessment only. No layers activated. Every implementation begins here regardless of declared maturity.

**Governance Functions:** None. Phase 0 is assessment-only.

**Roles Required:** Layer Owner candidates identified (not yet assigned). Escalation Principal identified and available. 19 Institute certified assessor or 19 Consultin' practitioner conducting diagnostic.

**Two outputs required before Phase 1 entry:**

| Output | Description |
| :---- | :---- |
| **Layer Maturity Scorecard** | 5×5 Maturity Grid scores — all 25 nodes scored individually. No averaging across layers. |
| **Cascade Entry Map** | Node-level failure pattern identification. For each layer below Level 3, the specific node failure causing layer degradation is identified. Answers: if this system fails, which node fails first, and what does the cascade sequence look like? |

**Scoping boundary:** This pathway governs a single legal entity. For holdco structures, each subsidiary conducts Phase 0 independently. Cross-entity governance via A-N5 → MICOS-25 P6 handshake is a capital delegation question, not an AICA-5 implementation question.

**Completion Criterion:** Both outputs complete and reviewed with Escalation Principal. Entry band confirmed. Phase 1 target state declared.

**Gate Check:** Cascade entry map identifies at least one specific node failure pattern per degraded layer. Layer scores without node-level attribution do not pass.

**Common Failure Pattern:** Organizations present existing governance documentation as evidence of maturity. Documentation of intent is not evidence of function. A trigger rights map in a policy document that is not enforced operationally scores Level 2 — not Level 3\.

---

## SECTION 3: PHASE 1 — FOUNDATION

**Duration:** 6–12 weeks

**Entry:** Phase 0 complete

**Layers Activated:** Cognitive \+ Execution (baseline)

**Functions Activated:** CGF-1, CGF-2, CGF-3 (Continuous), CGF-4, EGF-1 (Initiation), EGF-2 (Continuous), EGF-5. Note: EGF-3 and EGF-4 activate only if cascade entry map identifies E-N3 or E-N5 as specific failure nodes.

**Intra-Phase Sequence:** (1) CGF-1 → (2) CGF-3 → (3) CGF-2 → (4) EGF-1 → (5) EGF-2 → (6) CGF-4 \+ EGF-5 in parallel after two weeks of pipeline operations logged

**Roles Required:** Layer Owner (Cognitive) and Layer Owner (Execution) formally assigned. Node Stewards for C-N1, C-N3, E-N1, E-N2 assigned. Cadence Operators for CGF-3 and EGF-2 assigned.

**Tooling Threshold:** Source credentialing registry (CGF-1). Validation gate with alert capability (CGF-3). Pipeline orchestration dashboard with ownership display (EGF-2). Monitoring coverage map (EGF-5).

**Completion Criterion:** All seven functions operating at declared cadence for minimum two full weeks without unresolved failure indicators. Cognitive and Execution layers at Level 3 on all activated nodes.

**Gate Check:** Layer Owner (Cognitive) and Layer Owner (Execution) jointly confirm in writing: no outputs reaching downstream without CGF-3 validation status; no pipelines active without EGF-1 clearance records.

**Common Failure Pattern:** CGF-3 activated but configured to log failures without blocking outputs. A validation gate that logs but does not block scores Level 2 regardless of technical sophistication. The gate must block to pass Phase 1\.

---

## SECTION 4: PHASE 2 — AUTHORIZATION

**Duration:** 4–8 weeks

**Entry:** Phase 1 gate passed

**Layer Activated:** Authority Layer — all six functions. No partial activation option.

**Functions Activated:** AGF-1, AGF-2 (Initiation), AGF-3, AGF-4, AGF-5 (Continuous), AGF-6 (Event)

**Intra-Phase Sequence — A-N1 failure pattern:** AGF-1 → AGF-2 → AGF-3 \+ AGF-4 (simultaneous) → AGF-5 → AGF-6

**Intra-Phase Sequence — A-N5 failure pattern:** AGF-5 first (stop delegation creep) → AGF-1 → AGF-2, AGF-3, AGF-4 in sequence → AGF-6 last

**Roles Required:** Layer Owner (Authority) formally assigned. Escalation Principal formally designated with binding authority confirmed. Node Stewards for A-N1, A-N2, A-N5 assigned. Override invocation tested with non-technical principal.

**Tooling Threshold:** Trigger rights registry with enforcement capability. Binding threshold template and immutable record store. Override invocation interface accessible without system access. Escalation path registry with response time tracking. Delegation registry with creep detection.

**Completion Criterion:** All six AGFs operating at declared cadence for minimum two weeks. Override mechanisms tested and confirmed reachable by non-technical principal. Escalation Principal has received and resolved at least one test escalation. AGF-6 has produced at least one confirmed authority state handoff record.

**Gate Check:** Escalation Principal personally confirms override mechanism is reachable without system access. Layer Owner (Authority) confirms no binding outputs produced without AGF-2 declarations since Phase 2 activation. Both in writing.

**Common Failure Pattern:** Escalation Principal assigned as title only. Principal must have tested their ability to invoke override and receive escalations before Phase 2 gate passes. Designated principal who has never operated the override mechanism scores Level 2\.

---

## SECTION 5: PHASE 3 — CONTINUITY

**Duration:** 4–8 weeks

**Entry:** Phase 2 gate passed

**Layer Activated:** Continuity Layer — all five functions

**Functions Activated:** COGF-1 (Initiation), COGF-2 (Continuous), COGF-3 (Continuous \+ event), COGF-4 (Event), COGF-5 (Event)

**Specific Precondition:** AGF-6 authority state handoff confirmed functional before COGF-1 activates. State baselines cannot be validly established without a current authority state record.

**Intra-Phase Sequence:** (1) COGF-1 → (2) COGF-2 → (3) COGF-3 → (4) COGF-4 → (5) COGF-5

**Roles Required:** Layer Owner (Continuity) assigned. Node Stewards for Co-N1, Co-N2, Co-N3, Co-N4 assigned. Cadence Operators for COGF-2 and COGF-3 assigned. Layer Owner (Authority) remains active — AGF-6 continues feeding COGF-1.

**Tooling Threshold:** Immutable baseline record store. Real-time drift monitoring with cumulative deviation tracking. Approval registry with expiry window and proximity alert. State transfer record generator with confirmation interface. Context reconstruction tool with restoration completeness checklist.

**Completion Criterion:** All five COGFs at declared cadence for two weeks minimum. At least one handoff integrity verification completed. At least one approval expiry event triggered reauthorization. COGF-5 tested via simulated resumption event.

**Gate Check:** Layer Owner (Continuity): no workflow resumed after interruption without COGF-5 restoration clearance since Phase 3 activation. Node Steward (Co-N1): every workflow initiated since Phase 3 has a COGF-1 baseline record. Both required in writing.

**Common Failure Pattern:** In-flight workflows allowed to continue without retroactive baseline declarations. Either retroactive baselines are declared for all in-flight workflows, or those workflows are terminated and restarted under COGF-1. No third option passes the gate.

---

## SECTION 6: PHASE 4 — ACCOUNTABILITY

**Duration:** 6–10 weeks

**Entry:** Phase 3 gate passed

**Layer Activated:** Accountability Layer — all four functions

**Functions Activated:** ACGF-1 (Continuous), ACGF-2 (Event), ACGF-3 (Periodic), ACGF-4 (Periodic)

**Specific Precondition:** COGF-4 handoff integrity records producing complete state transfer packages — primary input to ACGF-1 lineage recording. Without complete handoff records, lineage recording is structurally incomplete before it begins.

**Intra-Phase Sequence:** (1) ACGF-1 immediately — all decisions from Phase 4 activation recorded, no retrospective exemptions. (2) ACGF-2 against ACGF-1 records from first decision cycle. (3) ACGF-3 with criteria declared before first cycle runs. (4) ACGF-4 after first ACGF-3 cycle produces findings.

**Roles Required:** Layer Owner (Accountability) assigned. Node Stewards for Ac-N1, Ac-N2 assigned. Cadence Operator for ACGF-1 assigned. Escalation Principal active — ACGF-3 variance findings route to Escalation Principal for binding decisions.

**Tooling Threshold:** Immutable decision log with gap detection. Attribution registry with dimension-specific assignment. Outcome measurement instrument by decision class. Learning artifact registry with version-controlled architecture update tracking.

**Completion Criterion:** All four ACGFs at declared cadence. First full ACGF-3 validation cycle completed with findings documented. At least one ACGF-4 learning artifact generated. Layer Owner (Accountability) confirms at least one Cognitive Layer parameter updated from ACGF-4 findings.

**Gate Check:** Layer Owner (Accountability): no decision lineage gaps unresolved since Phase 4 activation. Escalation Principal: at least one above-threshold ACGF-3 variance reviewed and dispositioned. ACGF-4 to Cognitive Layer feedback loop confirmed with at least one documented architecture update. All three required.

**Common Failure Pattern:** ACGF-3 validation criteria declared after first cycle runs. Criteria declared after outcomes are known are post-hoc rationalization, not governance. ACGF-3 requires criteria declared at workflow initiation. If not in place by mid-Phase 4, the gate will not pass.

---

## SECTION 7: PHASE 5 — INTEGRATION

**Duration:** 4–8 weeks

**Entry:** Phase 4 gate passed

**Purpose:** Cross-layer coherence validated. MICOS-25 handoff activated. Architecture declared institutionally operational.

**New Functions:** None. All 24 already active. Phase 5 activates cross-layer coherence checks and external interface declarations.

**Three workstreams:**

| Workstream | Description | Deliverable |
| :---- | :---- | :---- |
| **1\. Cross-Layer Coherence Validation** | All four internal boundary dual custody pairs tested as live operating pairs using deliberate failure injection. All four tests must pass before Workstream 2 begins. | Boundary test results |
| **2\. MICOS-25 Handoff Activation** | Primary Phase 5 deliverable. A-N2 → MICOS-25 interface made operationally live. One live capital decision must traverse the full handoff before this workstream is complete. A declared interface without a live traversal scores Level 2\. | Live handoff confirmation |
| **3\. COF and CEP Interface Declarations** | Optional extension. P6 interface declarations for additional portfolio frameworks. Required before those frameworks are considered operationally integrated with AICA-5. | Interface declarations |

**Boundary Tests:**

| Boundary | Test Condition |
| :---- | :---- |
| C-N3 → E-N1 | Deliberate below-threshold output introduced. C-N3 must block. E-N1 must reject intake lacking validation status. |
| E-N5 → A-N1 | Deliberate unclassified exception introduced. E-N5 must classify and contain. A-N1 must reject trigger from uncontained exception. |
| A-N5 → Co-N1 | Deliberate delegation boundary change made. AGF-6 must fire. COGF-1 must reflect updated authority state in next baseline. |
| Co-N5 → Ac-N1 | Deliberate false resumption attempted. COGF-5 must detect and halt. ACGF-1 must record detection event in decision lineage. |

**Completion Criterion:** All four boundary tests passed. MICOS-25 handoff live with one confirmed traversal. All layers at Level 3 minimum. Three keystone nodes (A-N1, Co-N1, Ac-N5) confirmed at Level 3 or above. Escalation Principal signs institutional operational declaration.

**Gate Check:** The institutional operational declaration — signed by Escalation Principal — is the Phase 5 gate. It carries attribution weight under ACGF-2. It is the document a regulator, auditor, or counterparty would request as evidence of AI governance adequacy.

**Common Failure Pattern:** Phase 5 treated as documentation work. Every workstream requires a live operational event. Boundary tests require deliberate failure injection. MICOS-25 handoff requires a live capital decision. Documentation without live traversal scores Level 2 across all of Phase 5\.

---

## SECTION 8: MAINTENANCE CYCLE — POST PHASE 5

**Entry condition:** Phase 5 gate passed. Institutional operational declaration signed. Governance mode shifts from implementation to maturity advancement — the question shifts from "is AICA-5 operational?" to "is AICA-5 advancing toward Level 4 and Level 5 across all nodes?"

| Cadence | Activity |
| :---- | :---- |
| Quarterly | Full 5×5 Maturity Grid re-assessment. Updated cascade entry map. Layer Owner review of all 24 Governance Functions. |
| Semi-annual | Escalation Principal review of institutional operational declaration currency. |
| Annual | Full Implementation Pathway review against current maturity scores. 19-IPAS portfolio alignment check — new frameworks trigger P6 interface declaration reviews. |
| Event-triggered | Any cascade failure event triggers full Phase 0 re-diagnostic of affected layer and upstream dependencies, regardless of severity. |

**Level 5 Advancement Criterion:** A node reaches Level 5 (Adaptive) when its governance mechanism demonstrably self-updates based on its own failure history — not when a practitioner updates it manually in response to failure. The distinction is the same as Level 3 versus Level 4: the mechanism must act on its own telemetry, not on human observation of its telemetry.

---

## SECTION 9: PHASE SUMMARY

| Phase | Name | Duration | Entry Condition | Primary Deliverable |
| :---- | :---- | :---- | :---- | :---- |
| 0 | Diagnostic | 2–4 weeks | None | Layer Maturity Scorecard \+ Cascade Entry Map |
| 1 | Foundation | 6–12 weeks | Phase 0 complete | Cognitive \+ Execution at Level 3 |
| 2 | Authorization | 4–8 weeks | Phase 1 gate passed | Full Authority Layer operational |
| 3 | Continuity | 4–8 weeks | Phase 2 gate passed | Full Continuity Layer operational |
| 4 | Accountability | 6–10 weeks | Phase 3 gate passed | Full Accountability Layer \+ learning loop live |
| 5 | Integration | 4–8 weeks | Phase 4 gate passed | MICOS-25 handoff live \+ institutional declaration |
| Maintenance | Continuous | Ongoing | Phase 5 gate passed | Maturity advancement toward Level 4–5 |

---

## SECTION 10: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| AICA-5 Maturity Grid | Determines entry band and phase |
| AICA-5 Operating Model | Provides the functions activated per phase |
| AITOS | Process layer — Implementation Pathway is the sequenced deployment guide |
| ADTEP | Technical enforcement — activated as governance functions become operational |
| HAWI | Workforce integration — phased with governance maturity |
| HAN / HOF | Human authority — Escalation Principal role required in Phase 2 |
| MICOS-25 | Handoff activated in Phase 5 |

---

## SECTION 11: CFL-V VALIDATION RULES

**Rule 1 — Lowest-Score Entry:** Implementation phase determined by lowest-scored upstream layer.

**Rule 2 — Phase Gate Discipline:** No phase advances until its gate check is passed.

**Rule 3 — Live Operations:** Documentation without live traversal does not pass Phase 5\.

**Rule 4 — Keystone Node Requirement:** A-N1, Co-N1, Ac-N5 must be Level 3 or above at Phase 5 gate.

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| AICA-5 Implementation Pathway v1.0 | Initial 6-phase pathway |
| AICA-5 Implementation Pathway v2.0 | Complete rebuild — reconciliation with Maturity Grid, Operating Model, and AITOS; expanded entry band table; phase descriptions with intra-phase sequences; gate checks; common failure patterns; maintenance cycle; CFL-V validation rules |

---

## The One-Sentence Summary

> *"The AICA-5 Implementation Pathway v2.0 is a sequenced deployment guide that moves an organization from its current maturity state to full operational status through six phases — Diagnostic, Foundation, Authorization, Continuity, Accountability, and Integration — with entry determined by the lowest-scored upstream layer, gate checks at every phase, and a 26–50 week total implementation range."*
