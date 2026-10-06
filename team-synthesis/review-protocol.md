# SLR Review Protocol: EP-BVA Based UAT Design on PURE

## 1. Context & Research Topic

- **Topic:** Comparing ChatGPT and Claude for EP–BVA-Based UAT Design on PURE
- **Repository:** RBL-SWT302-11-Group06

## 2. Research Question (RQ)

"For 20 frozen functional requirements from PURE, how do ChatGPT and Claude using the same one-shot EP–BVA prompt differ in coverage-item percentage relative to a human-designed test suite produced before viewing any AI output?"

## 3. PICOS Framework

- **P (Population):** 20 frozen functional requirements with well-defined input domains or business logic extracted from the PURE requirement dataset (Zenodo record 1414117).
- **I (Intervention):** ChatGPT and Claude generating black-box UAT test cases using a fixed one-shot EP–BVA prompt (specifying equivalence classes, boundary values, preconditions, test steps, and expected results).
- **C (Comparison):** A human-designed reference test suite independently produced and reconciled by two human evaluators prior to viewing any AI output.
- **O (Outcome):** EP–BVA coverage-item percentage calculated against the reference item set.
- **S (Study Design):** Empirical experimental study comparing median coverage across 5 independent runs per requirement, using Friedman test and post-hoc pairwise Wilcoxon signed-rank tests with Holm correction.

## 4. Search Configuration

- **Year Range:** 2018 – Present
- **Search Fields:** Title, Abstract, Keywords
- **Base Search String (String A):**
  ("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") AND ("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage")

## 5. Execution Rules

- **Deduplication:** Primary key: DOI (lowercase, normalized). Secondary key: Normalized Title + First Author + Year.
- **Screening:** Pass 1 on Title/Abstract -> Pass 2 on Full Text.
- **Snowballing:** Max 2 rounds from final included seeds using Semantic Scholar / Crossref API. Candidates must go through V1 and V2 screening before inclusion.
