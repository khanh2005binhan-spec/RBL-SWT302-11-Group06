# Search Log: Semantic Scholar

## Protocol snapshot (từ team-synthesis/review-protocol.md)

- RQ: For 20 frozen functional requirements from PURE, how do ChatGPT and Claude using the same one-shot EP–BVA prompt differ in coverage-item percentage relative to a human-designed test suite produced before viewing any AI output?
- Year range: 2018 – present
- Search fields: Title, Abstract, Keywords
- Dedup: DOI (lowercase, normalized); secondary: normalized title + first author + year
- Screening: Pass 1 (title/abstract) → Pass 2 (full text)
- Snowballing: max 2 rounds, Semantic Scholar / Crossref API; candidates must pass V1 and V2
- IC/EC: xem team-synthesis/ie_criteria.md

## Search S01 – String A nguyên văn (KHÔNG HỢP LỆ)

Date: 2026-10-16

Source: Semantic Scholar (web)

URL: https://www.semanticscholar.org

String ID: A (String A gốc của protocol, không chỉnh sửa)

Query:
("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") AND ("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage")

Search fields: không chọn được riêng Title/Abstract/Keywords trên web S2 (tìm toàn bộ metadata)

Year filter: không áp dụng ở lượt này

Other filters: none

Results displayed: 250

Status: KHÔNG HỢP LỆ. Trang hiện "Sorry, we couldn't find any papers about" rồi tự chạy lại bản "without quotes" (bỏ ngoặc kép, AND/OR coi như từ thường). Không tính vào PRISMA.

Action: web S2 không chạy được chuỗi dài; tách String A thành các cụm ngắn (S02–S07) theo hướng dẫn A2. Có ảnh chụp màn hình làm bằng chứng.

## Searches S02–S07 (String A tách thành cụm ngắn; mỗi lượt 1 cụm mỗi khối)

Date: 2026-10-16 | Source: Semantic Scholar (web) | String ID: A-split
Filters: Fields of Study = Computer Science; Date Range = 2018–2026

| ID | Query (nguyên văn) | Results | Valid? | Notes |
|---|---|---|---|---|
| S02 | "acceptance test generation" "ChatGPT" "requirements coverage" | 4 | Yes | Ảnh chụp ban đầu lọc 2019–2025; cần xác nhận lại với 2018–2026. Bài cũ nhất 2019 |
| S03 | "user acceptance testing" "equivalence partitioning" "coverage item" | 2 | Yes | 1 bài sát, 1 bài lạc đề |
| S04 | "black-box test case generation" "Claude" "boundary value coverage" | 58 | No | "couldn't find any papers"; tự chạy lại không ngoặc kép |
| S05 | "acceptance test generation" "boundary value analysis" "equivalence partition coverage" | 23 | No | Như S04 |
| S06 | "user acceptance testing" "one-shot prompting" "requirements coverage" | 2 | Yes | 1 bài sát, 1 bài ít liên quan |
| S07 | "PURE" "ChatGPT" "requirements coverage" | 54 | Yes | Nhiều nhiễu vì "PURE" khớp từ thông thường |

Nhận xét: phần lớn lượt hợp lệ < 50 kết quả. Đề xuất (chờ PL quyết định, chưa đổi String A): thêm từ đồng nghĩa hoặc bớt khối coverage. Mọi thay đổi sẽ ghi lý do và ngày vào log này.

## Metadata export / Dedup

- Date: 2026-10-16
- Cách export: file BibTeX (citation.bib) từ Semantic Scholar; web S2 không xuất hàng loạt qua CSV nên chuyển .bib sang 01_all_records.csv bằng script bib_to_csv.py (không viết tay bản ghi).
- Nguồn bản ghi: kết quả các lượt hợp lệ (S02, S03, S06, S07) gộp lại; chưa gắn cột query cho từng bản ghi
- Số bản ghi trong .bib: 54
- Sau dedup trong lượt (DOI; nếu không có thì tiêu đề chuẩn hóa + năm): 54 (không bỏ bản ghi nào; có 2 bài trùng khóa Li2025HowMC nhưng là 2 bài khác nhau nên giữ cả hai)
- Ghi vào 01_all_records.csv: 54 dòng (database = Semantic Scholar, source = search, record_id R001–R054)

### Metadata ngay sau khi chuyển từ .bib
- Ô trống: doi=54, abstract=54, year=0, venue=0, authors=1 (R007)
- Nhận xét: .bib của Semantic Scholar không có DOI và abstract; url là link CorpusID.

### Bổ sung DOI
- Đã điền 13 DOI có căn cứ: R008, R042 (xác minh trên trang nguồn); R002, R009, R012, R016, R017, R019, R033, R034, R040, R048, R051 (DOI arXiv dạng 10.48550/arXiv.<mã>, đã đối chiếu mã arXiv với tiêu đề/tác giả/năm)
- Còn trống doi: 41/54 → bổ sung bằng enrich_s2.py (Semantic Scholar API theo CorpusID); bài nào API không có thì ghi "không có DOI"
- Lưu ý R042: Semantic Scholar ghi năm 2019, OpenAlex ghi 2020; thống nhất giá trị năm: ___ (cả hai ≥ 2018)
- Lưu ý R002: tiêu đề arXiv hiện tại khác tiêu đề trong .bib ("ChatGPT" vs "Chatbots") nhưng cùng bài (cùng mã arXiv và tác giả)

### Bổ sung abstract/doi qua API (enrich_s2.py)
- Chạy lúc: ___ | Tra được: ___ / 54
- Ô trống sau bổ sung: doi=___ abstract=___
- Quy ước: abstract vẫn trống thì đánh dấu Unsure ở V1 (không EXCLUDE chỉ vì thiếu abstract)

### Kiểm chứng công cụ
1. Số bản ghi khớp số kết quả web? ___ (54 là tổng gộp các lượt hợp lệ đã lưu, không phải riêng một lượt)
2. Mở ngẫu nhiên 5 bản ghi, đối chiếu title/năm/DOI với trang gốc: ___ (R012 đã kiểm: đúng)
3. Chạy lại script, kết quả giống lần đầu? ___

### Ghi chú
- Cột query chưa điền cho từng bản ghi vì .bib không lưu thông tin lượt tìm; sẽ đối chiếu tiêu đề với kết quả S02/S03/S06/S07: ___
- Danh sách có nhiều bài không liên quan (y tế, giáo dục...), nhất là từ lượt S07 ("PURE"); loại ở V1 theo IC/EC.
- Bộ lọc năm 2018–nay đã áp dụng trên web; trong .bib không có bài trước 2018.

## Screening V1 (title/abstract) → 02_after_screening_v1.csv

- Date: 2026-10-16
- Input: 01_all_records.csv (54 bản ghi)
- Tiêu chí: IC/EC theo team-synthesis/ie_criteria.md
- Cách làm: dựa trên title; abstract chưa bổ sung đủ nên bài chưa rõ đánh UNSURE
- Cột thêm: v1_decision (INCLUDE / EXCLUDE / UNSURE), v1_reason

| Số bản ghi | Giá trị |
|---|---|
| Vào V1 (sau dedup) | 54 |
| EXCLUDE ở V1 | 48 |
| INCLUDE ở V1 | 2 (R015, R024) |
| UNSURE ở V1 | 4 (R008, R014, R035, R040) |
| Chuyển sang V2 (full-text) | 6 |

- Lý do EXCLUDE chủ yếu: không thuộc chủ đề (không phải sinh test/UAT bằng LLM từ yêu cầu): IC-P/IC-I; một số bài lý do riêng (R042 không dùng LLM; R032 thuật toán tối ưu test; R020 ngôn ngữ/không liên quan)
- Rà lại 6 bài INCLUDE/UNSURE sau khi có abstract: ___
- Bài tiềm năng liên quan bị loại ở V1 (nếu có) và lý do: ___
- Người rà soát V1: ___ | Ngày hoàn tất: ___

## Snowballing (A2b)

Chưa thực hiện (theo kế hoạch ngày 4). Seed (DOI): chưa chọn | Backward: chưa chạy | Forward: chưa chạy | Thêm vào 01_all_records.csv: 0 dòng
