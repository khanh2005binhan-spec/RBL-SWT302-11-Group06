# Inclusion and Exclusion Criteria (IC/EC)

## Research Topic

Comparison of ChatGPT and Claude for designing User Acceptance Testing (UAT) test cases using Equivalence Partitioning (EP) and Boundary Value Analysis (BVA) on the PURE system.

## Status

**Draft for team review.** These criteria must be reviewed and approved by the research team before formal screening. Do not treat screening decisions made with this draft as final until the team confirms it.

## Inclusion Criteria (IC)

- **IC1 — Relevant testing activity:** The study concerns software test-case generation, test design, acceptance testing, user acceptance testing (UAT), or another clearly relevant black-box testing activity.
- **IC2 — Relevant AI approach:** The study investigates a large language model (LLM) or generative AI for software testing, test-case generation, test-oracle generation, or testing-artifact generation. Studies specifically involving ChatGPT, Claude, one-shot prompting, or comparable prompting approaches are especially relevant.
- **IC3 — Relevant technique or evaluation:** The study discusses or evaluates equivalence partitioning (EP), boundary value analysis (BVA), requirements/test coverage, test-case quality, or another evaluation method that can inform the research question.
- **IC4 — Sufficient scholarly information:** The record identifies a retrievable scholarly publication or research manuscript with enough bibliographic information to verify the source and assess its relevance.

## Exclusion Criteria (EC)

- **EC1 — Out of scope:** The study is not about software testing, software test design, test-case generation, acceptance testing, or a closely relevant testing activity.
- **EC2 — No relevant AI/testing connection:** The study does not investigate or meaningfully discuss LLMs/generative AI in a software-testing context.
- **EC3 — No usable relevance to the research questions:** After reviewing the abstract or full text, the study provides no useful evidence about test generation/design, EP/BVA, coverage, test quality, or evaluation relevant to this project.
- **EC4 — Duplicate record:** The same publication appears more than once. Keep one canonical record and document the duplicate record ID(s); do not silently delete records from the raw export.
- **EC5 — Unverifiable or insufficient record:** After reasonable verification attempts, the publication/source cannot be verified or the available record is too incomplete to assess. Missing metadata alone should trigger verification first, not immediate exclusion.
- **EC6 — Non-scholarly or unsuitable publication type:** The item is not an eligible research publication under the team's approved protocol (for example, an unrelated blog or promotional page). Confirm eligible publication types with the instructor/team before applying this criterion.

## Screening Procedure

1. Preserve the original citation export unchanged in `raw/`.
2. Assign a stable `record_id` to each imported record.
3. Deduplicate using normalized title and, where available, DOI or publisher URL. Record duplicate relationships and retain the raw source.
4. Screen title and abstract first. Use `Include`, `Exclude`, or `Unclear`; do not infer missing abstracts.
5. For `Exclude`, record the primary exclusion criterion (EC code) and a short evidence-based reason.
6. Retrieve full text for records retained or marked `Unclear` after title/abstract screening.
7. Conduct full-text screening against the approved IC/EC and record one primary exclusion reason for each excluded full-text study.
8. If title/abstract or full text is unavailable, record the retrieval status and attempts. Do not automatically label it irrelevant.
9. Resolve uncertain decisions with a second reviewer/team discussion and document the resolution.
10. Report counts at each stage for the PRISMA flow diagram.

## Screening Decision Values

- `Include` — available evidence indicates the record meets the approved criteria for the current screening stage.
- `Exclude` — available evidence clearly meets a specified exclusion criterion.
- `Unclear` — evidence is insufficient; retrieve more metadata/abstract/full text.
- `Pending` — not yet screened.

## Suggested Tracking Fields

`record_id`, `Title`, `Authors`, `Year`, `Publication`, `doi_or_url`, `abstract`, `IC1`, `IC2`, `IC3`, `IC4`, `EC1`, `EC2`, `EC3`, `EC4`, `EC5`, `EC6`, `screening_decision`, `exclusion_reason`, `reviewer_notes`, `full_text_status`.

## Important Notes

- This document is a proposed draft, not a claim that the team or instructor has approved these criteria.
- Search terms and screening criteria are related but not identical. A paper may be relevant even if its title does not contain every search-string term.
- Do not exclude a paper solely because its title/abstract export is missing metadata; attempt verification first.
- Do not claim that a record was retrieved, read, or full-text screened unless that action actually occurred.
