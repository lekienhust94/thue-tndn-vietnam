# Skill Thuế TNDN Việt Nam 2026

AI skill tra cứu thuế thu nhập doanh nghiệp Việt Nam: thuế suất, căn cứ tính thuế, chi phí được trừ, ưu đãi, tạm nộp quý, quyết toán năm và nghĩa vụ doanh nghiệp liên quan.

[![Version](https://img.shields.io/badge/version-2.0.1-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()
[![Evidence](https://img.shields.io/badge/evidence-claim--level-yellowgreen)]()

> Nội dung pháp lý có mức rủi ro trung bình–cao. Skill hỗ trợ tra cứu, không thay thế việc kiểm tra văn bản hiện hành hoặc tư vấn chuyên nghiệp.

## Cài đặt

### Claude Code

Sao chép toàn bộ thư mục repo vào:

```text
<project>/.claude/skills/thue-tndn-vietnam/
```

Hoặc cài ở phạm vi người dùng:

```text
~/.claude/skills/thue-tndn-vietnam/
```

### Codex

Sao chép toàn bộ thư mục repo vào:

```text
<project>/.agents/skills/thue-tndn-vietnam/
```

Hoặc cài ở phạm vi người dùng:

```text
~/.codex/skills/thue-tndn-vietnam/
```

`AGENTS.md` ở gốc là adapter cho trường hợp chạy Codex trực tiếp trong repo. Nó không thay thế việc cài `SKILL.md` khi muốn dùng skill ở project khác.

### Claude Desktop và nền tảng knowledge-base

Không giả định Claude Desktop tự quét các thư mục của Claude Code. Hãy import/upload gói skill theo cơ chế mà phiên bản ứng dụng đang hỗ trợ. Với nền tảng chỉ có knowledge base, dùng phần thân `SKILL.md` làm instruction và tải các file Markdown trong `references/`; PDF/DOCX là lớp bằng chứng đối chiếu.

## Phạm vi

- TNDN cốt lõi: thuế suất, căn cứ tính thuế, chi phí được/không được trừ.
- Thuế suất theo doanh thu 15%/17% và điều kiện áp dụng.
- Ưu đãi theo ngành, địa bàn, dự án và thời gian.
- Tạm nộp quý, quy tắc 80%, quyết toán năm và deadline.
- GTGT, hóa đơn, lao động/BHXH và kiểm toán chỉ khi liên quan nghĩa vụ doanh nghiệp.

Mức 15%/17% trong NĐ 320/2025/NĐ-CP được gọi là **thuế suất theo doanh thu**, không gọi chung là ưu đãi ngành/địa bàn.

## Cấu trúc

```text
thue-tndn-vietnam/
├── SKILL.md
├── AGENTS.md
├── references/
│   ├── tong-quan-thue.md
│   ├── uu-dai-thue.md
│   ├── ke-khai-tam-nop-quyet-toan.md
│   ├── deadline-tracker.md
│   ├── thue-gtgt-lien-quan.md
│   ├── hoa-don-dien-tu.md
│   ├── lich-nghia-vu-doanh-nghiep.md
│   ├── faq.md
│   ├── changelog.md
│   ├── sources.md
│   ├── source-manifest.yaml
│   └── nguon-goc/
└── LICENSE
```

## Confidence và nguồn

Confidence được đánh giá theo từng claim:

- `HIGH`: đã đối chiếu văn bản gốc phù hợp.
- `MEDIUM`: nguồn phù hợp nhưng bản gốc chưa được đóng gói hoặc mới đối chiếu nguồn thứ cấp.
- `LOW`: chưa đủ cơ sở để dùng cho kết luận.

`references/source-manifest.yaml` phân biệt rõ văn bản có trong gói và văn bản còn thiếu. Không suy từ việc một số văn bản đã được kiểm tra rằng toàn bộ skill đạt “100% HIGH”.

Ưu tiên nguồn:

1. Văn bản gốc từ cơ quan nhà nước.
2. `vanban.chinhphu.vn`, `quochoi.vn`, `gdt.gov.vn`.
3. Nguồn tổng hợp tư nhân chỉ để hỗ trợ tìm kiếm; phải ghi rõ giới hạn.

## Hạn chế

- Tài liệu tập trung kỳ tính thuế 2026; không áp dụng máy móc cho kỳ trước.
- Một số văn bản được nhắc trong `sources.md` chưa có bản gốc trong gói.
- Chưa được chuyên gia thuế/luật sư độc lập thẩm định toàn bộ.
- Trước khi kê khai hoặc nộp tiền, phải kiểm tra văn bản hiện hành.

⚠️ Thông tin chỉ mang tính tham khảo, KHÔNG thay thế tư vấn thuế chuyên nghiệp. Kiểm tra tại https://vanban.chinhphu.vn hoặc https://gdt.gov.vn.
