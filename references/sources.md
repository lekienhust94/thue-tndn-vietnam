# Nguồn tham khảo và Confidence Level (v2.0.1)

> Confidence được đánh giá theo từng claim, không gán một mức tuyệt đối cho toàn bộ skill. Xem `source-manifest.yaml` để biết văn bản nào thực sự có trong gói. Một nguồn từng được đọc ở môi trường xây dựng nhưng không có trong gói không được xem là bằng chứng self-contained cho người dùng mới.

## 🟢 Nguồn cao nhất: văn bản gốc do người dùng cung cấp trực tiếp (v1.4.0, 22/07/2026)
Người dùng cung cấp trực tiếp các file gốc (PDF scan ký số hoặc .docx tải từ vanban.chinhphu.vn) trong thư mục project — đây là mức xác nhận cao nhất, KHÔNG qua web fetch nên không bị giới hạn nén nội dung của công cụ (đã gặp ở v1.3.0).

| File gốc | Đã đọc toàn văn? | Dùng để xác minh |
|---|---|---|
| `VanBanGoc_NĐ 320.2025-ndcp.pdf` (76 trang, PDF scan) | ✅ Toàn bộ (Điều 1-26) | `tong-quan-thue.md` (thuế suất, chi phí, chứng từ), `uu-dai-thue.md` (toàn bộ Chương V ưu đãi) |
| `Nghị-định-141-2026-NĐ-CP.docx` | ✅ Toàn văn (chuyển bằng `textutil`) | `uu-dai-thue.md` (miễn thuế ≤1 tỷ đồng/năm) — khớp 100% |
| `Nghị-định-254-2026-NĐ-CP.docx` + Phụ lục | ✅ Toàn văn (chuyển bằng `textutil`) | `hoa-don-dien-tu.md` (cấu trúc, Điều 7, hiệu lực, khen thưởng) |
| `TT 20-2026_BTC.docx` | ✅ Toàn văn (10 Điều + mẫu biểu 01/TNDN, 02/TNDN) | `tong-quan-thue.md` (căn cứ pháp lý, hiệu lực 12/03/2026) |
| `Thông-tư-91-2026-TT-BTC.docx`/`.pdf` | ✅ Toàn văn (thủ tục đăng ký/ngừng/tạm ngừng hóa đơn điện tử) | Xác nhận: TT91 chỉ dẫn chiếu NĐ 125/2020/NĐ-CP cho xử phạt, KHÔNG tự chứa khung phạt cụ thể — `hoa-don-dien-tu.md` vẫn cần NĐ 310/2025/NĐ-CP để xác nhận mức phạt |
| `Nghị-định-49-2026-NĐ-CP.docx` | ✅ Đọc tiêu đề — xác nhận là **Luật Đất đai, KHÔNG liên quan TNDN** | Loại khỏi phạm vi skill |
| `50.2026.pdf`, `QĐ 34 ngày 30.6.2026.docx` | ❌ Chưa xác định mức độ liên quan | Chưa dùng |
| `NĐ-310-2025-NĐ-CP.pdf` (16 trang, PDF scan ký số 02/12/2025) | ✅ Toàn văn (22 khoản sửa đổi/bổ sung NĐ 125/2020/NĐ-CP) | `hoa-don-dien-tu.md` (khung phạt cụ thể theo số lượng hóa đơn — lập sai thời điểm, không lập, cho/bán, tiêu hủy sai...) |
| `Luat-149-2025-QH15.pdf` (2 trang, PDF scan ký số) | ✅ Toàn văn | `thue-gtgt-lien-quan.md` (sửa khoản 25 Điều 5 Luật GTGT — ấn định cứng 500 triệu; sau đó bị Luật 09/2026/QH16 sửa tiếp, xem bên dưới) |
| `Luật-09-2026-QH16.pdf`/`.docx` (2 trang) | ✅ Toàn văn | `thue-gtgt-lien-quan.md`, `uu-dai-thue.md` — Điều 3 bổ sung khoản 14a Điều 4 Luật TNDN (giao Chính phủ quy định ngưỡng miễn thuế → NĐ 141/2026); Điều 2 sửa tiếp khoản 25 Điều 5 Luật GTGT (bỏ ngưỡng cố định 500 triệu, giao Chính phủ quy định) — xem "CẬP NHẬT" bên dưới |
| `Luat-67-2011-QH12.doc` (Luật Kiểm toán độc lập) | ✅ Toàn văn (chuyển bằng `textutil`) | `lich-nghia-vu-doanh-nghiep.md` (Điều 37 — đối tượng bắt buộc kiểm toán BCTC) |
| `ND-68-2026-NDCP.pdf` (19 trang, ký 05/03/2026) | ✅ Toàn văn (19 Điều — chính sách thuế/quản lý thuế hộ, cá nhân kinh doanh) | `thue-gtgt-lien-quan.md` — **CHỐT dứt điểm ngưỡng GTGT hộ kinh doanh = 500 triệu đồng/năm** (Điều 3.1), không phải 1 tỷ như claim cũ; con số 1 tỷ trong nghị định này là ngưỡng khác (bắt buộc hóa đơn điện tử, Điều 8.5.a) |
| `VanBanGoc_nghi-dinh-145-2020-huong-dan-thi-hanh-dieu-kien-lao-dong-va-quan-he-lao-dong.pdf` (122 trang) | ✅ Đọc trang 1-6 (Điều 1-4) | `lich-nghia-vu-doanh-nghiep.md` — **xác nhận chính xác** hạn báo cáo tình hình sử dụng lao động: Điều 4 khoản 2 quy định **trước ngày 05/06** (định kỳ 6 tháng) và **trước ngày 05/12** (định kỳ hằng năm), gửi Sở LĐTBXH qua Cổng DVC Quốc gia (mẫu 01/PLI) + báo cơ quan BHXH cấp huyện. Không có nghĩa vụ báo cáo hằng tháng riêng biệt nào khác trong phạm vi đã đọc |
| `ND-17-2012-NDCP.pdf` (nghị định hướng dẫn Luật Kiểm toán độc lập 67/2011/QH12) | ✅ Trích xuất bằng `pdftotext -layout` (có text layer), đọc Điều 15-16 | `lich-nghia-vu-doanh-nghiep.md` — Điều 15 "Đơn vị được kiểm toán" liệt kê cùng 7 nhóm như Luật, thêm chi tiết công ty mẹ/con có tỷ lệ biểu quyết ≥20%. **Xác nhận KHÔNG có tiêu chí "DN quy mô lớn"** trong cả Luật lẫn nghị định hướng dẫn |
| `ND-12-2022-NDCP.pdf` (83 trang, ký 17/01/2022, xử phạt VPHC lĩnh vực lao động/BHXH/NLĐ đi nước ngoài) | ✅ Đọc trang 1, 9-12 (không có text layer, dùng Read page-image) | `lich-nghia-vu-doanh-nghiep.md` — **đính chính**: đây là nghị định XỬ PHẠT, không phải nghị định quy định nghĩa vụ. Điều 8 khoản 2 điểm c chỉ phạt hành vi "không báo cáo tình hình thay đổi lao động", KHÔNG tự đặt ra hạn báo cáo. Trích dẫn cũ "NĐ 12/2022/NĐ-CP Điều 16" cho hạn báo cáo hằng tháng là **SAI** — đã loại bỏ, gộp vào dòng báo cáo lao động 6 tháng/năm (nguồn đúng: NĐ 145/2020/NĐ-CP) |
| `ND-158-2025-NDCP.pdf` (52 trang, ký 25/06/2025, hướng dẫn Luật BHXH về BHXH bắt buộc) | ✅ Đọc trang 1, 8-14, 45-52 (không có text layer, dùng Read page-image) | `lich-nghia-vu-doanh-nghiep.md` — xác nhận đúng tên/phạm vi nghị định (BHXH bắt buộc) nhưng nội dung đã đọc chỉ gồm: tạm dừng đóng quỹ hưu trí/tử tuất (Điều 10-11), điều kiện/mức hưởng lương hưu và BHXH một lần (Điều 12-15), và sửa đổi mức đóng quỹ TNLĐ-BNN theo NĐ 58/2020/NĐ-CP (cuối văn bản, Điều 44-45 là hiệu lực thi hành). **KHÔNG tìm thấy điều khoản về hạn/phương thức đóng BHXH bắt buộc hằng tháng** trong toàn bộ 52 trang — điều khoản này nằm trực tiếp trong Luật BHXH 41/2024/QH15 Điều 34 khoản 4 (xác nhận qua WebSearch, xem mục bên dưới), không phải trong nghị định hướng dẫn này |
| `Luat-41-2024-QH15-BHXH.pdf` (88 trang, có text layer) | ✅ Toàn văn gốc — tìm thấy trong project (đã bỏ sót ở v1.8.0, không có trong bản global lúc đó) | `lich-nghia-vu-doanh-nghiep.md` — **giải quyết dứt điểm bằng văn bản gốc**: Điều 34 khoản 4 điểm a — đóng hằng tháng → chậm nhất ngày cuối cùng của tháng tiếp theo; đóng theo phương thức 3 tháng/6 tháng một lần → chậm nhất ngày cuối cùng của tháng tiếp theo ngay sau chu kỳ đóng. Khớp 100% với kết quả tra WebSearch trước đó (thuvienphapluat.vn, ebh.vn) — nâng từ "xác nhận qua web" lên xác nhận qua bản gốc. 🟢 HIGH |
| (web, v1.9.0) Nghị định 90/2025/NĐ-CP (sửa đổi, bổ sung khoản 1 Điều 15 NĐ 17/2012/NĐ-CP) | ✅ Xác nhận qua WebSearch (thuvienphapluat.vn, cổng TTĐT tỉnh Cà Mau — camau.gov.vn, kiemtoansts.vn), chưa đọc bản gốc PDF | `lich-nghia-vu-doanh-nghiep.md` — **giải quyết dứt điểm** claim "DN quy mô lớn phải kiểm toán bắt buộc": CÓ THẬT, nhưng căn cứ là NĐ 90/2025/NĐ-CP (mới hơn NĐ 17/2012/NĐ-CP gốc đã đọc), bổ sung tiêu chí "quy mô lớn" = đạt ≥2/3 trong 3 tiêu chí (lao động BHXH bình quân >200 người, doanh thu năm >300 tỷ, tổng tài sản >100 tỷ), tính theo BCTC năm liền trước, áp dụng kiểm toán bắt buộc cho BCTC năm sau. 🟢 HIGH (nhiều nguồn độc lập khớp nhau dù chưa phải bản gốc; nếu cần trích dẫn chính xác tuyệt đối ngày ban hành/hiệu lực nên đối chiếu thêm bản gốc) |

## ⚠️ Lưu ý về bản chất các nguồn (đính chính)
- **vanban.chinhphu.vn**, **quochoi.vn**, **gdt.gov.vn** — nguồn **CHÍNH THỐNG** (cơ quan nhà nước, đăng văn bản gốc/công báo).
- **thuvienphapluat.vn** (LawSoft) và **luatvietnam.vn** (LuatVietnam JSC) — **CÔNG TY TƯ NHÂN**, không phải nhà nước. Họ số hóa/tổng hợp văn bản luật để bán dịch vụ tra cứu, thường trích y nguyên văn bản gốc nên độ tin cậy cao trong thực tế, nhưng về bản chất pháp lý không phải nguồn công bố chính thức.
- thuvienphapluat.vn chặn WebFetch tự động (trả lỗi 403 Forbidden) cho các trang: toàn văn NĐ 320/2025/NĐ-CP (Điều 19), NĐ 254/2026/NĐ-CP, Luật 149/2025/QH15, Thông tư 20/2026/TT-BTC — có thể do chặn bot/crawler, không phải nội dung bị hạn chế truy cập thông thường (người dùng vẫn xem được bằng trình duyệt thật).
- **luatvietnam.vn không bị chặn** trong phiên làm việc này và đã dùng thành công để lấy lại phần lớn nội dung bị thuvienphapluat.vn chặn — nâng nhiều mục từ 🟡 MEDIUM lên 🟢 HIGH.

## Phát hiện mới quan trọng (qua luatvietnam.vn)
| Nội dung | Chi tiết | Confidence |
|---|---|---|
| Luật 09/2026/QH16 | Đã đọc toàn văn gốc (v1.7.0): thông qua **24/04/2026**, sửa đồng thời Luật TNCN, GTGT, TNDN, TTĐB. Điều 3 bổ sung khoản 14a Điều 4 Luật TNDN 67/2025/QH15 — giao Chính phủ quy định ngưỡng miễn thuế TNDN (→ NĐ 141/2026/NĐ-CP cụ thể hóa = 1 tỷ đồng). **Điều 2 sửa TIẾP khoản 25 Điều 5 Luật GTGT** (khoản mà Luật 149/2025/QH15 vừa mới ấn định cứng 500 triệu đồng) — bỏ con số cố định, thay bằng "mức do Chính phủ quy định". Điều 1-3 hiệu lực từ **01/01/2026** (dù ban hành sau, áp dụng cùng mốc hiệu lực với Luật 149/2025/QH15) | 🟢 HIGH — đã đọc toàn văn gốc PDF/docx |
| Nghị định 141/2026/NĐ-CP | Ban hành 29/04/2026, hiệu lực 01/01/2026 — cụ thể hóa ngưỡng miễn thuế TNDN = **1 tỷ đồng/năm** (thay 500 triệu cũ), bổ sung Khoản 15 Điều 4 NĐ 320/2025/NĐ-CP | 🟢 HIGH (khớp amis.misa.vn, einvoice.vn, misaeshop.vn, fastca.vn) |
| ✅ CHỐT (v1.7.0, thay cho "CẬP NHẬT" tạm thời trước đó): ngưỡng GTGT hộ/cá nhân kinh doanh KHÔNG chịu thuế | Trình tự: Luật 149/2025/QH15 ấn định cứng 500 triệu → Luật 09/2026/QH16 sửa tiếp, bỏ con số cố định, giao Chính phủ quy định → **NĐ 68/2026/NĐ-CP Điều 3.1 cụ thể hóa: giữ nguyên 500 triệu đồng/năm** (Chính phủ KHÔNG thay đổi con số, dù có quyền). Claim cũ "nâng lên 1 tỷ qua NĐ 68/2026/NĐ-CP" là **SAI** — đã đọc toàn văn gốc và xác nhận: con số 1 tỷ trong nghị định này là một ngưỡng khác — bắt buộc dùng hóa đơn điện tử có mã cơ quan thuế khi doanh thu GTGT ≥1 tỷ đồng/năm (Điều 8 khoản 5 điểm a) — không liên quan đến việc có chịu thuế GTGT hay không. Đây là bài học: hai ngưỡng số khác nhau trong cùng 1 nghị định dễ bị nhầm lẫn khi chỉ đọc snippet/trích dẫn thứ cấp thay vì toàn văn. Xem chi tiết trong `thue-gtgt-lien-quan.md`. | 🟢 HIGH — đã đọc toàn văn gốc NĐ 68/2026/NĐ-CP (19 trang), hết nghi vấn |


## Đã xác nhận qua nguồn chính thống (vanban.chinhphu.vn)
| Nội dung | Xác nhận | Confidence |
|---|---|---|
| Nghị định 320/2025/NĐ-CP tồn tại, ký 15/12/2025, hướng dẫn Luật 67/2025/QH15, thay thế NĐ 218/2013 và 91/2014 | Fetch trực tiếp vanban.chinhphu.vn (?pageid=27160&docid=216219), có file PDF ký số | 🟢 HIGH |
| Nghị định 320/2025/NĐ-CP có Điều 11 (thuế suất), Điều 10 (chi không được trừ), Điều 18-19 (ưu đãi thuế) | Đã đọc toàn văn gốc 76 trang (v1.4.0) | 🟢 HIGH — nội dung chi tiết đã xác nhận đầy đủ, không còn phụ thuộc snippet web |
| **ĐÍNH CHÍNH**: "252/2025/NĐ-CP" KHÔNG tồn tại cho TNDN — số đúng là **252/2026/NĐ-CP**, về Luật Quản lý thuế, không phải TNDN | Search + WebFetch xác nhận | 🟢 HIGH |

## Chưa fetch được toàn văn (bị chặn 403 khi truy cập tự động)
- thuvienphapluat.vn: hầu hết văn bản luật/nghị định trả 403 Forbidden khi WebFetch trực tiếp — chỉ lấy được qua search snippet (bị nén, thiếu chi tiết).
- vanban.chinhphu.vn: fetch được nhưng nội dung trả về bị nén mạnh bởi tool nội bộ, không đầy đủ toàn văn Điều 19.
- **Khuyến nghị mạnh**: người dùng nên tự tra cứu trực tiếp 2 nguồn này bằng trình duyệt thường khi cần trích dẫn chính xác cho hồ sơ pháp lý.

## Theo chủ đề

| Nội dung | Nguồn | Confidence |
|---|---|---|
| Luật Thuế TNDN 67/2025/QH15, hiệu lực 01/10/2025 | amis.misa.vn, thuvienphapluat.vn (snippet), vanban.chinhphu.vn | 🟢 HIGH |
| Thuế suất 15%/17%/20% theo doanh thu | quocluat.vn, amis.misa.vn, einvoice.vn, xcyber.vn (nhiều nguồn khớp) | 🟢 HIGH |
| Ưu đãi thuế theo ngành/vùng (bảng trong uu-dai-thue.md) | Đã đọc toàn văn gốc Chương V (Điều 18-23) NĐ 320/2025/NĐ-CP (v1.4.0) | 🟢 HIGH |
| Thuế suất đặc thù khai khoáng (50%/40%) | xcyber.vn, khớp với Điều 10-11 NĐ 320/2025 | 🟢 HIGH |
| Quy tắc tạm nộp TNDN 80% | thuvienphapluat.vn (snippet), gialai.gov.vn (cổng thông tin tỉnh), easybooks.vn | 🟢 HIGH |
| Hạn quyết toán TNDN/TNCN/BCTC (90 ngày, ≈31/03) | thuvienphapluat.vn (nhiều bài viết, snippet đồng nhất) | 🟢 HIGH |
| Thuế suất GTGT 10%/8%/5%/0%, gia hạn giảm 8% cả năm 2026 | thuvienphapluat.vn, acman.vn (khớp nhau) | 🟢 HIGH |
| Luật GTGT sửa đổi 149/2025/QH15 — chi tiết điều chỉnh | Đã đọc toàn văn gốc (2 trang, PDF scan ký số, thông qua 11/12/2025) | 🟢 HIGH |
| Ngưỡng kê khai GTGT tháng/quý (50 tỷ) | ketoanthuanthien.vn, einvoice.vn, xcyber.vn | 🟢 HIGH |
| Hóa đơn điện tử — NĐ 254/2026/NĐ-CP thay thế NĐ 123/2020 | Đã đọc toàn văn gốc (file .docx do người dùng cung cấp) | 🟢 HIGH (tồn tại văn bản và nội dung chi tiết) |
| Mức phạt vi phạm hóa đơn (NĐ 310/2025/NĐ-CP) | Đã đọc toàn văn gốc 16 trang (v1.6.0) | 🟢 HIGH — khung phạt cụ thể theo số lượng hóa đơn đã xác nhận đầy đủ |
| Thuế môn bài bãi bỏ từ 01/01/2026 | thuvienphapluat.vn, meinvoice.vn (khớp nhau) | 🟢 HIGH |
| Đóng BHXH/BHYT/BHTN, báo cáo lao động | *(dòng cũ đã lỗi thời — xem 2 dòng chi tiết bên trên: NĐ 145/2020/NĐ-CP cho báo cáo lao động, Luật BHXH 41/2024/QH15 Điều 34.4 cho hạn đóng BHXH)* | 🟢 HIGH (xem chi tiết bên trên) |

## Hạn chế chung của skill (v2.0.1)

- Phần TNDN lõi, thủ tục tạm nộp và gia hạn đã được xây dựng từ các văn bản gốc quan trọng do người dùng cung cấp:
  - Nghị định 320/2025/NĐ-CP (76 trang full text)
  - **Nghị định 252/2026/NĐ-CP** (1416+ dòng full text) — thay thế NĐ 126/2020 và NĐ 91/2022 từ 01/07/2026
  - **Nghị định 245/2026/NĐ-CP** (full text) — gia hạn nộp thuế 2026
  - Nghị định 254/2026/NĐ-CP (full text) — hóa đơn điện tử
  - Thông tư 20/2026/TT-BTC (full text 10 điều + mẫu biểu)
  - Nghị định 68/2026/NĐ-CP, Nghị định 310/2025/NĐ-CP, Nghị định 145/2020, NĐ 12/2022, NĐ 17/2012, Luật 41/2024/QH15...
- Một số claim ngoài TNDN cốt lõi vẫn phải xem là 🟡 MEDIUM khi bản gốc chưa được đóng gói, điển hình nội dung dựa trên Nghị định 90/2025/NĐ-CP.
- CHƯA qua bước đối chiếu chuyên gia thuế/luật sư độc lập.
- Khuyến nghị trước khi dùng cho quyết định thực tế: đối chiếu trực tiếp bằng trình duyệt thường tại thuvienphapluat.vn, vanban.chinhphu.vn, gdt.gov.vn, hoặc tham vấn kế toán/luật sư thuế.

---
Data cập nhật: 23/07/2026.
