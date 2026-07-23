# Tạm Nộp Quý & Quyết Toán Năm — Thuế TNDN (2026)

## 1. Tạm nộp thuế TNDN theo quý

Doanh nghiệp tự xác định số thuế TNDN tạm nộp hàng quý (không phải nộp tờ khai tạm tính, chỉ nộp tiền thuế).

### Quy tắc 80%
- Tổng số thuế TNDN đã tạm nộp của **4 quý** không được thấp hơn **80%** số thuế TNDN phải nộp theo quyết toán năm.
- Nếu nộp thiếu so với 80%: phần chênh lệch từ **sau ngày hết hạn nộp thuế quý 4** đến ngày thực nộp số thuế còn thiếu sẽ bị tính **tiền chậm nộp** (mức phổ biến: 0,03%/ngày).
- Hạn nộp thuế tạm tính quý 4 thường là ngày **30 hoặc 31 tháng 01** năm sau (theo lịch nộp thuế cụ thể từng năm — xem `deadline-tracker.md`).

### Công thức kiểm tra
```
Tổng tạm nộp 4 quý ≥ 80% × Số thuế TNDN theo quyết toán năm
Nếu KHÔNG đạt → Số thiếu = 80% × Quyết toán − Tổng đã tạm nộp
→ Tính chậm nộp trên "Số thiếu" từ ngày hết hạn quý 4 đến ngày nộp bổ sung
```

## 2. Quyết toán thuế TNDN năm

### Hồ sơ quyết toán gồm:
- Tờ khai quyết toán thuế TNDN (mẫu theo quy định hiện hành của Tổng cục Thuế)
- Báo cáo tài chính năm (đã kiểm toán nếu thuộc diện bắt buộc)
- Các phụ lục liên quan (ưu đãi thuế, chuyển lỗ, giao dịch liên kết nếu có...)

### Hạn nộp quyết toán
- Trong vòng **90 ngày** kể từ ngày kết thúc năm tài chính (thường là 31/12 → hạn quyết toán khoảng cuối tháng 3 năm sau, điều chỉnh nếu trùng ngày nghỉ lễ).
- Nộp qua Cổng dịch vụ công của Tổng cục Thuế (thuedientu.gdt.gov.vn) hoặc phần mềm hỗ trợ kê khai (HTKK/iTaxViewer tùy quy định hiện hành).

### Sau quyết toán
- Nếu số đã tạm nộp > số phải nộp theo quyết toán: doanh nghiệp được bù trừ vào kỳ sau hoặc hoàn thuế theo quy định.
- Nếu số đã tạm nộp < số phải nộp: phải nộp bổ sung phần chênh lệch, có thể kèm tiền chậm nộp nếu vi phạm quy tắc 80%.

## Calculation Checklist (chạy trước khi tư vấn số liệu cụ thể)

```
□ 1. Xác định doanh thu năm trước liền kề (để biết thuế suất 15%/17%/20%)
□ 2. Xác định thu nhập tính thuế = Doanh thu - Chi phí được trừ + Thu nhập khác - Lỗ chuyển
□ 3. Áp thuế suất phù hợp
□ 4. Trừ đi số đã tạm nộp 4 quý (nếu có) để ra số phải nộp thêm/được hoàn
□ 5. Kiểm tra quy tắc 80% — nếu vi phạm, tính thêm tiền chậm nộp
□ 6. Khuyên user đối soát lại với phần mềm HTKK hoặc kế toán/kiểm toán
```

---
⚠️ Tham khảo, không thay thế tư vấn thuế chuyên nghiệp. Data cập nhật: 22/07/2026.
