# Search Log: Semantic Scholar

## Protocol snapshot (từ team-synthesis/review-protocol.md)
- RQ: For 20 frozen functional requirements from PURE, how do ChatGPT and Claude using the same one-shot EP–BVA prompt differ in coverage-item percentage relative to a human-designed test suite produced before viewing any AI output?
- Year range: 2018 – present
- Search fields: Title, Abstract, Keywords
- Dedup: DOI (lowercase, normalized); secondary: normalized title + first author + year
- Screening: Pass 1 (title/abstract) → Pass 2 (full text)
- Snowballing: max 2 rounds, Semantic Scholar / Crossref API; candidates must pass V1 and V2
- IC/EC: xem team-synthesis/ie_criteria.md

## Search S01

Date: 2026-10-16

Source: Semantic Scholar (web)

URL: https://www.semanticscholar.org

String ID: A (String A gốc của protocol, không chỉnh sửa)

Search fields: không chọn được riêng Title/Abstract/Keywords trên web S2

Year filter: không áp dụng

Other filters: none

Query:
(“black-box test case generation” OR “acceptance test generation” OR “user acceptance testing” OR “PURE”) AND (“ChatGPT” OR “Claude” OR “one-shot prompting” OR “equivalence partitioning” OR “boundary value analysis”) AND (“coverage item” OR “requirements coverage” OR “equivalence partition coverage” OR “boundary value coverage”)

Reported results: 250 (không hợp lệ)
Retrieved records: 0
Notes: S2 báo "couldn't find any papers" rồi tự chạy lại bản không ngoặc kép, nên 250 chỉ là khớp lỏng. Web S2 không chạy được chuỗi dài, tách String A thành cụm ngắn S02–S07 (mỗi khối 1 cụm). Có ảnh chụp.

## Search S02–S07 (String A tách ngắn)

Date: 2026-10-16
Source: Semantic Scholar (web) | Filters: Computer Science, năm 2018–2026

| ID | Query | Reported results | Hợp lệ |
|---|---|---|---|
| S02 | "acceptance test generation" "ChatGPT" "requirements coverage" | 4 | Có |
| S03 | "user acceptance testing" "equivalence partitioning" "coverage item" | 2 | Có |
| S04 | "black-box test case generation" "Claude" "boundary value coverage" | 58 | Không (couldn't find any papers) |
| S05 | "acceptance test generation" "boundary value analysis" "equivalence partition coverage" | 23 | Không (như S04) |
| S06 | "user acceptance testing" "one-shot prompting" "requirements coverage" | 2 | Có |
| S07 | "PURE" "ChatGPT" "requirements coverage" | 54 | Có (nhiều nhiễu) |

Notes: S04, S05 không tính vào PRISMA. Phần lớn lượt hợp lệ < 50 kết quả; đề xuất thêm từ đồng nghĩa hoặc nới khối O, chờ PL quyết định (chưa đổi String A).

## Export & Deduplication

Cách export: file BibTeX từ S2 (web không xuất CSV), chuyển sang 01_all_records.csv bằng bib_to_csv.py; bổ sung abstract/DOI bằng enrich_s2.py (Colab, 2026-10-19, tra được 41/54).
Raw records: 54
Duplicates removed: 0
Records after dedup: 54 (khớp số dòng của 01_all_records.csv)

## Kiểm tra metadata trước screening

Ô trống: doi = 1 (R003), abstract = 16/54, year = 0
Ghi chú: abstract thiếu thì không loại chỉ vì thiếu metadata, đánh Unclear và lấy thêm thông tin.
Kiểm chứng công cụ: số bản ghi khớp web: ___ | đối chiếu 5 bản ghi ngẫu nhiên: ___ | chạy lại script: ___

## Screening vòng 1 (V1)

Date: 2026-10-20
Tiêu chí áp dụng: team-synthesis/ie_criteria.md (IC1–IC4, EC1–EC6; bản nháp chờ nhóm duyệt)
Căn cứ: title + abstract (abstract thiếu ở 16/54)

Records after dedup: 54
V1 INCLUDE: 10 (R012, R013, R014, R015, R018, R024, R035, R037, R042, R054)
V1 UNCLEAR: 2 (R008, R040)
V1 EXCLUDE: 42
Full-text assessed (INCLUDE + UNCLEAR): 12

Kiểm tra: 54 - 42 = 12 (khớp)

Ghi chú:
- Năm 2018 đến nay lấy từ review-protocol.md; bài trước 2018: 0.
- R008, R040: title khớp IC1 + IC2 nhưng thiếu abstract, để Unclear, chưa quyết định.
- Lý do giữ cần bổ sung ở v1_reason: R012, R013, R018, R037, R054; R014, R035 (RE dùng dữ liệu PURE); R042 (NLP, không LLM).

## Screening vòng 2 (V2)

Date: ___
Records vào V2: 12 | V2 INCLUDE: 10 (file 03) | Chưa quyết: 2 (R008, R040) | V2 EXCLUDE: ___ | Không lấy được full-text: ___
