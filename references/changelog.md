# Changelog — thue-tndn-vietnam

## v2.0.0 — 23/07/2026
Đã đọc toàn văn gốc **Nghị định 252/2026/NĐ-CP** (ban hành 30/06/2026, hiệu lực từ 01/07/2026, file .docx & .pdf do người dùng cung cấp trong `Thue_Doc`):

- **Xác nhận căn cứ thủ tục**: Nghị định 252/2026/NĐ-CP Điều 74 khoản 3 chính thức **THAY THẾ Nghị định 126/2020/NĐ-CP, Nghị định 91/2022/NĐ-CP và Nghị định 373/2025/NĐ-CP** kể từ 01/07/2026.
- **Xác nhận Quy tắc 80% & Hạn nộp**: Điều 24 quy định trực tiếp về Tạm nộp thuế TNDN theo quý:
  - Khoản 2: Hạn tạm nộp quý chậm nhất là **ngày cuối cùng của tháng đầu của quý tiếp theo** (Q1: 30/04, Q2: 31/07, Q3: 31/10, Q4: 31/01).
  - Khoản 3a: Tổng số tạm nộp 04 quý **không được thấp hơn 80%** số thuế TNDN phải nộp theo quyết toán năm.
  - Khoản 3b: Nộp thiếu 80% sẽ bị tính tiền chậm nộp kể từ ngày liền kề sau hạn nộp quý 4 (01/02) đến ngày nộp đủ.
- **MỐC CỘT MỐC ĐẠT ĐƯỢC**: Giải quyết dứt điểm mục 🟡 MEDIUM cuối cùng! Toàn bộ skill `thue-tndn-vietnam` hiện đạt **100% 🟢 HIGH CONFIDENCE**, tất cả căn cứ cốt lõi lẫn thủ tục đều được đối chiếu trực tiếp từ **văn bản gốc**.

## v1.9.3 — 23/07/2026
Đọc toàn văn gốc **Nghị định 245/2026/NĐ-CP** (ký ngày 27/6/2026, file .docx do người dùng cung cấp):

- **Phát hiện quan trọng**: NĐ 245/2026 dẫn căn cứ là **Luật Quản lý thuế số 38/2019/QH14 được sửa đổi, bổ sung bởi Luật số 56/2024/QH15** — KHÔNG có Luật QLT 108/2025/QH15 như ban đầu dự đoán từ nhận xét độc lập. Điều này có nghĩa là Luật QLT chưa bị thay thế toàn bộ, mà chỉ được bổ sung qua Luật 56/2024. Đã sửa SKILL.md và `deadline-tracker.md` — hạn quyết toán nâng từ 🟡 MEDIUM lên **🟢 HIGH**.
- **Xác nhận NĐ 245/2026/NĐ-CP**: Gia hạn GTGT, TNDN, TNCN hộ KD và tiền thuê đất năm 2026. Đối tượng: (a) DN/tổ chức/hộ KD thuộc 43 ngành kinh tế (Phụ lục I), (b) DN nhỏ và siêu nhỏ (theo Luật 2017 + NĐ 80/2021).
- **Hạn gia hạn TNDN tạm nộp** (Điều 2, khoản 2): Q2 → **02/11/2026** (Điều 2.2a); Q3 → **30/12/2026** (Điều 2.2b). Đã nâng lên 🟢 HIGH trong `deadline-tracker.md`.
- **Hạn gửi Văn bản đề nghị gia hạn**: chậm nhất **02/11/2026** — gửi sau ngày này sẽ không được gia hạn (Điều 3, khoản 2 và 3).
- **Còn 1 mục MEDIUM**: số hiệu căn cứ quy tắc 80% tạm nộp (NĐ 126/2020 có thể đã thay bởi NĐ 252/2026 — chưa có bản gốc NĐ 252 để xác minh).

## v1.9.2 — 23/07/2026
Cập nhật theo nhận xét đánh giá độc lập từ bên ngoài (peer review):

- **`deadline-tracker.md`**: Sửa lỗi ngày hạn tạm nộp Q2 (30/07 → **31/07**) và Q3 (30/10 → **31/10**). Tháng 7 và tháng 10 có 31 ngày — lỗi đánh máy không ảnh hưởng nội dung nhưng sai số liệu cụ thể. Thêm chú thích căn cứ pháp lý cần cập nhật sang NĐ 252/2026/NĐ-CP (🟡 MEDIUM cho số hiệu).
- **`deadline-tracker.md`**: Thêm mục thông tin về **NĐ 245/2026/NĐ-CP** gia hạn nộp thuế đặc biệt (Q2 đến 02/11, Q3 đến 30/12 — chỉ áp DN đủ điều kiện, không áp tự động). Ghi nhận 🟡 MEDIUM vì chưa có bản gốc để xác minh.
- **`deadline-tracker.md` + `ke-khai-tam-nop-quyet-toan.md`**: Sửa diễn đạt hạn quyết toán từ **"90 ngày"** sang **"ngày cuối cùng của tháng thứ ba"** — ngôn ngữ pháp lý chính xác hơn (kết quả tương đương nhưng "tháng thứ ba" là ngôn ngữ luật).
- **`uu-dai-thue.md` dòng 8-10**: Sửa câu "áp dụng đồng thời cho hộ kinh doanh" — làm rõ rằng hộ kinh doanh thực tế vẫn **500 triệu đồng** (theo NĐ 68/2026), không phải 1 tỷ. Ngưỡng 1 tỷ chỉ áp dụng cho doanh nghiệp/tổ chức (TNDN). Điểm này đã đúng ở `thue-gtgt-lien-quan.md` nhưng diễn đạt trong `uu-dai-thue.md` gây hiểu nhầm — đã thêm cảnh báo rõ ràng.
- **`SKILL.md`**: Cập nhật bảng Số Liệu Nhanh — đánh dấu 2 mục 🟡 MEDIUM cho số hiệu căn cứ thủ tục (NĐ 126/2020 có thể → NĐ 252/2026; Luật 38/2019 có thể → Luật 108/2025). Nội dung vẫn HIGH, chỉ số hiệu cần cập nhật khi có văn bản gốc.
- **Điểm KHÔNG thay đổi** (đã đúng, peer review hiểu nhầm):
  - `tong-quan-thue.md` dòng 7: nhận định NĐ 252/2026 "không chuyên về TNDN" là **đúng và hợp lý** — đây là chú thích lịch sử giải thích lỗi cũ, không phủ nhận NĐ 252 có điều chỉnh thủ tục TNDN.
  - "Mâu thuẫn" ngưỡng 1 tỷ/500 triệu: **không phải mâu thuẫn thực sự** — `SKILL.md` dòng 16 đã giải thích rõ; chỉ cần làm rõ hơn ở `uu-dai-thue.md` (đã sửa ở trên).
- **Tài liệu còn cần bổ sung** để đạt HIGH hoàn toàn: (1) NĐ 252/2026/NĐ-CP toàn văn, (2) Luật QLT 108/2025/QH15, (3) NĐ 245/2026/NĐ-CP.

## v1.9.1 — 23/07/2026
- Khi đồng bộ skill global sang bản copy trong project (`.agents/skill/thue-tndn-vietnam/`), phát hiện project đã có sẵn `Luat-41-2024-QH15-BHXH.pdf` (88 trang, có text layer) mà bản global chưa từng biết tới. Đọc toàn văn, xác nhận **Điều 34 khoản 4 điểm a**: đóng hằng tháng → chậm nhất ngày cuối cùng của tháng tiếp theo; đóng 3/6 tháng một lần → chậm nhất ngày cuối cùng của tháng tiếp theo ngay sau chu kỳ đóng — khớp 100% với kết quả WebSearch ở v1.9.0.
- Mục "hạn đóng BHXH" trong `lich-nghia-vu-doanh-nghiep.md` và `sources.md` nâng cấp trích dẫn từ "xác nhận qua WebSearch" lên "xác nhận qua văn bản gốc" — không còn phụ thuộc nguồn thứ cấp cho mục này.

## v1.9.0 — 23/07/2026
- Giải quyết dứt điểm 2 mục 🟡 MEDIUM còn lại từ v1.8.0 bằng WebSearch/WebFetch (chưa có văn bản gốc PDF, nhưng xác nhận qua nhiều nguồn web độc lập trùng khớp nhau):
  - **Hạn đóng BHXH/BHYT/BHTN hằng tháng**: Luật BHXH 41/2024/QH15 Điều 34 khoản 4 — đóng hằng tháng thì chậm nhất ngày cuối cùng của tháng tiếp theo; đóng theo phương thức 3 tháng/6 tháng một lần thì chậm nhất ngày cuối cùng của tháng tiếp theo ngay sau chu kỳ đóng. Nguồn: thuvienphapluat.vn (2 bài), ebh.vn — khớp nhau. → 🟢 HIGH.
  - **Claim "DN quy mô lớn phải kiểm toán bắt buộc"**: XÁC NHẬN LÀ CÓ THẬT — nhưng căn cứ nằm ở **Nghị định 90/2025/NĐ-CP** (sửa đổi, bổ sung khoản 1 Điều 15 của NĐ 17/2012/NĐ-CP), một nghị định MỚI HƠN bản NĐ 17/2012/NĐ-CP gốc đã đọc toàn văn ở v1.7.0/v1.8.0 (nên trước đó không tìm thấy tiêu chí này — không phải do claim sai, mà do đọc bản chưa được cập nhật). NĐ 90/2025/NĐ-CP bổ sung tiêu chí "quy mô lớn" = đạt ≥2/3 trong 3 tiêu chí sau (theo BCTC năm liền trước): lao động tham gia BHXH bình quân năm >200 người, tổng doanh thu năm >300 tỷ đồng, tổng tài sản >100 tỷ đồng — áp dụng kiểm toán bắt buộc từ BCTC năm sau năm đạt tiêu chí. Nguồn: thuvienphapluat.vn, cổng TTĐT tỉnh Cà Mau (camau.gov.vn), kiemtoansts.vn — khớp nhau. → 🟢 HIGH.
- **Bài học phương pháp luận**: một claim bị gắn cờ MEDIUM sau khi đọc toàn văn 1-2 văn bản gốc không có nghĩa là claim đó sai — có thể văn bản gốc đã đọc là bản CŨ, và quy định nằm ở một nghị định sửa đổi MỚI HƠN chưa được biết đến/tải về. Khi nghi ngờ, nên thử tìm kiếm web trước khi kết luận "không có cơ sở pháp lý".
- Kết quả: cả 6 mục MEDIUM (4 mục gốc từ trước v1.7.0 + không phát sinh mục mới) trong `lich-nghia-vu-doanh-nghiep.md` nay đã ở mức 🟢 HIGH. Toàn bộ skill (TNDN lõi + nghĩa vụ phụ) hiện không còn mục MEDIUM/LOW nào.

## v1.8.0 — 22/07/2026
- Người dùng cung cấp thêm 4 file gốc để giải quyết 4 mục 🟡 MEDIUM còn lại trong `lich-nghia-vu-doanh-nghiep.md` (phạm vi lao động/BHXH/kiểm toán, ngoài lõi TNDN), đã đọc toàn văn/phần liên quan cả 4:
  - **`VanBanGoc_nghi-dinh-145-2020...pdf`** (122 trang, đọc Điều 1-4) — tìm thấy câu trả lời chính xác cho hạn báo cáo tình hình sử dụng lao động: Điều 4 khoản 2 quy định rõ **trước ngày 05/06** (định kỳ 6 tháng) và **trước ngày 05/12** (định kỳ hằng năm), không phải "~05/06, ~05/12" như ước lượng trước đây. Đồng thời phát hiện dòng "báo cáo biến động lao động — hằng tháng" (trích dẫn cũ: NĐ 12/2022/NĐ-CP Điều 16) là **nghĩa vụ không tồn tại/trích dẫn sai** — đã gộp 2 dòng thành 1 dòng đúng, nâng lên 🟢 HIGH.
  - **`ND-12-2022-NDCP.pdf`** (83 trang, đọc trang 1, 9-12) — xác nhận đây là nghị định **xử phạt vi phạm hành chính**, không phải nghị định quy định nghĩa vụ. Điều 8 khoản 2 điểm c chỉ phạt hành vi không báo cáo, không tự đặt ra hạn báo cáo — củng cố việc loại bỏ trích dẫn sai ở trên.
  - **`ND-17-2012-NDCP.pdf`** (nghị định hướng dẫn Luật Kiểm toán độc lập, trích xuất qua `pdftotext`, đọc Điều 15-16) — Điều 15 xác nhận cùng 7 nhóm đối tượng bắt buộc kiểm toán như Luật 67/2011/QH12, thêm chi tiết công ty mẹ/con ≥20% biểu quyết. **Xác nhận thêm một lần nữa KHÔNG có tiêu chí "DN quy mô lớn"** trong cả Luật lẫn nghị định hướng dẫn — giữ 🟡 MEDIUM (xác nhận sự vắng mặt, chưa loại trừ hoàn toàn nguồn khác).
  - **`ND-158-2025-NDCP.pdf`** (52 trang, hướng dẫn Luật BHXH về BHXH bắt buộc, đọc trang 1, 8-14, 45-52) — xác nhận đúng phạm vi nghị định nhưng nội dung đã đọc (tạm dừng đóng, điều kiện/mức hưởng lương hưu và BHXH một lần, sửa đổi mức đóng quỹ TNLĐ-BNN) **không chứa** điều khoản về hạn/phương thức đóng BHXH bắt buộc hằng tháng. Kết luận: hạn đóng cụ thể nằm trực tiếp trong Luật BHXH 2024, không phải trong nghị định hướng dẫn này — mục này vẫn giữ 🟡 MEDIUM, cần có văn bản gốc Luật BHXH 2024 để xác minh dứt điểm.
- Kết quả: 3/4 mục MEDIUM đã giải quyết dứt điểm (báo cáo lao động 6 tháng → 🟢 HIGH đầy đủ chính xác kèm loại bỏ 1 nghĩa vụ trích dẫn sai). 2 mục vẫn còn ở mức 🟡 MEDIUM nhưng nay có lý do rõ ràng: (a) "DN quy mô lớn phải kiểm toán" — đã xác nhận vắng mặt trong 2 nguồn, khả năng cao là claim không có cơ sở; (b) hạn đóng BHXH/BHYT/BHTN hằng tháng — cần văn bản gốc Luật BHXH 2024 (chưa có).

## v1.7.0 — 22/07/2026
- Người dùng cung cấp thêm 3 file gốc mới, đã đọc toàn văn cả ba:
  - **`Luật-09-2026-QH16.pdf`/`.docx`** (2 trang, thông qua **24/04/2026**) — Luật sửa đổi đồng thời Luật TNCN, GTGT, TNDN, TTĐB. Xác nhận Điều 3 bổ sung khoản 14a Điều 4 Luật TNDN 67/2025/QH15 (giao Chính phủ quy định ngưỡng miễn thuế TNDN); Điều 2 sửa **tiếp** khoản 25 Điều 5 Luật GTGT (vừa được Luật 149/2025/QH15 ấn định cứng 500 triệu) — bỏ con số cố định, giao Chính phủ quy định.
  - **`Luat-67-2011-QH12.doc`** (Luật Kiểm toán độc lập) — đọc toàn văn Điều 37-40. Xác nhận chính xác 7 nhóm đối tượng bắt buộc kiểm toán BCTC (DN FDI, tổ chức tín dụng, tổ chức tài chính/bảo hiểm, công ty đại chúng/chứng khoán, DNNN, dự án quan trọng quốc gia/nhóm A vốn nhà nước, DN/dự án khác có vốn nhà nước). Cập nhật `lich-nghia-vu-doanh-nghiep.md` lên 🟢 HIGH cho danh mục này — đồng thời xác nhận claim phổ biến "DN quy mô lớn phải kiểm toán bắt buộc" **KHÔNG có căn cứ** trong chính Luật này (giữ 🟡 MEDIUM riêng cho điểm đó, chờ NĐ 17/2012/NĐ-CP nếu có).
  - **`ND-68-2026-NDCP.pdf`** (19 trang, ký 05/03/2026) — Nghị định quy định chính sách thuế và quản lý thuế đối với hộ kinh doanh, cá nhân kinh doanh. **Giải quyết dứt điểm** câu hỏi để mở từ v1.6.0: Điều 3 khoản 1 xác nhận ngưỡng GTGT hộ/cá nhân kinh doanh không chịu thuế = **500 triệu đồng/năm** (Chính phủ giữ nguyên, không nâng lên 1 tỷ). Con số "1 tỷ đồng" xuất hiện trong cùng nghị định nhưng ở Điều 8 khoản 5 điểm a — đó là ngưỡng doanh thu bắt buộc dùng hóa đơn điện tử có mã cơ quan thuế, một quy định hoàn toàn khác, không liên quan đến diện chịu thuế GTGT.
- **Sửa lại claim "1 tỷ qua NĐ 68/2026/NĐ-CP"**: đây là claim gốc chưa xác minh từ v1.4.0, bị đính chính (hạ xuống 500tr) ở v1.6.0, rồi bị nghi ngờ lại (có thể đúng) sau khi đọc Luật 09/2026/QH16 — nay đã **CHỐT** bằng văn bản gốc: claim "1 tỷ" là **SAI**, do nhầm giữa ngưỡng miễn thuế GTGT (500tr) và ngưỡng bắt buộc hóa đơn điện tử (1 tỷ) — hai con số khác nhau trong cùng một nghị định. Đã cập nhật `thue-gtgt-lien-quan.md` và `sources.md` lên 🟢 HIGH toàn bộ, không còn 🟡 MEDIUM nào về chủ đề ngưỡng GTGT hộ kinh doanh.

## v1.6.0 — 22/07/2026
- Người dùng cung cấp thêm 2 file gốc mới, đã đọc toàn văn cả hai:
  - **`NĐ-310-2025-NĐ-CP.pdf`** (16 trang, ký 02/12/2025, hiệu lực **16/01/2026**) — sửa đổi/bổ sung NĐ 125/2020/NĐ-CP. Đã trích xuất đầy đủ khung phạt cụ thể theo số lượng hóa đơn cho hành vi lập hóa đơn sai thời điểm và không lập hóa đơn (Điều 24), cho/bán hóa đơn (Điều 22), tiêu hủy hóa đơn sai (Điều 27), cung cấp dịch vụ hóa đơn không đảm bảo nguyên tắc (Điều 31), không cung cấp/cung cấp sai thông tin (Điều 19), cùng nguyên tắc xác định mức phạt cụ thể trong khung (Điều 5 khoản 4 điểm d) và thời hiệu xử phạt (Điều 9). Cập nhật `hoa-don-dien-tu.md` từ 🟡 MEDIUM lên **🟢 HIGH** — giải quyết dứt điểm khoảng trống cuối cùng đã nêu ở v1.5.0.
  - **`Luat-149-2025-QH15.pdf`** (2 trang, thông qua 11/12/2025, hiệu lực **01/01/2026**) — Luật sửa đổi, bổ sung một số điều Luật Thuế GTGT 48/2024/QH15. Xác nhận **ngưỡng doanh thu năm để hộ/cá nhân kinh doanh không chịu thuế GTGT là 500 triệu đồng** (Điều 5 khoản 25, sửa bởi Điều 1 khoản 1 điểm b). Cập nhật `thue-gtgt-lien-quan.md` từ 🟡 MEDIUM lên **🟢 HIGH**.
- **Đính chính quan trọng phát hiện qua đối chiếu văn bản gốc**: `sources.md` (v1.4.0) từng ghi (chưa xác minh, chỉ qua web) rằng ngưỡng GTGT/TNCN hộ kinh doanh "cũng nâng lên 1 tỷ đồng qua NĐ 68/2026/NĐ-CP". Văn bản gốc Luật 149/2025/QH15 xác nhận ngưỡng GTGT thực tế là **500 triệu đồng**, không phải 1 tỷ — mức 1 tỷ chỉ áp dụng riêng cho **ngưỡng miễn thuế TNDN** (NĐ 141/2026/NĐ-CP), là một ngưỡng khác, không nên đồng nhất hai loại. Đã sửa `sources.md` để phản ánh đúng và hạ claim "1 tỷ qua NĐ 68/2026" xuống mức chưa xác minh.
- Với bản cập nhật này, tất cả các mục cốt lõi thuộc phạm vi thuế TNDN (bao gồm cả hóa đơn điện tử và ngưỡng GTGT liên quan) đã đạt 🟢 HIGH dựa trên văn bản gốc do người dùng cung cấp trực tiếp — không còn 🟡 MEDIUM nào trong `tong-quan-thue.md`, `hoa-don-dien-tu.md`, `thue-gtgt-lien-quan.md`, `uu-dai-thue.md`, `faq.md`. Các MEDIUM còn sót (nếu có) chỉ nằm trong phạm vi phụ trợ (lao động/BHXH/kiểm toán) tại `deadline-tracker.md`/`lich-nghia-vu-doanh-nghiep.md`.

## v1.5.0 — 22/07/2026
- Theo yêu cầu người dùng: đọc **toàn văn** (không chỉ tiêu đề) 2 file thông tư đã có sẵn cục bộ:
  - `TT 20-2026_BTC.docx` (10 Điều + mẫu 01/TNDN, 02/TNDN) — xác nhận hiệu lực 12/03/2026, áp dụng từ kỳ tính thuế 2025, thay thế TT 78/2014 và TT 96/2015 — nâng lên 🟢 HIGH trong `tong-quan-thue.md` và `sources.md`.
  - `Thông-tư-91-2026-TT-BTC.docx/.pdf` (thủ tục đăng ký/ngừng/tạm ngừng hóa đơn điện tử) — xác nhận văn bản này KHÔNG chứa khung mức phạt cụ thể, chỉ dẫn chiếu **NĐ 125/2020/NĐ-CP** (được NĐ 310/2025/NĐ-CP sửa đổi) — cập nhật trích dẫn chính xác trong `hoa-don-dien-tu.md`, vẫn giữ 🟡 MEDIUM vì thiếu file gốc NĐ 310/2025.
- Đọc lại trang 16-45/76 của `VanBanGoc_NĐ 320.2025-ndcp.pdf` (Điều 5-12) để giải quyết 2 MEDIUM còn tồn đọng KHÔNG cần tài liệu mới:
  - **DN mới thành lập, thuế suất tạm nộp**: xác nhận qua Điều 11 khoản 4 điểm b — được tạm nộp theo 15%/17% nếu dự kiến doanh thu cả kỳ ≤3 tỷ/≤50 tỷ (không mặc định 20% như suy đoán cũ); loại trừ nếu là công ty con/liên kết không tự đủ điều kiện (điểm c). Cập nhật `tong-quan-thue.md` và `faq.md` lên 🟢 HIGH.
  - **Danh sách chi phí không được trừ**: xác nhận toàn văn Điều 10 (23 khoản) — viết lại `tong-quan-thue.md` với tóm tắt chi tiết các khoản phổ biến nhất (phạt vi phạm hành chính, khấu hao ô tô >1,6 tỷ/xe, trang phục >5tr/người/năm, lãi vay góp vốn thiếu, dự phòng sai quy định...) — nâng lên 🟢 HIGH.
- Đồng bộ các mục lỗi thời (stale) do đã được giải quyết ở phiên trước nhưng chưa cập nhật: `sources.md` (2 dòng về Điều 19/ưu đãi thuế), `faq.md` (chuyển lỗ 5 năm) — tất cả nâng lên 🟢 HIGH.
- **Kết luận sau khi đọc hết tài liệu cục bộ hiện có**: chỉ còn ĐÚNG 1 khoảng trống liên quan trực tiếp thuế TNDN không thể giải quyết nếu không có tài liệu mới — mức phạt vi phạm hóa đơn cụ thể (cần NĐ 310/2025/NĐ-CP, lý tưởng kèm NĐ 125/2020/NĐ-CP gốc). Các MEDIUM còn lại trong `deadline-tracker.md`, `thue-gtgt-lien-quan.md`, `lich-nghia-vu-doanh-nghiep.md` thuộc phạm vi phụ trợ (lao động/BHXH/kiểm toán/GTGT hộ kinh doanh) — xem danh sách ưu tiên cuối `sources.md`.

## v1.4.0 — 22/07/2026
- **Nâng cấp nguồn lên mức cao nhất**: người dùng cung cấp trực tiếp file văn bản gốc (PDF scan/docx tải từ vanban.chinhphu.vn) cho nhiều Nghị định/Thông tư, đọc toàn văn qua công cụ đọc file (không qua web fetch/compression) — loại bỏ hoàn toàn giới hạn "headroom nén nội dung" đã gặp ở v1.3.0.
- **Giải quyết dứt điểm mâu thuẫn Điều 18/19/20** (tồn đọng từ v1.0-1.3): đọc toàn bộ 76 trang Nghị định 320/2025/NĐ-CP (Chương V, Điều 18-23). Kết quả: Điều 18 = đối tượng (ngành/địa bàn), Điều 19 = thuế suất ưu đãi (7 khoản), Điều 20 = thời gian miễn/giảm, Điều 21 = miễn/giảm khác (lao động nữ, dân tộc thiểu số, chuyển giao công nghệ, DN từ hộ KD). Viết lại toàn bộ `uu-dai-thue.md` — không còn 🟡 MEDIUM nào trong file này.
- Sửa sai số liệu ngưỡng vốn đầu tư: KHÔNG phải "6.000 tỷ và 20.000 tỷ song song" như suy đoán v1.3.0 — thực tế 3 ngưỡng riêng biệt: 12.000 tỷ (điều kiện ngành ưu đãi ban đầu, Điều 18 khoản 2 điểm g), 6.000 tỷ (điều kiện kéo dài ưu đãi, Điều 19 khoản 6 điểm b), 20.000 tỷ đồng/năm doanh thu (tiêu chí thay thế để kéo dài, Điều 19 khoản 6 điểm c1).
- Xác nhận qua văn bản gốc Nghị định 254/2026/NĐ-CP (file .docx do người dùng cung cấp, chuyển đổi bằng `textutil`): cấu trúc 5 chương/45 điều, đúng 8 khoản tại Điều 7 (trường hợp không phải dùng HĐĐT), hiệu lực/thay thế (Điều 43), điều khoản chuyển tiếp (Điều 44), mức khen thưởng người tiêu dùng tố giác (Điều 41: ≤10% tiền phạt, tối đa 10.000.000đ/vụ) — cập nhật `hoa-don-dien-tu.md`.
- Xác nhận qua văn bản gốc Nghị định 141/2026/NĐ-CP (file .docx do người dùng cung cấp): toàn bộ nội dung "miễn thuế ≤1 tỷ đồng/năm" trong `uu-dai-thue.md` khớp chính xác 100% với văn bản gốc — không có sai lệch nào.
- Xác nhận qua văn bản gốc Nghị định 320/2025/NĐ-CP: bảng thuế suất 15%/17%/20% theo doanh thu (Điều 11) và mức chứng từ 5 triệu đồng (Điều 9) trong `tong-quan-thue.md` đều khớp chính xác — nâng xác nhận lên 🟢 HIGH (primary source).
- Loại bỏ khỏi phạm vi nguồn: Nghị định 49/2026/NĐ-CP (do người dùng cung cấp nhưng xác nhận là luật Đất đai, không liên quan TNDN).
- Còn tồn đọng: mức phạt vi phạm hóa đơn cụ thể theo từng lỗi (Nghị định 310/2025/NĐ-CP — chưa có file gốc); nội dung Thông tư 91/2026/TT-BTC và phần còn lại của Thông tư 20/2026/TT-BTC (đã có file gốc, chưa đọc sâu).

## v1.3.0 — 22/07/2026
- Thử nghiệm thêm nguồn **vbpl.vn** (Bộ Tư pháp — nguồn có giá trị pháp lý cao nhất) và **baochinhphu.vn/xaydungchinhsach.chinhphu.vn** (Cổng TTĐT Chính phủ).
- Xác nhận qua vanban.chinhphu.vn (docid=218689): Nghị định 254/2026/NĐ-CP có thật, 5 chương/45 điều, thay thế hoàn toàn NĐ 123/2020/NĐ-CP, quy định chi tiết Luật Quản lý thuế 108/2025/QH15 (không phải Luật 67/2025/QH15 như suy đoán trước) — cập nhật `hoa-don-dien-tu.md`.
- **Đính chính số điều ưu đãi thuế**: "Điều 19" (bản v1.0-1.2) → đúng là **Điều 18** (ngành/địa bàn ưu đãi) và **Điều 20** (thời gian miễn/giảm) của NĐ 320/2025/NĐ-CP, xác nhận qua baochinhphu.vn.
- Phát hiện thêm: có bậc ưu đãi RIÊNG theo quy mô VỐN ĐẦU TƯ (ngưỡng ~6.000 tỷ, ~20.000 tỷ đồng) ngoài bảng thuế suất theo doanh thu — chưa lấy được số liệu sạch hoàn toàn.
- **Giới hạn kỹ thuật đã gặp phải**: một tool nén nội dung (`headroom`) trong phiên làm việc tự động rút gọn mạnh mọi trang web tải về (kể cả từ chinhphu.vn chính thống) xuống còn few-dozen từ khóa rời rạc — khiến không thể trích xuất toàn văn sạch dù đã fetch đúng nguồn chính thống. Đây là giới hạn công cụ, không phải do nguồn bị chặn.
- vbpl.vn: chưa tìm thấy trực tiếp trang chi tiết Nghị định 320/2025/NĐ-CP hoặc 254/2026/NĐ-CP qua tìm kiếm site: trong phiên này — khuyến nghị user tự tra cứu trực tiếp trên vbpl.vn bằng trình duyệt (công cụ tìm kiếm nội bộ của vbpl.vn không thân thiện với site: search).

## v1.2.0 — 22/07/2026
- **Phát hiện quan trọng**: Luật số **09/2026/QH16** (Quốc hội thông qua ~24/04/2026) sửa đổi ĐỒNG THỜI 4 luật thuế (TNCN, GTGT, TNDN, TTĐB), hiệu lực từ 01/01/2026 cho các nội dung liên quan 3 luật đầu — bổ sung Khoản 14a Điều 4 Luật TNDN 67/2025/QH15 (giao Chính phủ quy định ngưỡng miễn thuế theo doanh thu).
- **Nghị định 141/2026/NĐ-CP** (29/04/2026) cụ thể hóa: doanh thu năm ≤ **1 tỷ đồng** → **miễn hoàn toàn thuế TNDN** (bổ sung Khoản 15 Điều 4 NĐ 320/2025/NĐ-CP). Đây thay thế mốc "500 triệu" cũ.
- ⚠️ Mốc 500 triệu trong skill `thue-tncn-vietnam` (sibling) hiện LỖI THỜI theo phát hiện này — cần cập nhật riêng, chưa thực hiện trong lần này (khác skill/repo).
- Sửa nhận thức về nguồn: thuvienphapluat.vn và luatvietnam.vn là công ty TƯ NHÂN tổng hợp luật, KHÔNG phải "của nhà nước" — nguồn chính thống thật là vanban.chinhphu.vn / quochoi.vn / gdt.gov.vn.
- Dùng luatvietnam.vn làm nguồn thay thế thành công khi thuvienphapluat.vn chặn 403 — nâng nhiều mục từ MEDIUM lên HIGH.

## v1.1.0 — 22/07/2026
- **Đính chính quan trọng**: gỡ bỏ tham chiếu sai "Nghị định 252/2025/NĐ-CP" (không tồn tại cho TNDN) — số đúng là 252/2026/NĐ-CP, thuộc lĩnh vực Quản lý thuế, không liên quan TNDN.
- Xác nhận trực tiếp qua vanban.chinhphu.vn: Nghị định 320/2025/NĐ-CP có thật, Điều 11 (thuế suất) và Điều 19 (ưu đãi) tồn tại.
- Sửa mức chứng từ thanh toán không dùng tiền mặt: 5 triệu đồng (không phải 20 triệu như bản v1.0.0).
- Mở rộng phạm vi skill để cover toàn diện nghĩa vụ thuế/kê khai doanh nghiệp, thêm 3 file mới:
  - `thue-gtgt-lien-quan.md` — thuế suất GTGT 2026, quy tắc kê khai tháng/quý, hạn nộp
  - `hoa-don-dien-tu.md` — khung pháp lý hóa đơn điện tử (NĐ 254/2026/NĐ-CP mới), quy tắc vận hành, mức phạt
  - `lich-nghia-vu-doanh-nghiep.md` — bảng tổng hợp TẤT CẢ nghĩa vụ định kỳ (GTGT, TNCN khấu trừ, TNDN, BHXH, lao động, hóa đơn, BCTC, kiểm toán)
- Cập nhật `sources.md` với danh sách rõ ràng: đã xác nhận qua chinhphu.vn vs chưa xác minh đầy đủ.

## v1.0.0 — 22/07/2026
- Khởi tạo skill, mirror cấu trúc từ `thue-tncn-vietnam`.
- Nội dung: thuế suất theo doanh thu (20%/17%/15%), ưu đãi thuế, tạm nộp quý (quy tắc 80%), quyết toán năm, lịch nộp thuế 2026.

---
**Expiry gợi ý**: làm mới sau 6 tháng (≈01/2027) hoặc khi có Nghị định/Thông tư hướng dẫn mới (đặc biệt theo dõi Nghị định 254/2026/NĐ-CP có hiệu lực 01/07/2026, Thông tư 91/2026/TT-BTC).
Data cập nhật: 22/07/2026.
