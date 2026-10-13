
# Evidence Review: LLM-Based UAT Test Case Generation

## 1. Purpose

This document consolidates the preliminary evidence extraction and
eligibility assessment of three studies related to AI/LLM-based software
test case generation.

The review focuses on:
- Requirements-based User Acceptance Testing (UAT)
- Equivalence Partitioning (EP)
- Boundary Value Analysis (BVA)
- Quantitative evaluation metrics
- Full-text eligibility verification

All assessments are preliminary unless supported by verified evidence
from the full text.

---

## 2. Evidence Summary

| Record | Year | Research focus | EP/BVA evidence | Quantitative evidence | Decision |
|---|---|---|---|---|---|
| 15 | 2026 | LLM ensemble with RAG for automated software test generation | Abstract lists EP and BVA | Abstract reports 98.44% test coverage | Pending full-text verification |
| 21 | 2025 | LLM-based User Acceptance Test Case Generation | Not yet verified | Required metrics not yet verified | Pending full-text verification |
| 23 | 2024 | AI-driven prompt templates for UAT test generation | Not yet verified | Required metrics not yet verified | Pending full-text verification |

## 3. Detailed Evidence and Analysis

### 3.1 Record 15

**Title:** Automated Software Test Case Generation Using Directional
Partially Weighted Ensemble Large Language Models With
Retrieval-Augmented Generation (RAG)

- Year: 2026
- Venue: IEEE Access
- DOI: https://doi.org/10.1109/ACCESS.2026.3667925

#### Evidence E15-01: Testing techniques

- Source: Published abstract
- Location: IEEE Xplore article record
- Finding: The abstract identifies Equivalence Partitioning (EP),
  Boundary Value Analysis (BVA), Use Case Testing, and State
  Transition Testing.
- Relevance: Provides preliminary evidence that the study addresses
  EP and BVA.
- Limitation: Full-text verification is needed to determine how the
  techniques are implemented and evaluated.

#### Evidence E15-02: Quantitative evaluation

- Source: Published abstract
- Location: IEEE Xplore article record
- Finding: The abstract reports 98.44% test coverage.
- Relevance: Suggests that the study includes a quantitative
  evaluation outcome.
- Limitation: The coverage definition, denominator, dataset,
  experimental setup, and comparison baselines must be verified.

#### Evidence E15-03: UAT relevance

- Source: Published abstract
- Location: IEEE Xplore article record
- Finding: The study discusses acceptance criteria and automated
  acceptance test case generation.
- Relevance: Potentially relevant to requirements-based acceptance
  testing.
- Limitation: The full text must establish whether the study meets
  the review's precise UAT scope.

#### Critical analysis

The study is a promising candidate because its abstract explicitly
mentions EP, BVA, and a numerical coverage result. However, high
reported coverage alone does not establish superiority over other
methods. The experimental design and coverage definition must be
examined before drawing conclusions.

**Preliminary decision:** Pending full-text verification.

---

### 3.2 Record 21

**Title:** User Acceptance Test Case Generation Using LLMs

- Year: 2025
- Venue: IEEE CASCON 2025
- DOI: https://doi.org/10.1109/CASCON66301.2025.00084

#### Evidence E21-01: UAT research focus

- Source: Published title and bibliographic record
- Finding: The title explicitly addresses user acceptance test case
  generation using LLMs.
- Relevance: Establishes preliminary topical relevance to UAT
  test generation.
- Limitation: The title does not establish whether the actual
  method meets all inclusion criteria.

#### Evidence E21-02: EP and BVA

- Source: Full paper required
- Finding: Direct evidence confirming the use of EP and BVA has
  not yet been collected.
- Relevance: These techniques must be checked against the review
  protocol.
- Limitation: Neither technique should be marked as satisfied
  without evidence from the original paper.

#### Evidence E21-03: Quantitative evaluation

- Source: Full paper required
- Finding: The required outcome metrics and numerical results
  have not yet been verified.
- Required checks:
  - Metric names and definitions
  - Dataset and number of test cases
  - Baseline methods
  - Experimental results
  - Evaluation limitations

#### Critical analysis

The study appears directly relevant to the topic because it explicitly
focuses on UAT test case generation using LLMs. Nevertheless, its
methodological eligibility remains uncertain until EP/BVA usage and
quantitative evaluation are verified.

**Preliminary decision:** Pending full-text verification.

---

### 3.3 Record 23

**Title:** AI-Driven Prompt Templates for User Acceptance Test Case
Generation

- Year: 2024
- Publisher: Springer
- Book: Data Science and Artificial Intelligence
- Pages: 78–92
- DOI: https://doi.org/10.1007/978-981-97-9793-6_6

#### Evidence E23-01: UAT and prompt-template focus

- Source: Published title and bibliographic record
- Finding: The title identifies AI-driven prompt templates for
  user acceptance test case generation.
- Relevance: Potentially relevant to prompt engineering for
  acceptance test generation.
- Limitation: The exact model, prompt design, and input requirements
  must be confirmed in the full chapter.

#### Evidence E23-02: EP and BVA

- Source: Full chapter required
- Finding: Direct evidence confirming the use of EP and BVA has
  not yet been collected.
- Relevance: The full text must be examined for explicit application
  or evaluation of these techniques.
- Limitation: A focus on prompt templates does not by itself
  demonstrate EP/BVA coverage.

#### Evidence E23-03: Quantitative evaluation

- Source: Full chapter required
- Finding: Required outcome metrics and numerical results have
  not yet been verified.
- Required checks:
  - Evaluation dataset
  - Prompt-template variants
  - Model and experimental setup
  - Metric definitions and numerical results
  - Baseline comparisons and limitations

#### Critical analysis

The study may contribute useful evidence about prompt design for UAT
test case generation. However, its eligibility depends on the actual
AI/LLM method, whether EP/BVA are addressed, and whether the required
quantitative results are reported.

**Preliminary decision:** Pending full-text verification.

---

## 4. Cross-Study Comparison

| Assessment dimension | Record 15 | Record 21 | Record 23 |
|---|---|---|---|
| Explicit LLM/AI focus in title | Yes | Yes | AI-driven; exact model needs verification |
| Explicit UAT focus in title | Not explicit | Yes | Yes |
| EP mentioned in abstract-level evidence | Yes | Not verified | Not verified |
| BVA mentioned in abstract-level evidence | Yes | Not verified | Not verified |
| Numerical outcome identified | 98.44% coverage reported | Not verified | Not verified |
| Full-text verification completed | No | No | No |
| Final inclusion decision | Pending | Pending | Pending |

## 5. Overall Findings

Record 15 currently has the strongest preliminary evidence for EP,
BVA, and quantitative test coverage.

Record 21 has a direct UAT focus, but its eligibility depends on
verification of the testing techniques and evaluation metrics.

Record 23 may contribute evidence about prompt-template design for
UAT test generation, but the method and experimental outcomes
must be verified.

The available evidence is insufficient to make a final inclusion
decision for any of the three studies.

## 6. Next Steps

1. Obtain the full text of each study.
2. Record the exact PDF page, section, table, or figure supporting
   each eligibility criterion.
3. Verify the definition of UAT and whether EP/BVA are mandatory
   under the review protocol.
4. Extract the dataset, metric definitions, numerical results,
   and baseline comparisons.
5. Update each preliminary assessment to Met, Not met, or Unclear.
6. Record the final Include or Exclude decision with a justified reason.

## 7. Evidence Quality and Traceability

Bibliographic records and abstracts provide preliminary evidence only.
They must not be treated as proof of full-text eligibility.

Every final decision should be traceable to the original publication.
Any quotation should be short, accurate, and accompanied by its
page or section reference.

No final inclusion decision is made in this document until
full-text verification has been completed.
