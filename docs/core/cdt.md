# CDT-7 v2.0 — Capability Domains Taxonomy

**Status:** Built — v2.0 (Reconciliation with CTAM, CAM-5, and RGI-8) **Type:** Capability Taxonomy Instrument **Parent Stack:** AIGIS Capability Layer **Version:** 2.0 — Supersedes CDT-7 v1.0

---

## PREAMBLE

The Capability Domains Taxonomy (CDT-7) classifies machine capability into seven distinct axes before any authorization is granted. CDT-7 answers: *What kind of capability is this, and what authorization logic applies to it?*

CDT-7 exists to prevent a single failure mode: treating all machine capability as one undifferentiated mass, and therefore authorizing (or restricting) it with one undifferentiated rule. A system authorized to *perceive* a data source has not thereby been authorized to *act* on what it perceives. A system authorized to *generate* an output has not thereby been authorized to *decide* that the output should be deployed.

CDT-7 is the foundation of CTAM (Capability-Tier Authorization Matrix) and CAM-5 (5-Tier Capability Authorization Model). CTAM grades each domain from Tier 1 through Tier 5\. CAM-5 bundles CTAM columns into board-governable postures.

---

## SECTION 1: THE SEVEN DOMAINS

### 1.1 Perception

**Definition:** The capability to see authorized sources—to ingest, read, or otherwise draw information from a designated input surface (documents, sensors, logs, live feeds, third-party APIs, other systems' outputs).

**Scope:** Perception is bounded by *source*, not by *content*. Authorizing perception means authorizing which wells a system may draw from—a specific database, a specific inbox, a specific sensor array—not what conclusions it may draw once it drinks. A system perceiving beyond its authorized source set (scraping an adjacent database it was never granted, listening to a channel it wasn't provisioned for) is in breach at the domain's root, independent of what it does with the excess information.

**Representative Capabilities:** Reading a document corpus; querying a database; ingesting sensor telemetry; monitoring a communications channel; retrieving another agent's output as input.

**Why It Is a Domain:** Every other domain depends on it. Synthesis without perception is confabulation. Decision without perception is guesswork wearing the clothes of judgment. Getting Perception's boundary wrong corrupts everything built downstream of it—silently.

**CTAM Trajectory:** Perception widens its aperture (Tiers 1–3), then deepens what it can do with accumulated context (Tiers 4–5). The risk in this column is a source slipping in beneath the grant, not the tier number itself.

**RGI-8 Applicability:** Perception-domain Steer grants must monitor source-fidelity, not only output-fidelity—a continuously-reweighted Perception grant can drift toward an unauthorized source gradually.

**AIGIS Components:** C-N1 (Intelligence Sourcing), C-N3 (Signal Validation), C-N5 (Knowledge Boundary Management)

---

### 1.2 Synthesis

**Definition:** The capability to generate authorized outputs—to produce new artifacts (text, code, images, structured data, decisions-in-draft-form) from what has been perceived.

**Scope:** Synthesis is bounded by *output class*, not by *effort*. A system authorized to draft a memo is not authorized to draft a contract merely because both are text. Output classes carry different downstream consequence profiles, and CDT-7 treats each class as a separately authorizable capability, even when the underlying generative mechanism is identical.

**Representative Capabilities:** Drafting prose or code; producing a structured recommendation; rendering a visualization; generating a candidate decision for human review; producing a certification artifact.

**Why It Is a Domain:** Synthesis is where the "monosomatic company" model lives or dies—unlimited synthetic labor is, concretely, unlimited authorized Synthesis. It is also the domain most prone to scope creep, because generative capability is fungible: a system that can draft a memo can, with no additional technical capability, draft a resignation letter, a legal filing, or a fabricated citation.

**CTAM Trajectory:** Synthesis widens its output types (Tiers 1–3), then changes its origin—learned patterns, then recursive synthesis (Tiers 4–5). Recursive synthesis at Tier 5 is the one cell in this column that changes in kind, not degree.

**RGI-8 Applicability:** Synthesis-domain Steer grants must monitor output fidelity against declared intent—a continuously-reweighted Synthesis grant can drift toward unauthorized output classes gradually.

**AIGIS Components:** C-N2 (Inference Architecture), C-N4 (Output Calibration), Ac-N1 (Decision Lineage)

---

### 1.3 Decision

**Definition:** The capability to make authorized choices—to select among alternatives in a way that has standing (i.e., the choice is treated as final, not merely advisory) within some bounded scope.

**Scope:** Decision is the domain most tightly coupled to HAN/HIS-12, because "who may authorize a decision-making capability" is the same question HIS-12 already answers for human authority. CDT-7 does not duplicate that logic—it marks the boundary at which a system's output stops being a draft (Synthesis) and starts being a determination (Decision). That boundary is the single most consequential line in the whole taxonomy.

**Representative Capabilities:** Approving or rejecting a transaction below a threshold; selecting a vendor from a pre-vetted list; triaging and routing a request without further review; setting a parameter within a pre-authorized range.

**Why It Is a Domain:** Conflating Synthesis and Decision is the single most common governance failure in AI deployment—a system that was only ever authorized to *suggest* gets treated, by drift or convenience, as authorized to *decide*.

**CTAM Trajectory:** Decision is the column with the least tolerance for rounding up. The Tier 2→3 line is the most consequential boundary in the whole matrix: it is where a human stops being the one who decides.

**RGI-8 Applicability:** Decision-domain Steer grants are the highest-risk category. Continuous monitoring of decision-character drift is mandatory. Drift detection thresholds must be declared and enforced.

**AIGIS Components:** A-N1 (Trigger Rights), A-N2 (Binding Thresholds), A-N3 (Override Protocols), A-N4 (Escalation Paths), A-N5 (Delegation Boundaries)

---

### 1.4 Interaction

**Definition:** The capability to touch authorized systems—to write, invoke, or otherwise cause effects in an external environment (a database, an API, a physical actuator, another agent).

**Scope:** Interaction is bounded by *surface*, not by *intent*. A system authorized to write to one table in a database is not authorized to write to an adjacent table, regardless of how benign the write. Interaction is the domain where governance failure becomes physically or operationally real—everything upstream (Perception, Synthesis, Decision) can be wrong quietly; Interaction is where wrongness becomes an event.

**Representative Capabilities:** Writing to a system of record; calling an external API; sending a communication on the organization's behalf; executing a financial transaction; actuating a physical or infrastructural control.

**Why It Is a Domain:** Interaction is where the "authorized under conditions" clause has the least tolerance for ambiguity, because the cost of an unauthorized interaction is frequently irreversible in a way that unauthorized perception or synthesis is not (you can retract a draft memo; you cannot always retract a sent wire transfer).

**CTAM Trajectory:** Interaction is the domain with the longest runway of "none" in the entire matrix—Tiers 1 and 2 grant no system interaction whatsoever. The real onset is Tier 3: read-only APIs, whitelisted. Tier 4 crosses into read-write on non-critical systems. Tier 5 opens all systems, with rollback as the compensating control.

**RGI-8 Applicability:** Interaction-domain Steer grants must monitor access surface fidelity—a continuously-reweighted Interaction grant can drift toward unauthorized surfaces gradually.

**AIGIS Components:** A-N5 (Delegation Boundaries), E-N2 (Pipeline Orchestration), E-N3 (Concurrency Governance)

---

### 1.5 Adaptation

**Definition:** The capability to change itself under authorized conditions—to modify its own parameters, prompts, policies, weights, or operating procedure in response to feedback, performance data, or explicit instruction.

**Scope:** Adaptation is bounded by *what may change* and *what may not*. Authorizing a system to adjust its retrieval strategy is not the same as authorizing it to adjust its own Decision-domain thresholds. CDT-7 treats self-modification as its own domain precisely because it is recursive—a system with unauthorized Adaptation capability can, in principle, use that capability to expand its authorization in every other domain.

**Representative Capabilities:** Updating a retrieval index based on feedback; revising an internal heuristic; proposing (not enacting) a change to its own operating parameters; fine-tuning behavior within a declared envelope.

**Why It Is a Domain:** This is the domain the "Formal Stack vs. Shadow" distinction exists partly to police—informal capture literacy (Altitude 2\) is largely about noticing Adaptation happening without anyone having authorized it.

**CTAM Trajectory:** Adaptation is the flattest column in the matrix by design—static at Tier 1, static at Tier 2, still static at Tier 3\. Nothing moves until Tier 4, where the matrix grants prompt tuning and self-correction. Tier 5 grants full learning and retraining.

**RGI-8 Applicability:** A Steer-mode signal's output may not be used as input to a live Adaptation-domain grant (Tier 4+) without passing through a fresh Declaration Binding event (RGI-8 1.6 Adaptation Firewall).

**AIGIS Components:** AITOS Evolution System, AICA-5 Ac-N5 (Learning Integration), AWOF Trigger System

---

### 1.6 Observability

**Definition:** The capability to expose authorized visibility—to make its own state, reasoning, activity, or outputs legible to a designated human or system for review.

**Scope:** Observability is bounded by *audience* and *granularity*. A system may be authorized to expose summary-level activity to one audience and full reasoning traces to another. This is the one domain where the default posture is expansive rather than restrictive—under-authorizing Observability defeats the purpose of every other domain's authorization.

**Representative Capabilities:** Logging decisions and their rationale; exposing a reasoning trace on request; surfacing activity to a dashboard; generating an audit artifact; flagging its own uncertainty or boundary violations.

**Why It Is a Domain:** Observability is the domain that makes the other six auditable rather than merely asserted. A Decision-domain grant with no corresponding Observability grant is an unfalsifiable claim of compliance.

**CTAM Trajectory:** Observability is the one column built to run *ahead* of the others, never behind. Tier 1 is baseline audit logging. Tier 2 adds decision lineage. Tier 3 adds drift detection. Tier 4 adds real-time metrics and dashboarding. Tier 5 reaches continuous state exposure.

**RGI-8 Applicability:** A Steer-mode flag on any cell requires Observability at minimum one tier above what the same domain/tier combination would require under Gate mode (RGI-8 1.8 Steer Observability Premium).

**AIGIS Components:** Co-N2 (Drift Detection), E-N4 (Monitoring Loops), Ac-N1 (Decision Lineage), ERDP

---

### 1.7 Constraint

**Definition:** The capability to enforce authorized limits—on itself or on other systems it interacts with; the capacity to refuse, halt, or bound an action because a limit has been reached.

**Scope:** Constraint is bounded by *what it can stop*, not by what it can start—it is the only domain defined entirely in the negative. A system's Constraint capability is what allows every other domain's authorization to have teeth: a Decision-domain grant with a value ceiling is only real if the system also has the Constraint-domain capability to actually refuse a decision above that ceiling.

**Representative Capabilities:** Enforcing a rate limit or value ceiling on its own outputs; refusing an out-of-scope request; halting an in-progress action when a threshold is crossed; enforcing a limit on another system's request (gatekeeping).

**Why It Is a Domain:** Without a distinct Constraint domain, every limit elsewhere in CDT-7 is a policy statement rather than an enforced boundary—the difference between "this system should not exceed X" and "this system cannot exceed X" is the entire difference between governance-on-paper and governance-in-practice.

**CTAM Trajectory:** Constraint is the domain CTAM uses as its own backstop. Tier 1 is boundary adherence. Tier 2 adds compliance checking. Tier 3 is the pivotal step: permission enforcement plus abort. Tier 4 adds rollback. Tier 5 adds self-enforcing constraints.

**RGI-8 Applicability:** Gate is absolute; Steer can never override a Gate boundary. A conflict between a Gate and a Steer signal on the same domain resolves to the Gate (RGI-8 1.5 Constraint Supremacy Over Steering).

**AIGIS Components:** A-N1 (Trigger Rights), A-N2 (Binding Thresholds), A-N3 (Override Protocols), ADTEP Escalation Flag, CEF

---

## SECTION 2: THE THREE GOVERNING RULES

These rules fall directly out of the domain architecture and are binding on how CDT-7 is applied:

### Rule 1: Asymmetric Tiering Is the Normal Case

The seven domains are not meant to escalate in lockstep. CAM-5's Tier 3 pairs autonomous Decision and live Interaction with a still-static Adaptation column, precisely because those domains are not meant to escalate together.

**Violation:** Granting Adaptation (Tier 4+) without corresponding Decision or Interaction maturity.

---

### Rule 2: Observability Must Never Lag

Observability's tier at any authorization should never trail the highest tier granted across the other six—because visibility is the precondition for trusting the others at all.

**Violation:** Decision at Tier 4 with Observability at Tier 2\.

---

### Rule 3: Constraint Sets the Real Ceiling

No other domain's tier should ever be granted at a level the Constraint column at that same tier cannot actually enforce. The Constraint cell is the real ceiling, whatever the other cells say.

**Violation:** Decision at Tier 3 with Constraint at Tier 1 (no abort capability).

---

## SECTION 3: DOMAIN INTERDEPENDENCIES

| Domain | Depends On | Why |
| :---- | :---- | :---- |
| Synthesis | Perception | Cannot generate outputs from nothing |
| Decision | Perception, Synthesis | Cannot decide without inputs and options |
| Interaction | Decision | Cannot act without a decision to act |
| Adaptation | All upstream | Cannot change itself without knowing what it is changing |
| Observability | All upstream | Cannot observe what it cannot see |
| Constraint | All upstream | Cannot enforce limits on what it cannot define |

---

## SECTION 4: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship |
| :---- | :---- |
| CTAM | Grades each domain from Tier 1 through Tier 5, cell by cell |
| CAM-5 | Bundles CTAM columns into board-governable postures |
| RGI-8 | Consumes CTAM's Execution Mode attribute per domain |
| AICA-5 | Operationalizes each domain through control nodes |
| AWOF | Classifies agents by domain capabilities |
| CAD-7 | Defines coalition boundaries across domains |

---

## SECTION 5: CFL-V VALIDATION RULES

**Domain Separation:** Each domain is distinct and non-overlapping. Perception is not Synthesis. Decision is not Interaction. Constraint is not Delegation.

**Observability Rule:** Observability tier ≥ highest tier granted elsewhere.

**Constraint Rule:** No domain tier may exceed Constraint tier in the same row.

**Adaptation Rule:** Adaptation is static through Tier 3\. No Adaptation grant at Tier 1–3.

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| CDT-7 v1.0 | Initial taxonomy — 7 domains, 3 governing rules |
| CDT-7 v2.0 | Complete rebuild — reconciliation with CTAM, CAM-5, and RGI-8; expanded domain definitions with scope, CTAM trajectory, RGI-8 applicability, AIGIS components; domain interdependencies; CFL-V validation rules |

---

## The One-Sentence Summary

> *"CDT-7 v2.0 classifies machine capability into seven distinct axes—Perception, Synthesis, Decision, Interaction, Adaptation, Observability, and Constraint—with three governing rules (asymmetric tiering, Observability never lags, Constraint sets the real ceiling), domain interdependencies, and explicit mapping to CTAM, CAM-5, RGI-8, AICA-5, AWOF, and CAD-7."*
