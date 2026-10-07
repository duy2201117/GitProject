# Tái cấu trúc CSS cho sẵn bằng SASS

Bài tập dựa trên mã HTML/CSS của [CodeGym responsive-grid](https://github.com/codegym-vn/responsive-grid).
File nguồn: `responsive_grid.htm`, blob `f844ce0a77430f510551022640e1200644dd8b40`.

## Kết quả

- Chuyển CSS trong thẻ style và toàn bộ inline style thành các lớp CSS.
- Dùng biến để quản lý màu sắc, kích thước, khoảng cách và độ trong suốt.
- Dùng mixins `span` và `panel` để tái sử dụng mã.
- Nesting cho các biến thể hàng/cột, phần lưới hướng dẫn và menu.
- Dùng `@for` sinh các lớp độ rộng cột và `@each` sinh chiều cao hàng.
- Tách partials thành `abstracts`, `base`, `layout`, `components`; tập hợp bằng `@use` trong `main.scss`.
- Giữ bố cục và nội dung nguồn: lưới 12 cột co giãn theo chiều rộng, header, menu, vùng bên phải, footer và lưới hướng dẫn.

## Các file chính

| Đường dẫn | Vai trò |
| --- | --- |
| `index.html` | HTML dùng các lớp CSS, liên kết CSS đã biên dịch |
| `original/responsive_grid.htm` | Bản gốc để đối chiếu |
| `scss/abstracts/_variables.scss` | Biến dùng chung |
| `scss/abstracts/_mixins.scss` | Mixins dùng chung |
| `scss/base/_global.scss` | Quy tắc chung |
| `scss/layout/_grid.scss` | Hàng, cột và vòng lặp |
| `scss/layout/_preview.scss` | Bố cục lớp phủ và lưới hướng dẫn |
| `scss/components/_panels.scss` | Header, footer, menu và aside |
| `scss/main.scss` | Điểm vào biên dịch |
| `css/main.css` | CSS đầu ra thực tế của Sass CLI |

## Chạy bài

Yêu cầu Node.js và npm. Mở terminal tại thư mục bài:

```bash
npm install
npm run build
npm run watch
```

Mở `index.html` trong trình duyệt. Thu/phóng cửa sổ để xem lưới co giãn.
Dừng watch bằng Ctrl+C. Có sẵn CSS đầu ra nên có thể mở HTML ngay mà không cần cài npm.

Muốn thay đổi màu hoặc kích thước, sửa `scss/abstracts/_variables.scss`, rồi biên dịch lại.
Không sửa trực tiếp `css/main.css` vì file này được tạo từ SCSS.


## Kiểm tra đã thực hiện

- `npm run build`: PASS, CSS được Sass CLI biên dịch thực tế.
- Watch: PASS, thay đổi biến màu làm CSS tự cập nhật; đã khôi phục màu gốc.
- So sánh bằng JSDOM: nội dung HTML và 24 thuộc tính CSS trên 35 phần tử body khớp bản gốc sau khi chuẩn hóa giá trị zero.
- Chưa kiểm tra ảnh render trên trình duyệt; có thể mở hai file HTML và đối chiếu khi thay đổi kích thước cửa sổ.
