# prisma-flow.md (cá nhân, bản tạm)

Chưa chốt: còn 6 paper search và 5 paper snowballing chờ full-text. Cập nhật số khi đọc xong.

| Ô PRISMA | Đếm thế nào | Số |
|---|---|---|
| Sau bỏ trùng (phễu chính) | Số dòng `source = search` trong `01_all_records.csv` (169 bản ghi, bỏ 4 trùng) | **165** |
| Loại vòng 1 | Số `EXCLUDE` ở `v1_decision` (nhóm search) | **143** |
| Đọc full-text (phễu chính) | Số dòng INCLUDE + Unsure ở 02 (nhóm search) = số dòng 03 (nhóm search) | **22** |
| Loại vòng 2 | Số `EXCLUDE` ở `v2_decision` (nhóm search): R005, R007, R019, R084, R127 | **5** |
| Chưa có full-text | R004, R029, R036, R072, R080, R103 | **6** |
| Final phễu chính (UU) | Dòng `INCLUDE`, `source = search` | **11** |
| Snowballing (SS) | Tổng "Số thêm vào 01" trong bảng seed (11 lùi + 8 tiến) | **19** |
| Loại vòng 1 (snowballing) | `EXCLUDE` ở `v1_decision` (9 lùi + 3 tiến) | **12** |
| Đọc full-text (snowballing) | Dòng Unsure ở 02, `source = snowball-*` | **7** |
| Loại vòng 2 (snowballing) | RAFT, Folorunsho và Reza (IC-T) | **2** |
| Chờ full-text (snowballing) | Fischbach 2023, Wang 2024, Karmouda 2025, SLR 2026, LLMCFG-TGen | **5** |
| Included từ snowballing (KK) | Dòng `INCLUDE`, `source = snowball-*` | **0** (chưa chốt) |
| Final included tổng | UU + KK | **11** (chưa chốt) |

**Kiểm tra số học**
- Phễu chính: 165 − 143 = 22; 22 − 5 − 6 = 11.
- Snowballing: 19 − 12 = 7; 7 − 2 − 5 = 0.
- Tổng: 11 + 0 = 11.
