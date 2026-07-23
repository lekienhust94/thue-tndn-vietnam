# 🇻🇳 Skill Thuế TNDN Vietnam (2026)

> AI Skill tra cứu thuế Thu nhập doanh nghiệp (TNDN), ưu đãi thuế, tạm nộp/quyết toán, và lịch nghĩa vụ định kỳ của doanh nghiệp (kèm GTGT, hóa đơn điện tử, lao động/BHXH, kiểm toán BCTC).

[![Version](https://img.shields.io/badge/version-2.0.0-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()
[![Confidence](https://img.shields.io/badge/confidence-100%25--HIGH-brightgreen)]()

## Tổng Quan

Skill **thue-tndn-vietnam** là bộ công cụ tra cứu thuế TNDN dạng AI, tự chứa toàn bộ dữ liệu cần thiết. Hoạt động trên Claude Code, Claude Desktop, và các nền tảng AI hỗ trợ skill/knowledge base. Đây là skill **độc lập, tách biệt hoàn toàn** với skill `thue-tncn-vietnam` (thuế cá nhân) — không dùng chung dữ liệu hay tham chiếu chéo.

### Tính năng chính

- 📊 **Thuế suất TNDN** (Luật 67/2025/QH15) + các mức ưu đãi theo ngành/địa bàn
- 🧾 **Chi phí được trừ / không được trừ** khi tính thuế TNDN
- 📅 **Tạm nộp theo quý + quyết toán năm** — quy trình, hạn nộp, mẫu biểu
- 🧮 **Thuế GTGT liên quan**: thuế suất, ngưỡng hộ/cá nhân kinh doanh (500 triệu/năm), kê khai tháng/quý
- 🧻 **Hóa đơn điện tử**: khung pháp lý hiện hành (NĐ 254/2026/NĐ-CP), ngưỡng bắt buộc
- 🗓️ **Lịch nghĩa vụ doanh nghiệp** đầy đủ: thuế + lao động/BHXH + kiểm toán BCTC bắt buộc

## Cài Đặt

### Claude Code / Claude Desktop

```
your-project/
└── .agents/
    └── skill/
        └── thue-tndn-vietnam/   ← copy vào đây
```

Hoặc cài global: `~/.claude/skills/thue-tndn-vietnam/`.

### Codex CLI

Repo đã có sẵn `AGENTS.md` ở gốc (bản chuyển thể từ `SKILL.md`, không có frontmatter riêng của Claude). Codex tự động đọc `AGENTS.md` khi chạy trong thư mục repo — không cần cấu hình thêm, chỉ cần chạy `codex` với working directory là gốc project này (hoặc thư mục cha chứa nó, tùy cách Codex quét).

> Lưu ý: khác với Claude Skill (tự nạp `references/*.md` theo mô tả khi cần), Codex không tự trigger — `AGENTS.md` chỉ định tường minh "phải mở file X trước khi trả lời câu hỏi Y", Codex sẽ tự đọc file đó vì có quyền truy cập filesystem.

### Các nền tảng khác (ChatGPT Custom GPT/Project, v.v.)

Dán nội dung thân `SKILL.md` (bỏ frontmatter) vào system prompt/instructions, upload toàn bộ thư mục `references/` vào knowledge base.

## Số Liệu Nhanh (2026)

| Chỉ số | Giá trị | Căn cứ |
|--------|---------|--------|
| Thuế suất TNDN phổ thông | 20% | Luật 67/2025/QH15 |
| Thuế suất ưu đãi | 15% / 17% | NĐ 320/2025/NĐ-CP |
| Ngưỡng GTGT miễn thuế hộ/cá nhân KD | **500 triệu đồng/năm** | NĐ 68/2026/NĐ-CP, Điều 3.1 |
| Ngưỡng bắt buộc hóa đơn điện tử có mã CQT (hộ/cá nhân KD) | 1 tỷ đồng/năm | NĐ 68/2026/NĐ-CP, Điều 8.5.a |
| Thủ tục quản lý thuế, Tạm nộp TNDN 80% | NĐ 252/2026/NĐ-CP, Điều 24 | NĐ 252/2026/NĐ-CP (thay NĐ 126/2020 & NĐ 91/2022 từ 01/07/2026) |
| Gia hạn nộp thuế TNDN 2026 (Q2 → 02/11, Q3 → 30/12) | NĐ 245/2026/NĐ-CP | NĐ 245/2026/NĐ-CP (DN thuộc 43 ngành hoặc DN nhỏ/siêu nhỏ) |
| Hạn đóng BHXH/BHYT/BHTN (đóng hằng tháng) | Chậm nhất ngày cuối cùng tháng tiếp theo | Luật BHXH 41/2024/QH15, Điều 34.4 |
| Tiêu chí "DN quy mô lớn" phải kiểm toán bắt buộc | ≥2/3: LĐ >200 người, doanh thu >300 tỷ, tổng tài sản >100 tỷ | NĐ 90/2025/NĐ-CP (sửa NĐ 17/2012/NĐ-CP) |

## Cấu Trúc

```
thue-tndn-vietnam/
├── SKILL.md                              ← Master file cho Claude Skill (AI đọc đầu tiên)
├── AGENTS.md                              ← Bản chuyển thể của SKILL.md cho Codex CLI/agent khác
├── README.md                             ← File này
├── LICENSE                               ← MIT
└── references/
    ├── tong-quan-thue.md                 ← Thuế suất TNDN, kỳ tính thuế
    ├── uu-dai-thue.md                     ← Ưu đãi thuế theo ngành/địa bàn/thời gian
    ├── ke-khai-tam-nop-quyet-toan.md      ← Tạm nộp quý + quyết toán năm
    ├── thue-gtgt-lien-quan.md             ← Thuế GTGT (thuế suất, ngưỡng, kê khai)
    ├── hoa-don-dien-tu.md                 ← Hóa đơn điện tử
    ├── lich-nghia-vu-doanh-nghiep.md      ← Lịch tổng hợp TẤT CẢ nghĩa vụ định kỳ
    ├── faq.md                             ← Câu hỏi thường gặp
    ├── deadline-tracker.md                ← Lịch nộp thuế 2026
    ├── changelog.md                       ← Lịch sử cập nhật theo version
    ├── sources.md                         ← Nguồn tham khảo + confidence level từng mục
    └── nguon-goc/                         ← Văn bản gốc dùng làm bằng chứng trích dẫn
        └── Luat-41-2024-QH15-BHXH.pdf     ← Văn bản gốc Luật BHXH 2024 (nguồn sơ cấp)
```

## Phương Pháp Xây Dựng & Confidence

Skill được xây dựng theo thứ tự ưu tiên nguồn:

1. **Văn bản gốc** do người dùng cung cấp trực tiếp (PDF/docx từ vanban.chinhphu.vn, Công báo) — mức xác nhận cao nhất, đọc toàn văn
2. Fetch trực tiếp từ vanban.chinhphu.vn / baochinhphu.vn
3. WebSearch/WebFetch từ các nguồn thứ cấp (thuvienphapluat.vn, luatvietnam.vn...) — chỉ dùng khi chưa có văn bản gốc, luôn ghi rõ trong `sources.md`

**Tính đến v2.0.0**: 100% toàn bộ nội dung — cả TNDN cốt lõi, thủ tục quản lý thuế (NĐ 252/2026), gia hạn nộp thuế (NĐ 245/2026), lẫn các nghĩa vụ phụ — đều đã ở mức 🟢 **HIGH CONFIDENCE**, được xác minh trực tiếp bằng văn bản gốc do người dùng cung cấp. Chi tiết từng mục xem `references/sources.md`.

## Lưu Ý Quan Trọng

⚠️ **Thông tin chỉ mang tính tham khảo, KHÔNG thay thế tư vấn thuế chuyên nghiệp.**

Kiểm tra lại tại:
- https://vanban.chinhphu.vn
- https://gdt.gov.vn

---

*Cập nhật: 23/07/2026 | Luật Thuế TNDN 67/2025/QH15*
