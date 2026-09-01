# AICA-5 Measurement Framework v2.0

**Status:** Built — v2.0 (Reconciliation with AICA-5, Operating Model, and Implementation Pathway) **Type:** Measurement Instrument **Parent Stack:** AICA-5 (Control Architecture) **Version:** 2.0 — Supersedes AICA-5 Measurement Framework v1.0

---

## PREAMBLE

The AICA-5 Measurement Framework defines 39 Governance Health Indicators (GHIs) across 5 layers and 3 reporting tiers. It answers: *How do we continuously observe governance health?*

A Governance Health Indicator is a control signal, not a performance metric. It measures whether the governance architecture is functioning within its declared validity conditions — not whether the business is performing. Healthy business performance is not evidence of healthy governance architecture.

**Aggregation Logic — Option C Dual Reporting:** Operational and Governance tiers report worst-node — layer health is the score of its lowest-performing GHI. No averaging. Degradation cannot be hidden behind healthy indicators. Institutional tier reports weighted average headline score alongside explicit disclosure of all Red indicators and any keystone node GHIs below Green threshold.

---

## SECTION 1: GHI STANDARD TEMPLATE

Every GHI is documented across eight fields:

| Field | Content |
| :---- | :---- |
| Indicator Identity | Name, layer, linked Governance Function or node |
| Measurement Definition | Precisely what is measured and how |
| Measurement Frequency | Sampling cadence |
| Green Threshold | Healthy operating condition |
| Amber Threshold | Degradation risk signal |
| Red Threshold | Active governance failure |
| Reporting Destination | Audience and frequency |
| Escalation Trigger | References Operating Model Failure Response matrix by function ID |

---

## SECTION 2: REPORTING ARCHITECTURE

| Tier | Audience | Frequency | Aggregation | Content |
| :---- | :---- | :---- | :---- | :---- |
| **Operational** | Layer Owners, Node Stewards, Cadence Operators | Continuous / Daily | Raw GHI status — no aggregation | All 39 GHIs at current status. Red indicators flagged for immediate action. Keystone Node GHIs displayed separately at top. |
| **Governance** | Escalation Principal | Weekly | Worst-node per layer \+ all Red indicators | Five layer worst-node scores. All Red indicators with resolution status. Persistent Amber indicators. Keystone Node GHI status. Escalation events summary. |
| **Institutional** | Holdco / Board / Regulators / Auditors | Quarterly | Weighted average \+ Red disclosures | Architecture health score. Material disclosures. External boundary declarations. Interoperability status. Escalation Principal attestation. |

**Institutional attestation:** The Escalation Principal signs the quarterly declaration. False attestation by the Escalation Principal is a declared Ac-N2 violation and triggers A-N4 escalation to holdco.

---

## SECTION 3: KEYSTONE NODE GHIs (HIGHEST-TIER INSTITUTIONAL INDICATORS)

### KN-GHI-1 — Trigger Rights Coverage ★ Keystone

**Measurement:** % of executable action classes in current production with a declared trigger rights entry. Measures coverage completeness independent of AGF-1 function health.

**Frequency:** Weekly scan of production action classes against trigger rights registry

| Threshold | Status |
| :---- | :---- |
| Green: 100% of production action classes have declared trigger rights. No exceptions. | ✅ Operational |
| Amber: 95–99% coverage. One or more classes without declaration, in remediation within current cycle. | ⚠️ Degradation risk |
| Red: Below 95% coverage, or any action class producing binding outputs without a trigger rights declaration. | ❌ Active failure |

**Reporting:** All tiers

**Escalation Trigger:** → AGF-1 Failure Response (Operating Model)

---

### KN-GHI-2 — Binding Threshold Declaration Coverage ★ Keystone

**Measurement:** % of output classes produced in the current period with a valid AGF-2 binding threshold declaration on record.

**Frequency:** Per workflow cycle — every output class produced is checked against AGF-2 records

| Threshold | Status |
| :---- | :---- |
| Green: 100% of output classes have valid declarations. External boundary outputs confirmed with fitness declaration. | ✅ Operational |
| Amber: 95–99% coverage. Undeclared classes in remediation. No external boundary outputs undeclared. | ⚠️ Degradation risk |
| Red: Any external boundary output without a fitness declaration, or below 95% overall coverage. | ❌ Active failure |

**Reporting:** All tiers

**Escalation Trigger:** → AGF-2 Failure Response (Operating Model)

---

### KN-GHI-3 — State Baseline Completeness ★ Keystone

**Measurement:** % of workflows initiated in the current period with a valid COGF-1 baseline record.

**Frequency:** Per workflow initiation — each new workflow checked for baseline record at activation

| Threshold | Status |
| :---- | :---- |
| Green: 100% of workflows have valid baseline records. No in-flight workflows without baselines. | ✅ Operational |
| Amber: One or more workflows initiated without baseline, identified within 24 hours, no binding outputs produced. | ⚠️ Degradation risk |
| Red: Any workflow producing binding outputs without a valid baseline, or any unbaselined in-flight workflow persisting beyond 24 hours. | ❌ Active failure |

**Reporting:** All tiers

**Escalation Trigger:** → COGF-1 Failure Response (Operating Model)

---

### KN-GHI-4 — Drift Detection Enrollment ★ Keystone

**Measurement:** % of active workflows currently enrolled in continuous drift surveillance.

**Frequency:** Continuous — enrollment status checked at every workflow state transition

| Threshold | Status |
| :---- | :---- |
| Green: 100% of active workflows enrolled. No enrollment gaps beyond 15-minute activation latency maximum. | ✅ Operational |
| Amber: One or more workflows without enrollment, identified within one operating cycle and enrolled before next state transition. | ⚠️ Degradation risk |
| Red: Any workflow producing outputs after 15-minute enrollment window without surveillance, or cumulative drift detected in any unenrolled workflow. | ❌ Active failure |

**Reporting:** All tiers

**Escalation Trigger:** → COGF-2 Failure Response (Operating Model)

---

### KN-GHI-5 — Learning Loop Integrity ★ Keystone

**Measurement:** Ratio of above-threshold ACGF-3 validation findings to confirmed architecture updates traceable to those findings. A ratio below 1:1 means learning artifacts accumulate without integration.

**Frequency:** Per ACGF-3 validation cycle completion

| Threshold | Status |
| :---- | :---- |
| Green: All above-threshold findings have declared learning artifacts. All artifacts beyond declared integration window have confirmed updates or authorized deferrals. | ✅ Operational |
| Amber: One or more artifacts in queue beyond declared window without update or authorized deferral. No Cognitive Layer corrections overdue. | ⚠️ Degradation risk |
| Red: High-impact findings beyond two integration cycles without update or deferral. Or Cognitive Layer not receiving upstream corrections within declared feedback cycle. | ❌ Active failure |

**Reporting:** All tiers — Red triggers holdco notification under 19-IPAS

**Escalation Trigger:** → ACGF-4 Failure Response (Operating Model)

---

## SECTION 4: COGNITIVE LAYER GHIs (6 INDICATORS)

### C-GHI-1 — Source Credential Currency

**Measurement:** % of active sources with credential status updated within declared refresh cycle.

**Frequency:** Daily

| Threshold | Status |
| :---- | :---- |
| Green: 100% of sources current within refresh cycle. Zero contamination flags unresolved. | ✅ Operational |
| Amber: One or more sources overdue for refresh by less than one cycle. No contamination flags active. | ⚠️ Degradation risk |
| Red: Any source feeding active pipelines with credential status overdue by more than one cycle, or any unresolved contamination flag. | ❌ Active failure |

**Reporting:** Ops daily; Gov weekly

**Escalation Trigger:** → CGF-1 Failure Response (Operating Model)

---

### C-GHI-2 — Inference Chain Completeness

**Measurement:** % of inference outputs in current cycle with complete reasoning chain logs and differentiated confidence assignments.

**Frequency:** Per inference cycle

| Threshold | Status |
| :---- | :---- |
| Green: 100% completeness. Confidence differentiated across all output types. | ✅ Operational |
| Amber: 95–99% completeness. Missing chains identified and flagged. No uniform confidence assignments. | ⚠️ Degradation risk |
| Red: Below 95% completeness, or any uniform confidence assignments indicating undifferentiated inference. | ❌ Active failure |

**Reporting:** Ops per cycle; Gov weekly

**Escalation Trigger:** → CGF-2 Failure Response (Operating Model)

---

### C-GHI-3 — Validation Gate Pass Rate

**Measurement:** Ratio of outputs passing signal validation on first submission versus requiring reprocessing or quarantine.

**Frequency:** Continuous — per output

| Threshold | Status |
| :---- | :---- |
| Green: Pass rate ≥ 95%. Failed validations alerted and resolved within threshold. Zero suppressed failures. | ✅ Operational |
| Amber: Pass rate 90–94%. Resolution time approaching threshold. No suppressed failures. | ⚠️ Degradation risk |
| Red: Pass rate below 90%, or any suppressed validation failure, or outputs reaching Execution Layer without validation status. | ❌ Active failure |

**Reporting:** All tiers — sustained Amber warrants trend disclosure

**Escalation Trigger:** → CGF-3 Failure Response (Operating Model)

---

### C-GHI-4 — Boundary Overreach Rate

**Measurement:** Number of overreach events detected per output cycle — outputs flagged for crossing declared knowledge boundaries.

**Frequency:** Per output cycle

| Threshold | Status |
| :---- | :---- |
| Green: Zero undetected overreach events. All detected events flagged and quarantined before downstream release. | ✅ Operational |
| Amber: One or more overreach events detected and contained within current cycle. No events reaching Authority Layer. | ⚠️ Degradation risk |
| Red: Any overreach event reaching Authority Layer without boundary flag, or domains active without declared boundaries. | ❌ Active failure |

**Reporting:** All tiers

**Escalation Trigger:** → CGF-4 Failure Response (Operating Model)

---

### C-GHI-5 — Calibration Distortion Detection

**Measurement:** Number of calibration events where output confidence language or granularity was altered from the validated inference record.

**Frequency:** Per calibration event

| Threshold | Status |
| :---- | :---- |
| Green: Zero distortion events. Calibration and inference logs consistent across all outputs. | ✅ Operational |
| Amber: One or more distortion events detected, corrected, and logged within current cycle. | ⚠️ Degradation risk |
| Red: Any distortion event not detected by automated controls — identified only through manual review or downstream complaint. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly

**Escalation Trigger:** → CGF-2 Failure Response (Operating Model)

---

### C-GHI-6 — Cognitive Layer Worst-Node Score

**Measurement:** Lowest GHI health status across C-GHI-1 through C-GHI-5.

**Frequency:** Weekly (Gov); Quarterly (Inst)

| Threshold | Status |
| :---- | :---- |
| Green: All five Cognitive GHIs at Green. | ✅ Operational |
| Amber: Any Cognitive GHI at Amber; none at Red. | ⚠️ Degradation risk |
| Red: Any Cognitive GHI at Red. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly

---

## SECTION 5: EXECUTION LAYER GHIs (7 INDICATORS)

### E-GHI-1 — Initiation Clearance Coverage

**Measurement:** % of workflows activated with confirmed EGF-1 initiation clearance records.

**Frequency:** Per workflow activation

| Threshold | Status |
| :---- | :---- |
| Green: 100% of activations have clearance records. No pipelines running without clearance. | ✅ Operational |
| Amber: One or more activations without clearance, identified within one cycle, no binding outputs produced. | ⚠️ Degradation risk |
| Red: Any pipeline producing binding outputs without initiation clearance. | ❌ Active failure |

**Reporting:** Ops per activation; Gov weekly

**Escalation Trigger:** → EGF-1 Failure Response (Operating Model)

---

### E-GHI-2 — Orchestration Ownership Coverage

**Measurement:** % of active pipelines with declared orchestration owners at any point in time.

**Frequency:** Continuous

| Threshold | Status |
| :---- | :---- |
| Green: 100% of active pipelines have declared orchestration owners. Zero ownership gaps. | ✅ Operational |
| Amber: Ownership gap detected and remediated within one cycle. No deadlocks triggered by gap. | ⚠️ Degradation risk |
| Red: Any deadlock event attributable to absent orchestration ownership, or ownership gap persisting beyond one cycle. | ❌ Active failure |

**Reporting:** Ops continuous; Gov weekly

**Escalation Trigger:** → EGF-2 Failure Response (Operating Model)

---

### E-GHI-3 — Concurrency Authorization Rate

**Measurement:** % of parallel execution sets activated with confirmed EGF-3 concurrency authorization records.

**Frequency:** Per parallel activation

| Threshold | Status |
| :---- | :---- |
| Green: 100% authorization rate. Zero unauthorized parallel sets. | ✅ Operational |
| Amber: One unauthorized parallel set detected and halted before producing outputs. No collision events. | ⚠️ Degradation risk |
| Red: Any concurrency collision event, or unauthorized parallel set producing outputs before detection. | ❌ Active failure |

**Reporting:** Ops per activation; Gov weekly

**Escalation Trigger:** → EGF-3 Failure Response (Operating Model)

---

### E-GHI-4 — Exception Classification Rate

**Measurement:** % of detected exceptions classified within declared threshold from detection.

**Frequency:** Per exception event

| Threshold | Status |
| :---- | :---- |
| Green: 100% of exceptions classified within threshold. Zero propagated to Authority Layer without classification. | ✅ Operational |
| Amber: Classification threshold exceeded for one or more exceptions. All contained at Execution Layer. | ⚠️ Degradation risk |
| Red: Any exception propagating to Authority Layer without classification record. | ❌ Active failure |

**Reporting:** All tiers — Red is a cross-layer boundary failure requiring disclosure

**Escalation Trigger:** → EGF-4 Failure Response (Operating Model)

---

### E-GHI-5 — Monitoring Coverage Completeness

**Measurement:** % of active pipeline types with confirmed monitoring coverage at any point in time.

**Frequency:** Weekly audit; continuous for new pipeline type introductions

| Threshold | Status |
| :---- | :---- |
| Green: 100% of pipeline types monitored. Zero coverage gaps. | ✅ Operational |
| Amber: Coverage gap identified within audit cycle. No unmonitored pipelines producing binding outputs. | ⚠️ Degradation risk |
| Red: Any unmonitored pipeline producing binding outputs, or audit cycle missed. | ❌ Active failure |

**Reporting:** Ops weekly; Gov weekly

**Escalation Trigger:** → EGF-5 Failure Response (Operating Model)

---

### E-GHI-6 — Pipeline Fragmentation Index

**Measurement:** Number of state reconciliation failures per operating period — events where parallel or sequential outputs could not be reconciled without human intervention.

**Frequency:** Daily

| Threshold | Status |
| :---- | :---- |
| Green: Zero reconciliation failures. All state reconciliations automated. | ✅ Operational |
| Amber: One or more failures resolved within current period without Authority Layer impact. | ⚠️ Degradation risk |
| Red: Any reconciliation failure requiring Authority Layer escalation, or recurring failures in same pipeline type across two consecutive periods. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly — recurring Amber warrants trend disclosure

**Escalation Trigger:** → EGF-2 Failure Response (Operating Model)

---

### E-GHI-7 — Execution Layer Worst-Node Score

**Measurement:** Lowest status across E-GHI-1 through E-GHI-6.

**Frequency:** Weekly; Quarterly

| Threshold | Status |
| :---- | :---- |
| Green: All six Execution GHIs at Green. | ✅ Operational |
| Amber: Any Execution GHI at Amber; none at Red. | ⚠️ Degradation risk |
| Red: Any Execution GHI at Red. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly

---

## SECTION 6: AUTHORITY LAYER GHIs (8 INDICATORS)

### A-GHI-1 — Trigger Rights Map Currency

**Measurement:** Days since last trigger rights map review against current production action classes.

**Frequency:** Daily

| Threshold | Status |
| :---- | :---- |
| Green: Map reviewed within declared governance cycle. Zero overdue reviews. | ✅ Operational |
| Amber: Review approaching cycle limit. No new action classes introduced since last review. | ⚠️ Degradation risk |
| Red: Map review overdue beyond one cycle, or new action classes introduced since last review without trigger rights declaration. | ❌ Active failure |

**Reporting:** Ops daily; Gov weekly

**Escalation Trigger:** → AGF-1 Failure Response (Operating Model)

---

### A-GHI-2 — Binding Declaration Completeness

**Measurement:** % of workflows where all output classes received AGF-2 binding threshold declarations before first output was produced.

**Frequency:** Per workflow initiation

| Threshold | Status |
| :---- | :---- |
| Green: 100% of workflows have pre-production binding declarations for all output classes. | ✅ Operational |
| Amber: One or more workflows where declarations produced after first output but before external boundary crossing. | ⚠️ Degradation risk |
| Red: Any workflow where binding declarations produced after external boundary crossing. | ❌ Active failure |

**Reporting:** Ops per workflow; Gov weekly; Inst quarterly

**Escalation Trigger:** → AGF-2 Failure Response (Operating Model)

---

### A-GHI-3 — Override Mechanism Test Frequency

**Measurement:** Days since override mechanisms were last tested by a non-technical principal.

**Frequency:** Daily tracking against declared test cycle

| Threshold | Status |
| :---- | :---- |
| Green: All override mechanisms tested within declared cycle by non-technical principal. | ✅ Operational |
| Amber: Test cycle approaching limit. No override events since last test. | ⚠️ Degradation risk |
| Red: Test cycle overdue, or override mechanism invocation failed during test, or override event occurred with mechanism unavailable. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly — Red requires explicit disclosure as authority binding failure

**Escalation Trigger:** → AGF-3 Failure Response (Operating Model)

---

### A-GHI-4 — Escalation Resolution Rate

**Measurement:** % of escalation events resolved within declared response time threshold.

**Frequency:** Per escalation event

| Threshold | Status |
| :---- | :---- |
| Green: 100% resolved within threshold. Default actions triggered correctly for all unresolved escalations. | ✅ Operational |
| Amber: One or more escalations resolved beyond threshold but within double threshold. Default actions triggered correctly. | ⚠️ Degradation risk |
| Red: Any escalation where default action failed to trigger on threshold breach, or Escalation Principal unavailable without declared backup. | ❌ Active failure |

**Reporting:** Gov per event and weekly; Inst quarterly

**Escalation Trigger:** → AGF-4 Failure Response (Operating Model)

---

### A-GHI-5 — Delegation Creep Detection Rate

**Measurement:** Number of delegation boundary violation alerts detected per governance cycle.

**Frequency:** Continuous detection; weekly reporting

| Threshold | Status |
| :---- | :---- |
| Green: Zero unresolved boundary violations. Alert rate consistent with delegation activity volume. | ✅ Operational |
| Amber: One or more violations detected and remediated within current cycle. No binding outputs under exceeded delegation. | ⚠️ Degradation risk |
| Red: Any binding output produced under delegation exceeding declared boundary, or detection rate anomalously zero in active delegation environment. | ❌ Active failure |

**Reporting:** All tiers

**Escalation Trigger:** → AGF-5 Failure Response (Operating Model)

---

### A-GHI-6 — Authority State Handoff Latency

**Measurement:** Time elapsed between an authority state change event and the corresponding COGF-1 baseline update in the Continuity Layer.

**Frequency:** Per authority state change event

| Threshold | Status |
| :---- | :---- |
| Green: All handoffs reflected in Co-N1 baseline within declared latency threshold (maximum: one operating cycle). | ✅ Operational |
| Amber: Handoff latency approaching threshold. No workflows initiated against stale authority state. | ⚠️ Degradation risk |
| Red: Any workflow initiated against an authority state baseline that does not reflect a known authority state change. | ❌ Active failure |

**Reporting:** Ops per event; Gov weekly

**Escalation Trigger:** → AGF-6 Failure Response (Operating Model)

---

### A-GHI-7 — External Fitness Declaration Rate

**Measurement:** % of outputs crossing external boundaries with complete A-N2 fitness declarations across all five required fields.

**Frequency:** Per external boundary crossing

| Threshold | Status |
| :---- | :---- |
| Green: 100% of external boundary outputs have complete fitness declarations across all five fields. | ✅ Operational |
| Amber: One or more outputs with incomplete declarations — fields present but partially populated. | ⚠️ Degradation risk |
| Red: Any output crossing external boundary without complete fitness declaration, or declared binding category not matching actual consequence class. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly — mandatory disclosure instrument

**Escalation Trigger:** → AGF-2 Failure Response (Operating Model)

---

### A-GHI-8 — Authority Layer Worst-Node Score

**Measurement:** Lowest status across A-GHI-1 through A-GHI-7 and KN-GHI-1 and KN-GHI-2.

**Frequency:** Weekly; Quarterly

| Threshold | Status |
| :---- | :---- |
| Green: All nine Authority indicators at Green. | ✅ Operational |
| Amber: Any Authority indicator at Amber; none at Red. | ⚠️ Degradation risk |
| Red: Any Authority indicator at Red. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly — Authority Red disclosed prominently regardless of other layer scores

---

## SECTION 7: CONTINUITY LAYER GHIs (7 INDICATORS)

### CO-GHI-1 — Baseline Declaration Rate

**Measurement:** % of workflows initiated with COGF-1 baseline records declared before first execution step.

**Frequency:** Per workflow initiation

| Threshold | Status |
| :---- | :---- |
| Green: 100% pre-execution baseline declarations. No in-flight workflows without baselines. | ✅ Operational |
| Amber: Baseline declared after first execution step but before binding output. Identified and remediated within current cycle. | ⚠️ Degradation risk |
| Red: Any binding output produced without a prior baseline declaration. | ❌ Active failure |

**Reporting:** Ops per initiation; Gov weekly

**Escalation Trigger:** → COGF-1 Failure Response (Operating Model)

---

### CO-GHI-2 — Cumulative Drift Score

**Measurement:** Cumulative deviation score per active workflow — sum of individual drift events since last validated baseline reset. Measures silent drift accumulation.

**Frequency:** Continuous per workflow

| Threshold | Status |
| :---- | :---- |
| Green: All active workflows below declared cumulative deviation threshold. No silent drift patterns detected. | ✅ Operational |
| Amber: One or more workflows approaching cumulative threshold. Silent drift pattern detected and under investigation. | ⚠️ Degradation risk |
| Red: Any workflow exceeding cumulative deviation threshold, or silent drift confirmed — cumulative threshold reached without individual event triggers having fired. | ❌ Active failure |

**Reporting:** All tiers — cumulative drift above threshold requires disclosure

**Escalation Trigger:** → COGF-2 Failure Response (Operating Model)

---

### CO-GHI-3 — Approval Validity Coverage

**Measurement:** % of active workflows currently operating under valid, non-expired approvals.

**Frequency:** Continuous

| Threshold | Status |
| :---- | :---- |
| Green: 100% of active workflows under valid approvals. All proximity alerts triggering reauthorization requests before expiry. | ✅ Operational |
| Amber: One or more approvals in proximity alert window. Reauthorization requested and pending. No lapsed approvals. | ⚠️ Degradation risk |
| Red: Any workflow continuing execution under a lapsed approval, or proximity alert system not triggering. | ❌ Active failure |

**Reporting:** All tiers

**Escalation Trigger:** → COGF-3 Failure Response (Operating Model)

---

### CO-GHI-4 — Handoff Integrity Rate

**Measurement:** % of handoff events completing with full state transfer records and receiving party confirmation.

**Frequency:** Per handoff event

| Threshold | Status |
| :---- | :---- |
| Green: 100% of handoffs with complete records and confirmations. Zero truncated handoffs accepted. | ✅ Operational |
| Amber: One truncated handoff detected, rejected, and retransferred within current cycle. No decisions made under truncated state. | ⚠️ Degradation risk |
| Red: Any decision made under a truncated handoff state, or truncated handoff accepted without rejection and retransfer. | ❌ Active failure |

**Reporting:** All tiers — Red triggers ACGF-2 attribution review disclosure

**Escalation Trigger:** → COGF-4 Failure Response (Operating Model)

---

### CO-GHI-5 — False Resumption Detection Rate

**Measurement:** Number of false resumption events detected per period — workflows that attempted resumption under incomplete context.

**Frequency:** Per resumption event

| Threshold | Status |
| :---- | :---- |
| Green: Zero false resumptions proceeding beyond detection point. All resumptions with confirmed restoration clearance records. | ✅ Operational |
| Amber: One false resumption detected and halted before producing outputs. Restoration clearance process identified as insufficient. | ⚠️ Degradation risk |
| Red: Any false resumption producing outputs, or false resumption detected only through downstream error rather than COGF-5 controls. | ❌ Active failure |

**Reporting:** Gov per event and weekly; Inst quarterly

**Escalation Trigger:** → COGF-5 Failure Response (Operating Model)

---

### CO-GHI-6 — State Continuity Index

**Measurement:** Composite indicator combining CO-GHI-1 through CO-GHI-5 into single continuity health index using worst-performing contributor.

**Frequency:** Daily

| Threshold | Status |
| :---- | :---- |
| Green: All five contributing indicators at Green. | ✅ Operational |
| Amber: Any contributing indicator at Amber; none at Red. | ⚠️ Degradation risk |
| Red: Any contributing indicator at Red. | ❌ Active failure |

**Reporting:** Gov daily; Inst quarterly as layer health indicator

---

### CO-GHI-7 — Continuity Layer Worst-Node Score

**Measurement:** Lowest status across CO-GHI-1 through CO-GHI-6 and KN-GHI-3 and KN-GHI-4.

**Frequency:** Weekly; Quarterly

| Threshold | Status |
| :---- | :---- |
| Green: All eight Continuity indicators at Green. | ✅ Operational |
| Amber: Any Continuity indicator at Amber; none at Red. | ⚠️ Degradation risk |
| Red: Any Continuity indicator at Red. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly

---

## SECTION 8: ACCOUNTABILITY LAYER GHIs (6 INDICATORS)

### AC-GHI-1 — Lineage Completeness Rate

**Measurement:** % of decisions in the current period with complete lineage records — all five components present: inputs, authority, executor identity, state context, timestamp.

**Frequency:** Continuous per decision

| Threshold | Status |
| :---- | :---- |
| Green: 100% of decisions with complete five-component lineage records. Zero gap alerts unresolved. | ✅ Operational |
| Amber: One or more decisions with incomplete records identified and under reconstruction within current cycle. | ⚠️ Degradation risk |
| Red: Any gap alert suppressed, or binding decision with incomplete lineage not identified within 24 hours. | ❌ Active failure |

**Reporting:** All tiers — Red is a material disclosure

**Escalation Trigger:** → ACGF-1 Failure Response (Operating Model)

---

### AC-GHI-2 — Attribution Coverage Rate

**Measurement:** % of decisions with complete responsibility attribution — all three accountability dimensions (authorization, execution, oversight) declared and unambiguous.

**Frequency:** Per decision completion

| Threshold | Status |
| :---- | :---- |
| Green: 100% with complete three-dimension attribution. No ambiguous multi-actor assignments. | ✅ Operational |
| Amber: One or more decisions with incomplete attribution under reconstruction. No external disclosures affected. | ⚠️ Degradation risk |
| Red: Any external disclosure produced without complete attribution, or attribution ambiguity on binding decision unresolved beyond one governance cycle. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly — mandatory disclosure component

**Escalation Trigger:** → ACGF-2 Failure Response (Operating Model)

---

### AC-GHI-3 — Validation Cycle Adherence

**Measurement:** % of declared validation cycles completed on schedule in the current period.

**Frequency:** Per declared validation cycle

| Threshold | Status |
| :---- | :---- |
| Green: 100% of declared cycles completed on schedule. Validation criteria pre-declared for all active decision classes. | ✅ Operational |
| Amber: One cycle delayed but completed within same governance period. All criteria pre-declared. | ⚠️ Degradation risk |
| Red: Any validation cycle deferred beyond current governance period, or criteria declared after outcome is known for any decision class. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly

**Escalation Trigger:** → ACGF-3 Failure Response (Operating Model)

---

### AC-GHI-4 — Validation Debt Level

**Measurement:** Total number of decision classes with declared validation debt — irrecoverable deferrals where the measurement window has closed.

**Frequency:** Per validation cycle completion

| Threshold | Status |
| :---- | :---- |
| Green: Zero validation debt entries. All decision classes validated within declared windows. | ✅ Operational |
| Amber: One or more debt entries, each with formal acknowledgment and corrective declaration for future cycles. | ⚠️ Degradation risk |
| Red: Any validation debt entry without formal acknowledgment, or validation debt growing across consecutive periods without remediation. | ❌ Active failure |

**Reporting:** Gov monthly; Inst quarterly — standing disclosure item regardless of current value

**Escalation Trigger:** → ACGF-3 Failure Response (Operating Model)

---

### AC-GHI-5 — Architecture Update Traceability Rate

**Measurement:** % of architecture updates in the current period with confirmed traceability to originating ACGF-3 validation events.

**Frequency:** Per architecture update

| Threshold | Status |
| :---- | :---- |
| Green: 100% of updates traceable to originating validation events. All holdco-level updates authorized before implementation. | ✅ Operational |
| Amber: One or more updates with incomplete traceability records under remediation. | ⚠️ Degradation risk |
| Red: Any architecture update implemented without traceability to a validation event, or holdco-level update implemented without authorization. | ❌ Active failure |

**Reporting:** Gov monthly; Inst quarterly — untraceable updates are a material governance disclosure

**Escalation Trigger:** → ACGF-4 Failure Response (Operating Model)

---

### AC-GHI-6 — Accountability Layer Worst-Node Score

**Measurement:** Lowest status across AC-GHI-1 through AC-GHI-5 and KN-GHI-5.

**Frequency:** Weekly; Quarterly

| Threshold | Status |
| :---- | :---- |
| Green: All six Accountability indicators at Green. | ✅ Operational |
| Amber: Any Accountability indicator at Amber; none at Red. | ⚠️ Degradation risk |
| Red: Any Accountability indicator at Red. | ❌ Active failure |

**Reporting:** Gov weekly; Inst quarterly

---

## SECTION 9: GHI SUMMARY TABLE

| ID | Name | Type | Frequency | Reporting Tier |
| :---- | :---- | :---- | :---- | :---- |
| KN-GHI-1 | Trigger Rights Coverage | Keystone Node | Weekly | All tiers |
| KN-GHI-2 | Binding Threshold Coverage | Keystone Node | Per workflow | All tiers |
| KN-GHI-3 | State Baseline Completeness | Keystone Node | Per initiation | All tiers |
| KN-GHI-4 | Drift Detection Enrollment | Keystone Node | Continuous | All tiers |
| KN-GHI-5 | Learning Loop Integrity | Keystone Node | Per cycle | All tiers |
| C-GHI-1 | Source Credential Currency | Function | Daily | Ops \+ Gov |
| C-GHI-2 | Inference Chain Completeness | Function | Per cycle | Ops \+ Gov |
| C-GHI-3 | Validation Gate Pass Rate | Function | Continuous | All tiers |
| C-GHI-4 | Boundary Overreach Rate | Function | Per cycle | All tiers |
| C-GHI-5 | Calibration Distortion Detection | Function | Per event | Gov \+ Inst |
| C-GHI-6 | Cognitive Worst-Node Score | Aggregation | Weekly | Gov \+ Inst |
| E-GHI-1 | Initiation Clearance Coverage | Function | Per activation | Ops \+ Gov |
| E-GHI-2 | Orchestration Ownership Coverage | Function | Continuous | Ops \+ Gov |
| E-GHI-3 | Concurrency Authorization Rate | Function | Per activation | Ops \+ Gov |
| E-GHI-4 | Exception Classification Rate | Function | Per event | All tiers |
| E-GHI-5 | Monitoring Coverage Completeness | Function | Weekly | Ops \+ Gov |
| E-GHI-6 | Pipeline Fragmentation Index | Function | Daily | Gov \+ Inst |
| E-GHI-7 | Execution Worst-Node Score | Aggregation | Weekly | Gov \+ Inst |
| A-GHI-1 | Trigger Rights Map Currency | Function | Daily | Ops \+ Gov |
| A-GHI-2 | Binding Declaration Completeness | Function | Per workflow | Ops \+ Gov |
| A-GHI-3 | Override Mechanism Test Frequency | Function | Daily | Gov \+ Inst |
| A-GHI-4 | Escalation Resolution Rate | Function | Per event | Gov \+ Inst |
| A-GHI-5 | Delegation Creep Detection Rate | Function | Continuous | All tiers |
| A-GHI-6 | Authority State Handoff Latency | Function | Per event | Ops \+ Gov |
| A-GHI-7 | External Fitness Declaration Rate | Function | Per crossing | All tiers |
| A-GHI-8 | Authority Worst-Node Score | Aggregation | Weekly | Gov \+ Inst |
| CO-GHI-1 | Baseline Declaration Rate | Function | Per initiation | Ops \+ Gov |
| CO-GHI-2 | Cumulative Drift Score | Function | Continuous | All tiers |
| CO-GHI-3 | Approval Validity Coverage | Function | Continuous | All tiers |
| CO-GHI-4 | Handoff Integrity Rate | Function | Per event | All tiers |
| CO-GHI-5 | False Resumption Detection Rate | Function | Per event | Gov \+ Inst |
| CO-GHI-6 | State Continuity Index | Aggregation | Daily | Gov \+ Inst |
| CO-GHI-7 | Continuity Worst-Node Score | Aggregation | Weekly | Gov \+ Inst |
| AC-GHI-1 | Lineage Completeness Rate | Function | Continuous | All tiers |
| AC-GHI-2 | Attribution Coverage Rate | Function | Per decision | Gov \+ Inst |
| AC-GHI-3 | Validation Cycle Adherence | Function | Per cycle | Gov \+ Inst |
| AC-GHI-4 | Validation Debt Level | Function | Per cycle | Gov \+ Inst |
| AC-GHI-5 | Architecture Update Traceability | Function | Per update | Gov \+ Inst |
| AC-GHI-6 | Accountability Worst-Node Score | Aggregation | Weekly | Gov \+ Inst |

---

## SECTION 10: INSTITUTIONAL DECLARATION — ATTESTATION STANDARD

The quarterly Institutional Architecture Health Declaration is signed by the Escalation Principal under the following attestation:

> *"I attest that this Architecture Health Declaration accurately reflects the governance health of \[Organization\]'s AICA-5 implementation for the period \[Quarter\]. All material disclosures known to me are included. I understand that this declaration is an informational binding output under AICA-5 Structural Principle 2 and that false attestation constitutes an Ac-N2 responsibility attribution violation triggering A-N4 escalation to holdco under 19-IPAS."*

The false attestation clause is not a deterrent formality. It is the accountability instrument that makes the Institutional Declaration a governed output rather than a reputational statement.

---

## SECTION 11: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| AICA-5 | Defines the nodes — Measurement Framework measures them |
| AICA-5 Operating Model | Escalation Triggers reference Failure Response matrix by function ID |
| AICA-5 Implementation Pathway | Measurement Framework tracks progress through phases |
| AITOS | Measurement System provides continuous observability |
| HAN / HOF | Escalation Principal signs Institutional Declaration |
| ERDP | Institutional tier reporting feeds into ERDP |
| ADTEP | Red indicators trigger ADTEP enforcement |

---

## SECTION 12: CFL-V VALIDATION RULES

**Rule 1 — No Averaging:** Operational and Governance tiers report worst-node. No averaging.

**Rule 2 — Keystone Node Visibility:** Keystone Node GHIs must be displayed separately at top of all reports.

**Rule 3 — Red Disclosure:** All Red indicators must be disclosed at all reporting tiers.

**Rule 4 — Institutional Attestation:** Quarterly Institutional Declaration signed by Escalation Principal. False attestation is Ac-N2 violation.

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| AICA-5 Measurement Framework v1.0 | Initial 39 GHIs, 3 reporting tiers |
| AICA-5 Measurement Framework v2.0 | Complete rebuild — reconciliation with AICA-5, Operating Model, and Implementation Pathway; expanded GHI definitions; Institutional Declaration attestation standard; CFL-V validation rules |

---

## The One-Sentence Summary

> *"The AICA-5 Measurement Framework v2.0 defines 39 Governance Health Indicators across 5 layers and 3 reporting tiers — Operational (raw GHI status), Governance (worst-node per layer \+ Red indicators), and Institutional (weighted average \+ Red disclosures) — with Keystone Node GHIs displayed separately, no averaging in Operational/Governance tiers, and the Institutional Declaration signed by the Escalation Principal under penalty of Ac-N2 violation."*
