# Nhật ký sử dụng AI

- **Họ tên / MSSV:** [ĐIỀN]
- **Ngày:** 20/10/2026

> Các chỗ có dấu `[ĐIỀN]` hoặc ô `[ ]` là phần chỉ riêng tôi biết. Tôi chỉ ghi những gì tôi thực sự đã làm.

## 1. Tên công cụ AI

**Claude** (do Anthropic phát triển), dùng qua giao diện chat web/ứng dụng. Phiên bản: Claude Sonnet 5.5.

## 2. Mục đích sử dụng

- Phân tích 5 khu vực của website Tiki.
- Đề xuất phương án thiết kế thẻ sản phẩm.
- Tạo mã HTML5/CSS3 ban đầu.
- Sửa lỗi khi trang chạy bị mất định dạng và ảnh.
- Soạn nháp `README.md` và `AI_USAGE_LOG.md`.

## 3. Các prompt đã dùng

| # | Nội dung prompt (tóm tắt) | Kết quả AI trả về |
|---|---|---|
| 1 | Đóng vai chuyên gia phân tích nghiệp vụ và UX, lập bảng phân tích 5 khu vực của Tiki (mục đích, thành phần giao diện, điểm thuận tiện, một vấn đề, một đề xuất). Yêu cầu không khẳng định tính năng chưa kiểm chứng, phân biệt quan sát và đề xuất của AI. | Bảng phân tích có nhãn `[QS]`, `[CKC]`, `[AI]`. AI nói rõ chỉ đọc được phần văn bản trang chủ, các khu vực còn lại là giả định cần kiểm chứng. |
| 2 | Đề xuất bố cục, thành phần HTML, cách tổ chức CSS và cách hiển thị desktop/mobile cho thẻ sản phẩm hiển thị rõ giá gốc, giá giảm, tỷ lệ giảm, dành cho khách hàng Việt Nam. | Phương án khối giá hai tầng, cấu trúc `ul/li/article`, CSS chia 5 phần, bảng số cột theo màn hình, kèm một file HTML demo. |
| 3 | Tạo trang HTML5/CSS3 hoàn chỉnh: có tiêu đề, khu vực sản phẩm, tối thiểu 4 sản phẩm (ảnh, tên, giá, nút mua), responsive, HTML rõ ràng, CSS tách file riêng. | Bộ `index.html`, `style.css` và 6 ảnh SVG (6 sản phẩm). |
| 4 | Gửi ảnh chụp màn hình trang chạy trên Edge (không có định dạng, ảnh vỡ), yêu cầu sửa để HTML liên kết đúng với CSS. | AI giải thích thư mục của tôi chỉ có `index.html`, thiếu `style.css` và `images/`. AI nhúng ảnh vào HTML và đóng gói lại hai file. |
| 5 | Yêu cầu viết `README.md` và `AI_USAGE_LOG.md`. | Hai file này (bản nháp để em chỉnh lại). |

## 4. Cách em sử dụng kết quả của AI

- Bảng phân tích (prompt 1) dùng làm khung khảo sát. Tôi hiểu rằng các mục `[CKC]` phải tự kiểm chứng trên Tiki trước khi dùng làm kết luận.
- Phương án (prompt 2) được chọn làm hướng thiết kế.
- Mã (prompt 3, 4) được đặt vào thư mục `ecommerce-ui-improvement`, chạy thử trên Microsoft Edge và dùng làm sản phẩm nộp.
- Em không coi nội dung AI viết là đúng tuyệt đối. Em đã chạy thử và phát hiện lỗi ở prompt 4.

## 5. Phần em đã tự sửa

Đã xác nhận được qua quá trình làm bài:
- Đặt tên và tổ chức thư mục dự án `ecommerce-ui-improvement` trong `Documents`.
- Chạy thử `index.html` trên Edge, phát hiện trang mất định dạng và ảnh vỡ, rồi báo lại để sửa.

Em tự điền thêm:
- **Nội dung, ảnh, chữ đã đổi:**
  - **Đường dẫn CSS:** Sửa từ `href="style.css"` thành `href="css/style.css"` trong file `index.html`.
  - **Đường dẫn ảnh:** Chuyển toàn bộ ảnh từ định dạng `.svg` sang định dạng `.jpg` thực tế (`images/tai-nghe.jpg`, `images/noi-chien.jpg`, `images/ao-thun.jpg`, `images/sua-rua-mat.jpg`).
  - **Tên, giá, màu sắc:** Giữ nguyên theo mẫu, không thay đổi.

- **Đoạn CSS/HTML đã thêm, bớt hoặc sửa:**
  - **HTML:** Cập nhật thuộc tính `href` của thẻ `<link>` và thuộc tính `src` của 4 thẻ `<img>` hiển thị sản phẩm.
  - **CSS:** Thêm `aspect-ratio: 1 / 1;` cho lớp `.product-card__media` để cố định khung ảnh vuông. Thêm `object-fit: cover;` và `object-position: center;` cho `.product-card__media img` trong file `css/style.css` để hình ảnh căn giữa, lấp đầy khung và xóa bỏ khoảng trắng thừa.

- **Thiết bị hoặc trình duyệt đã kiểm thử:**
  - Trình duyệt máy tính: Google Chrome / Microsoft Edge.
  - Kiểm thử giao diện di động (Responsive): Sử dụng công cụ Chrome DevTools (phím `F12`).
  - Thiết bị di động thực tế: Không có.

## 6. Phần em tự giải thích được

**Hãy đánh dấu `[x]` chỉ những mục bạn thực sự giải thích được khi giảng viên hỏi.** 

- **Vì sao trang bị mất định dạng ban đầu:** `index.html` dùng `<link rel="stylesheet" href="style.css">`, đường dẫn tương đối nên `style.css` phải nằm cùng thư mục. Thiếu file thì trình duyệt không tìm thấy CSS.
- **Vì sao dùng `<del>` cho giá gốc:** thẻ này có nghĩa "nội dung đã bị thay thế", và trình duyệt gạch ngang mặc định.
- **Vì sao có `.sr-only`:** để người dùng trình đọc màn hình nghe được "Giá hiện tại", "Giá gốc", "Giảm", dù chữ này không hiện trên màn hình.
- **CSS Grid đổi số cột thế nào:** `.product-grid` dùng `repeat(N, minmax(0, 1fr))`, và `@media (min-width: …)` tăng N từ 2 lên 3, 4, 5.
- **Thế nào là mobile-first:** viết CSS cho điện thoại trước, sau đó dùng `min-width` để bổ sung cho màn hình lớn hơn.
- **Vì sao dùng biến CSS `:root`:** đổi một giá trị (ví dụ `--c-sale`) là cập nhật toàn bộ trang.
- **Vì sao ảnh được nhúng thẳng vào HTML:** để chỉ cần hai file `index.html` và `style.css` là chạy đủ, không phụ thuộc thư mục `images/`.

## Cam kết

Em đã đọc, chạy thử và hiểu các phần đã đánh dấu ở mục 6. Các phần AI hỗ trợ đã được ghi rõ trong nhật ký này. Phần phân tích Tiki ngoài trang chủ chưa được kiểm chứng và tôi không trình bày như sự thật đã xác minh.