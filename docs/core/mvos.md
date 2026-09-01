# MVOS v2.0 — Minimum Viable Operations State

**Status:** Built — v2.0 (Reconciliation with AWOF, Trigger System, ADTEP, HAN/HOF, and ICC-8 I7 Continuity Invariance)  
**Type:** Continuity Instrument  
**Parent Stack:** AWOF (AI Workforce Operating Framework)  
**Version:** 2.0 — Supersedes MVOS v1.0

---

## PREAMBLE

The Minimum Viable Operations State (MVOS) defines the constitutional condition in which the HAN operates without AI agent support. It answers: *What happens when all agents are unavailable?*

MVOS is not a failure mode. It is a defined constitutional condition — the irreducible set of functions the institution can perform without its AI workforce. Every institution that depends on AI must define what it does when AI is unavailable. MVOS is that definition.

**The core insight:** An institution that cannot operate without its AI workforce is not an institution — it is a dependent system. MVOS is the institutional continuity guarantee that prevents AI dependency from becoming institutional fragility.

---

## SECTION 1: MVOS TRIGGER CONDITIONS

MVOS is triggered when any of the following conditions occur. Trigger detection is continuous — Raidillo monitors for all trigger conditions and escalates to MVOS immediately upon detection.

| Trigger Condition | Description | Detection Method |
| :---- | :---- | :---- |
| **Full AI Workforce Unavailability** | Platform outage, model deprecation, or systemic event renders all agents non-operational | Raidillo health checks; Agent Registry check; platform status monitoring |
| **Constitutional Suspension** | ADTEP Constitutional Suspension activated due to I9 violation or other constitutional breach | ADTEP Escalation Flag acknowledgment |
| **HAN Initiated** | HAN may proactively declare MVOS in response to observed or anticipated risk | HAN declaration via HAN Interface |
| **Catastrophic Risk I9** | I9 Catastrophic Risk Invariant triggered — system shutdown initiated | Raidillo hard-coded block; I9 detection |
| **Widespread Agent Drift** | Multiple agents across multiple entities simultaneously enter Alignment Drift or Scope Drift | Trigger System cross-agent pattern detection |
| **Orchestrator Cascade Failure** | T-OR orchestrator failure cascades across all active workflows | EGF-4 Exception Classification and Containment |

**MVOS Trigger Verification:**

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Trigger condition detected | Raidillo | Immediate |
| 2 | Trigger verified — false positive check | Raidillo | Within 5 minutes |
| 3 | HAN notification | Raidillo | Within 10 minutes |
| 4 | MVOS declaration logged | IMP | Within 30 minutes |
| 5 | ERDP event-triggered disclosure (if material) | ERDP | Within 14 days |

---

## SECTION 2: MVOS OPERATING STATE

### MVOS Conditions

Upon MVOS activation:

| Condition | Status | Description |
| :---- | :---- | :---- |
| **New Material Institutional Actions** | ❌ Suspended | No new material institutional actions may be initiated |
| **Existing Commitments** | ✅ Maintained | Existing commitments are maintained under existing authority where no AI execution is required |
| **HAN Authority** | ✅ Sole Institutional Actor | HAN operates as the sole institutional actor |
| **SPV Operations** | ✅ Reduced Operations State | All three SPV entities simultaneously enter Reduced Operations State as defined in their respective charters |
| **AI Agents** | ❌ Suspended | All AI agents are suspended. No agent operates during MVOS |
| **Observability** | ✅ HAN-Only | HAN maintains manual observability of existing commitments |
| **IMP Logging** | ✅ Active | IMP continues logging HAN actions during MVOS |

### HAN-Only Operations

During MVOS, HAN may perform the following operations without AI support:

| Operation | Description | Limitations |
| :---- | :---- | :---- |
| **Monitoring** | Monitor existing commitments and their status | May not initiate new commitments |
| **Communication** | Communicate with stakeholders, clients, regulators | May not commit institutional resources |
| **Documentation** | Document MVOS status and actions | Manual documentation only |
| **Recovery Coordination** | Coordinate AI agent recovery process | May not deploy agents until recovery confirmed |
| **Escalation Management** | Manage escalations received during MVOS | May not delegate escalations to agents |
| **Incident Response** | Respond to incidents requiring human intervention | May not use AI for incident response |

### HAN-Only Limitations

During MVOS, HAN may NOT:

| Limitation | Reason |
| :---- | :---- |
| **Initiate new engagements** | New engagements require agent support for scoping, drafting, and delivery |
| **Execute binding transactions** | Binding transactions require agent support for validation and audit trail |
| **Certify AI systems** | Certification requires agent performance validation |
| **Generate compliance reports** | Compliance reports require agent support for data aggregation and validation |
| **Delegate to AI agents** | All agents are suspended during MVOS |

---

## SECTION 3: MVOS RECOVERY PROTOCOL

Recovery from MVOS follows a sequenced protocol. No step may be skipped.

### Phase 1: Platform Restoration

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Platform restoration confirmed | HAN | Upon restoration |
| 2 | MVOS trigger condition resolved | HAN | Upon resolution |
| 3 | HAN confirms platform operational | HAN | Within 2 hours |

### Phase 2: Agent Redeployment

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 4 | Agent instances redeployed under existing Role Specifications | Raidillo | Within 4 hours of restoration |
| 5 | Agent health checks performed | Raidillo | Within 4 hours of redeployment |
| 6 | All agents confirmed operational | Raidillo | Within 6 hours of redeployment |

### Phase 3: Session Reconciliation

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 7 | Handoff Package review for all suspended sessions | HAN \+ Node Stewards | Within 24 hours of redeployment |
| 8 | Suspended sessions resumed or terminated | HAN | Within 48 hours of redeployment |
| 9 | Session reconciliation logged | IMP | Within 72 hours of redeployment |

### Phase 4: MVOS Deactivation

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 10 | HAN confirms recovery status | HAN | Within 72 hours of redeployment |
| 11 | MVOS deactivation declared | HAN | Upon confirmation |
| 12 | ERDP event-triggered disclosure (if material) | ERDP | Within 14 days of deactivation |
| 13 | Normal operations resume | All | Upon deactivation |

---

## SECTION 4: MVOS LOGGING REQUIREMENTS

Every MVOS event must be logged with:

| Field | Description |
| :---- | :---- |
| **MVOS ID** | Unique identifier for the MVOS event |
| **Trigger Condition** | What triggered MVOS (from Section 1\) |
| **Trigger Verification** | False positive check result |
| **Activation Timestamp** | When MVOS was activated |
| **Declared By** | HAN or Raidillo (automatic) |
| **HAN Acknowledgment** | HAN signature and timestamp |
| **Current Status** | Active / Recovering / Resolved |
| **Recovery Timeline** | Milestone completion dates |
| **Deactivation Timestamp** | When MVOS was deactivated |
| **Post-Incident Review** | Root cause analysis, lessons learned, corrective actions |

**IMP Logging:**

| Object | Type | Content |
| :---- | :---- | :---- |
| **XOO** | `exception_type: "mvos_activation"` | Exception record with trigger condition, activation timestamp, and HAN acknowledgment |
| **XOO** | `exception_type: "mvos_deactivation"` | Exception record with deactivation timestamp and recovery confirmation |
| **OEO** | `outcome_type: "mvos_event"` | Outcome evidence with MVOS description, recovery timeline, and post-incident review |
| **DRO** | `decision_type: "escalation"` | Decision record with HAN declarations and acknowledgments |
| **GAO** | `artifact_type: "incident_report"` | Post-incident review document |

---

## SECTION 5: MVOS AND SPV ENTITIES

Upon MVOS activation, all three SPV entities simultaneously enter Reduced Operations State as defined in their respective charters.

### 19 Consultin' Reduced Operations State

| Activity | Status | Description |
| :---- | :---- | :---- |
| **New client engagements** | ❌ Suspended | No new engagements may be initiated |
| **Active engagements** | ⚠️ Maintained | Existing engagements maintained under existing authority |
| **Deliverable production** | ❌ Suspended | No new deliverables may be produced |
| **Client communication** | ✅ Maintained | HAN may communicate with clients but may not commit new resources |
| **IP generation** | ❌ Suspended | No new IP may be generated |

### 19 Publishin' Reduced Operations State

| Activity | Status | Description |
| :---- | :---- | :---- |
| **New publications** | ❌ Suspended | No new publications may be released |
| **Existing content distribution** | ✅ Maintained | Distribution of already-cleared content continues |
| **Licensing decisions** | ❌ Suspended | No new licensing decisions may be executed |
| **Framework development** | ❌ Suspended | No new framework development may proceed |

### 19 Institute Reduced Operations State

| Activity | Status | Description |
| :---- | :---- | :---- |
| **New designations** | ❌ Suspended | No new designations may be issued |
| **Designation revocations** | ❌ Suspended | No revocations may be executed |
| **Curriculum delivery** | ✅ Maintained | Curriculum delivery under confirmed programs continues |
| **Assessment administration** | ✅ Maintained | Assessment administration under confirmed programs continues |

---

## SECTION 6: MVOS AND EXISTING COMMITMENTS

### Commitment Maintenance Rule

During MVOS, existing commitments are maintained under existing authority. This means:

| Commitment Type | Maintenance Action | Limitations |
| :---- | :---- | :---- |
| **Client engagements** | Continued monitoring, client communication | No new deliverables |
| **IP licenses** | Continued validity | No new licenses |
| **Certifications** | Continued validity | No new certifications |
| **Regulatory reporting** | Continued compliance with existing reporting obligations | No new reports |

### No New Commitment Rule

During MVOS, no new material institutional actions may be initiated. This includes:

| Action Type | Status | Reason |
| :---- | :---- | :---- |
| **New client engagements** | ❌ Prohibited | Requires agent support for scoping, drafting, delivery |
| **New IP licensing** | ❌ Prohibited | Requires agent support for due diligence, documentation |
| **New certification programs** | ❌ Prohibited | Requires agent support for curriculum development, assessment |
| **New regulatory submissions** | ❌ Prohibited | Requires agent support for data aggregation, validation |

---

## SECTION 7: MVOS TESTING AND DRILLS

MVOS must be tested periodically to ensure operational readiness.

| Test Type | Frequency | Description |
| :---- | :---- | :---- |
| **Tabletop Exercise** | Quarterly | HAN walks through MVOS activation scenario without actual system disruption |
| **Partial Drill** | Semi-annual | One entity enters MVOS while others remain operational |
| **Full Drill** | Annual | Full MVOS activation with all entities, HAN-only operations for up to 4 hours |
| **Surprise Drill** | Annual | Unannounced MVOS activation test |

**Drill Logging:**

| Object | Type | Content |
| :---- | :---- | :---- |
| **OEO** | `outcome_type: "mvos_drill"` | Outcome evidence with drill description, participants, outcomes, and lessons learned |
| **DRO** | `decision_type: "framework_selection"` | Decision record with drill authorization and HAN acknowledgment |

---

## SECTION 8: MVOS POST-INCIDENT REVIEW

Following any MVOS activation (drill or real event), a post-incident review is required.

### Review Requirements

| Requirement | Description |
| :---- | :---- |
| **Root Cause Analysis** | Identify the root cause of the MVOS trigger |
| **Trigger Detection Assessment** | Assess whether detection mechanisms functioned correctly |
| **HAN Performance Assessment** | Assess HAN's ability to operate without AI support |
| **Recovery Time Assessment** | Assess whether recovery occurred within defined timelines |
| **Lessons Learned** | Document lessons learned and corrective actions |
| **Corrective Actions** | Implement corrective actions to prevent recurrence or improve recovery |

### Review Timeline

| Step | Action | Responsible | Timeline |
| :---- | :---- | :---- | :---- |
| 1 | Root cause analysis completed | Node Steward (Ac-N5) | Within 7 days |
| 2 | Lessons learned documented | Layer Owner (Accountability) | Within 10 days |
| 3 | Corrective actions defined | HAN | Within 14 days |
| 4 | Corrective actions implemented | Assigned owners | Within 30 days |
| 5 | Post-incident review published | ERDP | Within 60 days (if material) |

---

## SECTION 9: MVOS AND EAF TRUST TIERS

MVOS triggers automatically across all trust tiers. However, the impact on client relationships varies by tier.

| EAF Tier | MVOS Impact | Client Communication |
| :---- | :---- | :---- |
| **Tier 1: Public** | Minimal | No notification required |
| **Tier 2: Discovery** | Minimal | No notification required unless engagement is active |
| **Tier 3: Active** | Moderate | Client notification within 24 hours if engagement affected |
| **Tier 4: Continuous** | Significant | Client notification within 12 hours; regular updates |
| **Tier 5: Partnership** | Significant | Client notification within 4 hours; dedicated updates |

---

## SECTION 10: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **AWOF** | Parent instrument. MVOS is the continuity guarantee for AWOF governance. |
| **Trigger System** | MVOS may be triggered by Class 6 (Catastrophic Risk) and widespread Class 3 (Alignment Drift). |
| **ADTEP** | Constitutional Suspension triggers MVOS. ADTEP Escalation Flag acknowledgment is required for deactivation. |
| **HAN / HOF** | HAN is the sole institutional actor during MVOS. HAN declares MVOS and confirms recovery. |
| **ICC-8 I7** | MVOS operationalizes I7 Continuity Invariance — institutional function persists through system failure. |
| **IMP** | All MVOS events logged as XOO, OEO, DRO, and GAO. |
| **ERDP** | MVOS activation and deactivation may trigger event-triggered disclosure. |
| **SPV Charters** | All three SPV entities enter Reduced Operations State during MVOS. |

---

## SECTION 11: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Trigger Definition** | All MVOS trigger conditions are defined and mapped to detection mechanisms. |
| **Operating State** | MVOS operating state is defined — HAN-only operations, existing commitments maintained. |
| **Recovery Protocol** | MVOS recovery protocol is defined with sequenced phases and timelines. |
| **Test Requirement** | MVOS testing is required — tabletop, partial, full, surprise drills. |
| **Post-Incident Review** | MVOS post-incident review is required — root cause analysis, lessons learned, corrective actions. |
| **SPV Integration** | MVOS triggers Reduced Operations State in all three SPV entities. |
| **I7 Compliance** | MVOS satisfies ICC-8 I7 Continuity Invariance — institutional function persists through system failure. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| MVOS v1.0 | Initial specification — HAN-only operations, recovery protocol |
| MVOS v2.0 | Complete rebuild — reconciliation with AWOF, Trigger System, ADTEP, HAN/HOF, and ICC-8 I7; expanded trigger conditions; HAN-only operations; SPV Reduced Operations State; testing and drills; post-incident review; EAF tier impact; CFL-V validation rules |

---

## The One-Sentence Summary

> *"MVOS v2.0 defines the Minimum Viable Operations State as a constitutional condition triggered by full AI workforce unavailability, Constitutional Suspension, HAN initiation, I9 Catastrophic Risk, widespread agent drift, or orchestrator cascade failure — transitioning the institution to HAN-only operations with no new material actions, existing commitments maintained, all three SPV entities in Reduced Operations State, and a sequenced recovery protocol satisfying ICC-8 I7 Continuity Invariance."*
