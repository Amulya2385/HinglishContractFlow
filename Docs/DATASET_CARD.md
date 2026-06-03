
# DATASET CARD — HinglishContractFlow

## Dataset Identification

**Dataset Name:** HinglishContractFlow

**Dataset Type:** Large-Scale Synthetic Legal Benchmark

**Domain:** Legal AI, Contract Intelligence, Arbitration Analytics, Code-Mixed Language Understanding

**Primary Language:** Hinglish (Hindi-English Code-Mixed Legal Discourse)

**Storage Format:** Apache Parquet (Snappy Compression)

**Dataset Size:** 595.85 MB

**Total Records:** 1,000,000

**Total Features:** 59

**States Represented:** 5

**Dispute Categories:** 6

**Statutory Frameworks:** 59

---

# Executive Summary

HinglishContractFlow is a large-scale benchmark dataset designed to advance research in legal reasoning, dispute resolution, arbitration intelligence, multilingual natural language processing, contract analytics, and code-mixed language understanding.

The benchmark focuses on disputes emerging from India's informal and semi-formal economic sectors, where contractual communication frequently combines Hindi expressions, regional vernacular speech patterns, and English legal terminology.

Unlike traditional legal datasets that focus primarily on formal contracts or judicial opinions, HinglishContractFlow models complete dispute lifecycles, including contractual ambiguity, negotiation trajectories, evidentiary strength, enforceability assessment, arbitration risk, procedural progression, and dispute outcomes.

The benchmark is specifically designed to support the development of intelligent legal systems capable of reasoning within multilingual, code-mixed, and procedurally complex environments.

---

# Motivation

Modern Legal AI systems are typically trained on formal English legal corpora.

However, a substantial portion of legal communication in emerging economies occurs through:

* Informal contractual arrangements
* Vernacular negotiations
* Oral amendments
* Regional legal interpretations
* Code-mixed legal discourse

Existing benchmarks rarely model:

* Contract ambiguity propagation
* Negotiation dynamics
* Arbitration processes
* Mediation trajectories
* Procedural stage transitions
* Multilingual legal communication

HinglishContractFlow addresses these gaps through a large-scale benchmark that integrates legal reasoning, dispute progression, arbitration analytics, and code-mixed language understanding.

---

# Geographic Coverage

The benchmark models disputes across five major Indian jurisdictions:

| State         | Coverage Focus                                 |
| ------------- | ---------------------------------------------- |
| Maharashtra   | Agricultural leasing, logistics, cold storage  |
| Punjab        | Agricultural contracts and machinery leasing   |
| Haryana       | Land-use agreements and logistics partnerships |
| Rajasthan     | Water-sharing and commercial rentals           |
| Uttar Pradesh | Commercial leasing and contractual disputes    |

The selected jurisdictions provide linguistic diversity, procedural variation, and heterogeneous dispute structures.

---

# Dispute Categories

The benchmark includes six dispute categories.

## Agricultural Lease

Disputes involving:

* Agricultural tenancy
* Land-use restrictions
* Crop-sharing arrangements
* Yield-related disagreements

---

## Commercial Rental

Disputes involving:

* Commercial property leasing
* Security deposit conflicts
* Notice-period disagreements
* Early termination disputes

---

## Cold Storage

Disputes involving:

* Agricultural storage agreements
* Damage liability
* Capacity allocation
* Delayed release of stored goods

---

## Water Sharing

Disputes involving:

* Irrigation access
* Water allocation rights
* Seasonal resource sharing
* Distribution disagreements

---

## Machinery Lease

Disputes involving:

* Agricultural equipment leasing
* Maintenance responsibility
* Damage liability
* Equipment-return compliance

---

## Logistics Partnership

Disputes involving:

* Freight agreements
* Distribution partnerships
* Delivery obligations
* Cost-sharing arrangements

---

# Legal Framework Coverage

The benchmark incorporates 59 statutory frameworks and legal reference structures.

Each record contains:

* Jurisdictional context
* Applicable statutory references
* Contract validity assessments
* Legal critic evaluations

Legal reasoning components are grounded within the dispute-specific statutory context associated with each record.

---

# Dataset Composition

## Total Records

```text
1,000,000
```

## Total Features

```text
59
```

## Dataset Size

```text
595.85 MB
```

## Storage Format

```text
Apache Parquet
```

## Compression

```text
Snappy
```

## Number of Parquet Files

```text
40
```

## Average Records per Chunk

```text
25,000
```

---

# Dataset Splits

| Split      | Records | Percentage |
| ---------- | ------- | ---------- |
| Train      | 800,000 | 80%        |
| Validation | 100,000 | 10%        |
| Test       | 100,000 | 10%        |

Split assignments are stored directly within the `split` column.

This design enables:

* Single-file loading
* Distributed processing
* Flexible benchmark partitioning
* Reproducible evaluation pipelines
# Dataset Schema Overview

The benchmark contains 59 features grouped into multiple semantic blocks.

## Identity and Metadata

These fields uniquely identify disputes and dataset partitions.

* dispute_id
* chunk_id
* record_index

---

## Jurisdiction and Context

These fields provide regional and legal context.

* state
* district_hub
* dispute_type
* applicable_statute
* legal_institution

---

## Temporal Features

These fields model contractual and procedural timelines.

* contract_start_date
* dispute_filing_date
* hearing_date
* contract_duration_days
* delay_days
* dispute_age_days
* limitation_risk_flag

---

## Financial Features

These variables model contractual economics.

* monthly_rent_inr
* contract_value_inr
* security_deposit_inr
* penalty_inr
* claimed_damages_inr

---

## Agricultural Features

These fields model land and productivity characteristics.

* land_area_acres
* crop_yield_qtl

---

## Documentary Evidence Features

These variables capture evidentiary support.

* has_written_agreement
* has_registered_deed
* has_witness_testimony
* legal_aid_utilized

---

## Legal Assessment Features

These fields quantify dispute quality and enforceability.

* evidence_strength_score
* ambiguity_score
* legal_score
* dispute_severity_score
* arbitration_risk_score
* settlement_probability

---

## Linguistic Features

These variables capture code-mixing behavior.

* linguistic_mix_ratio
* num_code_switch_events
* dialect_intensity_score
* regional_dialect

---

## Procedural Features

These variables model dispute progression.

* initial_stage
* final_stage
* num_stage_transitions
* stage_trajectory

---

## Outcome Features

These variables represent dispute resolution outcomes.

* validity_label
* final_outcome
* difficulty_tier

---

## Explainability Features

These fields support interpretable legal reasoning.

* critic_finding
* critic_confidence

---

## Structured Trace Features

These fields contain rich procedural telemetry.

* negotiation_trace_json
* transaction_manifest_json

---

## Latent Variables

Internal latent variables used during generation.

* latent_economic_scale
* latent_legal_formality
* latent_dispute_intensity
* latent_ambiguity_level
* latent_settlement_proclivity

---

## Statistical Noise Features

Generation diagnostics.

* colored_noise_economic
* colored_noise_temporal

---

# Generation Methodology Summary

The benchmark is produced through a structured simulation pipeline designed to generate realistic legal disputes while preserving statistical diversity and procedural consistency.

Core components include:

### Correlated Feature Generation

Feature dependencies are introduced through correlation-aware sampling procedures.

This enables realistic relationships between:

* evidence strength
* legal quality
* ambiguity
* settlement probability
* arbitration risk

---

### Contract Simulation

Each record is instantiated through a synthetic contract generation framework that models:

* contractual value
* lease duration
* deposits
* penalties
* disputed damages

---

### Ambiguity Injection

Selected contractual clauses are deliberately assigned ambiguity levels.

Examples include:

* force majeure clauses
* escalation mechanisms
* payment schedules
* oral amendments
* termination conditions

---

### Procedural Simulation

Each dispute progresses through multiple procedural stages.

Example trajectory:

```text
Draft_Circulated
→ Clause_Negotiation
→ Counter_Offer_Filed
→ Mediation_Requested
→ Terminated
```

---

### Legal Critic Evaluation

Every dispute is processed through a legal critic framework that evaluates:

* enforceability
* evidentiary sufficiency
* statutory consistency
* procedural compliance

The resulting reasoning is stored within:

```text
critic_finding
```

---

### Outcome Assignment

Dispute outcomes are generated using structured legal and procedural signals.

Possible outcomes include:

* Mutual_Settlement
* Mediation_Pending
* Lok_Adalat_Referral
* Judicial_Referral_District_Court

Outcome generation is conditioned upon:

* evidence strength
* ambiguity
* legal score
* procedural trajectory

---

# Intended Research Applications

The benchmark supports a wide range of research tasks.

## Legal AI

* Legal reasoning
* Contract intelligence
* Statute retrieval
* Case assessment

---

## Natural Language Processing

* Code-mixed language understanding
* Legal text generation
* Explanation generation
* Dialogue modeling

---

## Predictive Analytics

* Outcome prediction
* Settlement forecasting
* Arbitration risk estimation
* Validity classification

---

## Agentic Systems

* Autonomous mediation
* Legal assistants
* Negotiation agents
* Multi-agent dispute resolution

# Ethical Considerations

HinglishContractFlow is a synthetic benchmark intended exclusively for research, benchmarking, and educational purposes.

The dataset does not contain:

* Real litigants
* Real contracts
* Real court proceedings
* Personally identifiable information
* Sensitive legal records

Although statutory references and procedural structures are modeled to resemble realistic legal environments, the dataset should not be interpreted as legal authority.

Users should not deploy models trained on this dataset as substitutes for professional legal advice.

---

# Known Limitations

Several limitations should be considered when interpreting benchmark results.

## Synthetic Generation

The dataset is procedurally generated and therefore may not capture all nuances of real-world legal disputes.

---

## Geographic Scope

The benchmark currently models five Indian states.

Future releases may expand jurisdictional coverage.

---

## Procedural Simplification

Certain legal procedures are abstracted to maintain tractable simulation complexity.

---

## Limited Dispute Categories

Only six dispute categories are currently represented.

Many important legal domains remain outside scope.

Examples include:

* Criminal law
* Constitutional law
* Intellectual property
* Taxation
* Labor disputes

---

## No Judicial Authority

The benchmark is not intended to model actual judicial decision making.

It should not be used for legal decision support.

---

# Validation Summary

The benchmark generation pipeline includes automated validation procedures.

## Dataset Integrity Checks

* Record count verification
* Schema compliance validation
* Null-value inspection
* Data-type consistency checks

---

## Statistical Validation

Validation includes:

* Distribution consistency
* Correlation inspection
* Score-range verification
* Split-balance validation

---

## Procedural Validation

Checks include:

* Stage trajectory integrity
* Outcome consistency
* Validity label verification
* Negotiation trace completeness

---

## Split Validation

The following split distribution is verified:

| Split      | Records |
| ---------- | ------- |
| Train      | 800,000 |
| Validation | 100,000 |
| Test       | 100,000 |

---

# Related Documentation

The following documents provide additional details.

| Document           | Purpose                                               |
| ------------------ | ----------------------------------------------------- |
| DATA_DICTIONARY.md | Complete feature-level schema documentation           |
| METHODOLOGY.md     | Detailed generation pipeline and modeling assumptions |
| BENCHMARK_TASKS.md | Benchmark tasks and evaluation settings               |
| README.md          | Repository overview and usage instructions            |

---

# Citation

```bibtex
@dataset{hinglishcontractflow2026,
  title={HinglishContractFlow: A Large-Scale Benchmark for Vernacular Contract Intelligence, Dispute Resolution, and Code-Mixed Legal Reasoning},
  year={2026}
}
```

---

# License

Released for research, benchmarking, and educational purposes.

Users are encouraged to cite the benchmark when reporting experimental results.

Refer to the repository LICENSE file for usage terms.

---

# Contact

For benchmark-related questions, issues, or improvements, please use the repository issue tracker and accompanying documentation.

---

End of Dataset Card.


