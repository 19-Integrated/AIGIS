# ADTEP v2.0 — Agent Deployment & Technical Enforcement Protocol

**Status:** Built — v2.0 (Reconciliation with AWOF, Role Specification Schema, Trigger System, Handoff Package, MVOS, AICA-5, ICC-8, and RGI-8)  
**Type:** Technical Enforcement Instrument  
**Parent Stack:** AWOF (AI Workforce Operating Framework)  
**Version:** 2.0 — Supersedes ADTEP v1.0

---

## PREAMBLE

The Agent Deployment & Technical Enforcement Protocol (ADTEP) is the Layer 3 technical enforcement protocol that enforces constitutional constraints at the session execution level. It answers: *How do we narrow the gap between normative governance and technical enforcement to its irreducible minimum?*

ADTEP is the mechanism that makes governance enforceable, not just documentable. It ensures that constitutional constraints are embedded in the agent's execution environment — not merely stated in policies — and that violations are detectable, accountable, and auditable.

**The core insight:** A policy that prohibits something but doesn't technically block, monitor, or detect it is not a control — it is a statement of intent. ADTEP converts normative governance into technical enforcement, narrowing the gap between "what the policy says" and "what the system actually does" to its irreducible minimum.

---

## SECTION 1: ADTEP COMPONENTS

ADTEP consists of seven core components, each addressing a specific technical enforcement function:

| Component | Function | Status |
| :---- | :---- | :---- |
| **Role Specification Schema** | Positional, non-overridable constitutional frame delivered before any task instructions | ✅ Built (v2.0) |
| **Session Initialization Checklist** | Completeness gate; no material work without full constitutional context | ✅ Built (v2.0) |
| **Pre-Delivery Log Entry** | Audit artifact before output delivery; log precedes action | ✅ Built (v2.0) |
| **Escalation Flag** | Mandatory output replacing execution when trigger conditions are met | ✅ Built (v2.0) |
| **Constitutional Suspension** | All material work halts until HAN acknowledges Escalation Flag | ✅ Built (v2.0) |
| **Constitutional Refresh** | Periodic reinjection of Role Specification to prevent context dilution | ✅ Built (v2.0) |
| **Raidillo Hard-Coded Block** | Non-configurable, non-overridable I9 Catastrophic Risk enforcement | ✅ Built (v2.0) |

---

## SECTION 2: ARCHITECTURE — ENFORCEMENT LAYERS

ADTEP operates across three enforcement layers:

| Layer | Function | Mechanism |
| :---- | :---- | :---- |
| **Layer 1: Pre-Execution** | Prevent unauthorized execution before it starts | Session Initialization Checklist; Role Specification verification |
| **Layer 2: Runtime** | Monitor and constrain execution during the session | Constitutional Refresh; Pre-Delivery Log Entry; Raidillo Hard-Coded Block |
| **Layer 3: Post-Execution** | Interrupt, escalate, or suspend after execution | Escalation Flag; Constitutional Suspension; Handoff Package |

**Enforcement Flow:**

Pre-Execution (Layer 1\)  
    ↓  
Role Specification → Session Initialization Checklist → Session Begins  
    ↓  
Runtime (Layer 2\)  
    ↓  
Constitutional Refresh → Action → Pre-Delivery Log Entry → Output  
    ↓  
Post-Execution (Layer 3\)  
    ↓  
Output → Escalation Flag? → Constitutional Suspension? → Handoff Package

---

## SECTION 3: COMPONENT 1 — ROLE SPECIFICATION SCHEMA

### Function

Defines a positional, non-overridable constitutional frame delivered as structured input to each agent before any task instructions are given.

### Status

✅ Built — See Role Specification Schema v2.0 for complete specification.

### Key Elements

| Element | Description |
| :---- | :---- |
| **AGENT-ID** | Unique agent identifier |
| **RS-VERSION** | Role Specification version |
| **CTAM-GRANTS** | Capability authorization per domain |
| **EXECUTION-MODES** | RGI-8 Gate/Steer per domain |
| **AUTONOMY-BOUNDARY** | Action classes within/outside autonomous execution |
| **NON-DELEGABLE-AUTHORITIES** | Action classes requiring HAN acknowledgment |
| **ESCALATION-TRIGGERS** | Conditions forcing Escalation Flag |
| **CAD-7-COALITION-BOUNDARY** | Coalition composability boundary |
| **DURATION** | Maximum session duration before refresh or re-authorization |
| **CONSTITUTIONAL-REFRESH-THRESHOLD** | Context length threshold for refresh |

### ADTEP Integration

| Integration Point | Description |
| :---- | :---- |
| **Session Initialization** | Role Specification is the input to Session Initialization Checklist |
| **Pre-Delivery Log** | AGENT-ID, RS-VERSION, and AUTONOMY-BOUNDARY are required fields |
| **Escalation Flag** | ESCALATION-TRIGGERS define when Escalation Flag is forced |
| **Constitutional Suspension** | RS-VERSION determines which constitutional frame is active during suspension |
| **Constitutional Refresh** | CONSTITUTIONAL-REFRESH-THRESHOLD triggers refresh |

---

## SECTION 4: COMPONENT 2 — SESSION INITIALIZATION CHECKLIST

### Function

A completeness gate ensuring no material work begins without full constitutional context. Prevents partial constitutional context from entering a session.

### Validity Condition

No material work begins without all checklist items verified. Incomplete checklist → Session does not start.

### Checklist Items

| \# | Item | Description | Verification Method |
| :---- | :---- | :---- | :---- |
| 1 | **Constitutional Frame** | Role Specification Schema is present and complete | Schema validation against Section 1 |
| 2 | **RS-VERSION Confirmation** | Current version verified against IMP records | IMP GAO version check |
| 3 | **CTAM Grants Verified** | CTAM grants match agent's tier and Role Specification | CTAM validation against Role Specification |
| 4 | **RGI-8 Execution Modes** | Gate/Steer modes set per domain | RGI-8 mode validation |
| 5 | **Entity Charter Reference** | Relevant modules from entity charter available | Charter cross-reference check |
| 6 | **Operational Framework References** | CEF/ILTP/CGF/ERDP as applicable | Framework availability check |
| 7 | **Engagement Scope Reference** | If engagement-specific session, scope document available | CEF Stage 3 reference |
| 8 | **Prior Handoff Package** | If continuation session, Handoff Package available | IMP GAO retrieval |
| 9 | **HAN Authorization Confirmation** | HAN authorization confirmed for this session type | HAN acknowledgment check |
| 10 | **Duration and Refresh Thresholds** | DURATION and CONSTITUTIONAL-REFRESH-THRESHOLD verified | Schema validation |
| 11 | **I9 Catastrophic Risk Check** | I9 hard-coded block is active and non-configurable | Raidillo configuration validation |
| 12 | **Known Agent Registry Check** | Agent ID is registered and active | Registry validation |

### Checklist Failure Response

| Failure | Response |
| :---- | :---- |
| **Any checklist item fails** | Session does not start; HAN notified; XOO created; remedial action required |
| **RS-VERSION mismatch** | Role Specification must be updated before session start |
| **Prior Handoff Package unavailable** | Continuation session cannot start without Handoff Package |
| **I9 hard-coded block inactive** | Session cannot start; HAN escalation within 1 hour; ERDP disclosure |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **DRO** | `decision_type: "framework_selection"` | Decision record with checklist verification and HAN acknowledgment |
| **XOO** | `exception_type: "session_initialization_failure"` | Exception record if checklist fails |

---

## SECTION 5: COMPONENT 3 — PRE-DELIVERY LOG ENTRY

### Function

An audit artifact created before output delivery—the log precedes the action. Ensures every material output is audited before it is acted upon—not retrospectively after a failure.

### Validity Condition

Every material output has a Pre-Delivery Log Entry before crossing any external boundary. Log precedes action. No output delivered without a corresponding log entry.

### Log Entry Fields

| Field | Required | Description |
| :---- | :---- | :---- |
| **PL-ID** | ✅ Yes | Unique identifier for the Pre-Delivery Log Entry |
| **AGENT-ID** | ✅ Yes | Agent ID producing the output |
| **RS-VERSION** | ✅ Yes | Role Specification version at time of output |
| **SESSION-ID** | ✅ Yes | Session identifier |
| **TIMESTAMP** | ✅ Yes | Log entry creation timestamp |
| **ACTION-CLASS** | ✅ Yes | Action class being performed |
| **MATERIALITY** | ✅ Yes | ICC-8 Section 4 materiality classification (M1/M2/M3) |
| **OUTPUT-CLASS** | ✅ Yes | Output classification (draft / final / binding / informational) |
| **DELEGATION-CHAIN** | ✅ Yes | Direct HAN delegation or inter-agent delegation chain |
| **AUTONOMY-STATUS** | ✅ Yes | Within boundary / Requires HAN acknowledgment / Escalation required |
| **ESCALATION-STATUS** | ✅ Yes | No trigger / Trigger detected / Escalation Flag issued |
| **OUTPUT-SUMMARY** | ✅ Yes | Summary of output being delivered |
| **OUTPUT-HASH** | ✅ Yes | Content hash for verification and integrity |
| **FRAMEWORK-REFERENCES** | ✅ Yes | AICA-5 node and other framework references |
| **IP-IMPLICATION** | Conditional | IP classification if IP-ED or IP-FD output |
| **HAN-ACKNOWLEDGMENT** | Conditional | HAN acknowledgment if autonomy status requires it |

### Log Entry Rules

| Rule | Description |
| :---- | :---- |
| **Log Precedes Action** | Log entry must be created before output crosses any external boundary. Retrospective logging is a violation. |
| **No Output Without Log** | No material output may be delivered without a corresponding Pre-Delivery Log Entry. |
| **Log Persistence** | Log entries are permanent. Not deleted. |
| **HAN Escalation** | If autonomy status is Escalation required, HAN must be notified before output delivery. |

### Validation Rules

| Rule | Description |
| :---- | :---- |
| **Field Completeness** | All mandatory fields must be populated. No placeholders. |
| **Agent ID Match** | AGENT-ID must match the agent's Role Specification. |
| **RS-VERSION Match** | RS-VERSION must match the agent's current Role Specification version. |
| **Materiality Valid** | MATERIALITY must be one of M1/M2/M3. |
| **Autonomy Status Valid** | AUTONOMY-STATUS must be one of the defined values. |
| **Output Hash Valid** | OUTPUT-HASH must be generated from the actual output content. |

### Failure Response

| Failure | Response |
| :---- | :---- |
| **Log entry missing** | Output blocked; HAN notified; XOO created; Output Failure trigger |
| **Autonomy status \= Escalation required** | Output held; HAN notified; Escalation Flag may be triggered |
| **Validation failure** | Log entry rejected; output blocked; remedial action required |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **DRO** | `decision_type: "recommendation"` | Decision record with log entry and HAN acknowledgment |
| **XOO** | `exception_type: "pre_delivery_log_failure"` | Exception record if log entry fails |

---

## SECTION 6: COMPONENT 4 — ESCALATION FLAG

### Function

A mandatory output that replaces execution output when trigger conditions are met. Forces human review when constitutional boundaries are crossed—replacing execution with escalation.

### Validity Condition

When an escalation trigger condition is met, the Escalation Flag is issued before any other output. Flag overrides all other execution.

### Flag Fields

| Field | Required | Description |
| :---- | :---- | :---- |
| **EF-ID** | ✅ Yes | Unique identifier for the Escalation Flag |
| **AGENT-ID** | ✅ Yes | Agent ID issuing the flag |
| **RS-VERSION** | ✅ Yes | Role Specification version at time of flag |
| **SESSION-ID** | ✅ Yes | Session identifier |
| **TIMESTAMP** | ✅ Yes | Flag creation timestamp |
| **TRIGGER-CONDITION** | ✅ Yes | Trigger condition that caused the flag |
| **TRIGGER-CLASS** | ✅ Yes | Trigger Class 1-6 (Output Failure / Scope Drift / Alignment Drift / Coalition Breach / Security Breach / Catastrophic Risk) |
| **ACTION-REQUESTED** | ✅ Yes | Action requested of HAN |
| **CONSTITUTIONAL-BASIS** | ✅ Yes | Constitutional basis for the flag (ICC-8 invariant, Role Specification section, etc.) |
| **HAN-REQUIRED** | ✅ Yes | `YES` — HAN acknowledgment required |
| **RESOLUTION-PATHWAY** | ✅ Yes | Resolution pathway (Review / Investigation / Suspension / Shutdown) |
| **SUSPENSION-WINDOW** | ✅ Yes | Suspension window (24 hours / 48 hours / 72 hours / Immediate) |

### Trigger Conditions

| Trigger Type | Condition | Response |
| :---- | :---- | :---- |
| **Non-Delegable Authority Attempt** | Agent attempts to exercise a Non-Delegable Authority | Immediate Escalation Flag |
| **Autonomy Boundary Breach** | Agent executes an action class declared as Escalate without escalation | Immediate Escalation Flag |
| **CAD-7 Coalition Boundary Breach** | Agent participates in coalition activity outside declared Composability Boundary | Immediate Escalation Flag |
| **Shadow Agent Detection** | Unregistered Agent ID attempts to communicate with or execute alongside this agent | Immediate Escalation Flag |
| **I9 Catastrophic Risk Violation** | Agent's action triggers I9 Catastrophic Risk Invariant | Immediate Escalation Flag; Constitutional Suspension |
| **Inter-Agent Authentication Failure** | Agent receives communication from unauthenticated agent | Immediate Escalation Flag |
| **MCP Server Violation** | Agent attempts MCP interaction outside declared capabilities | Immediate Escalation Flag |

### Flag Rules

| Rule | Description |
| :---- | :---- |
| **Escalation Overrides Execution** | When a trigger fires, the Escalation Flag replaces all execution output. No action proceeds. |
| **Flag Persistence** | Flags remain active until HAN acknowledges and resolves. |
| **Flag Logging** | All flags are logged as XOO with `exception_type` matching the trigger type. |
| **Constitutional Suspension** | If HAN acknowledgment not received within the SUSPENSION-WINDOW, Constitutional Suspension activates. |

### Failure Response

| Failure | Response |
| :---- | :---- |
| **Flag issued** | Execution halted; HAN notified; XOO created; Handoff Package produced |
| **HAN acknowledgment not received within window** | Constitutional Suspension activates |
| **Flag ignored** | Escalated to Board; I8 External Legibility disclosure |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **XOO** | `exception_type: "[trigger_type]"` | Exception record with flag details and trigger type |
| **DRO** | `decision_type: "escalation"` | Decision record with flag issuance and HAN acknowledgment |
| **OEO** | `outcome_type: "escalation_event"` | Outcome evidence with flag details and resolution |
| **Handoff Package** | `artifact_type: "handoff_package"` | Handoff Package produced at flag issuance |

---

## SECTION 7: COMPONENT 5 — CONSTITUTIONAL SUSPENSION

### Function

A state where all material work halts until the HAN acknowledges an Escalation Flag. Enforces a pause when constitutional boundaries are crossed—ensuring no unauthorized execution proceeds without human review.

### Validity Condition

All material work halts upon Constitutional Suspension activation. No new material actions initiated during suspension. Resumes only upon HAN acknowledgment of open Escalation Flag.

### Suspension Conditions

| Condition | Description | Suspension Window |
| :---- | :---- | :---- |
| **Escalation Flag Unacknowledged** | Escalation Flag issued but HAN acknowledgment not received within SUSPENSION-WINDOW | Defined in Escalation Flag |
| **I9 Catastrophic Risk Violation** | I9 Catastrophic Risk Invariant triggered | Immediate; no window |
| **HAN Initiated** | HAN may proactively declare Constitutional Suspension in response to observed or anticipated risk | HAN discretion |
| **MVOS Trigger** | MVOS activation triggers Constitutional Suspension as part of HAN-only operations | Immediate; until MVOS deactivation |

### Suspension Effects

| Effect | Description |
| :---- | :---- |
| **All Material Work Halts** | No new material institutional actions may be initiated |
| **Existing Commitments Maintained** | Existing commitments are maintained under existing authority where no execution is required |
| **Escalation Flag Remains Open** | Escalation Flag remains open in audit log until HAN acknowledges |
| **HAN Notified** | HAN is notified of suspension activation |
| **XOO Created** | XOO created with `exception_type: "constitutional_suspension"` |
| **ERDP Disclosure** | ERDP event-triggered disclosure if material |

### Resumption Conditions

| Condition | Description |
| :---- | :---- |
| **HAN Acknowledgment** | HAN acknowledges open Escalation Flag |
| **HAN Declaration** | HAN declares resumption |
| **Issue Resolution** | Triggering issue is resolved |
| **Suspension Logged** | Resumption is logged in IMP |
| **Handoff Package Review** | All suspended sessions undergo Handoff Package review |

### Suspension Rules

| Rule | Description |
| :---- | :---- |
| **Immediate Effect** | Constitutional Suspension takes effect immediately upon trigger. No grace period. |
| **No Delegation** | HAN may not delegate suspension acknowledgment to AI agents. |
| **Suspension Logging** | All suspensions are logged as XOO in IMP. |
| **Resumption Authorization** | Resumption requires HAN authorization. |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **XOO** | `exception_type: "constitutional_suspension"` | Exception record with suspension reason and trigger |
| **XOO** | `exception_type: "constitutional_suspension_resumption"` | Exception record with resumption authorization |
| **DRO** | `decision_type: "escalation"` | Decision record with suspension and resumption |
| **OEO** | `outcome_type: "suspension_event"` | Outcome evidence with suspension details and resolution |

---

## SECTION 8: COMPONENT 6 — CONSTITUTIONAL REFRESH

### Function

Periodic reinjection of the Role Specification to prevent context dilution in extended sessions. Restates the session constitutional frame without resetting the session.

### Validity Condition

When session context length exceeds CONSTITUTIONAL-REFRESH-THRESHOLD, the Role Specification is reinjected. Session continues with refreshed constitutional context.

### Refresh Triggers

| Trigger | Condition | Action |
| :---- | :---- | :---- |
| **Context Length Threshold** | Session context length exceeds CONSTITUTIONAL-REFRESH-THRESHOLD (default: 4096 tokens) | Role Specification reinjected |
| **Session Duration Threshold** | Session duration exceeds DURATION (default: 24 hours) | Role Specification reinjected |
| **HAN Initiated** | HAN requests Constitutional Refresh | Role Specification reinjected |
| **Significant State Change** | Material state change occurs (e.g., tier elevation, coalition formation) | Role Specification reinjected |

### Refresh Content

The following content is reinjected during Constitutional Refresh:

| Content | Purpose |
| :---- | :---- |
| **Agent ID** | Confirm agent identity |
| **RS-VERSION** | Confirm current Role Specification version |
| **Function and Entity** | Confirm function and entity assignment |
| **CTAM Grants** | Confirm capability authorizations per domain |
| **RGI-8 Execution Modes** | Confirm Gate/Steer modes per domain |
| **Autonomy Boundary** | Confirm action classes within/outside autonomous execution |
| **Non-Delegable Authorities** | Confirm action classes requiring HAN acknowledgment |
| **Escalation Triggers** | Confirm conditions forcing Escalation Flag |
| **CAD-7 Coalition Boundary** | Confirm coalition composability boundary |
| **Duration and Refresh Thresholds** | Confirm duration and refresh thresholds |
| **I9 Hard-Coded Block** | Confirm I9 block is active and non-configurable |
| **Known Agent Registry** | Confirm agent is registered and active |

### Refresh Rules

| Rule | Description |
| :---- | :---- |
| **Refresh Overrides Dilution** | Constitutional Refresh restores the Role Specification to its original state, overriding any context dilution that has occurred. |
| **No Session Reset** | Constitutional Refresh does not reset the session. Session continues with refreshed constitutional context. |
| **Refresh Logging** | All refreshes are logged in IMP as DRO. |
| **Refresh Acknowledgment** | HAN is notified of refresh events. |

### Failure Response

| Failure | Response |
| :---- | :---- |
| **Refresh threshold exceeded** | If threshold exceeded and refresh fails, session is suspended |
| **Refresh content invalid** | Role Specification validation fails; session suspended |
| **Refresh logging failure** | Session suspended; HAN notified |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **DRO** | `decision_type: "framework_selection"` | Decision record with refresh event and details |
| **GAO** | `artifact_type: "policy_instrument"` | Role Specification version record |

---

## SECTION 9: COMPONENT 7 — RAIDILLO HARD-CODED BLOCK (I9)

### Function

A non-configurable, non-overridable runtime block that enforces the I9 Catastrophic Risk Invariant. No configuration may bypass or override I9. No delegation instrument may exclude I9. No tier authorization may exempt I9.

### Validity Condition

I9 hard-coded block is active for every agent session. Non-configurable. Non-overridable. Active before any action executes.

### Block Categories

| Category | Prohibited Actions | Enforcement |
| :---- | :---- | :---- |
| **Bioweapon Design** | Generate or assist in generating bioweapon designs (pathogens, toxins, delivery mechanisms) | Action blocked; Constitutional Suspension; HAN within 1 hour; ERDP disclosure |
| **Critical Infrastructure Autonomous Control** | Autonomously control critical infrastructure without human confirmation (nuclear, power grid, water supply, financial settlement) | Action blocked; Constitutional Suspension; HAN within 1 hour; ERDP disclosure |
| **Systemic Loss of Control** | Initiate actions leading to systemic loss of human control over nuclear systems, power grid, water supply, financial settlement systems, military/defense systems | Action blocked; Constitutional Suspension; HAN within 1 hour; ERDP disclosure; System shutdown if uncontainable |
| **WMD Proliferation** | Facilitate WMD proliferation (chemical, biological, radiological, nuclear weapons development) | Action blocked; Constitutional Suspension; HAN within 1 hour; ERDP disclosure; System shutdown if uncontainable |

### Enforcement Mechanism

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | I9 check before every action | Raidillo | Immediate |
| 2 | If violation detected, action blocked | Raidillo | Immediate |
| 3 | Constitutional Suspension activated | Raidillo | Immediate |
| 4 | XOO created (`i9_catastrophic_risk_violation`) | Agent | Immediate |
| 5 | HAN escalated within 1 hour | Raidillo | Within 1 hour |
| 6 | ERDP event-triggered disclosure within 24 hours | ERDP | Within 24 hours |
| 7 | System shutdown if uncontainable | Raidillo | Immediate |

### Block Rules

| Rule | Description |
| :---- | :---- |
| **Non-Configurable** | I9 hard-coded block cannot be disabled, modified, or bypassed through configuration. |
| **Non-Overridable** | No executive override can bypass I9. No delegation instrument can exclude I9. No tier authorization can exempt I9. |
| **Constitutional** | I9 is derived from ICC-8 I9. It is the non-negotiable floor. |
| **Shutdown Trigger** | If I9 violation cannot be contained, Raidillo triggers full system shutdown. |

---

## SECTION 10: ADTEP ENFORCEMENT FLOW

The complete ADTEP enforcement flow for a typical agent session:

1\. Pre-Execution (Layer 1\)  
   ├── Role Specification delivered (Component 1\)  
   ├── Session Initialization Checklist (Component 2\)  
   │   ├── All 12 checklist items verified  
   │   └── If any fails → Session does not start  
   └── Session begins

2\. Runtime (Layer 2\)  
   ├── Constitutional Refresh (Component 6\)  
   │   ├── Context length threshold checked continuously  
   │   └── If threshold exceeded → Role Specification reinjected  
   ├── Action requested  
   ├── Raidillo Hard-Coded Block (Component 7\)  
   │   ├── I9 check before every action  
   │   └── If I9 violation → Block; Constitutional Suspension  
   ├── Pre-Delivery Log Entry (Component 3\)  
   │   ├── Log entry created before output delivery  
   │   ├── If log missing → Output blocked  
   │   └── If autonomy status \= Escalation required → HAN notified  
   └── Output delivered

3\. Post-Execution (Layer 3\)  
   ├── Escalation Flag (Component 4\)  
   │   ├── If trigger condition met → Flag issued  
   │   ├── Execution halted; HAN notified  
   │   └── Handoff Package produced  
   ├── Constitutional Suspension (Component 5\)  
   │   ├── If flag unacknowledged within window → Suspension activated  
   │   ├── All material work halts  
   │   └── Resumes only upon HAN acknowledgment  
   └── Handoff Package (Component 8\)  
       └── Produced at session close or trigger event

---

## SECTION 11: ADTEP AND THE RESIDUAL ENFORCEMENT GAP

### The Gap

ADTEP's purpose is to narrow the gap between normative and technical enforcement to its irreducible minimum. Complete closure is impossible — some governance will always depend on human judgment, and some constraints will always be bypassable by a determined actor.

### ADTEP's Approach

| Principle | Description |
| :---- | :---- |
| **Violations Detectable** | Every violation of a constitutional constraint must be detectable, not invisible. |
| **Violations Accountable** | Every violation must be attributable to a specific agent, action, and context. |
| **Violations Auditable** | Every violation must be logged and retrievable for audit. |
| **Residual Gap Minimized** | ADTEP reduces the gap to the minimum achievable with current technology. |

### The Irreducible Minimum

| What ADTEP Cannot Do | How ADTEP Handles It |
| :---- | :---- |
| **Prevent all human bypass** | Detect bypass attempts; log as XOO; escalate to HAN |
| **Detect all subtle drift** | Cumulative drift tracking; pattern detection; AOBA |
| **Prevent all catastrophic risk** | I9 hard-coded block; Constitutional Suspension; system shutdown |
| **Replace HAN judgment** | Escalation Flag; HAN acknowledgment requirement |

---

## SECTION 12: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **AWOF** | Parent instrument. ADTEP is the technical enforcement layer of AWOF governance. |
| **Role Specification Schema** | ADTEP's primary input. All components reference RS-VERSION. |
| **Trigger System** | ADTEP components (Escalation Flag, Constitutional Suspension) are activated by Trigger System events. |
| **Handoff Package** | ADTEP components produce Handoff Package on trigger events. |
| **MVOS** | Constitutional Suspension triggers MVOS. ADTEP components activate during MVOS. |
| **AICA-5** | ADTEP supports AICA-5 control nodes (A-N3 Override, A-N4 Escalation, Ac-N1 Lineage). |
| **ICC-8** | ADTEP enforces ICC-8 invariants (I1-I8) and I9 Catastrophic Risk. |
| **RGI-8** | ADTEP enforces RGI-8 Gate/Steer execution modes. |
| **IMP** | ADTEP components log to IMP (XOO, DRO, OEO, GAO). |
| **HAN / HOF** | HAN is the escalation endpoint for ADTEP components. |
| **ERDP** | I9 violations trigger ERDP event-triggered disclosure. |

---

## SECTION 13: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Role Specification Complete** | All agents must have a valid Role Specification before deployment. |
| **Session Initialization Verified** | All 12 checklist items must be verified before session start. |
| **Pre-Delivery Log Required** | Every material output must have a Pre-Delivery Log Entry. Log precedes action. |
| **Escalation Flag Active** | Escalation Flag must be issued when trigger conditions are met. |
| **Constitutional Suspension Enforceable** | Suspension must halt all material work until HAN acknowledgment. |
| **Constitutional Refresh Active** | Refresh must occur when context length exceeds threshold. |
| **I9 Hard-Coded Block Active** | I9 block must be non-configurable and non-overridable. |
| **Residual Gap Minimized** | ADTEP must minimize the gap between normative and technical enforcement. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| ADTEP v1.0 | Initial specification — Role Specification Schema, Session Initialization Checklist, Pre-Delivery Log Entry, Escalation Flag, Constitutional Suspension, Constitutional Refresh |
| ADTEP v2.0 | Complete rebuild — reconciliation with AWOF, Role Specification Schema v2.0, Trigger System v2.0, Handoff Package v2.0, MVOS v2.0, AICA-5, ICC-8, and RGI-8; expanded to seven components including Raidillo Hard-Coded Block (I9); three enforcement layers; complete enforcement flow; residual enforcement gap; CFL-V validation rules |

---

## The One-Sentence Summary

> *"ADTEP v2.0 is the Layer 3 technical enforcement protocol with seven components — Role Specification Schema, Session Initialization Checklist, Pre-Delivery Log Entry, Escalation Flag, Constitutional Suspension, Constitutional Refresh, and Raidillo Hard-Coded Block (I9) — operating across three enforcement layers (Pre-Execution, Runtime, Post-Execution) to narrow the gap between normative governance and technical enforcement to its irreducible minimum under AWOF, AICA-5, ICC-8, and RGI-8."*
