## Metadata export / Dedup

- Date: 2026-10-16
- Cách export: file BibTeX (citation.bib) từ Semantic Scholar; web S2 không xuất hàng loạt qua CSV nên chuyển .bib sang 01_all_records.csv bằng script bib_to_csv.py (không viết tay bản ghi).
- Nguồn bản ghi: kết quả các lượt hợp lệ (S02, S03, S06, S07) gộp lại; chưa gắn được query cho từng bản ghi (xem Ghi chú bên dưới)
- Số bản ghi trong .bib: 54
- Sau dedup trong lượt (DOI; nếu không có thì tiêu đề chuẩn hóa + năm): 54 (không bỏ bản ghi nào; có 2 bài trùng khóa Li2025HowMC nhưng là 2 bài khác nhau nên giữ cả hai)
- Ghi vào 01_all_records.csv: 54 dòng (database = Semantic Scholar, source = search, record_id R001–R054)

### Metadata trước khi bổ sung (ngay sau khi chuyển từ .bib)
- Ô trống: doi=54, abstract=54, year=0, venue=0, authors=1
- Nhận xét: .bib của Semantic Scholar không có DOI và abstract; url là link CorpusID.

### Bổ sung abstract/doi qua API
- Tool: enrich_s2.py (Semantic Scholar Graph API, endpoint /paper/batch, tra theo CorpusID)
- Chạy lúc: ___ | Tra được: ___ / 54
- Ô trống sau bổ sung: doi=___ abstract=___
- Quy ước: abstract vẫn trống thì đánh dấu Unsure ở vòng 1 (không EXCLUDE chỉ vì thiếu abstract)

### Kiểm chứng công cụ
1. Số bản ghi khớp số kết quả web? ___ (nếu lệch, giải thích: .bib có thể là tổng các lượt hợp lệ sau khi gộp, không phải riêng một lượt)
2. Mở ngẫu nhiên 5 bản ghi, đối chiếu title/năm/DOI với trang gốc: ___
3. Chạy lại script, kết quả giống lần đầu? ___

### Ghi chú
- Chưa điền cột query cho từng bản ghi vì .bib không lưu thông tin lượt tìm; sẽ đối chiếu tiêu đề với các trang kết quả S02/S03/S06/S07 rồi cập nhật: ___
- Danh sách chứa nhiều bài không liên quan (y tế, giáo dục...), nhất là từ lượt S07 ("PURE"); loại ở vòng screening theo IC/EC, không xóa ở bước này.
- Bộ lọc năm 2018–nay đã áp dụng trên web; trong .bib không có bài trước 2018.

## Snowballing (A2b)

Seed (DOI): ___ | Backward: ___ | Forward: ___ | Thêm vào 01_all_records.csv: ___ dòng
