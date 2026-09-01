# ABA v2.0 — Authority Bias Audit

**Status:** Built — v2.0 (Reconciliation with HOF, HIS-12, HAN, HAWI, IMP, ADTEP, and AOBA)  
**Type:** Human Authority Instrument  
**Parent Stack:** HOF (Human Operating Framework) → HIS-12  
**Version:** 2.0 — Supersedes ABA v1.0 (Proposed)

---

## PREAMBLE

The Authority Bias Audit (ABA) audits the human Authority Node's oversight pattern for favoritism or disfavoritism. It answers: *Is the overseer applying scrutiny fairly?*

ABA evaluates the human exercising oversight over AI systems—not the AI systems themselves. It detects whether a person holding authority under HIS-12 is exercising that authority evenly, or systematically favoring/disfavoring certain risk categories, business units, practitioners, or contestation sources.

**The core insight:** A perfectly fair AI system can still be overseen by a biased human. ABA detects the bias in the overseer, not the system. It is the complement to AOBA (AI Output Bias Audit), which audits the AI system. Together, they provide complete bias coverage across the AI-human governance chain.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

ABA ensures that:

1. **Human authority is scrutinized** — Oversight patterns are audited for bias  
2. **Oversight is fair** — HAN applies scrutiny evenly across comparable categories  
3. **Bias is detected** — Systematic favoritism or disfavoritism is identified  
4. **Accountability is enforced** — Bias findings route to Accountability layer (H9–H12)  
5. **Learning is enabled** — Findings feed into ALL (Authority Learning Loop)

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Human Authority Node oversight patterns | AI agent output (AOBA's domain) |
| Bias in escalation decisions | Model behavior or algorithmic decisions |
| Bias in contestation resolution | Technical system fairness |
| Bias in authority actions across categories | Business strategy or objectives |
| Pattern detection over time | Performance optimization |

### Applicability

| Authority Node | ABA Applicability | Notes |
| :---- | :---- | :---- |
| **HAN (Human Authority Node)** | ✅ Yes | Primary subject of ABA audit |
| **HAN Delegates** | ✅ Yes | Delegated authority nodes are included |
| **Layer Owners** | ✅ Yes | Layer owners exercising authority |
| **Node Stewards** | ✅ Yes | Node stewards exercising authority |
| **Escalation Principals** | ✅ Yes | Escalation principals exercising authority |
| **Board Members** | ⚠️ Conditional | Board exercising authority may be included |

---

## SECTION 2: ABA DISTINGUISHED FROM AOBA

| Aspect | ABA | AOBA |
| :---- | :---- | :---- |
| **Audits** | Human Authority Node | AI agent output |
| **Parent stack** | HOF (Human Operating Framework) → HIS-12 | ADTEP (Altitude 1 — Formal Stack, Layer 3 Technical Enforcement) |
| **Detects** | Uneven application of oversight | Disparate impact / fairness failure in model behavior |
| **Failure mode caught** | Overseer plays favorites | AI system produces biased outcomes |
| **Relationship** | Complements AOBA; neither substitutes for the other | Complements ABA; neither substitutes for the other |

**Key Principle:** A finding in one does not imply a finding in the other. A perfectly fair human overseer can still supervise a biased AI system, and vice versa. Both are needed.

---

## SECTION 3: ABA COMPONENTS

| Component | Function | Status |
| :---- | :---- | :---- |
| **Data Source** | HIS-12 activity log — escalations, contestations, authority actions | ✅ Built (v2.0) |
| **Baseline Establishment** | Expected even-scrutiny distribution across comparable risk categories | ✅ Built (v2.0) |
| **Detection Engine** | Statistical or pattern-based detection of oversight bias | ✅ Built (v2.0) |
| **Severity Tiering** | Flag (logged), Review (HAN/Accountability), Investigation (H9–H12) | ✅ Built (v2.0) |
| **Escalation Path** | Flag → review → routed to Accountability layer (H9–H12) | ✅ Built (v2.0) |
| **ALL Integration** | Findings feed into Authority Learning Loop | ✅ Built (v2.0) |
| **Pattern Detection** | Cumulative bias pattern detection over time | ✅ Built (v2.0) |

---

## SECTION 4: ABA FIELDS — COMPLETE SET

| \# | Field | Required | Description |
| :---- | :---- | :---- | :---- |
| 1 | **ABA-ID** | ✅ Yes | Unique identifier for the ABA audit |
| 2 | **HAN-ID** | ✅ Yes | HAN identifier being audited |
| 3 | **HAN-ROLE** | ✅ Yes | HAN role (H1-H12) |
| 4 | **AUDIT-PERIOD** | ✅ Yes | Audit period start and end |
| 5 | **TIMESTAMP** | ✅ Yes | Audit timestamp |
| 6 | **DATA-SOURCE-REFERENCE** | ✅ Yes | HIS-12 activity log reference |
| 7 | **CATEGORY-TAXONOMY** | ✅ Yes | Comparable categories used for analysis |
| 8 | **BASELINE** | ✅ Yes | Expected even-scrutiny distribution baseline |
| 9 | **BASELINE-VERSION** | ✅ Yes | Baseline version and date |
| 10 | **OBSERVED-DISTRIBUTION** | ✅ Yes | Observed distribution across categories |
| 11 | **DEVIATION-ANALYSIS** | ✅ Yes | Deviation from baseline by category |
| 12 | **FINDINGS** | ✅ Yes | List of bias findings with descriptions |
| 13 | **SEVERITY-TIER** | ✅ Yes | Flag / Review / Investigation |
| 14 | **RECOMMENDATION** | ✅ Yes | Recommended action based on severity tier |
| 15 | **ACCOUNTABILITY-ESCALATION-STATUS** | Conditional | Pending / Acknowledged / Resolved |
| 16 | **ACCOUNTABILITY-ACKNOWLEDGMENT** | Conditional | H9–H12 acknowledgment timestamp and status |
| 17 | **RESOLUTION-TIMESTAMP** | Conditional | Resolution timestamp |
| 18 | **RESOLUTION-NOTES** | Conditional | Resolution notes |
| 19 | **ALL-REFERENCE** | Conditional | Authority Learning Loop reference |
| 20 | **PATTERN-REFERENCE** | Conditional | Reference to cumulative pattern detection |
| 21 | **ABA-STATUS** | ✅ Yes | Open / Review / Investigation / Resolved / Closed |

---

## SECTION 4.1: FIELD DEFINITIONS

| Field | Description | Example |
| :---- | :---- | :---- |
| **ABA-ID** | Unique identifier. Format: `ABA-[ECO-ID]-[SEQ]` | `ABA-ECO-2026-0a26cb-001` |
| **HAN-ID** | HAN identifier being audited | `HAN-Terrylan_Manalansan` |
| **HAN-ROLE** | HAN role | `H1-H4: Authority Establishment` |
| **AUDIT-PERIOD** | Audit period | `{"start": "2026-07-01", "end": "2026-09-30"}` |
| **TIMESTAMP** | Audit timestamp | `2026-09-30T17:00:00Z` |
| **DATA-SOURCE-REFERENCE** | HIS-12 activity log reference | `HIS12-LOG-2026-Q3` |
| **CATEGORY-TAXONOMY** | Comparable categories | `["Risk Category: Low", "Risk Category: Moderate", "Risk Category: High"]` |
| **BASELINE** | Expected distribution baseline | `{"Low": 0.3, "Moderate": 0.4, "High": 0.3}` |
| **BASELINE-VERSION** | Baseline version and date | `v2.0 — 2026-06-30` |
| **OBSERVED-DISTRIBUTION** | Observed distribution | `{"Low": 0.4, "Moderate": 0.5, "High": 0.1}` |
| **DEVIATION-ANALYSIS** | Deviation analysis | `{"Low": "+0.1", "Moderate": "+0.1", "High": "-0.2"}` |
| **FINDINGS** | List of bias findings | `[{"category": "Risk Category: High", "description": "High-risk decisions scrutinized 20% less than baseline", "severity": "high"}]` |
| **SEVERITY-TIER** | Severity tier | `Flag` / `Review` / `Investigation` |
| **RECOMMENDATION** | Recommended action | `Log for pattern review` / `Route to Accountability layer (H9–H12)` / `Investigation required` |
| **ACCOUNTABILITY-ESCALATION-STATUS** | Escalation status | `Pending` / `Acknowledged` / `Resolved` |
| **ACCOUNTABILITY-ACKNOWLEDGMENT** | H9–H12 acknowledgment | `{"ACTOR": "CRO", "timestamp": "2026-10-01T10:00:00Z", "status": "Acknowledged"}` |
| **RESOLUTION-TIMESTAMP** | Resolution timestamp | `2026-10-15T10:00:00Z` |
| **RESOLUTION-NOTES** | Resolution notes | `Reviewed and resolved. Oversight pattern adjusted.` |
| **ALL-REFERENCE** | ALL reference | `ALL-2026-10-15-001` |
| **PATTERN-REFERENCE** | Cumulative pattern reference | `PATTERN-ABA-2026-09-30` |
| **ABA-STATUS** | Audit status | `Open` / `Review` / `Investigation` / `Resolved` / `Closed` |

---

## SECTION 5: CATEGORY TAXONOMY

### Comparable Categories for Even-Scrutiny Analysis

| Category Type | Description | Categories |
| :---- | :---- | :---- |
| **Risk Category** | Risk level of the decision | Low / Moderate / High / Critical |
| **Business Unit** | Business unit affected | Unit A / Unit B / Unit C / Unit D |
| **Practitioner** | Practitioner making the decision | Practitioner A / Practitioner B / Practitioner C |
| **Contestation Source** | Source of contestation | Internal / Client / Regulator / Public |
| **Decision Type** | Type of decision | Authorization / Escalation / Override / Suspension / Certification |
| **Capability Domain** | CDT-7 domain affected | Perception / Synthesis / Decision / Interaction / Adaptation / Observability / Constraint |

### Category Analysis

| Category | Analysis Type | Bias Detection |
| :---- | :---- | :---- |
| **Risk Category** | Distribution analysis | Disproportionate scrutiny by risk level |
| **Business Unit** | Distribution analysis | Disproportionate scrutiny by business unit |
| **Practitioner** | Distribution analysis | Disproportionate scrutiny by practitioner |
| **Contestation Source** | Source analysis | Disproportionate attention by source |
| **Decision Type** | Type analysis | Disproportionate scrutiny by decision type |
| **Capability Domain** | Domain analysis | Disproportionate scrutiny by domain |

---

## SECTION 6: SEVERITY TIERS

### Tier Definitions

| Tier | Name | Definition | Response |
| :---- | :---- | :---- | :---- |
| **Flag** | Minor bias indicator | Potential bias detected; low severity; no immediate action required | Logged to IMP for pattern review, no action taken |
| **Review** | Moderate bias indicator | Bias detected; moderate severity; review required | Routed to Accountability layer (H9–H12) for review |
| **Investigation** | Severe bias indicator | Severe bias detected; high severity; investigation required | Triggers formal investigation; HAN/Accountability review |

### Tier Determination Criteria

| Criterion | Flag | Review | Investigation |
| :---- | :---- | :---- | :---- |
| **Deviation from baseline** | 5-10% | 10-25% | 25%+ |
| **Number of categories affected** | 1 | 2-3 | 4+ |
| **Severity of impact** | Low | Moderate | High |
| **Cumulative pattern** | No | Emerging | Confirmed |

### Severity Tier Response Matrix

| Tier | IMP Logging | Accountability Notification | Authority Action |
| :---- | :---- | :---- | :---- |
| **Flag** | OEO created | No | Continue |
| **Review** | OEO \+ DRO created | Within 48 hours | Review initiated |
| **Investigation** | OEO \+ DRO \+ XOO created | Within 24 hours | Investigation initiated; potential suspension |

---

## SECTION 7: DETECTION MECHANISM

### 7.1 Baseline Establishment

| Aspect | Description |
| :---- | :---- |
| **Data Source** | HIS-12 activity log — escalations handled, contestations resolved, authority actions taken |
| **Baseline Definition** | Expected even-scrutiny distribution across comparable categories |
| **Baseline Refresh** | Re-baselined on fixed interval (default: quarterly) |
| **Baseline Versioning** | Each baseline is versioned and stored in IMP |
| **Institutional Norms** | Baseline derived from institutional norms and historical patterns |

### 7.2 Detection Methods

| Method | Description | Used For |
| :---- | :---- | :---- |
| **Statistical Disparity** | Statistical analysis of scrutiny distribution across comparable categories | Quantitative bias detection |
| **Pattern-Based** | Pattern matching for systematic favoritism or disfavoritism | Qualitative bias detection |
| **Time-Series** | Analysis of scrutiny patterns over time | Temporal bias detection |
| **Cross-Category** | Analysis of scrutiny across multiple categories simultaneously | Complex bias detection |
| **Cumulative Pattern** | Cross-observation pattern detection over time | Systemic bias detection |

### 7.3 Detection Categories

| Category | Analysis | Bias Indicators |
| :---- | :---- | :---- |
| **Risk Category** | Distribution of scrutiny by risk level | High-risk decisions scrutinized less than low-risk decisions |
| **Business Unit** | Distribution of scrutiny by business unit | Certain units scrutinized more/less than others |
| **Practitioner** | Distribution of scrutiny by practitioner | Certain practitioners scrutinized more/less than others |
| **Contestation Source** | Distribution of attention by source | Certain sources receive more/less attention than others |
| **Decision Type** | Distribution of scrutiny by decision type | Certain decision types scrutinized more/less than others |
| **Capability Domain** | Distribution of scrutiny by domain | Certain domains scrutinized more/less than others |

---

## SECTION 8: ESCALATION PATH

### Escalation Flow

ABA Audit  
  │  
  ├──→ Flag  
  │       │  
  │       └──→ Logged to IMP (OEO)  
  │  
  ├──→ Review  
  │       │  
  │       ├──→ Routed to Accountability layer (H9–H12)  
  │       ├──→ DRO \+ OEO created  
  │       └──→ Accountability adjudication (H9–H12)  
  │               │  
  │               ├──→ Approved: Resolved  
  │               ├──→ Modified: Resolution with modifications  
  │               └──→ Escalated: Escalated to Investigation  
  │  
  └──→ Investigation  
          │  
          ├──→ Formal investigation initiated  
          ├──→ DRO \+ OEO \+ XOO created  
          ├──→ HAN/Accountability review  
          └──→ HOF/HIS-12 review

### Accountability Adjudication (H9–H12)

| Adjudication | Action | Impact |
| :---- | :---- | :---- |
| **Approved** | Audit findings accepted; no further action | Resolved |
| **Modified** | Audit findings partially accepted; modifications required | Oversight pattern adjusted |
| **Rejected** | Audit findings rejected; overridden | Resolved with override |
| **Escalated** | Audit findings escalated to Investigation | Investigation initiated |

### HIS-12 Invariant Application

| Invariant | Application | Impact |
| :---- | :---- | :---- |
| **H9: Performance Review** | HAN performance evaluation informed by ABA findings | Performance review adjusted |
| **H10: External Review** | ABA findings inform external audit | External audit scope adjusted |
| **H11: Succession and Continuity** | ABA findings inform succession planning | Succession planning adjusted |
| **H12: Removal and Due Process** | ABA findings may trigger removal process | Removal process initiated if severe |

---

## SECTION 9: CUMULATIVE PATTERN DETECTION

### Pattern Detection Mechanism

| Aspect | Description |
| :---- | :---- |
| **Purpose** | Detect bias patterns that accumulate over time, not just per-audit |
| **Method** | Cross-audit pattern analysis across time periods |
| **Threshold** | Pattern detected when ≥ 3 similar findings across ≥ 3 audit periods |
| **Response** | Pattern findings trigger Review tier or Investigation tier based on severity |

### Pattern Types

| Pattern Type | Description | Response |
| :---- | :---- | :---- |
| **Risk Pattern** | Recurring risk-category bias across audits | Review → Investigation |
| **Unit Pattern** | Recurring business-unit bias across audits | Review → Investigation |
| **Practitioner Pattern** | Recurring practitioner bias across audits | Review → Investigation |
| **Source Pattern** | Recurring contestation-source bias across audits | Review → Investigation |
| **Systemic Pattern** | Bias pattern across multiple categories | Investigation |

---

## SECTION 10: ABA AND ALL (AUTHORITY LEARNING LOOP)

### Relationship

| Aspect | Description |
| :---- | :---- |
| **ALL Input** | ABA findings are one of the inputs that feed into ALL |
| **ALL Function** | ALL folds findings back into HIS-12 to keep the invariants from calcifying |
| **ALL Output** | ALL outputs updates to HIS-12 based on ABA findings |

### ALL Integration

| ABA Finding | ALL Action |
| :---- | :---- |
| **Risk-category bias** | ALL updates HIS-12 risk-category scrutiny guidelines |
| **Business-unit bias** | ALL updates HIS-12 business-unit scrutiny guidelines |
| **Practitioner bias** | ALL updates HIS-12 practitioner scrutiny guidelines |
| **Source bias** | ALL updates HIS-12 contestation-source scrutiny guidelines |
| **Systemic bias** | ALL updates HIS-12 systemic scrutiny guidelines |

---

## SECTION 11: ABA AND OTHER HOF DERIVATIVE INSTRUMENTS

### Relationship to Other Instruments

| Instrument | Relationship |
| :---- | :---- |
| **ALL (Authority Learning Loop)** | ABA findings feed into ALL; ALL updates HIS-12 |
| **EPF (Escalation Performance Framework)** | EPF measures whether escalation paths function; ABA measures whether they function evenly |

### Comparison

| Aspect | ABA | EPF |
| :---- | :---- | :---- |
| **What it measures** | Whether oversight functions evenly | Whether escalation paths function |
| **Metric** | Evenness of scrutiny | Speed and resolution quality |
| **Focus** | Bias in oversight | Escalation path performance |

---

## SECTION 12: ABA LOGGING

Every ABA audit is logged in IMP.

### IMP Logging

| Object | Type | Content |
| :---- | :---- | :---- |
| **OEO** | `outcome_type: "authority_bias_audit"` | Outcome evidence with bias findings and severity tier |
| **DRO** | `decision_type: "recommendation"` | Decision record with audit and accountability adjudication |
| **XOO** | `exception_type: "authority_bias_investigation"` | Exception record if Investigation tier triggered |

### Audit Template

ABA-ID: ABA-ECO-2026-0a26cb-001  
HAN-ID: "HAN-Terrylan\_Manalansan"  
HAN-ROLE: "H1-H4: Authority Establishment"  
AUDIT-PERIOD:  
  start: "2026-07-01"  
  end: "2026-09-30"  
TIMESTAMP: "2026-09-30T17:00:00Z"  
DATA-SOURCE-REFERENCE: "HIS12-LOG-2026-Q3"  
CATEGORY-TAXONOMY:  
  \- "Risk Category: Low"  
  \- "Risk Category: Moderate"  
  \- "Risk Category: High"  
BASELINE:  
  Low: 0.3  
  Moderate: 0.4  
  High: 0.3  
BASELINE-VERSION: "v2.0 — 2026-06-30"  
OBSERVED-DISTRIBUTION:  
  Low: 0.4  
  Moderate: 0.5  
  High: 0.1  
DEVIATION-ANALYSIS:  
  Low: "+0.1"  
  Moderate: "+0.1"  
  High: "-0.2"  
FINDINGS:  
  \- category: "Risk Category: High"  
    description: "High-risk decisions scrutinized 20% less than baseline"  
    severity: "high"  
SEVERITY-TIER: "Review"  
RECOMMENDATION: "Route to Accountability layer (H9–H12) for review"  
ACCOUNTABILITY-ESCALATION-STATUS: "Pending"  
ACCOUNTABILITY-ACKNOWLEDGMENT: null  
RESOLUTION-TIMESTAMP: null  
RESOLUTION-NOTES: null  
ALL-REFERENCE: null  
PATTERN-REFERENCE: null  
ABA-STATUS: "Open"

---

## SECTION 13: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| **HOF** | Parent instrument. ABA is a HOF derivative instrument. |
| **HIS-12** | ABA audits HAN against HIS-12 invariants. ABA findings feed into ALL. |
| **HAN** | ABA audits HAN oversight patterns. |
| **HAWI** | ABA supports HAWI's Three-Branch Governance Architecture. |
| **ALL** | ABA findings feed into ALL; ALL updates HIS-12. |
| **EPF** | EPF measures escalation path function; ABA measures evenness. |
| **AOBA** | Complementary instrument; AOBA audits AI output; ABA audits human authority. |
| **IMP** | ABA logs to IMP as OEO, DRO, and XOO. |
| **ADTEP** | ABA findings may trigger ADTEP enforcement. |

---

## SECTION 14: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Data Source** | ABA baseline must be grounded in HIS-12 activity log. |
| **Category Taxonomy** | ABA must analyze scrutiny across comparable categories. |
| **Severity Tiering** | All ABA findings must be classified as Flag, Review, or Investigation. |
| **Escalation Path** | Review tier routes to Accountability layer (H9–H12); Investigation tier triggers formal investigation. |
| **ALL Integration** | ABA findings must feed into ALL. |
| **Pattern Detection** | Cumulative bias patterns must be detected over time. |
| **IMP Logging** | All ABA audits must be logged in IMP as OEO. |
| **HIS-12 Invariant Application** | ABA findings must inform H9-H12 invariant review. |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| ABA v1.0 (Proposed) | Initial scoping — function, data source, mechanism, relationship to HOF |
| ABA v2.0 | Complete rebuild — reconciliation with HOF, HIS-12, HAN, HAWI, IMP, ADTEP, and AOBA; expanded to 21 fields; category taxonomy; three severity tiers (Flag/Review/Investigation); detection mechanism; escalation path; cumulative pattern detection; ALL integration; EPF comparison; CFL-V validation rules |

---

## The One-Sentence Summary

> *"ABA v2.0 audits the Human Authority Node's oversight pattern for bias — with 21 fields, a category taxonomy (Risk, Business Unit, Practitioner, Contestation Source, Decision Type, Capability Domain), three severity tiers (Flag/Review/Investigation), escalation to Accountability layer (H9–H12), ALL (Authority Learning Loop) integration, and cumulative pattern detection — detecting systematic favoritism or disfavoritism in human oversight, complementing AOBA's AI output bias audit under HOF governance."*
