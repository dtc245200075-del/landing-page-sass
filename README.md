# [Bài Tập] Tái Cấu Trúc Mã CSS Cho Landing Page Bằng SASS

Dự án thực hành chuyên sâu môn Frontend Web Development tại [CodeGym](https://codegym.vn).

---

## 1. Mục tiêu bài tập
Tái cấu trúc toàn bộ mã nguồn CSS của Landing Page thiết kế sẵn (bao gồm 4 phần đã học trong bài Template) sang **SASS/SCSS** nhằm nâng cao tính mô-đun, dễ bảo trì và mở rộng:
1. **Dựng Navigation & Header của Landing Page**
2. **Dựng phần Sản phẩm nổi bật (Featured Products)**
3. **Dựng phần Số liệu thống kê (Statistics & Counters)**
4. **Dựng phần Footer (Chân trang đa cột)**

---

## 2. Các tính năng SASS đã áp dụng

### A. Variables (Biến lưu trữ tập trung)
- Bảng màu giao diện: `$primary-color`, `$secondary-color`, `$accent-color`, `$dark-bg`, `$light-bg`, `$text-dark`, `$text-muted`, `$white`,...
- Huy hiệu sản phẩm: `$badge-hot`, `$badge-new`, `$badge-discount`.
- Bố cục & Kích thước: `$container-max-width: 1200px`, `$section-padding`, bo góc `$radius-md`, `$radius-lg`, đổ bóng `$shadow-md`, `$shadow-xl`.

### B. Nesting (Cấu trúc lồng nhau)
- Toàn bộ các selector CSS được phân cấp theo đúng thứ tự phần tử cha - con trong cây DOM HTML.
- Sử dụng toán tử tham chiếu `&` cho các class con (`&__title`, `&__desc`), trạng thái hover (`&:hover`), active (`&.active`) và các biến thể giao diện (`&--primary`, `&--outline`, `&--hot`).

### C. Mixins (Tái sử dụng khối mã)
- `@mixin flex-center`: Căn giữa phần tử theo 2 chiều.
- `@mixin flex-between`: Căn dãn đều 2 đầu cho thanh điều hướng và chân thẻ.
- `@mixin button-variant($bg, $color, $hover-bg)`: Tạo các kiểu dáng nút bấm với hiệu ứng chuyển động khi hover và click.
- `@mixin respond-to($breakpoint)`: Xử lý linh hoạt thiết kế đáp ứng (Responsive) cho `mobile` (<= 576px), `tablet` (<= 768px), `desktop` (<= 1024px).

### D. Partials & Modular Architecture
Dự án được chia tách thành các tệp SCSS mô-đun chuyên biệt:
```
landing-page-sass/
├── scss/
│   ├── _variables.scss      # Biến màu sắc, kích thước, breakpoint
│   ├── _mixins.scss         # Các hàm mixin flexbox, responsive, button
│   ├── _base.scss           # Reset, container, button, section-header
│   ├── _navigation.scss     # Thanh điều hướng (Navbar & Mobile Menu)
│   ├── _header.scss         # Header & Hero Banner nổi bật
│   ├── _products.scss       # Danh sách thẻ sản phẩm nổi bật
│   ├── _statistics.scss     # Khối 4 số liệu thống kê thành tựu
│   ├── _footer.scss         # Chân trang 4 cột & Form đăng ký nhận tin
│   └── style.scss           # File SCSS tổng hợp import các partials
├── css/
│   └── style.css            # File CSS đã biên dịch từ SASS
├── images/                  # Thư mục hình ảnh chất lượng cao
├── index.html               # Trang Landing Page hoàn chỉnh
├── style.scss               # File SASS tại thư mục gốc
├── style.css                # File CSS tại thư mục gốc
└── README.md                # Tài liệu dự án
```

---

## 3. Cách xem và kiểm tra
1. Mở file [index.html](file:///c:/Users/admin/Downloads/responsive-grid-master/landing-page-sass/index.html) bằng trình duyệt web.
2. Để biên dịch SASS tự động khi chỉnh sửa, bật tính năng **Watch Sass** của extension **Live Sass Compiler** trong VS Code.
