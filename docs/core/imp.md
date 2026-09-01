# IMP v2.0 — Institutional Memory Protocol

**Status:** Built — v2.0 (Reconciliation with EAF, AICA-5, ICC-8, AWOF, CEF, ILTP, CGF, ERDP, DEP, and CAD-7)  
**Type:** Memory Architecture Instrument  
**Parent Stack:** 19 Integrated Primitive Layer  
**Version:** 2.0 — Supersedes IMP v1.0

---

## PREAMBLE

The Institutional Memory Protocol (IMP) governs the creation, structure, provenance, storage, retrieval, and retirement of all institutional state objects produced through engagement with clients, internal operations, and framework evolution. It answers: *How does 19 Integrated remember itself, govern its own outputs, and compound institutional intelligence over time?*

IMP is the institutional state system through which 19 Integrated remembers itself, governs its own outputs, and compounds institutional intelligence over time. It is not a knowledge base, a document archive, or a logging system. It is the first operational substrate — without IMP, no other system in the 19 Integrated stack can be tested, validated, or improved.

**The core insight:** Memory is governance. What an institution remembers — and how it remembers it — determines what it can learn, correct, and improve. IMP transforms institutional memory from an incidental byproduct of operations into a governed constitutional asset.

---

## SECTION 1: PURPOSE AND SCOPE

### Purpose

IMP ensures that:

1. **Memory is structured** — All institutional outputs exist as typed, structured objects with defined fields  
2. **Provenance is complete** — Every object carries a complete provenance chain  
3. **Temporal layering is maintained** — Current, historical, and revoked truth states are distinguished  
4. **Governance version binding is preserved** — Objects are bound to the framework version active at creation  
5. **Retrieval is governance-oriented** — Retrieval is constraint reconstruction, precedent matching, lineage tracing, and outcome similarity mapping  
6. **EAF supremacy is enforced** — IMP stores only what EAF permits

### Scope

| In Scope | Out of Scope |
| :---- | :---- |
| Six canonical object types (ECO, DRO, GAO, CRO, OEO, XOO) | Knowledge bases or document archives |
| Provenance chain standard | General logging systems |
| Temporal layering (Current/Historical/Revoked) | Ad-hoc storage |
| Governance version binding | Unstructured data storage |
| Retrieval semantics (4 modes) | Search engines |
| EAF-IMP interface | Data privacy policies (informed by EAF) |

### Governing Relationships

| Instrument | Relationship to IMP |
| :---- | :---- |
| **EAF** | Governs IMP — defines what may be stored, inferred, and retained |
| **AWOF** | Action layer — governed operations produce IMP objects |
| **AICA-5** | AI accountability — AI-origin objects carry AICA-5 provenance flags |
| **ICC-8** | Constitutional ceiling — IMP cannot persist objects that violate ICC-8 invariants |
| **CEF** | Engagement layer — defines the engagement lifecycle that IMP records |
| **ILTP** | IP governance — IP objects stored under ILTP classification |
| **CGF** | Certification governance — certification objects stored under CGF |
| **ERDP** | External reporting — disclosure objects stored under ERDP |
| **DEP** | Doctrine evolution — DEP proceedings recorded as DROs and GAOs |

---

## SECTION 2: FOUNDATIONAL PRINCIPLES

| \# | Principle | Description |
| :---- | :---- | :---- |
| **P1** | **Structured Objects Only** | No free text as primary storage. Every institutional output exists as a typed, structured object with defined fields. |
| **P2** | **Provenance Integrity** | Every object carries a complete provenance chain. An object without a complete provenance chain is invalid. |
| **P3** | **Temporal Layering** | IMP distinguishes three truth states: current truth (active state), historical truth (past states), and revoked truth (superseded decisions). No object is deleted. |
| **P4** | **Governance Version Binding** | Every object is bound to the version of the governing framework active at the time of its creation. Subsequent framework updates do not retroactively alter historical objects. |
| **P5** | **Retrieval as Governance** | Memory retrieval is not search. It is constraint reconstruction, precedent matching, governance lineage tracing, and outcome similarity mapping. |
| **P6** | **EAF Supremacy** | IMP stores only what EAF permits. Where EAF is silent, IMP defaults to minimum necessary persistence. Where EAF prohibits, IMP does not store regardless of operational convenience. |

---

## SECTION 3: CANONICAL OBJECT TYPES — OVERVIEW

IMP recognizes six canonical object types. Every engagement produces instances of some or all of these types. No other primary storage object types are permitted without formal amendment to this protocol.

| Object | Name | Purpose | Created | Fields |
| :---- | :---- | :---- | :---- | :---- |
| **ECO** | Engagement Context Object | Records full context of a client engagement | At intake initiation; updated at each phase transition | 13 fields |
| **DRO** | Decision Record Object | Records every consequential decision | At each decision point | 16 fields |
| **GAO** | Governance Artifact Object | Records every institutional artifact produced | At draft; updated at revision; finalized at issuance | 17 fields |
| **CRO** | Constraint Record Object | Records all constraints that bounded decisions | During intake and discovery; updated when new constraints identified | 11 fields |
| **OEO** | Outcome Evidence Object | Records implementation outcomes and real-world evidence | Post-issuance; may be created at multiple points | 12 fields |
| **XOO** | Exception/Override Object | Records every instance where a standard governance rule was overridden | Immediately upon any exception or override being invoked | 12 fields |

---

## SECTION 4: ECO — ENGAGEMENT CONTEXT OBJECT

### Purpose

Records the full context of a client engagement at inception and updates through closure.

### Fields

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `eco_id` | String | Unique identifier. Format: `ECO-[YYYY]-[SEQ]` |
| 2 | `engagement_type` | Enum | governance\_charter / maturity\_assessment / workforce\_design / policy\_review / institutional\_design / other |
| 3 | `client_id` | String | Anonymized or identified per EAF consent tier |
| 4 | `intake_timestamp` | ISO 8601 | Date and time of first AI contact |
| 5 | `trust_tier` | Integer (1-5) | EAF trust tier active at engagement open |
| 6 | `frameworks_applicable` | Array | Framework identifiers determined at intake (e.g., AICA-5 v2.0, ICC-8 v2.0) |
| 7 | `governing_framework_versions` | Object | Key-value map of framework ID to version string active at engagement open |
| 8 | `constraint_class` | Array | Enum: legal / ai\_risk / org\_capacity / time / capital / regulatory |
| 9 | `domain` | Array | Enum: ai\_deployment / org\_design / compliance / ip / workforce / institutional\_architecture |
| 10 | `risk_level` | Enum | low / moderate / elevated / critical / existential |
| 11 | `han_required` | Boolean | Whether HAN review is triggered for this engagement |
| 12 | `han_trigger_basis` | String | Reference to EAF rule that triggered HAN requirement |
| 13 | `status` | Enum | active / completed / suspended / terminated |
| 14 | `closure_timestamp` | ISO 8601 | Date and time of engagement closure (null if active) |
| 15 | `linked_objects` | Array | IDs of all DRO, GAO, CRO, OEO, XOO objects produced |

### Creation Rules

| Rule | Description |
| :---- | :---- |
| **Intake Initiation** | ECO is created at intake initiation |
| **Phase Updates** | ECO is updated at each phase transition (CEF Stages 1-6) |
| **Trust Tier Binding** | ECO captures trust tier at engagement open; changes logged as DRO |
| **Framework Version Binding** | ECO captures framework versions active at engagement open |

---

## SECTION 5: DRO — DECISION RECORD OBJECT

### Purpose

Records every consequential decision made during an engagement — by AI, by human, or jointly.

### Fields

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `dro_id` | String | Format: `DRO-[ECO_ID]-[SEQ]` |
| 2 | `eco_id` | String | Parent engagement reference |
| 3 | `decision_type` | Enum | framework\_selection / scope\_determination / risk\_classification / recommendation / escalation / exception |
| 4 | `decision_timestamp` | ISO 8601 | When decision was made |
| 5 | `decision_origin` | Enum | ai / human / hybrid |
| 6 | `ai_model_ref` | String | Model identifier if AI-origin or hybrid |
| 7 | `human_actor_ref` | String | HAN identifier if human-origin or hybrid (null if AI-only) |
| 8 | `plan_id` | String | Plan identifier if part of multi-step plan (v2.0) |
| 9 | `plan_objective` | String | Plan objective if part of multi-step plan (v2.0) |
| 10 | `step_number` | Integer | Step number in plan (v2.0) |
| 11 | `total_steps` | Integer | Total steps in plan (v2.0) |
| 12 | `planning_trace_hash` | String | Hash of planning trace (v2.0) |
| 13 | `framework_source` | Array | Framework(s) that governed this decision |
| 14 | `governing_framework_versions` | Object | Version map at time of decision |
| 15 | `justification_trace` | String | Structured reasoning chain: premise → framework rule → conclusion |
| 16 | `han_review_flag` | Boolean | Whether HAN reviewed this decision |
| 17 | `han_review_timestamp` | ISO 8601 | Timestamp of HAN review (null if not reviewed) |
| 18 | `han_outcome` | Enum | approved / modified / rejected / null |
| 19 | `client_acknowledgment_state` | Enum | pending / acknowledged / disputed / null |
| 20 | `inter_agent_communication` | Boolean | Whether this decision involved inter-agent communication (v2.0) |
| 21 | `sender_agent_id` | String | Sending agent ID if inter-agent communication (v2.0) |
| 22 | `receiver_agent_id` | String | Receiving agent ID if inter-agent communication (v2.0) |
| 23 | `communication_type` | String | Type of inter-agent communication (v2.0) |
| 24 | `superseded_by` | String | DRO ID of superseding decision (null if current) |
| 25 | `truth_state` | Enum | current / historical / revoked |

### Creation Rules

| Rule | Description |
| :---- | :---- |
| **Decision Point** | DRO created at each decision point that affects deliverable content, framework application, or client recommendation |
| **Plan Tracking** | If decision is part of a multi-step plan, plan fields must be populated (v2.0) |
| **Inter-Agent Communication** | If decision involves inter-agent communication, communication fields must be populated (v2.0) |
| **HAN Review** | HAN review flag set per EAF HAN Trigger Register |
| **Truth State** | Default: current; transitions to historical when superseded |

---

## SECTION 6: GAO — GOVERNANCE ARTIFACT OBJECT

### Purpose

Records every institutional artifact produced for a client — policies, charters, frameworks, assessments, operating models.

### Fields

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `gao_id` | String | Format: `GAO-[ECO_ID]-[SEQ]` |
| 2 | `eco_id` | String | Parent engagement reference |
| 3 | `artifact_type` | Enum | governance\_charter / policy\_instrument / assessment\_report / operating\_model / delegation\_structure / risk\_register / maturity\_map / institutional\_blueprint |
| 4 | `artifact_title` | String | Formal title of artifact |
| 5 | `version` | String | Semantic version (e.g., v1.0, v1.1) |
| 6 | `draft_origin` | Enum | ai / human / hybrid |
| 7 | `governing_frameworks` | Array | Frameworks applied in construction |
| 8 | `governing_framework_versions` | Object | Version map at time of draft |
| 9 | `dro_references` | Array | Decision Record IDs that produced this artifact |
| 10 | `han_review_flag` | Boolean | Whether HAN reviewed before issuance |
| 11 | `han_review_timestamp` | ISO 8601 | Timestamp of HAN review |
| 12 | `issuance_timestamp` | ISO 8601 | Timestamp of client delivery |
| 13 | `client_acknowledgment_state` | Enum | pending / acknowledged / disputed |
| 14 | `artifact_status` | Enum | draft / issued / superseded / revoked |
| 15 | `superseded_by` | String | GAO ID of superseding artifact (null if current) |
| 16 | `content_hash` | String | SHA-256 hash of artifact content at issuance for integrity verification |
| 17 | `truth_state` | Enum | current / historical / revoked |
| 18 | `regulatory_framework` | String | Regulatory framework applicable to this artifact (v2.0) |
| 19 | `supply_chain_reference` | String | Reference to supply chain provenance (v2.0) |
| 20 | `model_provenance_record` | String | Reference to model provenance if AI-generated (v2.0) |
| 21 | `mcp_server_reference` | String | Reference to MCP server used in generation (v2.0) |

### Creation Rules

| Rule | Description |
| :---- | :---- |
| **Draft Creation** | GAO created when a deliverable artifact is drafted |
| **Revision** | GAO updated at each revision |
| **Finalization** | GAO finalized at issuance |
| **HAN Review** | HAN review required per EAF HAN Trigger Register |
| **Supply Chain** | Supply chain provenance recorded if artifact depends on external models/data (v2.0) |
| **MCP Server** | MCP server referenced if used in generation (v2.0) |

---

## SECTION 7: CRO — CONSTRAINT RECORD OBJECT

### Purpose

Records all constraints — legal, regulatory, operational, constitutional — that bounded decisions and artifacts in an engagement.

### Fields

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `cro_id` | String | Format: `CRO-[ECO_ID]-[SEQ]` |
| 2 | `eco_id` | String | Parent engagement reference |
| 3 | `constraint_type` | Enum | legal / regulatory / constitutional / operational / capital / temporal / client\_imposed / meta\_duration / meta\_count / meta\_scope (v2.0) |
| 4 | `constraint_source` | String | Origin of constraint (e.g., regulation name, ICC-8 invariant reference, client instruction) |
| 5 | `constraint_description` | String | Structured statement of the constraint |
| 6 | `binding_scope` | Enum | engagement\_wide / artifact\_specific / decision\_specific |
| 7 | `affected_objects` | Array | IDs of DRO or GAO objects this constraint applies to |
| 8 | `governing_framework_versions` | Object | Version map at time of constraint identification |
| 9 | `jurisdiction` | String | Applicable jurisdiction (v2.0) |
| 10 | `conflict_resolution` | Enum | stricter / client\_choice / han\_escalation (v2.0) |
| 11 | `meta_constraint_value` | String | Value of meta-constraint (e.g., "5 decisions", "24 hours") (v2.0) |
| 12 | `constraint_status` | Enum | active / lifted / superseded |
| 13 | `lift_basis` | String | Justification if constraint was lifted (null if active) |
| 14 | `truth_state` | Enum | current / historical / revoked |

### Creation Rules

| Rule | Description |
| :---- | :---- |
| **Intake Identification** | CRO created during intake and discovery |
| **Constraint Updates** | Updated when new constraints are identified |
| **Meta-Constraints** | Meta-constraints (duration, count, scope) stored as constraint\_type (v2.0) |
| **Jurisdiction** | Jurisdiction recorded if applicable (v2.0) |
| **Conflict Resolution** | Conflict resolution rule recorded if jurisdiction conflict (v2.0) |

---

## SECTION 8: OEO — OUTCOME EVIDENCE OBJECT

### Purpose

Records implementation outcomes, client feedback, and real-world evidence following artifact issuance. This is the compounding layer — the substrate for precedent matching and framework efficacy assessment.

### Fields

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `oeo_id` | String | Format: `OEO-[ECO_ID]-[SEQ]` |
| 2 | `eco_id` | String | Parent engagement reference |
| 3 | `gao_reference` | String | GAO ID of the artifact this outcome relates to |
| 4 | `observation_timestamp` | ISO 8601 | When outcome was observed or reported |
| 5 | `observation_origin` | Enum | client\_reported / ai\_monitored / han\_assessed / third\_party |
| 6 | `outcome_type` | Enum | implementation\_success / partial\_implementation / implementation\_failure / governance\_drift / maturity\_improvement / compliance\_event / unintended\_consequence / bias\_audit / hallucination / public\_contestation (v2.0) |
| 7 | `outcome_description` | String | Structured description of observed outcome |
| 8 | `drift_detected` | Boolean | Whether governance drift was detected |
| 9 | `drift_description` | String | Nature of drift if detected (null if no drift) |
| 10 | `maturity_delta` | Object | Change in governance maturity scores if measured |
| 11 | `framework_efficacy_signal` | Enum | positive / neutral / negative / inconclusive |
| 12 | `framework_source` | Array | Frameworks whose efficacy this outcome evidences |
| 13 | `governing_framework_versions` | Object | Version map at time of original artifact issuance |
| 14 | `precedent_applicability` | Enum | high / moderate / low |
| 15 | `precedent_domain_tags` | Array | Domain tags for precedent retrieval |

### Creation Rules

| Rule | Description |
| :---- | :---- |
| **Post-Issuance Creation** | OEO created post-issuance; may be created at multiple points |
| **Bias Audit** | AOBA findings logged as OEO with outcome\_type "bias\_audit" (v2.0) |
| **Hallucination** | Hallucination detection logged as OEO with outcome\_type "hallucination" (v2.0) |
| **Public Contestation** | CEN-7 public contestation logged as OEO with outcome\_type "public\_contestation" (v2.0) |
| **Pattern Detection** | OEOs are used for pattern detection and precedent matching |

---

## SECTION 9: XOO — EXCEPTION/OVERRIDE OBJECT

### Purpose

Records every instance where a standard governance rule, framework requirement, or protocol step was overridden, waived, or excepted. XOOs are mandatory — exceptions that are not recorded are constitutional violations under ICC-8.

### Fields

| \# | Field | Type | Description |
| :---- | :---- | :---- | :---- |
| 1 | `xoo_id` | String | Format: `XOO-[ECO_ID]-[SEQ]` |
| 2 | `eco_id` | String | Parent engagement reference |
| 3 | `exception_type` | Enum | han\_review\_waived / framework\_rule\_excepted / protocol\_step\_skipped / constraint\_overridden / trust\_tier\_elevated / output\_failure / scope\_drift / alignment\_drift / coalition\_breach / security\_breach / i9\_catastrophic\_risk\_violation / constitutional\_suspension (v2.0) |
| 4 | `excepted_rule_reference` | String | Specific rule, invariant, or protocol step that was excepted |
| 5 | `exception_basis` | String | Structured justification for the exception |
| 6 | `exception_authority` | Enum | han / eaf\_rule / client\_request |
| 7 | `exception_timestamp` | ISO 8601 | When exception was invoked |
| 8 | `han_authorization` | Boolean | Whether HAN explicitly authorized this exception |
| 9 | `han_authorization_timestamp` | ISO 8601 | Timestamp of HAN authorization (null if not required) |
| 10 | `risk_assessment` | Enum | low / moderate / elevated / critical |
| 11 | `affected_objects` | Array | IDs of objects affected by this exception |
| 12 | `governing_framework_versions` | Object | Version map at time of exception |
| 13 | `exception_status` | Enum | active / resolved / escalated |

### Creation Rules

| Rule | Description |
| :---- | :---- |
| **Immediate Creation** | XOO created immediately upon any exception or override being invoked |
| **Exception Types** | All exception types defined; new types require DEP amendment |
| **I9 Violation** | I9 Catastrophic Risk violations logged as XOO with exception\_type "i9\_catastrophic\_risk\_violation" (v2.0) |
| **Constitutional Suspension** | Constitutional Suspension logged as XOO with exception\_type "constitutional\_suspension" (v2.0) |
| **HAN Authorization** | HAN authorization required for all exceptions unless EAF rule explicitly permits otherwise |

---

## SECTION 10: PROVENANCE CHAIN STANDARD

### Required Elements

Every object produced under IMP carries a complete provenance chain. An object without a complete provenance chain is invalid.

| \# | Element | Description |
| :---- | :---- | :---- |
| 1 | **Origin** | Was this object produced by AI, by a human (HAN), or through a hybrid process? If AI, which model? If human, which HAN identifier? |
| 2 | **Framework Source** | Which frameworks governed the production of this object? Listed by framework ID. |
| 3 | **Governance Version Binding** | What was the active version of each governing framework at the time this object was created? This binding is immutable. |
| 4 | **Justification Trace** | What reasoning chain produced this object? Structured as: premise → applicable framework rule → conclusion. |
| 5 | **HAN Intervention Flag** | Was this object reviewed, modified, or authorized by a Human Accountability Node? If yes, the HAN identifier, review timestamp, and outcome are recorded. |
| 6 | **Client Acknowledgment State** | Has the client acknowledged, disputed, or not yet responded to this object? |

### Validation Rules

| Rule | Description |
| :---- | :---- |
| **Complete Provenance** | Every object must have all 6 provenance elements. |
| **Immutable Version Binding** | Governance version binding is immutable. Subsequent framework updates do not alter this record. |
| **No Orphaned Objects** | Every object must trace to an accountable origin. |

---

## SECTION 11: TEMPORAL LAYERING

### Truth States

IMP maintains three truth states. No object transitions out of the record. Objects transition between truth states.

| State | Definition | Transition |
| :---- | :---- | :---- |
| **Current Truth** | The active, operative state of an object. Only one version may hold current truth status at any time. | New version supersedes prior → prior moves to Historical |
| **Historical Truth** | A prior state that has been superseded by a newer version. Fully readable and auditable. | Formal revocation → moves to Revoked |
| **Revoked Truth** | A state that was active but has been formally withdrawn, invalidated, or determined to be in error. Carries revocation basis record. | — |

### Transition Rules

| Rule | Description |
| :---- | :---- |
| **No Deletion** | No object is deleted from IMP. The record is permanent. |
| **Supersession** | A new version of an object supersedes the prior version. Prior version moves to Historical Truth. |
| **Revocation** | A formal revocation moves an object to Revoked Truth and records the revocation basis. |
| **Audit Access** | All truth states are accessible for audit purposes. |

---

## SECTION 12: RETRIEVAL SEMANTICS

IMP retrieval is governance-oriented, not search-oriented. Four retrieval modes are defined:

| Mode | Purpose | Output |
| :---- | :---- | :---- |
| **Constraint Reconstruction** | Given a current engagement context, reconstruct all constraints that apply based on ECO parameters and linked CROs | Constraint map for the current engagement |
| **Precedent Matching** | Given a current engagement type, domain, and risk level, retrieve OEOs from prior engagements with matching characteristics | Ranked precedent set with applicability scores |
| **Governance Lineage Tracing** | Given a GAO ID, trace the complete chain of DROs, CROs, and XOOs that produced it, back to the originating ECO | Full governance lineage map |
| **Outcome Similarity Mapping** | Given a current engagement context, retrieve prior OEOs where similar frameworks were applied to similar constraint classes | Pattern set for framework efficacy assessment |

### Retrieval Rules

| Rule | Description |
| :---- | :---- |
| **Governance Purpose** | Retrieval is for governance purposes, not general search |
| **EAF Compliance** | Retrieval respects EAF trust tiers and consent boundaries |
| **Audit Logging** | All retrievals are logged for audit purposes |
| **Version Awareness** | Retrieval considers governance version binding |

---

## SECTION 13: ENGAGEMENT LIFECYCLE — OBJECT PRODUCTION MAP

The following maps a standard AI Governance Charter engagement to IMP object production. This is the canonical reference sequence.

INTAKE (CEF Stage 1\)  
└── ECO created (engagement\_type: governance\_charter)  
└── CRO(s) created (initial constraint identification)

DISCOVERY (CEF Stage 2\)  
└── ECO updated (frameworks\_applicable, trust\_tier confirmed)  
└── CRO(s) updated or added (additional constraints identified)  
└── DRO created (framework\_selection decision)  
└── DRO created (risk\_classification decision)

DRAFTING (CEF Stage 3-4)  
└── GAO created v0.1 (artifact\_status: draft)  
└── DRO created (recommendation decisions embedded in artifact)

HAN REVIEW (if triggered)  
└── DRO updated (han\_review\_flag: true, han\_outcome recorded)  
└── GAO updated (han\_review\_flag: true)  
└── XOO created IF any exception invoked during review

ISSUANCE (CEF Stage 5\)  
└── GAO finalized (artifact\_status: issued, issuance\_timestamp, content\_hash)  
└── ECO updated (status: completed, closure\_timestamp)

POST-ISSUANCE (CEF Stage 6\)  
└── OEO created (as implementation evidence accumulates)  
└── OEO updated (as additional outcomes observed)  
└── ECO updated (linked\_objects includes all OEOs)

---

## SECTION 14: AMENDMENT PROTOCOL

IMP may be amended only through the Doctrine Extension Protocol (DEP). DEP governs all IMP amendments.

| Requirement | Description |
| :---- | :---- |
| **Structural Gap** | Documented structural gap or failure mode that the current specification cannot address |
| **HAN Review** | HAN review and approval |
| **Version Increment** | Minor amendments: v1.0 → v1.1; Structural changes: v1.0 → v2.0 |
| **Active ECO Notation** | All active ECOs carry a notation that they were opened under a prior IMP version |
| **CFL-V Validation** | All IMP amendments must pass CFL-V validation |

---

## SECTION 15: RELATIONSHIP TO OTHER INSTRUMENTS

| Instrument | Relationship to IMP |
| :---- | :---- |
| **EAF** | Governs IMP — defines what may be stored, inferred, and retained |
| **AWOF** | Action layer — governed operations produce IMP objects |
| **AICA-5** | AI accountability — AI-origin objects carry AICA-5 provenance flags |
| **ICC-8** | Constitutional ceiling — IMP cannot persist objects that violate ICC-8 invariants |
| **CEF** | Engagement layer — defines the engagement lifecycle that IMP records |
| **ILTP** | IP governance — IP objects stored under ILTP classification |
| **CGF** | Certification governance — certification objects stored under CGF |
| **ERDP** | External reporting — disclosure objects stored under ERDP |
| **DEP** | Doctrine evolution — DEP proceedings recorded as DROs and GAOs |

---

## SECTION 16: CFL-V VALIDATION RULES

| Rule | Description |
| :---- | :---- |
| **Object Type Completeness** | All 6 canonical object types are defined with complete field sets |
| **Provenance Integrity** | Every object must carry a complete provenance chain |
| **Temporal Layering** | All 3 truth states are supported with transition rules |
| **EAF Compliance** | IMP stores only what EAF permits |
| **Retrieval Semantics** | All 4 retrieval modes are defined |
| **Amendment Protocol** | IMP amendments require DEP process |
| **Version Binding** | Every object is bound to the governing framework version active at creation |

---

## VERSION HISTORY

| Version | Change |
| :---- | :---- |
| IMP v1.0 | Initial specification — 6 canonical object types, provenance chain standard, temporal layering, retrieval semantics |
| IMP v2.0 | Complete rebuild — reconciliation with EAF, AICA-5, ICC-8, AWOF, CEF, ILTP, CGF, ERDP, DEP, and CAD-7; expanded object fields (Plan Tracking, Inter-Agent Communication, Meta-Constraints, Jurisdiction, Supply Chain, MCP Server); new outcome types (bias\_audit, hallucination, public\_contestation); new exception types (i9\_catastrophic\_risk\_violation, constitutional\_suspension); CFL-V validation rules |

---

## The One-Sentence Summary

> *"IMP v2.0 governs the creation, structure, provenance, storage, retrieval, and retirement of all institutional state objects across 6 canonical object types — ECO, DRO, GAO, CRO, OEO, XOO — with complete provenance chains, temporal layering (Current/Historical/Revoked), governance version binding, 4 retrieval modes (Constraint Reconstruction, Precedent Matching, Governance Lineage Tracing, Outcome Similarity Mapping), and EAF supremacy, ensuring that 19 Integrated remembers itself, governs its own outputs, and compounds institutional intelligence over time under ICC-8 constitutional constraints."*
