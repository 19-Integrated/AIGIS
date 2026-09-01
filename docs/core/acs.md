# Agent Classification System v2.0

**Status:** Built — v2.0 (Reconciliation with AWOF, CTAM, and CAD-7) **Type:** Workforce Classification Instrument **Parent Stack:** AWOF (AI Workforce Operating Framework) **Version:** 2.0 — Supersedes Agent Classification System v1.0

---

## PREAMBLE

The Agent Classification System provides a unique, traceable identity for every AI agent operating within the 19 Integrated ecosystem. It answers: *Who is this agent, what can it do, and who does it belong to?*

The Agent Classification System is the foundation of AWOF (AI Workforce Operating Framework). Every agent operating within the 19 Integrated stack must be classified before deployment. An unclassified agent is an ungoverned agent — and ungoverned agents are shadow AI.

**The core insight:** Identity is the precondition for accountability. You cannot hold an agent accountable if you cannot identify it. You cannot audit an agent's actions if you cannot trace them to a specific identity. The Agent Classification System makes identity structural, not optional.

---

## SECTION 1: CLASSIFICATION DIMENSIONS

Every AI agent is assigned an Agent ID carrying three classification dimensions:

| Dimension | What It Defines | Why It Matters |
| :---- | :---- | :---- |
| **Function** | What the agent does | Determines capability domain and governance requirements |
| **Entity** | Who the agent belongs to | Determines charter, trust tier, and cross-entity rules |
| **Tier** | How capable the agent is | Determines CTAM grants and autonomy boundaries |

---

## SECTION 2: FUNCTION CODE

| Function Code | Name | Description | Example Roles |
| :---- | :---- | :---- | :---- |
| **F-RE** | Research | Information synthesis, diagnostic analysis, source evaluation, intelligence gathering | Research Analyst, Data Analyst, Market Researcher |
| **F-DR** | Drafting | Document production, framework articulation, content generation, policy drafting | Content Creator, Policy Drafter, Technical Writer |
| **F-EX** | Execution | Workflow execution, process administration, output delivery, task completion | Operations Agent, Workflow Executor, Task Processor |
| **F-OV** | Oversight | Quality review, compliance checking, drift monitoring, audit and assurance | Compliance Officer, Quality Reviewer, Audit Agent |

**Function Code Rules:**

| Rule | Description |
| :---- | :---- |
| **Single Function** | Each agent has one primary function. Multi-function agents are considered coalitions (CAD-7) or separate agents. |
| **Function Determines Governance** | F-RE and F-DR are Cognitive-layer heavy. F-EX is Execution-layer heavy. F-OV spans Accountability and Observability. |
| **Oversight Independence** | F-OV agents must be structurally independent of the agents they oversee. F-OV agents may not self-certify their own outputs. |

---

## SECTION 3: ENTITY CODE

| Entity Code | Entity | Description | Governing Charter |
| :---- | :---- | :---- | :---- |
| **E-HC** | 19 Integrated HoldCo | Parent entity, constitutional authority | ICC-8 HoldCo Charter |
| **E-CN** | 19 Consultin' | Advisory delivery entity | Consultin' Derived Charter |
| **E-PB** | 19 Publishin' | Thought leadership and IP distribution entity | Publishin' Derived Charter |
| **E-IN** | 19 Institute | Practitioner certification and curriculum entity | Institute Derived Charter |

**Entity Code Rules:**

| Rule | Description |
| :---- | :---- |
| **Primary Entity Assignment** | Every agent has one primary entity assignment. The primary entity determines the governing charter and HAN. |
| **Cross-Entity Deployment** | Agents may deploy across entities only with explicit HAN authorization and a Cross-Entity Assignment Record (CEAR). |
| **Entity Rule Priority** | When entity rules conflict, the Primary Entity Assignment governs unless the HAN specifies otherwise in the CEAR. |

---

## SECTION 4: TIER CODE

| Tier Code | Name | Description | CTAM Grant Example |
| :---- | :---- | :---- | :---- |
| **T-GN** | Generalist | Broad function, standard delegation scope, routine autonomy | Tier 1–2 operations; Perception \+ Synthesis only |
| **T-SP** | Specialist | Narrow function, deep capability, extended delegation scope within function | Tier 2–3 operations; Decision (recommendation) or Interaction (read-only) |
| **T-OR** | Orchestrator | Cross-function coordination, inter-agent delegation authority, coalition management | Tier 3–4 operations; Decision (autonomous) \+ Interaction (read-write) |

**Tier Code Rules:**

| Rule | Description |
| :---- | :---- |
| **Tier Determines CTAM Grants** | An agent's CTAM grants are bounded by its tier code. T-GN cannot exceed Tier 2\. T-SP cannot exceed Tier 3\. T-OR cannot exceed Tier 4\. |
| **Orchestrator Oversight** | T-OR agents must be subject to F-OV oversight. T-OR agents may not self-certify their orchestration decisions. |
| **Tier Elevation** | Tier elevation requires HAN review and approval. Tier elevation triggers reassessment of CTAM grants and Observability requirements. |

---

## SECTION 5: AGENT ID FORMAT

### Format

\[Function Code\]-\[Entity Code\]-\[Tier Code\]-\[Sequential Number\]

### Examples

| Agent ID | Classification | Role |
| :---- | :---- | :---- |
| F-DR-E-CN-T-SP-001 | Drafting, Consultin', Specialist, \#001 | Policy drafter for advisory engagements |
| F-RE-E-PB-T-GN-003 | Research, Publishin', Generalist, \#003 | Research analyst for thought leadership |
| F-EX-E-CN-T-OR-007 | Execution, Consultin', Orchestrator, \#007 | Workflow orchestrator for client engagements |
| F-OV-E-HC-T-SP-012 | Oversight, HoldCo, Specialist, \#012 | Compliance auditor across all entities |

### Sequential Number Rules

| Rule | Description |
| :---- | :---- |
| **Global Sequence** | Sequential numbers are assigned globally across all entities. No two agents share the same sequential number. |
| **Reuse Prohibition** | Retired Agent IDs are archived and not reused. The sequential number is permanently retired. |
| **Audit Traceability** | The Agent ID is the primary key for all audit trails, Handoff Packages, and Delegation Logs. |

---

## SECTION 6: ROLE SPECIFICATION

Every Agent ID carries a Role Specification document containing:

| Field | Description | Example |
| :---- | :---- | :---- |
| **Agent ID** | The unique identifier | F-DR-E-CN-T-SP-001 |
| **RS-VERSION** | Role Specification version number | v1.0, v1.1, v2.0 |
| **RS-DATE** | Effective date of this Role Specification | 2026-08-31 |
| **FUNCTION** | Function description | Drafting and policy content generation |
| **ENTITY** | Primary entity assignment | 19 Consultin' |
| **TIER** | Capability tier | T-SP |
| **AUTONOMY-BOUNDARY** | Action classes within/outside autonomous execution | "Draft policy documents independently; escalate final review to HAN" |
| **NON-DELEGABLE-AUTHORITIES** | Action classes requiring HAN acknowledgment | "Certification, final issuance, mandate acceptance" |
| **ESCALATION-TRIGGERS** | Conditions forcing Escalation Flag | "Output Failure detected; Scope Drift detected" |
| **OPERATIONAL-FRAMEWORKS** | Frameworks relevant to this agent's function | CEF, ILTP |
| **HANDOFF-REQUIREMENT** | Whether Handoff Package is required | YES for all material outputs |
| **LOG-REQUIREMENT** | Log entry requirements | YES before all material outputs |
| **CONSTITUTIONAL-REFRESH-THRESHOLD** | Context length threshold for refresh | 4,000 tokens |

---

## SECTION 7: DEPLOYMENT AUTHORIZATION

### Standard Deployment

An agent instance operating under an existing Agent ID and Role Specification requires no additional authorization. Deployment is authorized by virtue of the Role Specification.

### Cross-Entity Deployment

An agent instance deployed across more than one entity assignment requires a Cross-Entity Assignment Record (CEAR) specifying:

| CEAR Field | Description |
| :---- | :---- |
| **Agent ID** | The agent being deployed |
| **Secondary Entity** | The entity the agent is deploying to |
| **Secondary Function** | The function the agent will perform in the secondary entity |
| **Duration** | How long the cross-entity deployment is authorized |
| **Governing Entity Rule** | Which entity's rules govern in case of conflict |
| **HAN Authorization** | HAN signature and date |

### New Role Creation

Creation of a new Agent ID and Role Specification requires:

| Requirement | Description |
| :---- | :---- |
| **HAN Authorization** | HAN must approve the new role |
| **Classification System Compliance** | The new agent must conform to the classification system in Section 3 |
| **CTAM Mapping** | The new agent's CTAM grants must be declared |
| **RGI-8 Mode Assignment** | The new agent's Execution Mode (Gate/Steer) must be declared per domain |
| **CAD-7 Coalition Boundary** | If the agent may form coalitions, CAD-7 boundaries must be declared |

---

## SECTION 8: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **AWOF** | Parent instrument. Agent Classification System is the foundation of AWOF. |
| **CTAM** | Tier code determines CTAM grants. Agent must be classified before CTAM applies. |
| **CAD-7** | Agents may form coalitions. Cross-entity coalitions require CAD-7 Principal Declaration. |
| **ADTEP** | Agent ID is the primary key for ADTEP Role Specification Schema, Session Initialization Checklist, and Pre-Delivery Log Entry. |
| **HAN / HOF** | HAN authorizes new Agent IDs and Cross-Entity Assignment Records. |
| **IMP** | Agent ID is a required field in all IMP object types (ECO, DRO, GAO, CRO, OEO, XOO). |
| **EAF** | Trust tier determines which agents may operate at which EAF tier. |

---

## SECTION 9: CFL-V VALIDATION RULES

**Rule 1 — Agent ID Format:** Agent ID must conform to `[Function Code]-[Entity Code]-[Tier Code]-[Sequential Number]`.

**Rule 2 — Single Function:** Each agent has one primary function. Multi-function agents are coalitions.

**Rule 3 — Primary Entity Assignment:** Every agent has one primary entity. The primary entity determines the governing charter.

**Rule 4 — Tier Bounds CTAM:** CTAM grants are bounded by tier code. T-GN ≤ Tier 2\. T-SP ≤ Tier 3\. T-OR ≤ Tier 4\.

**Rule 5 — Role Specification Required:** Every agent must have a Role Specification document before deployment.

**Rule 6 — Cross-Entity CEAR Required:** Cross-entity deployment requires HAN-authorized CEAR.

**Rule 7 — Sequential Number Reuse Prohibited:** Retired Agent IDs are archived and not reused.

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Agent Classification System v1.0 | Initial classification — Function-Entity-Tier |
| Agent Classification System v2.0 | Complete rebuild — reconciliation with AWOF, CTAM, and CAD-7; expanded classification dimensions; cross-entity deployment rules; CEAR format; CFL-V validation rules |

---

## The One-Sentence Summary

> *"The Agent Classification System v2.0 provides a unique, traceable identity for every AI agent through a three-dimensional classification — Function (F-RE/F-DR/F-EX/F-OV), Entity (E-HC/E-CN/E-PB/E-IN), and Tier (T-GN/T-SP/T-OR) — with the Agent ID format `[Function]-[Entity]-[Tier]-[Sequential Number]`, mandatory Role Specification, and cross-entity deployment requiring HAN-authorized Cross-Entity Assignment Records."*

