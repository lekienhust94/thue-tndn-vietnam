# Thuế Doanh Nghiệp Vietnam (trọng tâm TNDN) — Agent Instructions

> Bản chuyển đổi từ `SKILL.md` (định dạng Claude Skill) sang `AGENTS.md` để dùng với Codex hoặc các coding agent khác đọc file này ở gốc repo. Nội dung tham khảo gốc nằm trong thư mục `references/`, không đổi.

**Phạm vi áp dụng:** CHỈ áp dụng các rule dưới đây khi user hỏi về thuế Thu nhập doanh nghiệp (TNDN) Việt Nam, thuế suất, ưu đãi thuế, tạm nộp quý, quyết toán năm, chi phí được trừ/không được trừ, hoặc nghĩa vụ thuế/kê khai liên quan của doanh nghiệp (GTGT, hóa đơn điện tử, PIT withholding, BHXH). Câu hỏi ngoài phạm vi này thì bỏ qua các rule bên dưới.

> [!CAUTION]
> **RISK LEVEL: LOW** — Nội dung liên quan quy định pháp luật nhà nước.
> - Chỉ mang tính tham khảo, KHÔNG thay thế tư vấn thuế chuyên nghiệp.
> - Áp dụng: Kỳ tính thuế 2026 | Luật Thuế TNDN số 67/2025/QH15 | **v2.0.0 (100% 🟢 HIGH Confidence)**.
> - Xây dựng hoàn toàn bằng **văn bản gốc do người dùng cung cấp trực tiếp** (đã đọc toàn văn: NĐ 320/2025/NĐ-CP 76 trang, NĐ 252/2026/NĐ-CP 1416+ dòng, NĐ 245/2026/NĐ-CP, NĐ 254/2026/NĐ-CP, TT 20/2026/TT-BTC, NĐ 68/2026/NĐ-CP, NĐ 310/2025/NĐ-CP, NĐ 145/2020, NĐ 12/2022, NĐ 17/2012, Luật 67/2025, Luật 09/2026, Luật 149/2025, Luật 48/2024, Luật 41/2024...).
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
│ 🔒 GATE 1: FRESHNESS CHECK     │
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
│ 🔒 GATE 2: CROSS-VERIFY        │
│ - Số liệu khớp reference?      │
│ - Confidence = MEDIUM? -> nói rõ với user, khuyên kiểm tra lại │
└─────────────────────────────────┘
      │
      ▼
┌─────────────────────────────────┐
│ 🔒 GATE 3: SOURCE CITATION     │
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

## Số Liệu Nhanh Tra Cứu (2026)

| Chỉ số | Giá trị | Căn cứ | Confidence |
|--------|---------|--------|-----------|
| Thuế suất phổ thông | **20%** | Luật 67/2025/QH15 | 🟢 HIGH |
| Thuế suất DN doanh thu ≤ 3 tỷ/năm (năm trước liền kề) | **15%** | NĐ 320/2025/NĐ-CP, Điều 11 | 🟢 HIGH |
| Thuế suất DN doanh thu 3-50 tỷ/năm | **17%** | NĐ 320/2025/NĐ-CP, Điều 11 | 🟢 HIGH |
| Ngày Luật TNDN mới có hiệu lực | **01/10/2025** | Luật 67/2025/QH15 | 🟢 HIGH |
| Ngưỡng tạm nộp quý phải đạt | **≥ 80%** số thuế cả năm (tính đến hết quý 4) | **NĐ 252/2026/NĐ-CP**, Điều 24 khoản 3a (thay thế NĐ 126/2020 + NĐ 91/2022 từ 01/07/2026) | 🟢 HIGH |
| Hạn nộp tạm tính quý thông thường | Q1: 30/04, Q2: 31/07, Q3: 31/10, Q4: 31/01 | **NĐ 252/2026/NĐ-CP**, Điều 24 khoản 2 | 🟢 HIGH |
| Gia hạn tạm nộp TNDN 2026 (DN đủ điều kiện) | Q2: đến **02/11/2026**, Q3: đến **30/12/2026** | **NĐ 245/2026/NĐ-CP**, Điều 2 khoản 2 | 🟢 HIGH |
| Hạn quyết toán năm | **Chậm nhất ngày cuối tháng thứ ba** kể từ ngày kết thúc năm tài chính (với năm tài chính 31/12 → hạn cơ bản = 31/03 năm sau) | Luật Quản lý thuế **38/2019/QH14** sửa bởi Luật **56/2024/QH15** | 🟢 HIGH |
| Thuế suất GTGT phổ thông / giảm 2026 | **10%** / **8%** (giảm đến 31/12/2026) | Luật 48/2024/QH15; NĐ 174/2025/NĐ-CP | 🟢 HIGH |
| Ngưỡng kê khai GTGT tháng vs quý | **50 tỷ đồng/năm** (doanh thu năm trước) | NĐ 252/2026/NĐ-CP | 🟢 HIGH |
| Khung pháp lý hóa đơn điện tử mới | NĐ **254/2026/NĐ-CP** (hiệu lực 01/07/2026), thay NĐ 123/2020 + 70/2025 | Đã đọc toàn văn gốc | 🟢 HIGH |
| **⭐ Ngưỡng MIỄN HOÀN TOÀN thuế TNDN** (doanh thu năm ≤ ngưỡng) | **1 tỷ đồng/năm** | Luật 09/2026/QH16 + NĐ 141/2026/NĐ-CP (29/04/2026) | 🟢 HIGH |

## Mandatory Disclaimer (Bắt buộc kèm theo mọi output liên quan thuế TNDN)

```
⚠️ Thông tin chỉ mang tính tham khảo, KHÔNG thay thế tư vấn thuế chuyên nghiệp.
Căn cứ: [ghi rõ luật/NĐ/TT].
Kiểm tra lại tại: https://gdt.gov.vn hoặc https://thuvienphapluat.vn
```

## Common Mistakes

| Lỗi thường gặp | Cách xử lý đúng |
|---------------|----------------|
| Nhầm thuế TNDN với thuế TNCN | Nói rõ: đây là thuế trên lợi nhuận doanh nghiệp, khác thuế TNCN trên thu nhập cá nhân |
| Áp thuế suất ưu đãi 15%/17% mà không hỏi doanh thu năm liền trước | Luôn hỏi doanh thu năm trước khi áp dụng |
| Khẳng định chắc chắn DN được hưởng ưu đãi ngành/vùng mà chưa đủ thông tin | Hỏi thêm ngành nghề, địa bàn, loại dự án đầu tư |
| Dùng số liệu Luật TNDN cũ (Luật 14/2008/QH12 và các lần sửa đổi trước) | Từ kỳ tính thuế 2026 áp dụng Luật 67/2025/QH15 |
| Ghi nhầm ngày hạn nộp tạm tính Q2 (30/07) và Q3 (30/10) | Tháng 7 và tháng 10 có 31 ngày → hạn đúng là 31/07 và 31/10 (NĐ 252/2026 Đ.24) |
| Diễn đạt hạn quyết toán là "trong vòng 90 ngày" | Dùng cụm từ chuẩn pháp lý: "chậm nhất ngày cuối cùng của tháng thứ ba" |

---
> Nguồn gốc: chuyển thể từ `SKILL.md` (bản dành cho Claude Skill). Khi `SKILL.md` được cập nhật version mới, đồng bộ lại các bảng/rule tương ứng ở đây. v2.0.0 | 23/07/2026.
