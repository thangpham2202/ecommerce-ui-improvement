# Nhật ký sử dụng AI

- **Họ tên**: Phạm Văn Thắng
- **MSSV:** 31241027009 
- **Ngày:** 3/11/2026

# Báo cáo sử dụng AI

## 1. Công cụ và mục đích
- **Công cụ:** Claude (Anthropic).
- **Mục đích:** Phân tích mã Buổi 1, giải thích khái niệm HTML5/CSS3, đề xuất đoạn CSS, hỗ trợ tìm nguyên nhân lỗi và soạn nháp README. AI không thay thế việc em chạy thử và kiểm tra: mọi đề xuất đều được kiểm tra trên trình duyệt trước khi đưa vào bài.

## 2. Các prompt tiêu biểu và kết quả

**Bảng 1: Tổng hợp 9 prompt đã dùng**

| # | Prompt (mục) | Kết quả AI | Phần em kiểm tra / tự điều chỉnh |
|---|---|---|---|
| 1 | Phân tích mã hiện tại (1.3) | Liệt kê thành phần, 4-5 vấn đề, thứ tự cải tiến | Tự xác nhận từng vấn đề ở 3 độ rộng, kiểm tra định dạng ảnh thật |
| 2 | Kiểm tra HTML5 (2.2) | Menu `ul`/`li`, logo trỏ `index.html`, nhóm nút | Giữ nguyên các thẻ đã đúng, không thêm `div` thừa; kiểm tra thẻ đóng/mở |
| 3 | CSS cơ bản (3.2) | Giải thích nhóm thuộc tính, cách kiểm tra Network | Thử đổi đường dẫn sai để thấy lỗi thật |
| 4 | Selector và Box Model (4.2) | Giải thích `margin`/`padding`/`border`/`border-box` | Đối chiếu số đo thật: thẻ 285px, nội dung 259px |
| 5 | Flexbox (5.2) | CSS cho header, menu, nhóm nút | Thử 4 giá trị `justify-content`, 3 giá trị `gap`, bỏ `display: flex` |
| 6 | CSS Grid (6.2) | Lưới repeat, `gap`, `object-fit` | Thử 2/3/4 cột và bỏ `display: grid` |
| 7 | Hover/focus (7.2) | `transition`, `:hover`, `:focus-visible` | Duyệt bằng phím Tab; tính độ tương phản màu |
| 8 | Tìm lỗi (8.2) | Nguyên nhân + cách sửa ít thay đổi nhất | Tự sửa 4 lỗi, phân biệt nguyên nhân đã xác định và giả thuyết |
| 9 | Kiểm tra README (mục GitHub) | Cấu trúc README 7 mục | Điền thông tin thật, để trống phần chưa có (link repository) |

## 3. Phần em tự điều chỉnh sau khi dùng AI
- Không dùng `:focus-within` cho viền cả thẻ vì phát hiện 2 viền chồng nhau khi Tab; đổi sang `:has(.product-card__link:focus-visible)`.
- Bỏ các mốc 3 cột và 5 cột vì danh sách chỉ có 4 sản phẩm.
- Đổi ảnh về JPEG thật 800×800px; ảnh tai nghe đệm nền thay vì cắt để không mất hình.
- Gom khối CSS bị viết lặp cuối tệp vào đúng mục 5. Thẻ sản phẩm.
- Chỉ đưa vào bài phần CSS cần thiết, không dùng framework (Bootstrap/Tailwind) theo đúng yêu cầu prompt.

## 4. Phần em tự giải thích được
Em giải thích được: 
- Vì sao CSS phải liên kết bằng đường dẫn đúng.
- `margin` khác `padding`.
- `box-sizing: border-box` làm gì.
- `display: flex` đặt ở cha.
- `justify-content` (trục chính) khác `align-items` (trục phụ).
- `grid-template-columns: repeat(N, minmax(0, 1fr))`.
- `object-fit: cover`.
- `hover` khác `focus`.
- Vì sao cần thuộc tính `alt` cho ảnh.
- Lý do của từng lần sửa ở Bước 8.
