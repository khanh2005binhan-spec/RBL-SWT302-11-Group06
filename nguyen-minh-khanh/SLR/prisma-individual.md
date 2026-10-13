# Individual PRISMA Flow — Nguyen Minh Khanh

## Research Topic

Comparison of ChatGPT and Claude for generating User Acceptance Testing (UAT) test cases using Equivalence Partitioning (EP) and Boundary Value Analysis (BVA) on the PURE system.

## 1. Identification

| Item                                                                               |                    Count |
| ---------------------------------------------------------------------------------- | -----------------------: |
| Records documented from Google Scholar searches in `01_all_records.csv`            |                       25 |
| Additional records identified through backward snowballing in `04_snowballing.csv` |             3 candidates |
| Additional records identified through forward snowballing                          |             0 documented |
| Duplicate records removed                                                          | TBD — not yet documented |
| Total unique records after duplicate removal                                       |                      TBD |

**Note:** The 25 records are the entries currently listed in `01_all_records.csv`, not the total number of results displayed by Google Scholar. The three snowballing entries are candidates and must be verified against the seed paper's references before being reported as confirmed backward-snowballing records.

## 2. Screening

| Item                                                                     | Count |
| ------------------------------------------------------------------------ | ----: |
| Records listed in `02_after_screening_v1.csv`                            |    25 |
| Records excluded at preliminary screening                                |     7 |
| Records marked “Need more information”                                   |    18 |
| Records with completed full-text checks documented in the screening file |     0 |
| Records with unresolved screening decisions                              |    18 |

The seven preliminary exclusions are:

- EC-S: Review papers rather than primary empirical studies — 2 records.
- EC-P: Outside the target review scope — 5 records.

The 18 records marked “Need more information” have not yet received final eligibility decisions.

## 3. Eligibility

| Item                                        |              Count |
| ------------------------------------------- | -----------------: |
| Full-text reports sought for retrieval      |                TBD |
| Reports not retrieved                       |                TBD |
| Full-text reports assessed for eligibility  |       0 documented |
| Reports excluded after full-text assessment |                TBD |
| Studies meeting all inclusion criteria      | 0 confirmed so far |

The three records in `03_final_included_review_pending.csv` are still pending full-text verification:

1. *Automated Software Test Case Generation Using Directional Partially Weighted Ensemble Large Language Models With Retrieval-Augmented Generation (RAG)* (2026).
2. *User Acceptance Test Case Generation Using LLMs* (2025).
3. *AI-Driven Prompt Templates for User Acceptance Test Case Generation* (2024).

These records must not be counted as final included studies until the inclusion criteria have been verified.

## 4. Snowballing Candidates

| Candidate                                                                                                                                                | Preliminary decision | Current status                                                 |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | -------------------------------------------------------------- |
| LLM4Fin: Fully Automating LLM-Powered Test Case Generation for FinTech Software Acceptance Testing                                                       | Include              | Candidate for further screening; verify source and eligibility |
| Comprehensive Evaluation and Insights Into the Use of Large Language Models in the Automation of Behavior-Driven Development Acceptance Test Formulation | Include              | Candidate for further screening; verify source and eligibility |
| Automatic Creation of Acceptance Tests by Extracting Conditionals from Requirements: NLP Approach and Case Study                                         | Exclude — EC-2       | Preliminary exclusion because no LLM evaluation is documented  |

The two candidates marked “Include” are not final included studies. Their relevance to EP/BVA and the required quantitative outcomes must be checked. The backward-snowballing relationship must also be confirmed against the seed paper's reference list.

## 5. Search and Screening Notes

- Search platform: Google Scholar.
- Search dates recorded: 6 October 2026 and 13 October 2026.
- Search strategy: three original queries and three revised queries.
- Revised Search 1: 9 records reviewed.
- Revised Search 2: the number of records reviewed has not been recorded precisely.
- Revised Search 3: 9 records reviewed.
- The displayed Google Scholar result estimates were not treated as counts of collected or screened records.
- Screening decisions are recorded in `02_after_screening_v1.csv`.
- Candidate studies pending full-text verification are tracked in `03_final_included_review_pending.csv`.
- Snowballing candidates are tracked in `04_snowballing.csv`.

## 6. Final Verification Checklist

- [ ] Confirm whether any duplicate records exist across searches and snowballing.
- [ ] Record the exact number of reports sought for full-text retrieval.
- [ ] Complete full-text screening for the remaining candidates.
- [ ] Apply the agreed inclusion and exclusion criteria consistently.
- [ ] Verify the two provisionally included snowballing candidates.
- [ ] Update the final included-study count after eligibility assessment.
- [ ] Reconcile all PRISMA counts before submission.
