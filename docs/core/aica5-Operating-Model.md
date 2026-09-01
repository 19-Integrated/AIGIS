# AICA-5 Operating Model v2.0

**Status:** Built — v2.0 (Reconciliation with AICA-5, Measurement Framework, and Implementation Pathway) **Type:** Operational Instrument **Parent Stack:** AICA-5 (Control Architecture) **Version:** 2.0 — Supersedes AICA-5 Operating Model v1.0

---

## PREAMBLE

The AICA-5 Operating Model defines the 24 Governance Functions across 5 layers, each with a declared owner, tooling, cadence, input condition, output declaration, node dependency, failure indicator, and failure response. It answers: *How does AICA-5 run in practice?*

The Operating Model is the bridge between governance architecture and operational reality. It is not a policy statement. It is a declared operational activity that must be performed on a declared cadence to maintain a node's validity condition.

Every Governance Function in this Operating Model is executable by a certified practitioner without 19 Integrated on site. This is the product/services boundary: the Operating Model is the instrument that makes AICA-5 a licensable product, not just a consulting engagement.

---

## SECTION 1: CADENCE ARCHITECTURE

| Type | Definition | Examples |
| :---- | :---- | :---- |
| **Continuous** | Always running, no trigger required | C-N3, E-N2, A-N5, Co-N2, Co-N3, Ac-N1 |
| **Periodic** | Declared schedule — daily, weekly, or cycle-based | C-N1, C-N2, C-N4, E-N5, A-N1, A-N3, A-N4, Ac-N3, Ac-N4 |
| **Event-triggered** | Runs when a specific condition is met | E-N3, E-N4, A-N6, Co-N3, Co-N4, Co-N5, Ac-N2 |
| **Initiation-triggered** | Runs exactly once per workflow at inception | E-N1, A-N2, Co-N1 |

---

## SECTION 2: ROLES ARCHITECTURE

| Role | Scope | Count |
| :---- | :---- | :---- |
| **Layer Owner** | Accountable for all Governance Functions within one layer. Authorizes layer-level decisions and escalation responses. | 5 (one per layer) |
| **Node Steward** | Accountable for specific node validity conditions. Oversees Cadence Operators. May cover adjacent nodes in the dependency chain. | Variable by deployment |
| **Cadence Operator** | Performs continuous and periodic Governance Functions. Execution role — responsible for function performance but not accountable for layer health. | Variable by deployment |
| **Escalation Principal** | Receives A-N4 escalations and authority-level failure responses. Must be a human principal with binding authority (HAN or delegate). Cannot be a Cadence Operator. | 1 minimum; 1 per domain for large deployments |

---

## SECTION 3: GOVERNANCE FUNCTION TEMPLATE

Every Governance Function is documented across eight fields:

| Field | Content |
| :---- | :---- |
| **Function Identity** | Name, layer, cadence type |
| **Owner Role** | Accountable functional role |
| **Tooling Requirement** | Minimum tooling to perform the function |
| **Input Condition** | What must be true before this function runs |
| **Output Declaration** | What this function produces |
| **Node Dependency** | Which AICA-5 node(s) this function maintains |
| **Failure Indicator** | Observable signal of function degradation |
| **Failure Response** | Immediate action \+ escalation path \+ fallback function |

---

## SECTION 4: LAYER 1 — COGNITIVE LAYER

### CGF-1 — Source Registry Maintenance

**Function Identity:** Cognitive Layer · Periodic (weekly minimum; daily for high-velocity environments)

**Owner Role:** Node Steward (C-N1)

**Tooling Requirement:** Source credentialing registry with version control; contamination flag capability; refresh cycle tracking

**Input Condition:** Active intelligence sources are declared and logged. No source admitted without a registry entry.

**Output Declaration:** Updated source registry with current credential status, last validation timestamp, and contamination flag state for every active source.

**Node Dependency:** C-N1 Intelligence Sourcing

**Failure Indicator:** Source feeds active without registry entries; credential status undated beyond refresh cycle; contamination flags absent on recently admitted sources.

**Failure Response:** Immediate: Suspend unregistered/overdue sources. Escalation: Layer Owner (Cognitive) reviews registry. Fallback: Revert to last clean registry state.

---

### CGF-2 — Inference Calibration Review

**Function Identity:** Cognitive Layer · Periodic (per delivery cycle or weekly, whichever is shorter)

**Owner Role:** Node Steward (C-N2, C-N3)

**Tooling Requirement:** Reasoning chain logging system; confidence differentiation instrument; output type taxonomy

**Input Condition:** Inference outputs from current cycle are logged. CGF-1 completed for same cycle.

**Output Declaration:** Calibration review record confirming reasoning chain completeness, confidence differentiation adequacy, and output type classification accuracy.

**Node Dependency:** C-N2 Inference Architecture · C-N3 Signal Validation

**Failure Indicator:** Reasoning chains absent or uniform; confidence assignments undifferentiated; output type classifications missing.

**Failure Response:** Immediate: Flag affected outputs unvalidated; suspend downstream consumption. Escalation: Layer Owner notified; E-N1 intake suspended. Fallback: Reprocess with logging enforced.

---

### CGF-3 — Signal Validation Gate Operation

**Function Identity:** Cognitive Layer · Continuous (gates every output before downstream release)

**Owner Role:** Cadence Operator (under Node Steward C-N3 oversight)

**Tooling Requirement:** Automated validation gate with threshold configuration; failed validation alert system; suppression detection log

**Input Condition:** Inference outputs have completed CGF-2. Validation thresholds current and version-controlled.

**Output Declaration:** Per-output validation status record — passed, failed, or flagged — attached before downstream release. Failed validations logged and alerted, never suppressed.

**Node Dependency:** C-N3 Signal Validation

**Failure Indicator:** Outputs reaching Execution Layer without validation status; failed validations absent from alert log; suppression events detected.

**Failure Response:** Immediate: Quarantine outputs lacking validation status; halt Execution intake. Escalation: Layer Owner (Cognitive) \+ Layer Owner (Execution) — dual custody protocol. Fallback: Manual validation by Node Steward.

---

### CGF-4 — Knowledge Boundary Declaration and Review

**Function Identity:** Cognitive Layer · Periodic (monthly minimum; additionally on new domain activation or model update)

**Owner Role:** Layer Owner (Cognitive)

**Tooling Requirement:** Domain boundary registry; overreach detection log; confidence floor tracking by domain

**Input Condition:** All active domains have declared boundaries with temporal validity and confidence floors. Overreach detection active.

**Output Declaration:** Updated boundary registry with current domain scope, confidence floor, temporal validity window, and overreach event log for the review period.

**Node Dependency:** C-N5 Knowledge Boundary Management

**Failure Indicator:** Domains active without declared boundaries; overreach events unlogged; confidence floors absent or not reviewed within declared cycle.

**Failure Response:** Immediate: Suspend outputs from domains with undeclared/expired boundaries. Escalation: Escalation Principal if overreach reached Authority Layer. Fallback: Restrict to last validated boundary declarations.

---

## SECTION 5: LAYER 2 — EXECUTION LAYER

### EGF-1 — Workflow Initiation Clearance

**Function Identity:** Execution Layer · Initiation-triggered (once per workflow at activation)

**Owner Role:** Node Steward (E-N1)

**Tooling Requirement:** Task decomposition template; dependency map tool; assignment registry; completion criteria log

**Input Condition:** High-level objective declared. Intelligence inputs passed CGF-3. No pipeline activates before clearance is issued.

**Output Declaration:** Initiation clearance record confirming all execution units have declared scope boundaries, dependency maps, assignment owners, and completion criteria. Prerequisite for pipeline activation.

**Node Dependency:** E-N1 Task Decomposition

**Failure Indicator:** Pipelines activated without clearance records; execution units missing scope or completion criteria; dependency maps absent.

**Failure Response:** Immediate: Halt pipeline; require clearance before reactivation. Escalation: Layer Owner (Execution) reviews decomposition. Fallback: Redecompose using declared template; re-issue clearance.

---

### EGF-2 — Pipeline Orchestration Monitoring

**Function Identity:** Execution Layer · Continuous

**Owner Role:** Cadence Operator (under Node Steward E-N2 oversight)

**Tooling Requirement:** Orchestration dashboard with ownership display; state reconciliation log; deadlock detection alert

**Input Condition:** EGF-1 clearance issued. All active pipelines have declared orchestration owners and handoff protocols.

**Output Declaration:** Continuous orchestration status record — active pipelines, ownership assignments, state reconciliation events, and deadlock alerts — updated in real time.

**Node Dependency:** E-N2 Pipeline Orchestration

**Failure Indicator:** Pipelines without declared orchestration owners; state reconciliation events unlogged; deadlock alerts firing without resolution.

**Failure Response:** Immediate: Assign emergency orchestration ownership; freeze state at last valid checkpoint. Escalation: Layer Owner (Execution); A-N4 if threshold breached. Fallback: Roll back to last confirmed shared state.

---

### EGF-3 — Concurrency Authorization

**Function Identity:** Execution Layer · Event-triggered (before any parallel execution set activates)

**Owner Role:** Node Steward (E-N3)

**Tooling Requirement:** Concurrency eligibility matrix; state isolation boundary declaration; merge protocol registry

**Input Condition:** Parallel execution proposed. EGF-2 monitoring active. Concurrency eligibility criteria current.

**Output Declaration:** Concurrency authorization record per parallel set — eligibility confirmed, state isolation declared, merge protocol assigned. No parallel execution activates without this record.

**Node Dependency:** E-N3 Concurrency Governance

**Failure Indicator:** Parallel sets active without authorization records; state isolation boundaries undeclared; merge protocols absent.

**Failure Response:** Immediate: Halt unauthorized parallel sets; isolate diverged states. Escalation: Layer Owner (Execution) applies merge protocol or escalates to adjudication. Fallback: Serialize execution pending re-authorization.

---

### EGF-4 — Exception Classification and Containment

**Function Identity:** Execution Layer · Event-triggered (on anomaly detection from EGF-2)

**Owner Role:** Node Steward (E-N5)

**Tooling Requirement:** Exception classification taxonomy; containment protocol library; escalation threshold registry

**Input Condition:** Anomaly detected by EGF-2. Exception classification scheme current and version-controlled.

**Output Declaration:** Exception record per event — classification, containment action, escalation threshold status, and resolution or escalation outcome.

**Node Dependency:** E-N5 Exception Handling

**Failure Indicator:** Exceptions unclassified or misclassified; containment not applied within threshold; exceptions propagating to Authority Layer without classification records.

**Failure Response:** Immediate: Classify retroactively; contain at current layer. Escalation: A-N1 Trigger Rights review — boundary dual custody invoked (E-N5 exit, A-N1 intake). Fallback: Default containment pending classification; patch gap.

---

### EGF-5 — Monitoring Coverage Audit

**Function Identity:** Execution Layer · Periodic (weekly minimum; additionally on new pipeline type introduction)

**Owner Role:** Layer Owner (Execution)

**Tooling Requirement:** Coverage map tool; blind spot detection log; monitoring cycle interval registry

**Input Condition:** All active pipeline types declared. EGF-2 monitoring running.

**Output Declaration:** Coverage audit record confirming all active pipeline types have declared monitoring coverage. Blind spots named and assigned for remediation — not silently accepted.

**Node Dependency:** E-N4 Monitoring Loops

**Failure Indicator:** Pipeline types active without monitoring coverage declarations; audit cycle overdue; blind spots without remediation assignments.

**Failure Response:** Immediate: Assign monitoring to uncovered pipelines; audit unmonitored execution for anomalies. Escalation: Escalation Principal if unmonitored execution produced binding outputs. Fallback: Restrict new pipeline activation until audit closed.

---

## SECTION 6: LAYER 3 — AUTHORITY LAYER

### AGF-1 — Trigger Rights Map Maintenance

**Function Identity:** Authority Layer · Periodic (reviewed per governance cycle; updated immediately on new action class introduction)

**Owner Role:** Layer Owner (Authority)

**Tooling Requirement:** Trigger rights registry with version control; action class taxonomy; enforcement audit log

**Input Condition:** All executable action classes declared. Enforcement mechanism active and auditable.

**Output Declaration:** Current trigger rights map — every action class with declared initiator rights, last review timestamp, and enforcement status.

**Node Dependency:** A-N1 Trigger Rights ★ Keystone

**Failure Indicator:** Action classes active without trigger rights declarations; enforcement audit log gaps; map not reviewed within declared cycle.

**Failure Response:** Immediate: Suspend all action classes without valid trigger rights. Escalation: Escalation Principal — A-N1 failure has highest cascade consequence. Fallback: Restrict to action classes with confirmed trigger rights.

---

### AGF-2 — Binding Threshold Declaration

**Function Identity:** Authority Layer · Initiation-triggered (at workflow initiation for each output class produced)

**Owner Role:** Node Steward (A-N2)

**Tooling Requirement:** Binding threshold registry; consequence scope declaration template; external fitness declaration generator

**Input Condition:** Workflow received EGF-1 clearance. Output classes for the workflow declared before execution begins.

**Output Declaration:** Per-workflow binding threshold record — every output class with binding status, consequence scope, confirmation requirements, and external fitness declaration where applicable. Immutable once declared.

**Node Dependency:** A-N2 Binding Thresholds

**Failure Indicator:** Output classes produced without binding declarations; consequence scope absent or ambiguous; external fitness declarations missing for external boundary outputs.

**Failure Response:** Immediate: Flag outputs without declarations as unclassified; suspend external boundary crossing. Escalation: Escalation Principal if unclassified outputs crossed external boundary. Fallback: Provisional binding status; log as governance exception.

---

### AGF-3 — Override Protocol Readiness

**Function Identity:** Authority Layer · Periodic (tested per governance cycle; activated on-demand on override condition)

**Owner Role:** Layer Owner (Authority)

**Tooling Requirement:** Override invocation interface accessible to non-technical principals; state preservation mechanism; override event log

**Input Condition:** Binding threshold declarations (AGF-2) current. Override mechanisms declared for all binding output classes.

**Output Declaration:** Override readiness record per cycle — mechanisms tested, invocation procedures confirmed reachable, state preservation confirmed functional. Per-event override records when activated.

**Node Dependency:** A-N3 Override Protocols

**Failure Indicator:** Override mechanisms untested beyond declared cycle; invocation requiring system-level access; state preservation failures during override events.

**Failure Response:** Immediate: Halt binding execution where override unreachable. Escalation: Escalation Principal — override unavailability requires immediate principal intervention. Fallback: Manual override by Escalation Principal; post-event repair mandatory.

---

### AGF-4 — Escalation Path Verification

**Function Identity:** Authority Layer · Periodic (verified per governance cycle; activated on event trigger)

**Owner Role:** Layer Owner (Authority)

**Tooling Requirement:** Escalation path registry; authority chain availability monitor; response time threshold tracker; default action library

**Input Condition:** Escalation paths declared for all executable exception classes. Authority chain availability monitored.

**Output Declaration:** Escalation readiness record per cycle — paths tested, authority chain confirmed, response thresholds active, default actions declared. Per-event records when activated.

**Node Dependency:** A-N4 Escalation Paths

**Failure Indicator:** Escalation paths untested; authority chain unavailable without fallback; response time thresholds breached without default action triggered.

**Failure Response:** Immediate: Apply declared default action. Escalation: Escalation Principal assumes direct authority; retroactive path reconstruction mandatory. Fallback: Restrict to action classes with confirmed escalation paths.

---

### AGF-5 — Delegation Boundary Enforcement

**Function Identity:** Authority Layer · Continuous (creep detection always running; formal review periodic)

**Owner Role:** Node Steward (A-N5)

**Tooling Requirement:** Delegation registry with scope and duration tracking; creep detection alert system; revocation protocol log

**Input Condition:** All active delegations have declared scope, duration, and revocation triggers. Creep detection active.

**Output Declaration:** Delegation status record — all active delegations with scope compliance, duration validity, and creep detection alert log. Boundary extensions logged as governance events requiring re-authorization.

**Node Dependency:** A-N5 Delegation Boundaries

**Failure Indicator:** Active delegations without declared scope or duration; creep detection alerts unresolved; boundary extensions without re-authorization.

**Failure Response:** Immediate: Revoke delegations with confirmed boundary violations; suspend affected execution. Escalation: Escalation Principal if creep produced binding outputs. Fallback: Revert all delegations to last confirmed valid scope.

---

### AGF-6 — Authority State Handoff to Continuity

**Function Identity:** Authority Layer · Event-triggered (at every authority state change)

**Owner Role:** Node Steward (A-N5) in coordination with Node Steward (Co-N1)

**Tooling Requirement:** Authority state snapshot tool; handoff record generator; Co-N1 state establishment interface

**Input Condition:** An authority state change event has occurred. Co-N1 State Establishment active and capable of receiving updated state.

**Output Declaration:** Authority state handoff record — current delegation state, active binding thresholds, override status, and escalation path availability — transferred to Continuity Layer as Co-N1 input. Operational instantiation of A-N5 → Co-N1 dual custody protocol.

**Node Dependency:** A-N5 Delegation Boundaries · Co-N1 State Establishment (boundary function)

**Failure Indicator:** Authority state changes not reflected in Co-N1 baseline; handoff records absent after authority events; Continuity Layer operating on stale authority state.

**Failure Response:** Immediate: Force authority state snapshot; retransfer to Co-N1 with full current state. Escalation: Layer Owner (Authority) \+ Layer Owner (Continuity) — cross-layer dual custody failure. Fallback: Freeze workflows dependent on changed authority state until handoff confirmed.

---

## SECTION 7: LAYER 4 — CONTINUITY LAYER

### COGF-1 — Workflow State Baseline Declaration

**Function Identity:** Continuity Layer · Initiation-triggered (once per workflow at inception, after AGF-2)

**Owner Role:** Node Steward (Co-N1)

**Tooling Requirement:** State baseline declaration template; immutable record store; authority state interface (receives from AGF-6)

**Input Condition:** AGF-2 binding threshold declaration complete. AGF-6 authority state handoff current. No workflow proceeds without a confirmed baseline.

**Output Declaration:** Immutable workflow baseline record capturing active authority assignments, input validity status, pipeline configuration, binding threshold declarations, and inception timestamp. Reference point for all subsequent continuity governance in this workflow.

**Node Dependency:** Co-N1 State Establishment ★ Keystone

**Failure Indicator:** Workflows active without baseline records; baseline records missing authority state or binding threshold data; records editable after declaration.

**Failure Response:** Immediate: Suspend workflow; reconstruct baseline from available initiation artifacts. Escalation: Layer Owner (Continuity) validates reconstruction. Fallback: Declare reconstructed baseline with flag; require Layer Owner authorization to proceed.

---

### COGF-2 — Continuous Drift Surveillance

**Function Identity:** Continuity Layer · Continuous

**Owner Role:** Cadence Operator (under Node Steward Co-N2 oversight)

**Tooling Requirement:** Real-time state monitoring against COGF-1 baseline; cumulative deviation tracker; silent drift detection capability; threshold alert system

**Input Condition:** COGF-1 baseline declared. All active workflows enrolled in drift surveillance at initiation.

**Output Declaration:** Continuous drift status per active workflow — individual deviation events, cumulative deviation score, silent drift detection status, and threshold breach alerts in real time.

**Node Dependency:** Co-N2 Drift Detection

**Failure Indicator:** Workflows not enrolled in surveillance; cumulative deviation untracked; silent drift — gradual below-threshold accumulation — undetected.

**Failure Response:** Immediate: Enroll unmonitored workflows; audit recent unmonitored period for accumulated drift. Escalation: Layer Owner (Continuity) reviews cumulative deviation; workflow restart if irreconcilable. Fallback: Freeze at last confirmed valid state.

---

### COGF-3 — Approval Validity Monitoring

**Function Identity:** Continuity Layer · Continuous (expiry monitoring always running; reauthorization requests event-triggered on proximity alert)

**Owner Role:** Node Steward (Co-N3)

**Tooling Requirement:** Approval registry with expiry window tracking; proximity alert system; reauthorization request generator; lapsed approval suspension mechanism

**Input Condition:** All active approvals have declared expiry windows established at COGF-1 baseline. Proximity alert thresholds configured.

**Output Declaration:** Approval validity status record — all active approvals with current validity, proximity alert state, and reauthorization request log. Lapsed approval suspension events recorded as governance events.

**Node Dependency:** Co-N3 Approval Expiry

**Failure Indicator:** Approvals active beyond declared expiry windows; proximity alerts not firing; lapsed approval suspension not triggering automatically.

**Failure Response:** Immediate: Suspend execution dependent on lapsed approvals; trigger emergency reauthorization. Escalation: Escalation Principal if lapsed approvals governed binding outputs. Fallback: Revert to last valid approval state; audit decisions under stale authorization.

---

### COGF-4 — Handoff Integrity Verification

**Function Identity:** Continuity Layer · Event-triggered (at every agent-to-agent, agent-to-human, and human-to-agent transition)

**Owner Role:** Node Steward (Co-N4)

**Tooling Requirement:** State transfer record generator; receiving party confirmation interface; truncation detection mechanism; handoff integrity log

**Input Condition:** A handoff event declared. COGF-1 baseline, COGF-2 drift status, and COGF-3 approval validity all current at point of handoff.

**Output Declaration:** Per-handoff integrity record — complete state transfer package validated against current baseline, receiving party confirmation, and truncation detection status. Truncated handoffs rejected and logged.

**Node Dependency:** Co-N4 Handoff Integrity

**Failure Indicator:** Handoffs completed without integrity records; receiving party confirmation absent; truncated state transfers accepted without rejection and re-transfer.

**Failure Response:** Immediate: Reject truncated handoff; reconstruct complete state; retransfer. Escalation: Layer Owner (Continuity) \+ Layer Owner (Accountability) — lineage risk. Fallback: Suspend handoff-dependent execution until integrity verified.

---

### COGF-5 — Context Restoration Clearance

**Function Identity:** Continuity Layer · Event-triggered (before workflow resumption after any interruption, override, or partial failure)

**Owner Role:** Layer Owner (Continuity)

**Tooling Requirement:** Context reconstruction tool; restoration completeness checklist against COGF-1 baseline; false resumption detection; resumption authorization log

**Input Condition:** Resumption proposed after disruption. COGF-1 baseline exists. COGF-2 drift status and COGF-3 approval validity assessed at point of restoration.

**Output Declaration:** Restoration clearance record — completeness status against baseline, partial restoration declaration where applicable, explicit resumption authorization by Layer Owner. No workflow resumes without this record.

**Node Dependency:** Co-N5 Context Restoration

**Failure Indicator:** Workflows resuming without clearance records; partial restorations undisclosed; false resumption — resumption under assumed-complete but incomplete context — undetected.

**Failure Response:** Immediate: Halt false resumption; freeze at earliest valid checkpoint. Escalation: Layer Owner (Continuity) \+ Layer Owner (Accountability) jointly. Fallback: Restart workflow from COGF-1 baseline if restoration irrecoverable.

---

## SECTION 8: LAYER 5 — ACCOUNTABILITY LAYER

### ACGF-1 — Decision Lineage Recording

**Function Identity:** Accountability Layer · Continuous

**Owner Role:** Cadence Operator (under Node Steward Ac-N1 oversight)

**Tooling Requirement:** Immutable decision log with input capture; authority record interface; executor identity recording; state context snapshot at decision point; gap detection alert

**Input Condition:** All active workflows have COGF-1 baselines. Authority records from AGF-2 current. No decision recorded without full lineage components.

**Output Declaration:** Continuous per-decision lineage record — inputs, authority assignment, executor identity, state context, and timestamp. Records immutable once written. Gap detection alerts fire immediately on missing components.

**Node Dependency:** Ac-N1 Decision Lineage

**Failure Indicator:** Decisions without lineage records; records missing authority or executor components; gap detection alerts suppressed or unresolved.

**Failure Response:** Immediate: Reconstruct from available artifacts; declare reconstruction status and confidence level. Escalation: Escalation Principal — lineage gaps on binding decisions require immediate review. Fallback: Flag for heightened review; patch recording architecture before new decisions proceed.

---

### ACGF-2 — Responsibility Attribution Management

**Function Identity:** Accountability Layer · Event-triggered (at decision completion, handoff, and escalation resolution events)

**Owner Role:** Node Steward (Ac-N2)

**Tooling Requirement:** Attribution registry with dimension-specific assignment; multi-actor scope declaration template; external disclosure interface

**Input Condition:** ACGF-1 lineage record complete for the relevant decision. COGF-4 handoff integrity record available where handoffs involved.

**Output Declaration:** Per-decision attribution record — responsible actor declared per accountability dimension (authorization, execution, oversight). Multi-actor assignments specify each actor's scope unambiguously. External fitness declarations generated where required by SP2.

**Node Dependency:** Ac-N2 Responsibility Attribution

**Failure Indicator:** Decisions without attribution records; multi-actor assignments with ambiguous dimension scope; external fitness declarations absent for external boundary outputs.

**Failure Response:** Immediate: Reconstruct from ACGF-1 lineage and COGF-4 handoff records. Escalation: Layer Owner (Accountability) resolves ambiguity through authority chain review. Fallback: Provisional attribution by dimension; flag for formal resolution within one governance cycle.

---

### ACGF-3 — Outcome Validation Cycle

**Function Identity:** Accountability Layer · Periodic (cycle declared per decision class at workflow initiation — not post-hoc)

**Owner Role:** Layer Owner (Accountability)

**Tooling Requirement:** Outcome measurement instrument by decision class; variance classification taxonomy; validation debt registry

**Input Condition:** Validation criteria and measurement timing declared at workflow initiation per AGF-2. ACGF-1 lineage and ACGF-2 attribution records complete.

**Output Declaration:** Per-cycle validation record — outcomes measured against declared criteria, variance classified, above-threshold variances flagged for ACGF-4 review. Validation debt declared explicitly when irrecoverable deferral has occurred.

**Node Dependency:** Ac-N3 Outcome Validation

**Failure Indicator:** Validation cycles missed or deferred beyond declared timing; variance thresholds qualitative rather than quantified; above-threshold variances not triggering rollback or learning review.

**Failure Response:** Immediate: Conduct catch-up validation; declare validation debt for irrecoverable gaps. Escalation: Escalation Principal if above-threshold variance involves binding decisions with external consequences. Fallback: Maximum feasible retrospective measurement; log irrecoverable gaps.

---

### ACGF-4 — Learning Integration and Architecture Update

**Function Identity:** Accountability Layer · Periodic (review cycle declared; update cadence governed by impact level)

**Owner Role:** Layer Owner (Accountability) for operational-level updates; Escalation Principal authorization required for architecture-level updates

**Tooling Requirement:** Learning artifact registry; impact classification tool; version control for architecture updates; update-to-validation-event traceability log

**Input Condition:** ACGF-3 validation cycle has produced above-threshold variance findings or rollback events. Learning artifacts logged and classified by architecture impact level.

**Output Declaration:** Per-cycle learning integration record — artifacts reviewed, impact classifications, operational updates implemented, architecture-level updates submitted for authorization. Every architecture update traceable to originating validation event. Cognitive Layer corrections fed back upstream as architecture self-correction loop.

**Node Dependency:** Ac-N5 Learning Integration ★ Keystone

**Failure Indicator:** Validation findings in logs without learning artifact generation; architecture updates not traceable to originating events; learning integration cycle overdue; Cognitive Layer not receiving upstream corrections.

**Failure Response:** Immediate: Audit logs; generate learning artifacts retroactively. Escalation: Escalation Principal reviews architecture-level findings; unintegrated high-impact findings trigger holdco notification. Fallback: Implement operational-level updates immediately; queue architecture-level updates for next authorized review.

---

## SECTION 9: FAILURE RESPONSE MATRIX

| Function | Failure Indicator | Immediate Action | Escalation Path | Fallback |
| :---- | :---- | :---- | :---- | :---- |
| CGF-1 | Unregistered sources active; stale credentials | Suspend unregistered/overdue feeds | Layer Owner (Cognitive) | Revert to last clean registry |
| CGF-2 | Uniform confidence; absent reasoning chains | Flag outputs unvalidated; suspend downstream | Layer Owner; E-N1 intake suspended | Reprocess with logging enforced |
| CGF-3 | Outputs reaching Execution without validation | Quarantine; halt Execution intake | Layer Owner (Cognitive) \+ Layer Owner (Execution) | Manual validation by Node Steward |
| CGF-4 | Domains active without boundaries; overreach unlogged | Suspend outputs from undeclared domains | Escalation Principal if overreach reached Authority Layer | Restrict to last validated boundaries |
| EGF-1 | Pipelines activated without clearance | Halt pipeline; require clearance | Layer Owner (Execution) | Redecompose; re-issue clearance |
| EGF-2 | Pipelines without owners; deadlocks unresolved | Assign emergency ownership; freeze state | Layer Owner (Execution); A-N4 if threshold breached | Roll back to last confirmed shared state |
| EGF-3 | Parallel sets active without authorization | Halt unauthorized parallel sets | Layer Owner (Execution) | Serialize execution pending re-authorization |
| EGF-4 | Exceptions unclassified; propagating to Authority | Classify retroactively; contain | A-N1 Trigger Rights review — dual custody | Default containment pending classification |
| EGF-5 | Pipeline types without monitoring coverage | Assign immediate monitoring; audit unmonitored period | Escalation Principal if binding outputs unmonitored | Restrict new pipeline activation |
| AGF-1 | Action classes without trigger rights | Suspend undeclared action classes | Escalation Principal — highest cascade consequence | Restrict to confirmed trigger rights only |
| AGF-2 | Outputs without binding declarations | Flag unclassified; suspend external crossing | Escalation Principal if boundary already crossed | Provisional binding status; log exception |
| AGF-3 | Override mechanisms untested or unreachable | Halt binding execution where override unreachable | Escalation Principal — direct intervention | Manual override by Escalation Principal |
| AGF-4 | Escalation paths untested; default actions absent | Apply declared default action | Escalation Principal assumes direct authority | Restrict to confirmed escalation path classes |
| AGF-5 | Delegations without scope; creep unresolved | Revoke boundary-violating delegations | Escalation Principal if creep produced binding outputs | Revert all delegations to last valid scope |
| AGF-6 | Authority state changes not in Co-N1 | Force snapshot; retransfer to Co-N1 | Layer Owner (Authority) \+ Layer Owner (Continuity) | Freeze authority-state-dependent workflows |
| COGF-1 | Workflows without baseline records | Suspend workflow; reconstruct baseline | Layer Owner (Continuity) validates reconstruction | Reconstructed baseline with flag; require authorization |
| COGF-2 | Workflows unenrolled; cumulative drift untracked | Enroll immediately; audit unmonitored period | Layer Owner (Continuity) assesses reconcilability | Freeze at last confirmed valid state |
| COGF-3 | Approvals beyond expiry; suspension not triggering | Suspend lapsed-approval execution; emergency reauth | Escalation Principal if lapsed approvals governed binding outputs | Revert to last valid approval state |
| COGF-4 | Handoffs without integrity; truncation accepted | Reject truncated handoff; retransfer | Layer Owner (Continuity) \+ Layer Owner (Accountability) | Suspend handoff-dependent execution |
| COGF-5 | Resumption without clearance; false resumption | Halt false resumption; freeze at valid checkpoint | Layer Owner (Continuity) \+ Layer Owner (Accountability) | Restart from COGF-1 baseline |
| ACGF-1 | Decisions without lineage; gap alerts suppressed | Reconstruct; declare reconstruction status | Escalation Principal — binding decisions | Flag for heightened review; patch recording architecture |
| ACGF-2 | Decisions without attribution; ambiguous scope | Reconstruct from lineage and handoff records | Layer Owner (Accountability) | Provisional attribution; formal resolution within one cycle |
| ACGF-3 | Validation cycles deferred; variance not triggering | Catch-up validation; declare validation debt | Escalation Principal if binding decisions affected | Maximum retrospective measurement; log gaps |
| ACGF-4 | Learning artifacts unintegrated; updates untraceable | Audit logs; generate artifacts retroactively | Escalation Principal; holdco notification for architecture failures | Operational updates immediately; queue architecture updates |

---

## SECTION 10: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| AICA-5 | Defines the nodes — Operating Model operationalizes them |
| AICA-5 Measurement Framework | References Failure Response Matrix by function ID |
| AICA-5 Implementation Pathway | Operating Model functions activated per phase |
| AITOS | Process layer — Operating Model is the steady-state execution |
| AWOF | Workforce governance — agents execute Operating Model functions |
| HAN / HOF | Human authority — Escalation Principal role defined in HOF |
| ADTEP | Technical enforcement — Operating Model functions feed into ADTEP |

---

## SECTION 11: CFL-V VALIDATION RULES

**Rule 1 — Function Completeness:** All 24 Governance Functions are defined and mapped to nodes.

**Rule 2 — Owner Assignment:** Every function has a declared owner role.

**Rule 3 — Cadence Defined:** Every function has a declared cadence (Continuous/Periodic/Event-triggered/Initiation-triggered).

**Rule 4 — Failure Response Defined:** Every function has a declared Failure Indicator, Immediate Action, Escalation Path, and Fallback.

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| AICA-5 Operating Model v1.0 | Initial 24 Governance Functions |
| AICA-5 Operating Model v2.0 | Complete rebuild — reconciliation with AICA-5, Measurement Framework, and Implementation Pathway; expanded function definitions; Failure Response Matrix; CFL-V validation rules |

---

## The One-Sentence Summary

> *"The AICA-5 Operating Model v2.0 defines 24 Governance Functions across 5 layers — each with a declared owner, tooling, cadence, input condition, output declaration, node dependency, failure indicator, and failure response — forming the bridge between governance architecture and operational reality, making AICA-5 executable by certified practitioners without 19 Integrated on site."*
