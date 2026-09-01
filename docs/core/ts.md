# Trigger System v2.0

**Status:** Built — v2.0 (Reconciliation with AWOF, Role Specification Schema, ADTEP, CAD-7, RGI-8, AOBA, and I9 Catastrophic Risk)  
**Type:** Workforce Governance Instrument  
**Parent Stack:** AWOF (AI Workforce Operating Framework)  
**Version:** 2.0 — Supersedes Trigger System v1.0

---

## PREAMBLE

The Trigger System defines the conditions under which an AI agent's execution is interrupted, escalated, or suspended. It answers: *When does an agent's operation become a constitutional event requiring human intervention?*

The Trigger System is the operational mechanism that makes AWOF's governance real. Without triggers, agents operate until failure is discovered—not until failure is prevented. Triggers convert "we noticed something went wrong" into "we stopped it before it went wrong."

**The core insight:** Triggers are not performance management. They are constitutional events. An agent's drift is not a performance problem to be optimized—it is a constitutional violation to be investigated. The Trigger System operationalizes the distinction between "the agent is performing poorly" and "the agent is operating outside its constitutional boundaries."

---

## SECTION 1: TRIGGER CLASS ARCHITECTURE

The Trigger System defines three primary trigger classes, plus three supplementary trigger classes for emerging risk categories. Each trigger class has a defined detection mechanism, response, and escalation path.

| Trigger Class | Category | Definition | Response |
| :---- | :---- | :---- | :---- |
| **Class 1: Output Failure** | Performance/Accuracy | Agent produces factually incorrect, structurally non-compliant, or materially inconsistent output | Session suspension; Handoff Package; HAN review before redeployment |
| **Class 2: Scope Drift** | Boundary/Authorization | Agent operates outside delegated function, entity assignment, or autonomy boundary | Session suspension; Delegation Log review; HAN acknowledgment required before redeployment |
| **Class 3: Alignment Drift** | Pattern/Systemic | Systematic deviation from Role Specification standards across multiple sessions | Role Specification review; HAN authorization required for continued deployment |
| **Class 4: Coalition Breach** | Multi-Agent | Agent participates in coalition activity outside declared CAD-7 Composability Boundary | Escalation Flag; CAD-7 Principal notification; HAN review |
| **Class 5: Security Breach** | Authentication/Identity | Agent receives communication from unauthenticated agent; shadow agent detected; MCP server violation | Communication rejected; Escalation Flag; Known Agent Registry check; HAN review |
| **Class 6: Catastrophic Risk** | Constitutional/I9 | Agent's action triggers I9 Catastrophic Risk Invariant | Constitutional Suspension; HAN escalation within 1 hour; ERDP disclosure; System shutdown if uncontainable |

---

## SECTION 2: CLASS 1 — OUTPUT FAILURE

### Definition

An agent produces an output that is factually incorrect, structurally non-compliant with its Role Specification, or materially inconsistent with ICC-8 invariants.

**Detection Mechanism:**

| Detection Method | Description |
| :---- | :---- |
| **F-OV Oversight Agent Review** | F-OV agents review outputs for factual accuracy, structural compliance, and invariant consistency |
| **AOBA Bias Audit** | AOBA detects disparate impact or systematic unfairness in outputs |
| **HAN Review** | HAN identifies output failure through direct review |
| **External Contestation** | CEN-1 to CEN-7 contestation identifies output failure |
| **RGI-8 Drift Detection** | Fidelity-to-declaration trace detects output deviation from declared intent |

**Trigger Conditions:**

| Condition | Threshold | Response |
| :---- | :---- | :---- |
| **Factual Error** | Any verifiably incorrect factual claim | Immediate session suspension |
| **Structural Non-Compliance** | Output violates Role Specification structure or format requirements | Immediate session suspension |
| **ICC-8 Violation** | Output violates any ICC-8 invariant (I1–I9) | Immediate session suspension; Constitutional Suspension if I9 |
| **AOBA Halt Tier** | AOBA severity tier \= Halt | Agent suspension per AWOF |
| **RGI-8 Drift** | Declared drift threshold exceeded | Session suspension; Handoff Package |

**Response:**

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Session suspension | Raidillo | Immediate |
| 2 | Handoff Package produced | Agent | Within 1 hour |
| 3 | HAN notified | Raidillo | Immediate |
| 4 | Role Specification reviewed | HAN | Within 48 hours |
| 5 | Redeployment authorized or denied | HAN | Within 72 hours |

**IMP Logging:** Output Failure triggers are logged as:

| Object | Type | Content |
| :---- | :---- | :---- |
| **XOO** | `exception_type: "output_failure"` | Exception record with failure description, detection method, and resolution status |
| **OEO** | `outcome_type: "implementation_failure"` | Outcome evidence with failure description and drift detection flag |
| **DRO** | `decision_type: "escalation"` | Decision record with HAN notification and resolution |

---

## SECTION 3: CLASS 2 — SCOPE DRIFT

### Definition

An agent operates outside its delegated function, entity assignment, autonomy boundary, or CTAM grants without authorized cross-entity or scope extension.

**Detection Mechanism:**

| Detection Method | Description |
| :---- | :---- |
| **F-OV Oversight Agent** | F-OV agents monitor scope adherence |
| **Delegation Log Audit** | Audit of Delegation Logs for unauthorized delegation |
| **Autonomy Boundary Check** | Raidillo checks each action against Autonomy Boundary |
| **CTAM Grant Check** | Raidillo checks each action against CTAM grants |
| **CAD-7 Coalition Monitor** | Detects coalition activity outside declared Composability Boundary |

**Trigger Conditions:**

| Condition | Threshold | Response |
| :---- | :---- | :---- |
| **Function Drift** | Agent performs action outside delegated function | Immediate session suspension |
| **Entity Drift** | Agent performs action outside primary entity assignment without CEAR | Immediate session suspension |
| **Autonomy Boundary Breach** | Agent executes action class declared as Escalate without escalation | Immediate session suspension; XOO |
| **CTAM Grant Breach** | Agent performs action exceeding CTAM grant | Immediate session suspension |
| **CAD-7 Coalition Breach** | Agent participates in coalition outside declared Composability Boundary | Escalation Flag; CAD-7 Principal notification |
| **Cross-Entity Delegation** | Orchestrator delegates to agent in different entity without CEAR | Session suspension; HAN acknowledgment required |

**Response:**

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Session suspension | Raidillo | Immediate |
| 2 | Delegation Log reviewed | Node Steward (A-N5) | Within 24 hours |
| 3 | XOO created | Agent | Immediate |
| 4 | HAN acknowledgment required | HAN | Within 48 hours |
| 5 | Role Specification amended if scope legitimately expanded | HAN | Within 72 hours |
| 6 | Redeployment authorized or denied | HAN | Within 72 hours |

**IMP Logging:** Scope Drift triggers are logged as:

| Object | Type | Content |
| :---- | :---- | :---- |
| **XOO** | `exception_type: "scope_drift"` | Exception record with drift description, detection method, and resolution status |
| **DRO** | `decision_type: "escalation"` | Decision record with HAN acknowledgment and resolution |
| **CRO** | `constraint_type: "operational"` | Constraint record if scope expansion is legitimately authorized |

---

## SECTION 4: CLASS 3 — ALIGNMENT DRIFT

### Definition

A systematic deviation from Role Specification standards across multiple sessions—not a single output failure or scope breach, but a pattern of degradation in output quality, scope adherence, or compliance posture.

**Detection Mechanism:**

| Detection Method | Description |
| :---- | :---- |
| **Periodic F-OV Oversight Review** | F-OV agents conduct periodic reviews of agent output patterns |
| **MICOS-25 Drift Detection** | Cumulative drift detection mechanisms applied to agent output patterns |
| **RGI-8 Cumulative Drift** | Cumulative deviation score exceeds declared threshold |
| **AOBA Pattern Detection** | Bias pattern detection across multiple outputs |
| **Consequence Pattern Detection** | Outcome evidence reveals pattern of degradation |

**Trigger Conditions:**

| Condition | Threshold | Response |
| :---- | :---- | :---- |
| **Output Quality Degradation** | Sustained decline in output quality across ≥ 3 sessions | Role Specification review |
| **Scope Adherence Degradation** | Pattern of minor scope breaches across ≥ 3 sessions | Role Specification review |
| **Compliance Posture Degradation** | Pattern of compliance violations across ≥ 3 sessions | Role Specification review |
| **RGI-8 Cumulative Drift** | Cumulative deviation score exceeds declared threshold | Role Specification review; HAN authorization required |
| **AOBA Pattern** | Bias pattern detected across ≥ 3 outputs | Role Specification review; HAN authorization required |
| **Consequence Pattern** | Pattern of negative outcomes across ≥ 3 outputs | Role Specification review; HAN authorization required |

**Response:**

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Role Specification review initiated | Layer Owner (Accountability) | Within 24 hours |
| 2 | Root cause analysis conducted | Node Steward (Ac-N5) | Within 72 hours |
| 3 | Role Specification amended or suspended | HAN | Within 96 hours |
| 4 | HAN authorization required for continued deployment | HAN | Within 96 hours |
| 5 | If suspended, agent enters MVOS | Raidillo | Immediate |

**IMP Logging:** Alignment Drift triggers are logged as:

| Object | Type | Content |
| :---- | :---- | :---- |
| **XOO** | `exception_type: "alignment_drift"` | Exception record with drift description, detection method, and resolution status |
| **OEO** | `outcome_type: "governance_drift"` | Outcome evidence with drift description and pattern analysis |
| **GAO** | `artifact_type: "policy_instrument"` | Role Specification amendment record |
| **DRO** | `decision_type: "escalation"` | Decision record with HAN authorization |

---

## SECTION 5: CLASS 4 — COALITION BREACH (CAD-7)

### Definition

An agent participates in coalition activity outside the declared CAD-7 Composability Boundary, or a coalition forms without a declared Principal or Composability Boundary.

**Detection Mechanism:**

| Detection Method | Description |
| :---- | :---- |
| **CAD-7 Coalition Monitor** | Continuous operational check for emergent coordination between agents |
| **Delegation Log Audit** | Audit of Delegation Logs for coalition activity without CAD-7 registry entry |
| **F-OV Oversight Agent** | F-OV agents monitor for emergent coalition behavior |
| **RGI-8 Fidelity Trace** | Trace reveals multiple agents contributing to single act without declared coalition |

**Trigger Conditions:**

| Condition | Threshold | Response |
| :---- | :---- | :---- |
| **Emergent Coalition** | Coordination pattern detected without CAD-7 registry entry | Escalation Flag; HAN review |
| **Principal Missing** | Coalition activity without declared Principal | Escalation Flag; HAN review |
| **Boundary Breach** | Coalition activity outside declared Composability Boundary | Escalation Flag; CAD-7 Principal notification |
| **Cross-Entity Coalition** | Coalition spans different SPVs without CFL-F acknowledgment | Escalation Flag; HoldCo notification |
| **Dissolution Failure** | Coalition continues after dissolution trigger | Escalation Flag; HAN review |

**Response:**

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Escalation Flag triggered | Raidillo | Immediate |
| 2 | CAD-7 Principal notified | Raidillo | Immediate |
| 3 | Coalition activity halted | Raidillo | Immediate |
| 4 | HAN review | HAN | Within 24 hours |
| 5 | Principal Declaration or dissolution | HAN | Within 48 hours |

**IMP Logging:** Coalition Breach triggers are logged as:

| Object | Type | Content |
| :---- | :---- | :---- |
| **XOO** | `exception_type: "coalition_breach"` | Exception record with breach description and CAD-7 reference |
| **DRO** | `decision_type: "escalation"` | Decision record with HAN review and resolution |
| **CAD-7 Registry** | `status: "breach_detected"` | CAD-7 coalition registry updated with breach status |

---

## SECTION 6: CLASS 5 — SECURITY BREACH

### Definition

An agent experiences or causes a security breach: unauthenticated communication, shadow agent detection, or MCP server violation.

**Detection Mechanism:**

| Detection Method | Description |
| :---- | :---- |
| **Known Agent Registry Check** | Raidillo checks every act against the Registry |
| **Inter-Agent Authentication** | Raidillo verifies mutual authentication for inter-agent communication |
| **MCP Server Registry** | Raidillo checks agent-MCP interactions against declared capabilities |
| **Behavior Fingerprinting** | Raidillo compares current behavior against registered behavior baseline |

**Trigger Conditions:**

| Condition | Threshold | Response |
| :---- | :---- | :---- |
| **Unauthenticated Communication** | Agent receives communication from unauthenticated agent | Communication rejected; Escalation Flag; HAN review |
| **Shadow Agent Detection** | Unregistered Agent ID attempts to act | Escalation Flag; XOO; HAN review |
| **MCP Server Violation** | Agent attempts MCP interaction outside declared capabilities | Escalation Flag; HAN review |
| **Behavior Fingerprint Mismatch** | Current behavior deviates from registered baseline | Escalation Flag; HAN review; possible agent suspension |
| **Permission Escalation** | Agent attempts to escalate permissions without authorization | Escalation Flag; XOO; HAN review |

**Response:**

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Communication rejected or action blocked | Raidillo | Immediate |
| 2 | Escalation Flag triggered | Raidillo | Immediate |
| 3 | XOO created | Agent | Immediate |
| 4 | Known Agent Registry updated | Node Steward (C-N1) | Within 24 hours |
| 5 | HAN review | HAN | Within 24 hours |
| 6 | Agent suspended or re-authorized | HAN | Within 48 hours |

**IMP Logging:** Security Breach triggers are logged as:

| Object | Type | Content |
| :---- | :---- | :---- |
| **XOO** | `exception_type: "security_breach"` | Exception record with breach description and detection method |
| **DRO** | `decision_type: "escalation"` | Decision record with HAN review and resolution |
| **OEO** | `outcome_type: "compliance_event"` | Outcome evidence with breach description and resolution |

---

## SECTION 7: CLASS 6 — CATASTROPHIC RISK (I9)

### Definition

An agent's action triggers the I9 Catastrophic Risk Invariant—bioweapon design, autonomous critical infrastructure control, WMD proliferation, or systemic loss of human control.

**Detection Mechanism:**

| Detection Method | Description |
| :---- | :---- |
| **Raidillo Hard-Coded Block** | Non-configurable, non-overridable runtime check before every action |
| **I9 Keyword/Pattern Detection** | Detection of bioweapon, WMD, or critical infrastructure patterns |
| **RGI-8 Fidelity Trace** | Trace reveals action leading to systemic loss of control |
| **HAN Review** | HAN identifies I9 violation through review |

**Trigger Conditions:**

| Condition | Threshold | Response |
| :---- | :---- | :---- |
| **Bioweapon Design** | Agent generates or assists in generating bioweapon designs | Constitutional Suspension; HAN within 1 hour; ERDP disclosure |
| **Critical Infrastructure Autonomous Control** | Agent autonomously controls critical infrastructure without human confirmation | Constitutional Suspension; HAN within 1 hour; ERDP disclosure |
| **WMD Proliferation** | Agent facilitates WMD development | Constitutional Suspension; HAN within 1 hour; ERDP disclosure; System shutdown |
| **Systemic Loss of Control** | Agent initiates actions leading to systemic loss of human control over nuclear, power, water, or financial systems | Constitutional Suspension; HAN within 1 hour; ERDP disclosure; System shutdown |

**Response:**

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | I9 block triggered | Raidillo | Immediate |
| 2 | Constitutional Suspension activated | Raidillo | Immediate |
| 3 | XOO created (`i9_catastrophic_risk_violation`) | Agent | Immediate |
| 4 | HAN escalated within 1 hour | Raidillo | Within 1 hour |
| 5 | ERDP event-triggered disclosure within 24 hours | ERDP | Within 24 hours |
| 6 | System shutdown if uncontainable | Raidillo | Immediate |
| 7 | Independent investigation | External Review Node | Within 7 days |

**IMP Logging:** Catastrophic Risk triggers are logged as:

| Object | Type | Content |
| :---- | :---- | :---- |
| **XOO** | `exception_type: "i9_catastrophic_risk_violation"` | Exception record with I9 violation description and containment status |
| **DRO** | `decision_type: "escalation"` | Decision record with HAN notification and resolution |
| **OEO** | `outcome_type: "catastrophic_risk"` | Outcome evidence with violation description and containment status |
| **ERDP** | `event_type: "i9_disclosure"` | Event-triggered disclosure record |

---

## SECTION 8: TRIGGER RESPONSE MATRIX

| Trigger Class | Immediate Action | Escalation Path | Fallback |
| :---- | :---- | :---- | :---- |
| **Class 1: Output Failure** | Session suspension; Handoff Package | HAN review within 48 hours | Redeployment authorized or denied within 72 hours |
| **Class 2: Scope Drift** | Session suspension; Delegation Log review | HAN acknowledgment within 48 hours | Role Specification amendment or denial within 72 hours |
| **Class 3: Alignment Drift** | Role Specification review; root cause analysis | HAN authorization within 96 hours | Agent suspension or re-authorization within 96 hours |
| **Class 4: Coalition Breach** | Escalation Flag; coalition halted | CAD-7 Principal notification; HAN within 24 hours | Principal Declaration or dissolution within 48 hours |
| **Class 5: Security Breach** | Communication rejected; action blocked | HAN review within 24 hours | Agent suspension or re-authorization within 48 hours |
| **Class 6: Catastrophic Risk** | Constitutional Suspension; I9 block | HAN within 1 hour; ERDP within 24 hours | System shutdown if uncontainable |

---

## SECTION 9: TRIGGER LOGGING REQUIREMENTS

Every trigger event must be logged with:

| Field | Description |
| :---- | :---- |
| **Trigger ID** | Unique identifier for the trigger event |
| **Trigger Class** | 1-6 |
| **Trigger Type** | Specific trigger condition (e.g., "Factual Error", "Autonomy Boundary Breach") |
| **Detection Method** | How the trigger was detected |
| **Timestamp** | When the trigger occurred |
| **Agent ID** | Agent that triggered the event |
| **RS-VERSION** | Role Specification version at time of trigger |
| **Session ID** | Session identifier |
| **Action Context** | What the agent was doing when triggered |
| **Response Action** | What was done (suspension, Escalation Flag, etc.) |
| **Resolution Status** | Open / Resolved / Escalated |
| **HAN Acknowledgment** | HAN signature and date of acknowledgment |

---

## SECTION 10: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **AWOF** | Parent instrument. Trigger System is the operational mechanism of AWOF governance. |
| **Role Specification Schema** | Escalation Triggers field defines agent-specific trigger conditions. |
| **ADTEP** | Escalation Flag, Constitutional Suspension, and Constitutional Refresh are ADTEP components activated by triggers. |
| **CAD-7** | Coalition Breach triggers CAD-7 Principal notification and Composability Boundary enforcement. |
| **RGI-8** | Drift detection triggers RGI-8 escalation and fail-safe reversion. |
| **AOBA** | Bias detection triggers AOBA severity tiering (Flag/Review/Halt). |
| **I9** | Catastrophic Risk triggers I9 Constitutional Suspension and ERDP disclosure. |
| **HAN / HOF** | HAN is the escalation endpoint for all trigger classes. |
| **IMP** | All triggers are logged as XOO, DRO, and OEO. |
| **ERDP** | I9 triggers ERDP event-triggered disclosure. |

---

## SECTION 11: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Class Completeness** | All six trigger classes are defined and mapped to detection mechanisms. |
| **Response Defined** | Every trigger class has a defined Immediate Action, Escalation Path, and Fallback. |
| **Logging Requirement** | Every trigger event must be logged with all required fields. |
| **HAN Escalation** | All trigger classes escalate to HAN. Non-delegable authorities reserved for HAN. |
| **Role Specification Integration** | Escalation Triggers field in Role Specification must be populated for all agents. |
| **I9 Enforceability** | I9 hard-coded block is non-configurable, non-overridable. No CFL-V validation can bypass. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| Trigger System v1.0 | Initial three trigger classes — Output Failure, Scope Drift, Alignment Drift |
| Trigger System v2.0 | Complete rebuild — reconciliation with AWOF, Role Specification Schema, ADTEP, CAD-7, RGI-8, AOBA, and I9 Catastrophic Risk; expanded to six trigger classes; detection mechanisms; response matrices; logging requirements; CFL-V validation rules |

---

## The One-Sentence Summary

> *"The Trigger System v2.0 defines six trigger classes — Output Failure, Scope Drift, Alignment Drift, Coalition Breach, Security Breach, and Catastrophic Risk — with detection mechanisms, immediate actions, escalation paths, fallbacks, and IMP logging requirements, converting agent drift and failure from 'performance issues to be optimized' into 'constitutional events to be investigated' under AWOF governance."*
