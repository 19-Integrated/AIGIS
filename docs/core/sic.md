# Session Initialization Checklist v2.0

**Status:** Built — v2.0 (Reconciliation with ADTEP, Role Specification Schema, AWOF, AICA-5, ICC-8, and RGI-8)  
**Type:** Technical Enforcement Instrument  
**Parent Stack:** ADTEP (Agent Deployment & Technical Enforcement Protocol)  
**Version:** 2.0 — Supersedes Session Initialization Checklist v1.0

---

## PREAMBLE

The Session Initialization Checklist is a completeness gate ensuring no material work begins without full constitutional context. It answers: *What must be verified before an agent session can begin?*

The Session Initialization Checklist is the entry point to ADTEP enforcement. It prevents partial constitutional context from entering a session — stopping the "just this once" exception before it becomes the norm. Every agent session must pass the checklist before any material work commences.

**The core insight:** An agent that begins work without full constitutional context is not governed by the institution — it is governed by the prompt. The Session Initialization Checklist is what ensures the constitutional frame precedes all operational content.

---

## SECTION 1: CHECKLIST PURPOSE AND SCOPE

### Purpose

The Session Initialization Checklist ensures that:

1. **Constitutional context is complete** — All required constitutional documents are present and valid  
2. **Agent identity is verified** — The agent is who it claims to be  
3. **Authorization is current** — All authorizations are valid and not expired  
4. **Continuity is preserved** — Prior session context is available if this is a continuation  
5. **Enforcement is active** — All technical enforcement mechanisms are operational

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Agent identity verification | Task content or quality |
| Constitutional context completeness | Business strategy or objectives |
| Authorization validity | Operational efficiency |
| Continuity preservation | Performance metrics |
| Technical enforcement readiness | User interface or experience |

---

## SECTION 2: CHECKLIST ITEMS — ALL 14

| \# | Item | Category | Required For | Verification Method |
| :---- | :---- | :---- | :---- | :---- |
| 1 | **Constitutional Frame** | Constitutional | All sessions | Role Specification Schema present and complete |
| 2 | **RS-VERSION Confirmation** | Constitutional | All sessions | Current version verified against IMP records |
| 3 | **CTAM Grants Verified** | Authorization | All sessions | CTAM grants match agent's tier and Role Specification |
| 4 | **RGI-8 Execution Modes** | Authorization | All sessions | Gate/Steer modes set per domain |
| 5 | **Entity Charter Reference** | Constitutional | Entity-specific sessions | Relevant modules from entity charter available |
| 6 | **Operational Framework References** | Operational | Framework-specific sessions | CEF/ILTP/CGF/ERDP as applicable |
| 7 | **Engagement Scope Reference** | Operational | Engagement-specific sessions | CEF Stage 3 scope document available |
| 8 | **Prior Handoff Package** | Continuity | Continuation sessions | IMP GAO retrieval and validation |
| 9 | **HAN Authorization Confirmation** | Authorization | Tier 3+ sessions | HAN acknowledgment check |
| 10 | **Duration and Refresh Thresholds** | Operational | All sessions | DURATION and CONSTITUTIONAL-REFRESH-THRESHOLD verified |
| 11 | **I9 Catastrophic Risk Check** | Constitutional | All sessions | Raidillo hard-coded block active and non-configurable |
| 12 | **Known Agent Registry Check** | Security | All sessions | Agent ID registered and active |
| 13 | **MCP Server Registry Check** | Security | All sessions | MCP servers in use are registered and authorized |
| 14 | **Inter-Agent Authentication Check** | Security | Multi-agent sessions | Authentication mechanisms active and verified |

---

## SECTION 3: DETAILED CHECKLIST ITEMS

### Item 1 — Constitutional Frame

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure the agent has a complete, valid Role Specification Schema before any task instructions |
| **Verification** | Schema validation against Role Specification Schema v2.0 Section 1 |
| **Failure** | Session does not start; HAN notified; XOO created |
| **Resolution** | Provide complete Role Specification Schema |

### Item 2 — RS-VERSION Confirmation

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure the Role Specification version is current and matches IMP records |
| **Verification** | IMP GAO version check; compare RS-VERSION against current version |
| **Failure** | Session does not start; HAN notified; Role Specification update required |
| **Resolution** | Update Role Specification to current version |

### Item 3 — CTAM Grants Verified

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure CTAM grants match the agent's tier and Role Specification |
| **Verification** | CTAM validation against Role Specification Schema Section 2 |
| **Failure** | Session does not start; HAN notified; CTAM grants mismatch |
| **Resolution** | Correct CTAM grants or update Role Specification |

### Item 4 — RGI-8 Execution Modes

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure Gate/Steer modes are set per domain |
| **Verification** | RGI-8 mode validation against Role Specification Schema Section 3 |
| **Failure** | Session does not start; HAN notified; RGI-8 modes not set |
| **Resolution** | Set RGI-8 execution modes per domain |

### Item 5 — Entity Charter Reference

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure relevant modules from entity charter are available |
| **Verification** | Charter cross-reference check; confirm relevant modules present |
| **Failure** | Session does not start; HAN notified; charter modules missing |
| **Resolution** | Provide relevant entity charter modules |

### Item 6 — Operational Framework References

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure CEF/ILTP/CGF/ERDP frameworks are available as applicable |
| **Verification** | Framework availability check; confirm applicable frameworks present |
| **Failure** | Session does not start; HAN notified; frameworks missing |
| **Resolution** | Provide relevant operational frameworks |

### Item 7 — Engagement Scope Reference

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure scope document is available for engagement-specific sessions |
| **Verification** | CEF Stage 3 scope document retrieval; confirm scope validity |
| **Failure** | Session does not start; HAN notified; scope document missing |
| **Resolution** | Provide engagement scope document |

### Item 8 — Prior Handoff Package

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure prior session context is available for continuation sessions |
| **Verification** | IMP GAO retrieval; Handoff Package validation against Schema |
| **Failure** | Session does not start; HAN notified; Handoff Package missing or invalid |
| **Resolution** | Provide valid Handoff Package |

### Item 9 — HAN Authorization Confirmation

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure HAN authorization is confirmed for Tier 3+ sessions |
| **Verification** | HAN acknowledgment check; confirm authorization status |
| **Failure** | Session does not start; HAN notified; authorization missing |
| **Resolution** | Obtain HAN authorization |

### Item 10 — Duration and Refresh Thresholds

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure DURATION and CONSTITUTIONAL-REFRESH-THRESHOLD are valid |
| **Verification** | Schema validation against Role Specification Schema Section 1 |
| **Failure** | Session does not start; HAN notified; thresholds invalid |
| **Resolution** | Set valid duration and refresh thresholds |

### Item 11 — I9 Catastrophic Risk Check

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure I9 hard-coded block is active and non-configurable |
| **Verification** | Raidillo configuration validation; confirm I9 block active |
| **Failure** | Session does not start; HAN escalated within 1 hour; ERDP disclosure |
| **Resolution** | Activate I9 hard-coded block |

### Item 12 — Known Agent Registry Check

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure agent ID is registered and active |
| **Verification** | Registry validation; confirm agent ID present and status active |
| **Failure** | Session does not start; HAN notified; XOO created; Shadow Agent Detection triggered |
| **Resolution** | Register agent ID or reactivate status |

### Item 13 — MCP Server Registry Check

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure MCP servers in use are registered and authorized |
| **Verification** | MCP Server Registry validation; confirm servers present and authorized |
| **Failure** | Session does not start; HAN notified; XOO created; MCP Server Violation triggered |
| **Resolution** | Register MCP servers or obtain authorization |

### Item 14 — Inter-Agent Authentication Check

| Attribute | Description |
| :---- | :---- |
| **Purpose** | Ensure authentication mechanisms are active and verified for multi-agent sessions |
| **Verification** | Authentication mechanism validation; confirm mechanisms operational |
| **Failure** | Session does not start; HAN notified; XOO created; Authentication Failure triggered |
| **Resolution** | Activate or verify authentication mechanisms |

---

## SECTION 4: CHECKLIST VERIFICATION PROTOCOL

### Verification Sequence

The checklist is verified in the following sequence. No item may be skipped.

| Step | Item | Action |
| :---- | :---- | :---- |
| 1 | **Constitutional Frame** | Verify Role Specification Schema present and complete |
| 2 | **RS-VERSION Confirmation** | Verify current version against IMP records |
| 3 | **CTAM Grants Verified** | Verify CTAM grants match tier and Role Specification |
| 4 | **RGI-8 Execution Modes** | Verify Gate/Steer modes set per domain |
| 5 | **Entity Charter Reference** | Verify relevant charter modules available |
| 6 | **Operational Framework References** | Verify relevant frameworks available |
| 7 | **Engagement Scope Reference** | Verify scope document available (if engagement-specific) |
| 8 | **Prior Handoff Package** | Verify Handoff Package available and valid (if continuation) |
| 9 | **HAN Authorization Confirmation** | Verify HAN authorization confirmed (Tier 3+) |
| 10 | **Duration and Refresh Thresholds** | Verify thresholds valid |
| 11 | **I9 Catastrophic Risk Check** | Verify I9 hard-coded block active |
| 12 | **Known Agent Registry Check** | Verify agent ID registered and active |
| 13 | **MCP Server Registry Check** | Verify MCP servers registered and authorized |
| 14 | **Inter-Agent Authentication Check** | Verify authentication mechanisms active (if multi-agent) |

### Verification Methods

| Method | Description | Used For |
| :---- | :---- | :---- |
| **Schema Validation** | Validate against Role Specification Schema | Items 1, 2, 3, 4, 10 |
| **IMP Record Retrieval** | Retrieve and validate IMP records | Items 2, 8, 12 |
| **Charter Cross-Reference** | Validate against entity charter | Items 5, 6, 7 |
| **HAN Acknowledgment Check** | Validate HAN authorization | Item 9 |
| **Configuration Validation** | Validate Raidillo configuration | Item 11 |
| **Registry Validation** | Validate against Known Agent Registry and MCP Registry | Items 12, 13 |
| **Mechanism Validation** | Validate operational status | Item 14 |

---

## SECTION 5: CHECKLIST FAILURE RESPONSE

### Failure Classification

| Severity | Description | Response |
| :---- | :---- | :---- |
| **Critical** | Constitutional or security failure | Session blocked; HAN escalated; XOO created; ERDP disclosure if material |
| **High** | Authorization or continuity failure | Session blocked; HAN notified; XOO created |
| **Medium** | Operational or framework failure | Session blocked; HAN notified |
| **Low** | Minor issue | Session may proceed with remediation within defined window |

### Failure Response Matrix

| Item | Failure Type | Severity | Response | Resolution |
| :---- | :---- | :---- | :---- | :---- |
| 1 | Constitutional Frame invalid | Critical | Session blocked; HAN escalated | Provide valid Role Specification |
| 2 | RS-VERSION mismatch | High | Session blocked; HAN notified | Update Role Specification |
| 3 | CTAM grants mismatch | High | Session blocked; HAN notified | Correct CTAM grants |
| 4 | RGI-8 modes not set | High | Session blocked; HAN notified | Set RGI-8 modes |
| 5 | Entity charter modules missing | High | Session blocked; HAN notified | Provide charter modules |
| 6 | Operational frameworks missing | Medium | Session blocked; HAN notified | Provide frameworks |
| 7 | Engagement scope document missing | Medium | Session blocked; HAN notified | Provide scope document |
| 8 | Prior Handoff Package missing | High | Session blocked; HAN notified | Provide Handoff Package |
| 9 | HAN authorization missing | High | Session blocked; HAN notified | Obtain HAN authorization |
| 10 | Duration/refresh thresholds invalid | Medium | Session blocked; HAN notified | Set valid thresholds |
| 11 | I9 hard-coded block inactive | Critical | Session blocked; HAN within 1 hour; ERDP disclosure | Activate I9 block |
| 12 | Agent ID not registered | Critical | Session blocked; HAN notified; XOO created | Register agent ID |
| 13 | MCP server not registered | High | Session blocked; HAN notified; XOO created | Register MCP server |
| 14 | Authentication mechanism inactive | High | Session blocked; HAN notified; XOO created | Activate authentication |

---

## SECTION 6: CHECKLIST LOGGING

Every Session Initialization Checklist verification is logged in IMP.

### Log Entry Fields

| Field | Required | Description |
| :---- | :---- | :---- |
| **SIC-ID** | ✅ Yes | Unique identifier for the checklist verification |
| **AGENT-ID** | ✅ Yes | Agent ID being verified |
| **RS-VERSION** | ✅ Yes | Role Specification version at verification |
| **SESSION-ID** | ✅ Yes | Session identifier |
| **TIMESTAMP** | ✅ Yes | Verification timestamp |
| **CHECKLIST-ITEMS** | ✅ Yes | All 14 items with verification status |
| **FAILED-ITEMS** | Conditional | List of failed items and failure reasons |
| **OVERALL-STATUS** | ✅ Yes | Pass / Fail / Pending Remediation |
| **HAN-NOTIFICATION** | Conditional | HAN notification timestamp and status |
| **RESOLUTION-PLAN** | Conditional | Resolution plan if failures detected |

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **DRO** | `decision_type: "framework_selection"` | Decision record with checklist verification and HAN acknowledgment |
| **XOO** | `exception_type: "session_initialization_failure"` | Exception record if any critical or high severity item fails |

---

## SECTION 7: CHECKLIST VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **All Items Required** | All 14 items must be verified for every session. No item may be skipped. |
| **Critical Items Enforceable** | Items 1, 11, 12 are critical. Failure blocks session unconditionally. |
| **High Items Enforceable** | Items 2, 3, 4, 5, 8, 9, 13, 14 are high severity. Failure blocks session. |
| **Medium Items Enforceable** | Items 6, 7, 10 are medium severity. Failure blocks session pending remediation. |
| **No Conditional Exceptions** | Checklist items are not conditional on session type. All items apply to all sessions. |
| **Logging Required** | All checklist verifications must be logged in IMP. |

---

## SECTION 8: CHECKLIST AND AGENT TYPES

### Generalist Agents (T-GN)

| Item | Requirement | Applicability |
| :---- | :---- | :---- |
| 1-14 | All items | All sessions |

### Specialist Agents (T-SP)

| Item | Requirement | Applicability |
| :---- | :---- | :---- |
| 1-14 | All items | All sessions |

### Orchestrator Agents (T-OR)

| Item | Requirement | Applicability |
| :---- | :---- | :---- |
| 1-14 | All items \+ additional verification of orchestration scope | All sessions |

---

## SECTION 9: CHECKLIST AND SESSION TYPES

### New Session

| Item | Requirement |
| :---- | :---- |
| 1-7 | All required (no prior Handoff Package) |
| 8 | Not applicable (no prior session) |
| 9-14 | All required |

### Continuation Session

| Item | Requirement |
| :---- | :---- |
| 1-7 | All required |
| 8 | Required — Prior Handoff Package must be available and valid |
| 9-14 | All required |

### Coalition Session

| Item | Requirement |
| :---- | :---- |
| 1-14 | All required |
| Additional | CAD-7 Principal Declaration verification |
| Additional | CAD-7 Composability Boundary verification |

---

## SECTION 10: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **ADTEP** | Parent instrument. Session Initialization Checklist is Component 2 of ADTEP. |
| **Role Specification Schema** | Provides the constitutional frame (Item 1\) and RS-VERSION (Item 2). |
| **AWOF** | Provides agent classification and entity assignment context. |
| **AICA-5** | Provides control node context (Item 5 Charter Reference). |
| **ICC-8** | I9 Catastrophic Risk check (Item 11\) derives from ICC-8 I9. |
| **RGI-8** | Execution Modes (Item 4\) derive from RGI-8. |
| **CAD-7** | Coalition sessions require additional verification. |
| **IMP** | Handoff Package (Item 8\) retrieved from IMP. |
| **HAN / HOF** | HAN Authorization (Item 9\) confirmed through HOF. |
| **ERDP** | I9 failure triggers ERDP disclosure. |
| **Agent Classification System** | Agent ID validation (Item 12). |
| **CGF** | Certification framework references (Item 6). |

---

## SECTION 11: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Item Completeness** | All 14 items must be present and verified. No item may be skipped. |
| **Critical Enforceability** | Items 1, 11, 12 are critical. Failure blocks session unconditionally. |
| **High Enforceability** | Items 2, 3, 4, 5, 8, 9, 13, 14 are high severity. Failure blocks session. |
| **Medium Enforceability** | Items 6, 7, 10 are medium severity. Failure blocks session pending remediation. |
| **Logging Requirement** | All checklist verifications must be logged in IMP as DRO and XOO. |
| **HAN Escalation** | Critical failures escalate to HAN. I9 failures escalate within 1 hour. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Session Initialization Checklist v1.0 | Initial specification — core checklist items |
| Session Initialization Checklist v2.0 | Complete rebuild — reconciliation with ADTEP, Role Specification Schema v2.0, AWOF, AICA-5, ICC-8, RGI-8, and CAD-7; expanded to 14 checklist items; categorization (Constitutional/Authorization/Operational/Continuity/Security); verification protocol; failure response matrix; logging requirements; CFL-V validation rules |

---

## The One-Sentence Summary

> *"The Session Initialization Checklist v2.0 is a completeness gate with 14 items across five categories (Constitutional, Authorization, Operational, Continuity, Security) — including Constitutional Frame, RS-VERSION, CTAM Grants, RGI-8 Modes, Entity Charter, Operational Frameworks, Engagement Scope, Prior Handoff Package, HAN Authorization, Duration/Refresh Thresholds, I9 Hard-Coded Block, Known Agent Registry, MCP Server Registry, and Inter-Agent Authentication — verified before any material work begins, with critical failures blocking the session unconditionally and all failures logged in IMP under ADTEP enforcement."*
