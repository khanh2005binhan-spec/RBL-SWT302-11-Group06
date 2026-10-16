## Semantic Scholar

### String A gốc (theo review-protocol.md)
("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") AND ("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage")

Bộ lọc: Computer Science, năm 2018 – nay. Ghi chú: web Semantic Scholar không lọc riêng Title/Abstract/Keywords.

### Lượt 0 – String A Trần Văn Thiện – KHÔNG HỢP LỆ
- Ngày chạy: 16/10/2026
- Kết quả hiển thị: 250
- Quan sát: trang hiện dòng "Sorry, we couldn't find any papers about" và tự chạy lại bản "without quotes" (bỏ ngoặc kép, coi AND/OR như từ thường). 250 bài là kết quả khớp lỏng, không phải bài thỏa cả 3 khối.
- Kết luận: không tính vào PRISMA; chuỗi dài không chạy được trên web S2 nên tách thành các cụm ngắn (theo A2). Có ảnh chụp màn hình làm bằng chứng.

### Các lượt query rút gọn (1 cụm mỗi khối của String A)
| # | Query (nguyên văn) | Ngày | Số kết quả | Hợp lệ? | Trước dedup | Sau dedup | Ghi chú / lý do chỉnh |
|---|---|---|---|---|---|---|---|
| 1 | "acceptance test generation" "ChatGPT" "requirements coverage" | 16/10/2026 | ___ | ___ | ___ | ___ | |
| 2 | "user acceptance testing" "equivalence partitioning" "coverage item" | | | | | | |
| 3 | "black-box test case generation" "Claude" "boundary value coverage" | | | | | | |
| 4 | "acceptance test generation" "boundary value analysis" "equivalence partition coverage" | | | | | | |
| 5 | "user acceptance testing" "one-shot prompting" "requirements coverage" | | | | | | |
| 6 | "PURE" "ChatGPT" "requirements coverage" | | | | | | |

"Hợp lệ?" = không có dòng "couldn't find any papers"; nếu có thì ghi "Không" và lý do.

### Lấy metadata qua API (nếu chạy s2_fetch.py)
- Lệnh: python s2_fetch.py bulk "<String A>" --year 2018-
- Chuỗi sau khi đổi cú pháp bulk (AND -> +, OR -> |): ___
- Total API báo: ___ | Lấy được: ___ | Sau dedup: ___
- Lệch so với web (nếu có) và lý do: ___

### Kiểm chứng công cụ
1. Số bản ghi script khớp số trên web? ___ (nếu lệch, giải thích)
2. Mở ngẫu nhiên 5 bản ghi, đối chiếu title/năm/DOI: ___
3. Chạy lại cùng query, số bản ghi: ___

### Ô trống trước screening
doi trống: ___ | abstract trống: ___ | year trống: ___

### Việc báo PL
- (nếu có) Lượt nào dưới ~50 kết quả hợp lệ: ___ -> đề xuất: ___ (PL quyết định)
