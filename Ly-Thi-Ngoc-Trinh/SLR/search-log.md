# Search Log - Nhật ký tìm kiếm tài liệu SLR

## 1. Thông tin chung
- **Đề tài:** FA26-W4-11 (So sánh ChatGPT/Claude khi thiết kế test UAT theo EP–BVA trên PURE).
- **Cơ sở dữ liệu sử dụng:** OpenAlex.
- **Thời gian thực hiện tìm kiếm:** Tháng 10/2026.

## 2. Các lần tìm kiếm chính thức (Search String)

### Lần 1 (Tìm kiếm diện rộng ban đầu):
- **Chuỗi truy vấn:** `("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis")`
- **Bộ lọc:** Since 2025 (Từ năm 2025 trở lại đây)
- **Kết quả:** `546 works`
- **Mục đích:** Dùng số liệu này để xuất file 01_all_records.csv phục vụ sàng lọc.

### Lần 2 (Tinh chỉnh chuyên sâu bám sát BDD/Gherkin và UAT - Bản chính thức):
- **Chuỗi truy vấn:** `("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "UAT") AND ("ChatGPT" OR "Claude" OR "GPT-4" OR "Anthropic" OR "equivalence partitioning" OR "boundary value analysis") AND ("software requirements" OR "requirements coverage" OR "behavior-driven development" OR "Gherkin")`
- **Bộ lọc:** Since 2025
- **Kết quả:** `3 works`
- **Mục đích:** Đây là tập kết quả tinh gọn và chất lượng cao nhất, được chọn lọc để đưa vào file sàng lọc cuối cùng (03_final_included.csv) và phân tích chuyên sâu.
