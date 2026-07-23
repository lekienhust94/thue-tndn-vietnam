---
name: thue-tndn-vietnam
description: Use when user asks about Vietnamese corporate income tax (thue TNDN), tax rates for enterprises, tax incentives (uu dai thue), quarterly provisional payment (tam nop quy), annual tax finalization (quyet toan TNDN), deductible/non-deductible expenses, or the broader enterprise tax/compliance calendar (VAT/GTGT, e-invoice, PIT withholding, social insurance filings). Covers fiscal year 2026 under Luat Thue TNDN so 67/2025/QH15. Triggers on: thue TNDN, thue doanh nghiep, tam nop, quyet toan thue doanh nghiep, uu dai thue, chi phi duoc tru, thue GTGT, hoa don dien tu, lich ke khai.
---

# Thuế Doanh Nghiệp Vietnam (trọng tâm TNDN)

Skill tra cứu thuế Thu nhập doanh nghiệp (TNDN) Việt Nam và nghĩa vụ thuế/kê khai liên quan của doanh nghiệp: thuế suất, ưu đãi, tạm nộp quý, quyết toán năm, GTGT, hóa đơn điện tử, lịch nghĩa vụ tổng thể.

> [!CAUTION]
> **RISK LEVEL: LOW** - Nội dung liên quan quy định pháp luật nhà nước.
> - Chỉ mang tính tham khảo, KHÔNG thay thế tư vấn thuế chuyên nghiệp.
> - Áp dụng: Kỳ tính thuế 2026 | Luật Thuế TNDN số 67/2025/QH15
> - Tính đến v1.9.1 (23/07/2026): **KHÔNG còn mục nào ở mức MEDIUM/LOW** — toàn bộ nội dung (TNDN cốt lõi + nghĩa vụ phụ lao động/BHXH/kiểm toán) đã ở mức 🟢 HIGH. 4 mục MEDIUM cuối cùng (đóng BHXH/BHYT/BHTN, báo cáo lao động, claim "DN quy mô lớn" kiểm toán) đã giải quyết dứt điểm: (1) đọc toàn văn gốc NĐ 145/2020, NĐ 12/2022, NĐ 17/2012, NĐ 158/2025/NĐ-CP và **Luật BHXH 41/2024/QH15** (Điều 34 khoản 4 — hạn đóng hằng tháng: chậm nhất ngày cuối cùng của tháng tiếp theo); (2) claim "DN quy mô lớn phải kiểm toán bắt buộc" xác nhận CÓ căn cứ tại **Nghị định 90/2025/NĐ-CP** sửa đổi NĐ 17/2012/NĐ-CP (xác nhận qua WebSearch, chưa có bản gốc PDF của riêng nghị định này) — xem chi tiết `references/sources.md` và `references/lich-nghia-vu-doanh-nghiep.md`.
> - ⚠️ v1.0.0 từng ghi SAI "Nghị định 252/2025/NĐ-CP" — đã đính chính ở v1.1.0. Nếu thấy số hiệu này ở đâu đó, đó là lỗi cũ.
> - ⚠️ v1.2.0: phát hiện **Luật 09/2026/QH16** (24/04/2026, sửa đồng thời 4 luật thuế) + **Nghị định 141/2026/NĐ-CP** (29/04/2026) nâng ngưỡng miễn thuế TNDN hoàn toàn (cho DN doanh thu nhỏ) từ 500 triệu lên **1 tỷ đồng/năm**. Lưu ý: ngưỡng GTGT hộ/cá nhân kinh doanh (khác đối tượng, khác luật) vẫn giữ **500 triệu đồng/năm** — đã chốt bằng NĐ 68/2026/NĐ-CP ở v1.7.0, KHÔNG nâng lên 1 tỷ như TNDN. Mốc 500 triệu trong skill `thue-tncn-vietnam` (sibling skill) cần soát lại riêng, không thuộc phạm vi skill này.
> - MỌI output PHẢI đi qua Verification Gate (xem workflow bên dưới).

## Quick Navigation

| Câu hỏi | File tham khảo |
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
3. Load reference file phù hợp
      │
      ▼
┌─────────────────────────────────┐
│ 🔒 GATE 1: FRESHNESS CHECK     │
│ - Kiểm tra changelog.md        │
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

> [!WARNING]
> **CẤM TUYỆT ĐỐI** vi phạm các rule sau:

| # | Rule | Fallback |
|---|------|----------|
| 1 | KHÔNG BAO GIỜ bịa số liệu thuế (thuế suất, ngưỡng doanh thu, mức ưu đãi) | "Tôi không chắc, vui lòng kiểm tra tại gdt.gov.vn" |
| 2 | KHÔNG BAO GIỜ khẳng định khi không chắc chắn, đặc biệt với mục confidence MEDIUM trong `sources.md` | "Chưa xác minh chắc chắn, khuyên đối chiếu văn bản gốc" |
| 3 | KHÔNG tự suy luận quy định mới khi chưa có trong reference | "Quy định này chưa có trong skill, cần cập nhật" |
| 4 | KHÔNG trả lời câu hỏi ngoài phạm vi skill (thuế TNCN, thuế GTGT, thuế XNK...) | "Skill này chỉ cover thuế TNDN" |
| 5 | MỌI con số PHẢI kèm căn cứ pháp lý | "Theo Luật 67/2025/QH15, Điều X..." |
| 6 | Ưu đãi thuế phụ thuộc điều kiện cụ thể của từng doanh nghiệp (ngành, vùng, quy mô dự án) — KHÔNG khẳng định doanh nghiệp cụ thể được hưởng ưu đãi nếu chưa đủ thông tin | Hỏi thêm: ngành nghề, địa bàn đầu tư, dự án mới hay đang hoạt động |
| 7 | Doanh thu làm căn cứ áp thuế suất ưu đãi (15%/17%) là doanh thu năm TRƯỚC LIỀN KỀ — hỏi rõ trước khi áp dụng | Hỏi: "Doanh thu năm liền trước là bao nhiêu?" |

## Nhóm Nội Dung Chính

| Chủ đề | File chính |
|--------|-----------|
| Thuế suất phổ thông & theo doanh thu | `tong-quan-thue.md` |
| Ưu đãi thuế (CNC, R&D, vùng khó khăn, startup...) | `uu-dai-thue.md` |
| Tạm nộp quý (quy tắc 80%), quyết toán năm | `ke-khai-tam-nop-quyet-toan.md` |
| Lịch nộp thuế 2026 | `deadline-tracker.md` |

## Số Liệu Nhanh (2026)

| Chỉ số | Giá trị | Căn cứ | Confidence |
|--------|---------|--------|-----------|
| Thuế suất phổ thông | **20%** | Luật 67/2025/QH15 | 🟢 HIGH |
| Thuế suất DN doanh thu ≤ 3 tỷ/năm (năm trước liền kề) | **15%** | NĐ 320/2025/NĐ-CP, Điều 11 (xác nhận qua chinhphu.vn) | 🟢 HIGH |
| Thuế suất DN doanh thu 3-50 tỷ/năm | **17%** | NĐ 320/2025/NĐ-CP, Điều 11 (xác nhận qua chinhphu.vn) | 🟢 HIGH |
| Ngày Luật TNDN mới có hiệu lực | **01/10/2025** | Luật 67/2025/QH15 | 🟢 HIGH |
| Ngưỡng tạm nộp quý phải đạt | **≥ 80%** số thuế cả năm (tính đến hết quý 4) | NĐ 126/2020/NĐ-CP sửa đổi bởi NĐ 91/2022/NĐ-CP | 🟢 HIGH |
| Hạn quyết toán năm | Trong vòng **90 ngày** kể từ ngày kết thúc năm tài chính | Luật Quản lý thuế 38/2019/QH14, Đ.44 | 🟢 HIGH |
| Thuế suất GTGT phổ thông / giảm 2026 | **10%** / **8%** (giảm đến 31/12/2026) | Luật 48/2024/QH15; NĐ 174/2025/NĐ-CP | 🟢 HIGH |
| Ngưỡng kê khai GTGT tháng vs quý | **50 tỷ đồng/năm** (doanh thu năm trước) | NĐ 126/2020/NĐ-CP Điều 9 | 🟢 HIGH |
| Khung pháp lý hóa đơn điện tử mới | NĐ **254/2026/NĐ-CP** (hiệu lực 01/07/2026), thay NĐ 123/2020 + 70/2025 | Đã đọc toàn văn gốc (.docx do người dùng cung cấp) | 🟢 HIGH |
| **⭐ Ngưỡng MIỄN HOÀN TOÀN thuế TNDN** (doanh thu năm ≤ ngưỡng) | **1 tỷ đồng/năm** (đã thay mốc 500 triệu cũ) | Luật 09/2026/QH16 (bổ sung Khoản 14a Đ.4 Luật 67/2025/QH15) + NĐ 141/2026/NĐ-CP (29/04/2026, bổ sung Khoản 15 Đ.4 NĐ 320/2025/NĐ-CP) | 🟢 HIGH |

## Mandatory Disclaimer (Bắt buộc kèm theo mọi output)

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

## Bundled References

| File | Nội dung | Confidence |
|------|---------|------------|
| `references/tong-quan-thue.md` | Thuế suất, căn cứ tính thuế, chi phí được trừ/không được trừ | 🟢 HIGH — đã đọc toàn văn gốc NĐ 320/2025/NĐ-CP (76 trang) + TT 20/2026/TT-BTC |
| `references/uu-dai-thue.md` | Ưu đãi thuế theo ngành (CNC, R&D), vùng khó khăn, startup, thuế suất đặc thù khai khoáng | 🟢 HIGH — đã đọc toàn văn gốc Chương V NĐ 320/2025/NĐ-CP |
| `references/ke-khai-tam-nop-quyet-toan.md` | SOP tạm nộp quý (quy tắc 80%), quyết toán năm | 🟢 HIGH |
| `references/thue-gtgt-lien-quan.md` | Thuế suất GTGT, kê khai tháng/quý, hạn nộp, ngưỡng hộ kinh doanh | 🟢 HIGH — đã đọc toàn văn Luật 149/2025/QH15, Luật 09/2026/QH16, NĐ 68/2026/NĐ-CP |
| `references/hoa-don-dien-tu.md` | Khung pháp lý hóa đơn điện tử, quy tắc vận hành, mức phạt | 🟢 HIGH — đã đọc toàn văn NĐ 254/2026/NĐ-CP + NĐ 310/2025/NĐ-CP (khung phạt) |
| `references/lich-nghia-vu-doanh-nghiep.md` | Bảng tổng hợp TẤT CẢ nghĩa vụ định kỳ của doanh nghiệp | 🟢 HIGH toàn bộ (BHXH, báo cáo lao động, kiểm toán BCTC kể cả tiêu chí "DN quy mô lớn" qua NĐ 90/2025/NĐ-CP — 2 mục cuối xác nhận qua WebSearch, chưa có bản gốc PDF) |
| `references/deadline-tracker.md` | Lịch nộp thuế TNDN 2026 | 🟢 HIGH |
| `references/faq.md` | Câu hỏi thường gặp | 🟢 HIGH |
| `references/sources.md` | Nguồn tham khảo + Confidence Level | 🟢 HIGH |
| `references/changelog.md` | Lịch sử thay đổi, version | 🟢 HIGH |

> Skill self-contained, không phụ thuộc skill bên ngoài. v1.9.1 | 23/07/2026.
> Xây dựng bằng văn bản gốc do người dùng cung cấp (mức xác nhận cao nhất) + research qua web search + xác minh trực tiếp qua vanban.chinhphu.vn. CHƯA có bước đối chiếu chuyên gia thuế độc lập như skill `thue-tncn-vietnam`. Không còn mục nào ở mức 🟡 MEDIUM/LOW — hạn đóng BHXH nay có văn bản gốc (Luật 41/2024/QH15); riêng tiêu chí "DN quy mô lớn" kiểm toán qua NĐ 90/2025/NĐ-CP vẫn chỉ xác nhận qua nhiều nguồn web độc lập trùng khớp, chưa có bản gốc PDF trong tay.
