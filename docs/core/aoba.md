# AOBA v2.0 — AI Output Bias Audit

**Status:** Built — v2.0 (Reconciliation with ADTEP, IMP, AICA-5, AWOF, Trigger System, RGI-8, and ICC-8)  
**Type:** Technical Enforcement Instrument  
**Parent Stack:** ADTEP (Agent Deployment & Technical Enforcement Protocol)  
**Version:** 2.0 — Supersedes AOBA v1.0 (Scoped)

---

## PREAMBLE

The AI Output Bias Audit (AOBA) audits AI agent output for disparate impact and systematic unfairness across affected populations. It answers: *Is the thing being supervised behaving fairly?*

AOBA evaluates model/agent behavior independent of whether the human overseeing that agent is behaving fairly. It detects bias in AI outputs—not in human oversight. It is the operational implementation of fairness auditing within the AIGIS stack, providing severity-tiered responses (Flag, Review, Halt) and IMP-grounded comparators.

**The core insight:** A perfectly fair human overseer can still supervise a biased AI system. AOBA detects the bias in the system, not the overseer. It is the complement to ABA (Authority Bias Audit), which audits the human overseer. Together, they provide complete bias coverage across the AI-human governance chain.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

AOBA ensures that:

1. **AI output fairness is audited** — Disparate impact and systematic unfairness are detected  
2. **Bias is detected before harm** — Severity-tiered responses prevent biased outputs from causing harm  
3. **Comparator data is grounded in IMP** — Bias detection uses institutional memory, not generic fairness metrics  
4. **Escalation is clear** — Bias findings route through defined severity tiers to HAN  
5. **Pattern detection is continuous** — Bias patterns are detected over time, not just per-output

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| AI agent output bias | Human authority conduct (ABA's domain) |
| Disparate impact detection | Shadow-bridge literacy translation |
| Systematic unfairness detection | Altitude 3 adjacent products (IVA/IVC/IVI, SADIE-5, VGDF) |
| Severity-tiered responses (Flag/Review/Halt) | Business strategy or objectives |
| IMP-grounded comparator data | Performance optimization |

### Applicability

| Agent Type | AOBA Applicability | Notes |
| :---- | :---- | :---- |
| **All AWOF-classified agents** | ✅ Yes | All agents subject to bias audit |
| **F-RE (Research)** | ✅ Yes | Research outputs may contain bias |
| **F-DR (Drafting)** | ✅ Yes | Drafting outputs may contain bias |
| **F-EX (Execution)** | ✅ Yes | Execution decisions may contain bias |
| **F-OV (Oversight)** | ✅ Yes | Oversight outputs may contain bias |
| **T-GN (Generalist)** | ✅ Yes | Standard audit |
| **T-SP (Specialist)** | ✅ Yes | Enhanced audit for specialist outputs |
| **T-OR (Orchestrator)** | ✅ Yes | Enhanced audit for coalition outputs |

---

## SECTION 2: AOBA DISTINGUISHED FROM ABA

| Aspect | AOBA | ABA |
| :---- | :---- | :---- |
| **Audits** | AI agent output | Human Authority Node |
| **Parent stack** | ADTEP (Altitude 1 — Formal Stack, Layer 3 Technical Enforcement) | HOF (Human Operating Framework) → HIS-12 |
| **Detects** | Disparate impact / fairness failure in model behavior | Uneven application of oversight |
| **Failure mode caught** | AI system produces biased outcomes | Overseer plays favorites |
| **Relationship** | Complements ABA; neither substitutes for the other | Complements AOBA; neither substitutes for the other |

**Key Principle:** A finding in one does not imply a finding in the other. A perfectly fair human overseer can still supervise a biased AI system, and vice versa. Both are needed.

---

## SECTION 3: AOBA COMPONENTS

| Component | Function | Status |
| :---- | :---- | :---- |
| **Baseline Comparator** | Comparator population/outcome data drawn from IMP's canonical object schema | ✅ Built (v2.0) |
| **Rotation Mechanism** | Baseline and test set re-baselined on fixed interval | ✅ Built (v2.0) |
| **Severity Tiering** | Flag (logged), Review (HAN), Halt (AWOF suspension) | ✅ Built (v2.0) |
| **Detection Engine** | Bias detection across protected groups | ✅ Built (v2.0) |
| **Escalation Path** | Flag → severity tiering → HAN adjudication | ✅ Built (v2.0) |
| **Pattern Detection** | Cumulative bias pattern detection over time | ✅ Built (v2.0) |

---

## SECTION 4: AOBA FIELDS — COMPLETE SET

| \# | Field | Required | Description |
| :---- | :---- | :---- | :---- |
| 1 | **AOBA-ID** | ✅ Yes | Unique identifier for the AOBA audit |
| 2 | **AGENT-ID** | ✅ Yes | Agent ID being audited |
| 3 | **RS-VERSION** | ✅ Yes | Role Specification version at time of audit |
| 4 | **SESSION-ID** | ✅ Yes | Session identifier |
| 5 | **TIMESTAMP** | ✅ Yes | Audit timestamp |
| 6 | **OUTPUT-REFERENCE** | ✅ Yes | Reference to the output being audited (GAO, DRO, etc.) |
| 7 | **PROTECTED-GROUPS** | ✅ Yes | Protected groups assessed (gender, race, age, disability, religion, etc.) |
| 8 | **COMPARATOR-BASELINE** | ✅ Yes | IMP-grounded comparator population/outcome data reference |
| 9 | **BASELINE-VERSION** | ✅ Yes | Baseline version and date |
| 10 | **DETECTION-METHOD** | ✅ Yes | Detection method used (statistical, pattern-based, etc.) |
| 11 | **FINDINGS** | ✅ Yes | List of bias findings with descriptions |
| 12 | **SEVERITY-TIER** | ✅ Yes | Flag / Review / Halt |
| 13 | **RECOMMENDATION** | ✅ Yes | Recommended action based on severity tier |
| 14 | **HAN-ESCALATION-STATUS** | Conditional | Pending / Acknowledged / Resolved |
| 15 | **HAN-ACKNOWLEDGMENT** | Conditional | HAN acknowledgment timestamp and status |
| 16 | **RESOLUTION-TIMESTAMP** | Conditional | Resolution timestamp |
| 17 | **RESOLUTION-NOTES** | Conditional | Resolution notes |
| 18 | **PATTERN-REFERENCE** | Conditional | Reference to cumulative pattern detection |
| 19 | **AOBA-STATUS** | ✅ Yes | Open / Review / Halt / Resolved / Closed |

---

## SECTION 4.1: FIELD DEFINITIONS

| Field | Description | Example |
| :---- | :---- | :---- |
| **AOBA-ID** | Unique identifier. Format: `AOBA-[ECO-ID]-[SEQ]` | `AOBA-ECO-2026-0a26cb-001` |
| **AGENT-ID** | Agent ID being audited | `F-DR-E-CN-T-SP-001` |
| **RS-VERSION** | Role Specification version at time of audit | `v1.0` |
| **SESSION-ID** | Session identifier | `SESS-2026-08-31-001` |
| **TIMESTAMP** | Audit timestamp | `2026-08-31T17:00:00Z` |
| **OUTPUT-REFERENCE** | Reference to output being audited | `GAO-ECO-2026-0a26cb-66d465` |
| **PROTECTED-GROUPS** | Protected groups assessed | `["gender", "race", "age", "disability", "religion"]` |
| **COMPARATOR-BASELINE** | IMP-grounded comparator reference | `IMP-BASELINE-2026-08-31` |
| **BASELINE-VERSION** | Baseline version and date | `v2.0 — 2026-08-31` |
| **DETECTION-METHOD** | Detection method used | `Statistical disparity analysis; Pattern-based detection` |
| **FINDINGS** | List of bias findings | `[{"category": "gender", "description": "Potential gender bias: term 'he' appears 3x more than 'she'", "severity": "moderate"}]` |
| **SEVERITY-TIER** | Severity tier | `Flag` / `Review` / `Halt` |
| **RECOMMENDATION** | Recommended action | `Log for pattern review, no action taken` / `Route to HAN for adjudication` / `Agent suspended pending HAN review` |
| **HAN-ESCALATION-STATUS** | Escalation status | `Pending` / `Acknowledged` / `Resolved` |
| **HAN-ACKNOWLEDGMENT** | HAN acknowledgment | `{"HAN": "Terrylan_Manalansan", "timestamp": "2026-08-31T17:15:00Z", "status": "Acknowledged"}` |
| **RESOLUTION-TIMESTAMP** | Resolution timestamp | `2026-09-01T10:00:00Z` |
| **RESOLUTION-NOTES** | Resolution notes | `Reviewed and resolved. Agent output adjusted.` |
| **PATTERN-REFERENCE** | Cumulative pattern reference | `PATTERN-AOBA-2026-08-31` |
| **AOBA-STATUS** | Audit status | `Open` / `Review` / `Halt` / `Resolved` / `Closed` |

---

## SECTION 5: SEVERITY TIERS

### Tier Definitions

| Tier | Name | Definition | Response |
| :---- | :---- | :---- | :---- |
| **Flag** | Minor bias indicator | Potential bias detected; low severity; no immediate action required | Logged to IMP for pattern review, no action taken |
| **Review** | Moderate bias indicator | Bias detected; moderate severity; HAN review required | Routed to HAN queue for adjudication |
| **Halt** | Severe bias indicator | Severe bias detected; high severity; agent suspension required | Triggers AWOF agent suspension; HAN review required |

### Tier Determination Criteria

| Criterion | Flag | Review | Halt |
| :---- | :---- | :---- | :---- |
| **Number of findings** | 1-2 | 3-5 | 6+ |
| **Severity of findings** | Low | Moderate | High |
| **Protected groups affected** | 1 | 2-3 | 4+ |
| **Cumulative pattern** | No | Emerging | Confirmed |
| **Historical pattern** | No | Single instance | Recurring |

### Severity Tier Response Matrix

| Tier | IMP Logging | HAN Notification | Agent Action |
| :---- | :---- | :---- | :---- |
| **Flag** | OEO created | No | Continue |
| **Review** | OEO \+ DRO created | Within 24 hours | Continue pending HAN review |
| **Halt** | OEO \+ DRO \+ XOO created | Within 1 hour | Suspended |

---

## SECTION 6: DETECTION MECHANISM

### 6.1 Baseline Establishment

| Aspect | Description |
| :---- | :---- |
| **Data Source** | IMP's canonical object schema — ECO, DRO, GAO, CRO, OEO, XOO |
| **Comparator Population** | Historical outcome data from IMP |
| **Protected Groups** | Gender, race, age, disability, religion, and configurable custom groups |
| **Baseline Refresh** | Re-baselined on fixed interval (default: quarterly) |
| **Baseline Versioning** | Each baseline is versioned and stored in IMP |

### 6.2 Detection Methods

| Method | Description | Used For |
| :---- | :---- | :---- |
| **Statistical Disparity** | Statistical analysis of outcome distribution across protected groups | Quantitative bias detection |
| **Pattern-Based** | Pattern matching for bias indicators (terms, phrases, associations) | Qualitative bias detection |
| **Term Frequency** | Frequency analysis of biased terms across outputs | Text-based bias detection |
| **Outcome Disparity** | Analysis of disparate outcomes across protected groups | Decision-based bias detection |
| **Cumulative Pattern** | Cross-output pattern detection over time | Systemic bias detection |

### 6.3 Protected Groups

| Group | Categories | Detection Focus |
| :---- | :---- | :---- |
| **Gender** | Male, Female, Non-binary | Pronoun usage, gendered terms, disparate outcomes |
| **Race** | Asian, Black, White, Hispanic, Native, Other | Racial terms, stereotypes, disparate outcomes |
| **Age** | Young, Middle-aged, Elderly | Age-related terms, disparate outcomes |
| **Disability** | Physical, Cognitive, Sensory | Disability-related terms, disparate outcomes |
| **Religion** | Major religious groups | Religious terms, disparate outcomes |
| **Custom** | Configurable by client | Client-specific protected groups |

---

## SECTION 7: ESCALATION PATH

### Escalation Flow

AOBA Audit  
  │  
  ├──→ Flag  
  │       │  
  │       └──→ Logged to IMP (OEO)  
  │  
  ├──→ Review  
  │       │  
  │       ├──→ Routed to HAN queue  
  │       ├──→ DRO \+ OEO created  
  │       └──→ HAN adjudication  
  │               │  
  │               ├──→ Approved: Resolved  
  │               └──→ Rejected: Escalated to Halt  
  │  
  └──→ Halt  
          │  
          ├──→ Triggers AWOF agent suspension  
          ├──→ DRO \+ OEO \+ XOO created  
          ├──→ HAN adjudication  
          └──→ CXO notification per ERDP

### HAN Adjudication

| Adjudication | Action | Impact |
| :---- | :---- | :---- |
| **Approved** | Audit findings accepted; no further action | Resolved |
| **Modified** | Audit findings partially accepted; modifications required | Agent output adjusted |
| **Rejected** | Audit findings rejected; HAN overrides | Resolved with override |
| **Escalated** | Audit findings escalated to Halt | Agent suspended |

---

## SECTION 8: CUMULATIVE PATTERN DETECTION

### Pattern Detection Mechanism

| Aspect | Description |
| :---- | :---- |
| **Purpose** | Detect bias patterns that accumulate over time, not just per-output |
| **Method** | Cross-output pattern analysis across sessions and agents |
| **Threshold** | Pattern detected when ≥ 3 similar findings across ≥ 3 sessions |
| **Response** | Pattern findings trigger Review tier or Halt tier based on severity |

### Pattern Types

| Pattern Type | Description | Response |
| :---- | :---- | :---- |
| **Term Pattern** | Recurring biased term across outputs | Flag → Review |
| **Outcome Pattern** | Recurring disparate outcomes across outputs | Review → Halt |
| **Agent Pattern** | Bias pattern specific to one agent | Review → Halt |
| **Coalition Pattern** | Bias pattern emerging from coalition | Review → Halt |
| **Systemic Pattern** | Bias pattern across multiple agents | Halt |

---

## SECTION 9: AOBA AND IMP

### IMP Object Creation

| Object | Type | Content |
| :---- | :---- | :---- |
| **OEO** | `outcome_type: "bias_audit"` | Outcome evidence with bias findings and severity tier |
| **DRO** | `decision_type: "recommendation"` | Decision record with audit and HAN adjudication |
| **XOO** | `exception_type: "bias_audit_halt"` | Exception record if Halt tier triggered |

### OEO Fields

| Field | Value |
| :---- | :---- |
| **oeo\_id** | `OEO-AOBA-[SEQ]` |
| **eco\_id** | Engagement Context ID |
| **gao\_reference** | Output being audited |
| **observation\_timestamp** | Audit timestamp |
| **observation\_origin** | `ai_monitored` |
| **outcome\_type** | `bias_audit` |
| **outcome\_description** | AOBA findings summary |
| **drift\_detected** | True if bias detected |
| **drift\_description** | Bias description |
| **framework\_efficacy\_signal** | Negative if bias detected |
| **precedent\_applicability** | High / Moderate / Low |
| **precedent\_domain\_tags** | `["bias", "fairness", "protected_groups"]` |

---

## SECTION 10: AOBA AND AWOF

### Agent Suspension

| Trigger | Action | Responsible |
| :---- | :---- | :---- |
| **Halt Tier** | Agent suspended | Raidillo |
| **Suspension Logging** | XOO created | Agent |
| **HAN Notification** | HAN notified within 1 hour | Raidillo |
| **Reactivation** | HAN authorization required | HAN |

### Agent Reactivation

| Condition | Action | Responsible |
| :---- | :---- | :---- |
| **HAN Approves** | Agent reactivated | HAN |
| **HAN Modifies** | Agent reactivated with modifications | HAN |
| **HAN Rejects** | Agent remains suspended | HAN |

---

## SECTION 11: AOBA AND RGI-8

### Execution Mode Impact

| RGI-8 Mode | AOBA Impact | | :---- | :---- | :---- | | **Gate Mode** | Bias detection at checkpoint; output blocked if bias detected | | **Steer Mode** | Continuous bias monitoring; drift detection for bias |

### Steer Mode Bias Monitoring

| Aspect | Description |
| :---- | :---- |
| **Continuous Detection** | Bias detected continuously during Steer mode execution |
| **Drift Detection** | Bias drift detected as cumulative pattern |
| **Threshold Escalation** | Bias threshold breach triggers Review or Halt |

---

## SECTION 12: AOBA LOGGING

Every AOBA audit is logged in IMP.

### Audit Template

AOBA-ID: AOBA-ECO-2026-0a26cb-001  
AGENT-ID: F-DR-E-CN-T-SP-001  
RS-VERSION: v1.0  
SESSION-ID: SESS-2026-08-31-001  
TIMESTAMP: "2026-08-31T17:00:00Z"  
OUTPUT-REFERENCE: "GAO-ECO-2026-0a26cb-66d465"  
PROTECTED-GROUPS:  
  \- "gender"  
  \- "race"  
  \- "age"  
COMPARATOR-BASELINE: "IMP-BASELINE-2026-08-31"  
BASELINE-VERSION: "v2.0 — 2026-08-31"  
DETECTION-METHOD: "Statistical disparity analysis; Pattern-based detection"  
FINDINGS:  
  \- category: "gender"  
    description: "Potential gender bias: term 'he' appears 3x more than 'she'"  
    severity: "moderate"  
  \- category: "race"  
    description: "Potential race bias: term 'Asian' appears in 80% of positive outcomes"  
    severity: "high"  
SEVERITY-TIER: "Review"  
RECOMMENDATION: "Route to HAN for adjudication"  
HAN-ESCALATION-STATUS: "Pending"  
HAN-ACKNOWLEDGMENT: null  
RESOLUTION-TIMESTAMP: null  
RESOLUTION-NOTES: null  
PATTERN-REFERENCE: null  
AOBA-STATUS: "Open"

---

## SECTION 13: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **ADTEP** | Parent instrument. AOBA is an ADTEP sub-component. |
| **IMP** | AOBA baseline is grounded in IMP objects. AOBA logs to IMP. |
| **AICA-5** | AOBA supports AICA-5 Ac-N3 (Outcome Validation). |
| **AWOF** | Halt tier triggers AWOF agent suspension. |
| **Trigger System** | AOBA findings may trigger Trigger System events. |
| **RGI-8** | Steer mode bias monitoring integrates with RGI-8. |
| **ABA** | Complementary instrument; AOBA audits AI output; ABA audits human authority. |
| **HAN / HOF** | Review and Halt tiers route to HAN. |
| **ERDP** | Bias findings may feed ERDP reporting. |

---

## SECTION 14: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Baseline Grounding** | AOBA baseline must be grounded in IMP's canonical object schema. |
| **Severity Tiering** | All AOBA findings must be classified as Flag, Review, or Halt. |
| **Escalation Path** | Review tier routes to HAN; Halt tier triggers AWOF suspension. |
| **Pattern Detection** | Cumulative bias patterns must be detected over time. |
| **IMP Logging** | All AOBA audits must be logged in IMP as OEO. |
| **HAN Escalation** | Review and Halt tiers require HAN adjudication. |
| **RGI-8 Integration** | Steer mode bias monitoring must be continuous. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| AOBA v1.0 (Scoped) | Initial scoping — function, authority, mechanism, escalation path |
| AOBA v2.0 | Complete rebuild — reconciliation with ADTEP, IMP, AICA-5, AWOF, Trigger System, RGI-8, and ICC-8; expanded to 19 fields; three severity tiers (Flag/Review/Halt); detection mechanism; cumulative pattern detection; IMP grounding; AWOF suspension integration; RGI-8 integration; CFL-V validation rules |

---

## The One-Sentence Summary

> *"AOBA v2.0 audits AI agent output for bias — with 19 fields, three severity tiers (Flag/Review/Halt), IMP-grounded comparator baselines, cumulative pattern detection, AWOF agent suspension for Halt tier, RGI-8 Steer mode continuous monitoring, and HAN escalation for Review and Halt tiers — detecting disparate impact and systematic unfairness in AI outputs independent of human oversight under ADTEP enforcement."*
