# Thực hành: Chuyển đổi CSS có sẵn sang SASS theo chuẩn

Bài thực hành chuyển một file CSS truyền thống sang cấu trúc SASS/SCSS dễ bảo trì hơn bằng **variables, mixins, nesting và partials**.

## Cấu trúc thư mục

```text
chuyen-css-sang-sass/
├── css-original/
│   └── styles.css
├── css/
│   └── main.css
├── scss/
│   ├── abstracts/
│   │   ├── _variables.scss
│   │   └── _mixins.scss
│   ├── base/
│   │   └── _global.scss
│   ├── layout/
│   │   └── _container.scss
│   ├── components/
│   │   ├── _buttons.scss
│   │   └── _cards.scss
│   └── main.scss
├── index.html
├── package.json
└── README.md
```

## Nội dung đã thực hiện

- Tách màu sắc, kích thước và shadow thành biến trong `abstracts/_variables.scss`.
- Tạo mixin cho button, box-shadow và transition trong `abstracts/_mixins.scss`.
- Tách style toàn cục vào `base/_global.scss`.
- Tách layout `.container` vào `layout/_container.scss`.
- Tách button và card vào thư mục `components`.
- Sử dụng nesting với `&:hover`, `&:active`, `&__title`, `&__text`.
- Gom toàn bộ module vào `scss/main.scss`.
- Biên dịch SCSS thành `css/main.css`.

> Bài sử dụng cú pháp `@use` của Dart Sass thay cho `@import` cũ vì `@use` là cách tổ chức module hiện đại và tránh làm biến/mixin bị đưa vào global scope.

## Cài đặt

Yêu cầu máy có Node.js và npm.

```bash
node -v
npm -v
npm install
```

## Biên dịch SCSS sang CSS

```bash
npm run build
```

Lệnh tương đương:

```bash
npx sass scss/main.scss css/main.css
```

## Chế độ theo dõi tự động

```bash
npm run watch
```

Lệnh tương đương:

```bash
npx sass --watch scss/main.scss:css/main.css
```

Sau đó mở `index.html` bằng trình duyệt để xem kết quả.

## Kết quả

CSS ban đầu đã được chuyển sang cấu trúc SASS rõ ràng, có thể tái sử dụng và dễ mở rộng hơn nhờ variables, mixins, nesting và partials.
