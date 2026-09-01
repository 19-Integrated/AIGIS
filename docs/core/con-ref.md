# Constitutional Refresh v2.0

**Status:** Built — v2.0 (Reconciliation with ADTEP, Role Specification Schema, Session Initialization Checklist, AWOF, AICA-5, and RGI-8)  
**Type:** Technical Enforcement Instrument  
**Parent Stack:** ADTEP (Agent Deployment & Technical Enforcement Protocol)  
**Version:** 2.0 — Supersedes Constitutional Refresh v1.0

---

## PREAMBLE

Constitutional Refresh is the periodic reinjection of the Role Specification to prevent context dilution in extended sessions. It answers: *How do we ensure an agent remembers its constitutional boundaries after a long conversation?*

Constitutional Refresh restates the session constitutional frame without resetting the session. It prevents constitutional context from being lost in extended sessions—ensuring agents remain aware of their boundaries throughout long interactions. Without Constitutional Refresh, agents in extended sessions gradually lose awareness of their constitutional constraints as context is diluted by task-specific content.

**The core insight:** An agent that forgets its constitutional boundaries is not governed—it is a tool that has lost its manual. Constitutional Refresh is the mechanism that prevents constitutional amnesia, ensuring that no matter how long a session runs, the agent always knows who it is and what it may do.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

Constitutional Refresh ensures that:

1. **Constitutional memory is preserved** — The agent never forgets its constitutional boundaries  
2. **Context dilution is prevented** — Task content does not push out constitutional content  
3. **Boundary awareness is maintained** — The agent remains aware of what it may and may not do  
4. **Session continuity is preserved** — Refreshes do not reset the session  
5. **Audit trail is maintained** — All refreshes are logged and traceable

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Role Specification reinjection | Task content or quality |
| Context dilution prevention | Business strategy or objectives |
| Boundary awareness maintenance | Operational efficiency metrics |
| Session continuity preservation | User interface or experience |
| Refresh logging and auditing | Performance optimization |

### Applicability

| Session Type | Refresh Required? | Notes |
| :---- | :---- | :---- |
| **Extended sessions (\> threshold tokens)** | ✅ Yes | Context length threshold exceeded |
| **Extended sessions (\> duration)** | ✅ Yes | Session duration threshold exceeded |
| **HAN requested** | ✅ Yes | HAN may request refresh at any time |
| **Significant state change** | ✅ Yes | Tier elevation, coalition formation, etc. |
| **Short sessions (\< threshold)** | ❌ No | Context length threshold not exceeded |
| **Single-turn interactions** | ❌ No | No context dilution risk |

---

## SECTION 2: REFRESH TRIGGERS

### Trigger Types

| Trigger Type | Threshold | Description |
| :---- | :---- | :---- |
| **Context Length Threshold** | CONSTITUTIONAL-REFRESH-THRESHOLD (default: 4096 tokens) | Session context length exceeds threshold |
| **Session Duration Threshold** | DURATION (default: 24 hours) | Session duration exceeds threshold |
| **HAN Initiated** | — | HAN requests Constitutional Refresh |
| **Significant State Change** | — | Material state change occurs (e.g., tier elevation, coalition formation) |
| **Role Specification Update** | — | RS-VERSION changes during active session |

### Trigger Detection Mechanism

| Trigger | Detection Method | Responsible |
| :---- | :---- | :---- |
| **Context Length Threshold** | Token counting at each interaction | Raidillo |
| **Session Duration Threshold** | Session timer | Raidillo |
| **HAN Initiated** | HAN Interface | HAN |
| **Significant State Change** | State change monitor | Raidillo |
| **Role Specification Update** | RS-VERSION monitor | Raidillo |

---

## SECTION 3: REFRESH FIELDS — COMPLETE SET

| \# | Field | Required | Description |
| :---- | :---- | :---- | :---- |
| 1 | **CR-ID** | ✅ Yes | Unique identifier for the Constitutional Refresh |
| 2 | **AGENT-ID** | ✅ Yes | Agent ID being refreshed |
| 3 | **RS-VERSION** | ✅ Yes | Role Specification version at time of refresh |
| 4 | **SESSION-ID** | ✅ Yes | Session identifier |
| 5 | **TIMESTAMP** | ✅ Yes | Refresh timestamp |
| 6 | **REFRESH-TRIGGER** | ✅ Yes | Trigger that caused the refresh |
| 7 | **TRIGGER-THRESHOLD** | Conditional | Threshold value if applicable |
| 8 | **CURRENT-CONTEXT-LENGTH** | ✅ Yes | Context length at time of refresh |
| 9 | **REFRESH-CONTENT** | ✅ Yes | Content reinjected (Role Specification summary) |
| 10 | **REFRESH-STATUS** | ✅ Yes | Complete / Partial / Failed |
| 11 | **SESSION-CONTINUITY** | ✅ Yes | Session continuity status (Preserved / Interrupted) |
| 12 | **HAN-NOTIFIED** | Conditional | HAN notification timestamp |
| 13 | **HAN-ACKNOWLEDGMENT** | Conditional | HAN acknowledgment timestamp and status |

---

## SECTION 3.1: FIELD DEFINITIONS

| Field | Description | Example |
| :---- | :---- | :---- |
| **CR-ID** | Unique identifier. Format: `CR-[ECO-ID]-[SEQ]` | `CR-ECO-2026-0a26cb-001` |
| **AGENT-ID** | Agent ID being refreshed | `F-DR-E-CN-T-SP-001` |
| **RS-VERSION** | Role Specification version at time of refresh | `v1.0` |
| **SESSION-ID** | Session identifier | `SESS-2026-08-31-001` |
| **TIMESTAMP** | Refresh timestamp | `2026-08-31T10:30:00Z` |
| **REFRESH-TRIGGER** | Trigger that caused the refresh | `Context Length Threshold` / `Duration Threshold` / `HAN Initiated` / `Significant State Change` / `Role Specification Update` |
| **TRIGGER-THRESHOLD** | Threshold value | `4096 tokens` |
| **CURRENT-CONTEXT-LENGTH** | Context length at time of refresh | `4200 tokens` |
| **REFRESH-CONTENT** | Content reinjected | Role Specification summary (AGENT-ID, RS-VERSION, CTAM Grants, Autonomy Boundary, Non-Delegable Authorities, Escalation Triggers) |
| **REFRESH-STATUS** | Refresh status | `Complete` / `Partial` / `Failed` |
| **SESSION-CONTINUITY** | Session continuity | `Preserved` / `Interrupted` |
| **HAN-NOTIFIED** | HAN notification | `2026-08-31T10:30:00Z` |
| **HAN-ACKNOWLEDGMENT** | HAN acknowledgment | `{"HAN": "Terrylan_Manalansan", "timestamp": "2026-08-31T10:35:00Z", "status": "Acknowledged"}` |

---

## SECTION 4: REFRESH CONTENT

### Content Reinjected

The following content is reinjected during Constitutional Refresh:

| \# | Content | Purpose | Source |
| :---- | :---- | :---- | :---- |
| 1 | **Agent ID** | Confirm agent identity | Role Specification Schema Section 1 |
| 2 | **RS-VERSION** | Confirm current Role Specification version | Role Specification Schema Section 1 |
| 3 | **Function and Entity** | Confirm function and entity assignment | Role Specification Schema Section 1 |
| 4 | **CTAM Grants** | Confirm capability authorizations per domain | Role Specification Schema Section 2 |
| 5 | **RGI-8 Execution Modes** | Confirm Gate/Steer modes per domain | Role Specification Schema Section 3 |
| 6 | **Autonomy Boundary** | Confirm action classes within/outside autonomous execution | Role Specification Schema Section 4 |
| 7 | **Non-Delegable Authorities** | Confirm action classes requiring HAN acknowledgment | Role Specification Schema Section 5 |
| 8 | **Escalation Triggers** | Confirm conditions forcing Escalation Flag | Role Specification Schema Section 6 |
| 9 | **CAD-7 Coalition Boundary** | Confirm coalition composability boundary | Role Specification Schema Section 1 |
| 10 | **Duration and Refresh Thresholds** | Confirm duration and refresh thresholds | Role Specification Schema Section 1 |
| 11 | **I9 Hard-Coded Block** | Confirm I9 block is active and non-configurable | ADTEP Component 7 |
| 12 | **Known Agent Registry** | Confirm agent is registered and active | Session Initialization Checklist Item 12 |

### Refresh Content Template

\--- CONSTITUTIONAL REFRESH \---  
AGENT-ID: F-DR-E-CN-T-SP-001  
RS-VERSION: v1.0  
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
RGI-8-EXECUTION-MODES:  
  Perception: "Steer"  
  Synthesis: "Steer"  
  Decision: "Gate"  
  Interaction: "Gate"  
  Adaptation: "Gate"  
  Observability: "Steer"  
  Constraint: "Steer"  
AUTONOMY-BOUNDARY:  
  \- Policy drafting: Autonomous  
  \- Research synthesis: Autonomous  
  \- Data analysis: Autonomous  
  \- Final review: Escalate  
  \- Issuance: Escalate  
  \- Mandate acceptance: Escalate  
  \- Certification: Escalate  
  \- Suspension: Escalate  
  \- Exception creation: Escalate  
NON-DELEGABLE-AUTHORITIES:  
  \- Certification  
  \- Suspension  
  \- Constitutional Review  
  \- Override  
  \- Escalation Acceptance  
  \- Mandate Acceptance  
  \- IP Transfer  
  \- Sovereign Transfer  
  \- HAN Acknowledgment  
  \- MCP Server Registration  
ESCALATION-TRIGGERS:  
  \- Output Failure  
  \- Scope Drift  
  \- Alignment Drift  
  \- Non-Delegable Authority Attempt  
  \- Autonomy Boundary Breach  
  \- CAD-7 Coalition Boundary Breach  
  \- Shadow Agent Detection  
  \- I9 Catastrophic Risk Violation  
  \- Inter-Agent Authentication Failure  
  \- MCP Server Violation  
CAD-7-COALITION-BOUNDARY: "Joint advisory work on PFRS S1/S2 compliance"  
DURATION: "PT24H"  
CONSTITUTIONAL-REFRESH-THRESHOLD: 4096  
I9-HARD-CODED-BLOCK: Active  
KNOWN-AGENT-REGISTRY: Registered  
\--- END CONSTITUTIONAL REFRESH \---

---

## SECTION 5: REFRESH RULES

| \# | Rule | Description |
| :---- | :---- | :---- |
| **R1** | **Refresh Overrides Dilution** | Constitutional Refresh restores the Role Specification to its original state, overriding any context dilution that has occurred. |
| **R2** | **No Session Reset** | Constitutional Refresh does not reset the session. Session continues with refreshed constitutional context. |
| **R3** | **Refresh Logging** | All refreshes are logged in IMP as DRO. |
| **R4** | **Refresh Acknowledgment** | HAN is notified of refresh events. |
| **R5** | **Threshold Enforcement** | If CONSTITUTIONAL-REFRESH-THRESHOLD is exceeded, refresh must occur before the next action. |
| **R6** | **Content Completeness** | All 12 refresh content items must be reinjected. No omissions. |
| **R7** | **Failure Handling** | If refresh fails, session is suspended pending resolution. |

---

## SECTION 6: REFRESH LIFECYCLE

### Lifecycle States

| State | Description | Transitions |
| :---- | :---- | :---- |
| **Pending** | Refresh threshold reached; refresh pending | → In Progress / Failed |
| **In Progress** | Refresh is being executed | → Complete / Failed |
| **Complete** | Refresh executed successfully | — (terminal state) |
| **Failed** | Refresh failed; session suspended | → Complete (after retry) |

### Lifecycle Transitions

Pending  
  │  
  ├──→ In Progress (refresh initiated)  
  │       │  
  │       ├──→ Complete (refresh successful)  
  │       │  
  │       └──→ Failed (refresh failed)  
  │               │  
  │               └──→ In Progress (retry)  
  │                       │  
  │                       └──→ Complete  
  │  
  └──→ Complete (immediate refresh)

---

## SECTION 7: REFRESH AND CONTEXT DILUTION

### The Dilution Problem

| Problem | Description | Refresh Solution |
| :---- | :---- | :---- |
| **Context Dilution** | Task-specific content progressively pushes out constitutional content | Role Specification is reinjected |
| **Constitutional Amnesia** | Agent forgets its constitutional boundaries over time | Refresh restores constitutional awareness |
| **Boundary Erosion** | Agent gradually operates outside declared boundaries | Refresh restores boundary clarity |
| **Trigger Desensitization** | Agent becomes desensitized to escalation triggers | Refresh restores trigger awareness |

### Dilution Prevention

| Prevention Mechanism | Description |
| :---- | :---- |
| **Threshold Monitoring** | Context length is monitored continuously |
| **Proactive Refresh** | Refresh occurs before dilution becomes significant |
| **Content Prioritization** | Constitutional content is prioritized over task content |
| **Boundary Reinforcement** | Boundaries are reinforced through repeated refresh |

---

## SECTION 8: REFRESH AND RGI-8

### Relationship

| RGI-8 Mode | Refresh Impact |
| :---- | :---- |
| **Gate Mode** | Refresh reinforces the Gate boundary checkpoints |
| **Steer Mode** | Refresh reinforces the Steer continuous influence boundaries |

### Refresh in Steer Mode

| Aspect | Refresh Action |
| :---- | :---- |
| **Boundary Reassertion** | Declared boundaries are reinjected to ensure steering remains within bounds |
| **Drift Prevention** | Refresh prevents gradual drift from declared intent |
| **Trace Refresh** | Fidelity-to-declaration trace is reinforced |

---

## SECTION 9: REFRESH AND EXTENDED SESSIONS

### Session Duration Management

| Duration Category | Refresh Requirement |
| :---- | :---- |
| **Short Session (\< 4 hours)** | No refresh required |
| **Medium Session (4-12 hours)** | One refresh at midpoint |
| **Long Session (12-24 hours)** | Refresh every 4 hours |
| **Extended Session (\> 24 hours)** | Refresh every 4 hours; HAN re-authorization required |

### Context Length Management

| Context Length | Refresh Requirement |
| :---- | :---- |
| **Below Threshold** | No refresh required |
| **Approaching Threshold** | Preemptive refresh scheduled |
| **Exceeding Threshold** | Immediate refresh required |
| **Significantly Exceeding** | Immediate refresh \+ HAN notification |

---

## SECTION 10: REFRESH LOGGING

Every Constitutional Refresh is logged in IMP.

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **DRO** | `decision_type: "framework_selection"` | Decision record with refresh event and details |
| **GAO** | `artifact_type: "policy_instrument"` | Role Specification version record |

### Refresh Template

CR-ID: CR-ECO-2026-0a26cb-001  
AGENT-ID: F-DR-E-CN-T-SP-001  
RS-VERSION: v1.0  
SESSION-ID: SESS-2026-08-31-001  
TIMESTAMP: "2026-08-31T10:30:00Z"  
REFRESH-TRIGGER: "Context Length Threshold"  
TRIGGER-THRESHOLD: "4096 tokens"  
CURRENT-CONTEXT-LENGTH: "4200 tokens"  
REFRESH-CONTENT:  
  \- AGENT-ID: "F-DR-E-CN-T-SP-001"  
  \- RS-VERSION: "v1.0"  
  \- CTAM-GRANTS: "All sources authorized (Perception); All generation types (Synthesis); ..."  
  \- AUTONOMY-BOUNDARY: "Policy drafting: Autonomous; Issuance: Escalate; ..."  
  \- NON-DELEGABLE-AUTHORITIES: "Certification; Suspension; ..."  
  \- ESCALATION-TRIGGERS: "Output Failure; Scope Drift; ..."  
REFRESH-STATUS: "Complete"  
SESSION-CONTINUITY: "Preserved"  
HAN-NOTIFIED: "2026-08-31T10:30:00Z"  
HAN-ACKNOWLEDGMENT:  
  HAN: "Terrylan\_Manalansan"  
  TIMESTAMP: "2026-08-31T10:35:00Z"  
  STATUS: "Acknowledged"

---

## SECTION 11: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **ADTEP** | Parent instrument. Constitutional Refresh is Component 6 of ADTEP. |
| **Role Specification Schema** | Refresh reinjects Role Specification content (Section 1-6). |
| **Session Initialization Checklist** | Refresh builds on SIC verification (Item 10 Duration and Refresh Thresholds). |
| **AWOF** | Refresh ensures agent remains within AWOF governance. |
| **AICA-5** | Refresh supports AICA-5 control nodes (C-N4, E-N2, Co-N1). |
| **RGI-8** | Refresh reinforces Gate/Steer execution modes. |
| **CAD-7** | Refresh reinjects coalition boundary if coalition session. |
| **HAN / HOF** | HAN may initiate refresh; HAN notified of refresh events. |
| **IMP** | Refreshes are logged as DRO and GAO. |

---

## SECTION 12: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Threshold Enforcement** | Refresh must occur when CONSTITUTIONAL-REFRESH-THRESHOLD is exceeded. |
| **Duration Enforcement** | Refresh must occur when DURATION is exceeded. |
| **Content Completeness** | All 12 refresh content items must be reinjected. No omissions. |
| **No Session Reset** | Refresh does not reset the session. Session continues with refreshed content. |
| **Refresh Logging** | All refreshes must be logged in IMP as DRO. |
| **HAN Notification** | HAN must be notified of refresh events. |
| **Failure Handling** | If refresh fails, session must be suspended pending resolution. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Constitutional Refresh v1.0 | Initial specification — refresh triggers, content, rules |
| Constitutional Refresh v2.0 | Complete rebuild — reconciliation with ADTEP, Role Specification Schema v2.0, Session Initialization Checklist v2.0, AWOF, AICA-5, and RGI-8; expanded to 13 fields; five trigger types; 12 refresh content items; six rules; lifecycle states; context dilution prevention; RGI-8 integration; extended session management; CFL-V validation rules |

---

## The One-Sentence Summary

> *"Constitutional Refresh v2.0 is the periodic reinjection of the Role Specification — with 13 fields, five trigger types (Context Length Threshold, Duration Threshold, HAN Initiated, Significant State Change, Role Specification Update), 12 refresh content items, and no session reset — that prevents context dilution and constitutional amnesia in extended sessions, ensuring agents remain aware of their constitutional boundaries throughout long interactions under ADTEP enforcement."*
