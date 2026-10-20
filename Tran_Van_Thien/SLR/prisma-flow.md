
# PRISMA Flow — Tran Van Thien

> Working draft based on the current source files. Screening counts reflect recorded spreadsheet decisions. Final eligibility and study inclusion should be verified before publication.

## Study Selection Flow

```text
Records identified from Semantic Scholar (N = 54)
                    |
                    v
        Title/abstract screening
        Exclude (N = 48)
        Unclear (N = 4)
        Include (N = 2)
                    |
                    v
     Records in the second-stage assessment file (N = 10)
                    |
                    v
          Full-text assessment decisions
          Exclude (N = 5)
          Unclear (N = 3)
          Include (N = 2)
                    |
                    v
      Final included studies (N = 2)
      Pending final team verification
```

## High-priority candidates for verification (N = 3)

The following studies are relevant to the research topic and should be reviewed alongside the recorded screening decisions.

- **User Acceptance Test Case Generation Using LLMs**
  - Generates user acceptance test cases from software requirements using multiple open-weight LLMs.
  - Evaluates generated test cases using similarity measures and requirement coverage.
  - Current decision: Include.

- **Improving Requirement Comprehension in GPT Models for Enhanced Consistency in Test Case Generation**
  - Investigates improving GPT-based test-case generation through additional training on functional requirements.
  - Reports improvements in consistency and requirement coverage.
  - Current decision: Include.

- **Automatic Generation of Acceptance Test Cases From Use Case Specifications: An NLP-Based Approach**
  - Investigates acceptance-test generation from use-case specifications using NLP.
  - Relevant to acceptance testing, but does not meet the current LLM/GenAI inclusion criterion.
  - Current decision: Unclear; requires a team decision on whether to retain it as a baseline study.

## Count check

- The initial record inventory contains **54 records**.
- The first-round screening file contains **48 Exclude, 4 Unclear, and 2 Include** decisions.
- The second-stage assessment file contains **10 records**: 5 Exclude, 3 Unclear, and 2 Include.
- The three high-priority candidates listed above are a follow-up shortlist, not three additional studies.
- The first-round decisions do not directly reconcile with the ten records in the second-stage file. The screening history should be checked before treating this as a final PRISMA flow.
- Duplicate removal, reports not retrieved, and any other unrecorded screening stages are not quantified in the supplied files and are therefore not represented as separate counts.

## Source files

- `01_all_records.csv` — Initial literature-search records.
- `02_after_screening_v1.csv` — First-round screening decisions and reasons.
- `03_final_included.csv` — Second-stage decisions and full-text assessment reasons.

> **Status:** PRISMA-style working draft. Confirm the screening sequence and final eligibility decisions with the review team before publication.
