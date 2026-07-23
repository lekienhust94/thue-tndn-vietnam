# Thuế Doanh Nghiệp Vietnam (trọng tâm TNDN) — Agent Instructions

> Bản chuyển đổi từ `SKILL.md` (định dạng Claude Skill) sang `AGENTS.md` để dùng với Codex hoặc các coding agent khác đọc file này ở gốc repo. Nội dung tham khảo gốc nằm trong thư mục `references/`, không đổi.

**Phạm vi áp dụng:** CHỈ áp dụng các rule dưới đây khi user hỏi về thuế Thu nhập doanh nghiệp (TNDN) Việt Nam, thuế suất, ưu đãi thuế, tạm nộp quý, quyết toán năm, chi phí được trừ/không được trừ, hoặc nghĩa vụ thuế/kê khai liên quan của doanh nghiệp (GTGT, hóa đơn điện tử, PIT withholding, BHXH). Câu hỏi ngoài phạm vi này thì bỏ qua các rule bên dưới.

> [!CAUTION]
> **RISK LEVEL: LOW** — Nội dung liên quan quy định pháp luật nhà nước.
> - Chỉ mang tính tham khảo, KHÔNG thay thế tư vấn thuế chuyên nghiệp.
> - Áp dụng: Kỳ tính thuế 2026 | Luật Thuế TNDN số 67/2025/QH15.
> - Xem `references/changelog.md` và `references/sources.md` để biết confidence level từng mục trước khi trả lời.

## Bắt buộc: đọc file reference tương ứng trước khi trả lời

Codex không tự động nạp file theo mô tả (khác cơ chế skill-matching của Claude) — PHẢI tự mở đúng file bên dưới trước khi trả lời, KHÔNG trả lời từ trí nhớ/suy đoán:

| Câu hỏi | File PHẢI đọc trước |
|---------|---------------|
| Thuế suất bao nhiêu? Căn cứ tính thuế? Chi phí được trừ? | `references/tong-quan-thue.md` |
| Ưu đãi thuế theo ngành/vùng/dự án đầu tư? | `references/uu-dai-thue.md` |
| Cách tạm nộp quý, quyết toán năm? SOP? | `references/ke-khai-tam-nop-quyet-toan.md` |
| Thuế GTGT (VAT) — thuế suất, kê khai tháng/quý? | `references/thue-gtgt-lien-quan.md` |
| Hóa đơn điện tử — quy định, mức phạt? | `references/hoa-don-dien-tu.md` |
| Doanh nghiệp cần kê khai/nộp gì hàng tháng/quý/năm? (tổng thể) | `references/lich-nghia-vu-doanh-nghiep.md` |
| Hạn nộp thuế TNDN cụ thể khi nào? | `references/deadline-tracker.md` |
| Câu hỏi thường gặp | `references/faq.md` |
| Data đã thay đổi gì? Phiên bản? | `references/changelog.md` |
| Nguồn tham khảo + Confidence Level | `references/sources.md` |

## Workflow (5 bước, có 3 Verification Gate)

```
1. User hỏi về thuế TNDN
2. Xác định chủ đề: thuế suất / ưu đãi / kê khai-tạm nộp / quyết toán / hạn nộp
      │
      ▼
3. Mở file reference phù hợp (bảng trên) — bắt buộc, không bỏ qua
      │
      ▼
┌─────────────────────────────────┐
│ GATE 1: FRESHNESS CHECK        │
│ - Kiểm tra references/changelog.md │
│ - Data > 6 tháng? -> CẢNH BÁO  │
└─────────────────────────────────┘
      │
      ▼
4. Soạn câu trả lời
   (nếu có phép tính thuế: PHẢI tách từng bước, ghi rõ doanh thu làm căn cứ)
      │
      ▼
┌─────────────────────────────────┐
│ GATE 2: CROSS-VERIFY           │
│ - Số liệu khớp reference?      │
│ - Confidence = MEDIUM? -> nói rõ với user, khuyên kiểm tra lại │
└─────────────────────────────────┘
      │
      ▼
┌─────────────────────────────────┐
│ GATE 3: SOURCE CITATION        │
│ - Ghi căn cứ pháp lý           │
│ - Ghi ngày cập nhật data       │
│ - Kèm disclaimer bắt buộc      │
└─────────────────────────────────┘
      │
      ▼
5. Output + disclaimer
```

## Anti-Hallucination Rules

**CẤM TUYỆT ĐỐI** vi phạm các rule sau:

| # | Rule | Fallback |
|---|------|----------|
| 1 | KHÔNG BAO GIỜ bịa số liệu thuế (thuế suất, ngưỡng doanh thu, mức ưu đãi) | "Tôi không chắc, vui lòng kiểm tra tại gdt.gov.vn" |
| 2 | KHÔNG BAO GIỜ khẳng định khi không chắc chắn, đặc biệt với mục confidence MEDIUM trong `references/sources.md` | "Chưa xác minh chắc chắn, khuyên đối chiếu văn bản gốc" |
| 3 | KHÔNG tự suy luận quy định mới khi chưa có trong reference | "Quy định này chưa có trong tài liệu, cần cập nhật" |
| 4 | KHÔNG trả lời câu hỏi ngoài phạm vi (thuế TNCN, thuế GTGT không liên quan doanh nghiệp, thuế XNK...) | "Tài liệu này chỉ cover thuế TNDN" |
| 5 | MỌI con số PHẢI kèm căn cứ pháp lý | "Theo Luật 67/2025/QH15, Điều X..." |
| 6 | Ưu đãi thuế phụ thuộc điều kiện cụ thể của từng doanh nghiệp (ngành, vùng, quy mô dự án) — KHÔNG khẳng định doanh nghiệp cụ thể được hưởng ưu đãi nếu chưa đủ thông tin | Hỏi thêm: ngành nghề, địa bàn đầu tư, dự án mới hay đang hoạt động |
| 7 | Doanh thu làm căn cứ áp thuế suất ưu đãi (15%/17%) là doanh thu năm TRƯỚC LIỀN KỀ — hỏi rõ trước khi áp dụng | Hỏi: "Doanh thu năm liền trước là bao nhiêu?" |

## Mandatory Disclaimer (Bắt buộc kèm theo mọi output liên quan thuế TNDN)

```
⚠️ Thông tin chỉ mang tính tham khảo, KHÔNG thay thế tư vấn thuế chuyên nghiệp.
Căn cứ: [ghi rõ luật/NĐ/TT]. Một số số liệu confidence MEDIUM — khuyên đối chiếu văn bản gốc.
Kiểm tra lại tại: https://gdt.gov.vn hoặc https://thuvienphapluat.vn
```

## Common Mistakes

| Lỗi thường gặp | Cách xử lý đúng |
|---------------|----------------|
| Nhầm thuế TNDN với thuế TNCN | Nói rõ: đây là thuế trên lợi nhuận doanh nghiệp, khác thuế TNCN trên thu nhập cá nhân |
| Áp thuế suất ưu đãi 15%/17% mà không hỏi doanh thu năm liền trước | Luôn hỏi doanh thu năm trước khi áp dụng |
| Khẳng định chắc chắn DN được hưởng ưu đãi ngành/vùng mà chưa đủ thông tin | Hỏi thêm ngành nghề, địa bàn, loại dự án đầu tư |
| Dùng số liệu Luật TNDN cũ (Luật 14/2008/QH12 và các lần sửa đổi trước) | Từ kỳ tính thuế 2026 áp dụng Luật 67/2025/QH15 |

---
> Nguồn gốc: chuyển thể từ `SKILL.md` (bản dành cho Claude Skill). Khi `SKILL.md` được cập nhật version mới, đồng bộ lại các bảng/rule tương ứng ở đây.
