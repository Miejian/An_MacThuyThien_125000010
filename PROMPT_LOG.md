# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Mạc Thủy Thiên Ân
- **MSSV:** 25AI111
- **Tên đề tài Website:** Cyber-Gamified Showcase Landing Page (Tựa game nhập vai chiến thuật Gen Z: *CYBER-CHRONO 2088: NEON PROTOCOL*)
- **Công cụ AI đã sử dụng:** Gemini 3.8 Flash (High) / Antigravity AI Pair-Programmer

---

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> **Prompt gửi AI (Khởi tạo hệ thống giao diện Game & Cyberpunk):**
>
> *"Bạn là một Senior Front-end Developer chuyên về thiết kế giao diện Game & Cyberpunk. Hãy giúp tôi tạo cấu trúc mã nguồn cho một trang Cyber-Gamified Showcase Landing Page giới thiệu một tựa game nhập vai chiến thuật Gen Z."*
>
> **Yêu cầu kỹ thuật chi tiết:**
> 1. **Semantic HTML5:** Sử dụng chính xác ngữ nghĩa các thẻ `<header>`, `<nav>`, `<main>`, `<section id="...">`, `<article class="character-card">`, và `<footer>`. Không dùng thẻ `<div>` bừa bãi.
> 2. **CSS Variables & Theme Dark Mode:** Khai báo trong `:root`:
>    - `--primary-neon: #06b6d4` (Xanh Neon)
>    - `--accent-pink: #f43f5e` (Hồng Neon)
>    - `--bg-dark: #0f172a` (Dark Mode)
>    - `--card-bg: #1e293b`
>    - `--text-main: #f8fafc`
>    - `--font-main: 'Orbitron', 'Inter', sans-serif`
> 3. **Thư viện hiệu ứng CDN:** Nhúng sẵn CDN cho **Animate.css (v4.1.1)**, **AOS.css (Animate On Scroll)** và phông chữ Google Font **Orbitron**.
> 4. **Layout:** Dùng CSS Grid cho danh sách nhân vật và Flexbox cho thanh Navigation/Header.
> 5. Hãy xuất cho tôi 2 file: `index.html` và `style.css` đầy đủ.

---

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML & CSS Variable

- **Prompt đã dùng:**
  > *"Trong file `index.html` vừa tạo, bạn đang dùng quá nhiều thẻ lồng nhau ở phần nội dung. Hãy tối ưu lại như sau:*
  > - *Thay các `<div>` bọc nội dung chính bằng thẻ `<main>`.*
  > - *Chia các khối như Giới thiệu Thế giới (Lore), Danh sách Nhân vật (Characters), Tính năng (Gameplay), Đăng ký sớm (Pre-register) thành các thẻ `<section>` riêng biệt có `id` và tiêu đề rõ ràng.*
  > - *Mỗi nhân vật chiến thuật bắt buộc nằm trong một thẻ `<article class="character-card">` riêng biệt, bên trong có `<figure>` chứa ảnh nhân vật, thẻ độ hiếm SSR, thanh chỉ số Speed/Atk/Def và `<footer>` nút chọn tướng.*
  > - *Cập nhật file `style.css` để áp dụng triệt để các biến `:root` đã khai báo (`--primary-neon`, `--accent-pink`, `--bg-dark`, `--card-bg`, `--text-main`, `--font-main`) vào background, màu chữ, viền phát sáng và các nút bấm neon."*

- **Kết quả AI tạo ra:**
  - File `index.html` đáp ứng chuẩn W3C Semantic HTML5:
    - `<header class="site-header">` ứng dụng Flexbox căn chỉnh logo game và navigation menu `<nav class="main-nav">`.
    - Thẻ `<main class="site-main">` chứa 5 phân khu độc lập:
      - `<section id="hero">`: Giới thiệu tựa game Cyber-Chrono 2088.
      - `<section id="lore">`: Bối cảnh thành phố Neo-Veridia và cuộc nổi dậy Netrunner.
      - `<section id="characters">`: Danh sách 4 tướng SSR (Kira, Vex, Titan-09, Nyx) dưới dạng `<article class="character-card">`.
      - `<section id="gameplay">`: Các tính năng cơ chế Hex-Grid và AI Assistant.
      - `<section id="pre-register">`: Form đăng ký nhận quà Closed Beta với `<fieldset>`, `<legend>` và `<label>` rõ ràng.
    - `<footer>` chứa thông tin bản quyền, điều hướng phụ và thông tin sinh viên Mạc Thủy Thiên Ân (25AI111).
  - File `style.css` quản lý toàn bộ hệ thống màu Neon Cyberpunk qua các biến `:root`. Layout nhân vật được dàn trang bằng CSS Grid 4 cột (`grid-template-columns: repeat(4, 1fr)`) tự động co giãn theo responsive.

- **Nhận xét & Tinh chỉnh của SV:**
  - *Nhận xét:* Giao diện mang đậm chất Cyberpunk, độ tương phản cao, phông chữ Orbitron tạo cảm giác tương lai và công nghệ cực mạnh.
  - *Tinh chỉnh thêm:* SV bổ sung thêm thanh chỉ số phần trăm kỹ năng của tướng (`.stat-bar` và `.stat-fill`) để tăng tính "Gamified" cho showcase.

---

### Lần 2: Tích hợp thư viện Animate.css & AOS

- **Prompt đã dùng:**
  > *"Bây giờ hãy bổ sung hiệu ứng chuyển động cho trang web:*
  > - *Áp dụng các class của Animate.css cho khu vực Hero section (tiêu đề xuất hiện hiệu ứng `animate__animated animate__fadeInDown`, nút CTA hiệu ứng `animate__animated animate__zoomIn`, ảnh minh họa game hiệu ứng `animate__animated animate__fadeInRight`).*
  > - *Thêm thuộc tính `data-aos="fade-up"` cho các thẻ `<section>` và các thẻ `<article class="character-card">` để khi cuộn trang nội dung xuất hiện mượt mà.*
  > - *Tự viết mã CSS hiệu ứng `:hover` và `:focus` mượt mà (`transition: 0.3s`) cho nút bấm neon (glow sáng rực rỡ) và thẻ card nhân vật (hover nhấc nhẹ lên `-8px`, đổ bóng neon xanh/hồng và phóng to nhẹ hình ảnh nhân vật)."*

- **Kết quả AI tạo ra:**
  - Hero Section có chuyển động xuất hiện mạnh mẽ, nút CTA có hiệu ứng nhịp tim `animate__pulse` thu hút sự chú ý của game thủ.
  - Các thẻ `<article class="character-card">` có hiệu ứng `data-aos="fade-up"` với `data-aos-delay` tăng dần từ 100ms đến 400ms tạo cảm giác mở thẻ bài gacha tuần tự.
  - Hiệu ứng CSS `:hover` nâng thẻ card nhân vật `-8px`, viền phát sáng `--glow-cyan` / `--glow-pink`, ảnh nhân vật zoom 1.06x sống động.

- **Thách thức gặp phải:**
  - Sau khi tích hợp AOS, khi cuộn trang trên một số kích thước màn hình, các phần tử không kích hoạt hiệu ứng cuộn hoặc thanh cuộn ngang xuất hiện làm biến dạng giao diện (Horizontal overflow).
  - Nguyên nhân: Việc đặt `overflow-x: hidden;` trên cả thẻ `html` gây xung đột đối tượng lắng nghe sự kiện cuộn của thư viện AOS, khiến hàm tính toán tọa độ phần tử bị treo.

- **Cách sửa prompt (Debug prompt):**
  > *"Tôi đã nhúng thư viện AOS nhưng khi cuộn trang các phần tử không hiển thị hiệu ứng. Hãy giúp tôi kiểm tra lại:*
  > 1. *Đã chèn file script `aos.js` và lệnh khởi tạo `AOS.init()` ở cuối file HTML trước `</body>` chưa?*
  > 2. *Sửa lại cho tôi đoạn mã khởi tạo JS chuẩn và kiểm tra xem có xung đột CSS overflow nào khiến scrollbar không nhận diện được AOS không."*

- **Giải pháp xử lý từ AI & SV:**
  - Nhúng đầy đủ CDN script `aos.js` trước thẻ đóng `</body>`.
  - Khởi tạo script chuẩn trong sự kiện `DOMContentLoaded`:
    ```javascript
    document.addEventListener('DOMContentLoaded', function () {
      AOS.init({
        duration: 800,
        easing: 'ease-out-cubic',
        once: true,
        offset: 50
      });
      window.addEventListener('resize', function () {
        AOS.refresh();
      });
    });
    ```
  - Trong `style.css`, chỉ để `scroll-behavior: smooth;` trên thẻ `html` và xử lý chống tràn an toàn trên thẻ `body`. Sau khi sửa, hiệu ứng cuộn AOS chạy hoàn hảo 100%.

---

## 3. Đánh giá cá nhân về quá trình Vibe Coding

### AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?
- **Khởi tạo bảng màu & Hệ thống CSS Variables:** AI giúp phối màu Dark Mode kết hợp Xanh Neon (`#06b6d4`) và Hồng Neon (`#f43f5e`) vô cùng hài hòa, tạo ngay các biến phát sáng (`--glow-cyan`, `--glow-pink`) mà không tốn công căn chỉnh thủ công.
- **Dựng Layout CSS Grid đa cột phức tạp:** Việc dàn trang 4 thẻ nhân vật chiến thuật bằng CSS Grid, kèm theo cấu trúc responsive tự động co giãn về 2 cột trên Tablet và 1 cột trên Mobile được AI sinh mã chuẩn xác ngay lập tức.
- **Tiết kiệm thời gian tìm kiếm thư viện:** Tích hợp nhanh chóng Google Font Orbitron, CDN Animate.css v4.1.1 và AOS mà không cần tra cứu tài liệu từ nhiều nguồn khác nhau.

### Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?
1. **Định hình phong cách thiết kế ngay từ vai trò (Role):** Khi chỉ định *"Senior Front-end Developer chuyên về thiết kế giao diện Game & Cyberpunk"*, AI sẽ chủ động dùng các thuật ngữ, màu sắc và cấu trúc phù hợp với game (Rarity SSR, Hex-Grid, Stats, Factions, Neon Glow) thay vì một website thông thường.
2. **Kiểm soát chặt chẽ Semantic HTML:** Nếu không nhắc nhở ngay từ đầu, AI rất dễ dùng thẻ `<div>` cho mọi thứ. Khi đưa ra yêu cầu cụ thể về `<header>`, `<nav>`, `<main>`, `<section id="...">`, `<article class="character-card">`, `<footer>`, chất lượng mã nguồn đạt chuẩn cao cấp.
3. **Kỹ năng gỡ lỗi tương tác giữa CSS và JS:** Khi thư viện bên thứ 3 (như AOS) gặp lỗi, việc hiểu rõ cơ chế cuộn của trình duyệt giúp đặt câu hỏi Debug chính xác để AI tìm ra đúng nguyên nhân xung đột thuộc tính `overflow`.
