# Bài tập cá nhân Buổi 2 – HTML5 & CSS3 (Phát triển ứng dụng WEB/TMĐT)

- **Họ tên:** Phạm Văn Thắng
- **MSSV:** 31241027009
- **Giảng viên:** TS Nguyễn Mạnh Tuấn
- **Ngày thực hiện:** 03/11/2026

## 1. Giới thiệu bài tập

Tiếp tục phát triển website "Ưu đãi hôm nay – Cửa hàng mẫu" từ Buổi 1 (cùng repository). Buổi 2 thực hành HTML5 ngữ nghĩa, CSS selector, Box Model, Flexbox, CSS Grid, hover/focus và kiểm tra lỗi giao diện.

## 2. Website tham khảo và khu vực đã cải tiến

- Website tham khảo ở Buổi 1: Tiki (https://tiki.vn); dữ liệu sản phẩm là dữ liệu mẫu tự đặt.
- **Khu vực cải tiến:** danh sách 4 sản phẩm và thẻ sản phẩm; thực hành Flexbox ở header/menu và nhóm nút trong thẻ.

## 3. Kỹ thuật HTML5/CSS3 đã thực hành

| Kỹ thuật | Vị trí |
|---|---|
| HTML5 ngữ nghĩa | `header`, `nav`, `main`, `section`, `article`, `footer`, `ul/li`, `del` |
| CSS ngoài, liên kết | `css/style.css` liên kết trong `<head>` |
| Selector | element (`body`, `img`), class (`.product-card`), descendant (`.site-header .container`) |
| Box Model | `margin`, `padding`, `border`, `border-radius`, `box-sizing: border-box` |
| Flexbox | `.site-header .container`, `.site-nav ul`, `.product-card__actions` |
| CSS Grid | `.product-grid` (2 cột, 4 cột từ 960 px) |
| Hover/focus | `:hover`, `:focus-visible`, `transition` |

## 4. Hướng dẫn chạy website

Mở `index.html` bằng trình duyệt (không cần cài đặt). Giữ nguyên cấu trúc:

```
├── index.html
├── css/style.css
├── images/ (4 ảnh JPEG 800x800)
├── screenshots/ (ảnh minh họa, trước/sau)
├── README.md
└── AI_USAGE_LOG.md
```

## 5. Những thay đổi đã thực hiện

- Menu chuyển sang danh sách `ul/li`, thêm "Trang chủ", `aria-current`.
- Thêm nhóm nút `.product-card__actions` (Mua ngay + Yêu thích, mới chỉ là giao diện) bằng Flexbox.
- Gom khối CSS bị lặp cuối tệp vào đúng mục; thêm chú thích cho từng nhóm thuộc tính.
- Thêm hover, `transition`, `:focus-visible` cho menu và nút.
- Sửa lỗi (Bước 8): viền focus kép; lưới 3/5 cột làm lệch hàng với 4 sản phẩm; ảnh tai nghe bị cắt/lộ dải; ảnh có đuôi `.jpg` nhưng là PNG/WEBP.

## 6. Báo cáo kiểm thử

| Nội dung kiểm tra | Kết quả | Ghi chú |
|---|---|---|
| Trang HTML mở được | Đạt | Không có thẻ chưa đóng |
| CSS được áp dụng | Đạt | `css/style.css` trả về 200 |
| Hình ảnh hiển thị đúng | Đạt | 4 ảnh 800×800, tỷ lệ 1:1 |
| Liên kết hoạt động | Đạt | Logo/Trang chủ → `index.html`; các liên kết còn lại là `#` (chờ các buổi sau) |
| Bố cục không bị tràn nghiêm trọng | Đạt | Không cuộn ngang ở 1366, 768, 390 px |
| Hover/focus hoạt động | Đạt | Nút đổi `#d0261b` → `#b01e14`; viền focus 3 px |
| Đã tự sửa ít nhất một vấn đề | Đạt | 4 lỗi, xem mục 5 |

## 7. Công cụ AI và cách kiểm tra

Dùng Claude (Anthropic) cho 9 prompt của đề; chi tiết trong `AI_USAGE_LOG.md`. Mọi đề xuất đều được chạy thử trên trình duyệt ở 3 độ rộng và kiểm tra bằng bàn phím trước khi đưa vào bài.

## 8. Đường dẫn

- Repository: https://github.com/thangpham2202/ecommerce-ui-improvement.git 
- Website triển khai (nếu có): https://thangpham2202.github.io/ecommerce-ui-improvement/ 
