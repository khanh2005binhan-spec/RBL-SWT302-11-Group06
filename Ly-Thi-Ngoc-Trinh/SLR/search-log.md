# Search Log - OpenAlex

- **Nguồn:** OpenAlex
- **Ngày thực hiện:** 2026-10-09

## Các lần thử nghiệm chuỗi tìm kiếm (Search String):

1. **Lần 1 (Đầy đủ cả khối Metric):**
   - **Chuỗi:** `("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") AND ("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage")`
   - **Kết quả:** 0 works (Quá ít, do khắt khe quá)

2. **Lần 2 (Rút gọn, bỏ khối Metric - Bản chính thức):**
   - **Chuỗi:** `("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis")`
   - **Kết quả:** 1,157 works (Hợp lý, dùng số liệu này để tiếp tục sàng lọc)
3. **Lần 3 (Thêm bộ lọc "Since 2025" - Bản chính thức):**
   - **Chuỗi:** `("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis")` (kèm bộ lọc thời gian từ năm 2025 trở lại đây)
   - **Kết quả:** 554 works (Dùng số liệu này để xuất file `01_all_records.csv` phục vụ sàng lọc).
### Lần 4 (Tinh chỉnh chuyên sâu bám sát BDD/Gherkin và UAT - Bản chính thức):
- **Chuỗi truy vấn:** `("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "UAT") AND ("ChatGPT" OR "Claude" OR "GPT-4" OR "Anthropic" OR "equivalence partitioning" OR "boundary value analysis") AND ("software requirements" OR "requirements coverage" OR "behavior-driven development" OR "Gherkin")`
- **Bộ lọc áp dụng:** `Since 2025`
- **Kết quả:** `3 works` (Đây là tập kết quả chất lượng cao nhất, được chọn lọc chính xác để đưa vào file `02_after_screening_v1.csv` và `03_final_included.csv`).
