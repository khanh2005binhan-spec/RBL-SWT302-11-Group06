# Evidence Table: RQ EP–BVA UAT trên PURE (ChatGPT vs Claude)

**RQ:** For 20 frozen functional requirements from PURE, how do ChatGPT and Claude using the same one-shot EP–BVA prompt differ in coverage-item percentage relative to a human-designed test suite produced before viewing any AI output?

**Phạm vi:** 11 paper INCLUDE ở vòng 2 (nguồn: search OpenAlex v4). 6 paper chưa có full-text (R004, R029, R036, R072, R080, R103) sẽ bổ sung sau. Snowballing chưa làm.
**PICO của RQ:** P = thiết kế test black-box (UAT) cho 20 yêu cầu chức năng PURE. I = ChatGPT và Claude, cùng một prompt one-shot yêu cầu EP, BVA, điều kiện tiên quyết, bước test, kết quả mong đợi. C = bộ test do người thiết kế trước khi xem kết quả AI. O = % coverage item (EP, BVA, DT, ST, UC).

---

## Bảng 1. Đặc điểm nghiên cứu

| ID | Nghiên cứu | Năm | Nơi đăng | Loại | Bản đã đọc | DOI | Trích dẫn |
|---|---|---|---|---|---|---|---|
| R001 | Sisomboon et al., AI-Driven Prompt Templates for UAT Case Generation | 2024 | Springer CCIS (kỷ yếu), tr. 78–92 | conference | Bản xuất bản | 10.1007/978-981-97-9793-6_6 | 3 |
| R002 | Ferreira et al., Acceptance Test Generation with LLMs: An Industrial Case Study | 2025 | IEEE/ACM AST 2025 | conference | arXiv v1 (bài đã xuất bản AST) | 10.1109/ast66626.2025.00007 | 14 |
| R003 | Varpe et al., User Acceptance Test Case Generation Using LLMs | 2025 | IEEE CASCON 2025 | conference | Bản xuất bản | 10.1109/cascon66301.2025.00084 | 1 |
| R006 | Karpurapu et al., Comprehensive Evaluation... BDD Acceptance Test Formulation | 2024 | IEEE Access | journal | Bản xuất bản | 10.1109/access.2024.3391815 | 32 |
| R010 | Xue et al., LLM4Fin | 2024 | ACM ISSTA 2024 | conference | Bản xuất bản | 10.1145/3650212.3680388 | 30 |
| R014 | Fonseca et al., Streamlining Acceptance Test Generation for Mobile Apps (AToMIC) | 2025 | IEEE/ACM ASE 2025 | conference | arXiv v1 (bài đã xuất bản ASE) | 10.1109/ase63991.2025.00273 | 2 |
| R022 | Sisomboon et al., Automated Software Test Case Generation Using Directional Partially Weighted Ensemble LLMs With RAG | 2026 | IEEE Access | journal | Bản xuất bản | 10.1109/access.2026.3667925 | 4 |
| R038 | Intana et al., BlackBoxTestGen | 2026 | Computers (MDPI) | journal | Bản xuất bản | 10.3390/computers15050263 | 0 |
| R042 | Pereira et al., APITestGenie | 2026 | ACM/IEEE AST 2026 | conference | Bản xuất bản | 10.1145/3793654.3793743 | 0 |
| R099 | Li and Zheng, Enhancing Requirements via Structured Formalization... LLM-Assisted Test-Driven Framework | 2025 | IET Software | journal | Bản xuất bản | 10.1049/sfw2/6714956 | 3 |
| R128 | Almeyda Alania et al., Engineering Prompt-Orchestrated LLM Workflows... Agile | 2025 | IJACSA 16(12) | journal | Bản xuất bản | 10.14569/ijacsa.2025.0161272 | 1 |

---

## Bảng 2. Trích xuất PICO

| ID | P: nhiệm vụ và dữ liệu | I: công cụ, kỹ thuật, prompt | C: đối chứng | O: chỉ số | near_rq |
|---|---|---|---|---|---|
| R001 | Sinh UAT từ 8 yêu cầu chức năng thật (công ty kiểm thử Thái Lan). Không phải PURE | 5 công cụ: GPT-3.5, GPT-4(o), Gemini 1.5, Claude 2, Copilot. Prompt template (Task, Context, Role, Format...) + user story + ví dụ đầu ra. Kỹ thuật BVA, EP, complex BVA, use case, state transition | Tester người (so thời gian xử lý) | % test coverage theo kỹ thuật; accuracy, precision, recall, F1; thời gian | P I C O |
| R002 | Sinh kịch bản Gherkin từ user story, rồi script Cypress cho web app, dự án thật | GPT-4 Turbo (AutoUAT, Test Flow). Không EP/BVA | Không có | Mức hữu ích do người dùng đánh giá; tỷ lệ test dùng được | P |
| R003 | Sinh UAT từ SRS thuộc PURE (79 tài liệu) | 5 LLM mở (Gemma, LLaMA3, Mistral, Phi, Qwen). Zero-shot, prompt tự tối ưu 2 giai đoạn, tối đa 10 chu kỳ | Test case người viết cho 1/79 SRS (BERTScore) | Số test case; requirement coverage (LLM-as-judge); BERTScore | P O |
| R006 | Sinh BDD acceptance test (Gherkin) từ khoảng 50 user story | GPT-3.5-turbo, GPT-4, Llama-2-13B, PaLM-2. Zero-shot và few-shot (1 ví dụ), cùng 6 chỉ dẫn | Không có | Tỷ lệ file hợp lệ cú pháp (gherkin-lint) | P I |
| R010 | Sinh test case acceptance cho phần mềm chứng khoán từ business rule; 5 dataset (8–13 rule, 12–400 business scenario) | LLM4Fin (Mengzi tinh chỉnh + thuật toán SMT dùng BVA và EP) so với GPT-4 (prompt công phu yêu cầu equivalence class, boundary value) và ChatGLM | 3 kỹ sư senior (5–7 năm) và 4 sinh viên cao học | Business Scenario Coverage (BSC); code coverage (SBC, MC/DC); thời gian | P I C O |
| R014 | Sinh Gherkin, PageObject và UI test từ ticket JIRA và code thay đổi; app MyBMW (13 issue) | LLM chuyên biệt trong framework AToMIC. Không EP/BVA | Không có (khảo sát tiết kiệm thời gian) | Tỷ lệ đúng cú pháp, chạy được không sửa, thời gian | P |
| R022 | Sinh acceptance test từ yêu cầu (dataset mới, được 3 tester kiểm tra). Không phải PURE | Claude, ChatGPT, Gemini, Qwen, Mistral. Prompt zero-shot PARTS + user story. 16 tiêu chí từ BVA, EP, UC, ST. Đề xuất ensemble có trọng số + RAG | Gold standard acceptance criteria do chuyên gia lập | % test coverage theo kỹ thuật; precision, recall, F1 | P I C O |
| R038 | Sinh test case black-box từ đặc tả (data dictionary, decision tree, state machine) | Rule-based ECP, syntax testing, state transition. Không dùng LLM | Test suite thủ công của chuyên gia | Độ chính xác; coverage cộng dồn; hiệu năng, khả năng mở rộng | P O |
| R042 | Sinh script test tích hợp API từ business requirement và OpenAPI; 10 API (8 từ đối tác ô tô, ~1.000 endpoint), 25 requirement | GPT-4-Turbo + RAG, prompt một lượt theo TELeR | EvoMaster (1 API); ước tính làm tay 20–30 phút/test | Tỷ lệ script hợp lệ; thời gian; chi phí | P |
| R099 | Sinh use case specification và test case acceptance từ yêu cầu; một tài liệu PURE (GAMMA-J Web Store) | GPT-4 trong vòng lặp có người duyệt | Làm tay đặc tả (nhóm kỹ sư junior, senior) | Thời gian; số lần chỉnh prompt; nhất quán với mô hình quy trình | P I |
| R128 | Sinh BDD acceptance test từ 50 user story trong Product Backlog | Gemini 1.5 + GPT-4 (AIDTG), prompt nhúng schema CSDL | Baseline thủ công (về công sức) | Giảm công sức; điểm chuyên gia; đúng chức năng | P I C |

---

## Bảng 3. Kết quả chính

| ID | Kết quả định lượng đã đọc | Ghi chú |
|---|---|---|
| R001 | EP: coverage 100% ở mọi công cụ. BVA: 100% trừ Copilot. F1 tổng: ChatGPT-4o 0,68, ChatGPT-3.5 0,68, Claude 2 0,60, Gemini 0,58, Copilot 0,57. Complex BVA: ChatGPT-4o 0,80, Claude 2 0,50. Use case: F1 0,50 ở cả 5 công cụ. State transition: ChatGPT-3.5 0,67, Claude 2 0,50. Nhờ 3 người viết prompt khác nhau, BVA coverage thay đổi từ 100% xuống 81,67% | AI xử lý nhanh hơn tester người; một tester không hoàn thành state transition |
| R002 | 95% kịch bản Gherkin được đánh giá hữu ích. Test Cypress: 92% hữu ích (60% dùng ngay, 8% sửa nhỏ, 24% sinh lại, 8% bỏ) | Không đo coverage |
| R003 | Số test case: Gemma 1856, LLaMA3 764, Mistral 612, Qwen 575, Phi 543. Requirement coverage sau 10 chu kỳ: Gemma 72%, LLaMA3 72%, Mistral 50%, Phi 33%, Qwen 25%. BERTScore F1 (1 SRS): Qwen 0,806, Gemma 0,801, Phi 0,779, Mistral 0,759, LLaMA3 0,756 | Coverage do Gemini 2.5 chấm |
| R006 | Lỗi cú pháp: zero-shot 667 (89%) so với few-shot 80 (11%). GPT-3.5: 7 → 1; GPT-4: 6 → 1; PaLM-2: 189 → 49; Llama-2-13B: 465 → 29 | Tác giả nói rõ chưa đo coverage |
| R010 | BSC trung bình: LLM4Fin 91,89%, Experts 75,16%, ChatGPT 49,65%, Non-experts 43,46%, ChatGLM 41,63%. SBC: LLM4Fin 93,72, ChatGPT 87,61, Experts 86,90, Non-experts 71,01. MC/DC: LLM4Fin 90,86, Experts 82,30, ChatGPT 81,76, Non-experts 64,06. Thời gian: LLM4Fin ~7 giây, ChatGPT ~19 phút, Experts ~34 phút | Code coverage chỉ đo trên dataset 5 |
| R014 | 93,3% Gherkin đúng cú pháp; 78,8% PageObject chạy không cần sửa; 100% UI test chạy được; dưới 5 phút mỗi feature | Không đo coverage |
| R022 | EP: 100% ở mọi mô hình. BVA: 100% ở từng mô hình. UC: khoảng 95,83% (Mistral 91,67%). ST: Claude 100%, ChatGPT 100%, Gemini 66,67%, Qwen 50%, Mistral 50%. Ensemble 3 mô hình: 93,2% tổng; ensemble đề xuất đạt 98,44% | Bài ghi hai số recall khác nhau cho Claude (0,74 và 0,79); cần đọc lại bảng gốc |
| R038 | Precision 98,11% (OSPS) và 96,67% (SSMS); sau khi chỉnh cùng chuyên gia, test case sinh lại khớp hoàn toàn test suite thủ công | Không có LLM |
| R042 | 52/75 lần sinh hợp lệ (69,3%); 22/25 requirement (88,6%) có ít nhất 1 script hợp lệ trong 3 lần. API ít phức tạp 87,5% so với 60,8% (p = 0,038). Requirement có dữ liệu cụ thể 88,9% so với 63,2% (p = 0,039). Trung bình 126 giây và 0,37 € mỗi lần sinh | Không so Claude, không đo coverage-item |
| R099 | Nhóm dùng LLM tiết kiệm thời gian so với làm tay ở mọi mức kinh nghiệm; số lần chỉnh prompt: junior 11, senior 7 | Chưa trích số coverage |
| R128 | Giảm 80% công sức thiết kế test; điểm chuyên gia 4,75/5; 91,9% script đúng chức năng | Không đo coverage-item |

---

## Bảng 4. Hạn chế, độ tin cậy và liên quan tới RQ

| ID | Hạn chế và nguy cơ sai lệch | Liên quan tới RQ |
|---|---|---|
| R001 | Chỉ 8 yêu cầu. Công thức coverage của bài (x = số test case sinh ra, y = số test case đáp án) không phải coverage-item. Claude 2 đã cũ. Kết quả phụ thuộc người viết prompt | Cao: cùng thiết kế so ChatGPT với Claude, EP/BVA, so với người |
| R002 | Đánh giá chủ quan của người dùng, không baseline | Thấp: cùng bối cảnh acceptance test |
| R003 | Ground truth chỉ 1 SRS; coverage do LLM chấm; không dùng ChatGPT hay Claude | Trung bình: cùng dataset PURE |
| R006 | Chỉ đo cú pháp, một công cụ lint, không đo nội dung | Thấp: so sánh zero-shot và few-shot |
| R010 | Domain tài chính, một hệ thống; không có Claude; prompt ChatGPT soạn theo từng quy tắc | Cao: so LLM với người, đo coverage, dùng EP/BVA |
| R014 | Không baseline, tự báo cáo | Thấp |
| R022 | Dataset không phải PURE; prompt zero-shot; chưa rõ gold standard lập trước khi xem kết quả AI | Rất cao: có cả Claude và ChatGPT, EP/BVA/UC/ST, coverage % theo kỹ thuật |
| R038 | Không dùng LLM | Thấp: định nghĩa và cách tính coverage cho ECP |
| R042 | Test API, không phải UAT từ yêu cầu chức năng; không đo coverage-item | Thấp |
| R099 | Có người duyệt trong vòng lặp; mẫu nhỏ; đo thời gian chứ không đo coverage | Trung bình: có dùng PURE |
| R128 | Mẫu 50 user story; baseline chỉ về công sức; không EP/BVA | Thấp |

---

## Bảng 5. Loại sau khi đọc full-text

| ID | Nghiên cứu | Mã | Lý do |
|---|---|---|---|
| R005 | XUAT-Copilot (Wang et al.) | IC-T | Chỉ có bản arXiv; sinh script ADB chạy UAT, không thiết kế test case |
| R007 | Prompting LLMs for the Full SDLC (DevEval) | IC-P | Benchmark vòng đời phần mềm; acceptance test dùng để chấm code, không sinh test từ yêu cầu |
| R019 | Exploring LLMs Impact on Student-Created User Stories | EC-S | Poster 2 trang; nội dung là user story |
| R084 | Automated Black-Box Testing: LLM Agent Architectures | IC-P | Unit test hàm trên HumanEval bằng Nemotron nano, không phải UAT |
| R127 | LLM-as-a-Judge for Scalable Test Coverage Evaluation | IC-P | Đánh giá coverage bằng LLM, không sinh test; chỉ có bản arXiv |

---

## Tổng hợp so với RQ

1. **Bằng chứng gần nhất:** R022 và R001 đều so Claude với ChatGPT, dùng EP/BVA và đo % coverage. R010 so LLM với người nhưng không có Claude.
2. **Coverage EP và BVA gần như bão hòa.** R022: mọi mô hình đạt 100% EP và BVA. R001: mọi công cụ đạt 100% EP, và 100% BVA (trừ Copilot). Với RQ này, khác biệt giữa ChatGPT và Claude ở EP/BVA đơn giản có thể rất nhỏ (cần kiểm chứng bằng dữ liệu của nhóm).
3. **Khác biệt xuất hiện ở kỹ thuật khó hơn.** R001: complex BVA, ChatGPT-4o có F1 0,80 và Claude 2 có 0,50. R022: state transition, Claude và ChatGPT cùng 100%, các mô hình khác thấp hơn.
4. **Baseline người:** R010 và R001 so với tester người nhưng chủ yếu về thời gian hoặc coverage tổng; không bài nào nói rõ bộ test của người được làm trước khi xem kết quả AI.
5. **Khoảng trống:** trong 11 bài đã đọc, không bài nào kết hợp PURE, ChatGPT và Claude, cùng một prompt one-shot EP–BVA, baseline người lập trước và coverage-item. Kết luận này chỉ đúng với các bài đã đọc, chưa tính 6 bài thiếu và snowballing.

---

## Việc cần kiểm tra trước khi nộp

- Đối chiếu cột trong bảng này với mẫu Evidence Table của cô (mình chưa thấy mẫu).
- R022: đọc lại bảng precision/recall của Claude; xác định gold standard lập khi nào.
- R001: đọc kỹ công thức coverage và cách chọn 8 yêu cầu.
- Các số liệu lấy từ hình (R003 requirement coverage, R010 thời gian) nên đối chiếu với hình gốc.
- Bổ sung 6 bài còn thiếu và các bài snowballing.
