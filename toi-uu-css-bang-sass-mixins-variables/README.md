# Thực hành: Tạo mixins & biến để tối ưu CSS

## Mục tiêu

- Sử dụng SASS variables để quản lý màu sắc, font-size, padding, border-radius và box-shadow.
- Tạo mixins để giảm lặp code cho button và card.
- Tách mã nguồn thành các partial SCSS dễ bảo trì.
- Biên dịch SCSS sang CSS bằng SASS CLI.

## Cấu trúc thư mục

```text
toi-uu-css-bang-sass-mixins-variables/
├── css-original/
│   └── styles.css
├── css/
│   └── main.css
├── scss/
│   ├── abstracts/
│   │   ├── _variables.scss
│   │   └── _mixins.scss
│   ├── base/
│   │   └── _typography.scss
│   ├── components/
│   │   ├── _buttons.scss
│   │   └── _cards.scss
│   └── main.scss
├── index.html
├── package.json
└── README.md
```

## Nội dung đã thực hiện

### Variables

Các giá trị dùng nhiều lần được đưa vào `scss/abstracts/_variables.scss`, ví dụ:

- `$primary-color`
- `$text-color`
- `$font-large`
- `$font-medium`
- `$padding-standard`
- `$box-shadow-default`

### Mixins

`scss/abstracts/_mixins.scss` chứa:

- `button-style($bg-color)` dùng lại style cho button.
- `box-style` dùng lại style cho card/box.

### Partials

- `base/_typography.scss`: style cho `body`, `h1`, `h2`.
- `components/_buttons.scss`: áp dụng `button-style`.
- `components/_cards.scss`: áp dụng `box-style`.

Bài sử dụng `@use` theo SASS module system hiện đại thay cho `@import`.

## Cài đặt và chạy

```bash
npm install
```

Biên dịch SCSS sang CSS:

```bash
npm run build
```

Theo dõi và tự động biên dịch khi chỉnh SCSS:

```bash
npm run watch
```

Sau đó mở `index.html` bằng trình duyệt để xem kết quả.

## Kết quả

CSS sau khi tối ưu dễ quản lý và tái sử dụng hơn. Khi cần đổi màu, kích thước hoặc khoảng cách, chỉ cần chỉnh biến hoặc mixin tương ứng thay vì sửa nhiều vị trí trong CSS.
