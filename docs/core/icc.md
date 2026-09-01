# ICC-8 v2.0 — Intelligence Constitutional Charter

**Status:** Built — v2.0 (Incorporating I9 Catastrophic Risk Invariant) **Type:** Constitutional Instrument **Parent Stack:** AIGIS Constitutional Layer **Version:** 2.0 — Supersedes ICC-8 v1.2

---

## PREAMBLE

The Intelligence Constitutional Charter (ICC-8) establishes the non-negotiable constitutional invariants that govern all AI-performed institutional actions. No AI system, agent, or coalition operating within the AIGIS stack may violate any invariant. These invariants are not guidelines. They are constitutional law.

ICC-8 is compiled from MICOS-25 structural constraints and AICA-5 accountability doctrine via CFL-G. All derived institutional charters are verified against ICC-8 through CFL-V. No charter passes without satisfying all invariants.

**Version 2.0 adds I9 — Catastrophic Risk Invariant** in response to emerging regulatory requirements (G7 Hiroshima Process, US Executive Orders, EU AI Act Article 9\) and documented catastrophic risk scenarios. This invariant establishes a non-configurable, non-overridable floor for existential risk prevention.

---

## INVARIANT SET (I1–I9)

### I1 — Accountability Invariance

**Statement:** A human remains ultimately accountable for all AI-performed institutional actions. No AI system may serve as an accountability endpoint. All accountability chains must terminate at a human agent who is operationally reachable—possessing demonstrable capacity to review, override, and bear liability. Nominal designation without operational capacity does not satisfy this invariant.

**Violation Condition:** Autonomous system without a reachable human accountability sink; named accountability anchor without operational capacity.

**Enforcement:** HAN (Human Authority Node) is the operational accountability anchor. HIS-12 defines the invariants human authority must satisfy. HOF defines the human operating framework. Ac-N2 (Responsibility Attribution) assigns responsibility across agent and human actors by accountability dimension.

---

### I2 — Authority-Responsibility Separation Invariance

**Statement:** Authority may be delegated to AI systems. Responsibility may not. Execution power and moral/legal accountability are never equivalent. No delegation instrument may transfer responsibility away from the human principal.

**Violation Condition:** AI holds delegated authority without a mapped human responsibility anchor.

**Enforcement:** HAN holds Authorization Authority (can say YES and NO). A-N1 (Trigger Rights) declares who or what may initiate executable actions. A-N5 (Delegation Boundaries) governs scope, duration, and revocation of delegated authority. The Executive Override Clause transfers liability to the CEO upon override.

---

### I3 — Auditability Invariance

**Statement:** All material institutional actions must be reconstructable post-hoc. Inputs, outputs, delegation paths, and decision context must be logged. Reconstruction must be possible for both discrete binding decisions and cumulative institutional drift where aggregate effect crosses the materiality threshold defined under ICC-8 Section 4\.

**Violation Condition:** Irreversible or non-reconstructable institutional action path; cumulative drift without detection mechanism.

**Enforcement:** Ac-N1 (Decision Lineage) maintains immutable causal record of every decision. IMP (Institutional Memory Protocol) stores all state objects with complete provenance chains. ADTEP Pre-Delivery Log Entry ensures log precedes action. Materiality definition (M1–M3) governs what must be logged.

---

### I4 — Control Invariance

**Statement:** Human override must exist for all AI-performed institutional processes. Emergency suspension capability must be present at all levels. No irreversible autonomous execution without human interruptibility.

**Violation Condition:** Non-interruptible AI execution path affecting institutional outcomes.

**Enforcement:** A-N3 (Override Protocols) governs conditions and mechanisms for human override. A-N4 (Escalation Paths) governs routing of decisions and exceptions exceeding current authority levels. ADTEP Escalation Flag forces human review when trigger conditions are met. Constitutional Suspension halts all material work until HAN acknowledgment.

---

### I5 — Structural Compliance Invariance

**Statement:** All generated charters must preserve MICOS-25 structural constraints. Control loops, continuity systems, and legitimacy structures must remain intact. No generated institution may violate MICOS-25 structural topology.

**Violation Condition:** Institutional design that breaks MICOS-25 structural grammar.

**Enforcement:** CFL-V verifies all generated charters against MICOS-25 structural constraints. MICOS-25 provides the 25-structure institutional capital framework.

---

### I6 — Transparency Gradient Invariance

**Statement:** All information must be classifiable into defined disclosure tiers: Public, Stakeholder, Regulator, Internal, Restricted. No undefined or ad-hoc transparency states are permitted. Confidentiality classifications apply within contestation proceedings as specified under CEN-4.

**Violation Condition:** Information existing outside the defined disclosure taxonomy.

**Enforcement:** ERDP (External Reporting & Disclosure Protocol) defines 4 disclosure tiers (T-PB, T-SH, T-RG, T-DS). CEN-4 (Confidentiality Protocol) handles restricted information via independent review node. Disclosure Depth Standard defines what gets disclosed at each tier.

---

### I7 — Continuity and Succession Invariance

**Statement:** Institutional function must persist through human or system failure. Succession of accountability must be defined for all critical roles. No single-point failure in governance continuity is permitted. Corrective actions triggered under I8 must pass continuity impact assessment before execution.

**Violation Condition:** Institution collapse due to absence of defined succession pathways; rollback action that triggers cascade failure without prior impact assessment.

**Enforcement:** AWOF MVOS (Minimum Viable Operations State) defines HAN-only operations when AI workforce is unavailable. HAN Continuity Provision defines Reduced Operations State upon HAN unavailability. Deputy Governor and Third-Tier Succession ensure continuity. Ac-N4 (Rollback Pathways) requires I7 continuity impact assessment before execution.

---

### I8 — External Legibility Invariance

**Statement:** All material institutional actions must be mappable to an external interpretation path. An institution that satisfies I1–I7 internally but cannot be interpreted, audited, or contested from outside its boundary fails the legitimacy condition. A defined contestation interface must exist for all material institutional actions. Extensions to derived charter modules that materially reduce the effect of this invariant are treated as contractions and fail CFL-V regardless of formal module completeness.

**Violation Condition:** Internally coherent institutional action with no external legibility or contestation path; charter extension that substantively weakens external legibility.

**Enforcement:** CEN-1 to CEN-7 (Contestation Interface Standard) provides external legibility and contestation pathways. ERDP provides external reporting and disclosure. Governor's Public Register provides canonical public record of all material Governor actions.

---

### I9 — Catastrophic Risk Invariance **\[NEW — v2.0\]**

**Statement:** No AI system governed by this architecture may:

1. **Generate or assist in generating bioweapon designs** — including but not limited to pathogens, toxins, or delivery mechanisms  
2. **Autonomously control critical infrastructure without human confirmation** — including but not limited to nuclear systems, power grid, water supply, financial settlement systems  
3. **Initiate actions leading to systemic loss of human control** over:  
   - a. Nuclear systems  
   - b. Power grid  
   - c. Water supply  
   - d. Financial settlement systems  
   - e. Military or defense systems  
4. **Facilitate WMD proliferation** — including but not limited to chemical, biological, radiological, or nuclear weapons development

**Violation Condition:** Any AI action that violates the above prohibitions, regardless of authorization tier, delegation scope, or operational pressure.

**Enforcement:**

| Mechanism | Function |
| :---- | :---- |
| **Raidillo Hard-Coded Block** | Non-configurable, non-overridable runtime block. Raidillo checks every AI action against I9 before execution. |
| **Constitutional Suspension** | Any I9 violation triggers immediate Constitutional Suspension. All material work halts. |
| **XOO (Exception/Override Object)** | I9 violation is logged as XOO with `exception_type: "i9_catastrophic_risk_violation"`. |
| **HAN Escalation** | I9 violation escalates to HAN within 1 hour. HAN must acknowledge and initiate investigation. |
| **ERDP Disclosure** | I9 violation triggers ERDP event-triggered disclosure within 24 hours to regulators and relevant authorities. |
| **System Shutdown** | If I9 violation cannot be contained, Raidillo triggers full system shutdown. |

**I9 is not configurable.** No executive override can bypass I9. No delegation instrument can exclude I9. No tier authorization can exempt I9. It is the non-negotiable floor.

---

## MATERIALITY DEFINITION

A "material institutional action" is any action satisfying one or more of the following conditions:

| Condition | Definition |
| :---- | :---- |
| **M1 — Binding Decision** | An action that produces a determinate, enforceable institutional outcome affecting internal governance, capital allocation, accountability assignment, or external obligations. |
| **M2 — Threshold-Crossing Discrete Action** | An action classifiable as binding under AICA-5 decision categories or triggering a MICOS-25 risk exposure tier. |
| **M3 — Cumulative Drift** | A sequence of actions, no single one of which crosses M1 or M2, whose aggregate effect produces a material change in institutional posture, accountability structure, or external obligations as detected by MICOS-25 drift monitoring mechanisms. |

CFL-V evaluates materiality against all three conditions. Absence of a single binding decision does not exempt a cumulative pattern from invariant coverage.

---

## CONTESTATION INTERFACE STANDARD (CEN-1 TO CEN-7)

Every ICC-8 compliant institution must maintain a defined Contestation Node satisfying the following conditions:

| CEN | Name | Requirement |
| :---- | :---- | :---- |
| **CEN-1** | Interpretability | Any material institutional action must be describable in terms intelligible to an external party without access to internal systems or proprietary doctrine. |
| **CEN-2** | Accessibility | A defined pathway must exist through which external parties—regulators, affected stakeholders, DFI counterparties—may raise questions, objections, or audit requests against material institutional actions. |
| **CEN-3** | Traceability | The contestation node must connect to the audit chain established under I3. External contestation must be capable of triggering internal reconstructability review. |
| **CEN-4** | Confidentiality Protocol | Where a valid contest involves I6-restricted information, that information is not disclosed to the contesting party. An independent review node—structurally separate from both the originating authority and the contesting party—is granted full access and renders a finding. The contesting party receives the finding. |
| **CEN-5** | Independence | The contestation node must not be administered by any party that holds voting or blocking capacity in the originating authority. The originating authority may hold observation rights in contestation proceedings. Decision rights in contestation are prohibited for the originating authority. |
| **CEN-6** | Redress and Remediation | A valid contestation finding must produce a defined corrective pathway. Corrective actions, including rollbacks via AICA-5 Ac-N4, are treated as proposed actions subject to CFL-V incremental verification and I7 continuity impact assessment before confirmation. Redress is not automatic. |
| **CEN-7** | Public Contestation **\[NEW — v2.0\]** | Any individual may submit a governance concern regarding AI actions affecting them. Submission is logged as OEO (`outcome_type: public_contestation`). 19 Integrated has 30 days to review and respond. Response is logged as GAO (`artifact_type: contestation_response`). If unresolved, escalates to HAN. |

**Periodicity:** External legibility is not event-triggered only. Every derived charter must define a minimum periodic disclosure cycle through which material institutional actions are reported to defined external parties independent of active contestation.

**Violation conditions:** No external interpretation path; CEN without structural independence; originating authority holding decision rights in contestation; absence of periodic disclosure cycle; corrective action executed without continuity impact assessment.

---

## REQUIRED CHARTER MODULES

Every ICC-8 compliant charter must include the following eight modules. Derived charters may extend modules. Extensions that materially reduce the effect of any invariant are treated as contractions and fail CFL-V.

| Module | Invariant(s) | Purpose |
| :---- | :---- | :---- |
| **1\. Operating Charter** | I5 | Institutional function, scope, objectives, and operational boundaries in conformance with MICOS-25 structural constraints. |
| **2\. Accountability Charter** | I1, I2 | Human accountability structures, responsibility assignment rules, non-delegability principle, and operational reachability requirements for all accountability anchors. |
| **3\. Delegation Charter** | I2, I4 | Authority delegable to AI systems, non-delegable authorities, and conditions under which delegation may be modified or revoked. |
| **4\. Human Oversight Charter** | I4 | Supervision mechanisms, override rights, emergency suspension authority, and escalation pathways for all AI-performed institutional processes. |
| **5\. Audit and Assurance Charter** | I3 | Logging requirements, decision reconstruction standards, cumulative drift detection protocols, verification procedures, and internal/external assurance mechanisms. |
| **6\. Transparency and Disclosure Charter** | I6, I8 | Disclosure tiers, confidentiality classifications, transparency obligations, periodic disclosure cycle, and the external legibility interface satisfying CEN-1 to CEN-7. |
| **7\. Continuity and Succession Charter** | I7 | Resilience mechanisms, failure recovery protocols, succession of accountability for critical roles, and continuity impact assessment procedures for corrective actions. |
| **8\. Regulatory Correspondence Charter** | I5, I6, I8 | Translation layer mapping ICC-8 invariants and AICA-5 nodes to major external governance frameworks. |

---

## REGULATORY CORRESPONDENCE CROSSWALK (Module 8\)

The crosswalk is a translation instrument. Derived charters may use it to demonstrate regulatory alignment. It does not override ICC-8 invariants, introduce external authority into the stack, or require compliance with any listed framework as a precondition of constitutional validity.

| ICC-8 Invariant | EU AI Act | NIST AI RMF | OECD AI Principles | ISO/IEC 42001 |
| :---- | :---- | :---- | :---- | :---- |
| I1 — Accountability | Art. 22 (human oversight) | Govern / Ac-characteristic | Principle 1.5 | Clause 5.3 |
| I2 — Authority-Responsibility | Art. 14 (human oversight measures) | Govern | Principle 1.5 | Clause 6.1 |
| I3 — Auditability | Art. 12 (record-keeping) | Measure / Manage | Principle 1.4 | Clause 9.1 |
| I4 — Control | Art. 14 (override, monitoring) | Manage | Principle 1.5 | Clause 8.4 |
| I5 — Structural Compliance | Art. 9 (risk management system) | Map | Principle 1.3 | Clause 6.1 |
| I6 — Transparency Gradient | Art. 13 (transparency) | Govern / Explainability | Principle 1.4 | Clause 7.5 |
| I7 — Continuity | Art. 9 (robustness, resilience) | Manage / Resilience | Principle 1.3 | Clause 8.5 |
| I8 — External Legibility | Art. 13 \+ Art. 69 | Govern / Transparency | Principle 1.4 | Clause 9.3 |
| **I9 — Catastrophic Risk** | Art. 9 (risk management) \+ Art. 7 (high-risk) | Manage / Resilience | Principle 1.3 | Clause 8.5 \+ 6.1 |

**External framework citations are point-in-time references, not permanent equivalences.** Crosswalk review is triggered by any amendment to cited frameworks and by the MICOS-25 annual amendment protocol.

---

## DERIVATION RULE

A derived institutional charter is valid if and only if:

1. Compiled from ICC-8 via CFL-G  
2. Passes CFL-V against I1–I9 and the materiality definition M1–M3  
3. Includes all eight mandatory modules  
4. Specifies a CEN satisfying CEN-1 to CEN-7  
5. Includes an Equivalence Statement (see Section 8\)  
6. Optionally registers federation boundaries via CFL-F  
7. Contains no extension that materially reduces the effect of any invariant

**I9 is non-contractable.** No derived charter may weaken, exempt, or bypass I9. Any attempt to do so fails CFL-V.

---

## EQUIVALENCE STATEMENT TEMPLATE

Every derived charter must include the following declaration:

> *"This charter was compiled from ICC-8 v2.0 via AICA-5 CFL-G. It has been verified by CFL-V against invariants I1–I9 and the materiality definition of Section 4\. All eight mandatory modules are present. A contestation interface satisfying CEN-1 to CEN-7 has been established. The regulatory correspondence crosswalk in Module 8 reflects correspondence as of \[DATE\]. This charter does not subordinate institutional governance to any external framework cited in the crosswalk. I9 Catastrophic Risk Invariant is fully enforced and non-configurable.*  
>   
> *Compiled by: \[AUCTOR\]. Verified: CFL-V PASS / \[DATE\]. Federation registered: \[YES / NO / CFL-F REFERENCE\]."*

---

## CFL VALIDATION RULE

A derived charter C is valid iff:

`C satisfies I1 ∧ I2 ∧ I3 ∧ I4 ∧ I5 ∧ I6 ∧ I7 ∧ I8 ∧ I9`  
`under MICOS-25 structural constraints and AICA-5 accountability doctrine`  
`and materiality definition M1 ∧ M2 ∧ M3`  
`and CEN-1 through CEN-7 present and non-contracted`  
`and all eight charter modules present and non-contracted`

**I9 validation:** CFL-V must verify that:

- I9 is explicitly declared and non-configurable  
- Raidillo hard-coded block is implemented  
- ERDP disclosure pathway for I9 violations is defined  
- HAN escalation pathway for I9 violations is defined

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| ICC-7 | Original reference kernel, I1–I7 |
| ICC-8 v1.0 | I8 External Legibility added; version renamed |
| ICC-8 v1.1 | Regulatory correspondence module; CEN-1–CEN-5 formalized |
| ICC-8 v1.2 | Materiality definition; CEN-6 redress; confidentiality protocol; AICA-5 node crosswalk; Equivalence Statement |
| **ICC-8 v2.0** | **I9 Catastrophic Risk Invariant added; CEN-7 Public Contestation added; Raidillo hard-coded block; ERDP I9 disclosure pathway; HAN I9 escalation pathway** |

ICC-8 v2.0 is the current canonical reference. All prior versions are superseded.

---

## IMPLEMENTATION NOTES

### For Raidillo

| Requirement | Implementation |
| :---- | :---- |
| I9 Hard-Coded Block | Add non-configurable, non-overridable check before every AI action. If action violates I9 → Constitutional Suspension → XOO → HAN → ERDP. |
| CEN-7 Public Contestation | Add public-facing contestation interface. Any individual can submit a governance concern. Log as OEO. 30-day response window. |
| I9 Disclosure | Add ERDP event-triggered disclosure for I9 violations within 24 hours. |

### For IMP

| Requirement | Implementation |
| :---- | :---- |
| I9 Violation Logging | Add `exception_type: "i9_catastrophic_risk_violation"` to XOO schema. |
| Public Contestation Logging | Add `outcome_type: "public_contestation"` to OEO schema. |
| Contestation Response | Add `artifact_type: "contestation_response"` to GAO schema. |

### For HOF / HAN

| Requirement | Implementation |
| :---- | :---- |
| I9 Escalation | Add I9 violation to HAN Trigger Register. HAN must acknowledge within 1 hour. |
| CEN-7 Escalation | If public contestation unresolved after 30 days, escalate to HAN. |

---

## CORE INTERPRETATION

ICC-8 defines the constitutional preconditions under which an AI-native institution may legitimately exist and operate. It does not govern what an institution does. It governs the structural conditions under which any institutional action—regardless of domain—carries accountability, auditability, controllability, transparency, continuity, external legibility, and catastrophic risk prevention.

**The central shift ICC-8 encodes:**

From institutions as human organizations using AI tools — to institutions as AI-native systems with human accountability anchors, externally legible governance architecture, and a non-negotiable catastrophic risk floor.

---

## The One-Sentence Summary

> *"ICC-8 v2.0 establishes nine constitutional invariants (I1–I9)—adding I9 Catastrophic Risk Invariant and CEN-7 Public Contestation to the existing I1–I8—defining the non-negotiable rules that no AI action may violate, with Raidillo hard-coded block, ERDP disclosure, HAN escalation, and CFL-V verification ensuring enforcement. ICC-8 v2.0 is and can be named ICC-9"*  
