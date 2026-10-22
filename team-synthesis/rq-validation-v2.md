# RQ Validation, revised (merged GAP A + GAP B)

## 1. RQs + PICO

**RQ1:** For 20 functional requirements selected from PURE by public criteria, how much valid coverage-item coverage do two designated models (one from OpenAI, one from Anthropic), using the same one-shot EP-BVA prompt, achieve compared with a test suite designed independently by a human, when all are evaluated against the same reference coverage-item set?

**RQ2:** How do the two models' test suites and the human-designed suite differ in the omission rate of valid equivalence classes, invalid equivalence classes, and applicable boundary values?

| | PICO |
|---|---|
| P | 20 FRs selected from PURE by public criteria, with context preserved |
| I | One OpenAI model, one-shot EP-BVA prompt (model ID, run date, configuration recorded) |
| C | One Anthropic model, same prompt; human-designed suite as a further comparator |
| O | RQ1: valid coverage-item coverage on the reference set. RQ2: omission rate per item class, with a separate denominator per class |

## 2. Evidence base

**Five-gate check on evidence-table-merged (68 rows)**

| Gate | Result | Pass? |
|---|---|---|
| P1: at least 12 papers | 68 rows (63 after removing 5 off-topic rows) | Pass |
| P2: Tool/LLM at least 90% | 97% counting any entry; 85% counting only rows that name the LLM | Borderline; fill in missing LLM names |
| P3: Results with numbers at least 50% | 97% | Pass |
| P4: Limitations with data at least 50% | 66% | Pass |
| P5: Specific metric names | No bare "accuracy" | Pass |

**To do before counting again**
- Add Rodríguez, Rossi and Fernandez (2025), "Evaluating Large Language Models for the Generation of Unit Tests with Equivalence Partitions and Boundary Values" (arXiv 2505.09830). It is not in the current table.
- Remove the 5 off-topic rows; mark UMTG 2020 and BlackBoxTestGen as non-LLM references; mark "Generative language models… requirement engineering" as requirement extraction.
- The "Gắn RQ" column cannot be used for counting; assess P/I/C/O paper by paper.
- Re-open the PDFs for Req2Test (coverage figure), UMTG (Table 17 labels), R022 (table/figure numbers).

## 3. Nearest papers

Two papers are nearest, each on a different part of the RQ.

**Rodríguez et al. 2025 (nearest on EP-BVA and human comparison)**

| Element | Rodríguez et al. 2025 | Team RQ | Difference |
|---|---|---|---|
| P | 10 ad hoc Java artifacts, specification plus source code | 20 PURE FRs, requirements only, no code | Different input type and size |
| I | One model (GPT-4-0613), prompt tuned iteratively | Two models, prompt frozen on a separate pilot set | Different |
| C / human reference | One trained developer wrote manual tests under bias-avoidance instructions | Human suite designed independently, plus an independently validated reference item set | Different: the team separates the reference item set from the human suite |
| O | JaCoCo line/branch coverage, PIT mutation, test smells, plus manual qualitative analysis of equivalence partitions, boundary values, exceptions | Coverage-item coverage and omission rate per class on a reference set | Different denominator and class-level rates |

Reported there: both approaches identify equivalence partitions; the model tends to pick values near the middle of a partition rather than at the edges; floating-point assertion errors appear. Branch coverage is 100% in nearly all scenarios, so code coverage alone does not separate the approaches. Their stated limits: 10 scenarios, Java/JUnit only.

**R001 and R022 (Sisomboon et al., same author group, count as one)**
Nearest on comparing ChatGPT and Claude with EP/BVA from natural-language requirements. R001 uses 8 requirements from one company, R022 uses 16. Both report EP and BVA coverage at or near 100%.

**Novelty label:** extension, to be confirmed after reading the full texts. The differences to defend are: requirements only (no code), two models from different vendors, a reference item set validated independently of the human suite, and omission rates per item class. The novelty claim does not rest on using PURE, nor on the current table lacking a feature.

## 4. Gap (revised)

**Candidate gap, pending full-text confirmation:** within the literature searched, no paper found so far evaluates tests generated from natural-language requirements by two vendors' models against an independently validated reference coverage-item set, and reports omission rates separately for valid equivalence classes, invalid equivalence classes and applicable boundary values.

| Observation | Papers | Status |
|---|---|---|
| Small or single-domain requirement sets are a common stated limitation | 13 of 16 requirement-based papers | Does not show that a PURE subset fixes the limitation; the selection rationale for the 20 FRs must carry that argument |
| PURE used with test generation | 2 of 16 (UAT with PURE; R099) | Neither measures item-level coverage for two vendors' models |
| Claude and ChatGPT compared with EP/BVA on natural-language requirements | R001, R022 | Partly covered; the team's difference is the reference item set and class-level omission |
| Human reference suite | 5 papers in the table plus Rodríguez 2025 | Whether any builds an independent reference item set is unknown; read the full texts |
| Qualitative EP-BVA analysis against manual tests | Rodríguez 2025 | Exists for Java code plus specification with one model; not for requirements only |

**Benefit statement:** results would indicate which classes of EP-BVA obligations testers should prioritise when reviewing AI-drafted tests from requirement specifications. They would not show which parts can be delegated entirely to AI, nor which model is best in general.

**Why the gap may still be open (hypotheses to check):** an independent reference item set and a blind human suite are costly to build for every FR; and aggregate coverage can sit at the ceiling (100% in R001, R022 and in most scenarios of Rodríguez 2025), which hides differences that item-level rates could show.

## 5. Selection of the 20 FRs

To be completed and justified before the pilot:
- Public selection criteria (for example requirement type, presence of ordered domains or boundaries, size of the surrounding context).
- Source documents and domains in PURE, and which constraint types each chosen FR represents (numeric ranges, enumerations, string length, conditional rules).
- Each FR provided with its relevant definitions and rules; no sentence is separated from the rule it depends on.

## 6. Measurement and control

- Three artefacts kept separate: reference coverage-item set (derived from the requirement, explicit rules, independently validated), human-designed suite (written before any AI output is viewed), and each model's suite. All are scored against the same reference set.
- At least two independent people build or check the reference items; disagreements are logged and resolved before scoring any output. A valid item found after viewing output goes through validation and all parties are re-scored.
- BVA applies only where the domain is ordered or has a defined boundary; non-applicable items are not counted as missing.
- BVA variant fixed in advance (proposal: 3-value), with rules for discrete and continuous domains and precision.
- An item counts as covered only when the test has input, condition and expected result consistent with the requirement; naming a boundary is not enough.
- Incorrect tests, wrong expected results and AI-added constraints are recorded separately.
- Prompt and one-shot example frozen on a separate pilot set, not tuned on the 20 evaluation FRs.
- Model ID, run date, configuration and output limits recorded.
- Multiple independent runs per FR to estimate variation (proposal: 5).
- Comparison is paired by FR; report effect size and uncertainty; items and runs are not treated as independent observations.
- Coverage aggregation fixed in advance: mean per FR and pooled over all items are both reported, since complex FRs contribute more items.
- RQ2 rates use a separate denominator per class; absolute omitted counts are not used to rank class difficulty.
- Human designer's skill, time limit and allowed tools are specified; if there is one designer, representativeness is stated as a limitation.

## 7. Feasibility

| Criterion | Estimated figure | Rating |
|---|---|---|
| Dataset | PURE is public on Zenodo | ✅ |
| API/Tool | 20 FRs x 2 models x 5 runs = 200 runs, plus pilot; cost to be measured | ✅ |
| Compute | No GPU; laptop | ✅ |
| Ground truth | Independent reference item set plus human suite for 20 FRs; the largest workload | ⚠️ |
| Code base | Not needed | ✅ |
| Skills | Agreeing on item rules and scoring; two independent scorers; paired analysis | ⚠️ |
| Time | Pilot, reference set, multiple runs, scoring and re-scoring | ⚠️ |

**Count:** 0 ❌, 3 ⚠️. By the decision rule this is higher risk and needs a plan.

**Plan:** run the pilot on a few FRs outside the 20 first to measure the real time per FR for item building and scoring; reduce the number of FRs or runs per FR if the measured time exceeds the buffer; fix the scoring guide before any evaluation run.

## 8. Expected contributions

- A PURE subset with source traceability, EP-BVA coverage items and a validated scoring guide.
- A comparison of valid coverage-item coverage of two models against a human designer under defined conditions.
- An analysis of omission types, incorrect tests and content not required by the requirement.
- A suggestion of which item classes testers should prioritise for review when using AI-drafted tests.
- Not claimed: which model is best in general; which parts can be fully delegated to AI; cost-based recommendations without measured cost; equivalence of the two models without a significant difference test.

## 9. Decision

Keep the merged direction with RQ1 and RQ2. Final RQ lock depends on the updated nearest-paper table and the pilot. Instructor informed on: ________
