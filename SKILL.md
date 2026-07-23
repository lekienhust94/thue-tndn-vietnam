---
name: thue-tndn-vietnam
description: Tra cứu và giải thích thuế thu nhập doanh nghiệp (TNDN) Việt Nam cho kỳ tính thuế 2026, gồm thuế suất, căn cứ tính thuế, chi phí được trừ, ưu đãi theo ngành/địa bàn/dự án, tạm nộp quý, quyết toán năm và thời hạn. Cũng dùng khi câu hỏi TNDN cần đối chiếu nghĩa vụ doanh nghiệp liên quan như GTGT, hóa đơn điện tử, khấu trừ TNCN, lao động hoặc BHXH. Không dùng làm nguồn duy nhất để nộp hồ sơ hay ra quyết định pháp lý.
---

# Thuế TNDN Việt Nam 2026

Tra cứu theo tài liệu đi kèm; không trả lời số liệu pháp lý từ trí nhớ.

> [!CAUTION]
> **RISK LEVEL: MEDIUM-HIGH.** Sai sót có thể ảnh hưởng số thuế, tiền chậm nộp hoặc hồ sơ của doanh nghiệp. Luôn yêu cầu người dùng kiểm tra văn bản hiện hành hoặc tham vấn chuyên gia trước khi kê khai/nộp thuế.

## Phạm vi và cách nạp tài liệu

Chỉ mở file cần thiết cho câu hỏi:

| Câu hỏi | File phải đọc |
|---|---|
| Thuế suất, căn cứ tính thuế, chi phí được/không được trừ | `references/tong-quan-thue.md` |
| Ưu đãi theo ngành, địa bàn hoặc dự án | `references/uu-dai-thue.md` |
| Tạm nộp quý, quyết toán năm, quy tắc 80% | `references/ke-khai-tam-nop-quyet-toan.md` |
| Hạn nộp cụ thể | `references/deadline-tracker.md` |
| GTGT liên quan doanh nghiệp | `references/thue-gtgt-lien-quan.md` |
| Hóa đơn điện tử | `references/hoa-don-dien-tu.md` |
| Lịch nghĩa vụ tổng thể, lao động, BHXH, kiểm toán | `references/lich-nghia-vu-doanh-nghiep.md` |
| Câu hỏi thường gặp | `references/faq.md` |

Với mọi câu hỏi có số liệu hoặc căn cứ pháp lý, đọc thêm:

- `references/changelog.md` để kiểm tra độ mới.
- `references/sources.md` để kiểm tra confidence và giới hạn nguồn.
- `references/source-manifest.yaml` để biết văn bản nào thực sự được đóng gói.

Không tự mở toàn bộ PDF/DOCX nếu reference Markdown đã đủ. Chỉ đối chiếu văn bản gốc khi cần kiểm tra câu chữ, điều khoản hoặc phát hiện mâu thuẫn.

## Quy trình bắt buộc

1. Xác định kỳ tính thuế và chủ đề.
2. Đọc reference tương ứng, `changelog.md` và phần liên quan trong `sources.md`.
3. Nếu dữ liệu đã quá 6 tháng hoặc văn bản có thể đã sửa đổi, cảnh báo rõ.
4. Đối chiếu con số, đối tượng, điều kiện, ngoại lệ và ngày hiệu lực.
5. Trả lời có căn cứ pháp lý, ngày cập nhật dữ liệu và disclaimer.

Nếu có phép tính:

1. Ghi rõ doanh thu dùng để xác định thuế suất.
2. Ghi công thức thu nhập tính thuế.
3. Tách từng bước tính và đơn vị.
4. Nêu giả định, ưu đãi và khoản chuyển lỗ nếu có.

## Quy tắc chống áp sai

- Không bịa thuế suất, ngưỡng, thời hạn, mức phạt hoặc số điều.
- Không suy diễn quy định mới ngoài tài liệu. Nói rõ tài liệu chưa cập nhật và yêu cầu đối chiếu nguồn chính thức.
- Không coi mức 15%/17% theo doanh thu là “ưu đãi theo ngành/địa bàn”. Gọi là **thuế suất theo doanh thu**.
- Trước khi áp dụng 15%/17%, hỏi doanh thu năm trước liền kề. Với doanh nghiệp mới, dùng quy tắc riêng trong reference.
- Không khẳng định doanh nghiệp được hưởng ưu đãi nếu chưa có ngành nghề, địa bàn, loại dự án, thời điểm đầu tư và tình trạng hoạt động.
- Không nhầm ngưỡng miễn TNDN của doanh nghiệp/tổ chức với ngưỡng GTGT của hộ, cá nhân kinh doanh.
- Không diễn đạt hạn quyết toán thành “90 ngày” nếu văn bản quy định “ngày cuối cùng của tháng thứ ba”.
- Nếu nguồn chỉ là nguồn thứ cấp hoặc chưa có văn bản gốc trong gói, hạ confidence và nói rõ.
- Với câu hỏi ngoài phạm vi doanh nghiệp, từ chối áp dụng skill này và chuyển sang nguồn phù hợp.

## Mốc tra cứu nhanh

Các mốc này chỉ dùng sau khi đã đọc reference tương ứng:

| Nội dung | Mốc | Căn cứ chính |
|---|---:|---|
| Thuế suất phổ thông | 20% | Luật 67/2025/QH15 |
| Thuế suất theo doanh thu năm trước không quá 3 tỷ đồng | 15% | NĐ 320/2025/NĐ-CP, Điều 11 |
| Thuế suất theo doanh thu năm trước trên 3 đến 50 tỷ đồng | 17% | NĐ 320/2025/NĐ-CP, Điều 11 |
| Ngưỡng tạm nộp bốn quý | Ít nhất 80% thuế quyết toán năm | NĐ 252/2026/NĐ-CP, Điều 24 |
| Hạn tạm nộp thông thường | Ngày cuối tháng đầu quý tiếp theo | NĐ 252/2026/NĐ-CP, Điều 24 |
| Ngưỡng miễn TNDN theo doanh thu | Không quá 1 tỷ đồng/năm, nếu đủ điều kiện | Luật 09/2026/QH16; NĐ 141/2026/NĐ-CP |

## Mẫu kết thúc bắt buộc

```text
⚠️ Thông tin chỉ mang tính tham khảo, KHÔNG thay thế tư vấn thuế chuyên nghiệp.
Căn cứ: [ghi văn bản và điều/khoản đã đối chiếu].
Dữ liệu tài liệu cập nhật: [ngày trong changelog/sources].
Kiểm tra văn bản hiện hành tại: https://vanban.chinhphu.vn hoặc https://gdt.gov.vn
```

Không mặc định dẫn `thuvienphapluat.vn` như nguồn chính thức; đây là nguồn tổng hợp tư nhân.

**Phiên bản nội dung:** 2.0.1 — 23/07/2026.
