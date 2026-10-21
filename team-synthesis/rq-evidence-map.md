# RQ Validation (from evidence-table-merged, 68 rows)

## 1. RQ + PICO

**RQ:** For 20 frozen functional requirements from PURE, how do ChatGPT and Claude, using the same one-shot EP-BVA prompt, differ in coverage-item percentage relative to a human-designed test suite produced before viewing any AI output?

| | PICO |
|---|---|
| P | 20 frozen functional requirements from PURE |
| I | ChatGPT (one fixed version, recorded at run time), one-shot EP-BVA prompt |
| C | Claude, same prompt; human-designed suite as the reference |
| O | Coverage-item percentage relative to the human suite |

## 2. Evidence base

**Five-gate check**

| Gate | Result | Pass? |
|---|---|---|
| P1: at least 12 papers | 68 rows (63 after removing 5 off-topic rows) | Pass |
| P2: Tool/LLM at least 90% | 66/68 = 97% counting any entry; 58/68 = 85% counting only rows that name the LLM (10 rows say "LLM N/A") | Borderline; fill in missing LLM names |
| P3: Results with numbers at least 50% | 66/68 = 97% | Pass |
| P4: Limitations with data at least 50% | 45/68 = 66% (23 rows N/A) | Pass |
| P5: Specific metric names | No row lists a bare "accuracy" | Pass |

**Data issues to resolve before counting**
- Off-topic rows to remove: "Mamba-Hybrid… AI-Generated Text", "The Impact of AI Guilt…", "Homophily-induced… multi-agent", "A Complete Survey on Generative AI", "How Much Confidence… Reliability Estimation".
- Not usable for gaps: UMTG 2020 (not an LLM) and BlackBoxTestGen (no LLM). "Generative language models… requirement engineering" (PURE) is requirement extraction, not test generation.
- The "Gắn RQ" column cannot be used for counting: 59 of 68 rows share the same value "P I O ⚑". P/I/C/O must be assessed paper by paper.
- Re-open the PDFs for: Req2Test (coverage 91.75% or 85.97%), UMTG (Table 17 labels), R022 (table/figure numbers).

## 3. Combined counter-evidence

**Nearest paper:** R001, Sisomboon et al. 2024, "AI-Driven Prompt Templates for User Acceptance Test Case Generation".

| Element | R001 | Team RQ | Difference and evidence |
|---|---|---|---|
| P | 8 requirements from one company's tester training dataset | 20 frozen FRs from PURE | Different. R001 Section 5.2 itself notes the 8 requirements come from one company and may carry selection bias |
| I | ChatGPT 3.5 / 4o | ChatGPT (fixed version, recorded at run time) | Same, once the version is fixed |
| C | Claude (plus Gemini, Copilot) | Claude; human suite designed beforehand | The table does not say whether R001 has a blind, pre-designed human suite. Check the full text |
| O | Coverage % per EP and BVA; F1 | Coverage-item % relative to the human suite | Close; the definition of "coverage" may differ |

**Novelty label:** if P is read as "natural-language requirements in general", the RQ matches 4/4 elements and is a replication. If P is "20 frozen FRs from PURE", it matches 3/4 and is an extension. P should be stated precisely (PURE, 20 FRs, frozen) and the instructor informed before the lock.

R022 (Sisomboon 2026, 16 requirements, five LLMs including Claude and ChatGPT, EP/BVA) comes from the same author group as R001, so the two count as one.

**Ceiling-effect risk:** both R001 and R022 report 100% for EP and 100% for BVA across tools (R001 except Copilot). If the team's coverage-item measure also hits the ceiling, ChatGPT and Claude will be hard to tell apart. By contrast, "LLM comparison… natural-language requirements" (ISEC 2025) reports coverage below 25% at some requirement levels, but it measures MC/DC on a Simulink model, so the definition differs.

## 4. Feasibility

| Criterion | Concrete figure | Rating |
|---|---|---|
| Dataset | PURE is public on Zenodo; the 20 FRs are frozen per the RQ | ✅ |
| API/Tool | 20 FRs x 2 models x 1 prompt = 40 runs; web or API cost about 0 to a few dollars | ✅ |
| Compute | No GPU needed; runs on a laptop | ✅ |
| Ground truth | Human EP-BVA design for 20 FRs, about 20–30 minutes each, roughly 7–10 hours for the team; must be finished before any AI output is viewed | ⚠️ |
| Code base | Not needed | ✅ |
| Skills | Agree on a definition of coverage-item and a scoring method; at least 2 independent scorers to check agreement, about 1–2 days | ⚠️ |
| Time | AI runs about 1 day, scoring 2–3 days, buffer of at least 3 days | ✅ |

**Count:** 0 ❌, 2 ⚠️. Conclusion: **safe**.

**Plan for the ⚠️ items**
- Ground truth: split the 20 FRs among members; each submits their suite before anyone runs ChatGPT or Claude, with submission times recorded to show the design was blind.
- Skills: hold one session to fix the coverage-item definition using 2–3 sample FRs, then have two people score independently and reconcile.

## 5. Gap the RQ fills

**Initial gap (derived directly from the RQ, not from the counts below):** "Within the literature searched, there is no evidence on how ChatGPT and Claude, using the same one-shot EP-BVA prompt on a frozen set of 20 PURE FRs, differ in coverage-item percentage relative to a human-designed suite produced before viewing any AI output." Main type: **GAP-D** (PURE data), with a GAP-M aspect (blind human reference).

**Counts over papers that generate tests from natural-language requirements (N = 16):** 1 (AST 2025 industrial), 3 (Llama-3-70B on-premises), 8, 10, 16 (UAT with PURE), 23, 32 (IoT use cases), 42 (TriGen), 44, R001, R022, R042 (APITestGenie), R099, R128, Req2Test, ISEC 2025.

| Limitation / aspect | Papers | Remaining | Preliminary conclusion |
|---|---|---|---|
| Small or single-domain requirement set, limited generalizability | 13/16: 1, 3, 16, 23, 32, 42, 44, R001, R022, R042, R099, Req2Test, ISEC 2025 | 13 | Strong gap by the counting rule (at least 3), GAP-D, but a fairly generic limitation; quote the exact text with section/page |
| Uses PURE | 2/16 generate tests (16 and R099); one more paper does requirement extraction | 2 | No paper combines PURE + ChatGPT/Claude + coverage-item |
| Compares Claude and ChatGPT on NL requirements | 3/16 (R001, R022, ISEC 2025); only R001 and R022 use EP/BVA | n/a | Weak gap or partly filled, GAP-T |
| Human reference suite designed blind | 5 papers have a human reference (16, 31, 37, 55, ISEC 2025); the table does not say whether it was blind | unknown | Cannot conclude; read the full text of these 5 papers. Do not write "no one has done this" |

**Gap statement (to be confirmed after the PL verifies the counts):**
> "Of 16 papers generating tests from natural-language requirements, 13 report limitations on the scale or domain of the requirement set; 2 use PURE, but none measures coverage-item percentage of ChatGPT and Claude against a human suite designed beforehand (within the literature searched)."

**Benefit statement:** "The team wants to know whether ChatGPT or Claude covers EP-BVA coverage items closer to a human-designed suite on PURE requirements, to help a project's testing team decide which model to use for drafting tests from requirement specifications. If one model is clearly better, they use it for the first pass; if the two are similar or both fall well below the human suite, they choose by cost and still let a person design the boundary cases."

**Why the gap is still open:** two hypotheses to check against the full texts. (1) It is hard and costly: a blind human reference suite is needed for every FR. (2) Someone may have tried, but coverage hits the ceiling as in R001 and R022 (EP and BVA at 100%), making models hard to distinguish and results less publishable. Not found within the literature searched; this does not claim that no one has done it.

## 6. Decision

**Keep the RQ.** Novelty label: extension, with P defined as 20 frozen FRs from PURE; it differs from R001 in the requirement set (PURE instead of 8 requirements from one company) and in the blind human reference suite. Instructor informed on: ________
