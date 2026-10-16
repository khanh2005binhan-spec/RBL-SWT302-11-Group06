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

String ID: A (String A gốc của protocol, không chỉnh sửa), chạy nguyên văn

Query:
("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") AND ("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage")

Search fields: không chọn được riêng Title/Abstract/Keywords trên web S2 (tìm toàn bộ metadata)

Year filter: không áp dụng ở lượt này

Other filters: none

Results displayed: 250

Status: KHÔNG HỢP LỆ. Trang hiện "Sorry, we couldn't find any papers about" rồi tự chạy lại bản "without quotes" (bỏ ngoặc kép, AND/OR coi như từ thường). Không tính vào PRISMA.

Reason / Action: web S2 không chạy được chuỗi dài; tách String A thành các cụm ngắn (S02–S07) theo hướng dẫn A2. Có ảnh chụp màn hình làm bằng chứng.

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

## Metadata export / Dedup (điền sau khi chạy)

- Tool: s2_fetch.py (Semantic Scholar Graph API), lệnh: ___
- Total API báo: ___ | Lấy được: ___ | Sau dedup: ___ | Lệch so với web và lý do: ___
- Kiểm chứng: (1) số bản ghi khớp web? ___ (2) đối chiếu 5 bản ghi ngẫu nhiên: ___ (3) chạy lại cùng query: ___
- Ô trống trước screening: doi=___ abstract=___ year=___
- Ghi vào 01_all_records.csv: ___ dòng (database = Semantic Scholar, source = search)

## Snowballing (A2b)

Seed (DOI): ___ | Backward: ___ | Forward: ___ | Thêm vào 01_all_records.csv: ___ dòng
