# PRISMA Flow Diagram (prisma-flow.md)

## PHỄU CHÍNH (chốt trước, số không đổi)

[Paper từ IEEE Xplore (N = 214)]
        │
        ▼
[Sau dedup (N = 187)]  ◄── = số dòng trong 01_all_records.csv
        │
        ├─────────────────────────────► [Loại V1 (N = 158): EC-O, EC-S, ...]
        ▼
[Full-text đọc (N = 29)]
        │
        ├─────────────────────────────► [Loại V2 (N = 21): EC-A, IC-E, ...]
        ▼
[Final phễu chính (N = 8)]  ◄── = dòng INCLUDE, source = search


## NHÁNH SNOWBALLING (làm sau vòng 2, từ seed INCLUDE)

[Snowballing (N = 12)]  ◄── = tổng "Số thêm vào 01"
        │
        ├──► [Loại V1 (N = 8)] ──► [Full-text đọc (N = 4)] ──┬──► [Loại V2 (N = 2)]
        │                                                     │
        ▼                                                     ▼
[Included từ snowballing (N = 2)]  ◄── = dòng INCLUDE, source = snowball-*


## TỔNG KẾT
**TỔNG: Final included = UU + KK = 8 + 2 = 10**  ◄── = số dòng Include trong 03_final_included.csv

---

## 📊 Bảng đối chiếu số liệu PRISMA

| Ô trong PRISMA | Công thức / Cách đếm | Giá trị (N) |
| :--- | :--- | :---: |
| **Paper từ nguồn (XX)** | Tổng số kết quả từ IEEE Xplore (chưa bỏ trùng) | **214** |
| **Bản trùng bỏ qua** | Bản trùng bị lọc | **27** |
| **Sau bỏ trùng (YY)** | Số dòng trong `01_all_records.csv` | **187** |
| **Loại vòng 1 (ZZ)** | Số dòng `EXCLUDE` ở `v1_decision` | **158** |
| **Đọc full-text (WW)** | Số dòng trong `03_final_included.csv` (`INCLUDE` + `Unsure` ở V1) | **29** |
| **Loại vòng 2 (VV)** | Số dòng `EXCLUDE` ở `v2_decision` | **21** |
| **Final phễu chính (UU)** | Số dòng `INCLUDE` có `source = search` | **8** |
| **Snowballing thêm vào (SS)** | Tổng cột "Số thêm vào 01" của bảng seed | **12** |
| **Snowball: Loại V1 (S1)** | Lọc V1 từ nhánh snowballing | **8** |
| **Snowball: Full-text đọc (S2)** | Chỉ các dòng snowballing đọc full-text | **4** |
| **Snowball: Loại V2 (S3)** | Lọc V2 từ nhánh snowballing | **2** |
| **Included từ snowballing (KK)** | Số dòng `INCLUDE` có `source = snowball-*` | **2** |
| **Final included tổng** | **UU + KK** (Tổng số dòng Include trong bộ 03) | **10** |

---

## 🔍 Kiểm tra tính logic của số liệu (Check Arithmetic)
* **Phễu chính:** $214 - 27 = 187 \rightarrow 187 - 158 = 29 \rightarrow 29 - 21 = 8$
* **Nhánh Snowballing:** $12 - 8 = 4 \rightarrow 4 - 2 = 2$
* **Tổng bài nhận cuối cùng:** $8 \text{ (phễu chính)} + 2 \text{ (snowballing)} = 10 \text{ bài}$
