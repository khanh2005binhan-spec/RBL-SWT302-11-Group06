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

Year filter: Retrieved records: 3

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

Year filter: không áp dụng được trên ACM (Basic Edition khóa bộ lọc ngày); lọc năm ở V1 theo IC-Y, Reported results: 33, Retrieved records: 33

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

## Deduplication

Raw records: 36 (S02: 3, S03: 33)
Duplicates removed: 3 (cùng DOI: 10.1145/3822511, 10.1145/3832122, 10.1145/3644032.3644456)
Records after dedup: 33 (khớp số dòng của 01_all_records.csv)

## Screening vòng 1 (V1)

Date: 2026-10-09
Tiêu chí áp dụng: team-synthesis/ie_criteria.md (IC-P, IC-I, IC-O, IC-S, EC-1 đến EC-6)
Căn cứ: tiêu đề + phần đầu abstract trên trang kết quả ACM (abstract đầy đủ chưa có)

Records after dedup: 33
V1 INCLUDE: 3 (R007, R010, R030)
V1 UNSURE: 7 (R003, R004, R005, R008, R020, R024, R032)
V1 EXCLUDE: 23
Full-text assessed (INCLUDE + UNSURE): 10

Kiểm tra: 33 - 23 = 10 (khớp)

Ghi chú:
- ie_criteria.md không có tiêu chí năm; áp dụng khoảng năm 2018 đến nay của review-protocol.md. 3 bài trước 2018 (R021, R031, R033) bị loại bằng EC-2, có ghi chú thêm lý do năm trong v1_reason. Đã/sẽ đề nghị PL thêm mã năm vào ie_criteria.md.
- R015 và R017 bị loại bằng EC-3 vì chỉ dài 2 trang (pp. 76-77 và pp. 314-315).

## Kiểm tra metadata trước screening

Ô trống: doi = 1 (Boucher 2017, ACM không hiển thị DOI), abstract = 33/33, year = 0
Tác giả bị cắt trên trang ACM: R012, R017, R024, R029 (đã đánh dấu trong CSV)
Ghi chú: 5 trang Crossref bị rate limit (HTTP 429) nên không đọc được: 10.1145/3774748.3793625, 10.1145/3439961.3440002, 10.1145/3671016.3671404, 10.1145/3644032.3644454, 10.1145/3639478.3643087
Bài trước 2018 (sẽ loại ở V1 theo IC-Y): R021 (2016), R031 (2014), R033 (2017)
