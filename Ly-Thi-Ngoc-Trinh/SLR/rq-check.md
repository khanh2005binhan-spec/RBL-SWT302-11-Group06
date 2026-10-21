# rq-check.md: Kiểm chứng RQ (RBL-2, Tuần 7), bản cá nhân

**RQ đăng ký:** For 20 frozen functional requirements from PURE, how do ChatGPT and Claude using the same one-shot EP–BVA prompt differ in coverage-item percentage relative to a human-designed test suite produced before viewing any AI output?

| | Nội dung RQ |
|---|---|
| P | Thiết kế test black-box (UAT) cho 20 yêu cầu chức năng cố định của PURE |
| I | ChatGPT và Claude, cùng một prompt one-shot (kèm 1 ví dụ) yêu cầu EP, BVA, điều kiện tiên quyết, bước test, kết quả mong đợi; mỗi công cụ chạy lặp 5 lần cho từng yêu cầu |
| C | Bộ test do người thiết kế trước khi xem kết quả AI |
| O | % coverage item (EP, BVA, DT, ST, UC) |

---

## Bước 1. Bảng đối chiếu paper với RQ

Dấu ✓ là khớp, ~ là khớp một phần, ✗ là không khớp. Nguồn: cột Gắn RQ trong `03_final_included.csv` và `evidence-table.md`.

**A. Paper cá nhân đã đọc full-text**

| ID | P (PURE, 20 yêu cầu) | I (ChatGPT + Claude, one-shot EP–BVA) | C (người lập trước khi xem AI) | O (coverage-item) | Khác RQ ở đâu |
|---|---|---|---|---|---|
| R001 | ~ UAT từ 8 yêu cầu, không PURE | ✓ ChatGPT và Claude; EP, BVA; prompt có ví dụ đầu ra | ~ tester người, chủ yếu so thời gian | ~ coverage % theo kỹ thuật, công thức khác | 8 yêu cầu, không PURE, chưa rõ baseline người lập trước |
| R010 | ~ acceptance test từ business rule tài chính | ~ GPT-4 có yêu cầu equivalence class và boundary value; không có Claude | ✓ 3 kỹ sư senior và 4 sinh viên | ~ business scenario coverage, code coverage | Domain tài chính; công cụ chính là LLM4Fin chứ không phải so ChatGPT với Claude |
| R022 | ~ acceptance test từ 16 yêu cầu, không PURE | ✓ Claude, ChatGPT; EP, BVA, UC, ST; zero-shot | ✓ gold standard do chuyên gia lập | ✓ % coverage theo kỹ thuật | Zero-shot (không one-shot), không PURE, chưa rõ gold standard lập trước hay sau khi xem AI |
| R128 | ~ BDD acceptance test từ 50 user story | ~ GPT-4 và Gemini 1.5; không EP/BVA, không Claude | ~ baseline thủ công về công sức | ✗ | Không đo coverage-item |
| R003 | ✓ PURE (79 SRS) | ✗ 5 LLM mở, không ChatGPT/Claude | ~ test người viết cho 1 SRS | ~ requirement coverage do LLM chấm | Không ChatGPT/Claude, không EP/BVA |
| R099 | ✓ một tài liệu PURE | ~ GPT-4 | ✗ | ✗ | Đo thời gian, không phải coverage |
| R006, R002, R014, R042, R038 | ~ | ~ hoặc ✗ | ✗ | ✗ | Không baseline người lập trước, không coverage-item |

