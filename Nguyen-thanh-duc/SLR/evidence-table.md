# Evidence table — ACM Digital Library 

Chỉ gồm bài INCLUDE đã xác nhận ở V2 (R010, R030) và bài PENDING (R007) để PL xem. Chỗ nào bài không nêu ghi "not reported". Số liệu lấy từ full text.

| Cột | R010 — LLM4Fin (ISSTA'24, 10.1145/3650212.3680388) | R030 — Req2Test (SAC'26, 10.1145/3748522.3780013) | R007 — LLM comparison (ISEC'25, 10.1145/3717383.3717389) [PENDING] |
|---|---|---|---|
| Tool/LLM | LLM4Fin (fine-tuned Mengzi + thuật toán); đối chứng ChatGPT (GPT-4), ChatGLM | Req2Test, adapter GPT-4 (Gpt4Adapter); có thêm adapter cho model khác nhưng pipeline chạy đầy đủ bằng GPT-4 | BARD, ChatGPT3.5, Claude, Gemini, ChatGPT4.o, Llama3 |
| Task | Sinh test case chấp nhận (acceptance) cho phần mềm FinTech từ business rules | Sinh unit test từ user stories (DSL) cho REST API | Sinh test case từ requirements ngôn ngữ tự nhiên |
| Requirements/Dataset | 5 dataset business rules giao dịch tài chính (Table 2), công khai | 4 dự án API (P1–P4), user stories trên Zenodo/GitHub | Requirements có model Simulink viết tay làm ground truth |
| Prompting strategy | Prompt thiết kế kỹ (Section 2), sinh từng rule một; prompt có yêu cầu equivalence classes và boundary values | Prompt chuyên biệt theo từng bước, EP + BVA cho dữ liệu đầu vào | Prompt đơn: "Generate exhaustive test cases in table format for the requirement …" |
| Comparison | Chuyên gia (3 senior), người mới (4 sinh viên), ChatGPT, ChatGLM | EvoSuite, benchmark thủ công/QuixBugs | So sánh giữa các LLM; ground truth bằng SLDV |
| Metric | Business scenario coverage (BSC), SBC, MC/DC, thời gian | Code coverage, mutation score, pass rate | Decision, condition, MC/DC, execution coverage |
| Result | BSC trung bình: chuyên gia 75.16%, người mới 43.46%, ChatGPT 49.65%, ChatGLM 41.63%, LLM4Fin 91.89%. Code coverage (Dataset 5): SBC ChatGPT 87.61%, chuyên gia 86.90%; MC/DC 81.76% vs 82.30% | Abstract: 91.75% code coverage trung bình; so EvoSuite: tương đương ở Model package (100.0 vs 93.6), khác ở các lớp khác; phát hiện ~72.8% lỗi so với benchmark | Bài nêu LLM đều kém ở requirements phức tạp (không LLM nào hơn 25% ở một số mức); chi tiết từng LLM cần đọc lại Figure 3 trước khi trích số |
| Code/Artifact | github.com/13luoyu/intelligent-test; datasets công khai | github.com/specgentest/req2test-tool; Zenodo | not reported |
| Limitation | Domain-specific, thương mại, dữ liệu tiếng Trung; ChatGPT chỉ test dataset 5 ở code coverage | Chỉ GPT-4 chạy đủ pipeline; Java/REST | Chỉ đo coverage, không đánh giá tính đúng; requirements/dataset hạn chế |
| P (population khớp?) | Một phần (business rules, không phải PURE) | Một phần (user stories) | Một phần (requirements) |
| I (ChatGPT/Claude + EP/BVA) | Một phần (ChatGPT + EP/BVA; không có Claude) | Một phần (GPT-4 + EP/BVA; không có Claude) | Một phần (có Claude+ChatGPT; không rõ EP/BVA) |
| C (human-designed suite) | Có (chuyên gia, người mới) | Một phần (manual benchmark) | Không |
| O (coverage %) | Có | Có | Có |
| Near-RQ | 3/4 → CANDIDATE_COUNTEREVIDENCE (cần PL xác nhận) | 3/4 → CANDIDATE_COUNTEREVIDENCE (cần PL xác nhận) | 2/4 |

Ghi chú: tiêu chí Near-RQ đếm "Có" là 1, "Một phần" mình tạm tính theo mức đạt đủ ý chính; bạn đối chiếu lại với định nghĩa của nhóm. R030: abstract nói 91.75%, thân bài có đoạn nêu 85.97% trung bình cho một nhóm dự án — nên mở lại PDF khi trích dẫn.
