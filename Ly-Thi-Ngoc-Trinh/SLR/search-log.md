# Search Log: RQ EP–BVA UAT trên PURE (ChatGPT vs Claude)

**RQ:** For 20 frozen functional requirements from PURE, how do ChatGPT and Claude using the same one-shot EP–BVA prompt differ in coverage-item percentage relative to a human-designed test suite produced before viewing any AI output?

**Nguồn:** OpenAlex (openalex.org/works)
**Trường tìm kiếm:** title / abstract / keywords
**Người search:** <điền tên>

## Bảng tổng hợp các phiên bản

| Phiên bản | Ngày | Bộ lọc | Số hits | Ghi chú |
|---|---|---|---|---|
| v1 | 15/10/2026 | không | **0** | Chuỗi gốc của cô (3 khối P, I, O). Quá chặt vì khối O gồm các cụm quá hiếm |
| v2 | 15/10/2026 | không | **1.083** | Bỏ khối O (đúng thứ tự cô gợi ý). Quá nhiều |
| v3 | 15/10/2026 | Year 2020–2026 | **50** | Bỏ "PURE" (từ quá chung) + áp IC-Y. Sát ngưỡng dưới nên nới thêm |
| v4 | 15/10/2026 | Year 2020–2026 | **169** | Thêm "acceptance testing" vào khối P; thêm "large language model", "LLM", "GPT-4" vào khối I. **Bản chính thức** |

## Chuỗi search chính xác từng phiên bản

**v1 (0 hits)**
```
("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis") AND ("coverage item" OR "requirements coverage" OR "equivalence partition coverage" OR "boundary value coverage")
```

**v2 (1.083 hits)**
```
("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "PURE") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis")
```

**v3 (50 hits, Year 2020–2026)**
```
("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis")
```

**v4 (169 hits, Year 2020–2026) — CHÍNH THỨC**
```
("black-box test case generation" OR "acceptance test generation" OR "user acceptance testing" OR "acceptance testing") AND ("ChatGPT" OR "Claude" OR "one-shot prompting" OR "equivalence partitioning" OR "boundary value analysis" OR "large language model" OR "LLM" OR "GPT-4")
```

## Lý do thay đổi chuỗi

- **v1 → v2:** v1 trả về 0 hits vì khối O (`"coverage item"`, `"equivalence partition coverage"`...) là cụm rất hiếm. Theo hướng dẫn của cô, khi quá ít thì bỏ khối O.
- **v2 → v3:** 1.083 hits là quá nhiều (>500). Áp IC-Y (năm từ 2020, vì ChatGPT/LLM chỉ phổ biến từ giai đoạn này) và bỏ `"PURE"` vì là từ tiếng Anh thông dụng, kéo nhiều bài lạc đề.
- **v3 → v4:** 50 hits nằm sát ngưỡng dưới nên nới nhẹ bằng từ đồng nghĩa LLM và `"acceptance testing"` để không bỏ sót bài dùng cách gọi khác.
- **Khối C (baseline người) cố ý không đưa vào chuỗi** (chỉ thêm khi thật sự cần).

## Kết quả cuối

- **Chuỗi dùng chính thức:** v4
- **Số hits:** 169 (nằm trong khoảng 50–500)
- **File export:** `openalex_v4_2026-10-15.csv` (CSV từ nút tải xuống của OpenAlex)
- **Việc tiếp theo:** gộp vào `01_all_records.csv` của nhóm, rồi loại trùng và lọc vòng 1
