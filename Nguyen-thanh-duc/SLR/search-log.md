# Search Log: ACM Digital Library

## Protocol snapshot (từ team-synthesis/review-protocol.md)
- RQ: For 20 frozen functional requirements from PURE, how do ChatGPT and Claude using the same one-shot EP–BVA prompt differ in coverage-item percentage relative to a human-designed test suite produced before viewing any AI output?
- Year range: 2018 – present
- Search fields: Title, Abstract, Keywords
- Dedup: DOI (lowercase, normalized); secondary: normalized title + first author + year
- Screening: Pass 1 (title/abstract) → Pass 2 (full text)
- Snowballing: max 2 rounds, Semantic Scholar / Crossref API; candidates must pass V1 and V2

- IC/EC: xem team-synthesis/ie_criteria.md
## Search S01

Date: 2026-10-08

Source: ACM Digital Library

URL: https://dl.acm.org

String ID: A (String A gốc của protocol, không chỉnh sửa)

Collection: The ACM Full-Text Collection (852,537 records)

Search fields: Title, Abstract, Keywords

Year filter: chưa áp dụng (kết quả bằng 0)

Other filters: none

Query:

```
(Title:("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") OR Abstract:("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") OR Keyword:("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE"))
AND
(Title:("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") OR Abstract:("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") OR Keyword:("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis"))
AND
(Title:("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage") OR Abstract:("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage") OR Keyword:("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage"))
```

Reported results: 0
Retrieved records: 0
Notes: ACM phân tích query thành dạng [Title: ...] OR [Abstract: ...] OR [Keywords: ...] và trả về 0 kết quả ("did not return any results"). Chuỗi A có thể quá hẹp vì khối O chứa các cụm rất cụ thể. Không có export. Chưa thử "Expand your search to The ACM Guide to Computing Literature" (4,105,711 records). Dự kiến chạy String B (thêm từ đồng nghĩa, giữ cấu trúc P AND I AND O).

## Search S02

Date: 2026-10-09

Source: ACM Digital Library

URL: https://dl.acm.org

String ID: B (String A + từ đồng nghĩa, giữ cấu trúc P AND I AND O)

Collection: The ACM Full-Text Collection (852,537 records)

Search fields: Title, Abstract, Keywords

Year filter: chưa áp dụng (3 kết quả đều trong 2018 đến nay)

Other filters: none

Query:

```
(Title:("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "test case generation" OR "test design" OR "functional requirements" OR "PURE dataset") OR Abstract:("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "test case generation" OR "test design" OR "functional requirements" OR "PURE dataset") OR Keyword:("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "test case generation" OR "test design" OR "functional requirements" OR "PURE dataset"))
AND
(Title:("ChatGPT" OR "Claude" OR "large language model" OR "large language models" OR "LLM" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") OR Abstract:("ChatGPT" OR "Claude" OR "large language model" OR "large language models" OR "LLM" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") OR Keyword:("ChatGPT" OR "Claude" OR "large language model" OR "large language models" OR "LLM" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis"))
AND
(Title:("coverage item" OR "requirements coverage" OR "test coverage" OR "equivalence partition coverage" OR "boundary value coverage" OR "test adequacy") OR Abstract:("coverage item" OR "requirements coverage" OR "test coverage" OR "equivalence partition coverage" OR "boundary value coverage" OR "test adequacy") OR Keyword:("coverage item" OR "requirements coverage" OR "test coverage" OR "equivalence partition coverage" OR "boundary value coverage" OR "test adequacy"))
```

Reported results: 3
Retrieved records: 3
Notes: Thêm từ đồng nghĩa so với String A: khối P ("test case generation", "test design", "functional requirements", "PURE dataset"), khối I ("large language model", "large language models", "LLM"), khối O ("test coverage", "test adequacy"). ACM báo 3 kết quả, vẫn dưới 50. Dự kiến chạy String C (nới khối O).

## Search S03

Date: 2026-10-09

Source: ACM Digital Library

URL: https://dl.acm.org

String ID: C (String B, khối O được nới)

Collection: The ACM Full-Text Collection (852,549 records)

Search fields: Title, Abstract, Keywords

Year filter: 2018 – 2026 (áp dụng sau khi chạy query)

Other filters: none

Query:

```
(Title:("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "test case generation" OR "test design" OR "functional requirements" OR "PURE dataset") OR Abstract:("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "test case generation" OR "test design" OR "functional requirements" OR "PURE dataset") OR Keyword:("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "test case generation" OR "test design" OR "functional requirements" OR "PURE dataset"))
AND
(Title:("ChatGPT" OR "Claude" OR "large language model" OR "large language models" OR "LLM" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") OR Abstract:("ChatGPT" OR "Claude" OR "large language model" OR "large language models" OR "LLM" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") OR Keyword:("ChatGPT" OR "Claude" OR "large language model" OR "large language models" OR "LLM" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis"))
AND
(Title:("coverage" OR "test adequacy" OR "test effectiveness" OR "test quality") OR Abstract:("coverage" OR "test adequacy" OR "test effectiveness" OR "test quality") OR Keyword:("coverage" OR "test adequacy" OR "test effectiveness" OR "test quality"))
```

Reported results: 33 (trước khi lọc năm); <điền số sau khi lọc 2018–2026>
Retrieved records: <điền số dòng thực sự export được>
Notes: Khối P và I giữ nguyên String B; khối O nới thành "coverage", "test adequacy", "test effectiveness", "test quality". Dưới 50 kết quả nên dừng ở String C. Chưa chạy trên ACM Guide to Computing Literature (4,106,086 records), chờ PL quyết định.
