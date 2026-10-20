# Cải tiến thẻ hiển thị sản phẩm cho website thương mại điện tử

- **Họ tên / MSSV:** Phạm Văn Thắng
- **MSSV:** 31241027009 
- **Ngày thực hiện:** 19/10/2026

## 1. Website khảo sát

**Tiki – https://tiki.vn**, sàn thương mại điện tử dành cho khách hàng Việt Nam.

Khu vực khảo sát: Trang chủ, Danh mục sản phẩm, Chi tiết sản phẩm, Tìm kiếm, Giỏ hàng.

**Phạm vi kiểm chứng (nói rõ để không khẳng định quá mức):** trong lần khảo sát với AI, chỉ phần văn bản mô tả của trang chủ Tiki được đọc trực tiếp. Phần văn bản này nhắc đến giá sốc mỗi ngày, cửa hàng Official, Freeship+, TikiNOW, TikiCARD và các tiện ích như thẻ cào, hóa đơn, bảo hiểm. Các nhận xét về danh mục, chi tiết sản phẩm, tìm kiếm và giỏ hàng là **giả định chung của thương mại điện tử, chưa kiểm chứng trên Tiki**. Bảng phân tích gốc có gắn nhãn `[QS]` (đã quan sát), `[CKC]` (chưa kiểm chứng) và `[AI]` (đề xuất của AI) để phân biệt.
### Bảng khảo sát 5 khu vực trên website Tiki (tiki.vn)

| Khu vực | Chức năng đang cung cấp | Điểm hợp lý trong thiết kế | Điểm có thể cải thiện | Đề xuất cải tiến & Lý do |
| :--- | :--- | :--- | :--- | :--- |
| **1. Trang chủ** | Hiển thị banner khuyến mãi, danh mục tiện ích (TikiNOW, Astra, Thẻ cào), khối "Giá tốt mỗi ngày" `[QS]`. | Khối sản phẩm giá tốt đặt ở vị trí nổi bật, thu hút sự chú ý ngay khi truy cập `[QS]`. | Banner quảng cáo dày đặc gây xao nhãng và làm rối mắt người dùng `[AI]`. | Gộp các banner theo nhóm chủ đề để giao diện gọn gàng và tăng tốc độ tải trang `[AI]`. |
| **2. Danh mục sản phẩm** | Phân loại sản phẩm theo ngành hàng, tích hợp bộ lọc (thương hiệu, giá, đánh giá sao) `[CKC]`. | Bộ lọc xếp dọc bên trái giúp người dùng dễ chọn lọc thông tin theo nhu cầu `[CKC]`. | Chiều cao các thẻ sản phẩm chưa đồng đều khi tên sản phẩm quá dài `[AI]`. | Giới hạn tên sản phẩm trong 2 dòng (`-webkit-line-clamp: 2`) để lưới sản phẩm cân đối `[AI]`. |
| **3. Chi tiết sản phẩm** | Trình bày gallery ảnh, giá bán, giá gốc, mô tả kỹ thuật, thông tin giao hàng và nút chọn mua `[CKC]`. | Thông tin ưu đãi (Freeship, Hoàn tiền) đặt ngay dưới giá giúp kích thích mua hàng `[CKC]`. | Khối so sánh giá gốc và giá giảm chưa nổi bật khi xem trên màn hình điện thoại `[AI]`. | Thiết kế lại khối giá hai tầng với màu đỏ tương phản cho giá hiện tại để dễ nhận biết `[AI]`. |
| **4. Tìm kiếm** | Thanh tìm kiếm cố định trên header, gợi ý từ khóa hot và lưu lịch sử tìm kiếm `[CKC]`. | Ô tìm kiếm to, nằm chính giữa header giúp người dùng dễ dàng thao tác ở mọi trang `[CKC]`. | Kết quả gợi ý nhanh chưa hiển thị thông tin sản phẩm đang có giảm giá hay không `[AI]`. | Bổ sung nhãn giảm giá (%) nhỏ cạnh tên sản phẩm gợi ý để tăng tỷ lệ nhấp chuột `[AI]`. |
| **5. Giỏ hàng** | Liệt kê sản phẩm đã chọn, điều chỉnh số lượng, áp mã giảm giá và tính tổng tiền đơn hàng `[CKC]`. | Bảng tóm tắt thể hiện rõ phí vận chuyển và số tiền người mua tiết kiệm được `[CKC]`. | Nút "Thanh toán" ở màn hình điện thoại bị khuất nếu danh sách sản phẩm dài `[AI]`. | Cố định (sticky) thanh tổng tiền và nút "Thanh toán" ở đáy màn hình di động để dễ bấm `[AI]`. |

*Ghi chú ký hiệu:* `[QS]`: Đã quan sát thực tế; `[CKC]`: Chưa kiểm chứng trực tiếp trên Tiki; `[AI]`: Đề xuất phân tích từ AI.

## 2. Khu vực chọn cải tiến và lý do

**Khu vực:** thẻ hiển thị sản phẩm (product card).

**Lý do:** thẻ sản phẩm xuất hiện ở trang chủ, danh mục và kết quả tìm kiếm, nên là nơi người mua so sánh giá nhiều nhất. Mục tiêu cải tiến là làm rõ **giá gốc, giá giảm và tỷ lệ giảm** để người mua hiểu ngay mình tiết kiệm được bao nhiêu.

## 3. Công nghệ sử dụng

| Công nghệ | Dùng để |
|---|---|
| HTML5 | Cấu trúc ngữ nghĩa: `header`, `main`, `section`, `article`, `footer`, `ul/li`, `del`, `button`. |
| CSS3 | Toàn bộ giao diện trong file riêng `style.css`. |
| CSS Grid | Lưới thẻ sản phẩm, đổi số cột theo màn hình. |
| Flexbox | Xếp nội dung bên trong thẻ theo chiều dọc, căn hàng giá. |
| CSS Custom Properties | Khai báo màu, khoảng cách ở một chỗ (`--c-sale`, `--gap`, ...). |
| Media queries | Responsive mobile-first. |
| Google Fonts (Be Vietnam Pro) | Phông hỗ trợ tiếng Việt, có phông dự phòng nếu không có mạng. |
| Ảnh SVG | Ảnh minh họa, được nhúng trực tiếp vào HTML. |

Không dùng JavaScript hay framework.


## 4. Cải tiến đã thực hiện

| Vấn đề | Cải tiến |
|---|---|
| Giá gốc, giá giảm, % giảm dễ lẫn với nhau | Khối giá hai tầng: giá hiện tại chữ lớn, đậm, màu đỏ; bên dưới là giá gốc gạch ngang (`<del>`) kèm nhãn `-32%`. |
| Người dùng trình đọc màn hình không phân biệt được các mức giá | Thêm nhãn ẩn bằng `.sr-only`: "Giá hiện tại", "Giá gốc", "Giảm". |
| Sản phẩm không giảm giá vẫn dùng màu đỏ gây hiểu nhầm | Chỉ thẻ có `.has-discount` mới dùng màu đỏ cho giá. Thẻ không giảm giá hiện giá màu đen, không có giá gạch và nhãn %. |
| Tên dài làm các thẻ cao thấp khác nhau | Giới hạn 2 dòng (`-webkit-line-clamp`) và đặt `min-height`. |
| Ảnh tải chậm làm bố cục nhảy | `aspect-ratio: 1/1`, kèm `width` và `height` trên `<img>`. |
| Khó bấm trên điện thoại | Cả thẻ bấm được nhờ `::after` phủ kín; nút "Mua ngay" nằm trên lớp đó. |
| Hiển thị chưa phù hợp nhiều thiết bị | Lưới 2 cột (dưới 640px), 3 cột (từ 640px), 4 cột (từ 960px), 5 cột (từ 1200px). |
| Hiệu ứng rê chuột bị kẹt trên điện thoại | Chỉ bật hover trong `@media (hover: hover)`. |
| Thiếu hỗ trợ bàn phím | Viền focus rõ (`:focus-within`, `:focus-visible`) và tôn trọng `prefers-reduced-motion`. |

CSS tổ chức theo 6 phần có đánh số: Tokens, Base, Layout, Header/Footer, Thẻ sản phẩm (đặt tên theo BEM), Responsive.

## 5. Hạn chế

- Dữ liệu sản phẩm, giá và hình ảnh là dữ liệu mẫu tự đặt, không lấy từ Tiki.
- Nút "Mua ngay" chưa có chức năng (chưa dùng JavaScript).
- Tỷ lệ giảm đang viết sẵn trong HTML. Khi làm hệ thống thật, máy chủ nên tính theo công thức `(giá gốc − giá giảm) / giá gốc` rồi làm tròn.
- Chưa kiểm thử trên nhiều trình duyệt và thiết bị thật. Mới chạy thử trên Microsoft Edge (máy tính).

## 6. Tóm tắt sự hỗ trợ từ AI

Em dùng **Claude (Anthropic)** để: (1) lập bảng phân tích 5 khu vực của Tiki, (2) đề xuất bố cục, thành phần HTML, cách tổ chức CSS và responsive cho thẻ sản phẩm, (3) viết mã HTML/CSS ban đầu, (4) sửa lỗi liên kết file sau khi tôi chạy thử và báo lại. Chi tiết prompt, phần tôi tự sửa và phần tôi tự giải thích được nằm trong `AI_USAGE_LOG.md`.
