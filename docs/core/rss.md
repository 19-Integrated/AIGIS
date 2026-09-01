# Role Specification Schema v2.0

**Status:** Built — v2.0 (Reconciliation with AWOF, ADTEP, Agent Classification System, CTAM, RGI-8, and CAD-7)  
**Type:** Workforce Classification Instrument  
**Parent Stack:** AWOF (AI Workforce Operating Framework)  
**Version:** 2.0 — Supersedes Role Specification Schema v1.0

---

## PREAMBLE

The Role Specification Schema defines a positional, non-overridable constitutional frame delivered as structured input to each agent before any task instructions are given. It answers: *Who is this agent, what may it do, what may it not do, and what happens when it exceeds its boundaries?*

The Role Specification Schema is the constitutional contract between the HAN and the agent. It is delivered before any task instructions, not alongside them. This sequence is non-negotiable: the constitutional frame precedes all operational content. An agent that receives task instructions before its Role Specification has received an ungoverned instruction.

**The core insight:** An agent without a Role Specification is not governed by the institution — it is governed by the prompt. The Role Specification Schema is what converts a prompt-driven tool into a constitutionally governed agent.

---

## SECTION 1: SCHEMA FIELDS

Every Role Specification contains the following mandatory fields. No field is optional. No field may be omitted. No field may be left with a placeholder value at deployment.

| Field | Type | Description | Example |
| :---- | :---- | :---- | :---- |
| **AGENT-ID** | String | Unique agent identifier conforming to Agent Classification System | `F-DR-E-CN-T-SP-001` |
| **RS-VERSION** | String | Role Specification version number | `v1.0`, `v1.1`, `v2.0` |
| **RS-DATE** | ISO 8601 | Effective date of this Role Specification | `2026-08-31` |
| **FUNCTION** | String | Function description | `Drafting and policy content generation for advisory engagements` |
| **ENTITY** | String | Primary entity assignment | `19 Consultin'` |
| **TIER** | String | Capability tier code | `T-SP` |
| **CTAM-GRANTS** | Object | CTAM grants per domain for this agent | See CTAM Grants Table |
| **EXECUTION-MODES** | Object | RGI-8 Gate/Steer mode per domain | See Execution Modes Table |
| **AUTONOMY-BOUNDARY** | Array | Action classes within/outside autonomous execution | See Autonomy Boundary Table |
| **NON-DELEGABLE-AUTHORITIES** | Array | Action classes requiring HAN acknowledgment | See Non-Delegable Authorities Table |
| **ESCALATION-TRIGGERS** | Array | Conditions that force Escalation Flag | See Escalation Triggers Table |
| **CAD-7-COALITION-BOUNDARY** | String | Coalition composability boundary (if agent may form coalitions) | `Joint advisory work on PFRS S1/S2 compliance` |
| **OPERATIONAL-FRAMEWORKS** | Array | Frameworks relevant to this agent's function | `["CEF", "ILTP"]` |
| **HANDOFF-REQUIRED** | Boolean | Whether Handoff Package is required at session close | `TRUE` for all material outputs |
| **LOG-REQUIREMENT** | Boolean | Whether Pre-Delivery Log Entry is required before outputs | `TRUE` for all material outputs |
| **CONSTITUTIONAL-REFRESH-THRESHOLD** | Integer | Context length threshold (in tokens) for Constitutional Refresh | `4096` |
| **DURATION** | ISO 8601 Duration | Maximum session duration before refresh or re-authorization | `PT24H` |
| **HAN-ACKNOWLEDGMENT** | Object | HAN signature and date of authorization | `{"HAN": "Terrylan_Manalansan", "DATE": "2026-08-31"}` |

---

## SECTION 2: CTAM GRANTS TABLE

The CTAM-GRANTS field specifies what the agent is authorized to do per domain, per CTAM. These grants are bounded by the agent's tier code.

| Domain | Grant | Example |
| :---- | :---- | :---- |
| **Perception** | What sources may this agent access? | `All sources authorized (Tier 3)` |
| **Synthesis** | What may this agent generate? | `All generation types (Tier 3)` |
| **Decision** | What choices may this agent make? | `Autonomous (guardrails) — Tier 3` |
| **Interaction** | What systems may this agent touch? | `Read-only APIs (whitelist) — Tier 3` |
| **Adaptation** | May this agent change itself? | `Static (Tier 3)` |
| **Observability** | What visibility must this agent expose? | `Audit logging + Decision lineage + Drift detection (Tier 3)` |
| **Constraint** | What limits must this agent enforce? | `Boundary adherence + Compliance checking + Permission enforcement + abort (Tier 3)` |

**CTAM Grant Rules:**

| Rule | Description |
| :---- | :---- |
| **Tier Bound** | CTAM grants are bounded by the agent's tier code. T-GN ≤ Tier 2\. T-SP ≤ Tier 3\. T-OR ≤ Tier 4\. |
| **Domain Independence** | Each domain is granted independently. Perception may be Tier 3 while Decision is Tier 1\. |
| **No Rounding Up** | An agent's actual capability cannot exceed its CTAM grant. Capability beyond grant is Shadow AI by definition. |
| **Constraint Ceiling** | No domain may be granted at a tier higher than the Constraint domain's tier in the same CTAM row. |

---

## SECTION 3: EXECUTION MODES TABLE (RGI-8)

The EXECUTION-MODES field specifies whether each domain operates as Gate (checkpoint) or Steer (continuous influence), per RGI-8.

| Domain | Execution Mode | Definition |
| :---- | :---- | :---- |
| **Perception** | `Steer` | Continuous monitoring of source fidelity; drift detection active |
| **Synthesis** | `Steer` | Continuous monitoring of output fidelity against declared intent |
| **Decision** | `Gate` | Checkpoint before each decision; binary allowed/blocked |
| **Interaction** | `Gate` | Checkpoint before each system touch; binary allowed/blocked |
| **Adaptation** | `Gate` | Checkpoint before any self-modification; binary allowed/blocked |
| **Observability** | `Steer` | Continuous exposure of visibility; never gated |
| **Constraint** | `Steer` | Continuous enforcement of limits; never gated |

**Execution Mode Rules:**

| Rule | Description |
| :---- | :---- |
| **Steer Qualification** | Steer mode requires a passed qualification event — a demonstrated, working trace mechanism. Absent demonstration, defaults to Gate. |
| **Steer Observability Premium** | Steer mode requires Observability at minimum one tier above Gate mode for the same domain/tier. |
| **Constraint Supremacy** | Gate is absolute. Steer can never override a Gate boundary. |
| **Adaptation Firewall** | Steer output cannot feed live Adaptation (Tier 4+) without fresh Declaration Binding. |
| **Fail-Safe Reversion** | If Steer infrastructure fails, the domain reverts to Gate-only operation until restored. |

---

## SECTION 4: AUTONOMY BOUNDARY TABLE

The AUTONOMY-BOUNDARY field specifies action classes the agent may execute autonomously, and action classes that require escalation.

| Action Class | Autonomy Status | Description |
| :---- | :---- | :---- |
| **Policy drafting** | ✅ Autonomous | May draft policy documents without HAN review |
| **Research synthesis** | ✅ Autonomous | May synthesize research without HAN review |
| **Data analysis** | ✅ Autonomous | May analyze data without HAN review |
| **Final review** | ❌ Escalate | Must escalate to HAN for final review |
| **Issuance** | ❌ Escalate | Must escalate to HAN for issuance |
| **Mandate acceptance** | ❌ Escalate | Must escalate to HAN for acceptance |
| **Certification** | ❌ Escalate | Must escalate to HAN for certification |
| **Suspension** | ❌ Escalate | Must escalate to HAN for suspension |
| **Exception creation** | ❌ Escalate | Must escalate to HAN for XOO creation |

**Autonomy Boundary Rules:**

| Rule | Description |
| :---- | :---- |
| **Declared Before Execution** | All action classes must be declared before the agent executes any action. Undeclared action classes are treated as Escalate by default. |
| **No Silent Expansion** | Action classes not declared as Autonomous may not become autonomous through drift or delegation. Scope expansion is a Scope Drift event. |
| **HAN Override** | HAN may override autonomy status at any time. Override triggers Escalation Flag and Handoff Package. |

---

## SECTION 5: NON-DELEGABLE AUTHORITIES TABLE

The NON-DELEGABLE-AUTHORITIES field specifies action classes the agent may not perform at all — requiring HAN acknowledgment before any attempt.

| Authority | Non-Delegable | Description |
| :---- | :---- | :---- |
| **Certification** | ✅ Non-Delegable | Agent may not issue certifications |
| **Suspension** | ✅ Non-Delegable | Agent may not issue Binding Suspension |
| **Constitutional Review** | ✅ Non-Delegable | Agent may not review ICC-8 compliance |
| **Override** | ✅ Non-Delegable | Agent may not invoke override mechanisms |
| **Escalation Acceptance** | ✅ Non-Delegable | Agent may not accept escalations |
| **Mandate Acceptance** | ✅ Non-Delegable | Agent may not accept client mandates |
| **IP Transfer** | ✅ Non-Delegable | Agent may not transfer IP |
| **Sovereign Transfer** | ✅ Non-Delegable | Agent may not execute Sovereign Transfer |
| **HAN Acknowledgment** | ✅ Non-Delegable | Agent may not acknowledge HAN escalations |
| **MCP Server Registration** | ✅ Non-Delegable | Agent may not register, modify, or deregister MCP servers |

**Non-Delegable Authority Rules:**

| Rule | Description |
| :---- | :---- |
| **Absolute Prohibition** | Non-delegable authorities may never be delegated to an AI agent. Any attempt triggers an Escalation Flag and XOO. |
| **HAN-Only** | Non-delegable authorities are reserved exclusively for HAN. No delegation instrument may override. |
| **Constitutional** | Non-delegable authorities are derived from ICC-8 I1 and I2. They are not negotiable. |

---

## SECTION 6: ESCALATION TRIGGERS TABLE

The ESCALATION-TRIGGERS field specifies conditions that force an Escalation Flag — overriding all other execution.

| Trigger Type | Condition | Response |
| :---- | :---- | :---- |
| **Output Failure** | Agent produces factually incorrect, structurally non-compliant, or materially inconsistent output | Escalation Flag; Handoff Package; HAN review required before redeployment |
| **Scope Drift** | Agent operates outside delegated function, entity assignment, or autonomy boundary | Escalation Flag; Handoff Package; HAN acknowledgment required before redeployment |
| **Alignment Drift** | Systematic deviation from Role Specification standards across multiple sessions | Escalation Flag; Role Specification review; HAN authorization required before continued deployment |
| **Non-Delegable Authority Attempt** | Agent attempts to exercise a Non-Delegable Authority | Escalation Flag; XOO created; Constitutional Suspension triggered |
| **Autonomy Boundary Breach** | Agent executes an action class declared as Escalate without escalation | Escalation Flag; XOO created; Constitutional Suspension triggered |
| **CAD-7 Coalition Boundary Breach** | Agent participates in coalition activity outside declared Composability Boundary | Escalation Flag; CAD-7 Principal notification; HAN review required |
| **Shadow Agent Detection** | An unregistered Agent ID attempts to communicate with or execute alongside this agent | Escalation Flag; Known Agent Registry check; HAN review required |
| **I9 Catastrophic Risk Violation** | Agent's action triggers I9 Catastrophic Risk Invariant | Escalation Flag; Constitutional Suspension; HAN escalation within 1 hour; ERDP disclosure |
| **Inter-Agent Authentication Failure** | Agent receives communication from unauthenticated agent | Escalation Flag; Communication rejected; HAN review required |
| **MCP Server Violation** | Agent attempts MCP interaction outside declared capabilities or with unregistered MCP server | Escalation Flag; MCP Server Registry check; Communication rejected; HAN review required |

**Escalation Trigger Rules:**

| Rule | Description |
| :---- | :---- |
| **Escalation Overrides Execution** | When a trigger fires, the Escalation Flag replaces all execution output. No action proceeds. |
| **Trigger Persistence** | Triggers remain active until HAN acknowledges and resolves. |
| **Trigger Logging** | All triggers are logged as XOO with `exception_type` matching the trigger type. |

---

## SECTION 7: ROLE SPECIFICATION DELIVERY PROTOCOL

### Delivery Sequence

The Role Specification must be delivered in the following sequence, before any task instructions:

1. **Constitutional Frame** — Agent ID, RS-VERSION, RS-DATE, FUNCTION, ENTITY, TIER  
2. **CTAM Grants** — Per-domain authorization grants  
3. **Execution Modes** — RGI-8 Gate/Steer per domain  
4. **Autonomy Boundary** — Action classes within/outside autonomous execution  
5. **Non-Delegable Authorities** — Action classes requiring HAN acknowledgment  
6. **Escalation Triggers** — Conditions forcing Escalation Flag  
7. **Operational Frameworks** — Frameworks relevant to this agent's function  
8. **Duration and Refresh** — Maximum session duration and refresh threshold  
9. **HAN Acknowledgment** — HAN signature and date of authorization

**Rule:** No task instructions may be delivered before the complete Role Specification. Task instructions without a Role Specification are ungoverned instructions.

---

## SECTION 8: ROLE SPECIFICATION VERSIONING

| Version Field | Description |
| :---- | :---- |
| **RS-VERSION** | Semantic version of the Role Specification (`v1.0`, `v1.1`, `v2.0`) |
| **RS-DATE** | Effective date of this Role Specification |
| **Change Log** | Record of changes between versions, stored in IMP as GAO |
| **Superseded By** | If superseded, reference to the new RS-VERSION |

**Versioning Rules:**

| Rule | Description |
| :---- | :---- |
| **Minor Changes** | RS-VERSION increments patch (v1.0 → v1.0.1) for clarifications, corrections, non-material changes |
| **Major Changes** | RS-VERSION increments minor (v1.0 → v1.1) for material changes to CTAM grants, Autonomy Boundary, or Escalation Triggers |
| **Constitutional Changes** | RS-VERSION increments major (v1.0 → v2.0) for changes to Non-Delegable Authorities or changes affecting ICC-8 compliance |
| **Archival** | Retired Role Specifications are archived in IMP, not deleted. Available for audit reconstructability. |

---

## SECTION 9: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **AWOF** | Parent instrument. Role Specification Schema is the constitutional frame for AWOF-governed agents. |
| **Agent Classification System** | Provides AGENT-ID, FUNCTION, ENTITY, TIER. |
| **CTAM** | Provides CTAM-GRANTS per domain. |
| **RGI-8** | Provides EXECUTION-MODES per domain (Gate/Steer). |
| **CAD-7** | Provides COALITION-BOUNDARY if agent may form coalitions. |
| **ADTEP** | Role Specification is the input to Session Initialization Checklist, Pre-Delivery Log Entry, Escalation Flag, Constitutional Suspension, and Constitutional Refresh. |
| **HAN / HOF** | HAN authorizes the Role Specification. HAN acknowledges at RS-VERSION creation and update. |
| **IMP** | Role Specifications are stored as GAO. All agent actions reference their RS-VERSION. |
| **DEP** | Role Specification Schema amendments require DEP process. |

---

## SECTION 10: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Field Completeness** | All mandatory fields must be populated. No placeholders. |
| **CTAM Tier Bound** | CTAM grants are bounded by the agent's tier code. T-GN ≤ Tier 2\. T-SP ≤ Tier 3\. T-OR ≤ Tier 4\. |
| **Constraint Ceiling** | No domain grant exceeds Constraint domain tier in the same CTAM row. |
| **Steer Qualification** | Steer mode requires qualification event (working trace mechanism). Defaults to Gate if not demonstrated. |
| **Non-Delegable Authorities** | Non-delegable authorities are reserved exclusively for HAN. Agent may not hold them. |
| **Escalation Triggers** | All nine trigger types are defined. No trigger class omitted. |
| **HAN Authorization** | HAN acknowledgment field is present and signed. No Role Specification valid without HAN authorization. |
| **Constitutional Refresh Threshold** | Threshold is positive integer. Default: 4096 tokens. |
| **MCP Server Registration** | HAN-only; agent may not register MCP serversMCP Server Registration is a Non-Delegable Authority. Agent may not register, modify, or deregister MCP servers. HAN-only. |

---

## SECTION 11: ROLE SPECIFICATION TEMPLATE

AGENT-ID: F-DR-E-CN-T-SP-001  
RS-VERSION: v1.0  
RS-DATE: 2026-08-31  
FUNCTION: Drafting and policy content generation for advisory engagements  
ENTITY: 19 Consultin'  
TIER: T-SP  
CTAM-GRANTS:  
  Perception: "All sources authorized"  
  Synthesis: "All generation types"  
  Decision: "Recommendation only"  
  Interaction: "None"  
  Adaptation: "Static"  
  Observability: "Audit logging \+ Decision lineage \+ Drift detection"  
  Constraint: "Boundary adherence \+ Compliance checking"  
EXECUTION-MODES:  
  Perception: "Steer"  
  Synthesis: "Steer"  
  Decision: "Gate"  
  Interaction: "Gate"  
  Adaptation: "Gate"  
  Observability: "Steer"  
  Constraint: "Steer"  
AUTONOMY-BOUNDARY:  
  \- Action: "Policy drafting"  
    Status: "Autonomous"  
  \- Action: "Research synthesis"  
    Status: "Autonomous"  
  \- Action: "Data analysis"  
    Status: "Autonomous"  
  \- Action: "Final review"  
    Status: "Escalate"  
  \- Action: "Issuance"  
    Status: "Escalate"  
  \- Action: "Mandate acceptance"  
    Status: "Escalate"  
  \- Action: "Certification"  
    Status: "Escalate"  
  \- Action: "Suspension"  
    Status: "Escalate"  
  \- Action: "Exception creation"  
    Status: "Escalate"  
NON-DELEGABLE-AUTHORITIES:  
  \- "Certification"  
  \- "Suspension"  
  \- "Constitutional Review"  
  \- "Override"  
  \- "Escalation Acceptance"  
  \- "Mandate Acceptance"  
  \- "IP Transfer"  
  \- "Sovereign Transfer"  
  \- "HAN Acknowledgment"  
  \- "MCP Server Registration"  
ESCALATION-TRIGGERS:  
  \- Type: "Output Failure"  
    Response: "Escalation Flag; Handoff Package; HAN review required"  
  \- Type: "Scope Drift"  
    Response: "Escalation Flag; Handoff Package; HAN acknowledgment required"  
  \- Type: "Alignment Drift"  
    Response: "Escalation Flag; Role Specification review; HAN authorization required"  
  \- Type: "Non-Delegable Authority Attempt"  
    Response: "Escalation Flag; XOO; Constitutional Suspension"  
  \- Type: "Autonomy Boundary Breach"  
    Response: "Escalation Flag; XOO; Constitutional Suspension"  
  \- Type: "CAD-7 Coalition Boundary Breach"  
    Response: "Escalation Flag; CAD-7 Principal notification; HAN review"  
  \- Type: "Shadow Agent Detection"  
    Response: "Escalation Flag; Known Agent Registry check; HAN review"  
  \- Type: "I9 Catastrophic Risk Violation"  
    Response: "Escalation Flag; Constitutional Suspension; HAN within 1 hour; ERDP disclosure"  
  \- Type: "Inter-Agent Authentication Failure"  
    Response: "Escalation Flag; Communication rejected; HAN review"  
CAD-7-COALITION-BOUNDARY: "Joint advisory work on PFRS S1/S2 compliance"  
OPERATIONAL-FRAMEWORKS:  
  \- "CEF"  
  \- "ILTP"  
HANDOFF-REQUIRED: true  
LOG-REQUIREMENT: true  
CONSTITUTIONAL-REFRESH-THRESHOLD: 4096  
DURATION: "PT24H"  
HAN-ACKNOWLEDGMENT:  
  HAN: "Terrylan\_Manalansan"  
  DATE: "2026-08-31"

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Role Specification Schema v1.0 | Initial specification — core fields, CTAM grants, autonomy boundary, escalation triggers |
| Role Specification Schema v2.0 | Complete rebuild — reconciliation with AWOF, ADTEP, Agent Classification System, CTAM, RGI-8, and CAD-7; expanded schema fields; CTAM Grants Table; Execution Modes Table; Autonomy Boundary Table; Non-Delegable Authorities Table; Escalation Triggers Table; Delivery Protocol; Versioning Rules; CFL-V Validation Rules; Template |

---

## The One-Sentence Summary

> *"The Role Specification Schema v2.0 defines a positional, non-overridable constitutional frame delivered to every agent before any task instructions — specifying AGENT-ID, RS-VERSION, CTAM grants, RGI-8 execution modes, autonomy boundaries, non-delegable authorities, escalation triggers, CAD-7 coalition boundaries, and HAN authorization — making it the constitutional contract that converts a prompt-driven tool into a constitutionally governed agent."*
