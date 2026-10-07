# Thực hành cài đặt SASS bằng npm & SASS CLI

Bài thực hành đáp ứng các yêu cầu:

- Kiểm tra Node.js và npm.
- Cài đặt SASS bằng npm.
- Kiểm tra phiên bản SASS.
- Biên dịch một file SCSS sang CSS.
- Chạy chế độ `--watch`.
- Biên dịch nhiều file SCSS theo thư mục đầu vào/đầu ra.
- Có đầy đủ mã nguồn SCSS, CSS đã biên dịch và trang HTML minh họa.

## 1. Kiểm tra Node.js và npm

```bash
node -v
npm -v
```

Nếu máy chưa có Node.js, tải từ trang chính thức: https://nodejs.org/

## 2. Cài đặt thư viện của bài

Mở Terminal tại thư mục `thuc-hanh-sass-cli` và chạy:

```bash
npm install
```

Kiểm tra SASS:

```bash
npx sass --version
```

Ngoài ra có thể cài SASS global:

```bash
npm install -g sass
sass --version
```

## 3. Biên dịch một file SCSS sang CSS

```bash
npm run sass
```

Lệnh tương đương:

```bash
sass scss/styles.scss css/styles.css
```

## 4. Chế độ watch

```bash
npm run watch
```

Lệnh tương đương:

```bash
sass --watch scss:css
```

Khi sửa file trong thư mục `scss/`, SASS sẽ tự động cập nhật CSS trong thư mục `css/`.

## 5. Biên dịch nhiều file SCSS

```bash
npm run build
```

Script này chạy:

```bash
sass --style=expanded --no-source-map scss:css
```

Hai file đầu vào chính là:

- `scss/styles.scss`
- `scss/pages.scss`

Các file bắt đầu bằng dấu gạch dưới như `_variables.scss` và `_mixins.scss` là partial nên không tạo ra CSS riêng.

## 6. Cấu trúc thư mục

```text
thuc-hanh-sass-cli/
├── css/
│   ├── pages.css
│   └── styles.css
├── scss/
│   ├── _mixins.scss
│   ├── _variables.scss
│   ├── pages.scss
│   └── styles.scss
├── .gitignore
├── index.html
├── package.json
└── README.md
```

## 7. Lỗi PowerShell chặn npm.ps1 trên Windows

Nếu PowerShell báo lỗi không cho chạy script, nên ưu tiên chính sách giới hạn cho tài khoản hiện tại thay vì đặt `Unrestricted` toàn hệ thống:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

Hoặc chỉ bỏ chặn tạm thời cho phiên PowerShell hiện tại:

```powershell
Set-ExecutionPolicy -Scope Process Bypass
```

Sau đó mở lại Terminal và chạy lại lệnh npm/SASS.

## 8. Xem kết quả

Mở file `index.html` bằng trình duyệt. Trang demo sử dụng CSS được tạo từ SCSS và minh họa biến, mixin, nesting và responsive.
