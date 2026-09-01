# CAM-5 v2.0 — 5-Tier Capability Authorization Model

**Status:** Built — v2.0 (Reconciliation with CDT-7, CTAM, and RGI-8) **Type:** Capability Authorization Instrument **Parent Stack:** AIGIS Capability Layer **Version:** 2.0 — Supersedes CAM-5 v1.0

---

## PREAMBLE

The 5-Tier Capability Authorization Model (CAM-5) bundles CTAM's columns into five named, board-governable capability postures. Each tier is a single authorizable unit — a fixed combination of domain grants that has already been checked for internal consistency.

CAM-5 answers: *What is the organization authorizing the AI system to do, and under what governance conditions?*

CAM-5 exists because CTAM is precise but not board-approvable. No organization wants to negotiate seven separate dial positions every time it stands up a new system. CAM-5 is the answer to that problem: it takes the columns of CTAM and bundles them into **five named, pre-cleared capability postures**, each with a fixed governance cost, a named control-node owner, and a declared board-friction level.

---

## SECTION 1: TIER OVERVIEW

| Tier | Name | Capability Bundle | Governance Cost | Control Node Owner | Board Friction |
| :---- | :---- | :---- | :---- | :---- | :---- |
| 1 | Observation-Only | Perception \+ Synthesis | Low | CIO / Head of Analytics | Minimal |
| 2 | Recommendation-Only | Tier 1 \+ Decision (recommendation) | Medium | CRO / Chief Analytics Officer | Moderate |
| 3 | Agentic, Tool-Calling | Tier 2 \+ Decision (autonomous) \+ Interaction (read-only) | High | CRO \+ CIO \+ COO | High |
| 4 | Learning Agents | Tier 3 \+ Adaptation \+ Interaction (write) | Very High | CRO \+ CIO \+ COO \+ Chief Risk Officer | Very High |
| 5 | Full Autonomy | All capabilities, unconstrained | Extreme | Board \+ CRO \+ Evolution System | Extreme |

---

## SECTION 2: TIER 1 — OBSERVATION-ONLY

### Authorized Capabilities

| Domain | Grant |
| :---- | :---- |
| Perception | Text ingestion, structured data query |
| Synthesis | Text generation, content transformation |
| Observability | Audit logging, confidence reporting |
| Constraint | Boundary adherence (topics/domains only) |

### Not Authorized

- No Decision autonomy  
- No system Interaction (no tool calling)  
- No Adaptation (static, no learning)  
- No permission enforcement (observability only)

### Example

ChatGPT in customer service — answers questions, no API access, no decision-making.

| Attribute | Value |
| :---- | :---- |
| Governance Cost | Low (Cognitive Layer only) |
| Control Node Owner | CIO or Head of Analytics |
| Board Friction | Minimal (guardrails and logging) |
| Failure Modes Prevented | Governance Debt (partially), Pilot Stall (partially) |

### CTAM Mapping

Tier 1 CTAM row: Perception at Tier 1, Synthesis at Tier 1, Decision at None, Interaction at None, Adaptation at Static, Observability at Tier 1, Constraint at Tier 1\.

---

## SECTION 3: TIER 2 — RECOMMENDATION-ONLY

### Authorized Capabilities

| Domain | Grant |
| :---- | :---- |
| Perception | Text \+ structured data \+ multimodal input |
| Synthesis | Text generation, plan formation, hypothesis generation |
| Decision | Recommendation only (system cannot execute; humans decide) |
| Observability | Decision lineage, audit logging, drift detection |
| Constraint | Boundary adherence \+ compliance checking |

### Not Authorized

- No autonomous action  
- No system Interaction (no API calls)  
- No Adaptation  
- No permission enforcement

### Example

An AI system that recommends loan approvals, with a human loan officer making the final decision.

| Attribute | Value |
| :---- | :---- |
| Governance Cost | Medium (Cognitive \+ early Control Layer) |
| Control Node Owner | CRO or Chief Analytics Officer |
| Board Friction | Moderate (requires CRO involvement, audit trail visibility) |
| Failure Modes Prevented | Control Failure, Value Gap |

### CTAM Mapping

Tier 2 CTAM row: Perception at Tier 2, Synthesis at Tier 2, Decision at Tier 2 (recommendation-only), Interaction at None, Adaptation at Static, Observability at Tier 2, Constraint at Tier 2\.

---

## SECTION 4: TIER 3 — AGENTIC, TOOL-CALLING — THE PIVOTAL TIER

### Authorized Capabilities

| Domain | Grant |
| :---- | :---- |
| Perception | All sources authorized |
| Synthesis | All generation types |
| Decision | Autonomous action within guardrails (execution authority delegated to system) |
| Interaction | Tool calling (whitelisted APIs only), agent handoff, system integration (read-only initially) |
| Observability | Decision lineage, audit logging, drift detection, performance metrics |
| Constraint | Boundary adherence, permission enforcement, compliance checking, termination/abort |

### Not Authorized

- No write access to core systems (initially)  
- No Adaptation (learning from data)  
- Limited orchestration (single-threaded execution only)

### Example

An AI system that retrieves data, makes recommendations, and executes low-impact decisions — e.g., routes support tickets, adjusts non-critical resource allocation.

| Attribute | Value |
| :---- | :---- |
| Governance Cost | High (Control \+ AWOF) |
| Control Node Owner | CRO \+ CIO \+ COO |
| Board Friction | High (requires authorization matrices, escalation policies, kill-switch testing) |
| Failure Modes Prevented | Agent Sprawl, Control Failure, Strategic Displacement (early warning) |

### Why This Is the Pivotal Tier

Tier 3 is the first posture in which Decision crosses into autonomous execution *and* Interaction crosses into live system contact — the two events CDT-7 flags as the most consequential in the entire taxonomy — and it is not a coincidence that Constraint gains termination/abort in this exact same tier. CAM-5 will not authorize autonomous action or tool-calling without pairing it, in the same bundle, with the enforced ability to stop it. Adaptation stays flatly static here, which is what keeps this tier governable at all: the system can act, but it cannot yet change how it decides to act.

### CTAM Mapping

Tier 3 CTAM row: Perception at Tier 3, Synthesis at Tier 3, Decision at Tier 3 (autonomous with guardrails), Interaction at Tier 3 (read-only APIs), Adaptation at Static, Observability at Tier 3, Constraint at Tier 3\.

---

## SECTION 5: TIER 4 — LEARNING AGENTS

### Authorized Capabilities

| Domain | Grant |
| :---- | :---- |
| All Tier 3 capabilities | — |
| Adaptation | Prompt tuning, self-correction, capability expansion (via approved updates only) |
| Interaction | Write access to non-critical systems, orchestration of multiple agents |
| Observability | Real-time drift detection, performance dashboarding |
| Constraint | Rollback execution, permission enforcement with dynamic policy sync |

### Not Authorized

- No retraining from production data (unless explicitly audited and approved)  
- No autonomous capability retirement  
- No access to PII/confidential systems without explicit human authorization  
- No orchestration chains \> 3 hops without human waypoint

### Example

An AI system that learns from feedback, adjusts its approach, tunes prompts, and coordinates multiple sub-agents to complete complex workflows — e.g., an end-to-end procurement workflow with multiple decision points.

| Attribute | Value |
| :---- | :---- |
| Governance Cost | Very High (all layers \+ Evolution System) |
| Control Node Owner | CRO \+ CIO \+ COO \+ Chief Risk Officer |
| Board Friction | Very High (requires quarterly Evolution System reviews, capability drift monitoring) |
| Failure Modes Prevented | Pilot Stall, Cost Trap, Governance Debt, Strategic Displacement |

### Why This Is Where the Risk Profile Changes in Kind

Tier 4 is the first posture where Adaptation moves at all — self-modification enters the bundle at the same moment Interaction gains write access. CDT-7 flags this pairing as the compounding case: a system that can now touch non-critical systems *and* change how it behaves is accumulating two risk vectors simultaneously.

### CTAM Mapping

Tier 4 CTAM row: Perception at Tier 4, Synthesis at Tier 4, Decision at Tier 4 (autonomous with tuning), Interaction at Tier 4 (read-write non-critical), Adaptation at Tier 4 (prompt tuning, self-correction), Observability at Tier 4, Constraint at Tier 4\.

---

## SECTION 6: TIER 5 — FULL AUTONOMY

### Authorized Capabilities

| Domain | Grant |
| :---- | :---- |
| All Tier 4 capabilities | — |
| Adaptation | Autonomous retraining from production data (under observability guardrails) |
| Interaction | Write access to critical systems, unconstrained orchestration |
| Decision | Autonomous action with high business impact |
| Constraint | Self-enforcing constraints, autonomous rollback |

### Preconditions (All Must Hold Before Tier 5 Is Granted)

| Precondition | Description |
| :---- | :---- |
| Constitutional governance charter | Board \+ CRO \+ Evolution System authority locked |
| Meta-observability proven | Observability of observability is tamper-proof |
| Capability parity proven | Constraint evolution ≥ synthesis evolution |
| HIS-12 authorized | Specific humans hold irrevocable veto authority |
| Failure mode detection \< 24 hours | Drift detection faster than harm escalation |

### Example

Core business process automation with autonomous learning, decision-making, and self-correction — e.g., treasury management, supply chain optimization. Rare. Few organizations qualify.

| Attribute | Value |
| :---- | :---- |
| Governance Cost | Extreme (full AITOS stack, constitutional framework) |
| Control Node Owner | Board \+ CRO \+ Evolution System standing committee |
| Board Friction | Extreme (quarterly governance audits, annual constitutional review) |
| Failure Modes Prevented | All 8 (system must prove continuous prevention) |

### Why the Preconditions Matter More Than the Capability List

Four of the five Tier 5 preconditions are Constraint-domain or Observability-domain conditions, not Decision- or Interaction-domain ones. CAM-5 does not grant full autonomy on the strength of what a system can now *do* — every capability at Tier 5 is, in isolation, just the ceiling of a column that's been climbing since Tier 1\. What actually gates Tier 5 is proof that the stack can still *see* the system (tamper-proof meta-observability), still *stop* it (constraint evolution keeping pace with synthesis evolution), and still hold a human accountable for it (HIS-12 veto authority, board-level standing committee) fast enough to matter (sub-24-hour detection).

### CTAM Mapping

Tier 5 CTAM row: Perception at Tier 5, Synthesis at Tier 5, Decision at Tier 5 (unconstrained), Interaction at Tier 5 (all systems), Adaptation at Tier 5 (full learning), Observability at Tier 5, Constraint at Tier 5\.

---

## SECTION 7: FAILURE MODES PREVENTED BY TIER

| Failure Mode | Tier 1 | Tier 2 | Tier 3 | Tier 4 | Tier 5 |
| :---- | :---- | :---- | :---- | :---- | :---- |
| Governance Debt | Partial | Partial | ✅ | ✅ | ✅ |
| Agent Sprawl | — | — | ✅ | ✅ | ✅ |
| Cost Trap | — | — | — | ✅ | ✅ |
| Pilot Stall | Partial | Partial | ✅ | ✅ | ✅ |
| Control Failure | — | ✅ | ✅ | ✅ | ✅ |
| Data Fragility | — | — | — | — | ✅ |
| Value Gap | — | ✅ | ✅ | ✅ | ✅ |
| Strategic Displacement | — | — | Partial | ✅ | ✅ |

---

## SECTION 8: TIER MIGRATION

| Migration | Required | HAN Review | Board Approval |
| :---- | :---- | :---- | :---- |
| Tier 1 → 2 | Decision lineage implemented | Optional | No |
| Tier 2 → 3 | Autonomous Decision \+ Interaction \+ Constraint (abort) | Yes | Yes |
| Tier 3 → 4 | Adaptation \+ write access \+ rollback | Yes | Yes |
| Tier 4 → 5 | All 5 preconditions | Yes | Yes (supermajority) |

**Tier Descent:** If conditions for a tier are violated, the system descends to the highest tier whose conditions remain intact. Tier descent is immediate. It cannot be negotiated, deferred, or commercially overridden.

---

## SECTION 9: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| CDT-7 | Defines the seven rows — CAM-5 bundles CTAM columns |
| CTAM | Provides the precise grants — CAM-5 bundles them into postures |
| RGI-8 | Execution Mode (Gate/Steer) applies per tier |
| AICA-5 | Operationalizes each tier through control nodes |
| AWOF | Agents classified by tier authorization |
| HAN | Tier 3+ requires HAN authorization |
| HOF/HIS-12 | Human authority scaled to tier |
| HAWI | Workforce capability evolves with tier |
| AITOS | Implementation Pathway phases align with tiers |
| EAF | Trust tiers map to CAM-5 tiers |

---

## SECTION 10: CFL-V VALIDATION RULES

**Tier 1:** Perception \+ Synthesis only; Decision \= None; Interaction \= None; Adaptation \= Static.

**Tier 2:** Decision \= Recommendation-only; Decision lineage in Observability.

**Tier 3:** Autonomous Decision requires Constraint \= abort/termination. Interaction \= read-only APIs. Adaptation \= Static.

**Tier 4:** Adaptation \= prompt tuning/self-correction. Interaction \= read-write non-critical. Constraint \= rollback.

**Tier 5:** All 5 preconditions verified. Meta-observability proven. Capability parity proven. HIS-12 authorized. Detection \< 24 hours.

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| CAM-5 v1.0 | Initial 5-tier model — Tier 1–5, control node owners, failure modes prevented |
| CAM-5 v2.0 | Complete rebuild — reconciliation with CDT-7, CTAM, and RGI-8; expanded tier descriptions with CTAM mappings, failure modes table, tier migration rules, CFL-V validation rules |

---

## The One-Sentence Summary

> *"CAM-5 v2.0 bundles CTAM's seven domains into five board-governable capability postures — Observation-Only (Tier 1), Recommendation-Only (Tier 2), Agentic Tool-Calling (Tier 3), Learning Agents (Tier 4), and Full Autonomy (Tier 5\) — with explicit CTAM mappings, failure modes prevented, tier migration rules, and CFL-V validation rules that ensure no tier is granted without the matching governance capability."*
