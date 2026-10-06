# Stage A search and protocol record

## Protocol snapshot

- **Topic:** Comparing ChatGPT and Claude for EP–BVA-Based UAT Design on PURE
- **Research question:** For 20 frozen functional requirements from PURE, how do ChatGPT and Claude using the same one-shot EP–BVA prompt differ in coverage-item percentage relative to a human-designed test suite produced before viewing any AI output?
- **Year range:** 2018–present
- **Search fields:** Title, Abstract, Keywords
- **Deduplication:** Normalized DOI; otherwise normalized title + first author + year.
- **Screening:** Title/abstract, followed by full text for V1 INCLUDE and UNSURE records. Snowballing is limited to two rounds from final included seeds, with candidates screened at V1 and V2.
- **Inclusion criteria:** IC-P (black-box test case generation, UAT, or requirements-based testing from software requirements); IC-I (LLM evaluation using prompting for test generation specifically targeting EP or BVA); IC-O (quantitative coverage or fault-detection outcomes); IC-S (peer-reviewed empirical experimental study, journal article, or conference paper).
- **Exclusion criteria:** EC-1 (domain misalignment); EC-2 (no LLM evaluation); EC-3 (no empirical quantitative results); EC-4 (full text inaccessible); EC-5 (non-English); EC-6 (duplicate or earlier version).
- **Source of truth:** `team-synthesis/review-protocol.md` and `team-synthesis/ie_criteria.md`.

## Search S01 — protocol String A attempt

- **Date:** 2026-10-06
- **Source:** IEEE Xplore
- **URL:** https://ieeexplore.ieee.org/Xplore/home.jsp
- **String ID:** A
- **Search fields:** Not confirmed; the search page did not load.
- **Year filter:** 2018–present intended by protocol; application could not be verified.
- **Other filters:** None confirmed.
- **Query:**

```text
("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") AND ("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage")
```

- **Reported results:** N/A — IEEE Xplore returned “Unusual Traffic Detected (Error 418)”.
- **Retrieved records:** 0
- **Notes:** Access restriction was not bypassed. The query result count was unavailable.

## Search S02 — supplied IEEE Xplore export

- **Date:** 2026-10-06 (from the supplied export filename `export2026.10.06-04.17.30.csv`; time zone not specified)
- **Source:** IEEE Xplore
- **URL:** https://ieeexplore.ieee.org/Xplore/home.jsp
- **String ID:** Unknown — the export does not include the query or search identifier.
- **Search fields:** Unknown. The export contains document title, abstract, author keywords, and IEEE terms, but does not establish which fields were searched.
- **Year filter:** The export includes records both before and after 2018. The protocol's 2018–present publication-year limit was applied to the exported records before V1 screening.
- **Other filters:** Not recorded in the export.
- **Exact query:** N/A — not present in the supplied export. The String A from S01 is not attributed to this export.
- **Reported results:** N/A — no source-reported total is present in the export.
- **Retrieved records:** 72 data rows
- **Notes:** Imported from the supplied IEEE Xplore CSV. All 72 rows were retained in the raw/deduplicated record file; 39 records dated before 2018 were filtered out before V1 screening. The query and database filters cannot be independently reproduced from this export.

## Record accounting and screening

- **Raw export records:** 72
- **Duplicates removed:** 0
- **Records after deduplication:** 72
- **Outside protocol year range, removed before V1:** 39
- **In-range records screened at V1:** 33
- **V1 INCLUDE:** 0
- **V1 UNSURE:** 0
- **V1 EXCLUDE:** 33 (32 EC-1; 1 EC-2)
- **Full-text assessed:** 0
- **V2 EXCLUDE:** 0
- **Final included:** 0
- **Snowballing:** Not performed; no final included seeds.

The 39 out-of-range records were excluded by the shared protocol's year filter, not assigned an IC/EC code. They remain in `01_all_records.csv` for traceability and are not included in the V1 screening file.

| Seed DOI | Round | Direction | Viewed | Added to 01 | Final included |
|---|---:|---|---:|---:|---:|

## Protocol notes and limitations

The attached task text contained bug-reproduction/agent-feedback search concepts that do not match the shared PURE EP–BVA research question. The shared review protocol and IC/EC were treated as authoritative.

The supplied export does not identify its exact query, searched fields, source-reported hit count, or applied database filters. Therefore, the 72 exported rows are auditable, but the original IEEE Xplore retrieval cannot be fully reproduced. The protocol's year range was applied explicitly during this review; no IC/EC criteria or research question were changed.
