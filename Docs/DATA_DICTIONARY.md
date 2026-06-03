
# DATA DICTIONARY — HinglishContractFlow

## Overview

This document provides a complete schema reference for HinglishContractFlow.

The benchmark contains 59 features spanning identity, jurisdiction, finance, legal reasoning, procedural progression, linguistic behavior, dispute outcomes, and latent simulation variables.

---

# Feature Reference

| #  | Column                 | Type        | Description                                               |
| -- | ---------------------- | ----------- | --------------------------------------------------------- |
| 1  | dispute_id             | string      | Unique identifier assigned to each dispute record         |
| 2  | chunk_id               | integer     | Generation chunk identifier used during parquet streaming |
| 3  | record_index           | integer     | Record index within generation sequence                   |
| 4  | state                  | categorical | State jurisdiction associated with the dispute            |
| 5  | district_hub           | categorical | Regional district or operational hub                      |
| 6  | dispute_type           | categorical | Dispute category associated with the contractual conflict |
| 7  | applicable_statute     | string      | Statutory framework governing the dispute                 |
| 8  | complainant_name       | string      | Synthetic complainant identifier                          |
| 9  | respondent_name        | string      | Synthetic respondent identifier                           |
| 10 | legal_institution      | categorical | Legal body or dispute-resolution institution              |
| 11 | contract_start_date    | date        | Contract commencement date                                |
| 12 | dispute_filing_date    | date        | Date on which dispute was formally initiated              |
| 13 | hearing_date           | date        | Scheduled hearing or mediation date                       |
| 14 | contract_duration_days | integer     | Duration of contract in days                              |
| 15 | delay_days             | integer     | Delay observed relative to contractual expectations       |
| 16 | dispute_age_days       | integer     | Age of dispute in days                                    |
| 17 | limitation_risk_flag   | binary      | Indicates potential statutory limitation concerns         |
| 18 | monthly_rent_inr       | numeric     | Monthly contractual payment amount in Indian Rupees       |
| 19 | contract_value_inr     | numeric     | Total estimated contract value                            |
| 20 | security_deposit_inr   | numeric     | Security deposit associated with the agreement            |

---

# Feature Notes (1–20)

### Identity Features

Columns 1–3 provide unique identification and generation metadata.

These variables support:

* Record traceability
* Chunk-level processing
* Distributed storage

---

### Jurisdiction Features

Columns 4–7 define the legal and geographic context.

These variables are critical for:

* Statute retrieval
* Jurisdiction-aware reasoning
* Regional legal analysis

---

### Participant Features

Columns 8–9 represent synthetic legal actors.

These fields do not correspond to real individuals.

---

### Procedural Context

Column 10 specifies the institutional context under which the dispute proceeds.

Examples include:

* Mediation bodies
* Arbitration forums
* Local dispute-resolution institutions

---

### Temporal Features

Columns 11–17 model dispute timing and procedural progression.

These variables support:

* Delay analysis
* Limitation risk modeling
* Temporal forecasting

---

### Financial Features

Columns 18–20 capture core economic characteristics of the contract.

These variables frequently influence:

* Legal validity
* Settlement probability
* Arbitration risk
* Claimed damages
| #  | Column                  | Type        | Description                                                    |
| -- | ----------------------- | ----------- | -------------------------------------------------------------- |
| 21 | penalty_inr             | numeric     | Contractual penalty amount applicable under dispute conditions |
| 22 | claimed_damages_inr     | numeric     | Monetary damages claimed by the complainant                    |
| 23 | land_area_acres         | numeric     | Agricultural land area associated with the dispute             |
| 24 | crop_yield_qtl          | numeric     | Crop yield estimate in quintals                                |
| 25 | has_written_agreement   | binary      | Indicates presence of a written agreement                      |
| 26 | has_registered_deed     | binary      | Indicates whether the agreement was formally registered        |
| 27 | has_witness_testimony   | binary      | Indicates witness support for claims                           |
| 28 | legal_aid_utilized      | binary      | Indicates use of legal aid services                            |
| 29 | evidence_strength_score | numeric     | Quantifies evidentiary strength supporting claims              |
| 30 | ambiguity_score         | numeric     | Measures contractual ambiguity level                           |
| 31 | legal_score             | numeric     | Aggregate legal quality and enforceability score               |
| 32 | dispute_severity_score  | numeric     | Measures overall severity of dispute                           |
| 33 | arbitration_risk_score  | numeric     | Estimated risk of escalation to arbitration or litigation      |
| 34 | settlement_probability  | numeric     | Estimated likelihood of settlement                             |
| 35 | linguistic_mix_ratio    | numeric     | Degree of Hinglish code-mixing present in discourse            |
| 36 | num_code_switch_events  | integer     | Number of code-switching events detected                       |
| 37 | dialect_intensity_score | numeric     | Strength of regional dialect influence                         |
| 38 | regional_dialect        | categorical | Dominant regional dialect category                             |
| 39 | initial_stage           | categorical | Initial procedural stage of dispute                            |
| 40 | final_stage             | categorical | Final procedural stage reached by dispute                      |

---

# Feature Notes (21–40)

### Financial Escalation Features

Columns 21–22 quantify monetary consequences arising from contractual disagreements.

These variables are important for:

* Damages estimation
* Outcome prediction
* Settlement forecasting

---

### Agricultural Context Features

Columns 23–24 provide domain-specific information for agricultural disputes.

These features support:

* Land-use analysis
* Productivity assessment
* Resource conflict modeling

---

### Documentary Evidence Features

Columns 25–28 capture legal documentation quality.

Higher documentary support generally correlates with:

* Stronger legal positions
* Lower ambiguity
* Higher enforceability

---

### Legal Assessment Features

Columns 29–34 represent core benchmark scoring variables.

These variables are among the most important features in the dataset.

Examples:

* evidence_strength_score
* ambiguity_score
* legal_score
* arbitration_risk_score

These scores support predictive legal intelligence research.

---

### Linguistic Features

Columns 35–38 model code-mixed legal discourse.

They capture:

* Hinglish intensity
* Dialect variation
* Code-switching behavior
* Regional language influence

These variables are particularly valuable for multilingual NLP research.

---

### Procedural Stage Features

Columns 39–40 describe dispute lifecycle progression.

Examples:

* Draft_Circulated
* Clause_Negotiation
* Counter_Offer_Filed
* Mediation_Requested
* Arbitration_Proceeding
* Terminated

These features support procedural trajectory modeling and sequential prediction tasks.
| #  | Column                       | Type          | Description                                             |
| -- | ---------------------------- | ------------- | ------------------------------------------------------- |
| 41 | num_stage_transitions        | integer       | Total number of procedural stage transitions            |
| 42 | stage_trajectory             | JSON / string | Complete procedural stage sequence                      |
| 43 | validity_label               | categorical   | Legal validity classification of the contract           |
| 44 | final_outcome                | categorical   | Final dispute resolution outcome                        |
| 45 | difficulty_tier              | categorical   | Difficulty level assigned to the dispute                |
| 46 | primary_ambiguous_clause     | categorical   | Principal clause responsible for ambiguity              |
| 47 | num_disputed_clauses         | integer       | Number of clauses under dispute                         |
| 48 | critic_finding               | text          | Legal critic explanation and reasoning                  |
| 49 | critic_confidence            | numeric       | Confidence score associated with critic reasoning       |
| 50 | negotiation_trace_json       | JSON          | Multi-turn negotiation conversation trace               |
| 51 | transaction_manifest_json    | JSON          | Structured transaction and dispute metadata             |
| 52 | latent_economic_scale        | numeric       | Internal latent economic factor                         |
| 53 | latent_legal_formality       | numeric       | Internal latent legal-formality factor                  |
| 54 | latent_dispute_intensity     | numeric       | Internal latent dispute-intensity factor                |
| 55 | latent_ambiguity_level       | numeric       | Internal latent ambiguity factor                        |
| 56 | latent_settlement_proclivity | numeric       | Internal latent settlement tendency factor              |
| 57 | split                        | categorical   | Dataset partition assignment (train/validation/test)    |
| 58 | colored_noise_economic       | numeric       | Economic colored-noise component used during generation |
| 59 | colored_noise_temporal       | numeric       | Temporal colored-noise component used during generation |

---

# Feature Notes (41–59)

### Procedural Telemetry

Columns 41–42 capture procedural evolution.

These variables enable:

* Trajectory prediction
* Sequential modeling
* Legal process simulation
* Markov-state analysis

---

### Outcome Features

Columns 43–45 represent benchmark targets.

Common tasks include:

* Validity prediction
* Outcome prediction
* Difficulty classification

---

### Ambiguity Features

Columns 46–47 describe contractual uncertainty.

These variables support:

* Ambiguity analysis
* Clause-level reasoning
* Contract risk assessment

---

### Explainability Features

Columns 48–49 provide interpretable legal reasoning.

The critic framework generates:

* Legal findings
* Statutory observations
* Enforceability explanations

These fields are particularly useful for explainable AI research.

---

### Negotiation Trace Features

Columns 50–51 contain the richest information in the benchmark.

These fields capture:

* Multi-turn interactions
* Dispute trajectories
* Structured mediation records
* Procedural telemetry

These variables are suitable for:

* LLM training
* Legal dialogue modeling
* Agentic mediation systems
* Multi-agent simulation

---

### Latent Variables

Columns 52–56 represent hidden simulation factors.

These variables are included primarily for:

* Benchmark analysis
* Controlled experimentation
* Research reproducibility

---

### Dataset Partition Feature

Column 57 defines benchmark splits.

Possible values:

* train
* validation
* test

---

### Generation Diagnostics

Columns 58–59 contain colored-noise signals used during synthetic generation.

These variables support:

* Generation auditing
* Statistical validation
* Reproducibility studies

---

# Recommended Prediction Targets

The following columns are recommended benchmark targets:

| Task                         | Target Column            |
| ---------------------------- | ------------------------ |
| Contract Validity Prediction | validity_label           |
| Outcome Prediction           | final_outcome            |
| Arbitration Risk Regression  | arbitration_risk_score   |
| Settlement Prediction        | settlement_probability   |
| Difficulty Classification    | difficulty_tier          |
| Clause Ambiguity Analysis    | primary_ambiguous_clause |

---

# Data Types Summary

| Type        | Approximate Count |
| ----------- | ----------------- |
| Numeric     | 25+               |
| Integer     | 10+               |
| Binary      | 5+                |
| Categorical | 10+               |
| Text        | 2                 |
| JSON        | 2                 |

---

End of Data Dictionary.
