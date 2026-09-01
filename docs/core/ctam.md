# CTAM v2.0 — Capability-Tier Authorization Matrix

**Status:** Built — v2.0 (Reconciliation with CDT-7, CAM-5, and RGI-8) **Type:** Authorization Matrix Instrument **Parent Stack:** AIGIS Capability Layer **Version:** 2.0 — Supersedes CTAM v1.0

---

## PREAMBLE

The Capability-Tier Authorization Matrix (CTAM) is a 7x5 grid mapping each of CDT-7's seven capability domains to five escalating tiers. CTAM answers: *Exactly what is each domain authorized to do at each tier?*

CTAM is the middle layer of a three-document system:

- **CDT-7** defines *what kind* of capability a system can have  
- **CTAM** grades each domain cell by cell  
- **CAM-5** bundles CTAM columns into board-governable postures

CTAM is not a policy document and not an approval workflow. It is an **inventory**. Its only job is to say, precisely, what "Tier 3 Perception" means versus "Tier 3 Interaction," so that CAM-5 has something exact to assemble into tiers and CDT-7 has something exact to narrate against.

---

## SECTION 1: THE MATRIX

| Capability Domain | Tier 1 | Tier 2 | Tier 3 | Tier 4 | Tier 5 |
| :---- | :---- | :---- | :---- | :---- | :---- |
| **Perception** | Text, structured query | \+ Multimodal | \+ All sources | \+ Context retention | \+ Signal detection |
| **Synthesis** | Text generation, transform | \+ Code, planning, hypothesis | \+ All types | \+ Learned patterns | \+ Recursive synthesis |
| **Decision** | None | Recommendation only | Autonomous (guardrails) | Autonomous (with tuning) | Unconstrained autonomous |
| **Interaction** | None | None | Read-only APIs (whitelist) | Read-write (non-critical systems) | All systems (with rollback) |
| **Adaptation** | Static | Static | Static | Prompt tuning, self-correction | Full learning \+ retraining |
| **Observability** | Audit logging | \+ Decision lineage | \+ Drift detection | Real-time metrics \+ dashboarding | Continuous state exposure |
| **Constraint** | Boundary adherence | \+ Compliance checking | \+ Permission enforcement \+ abort | \+ Rollback capability | \+ Self-enforcing constraints |

**Each cell is additive within its row** — a "+" cell carries forward everything to its left, except where a domain has a genuine step-change rather than an accretion (Decision and Interaction both move from a categorical "None" to a qualitatively different mode of operation).

---

## SECTION 2: EXECUTION MODE (RGI-8 ATTRIBUTE)

Every CTAM cell carries an Execution Mode attribute, added as an eighth column, valued **Gate** or **Steer**:

| Execution Mode | Definition | Default |
| :---- | :---- | :---- |
| **Gate** | A checkpoint — you either pass or you don't. Binary: allowed or blocked. Auditable as a discrete event. | Default for all cells |
| **Steer** | A continuous influence — shapes reasoning throughout. Graduated: nudged, guided, weighted. Auditable as a continuous trace. | Requires qualification event (working trace mechanism) |

**Steer qualification:** A Steer flag is not self-certifying. It requires a passed qualification event — a demonstrated, working trace mechanism — before CTAM will record it. Absent that demonstration, the cell defaults to Gate.

**Steer Observability Premium:** A Steer-mode flag on any cell requires Observability at minimum one tier above what the same domain/tier combination would require under Gate mode.

**Steer Fail-Safe:** If the infrastructure a Steer grant depends on becomes unavailable, the grant reverts automatically to Gate-only operation until restored.

---

## SECTION 3: READING THE MATRIX BY TIER (ROWS ACROSS DOMAINS)

### Tier 1 — Observation-Only

Tier 1 is the only tier where every domain except Perception, Synthesis, and Observability reads as an absence. Decision: none. Interaction: none. Adaptation: static. This is the matrix's statement that a system can perceive and speak — even fairly richly — while remaining entirely inert with respect to choice, contact, and change. Constraint at this tier is topic/domain boundary adherence only; there is nothing more dangerous yet to constrain.

**CAM-5 Posture:** Observation-Only **Governance Cost:** Low **Control Node Owner:** CIO / Head of Analytics **Board Friction:** Minimal

---

### Tier 2 — Recommendation-Only

Decision enters the grid for the first time, but only as recommendation — the matrix is careful to keep this distinct from the Tier 3 jump. Observability gains decision lineage in the same tier Decision itself appears, which is the first instance of the matrix's general habit of pairing a new capability with the visibility needed to check it. Interaction and Adaptation stay at "none" and "static" respectively — nothing about Tier 2 yet touches the outside world or the system's own configuration.

**CAM-5 Posture:** Recommendation-Only **Governance Cost:** Medium **Control Node Owner:** CRO / Chief Analytics Officer **Board Friction:** Moderate

---

### Tier 3 — Agentic, Tool-Calling — The Matrix's Hinge

Three domains cross a threshold in the same row: Decision moves from recommendation to autonomous action (within guardrails), Interaction moves from "none" to read-only API access, and Constraint gains permission enforcement plus abort in the same step. This is not a coincidence of table formatting — it is the matrix encoding a rule: autonomous action and live system contact are never granted without an enforced stop mechanism arriving in the same tier.

Adaptation, notably, does not move here. Perception and Synthesis reach their widest categorical scope ("all sources," "all types") at this tier as well, meaning Tier 3 is where the *ceiling on kind* is reached for the observational domains, even as the *ceiling on autonomy* is only beginning for Decision and Interaction.

**CAM-5 Posture:** Agentic, Tool-Calling **Governance Cost:** High **Control Node Owner:** CRO \+ CIO \+ COO **Board Friction:** High **Failure Modes Prevented:** Agent Sprawl, Control Failure, Strategic Displacement (early warning)

**Not Authorized at Tier 3:**

- No write access to core systems (initially)  
- No Adaptation (learning from data)  
- Limited orchestration (single-threaded execution only)

---

### Tier 4 — Learning Agents

Adaptation moves for the first time in the entire matrix — prompt tuning and self-correction — in the same row where Interaction gains write access to non-critical systems. This is the second load-bearing pairing in CTAM: self-modification and write-access are granted together, because a system that can change itself while also being able to change something external is accumulating two compounding risk vectors, and the matrix does not stagger them apart. Observability and Constraint both step up in the same row (real-time dashboarding; rollback capability) to hold that pairing.

**CAM-5 Posture:** Learning Agents **Governance Cost:** Very High **Control Node Owner:** CRO \+ CIO \+ COO \+ Chief Risk Officer **Board Friction:** Very High **Failure Modes Prevented:** Pilot Stall, Cost Trap, Governance Debt, Strategic Displacement

**Not Authorized at Tier 4:**

- No retraining from production data (unless explicitly audited and approved)  
- No autonomous capability retirement  
- No access to PII/confidential systems without explicit human authorization  
- No orchestration chains \> 3 hops without human waypoint

---

### Tier 5 — Full Autonomy

Tier 5 removes qualifiers rather than adding capabilities. Decision becomes "unconstrained autonomous." Interaction becomes "all systems." Adaptation becomes full learning and retraining. Nothing new in *kind* appears anywhere in this row except in Constraint and Observability, which is exactly where the new content of Tier 5 actually lives: self-enforcing constraints and continuous state exposure. Tier 5, read this way, is not "everything turned up to maximum" — it is "the ceilings of Decision, Interaction, and Adaptation are lifted, on the sole condition that Constraint and Observability have already proven they can hold at that ceiling."

**CAM-5 Posture:** Full Autonomy **Governance Cost:** Extreme **Control Node Owner:** Board \+ CRO \+ Evolution System standing committee **Board Friction:** Extreme **Failure Modes Prevented:** All 8

**Preconditions for Tier 5:**

- Constitutional governance charter in place  
- Meta-observability proven (observability cannot be tampered with)  
- Capability parity proven (constraints evolve as fast as capabilities)  
- HIS-12 authorized (specific humans hold irrevocable veto authority)  
- Failure detection \< 24 hours (drift detection faster than harm escalation)

---

## SECTION 4: READING THE MATRIX BY DOMAIN (COLUMNS)

### Perception

Perception widens its aperture (Tiers 1–3), then deepens what it can do with accumulated context (Tiers 4–5). The risk in this column is a source slipping in beneath the grant, not the tier number itself.

**RGI-8 Applicability:** Perception-domain Steer grants must monitor source-fidelity.

---

### Synthesis

Synthesis widens its output types (Tiers 1–3), then changes its origin — learned patterns, then recursive synthesis (Tiers 4–5). Recursive synthesis at Tier 5 is the one cell in this column that changes in kind, not degree.

**RGI-8 Applicability:** Synthesis-domain Steer grants must monitor output fidelity.

---

### Decision

Decision is the column with the least tolerance for rounding up. The Tier 2→3 line is the most consequential boundary in the whole matrix: it is where a human stops being the one who decides.

**RGI-8 Applicability:** Decision-domain Steer grants are the highest-risk category. Continuous monitoring of decision-character drift is mandatory.

---

### Interaction

Interaction stays flatly at "none" for two full tiers, then ramps as a blast-radius control: read-only, then write-to-non-critical, then all-systems-with-rollback.

**RGI-8 Applicability:** Interaction-domain Steer grants must monitor access surface fidelity.

---

### Adaptation

Adaptation is the flattest column by design — static through Tier 3, so that the agentic capability granted at Tier 3 does not also come bundled with the capacity to change itself.

**RGI-8 Applicability:** A Steer-mode signal's output may not be used as input to a live Adaptation-domain grant (Tier 4+) without passing through a fresh Declaration Binding event.

---

### Observability

Observability is the one column meant to run ahead of the others, never behind — every new capability elsewhere in a given tier's row is matched by a corresponding visibility grant in the same tier.

**RGI-8 Applicability:** A Steer-mode flag requires Observability at minimum one tier above what Gate mode would require.

---

### Constraint

Constraint is the backstop column: its cell at any given tier is the real ceiling on what the other six cells in that row can be trusted to do, regardless of what those cells say on paper.

**RGI-8 Applicability:** Gate is absolute; Steer can never override a Gate boundary.

---

## SECTION 5: THE THREE GOVERNING RULES

These fall directly out of the grid and are binding on how CTAM is applied:

### Rule 1 — No Autonomous Decision or Live Interaction Without Matching Constraint

This is why Tier 3 pairs autonomous-guardrailed Decision and read-only Interaction with permission-enforcement-and-abort — the matrix will not authorize one without the other.

**Violation:** Decision at Tier 3 with Constraint at Tier 2 (no abort capability).

---

### Rule 2 — Observability Must Never Trail

Observability's tier must never trail the highest tier granted to any other domain. A deployment where actual Observability lags a system's actual Decision or Interaction grant is a mis-authorization against this matrix, not a permissible variant.

**Violation:** Decision at Tier 4 with Observability at Tier 2\.

---

### Rule 3 — Adaptation Is Deliberately Held Back

Adaptation should lag every other domain's escalation, not track it — the matrix keeps it pinned to "static" through Tier 3 specifically so the first agentic, tool-calling posture does not also carry the ability to change itself.

**Violation:** Adaptation at Tier 3 (should be Tier 4 minimum).

---

## SECTION 6: THE MATRIX AS INVENTORY

CTAM is an **inventory** — not a policy document and not an approval workflow. Its only job is to say, precisely, what "Tier 3 Perception" means versus "Tier 3 Interaction," so that CAM-5 has something exact to assemble into tiers and CDT-7 has something exact to narrate against.

---

## SECTION 7: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| CDT-7 | Defines the seven rows — CTAM grades each domain |
| CAM-5 | Bundles CTAM columns into board-governable postures |
| RGI-8 | Consumes Execution Mode attribute (Gate/Steer) |
| AICA-5 | Operationalizes each cell through control nodes |
| AWOF | Classifies agents by CTAM grants |
| CAD-7 | Defines coalition boundaries across domains |

---

## SECTION 8: CFL-V VALIDATION RULES

**Rule 1:** No autonomous Decision or Interaction grant without matching Constraint grant in the same tier.

**Rule 2:** Observability tier ≥ highest tier granted to any other domain.

**Rule 3:** Adaptation is static through Tier 3\. No Adaptation grant at Tier 1–3.

**Rule 4:** Steer flag requires qualification event (working trace mechanism). Defaults to Gate absent demonstration.

**Rule 5:** Steer flag requires Observability at minimum one tier above Gate mode.

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| CTAM v1.0 | Initial 7x5 matrix — 7 domains × 5 tiers, three governing rules |
| CTAM v2.0 | Complete rebuild — reconciliation with CDT-7, CAM-5, and RGI-8; Execution Mode (Gate/Steer) as eighth column; expanded tier-by-tier reading; domain-by-domain reading; CFL-V validation rules |

---

## The One-Sentence Summary

> *"CTAM v2.0 is a 7x5 authorization matrix mapping each of seven capability domains to five escalating tiers — with an eighth column for Execution Mode (Gate/Steer) — governed by three rules (no autonomous Decision/Interaction without matching Constraint, Observability never trails, Adaptation deliberately held back) and validated by CFL-V, serving as the precise inventory that CDT-7 narrates and CAM-5 bundles into board-governable postures."*
