# rq-check.md: Kiểm chứng RQ (RBL-2, Tuần 7), bản cá nhân

**Người thực hiện:** <họ tên, MSSV> · **Nhóm:** Group06
**Cơ sở bằng chứng (cá nhân):** `evidence-table.md` (11 paper INCLUDE từ search OpenAlex v4) và kết quả snowballing một lượt từ seed R010. Bảng nhóm `evidence-table-merged.md` chỉ dùng để đối chiếu ở Bước 1 (đánh dấu "bảng nhóm, chưa tự đọc").
**Trạng thái:** bản nháp. Còn 6 paper search chưa có full-text (R004, R029, R036, R072, R080, R103) và 5 paper snowballing chờ full-text.

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

**B. Paper tìm được khi snowballing (seed R010)**

| ID | P | I | C | O | Ghi chú |
|---|---|---|---|---|---|
| RAFT (arXiv 2601.09762, 2026), đã đọc full-text | ~ test tuân thủ quy định (tài chính, ô tô, năng lượng) | ~ GPT-5, Grok-4, DeepSeek-R1; EP/BVA qua LLM4Fin; không ChatGPT hay Claude | ✓ 3 kỹ sư senior viết test tay | ✓ BSC, precision, recall, F1 | Khớp P C O nên là ứng viên phản chứng. Loại theo IC-T vì chỉ có bản arXiv |
| Karmouda et al. 2025; Fischbach et al. 2023; Wang et al. 2024 (survey); LLMCFG-TGen; SLR 2026 | chưa đọc | chưa đọc | chưa đọc | chưa đọc | Chờ full-text vòng 2 |

**C. Đối chiếu nhanh với bảng nhóm** (chưa tự đọc; trạng thái trong bảng nhóm là PENDING, nên chỉ để định hướng)

| Paper trong bảng nhóm | Điểm đáng chú ý cho RQ | Cần kiểm tra |
|---|---|---|
| LLM comparison for test case generation from natural-language requirements (ISEC 2025) | So BARD, ChatGPT 3.5, ChatGPT 4o, Claude, Gemini, Llama 3 trên yêu cầu ngôn ngữ tự nhiên, ground truth viết tay, đo decision/condition/MC/DC coverage; ghi chú trong bảng nhóm: các LLM đều yếu ở yêu cầu phức tạp | Đọc full-text. Domain Simulink, không PURE, không EP/BVA |
| Leveraging Pre-Trained LLMs for On-Premises Comprehensive Automated Test Case Generation (ICIIBMS 2024) | Requirement-driven coverage đo thủ công; zero-shot 67,7%, one-shot 73,9% trên Llama-2-70B | Đọc full-text. Không ChatGPT/Claude |
| Large Language Model-Enhanced Test Case Generation (CBASE 2025) | So viết tay (coverage 98,1% với 60 yêu cầu đơn giản) và LLM cơ sở (62,8%) trên yêu cầu thật | Đọc full-text. LLM không nêu tên |

Lưu ý: bảng nhóm gắn dấu ⚑ cho hầu hết dòng (kể cả bài không liên quan như bài về cảm giác tội lỗi AI của sinh viên), nên mình không dùng dấu ⚑ làm căn cứ. Dòng nào mình dùng ở trên đều là dòng có nội dung đúng chủ đề.

**Kiểm tra từng yếu tố "đủ cả":** PURE + ChatGPT + Claude + cùng prompt one-shot EP–BVA + baseline người lập trước + coverage-item. Trong các paper cá nhân đã đọc không paper nào đủ cả sáu.

---

## Bước 2a. Có ai làm đúng RQ chưa?

> **Chọn một trong 4 kết luận mà cô cung cấp** (mình chưa thấy nội dung 4 kết luận; thay mục này khi có).

**Kết luận đề xuất:** chưa có paper nào làm đúng RQ, nhưng đã có paper làm gần đúng từng phần: R022 và R001 (so Claude với ChatGPT bằng EP/BVA và đo % coverage), R010 và RAFT (so LLM với người viết test, đo scenario coverage), R003 (dùng PURE). Chưa paper nào gộp được các phần này.

**Bằng chứng:** Bước 1 và cột Kết quả trong `evidence-table.md`.
**Giới hạn của kết luận:** mới dựa trên paper cá nhân; thiếu 6 paper search và 5 paper snowballing chưa đọc; forward snowballing mới tìm được 7 bài trích dẫn R010 (OpenAlex ghi 30), nên có thể sót.

---

## Bước 2b. Gap ban đầu và độ mạnh

**Gap ban đầu của nhóm:** chưa có nghiên cứu so sánh trực tiếp ChatGPT và Claude, cùng một prompt one-shot EP–BVA, trên yêu cầu PURE, với baseline người lập trước, đo bằng coverage-item.

**Hạn chế lặp lại giữa các paper** (nguồn: cột Hạn chế trong `evidence-table.md`; đếm trên 11 paper cá nhân):

| Hạn chế lặp lại | Paper | Số paper |
|---|---|---|
| Dữ liệu nhỏ hoặc lấy từ một công ty/nguồn | R001, R002, R014, R042, R003 | 5 |
| Không có baseline người lập độc lập, hoặc không nói rõ | R002, R006, R014, R042, R022 (chưa rõ) | 5 |
| Không đo coverage, hoặc đo bằng thước khác nhau (BSC, LLM chấm, F1, cú pháp) | R006, R003, R010, R128, R042 | 5 |
| Không so ChatGPT với Claude trực tiếp | R002, R003, R006, R010, R014, R038, R042, R099, R128 | 9 |

**Đánh giá độ mạnh của gap ban đầu:** yếu đến vừa. Từng điều kiện riêng lẻ đã có người làm (R022 và R001 so Claude với ChatGPT bằng EP/BVA; R010 và RAFT so LLM với người; R003 dùng PURE). Gap còn lại là tổ hợp các điều kiện cùng lúc (PURE, one-shot cố định, baseline người lập trước, coverage-item). Một người đánh giá có thể coi đây là bước mở rộng chứ không phải khoảng trống hoàn toàn. Bằng chứng ủng hộ tính mới: không paper nào trong số đã đọc nêu rõ thứ tự thời gian của baseline người.

> **Phát biểu gap theo đúng mẫu cô quy định** (chưa thấy mẫu; điền khi có):
> Gap 1: <điền theo mẫu>

---

## Bước 2c. Gap và RQ cho từng gap

| Gap | Phát biểu gap (dự thảo) | Mạnh hay yếu | RQ đo được |
|---|---|---|---|
| G1 (gap ban đầu) | Chưa có so sánh trực tiếp ChatGPT và Claude với cùng prompt one-shot EP–BVA trên yêu cầu PURE, có baseline người lập trước | Yếu đến vừa | RQ đã đăng ký |
| G2 (nếu đổi RQ) | Các paper đo coverage bằng nhiều thước khác nhau; chưa có so sánh theo từng loại coverage item (EP, BVA, DT, ST, UC) giữa hai LLM | Vừa | Với 20 yêu cầu PURE, ChatGPT và Claude khác nhau thế nào về % coverage theo từng loại item (EP, BVA, DT, ST, UC)? |
| G3 (nếu đổi RQ) | R022 và R001 cho thấy EP/BVA đơn giản gần bão hòa ở 100%; khác biệt chủ yếu ở kỹ thuật khó hơn (complex BVA ở R001, state transition ở R022) | Cần kiểm chứng | Ở các kỹ thuật khó (DT, ST, BVA phức tạp), ChatGPT và Claude khác nhau thế nào về % coverage item so với bộ test người? |

Lưu ý: G3 là quan sát từ vài paper, chưa phải kết luận. Nếu nhóm giữ G1, cần dự đoán trước rằng khác biệt EP/BVA có thể rất nhỏ (bão hòa), và chuẩn bị đo cả DT, ST, UC để RQ vẫn có tín hiệu.

---

## Bước 3. Khả thi

Chấm bằng số cụ thể của nhóm. Các ô <...> thay bằng số thật; cột "Ví dụ giả định" chỉ là con số mẫu để bạn thay.

| Hạng mục | RQ ban đầu (G1) | Ví dụ giả định (thay bằng số thật) |
|---|---|---|
| Số yêu cầu PURE | 20 (đã khóa) | |
| Công cụ | ChatGPT, Claude (phiên bản: <điền>) | |
| Số lượt sinh test | 2 công cụ × 20 yêu cầu × 5 lần = 200 | 200 lượt × 2 phút = khoảng 6,7 giờ |
| Bộ test người | 20 yêu cầu × <số phút/yêu cầu> × <số người> | 20 × 10 phút = khoảng 3,3 giờ/người |
| Chấm coverage-item | 200 bộ × <số phút/bộ> | 200 × 5 phút = khoảng 16,7 giờ |
| Thống kê | Wilcoxon theo cặp (hai điều kiện); Cochran Q hoặc Friedman nếu nhiều điều kiện | |
| Mini-pilot 5–10 mẫu để chốt ngưỡng chấp nhận | <số giờ> | |
| **Tổng giờ / nhóm** | <...> | khoảng 27 giờ (chia theo số thành viên) |
| **Kết luận khả thi** | <làm được / cần thu hẹp> | |

**Rủi ro cần ghi:** baseline người phải lập trước khi xem kết quả AI (cần bằng chứng thời gian, ví dụ commit); dữ liệu PURE lấy từ Zenodo (79 tài liệu, CC BY 4.0).

---

## Kết quả snowballing (seed R010, một lượt)

| Hướng | Đã lướt | Thêm vào 01 | Loại vòng 1 | Vào full-text | Loại vòng 2 | Include cuối |
|---|---|---|---|---|---|---|
| Lùi (60 tài liệu tham khảo) | 60 | 11 | 9 | 2 (Fischbach 2023, Wang 2024) | chưa đọc | chưa chốt |
| Tiến (tìm qua web) | 7 (OpenAlex ghi 30) | 7 | 3 | 4 | 1 (RAFT, IC-T) | chưa chốt |

Chi tiết lùi: `snowball_backward_R010.csv`. Cập nhật tại `01_all_records.csv`, `02_after_screening_v1.csv`, `03_final_included.csv`.

---

## Hạn chót

Mọi thay đổi RQ phải xong trước khi giảng viên khóa (hết buổi 1 của Tuần 7).

## Việc còn thiếu

1. Điền kết luận và mẫu gap theo mẫu của cô (mục "3 câu hỏi và 4 kết luận" và "Gap là gì, vì sao tìm từ hạn chế").
2. Điền số liệu nhóm ở Bước 3.
3. Đọc 6 paper search còn thiếu, 5 paper snowballing chờ full-text, và 3 dòng đối chiếu trong bảng nhóm; rồi cập nhật Bước 1.
4. Hoàn tất forward snowballing: xuất danh sách "Cited by" của R010 (Semantic Scholar hoặc OpenAlex) để lọc nốt.
