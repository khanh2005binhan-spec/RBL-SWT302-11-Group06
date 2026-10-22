# Snowballing cá nhân (một lượt, bước 7): đoạn dán vào `search-log.md`

## 1. Chọn seed

Seed: **R010** Xue et al., LLM4Fin, ISSTA 2024, DOI `10.1145/3650212.3680388` (nằm trong phần INCLUDE cá nhân của mình).

| Điều kiện | Kiểm tra | Kết quả |
|---|---|---|
| 1. Đã INCLUDE ở vòng 2 | `03_final_included.csv`: R010 INCLUDE | Đạt |
| 2. Sát RQ (near_rq từ 3/4 yếu tố) | near_rq = P I C O | Đạt |
| 3. Loại paper | Xuất bản 2024 (trong 3 năm gần nhất, tốt cho lướt tiến); 60 tài liệu tham khảo (đủ dài cho lướt lùi) | Đạt |
| 4. Số trích dẫn 10 đến 200 | OpenAlex: 30 | Đạt |

Lý do chọn seed: R010 là paper duy nhất trong phần của mình đạt đủ 4 điều kiện. R001 (3 trích dẫn) và R022 (4 trích dẫn) khớp nội dung hơn nhưng quá ít trích dẫn để lướt tiến.

## 2. Bảng snowballing (một lượt, không làm tiếp)

| Seed (DOI) | Vòng | Hướng | Số đã lướt | Số thêm vào 01 | Số include cuối |
|---|---|---|---|---|---|
| 10.1145/3650212.3680388 | 1 | lùi | 60 | 11 | 0 (2 chờ full-text) |
| 10.1145/3650212.3680388 | 1 | tiến | 8 (OpenAlex ghi 30) | 8 | 0 (3 chờ full-text) |

**Cách làm:**
- **Lùi:** lướt cả 60 tài liệu tham khảo của R010. Bỏ ngay các tài liệu trước 2020 (IC-Y), không phải paper (trang web, kho GitHub) hoặc tiêu đề không có từ nào của khối P hoặc I trong chuỗi search. 11 tài liệu còn lại được thêm vào `01_all_records.csv` với `source = snowball-back`. Chi tiết từng dòng: `snowball_backward_R010.csv`.
- **Tiến:** chưa mở được tab Citations của Semantic Scholar, nên tìm các bài trích dẫn R010 bằng tìm kiếm web và chỉ giữ bài có thể xác nhận đúng là trích dẫn R010 (qua danh mục tham khảo hoặc nội dung bài). Tìm được 8 bài, `source = snowball-fwd`. **Danh sách tiến chưa đầy đủ**: OpenAlex ghi 30 bài trích dẫn. Khi có danh sách "Cited by" từ Semantic Scholar hoặc OpenAlex thì lọc nốt, đúng một lượt.

**Kết quả vòng 1 (title/abstract, cùng IC/EC):**

| Hướng | EXCLUDE | Unsure |
|---|---|---|
| Lùi (11) | 9 (IC-P) | 2: Fischbach 2023 (acceptance test từ yêu cầu bằng NLP), Wang 2024 (survey kiểm thử bằng LLM) |
| Tiến (8) | 3 (IC-P) | 5: RAFT, Karmouda 2025, SLR 2026, LLMCFG-TGen, Folorunsho và Reza 2026 (survey) |

**Kết quả vòng 2 (full-text):** đã đọc 2 bài.
- RAFT (arXiv 2601.09762): EXCLUDE (IC-T), nhưng khớp P C O nên ghi vào danh sách ứng viên phản chứng.
- Folorunsho và Reza 2026 (arXiv 2606.06563): EXCLUDE (IC-T, bài tổng quan chỉ có bản arXiv); dùng làm bằng chứng gián tiếp cho gap ở `rq-check.md`.
- 5 bài còn lại chờ full-text: Fischbach 2023, Wang 2024, Karmouda 2025, SLR 2026, LLMCFG-TGen.

**Danh sách đã thêm vào 01:**
- Lùi: Fischbach 2023; Jiang 2023; Kang 2023; Lemieux 2023 (CodaMOSA); Liu 2023 (EvalPlus); Liu 2023 (prompting survey); Soman 2023; Vaithilingam 2022; Wang 2024; Wang 2023 (GPT-NER); Zamfirescu-Pereira 2023.
- Tiến: RAFT (2026); Karmouda 2025; SLR "Test case generation using LLMs" 2026; LLMCFG-TGen 2025; GERALLT 2025; DBMS MCTS 2026; Future Internet 2025; Folorunsho và Reza 2026.
