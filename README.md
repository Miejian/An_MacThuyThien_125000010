# BÀI THI GIỮA KỲ MÔN THIẾT KẾ WEB - ĐẠI HỌC LẠC HỒNG

- **Họ và tên sinh viên:** Mạc Thủy Thiên Ân
- **Mã số sinh viên (MSSV):** 25AI111
- **Khoa:** Công nghệ Thông tin - Trường Đại học Lạc Hồng (LHU)
- **Tên đề tài:** Cyber-Gamified Showcase Landing Page (Tựa game nhập vai chiến thuật Gen Z: *CYBER-CHRONO 2088: NEON PROTOCOL*)
- **Tên Repository theo quy chuẩn:** `An_MacThuyThien_25AI111`
- **Live Preview (GitHub Pages):** `https://<your-username>.github.io/An_MacThuyThien_25AI111/`

---

## 📁 Cấu Trúc Repository

```text
An_MacThuyThien_25AI111/
├── assets/
│   ├── cyber_hero.svg     # Banner thế giới tương lai Neo-Veridia 2088 (Vector SVG)
│   ├── character1.svg     # Nhân vật SSR: Kira - Sát thủ Neon (Cyber Assassin)
│   ├── character2.svg     # Nhân vật SSR: Vex - Netrunner Phá Mã (Neural Hacker)
│   ├── character3.svg     # Nhân vật SSR: Titan-09 - Chiến Giáp Tiên Phong (Mech Vanguard)
│   └── character4.svg     # Nhân vật SSR: Nyx - Ngoại Cảm Tâm Linh (Psionic Strategist)
├── index.html             # Mã nguồn chính theo chuẩn Semantic HTML5 & Cyberpunk
├── style.css              # Bảng định kiểu CSS Variables, CSS Grid, Flexbox, Neon Glow
├── PROMPT_LOG.md          # Nhật ký Prompt Engineering (Vibe Coding Log chuẩn mẫu ĐH Lạc Hồng)
└── README.md              # Tài liệu giới thiệu & hướng dẫn triển khai GitHub Pages
```

---

## 🎯 Các Tiêu Chuẩn Kỹ Thuật Đạt Được

1. **Chuẩn Semantic HTML5 (Tối thiểu 5 thành phần):**
   - `<header>`: Ứng dụng CSS Flexbox chứa Logo game `CYBERCHRONO 2088` và Menu điều hướng.
   - `<nav>`: Menu điều hướng linh hoạt với liên kết các phân khu Lore, Nhân vật, Tính năng, Đăng ký sớm.
   - `<main>`: Chứa toàn bộ nội dung chính của Landing Page.
   - `<section id="...">`: Phân khu rõ ràng:
     - `#hero`: Trailer mở đầu với Animate.css.
     - `#lore`: Bối cảnh thế giới tương lai Neo-Veridia.
     - `#characters`: Danh sách nhân vật chiến thuật.
     - `#gameplay`: Cơ chế Hex-Grid và AI Assistant.
     - `#pre-register`: Form ghi danh nhận quà Closed Beta.
   - `<article class="character-card">`: 4 thẻ nhân vật chiến thuật độc lập, tích hợp `<figure>`, `<figcaption>`, thanh chỉ số Speed/Atk/Def và nút chọn tướng.
   - `<footer>`: Chân trang đầy đủ thông tin bản quyền, mạng xã hội và thông tin sinh viên Mạc Thủy Thiên Ân (25AI111).
   - **Tuyệt đối không lạm dụng thẻ `<div>` vô nghĩa.**

2. **Kỹ thuật CSS & CSS Variables (Theme Dark Mode):**
   - Quản lý tập trung trong `:root` theo đúng yêu cầu đề bài:
     - `--primary-neon: #06b6d4` (Xanh Neon)
     - `--accent-pink: #f43f5e` (Hồng Neon)
     - `--bg-dark: #0f172a` (Dark Mode)
     - `--card-bg: #1e293b`
     - `--text-main: #f8fafc`
     - `--font-main: 'Orbitron', 'Inter', sans-serif`
   - **Bố cục hiện đại:**
     - **CSS Grid:** Dàn trang danh sách nhân vật 4 cột trên Desktop, 2 cột trên Tablet, 1 cột trên Mobile.
     - **Flexbox:** Căn chỉnh thanh điều hướng Navigation, Hero actions, chỉ số game thủ.
   - **Hiệu ứng Cyberpunk:** Viền phát sáng Neon (`--glow-cyan`, `--glow-pink`), hiệu ứng nút nhịp tim `animate__pulse`, đổ bóng tương phản cao.

3. **Tương tác & Hiệu ứng (Libraries):**
   - **Animate.css (v4.1.1):** Áp dụng hiệu ứng `animate__fadeInDown`, `animate__zoomIn`, `animate__fadeInRight` cho tiêu đề và các thành phần chính tại Hero section.
   - **AOS (Animate On Scroll v2.3.4):** Áp dụng hiệu ứng cuộn trang `data-aos="fade-up"` so le với delay `100ms - 400ms` cho từng nhân vật.
   - **Hiệu ứng tự viết bằng CSS:** Tương tác `:hover`, `:focus-visible` với `transition: 0.3s`, nhấc thẻ nhẹ nhàng (`transform: translateY(-8px)`), phóng to ảnh và đổ bóng viền neon rực rỡ.

4. **Nhật ký Vibe Coding (PROMPT_LOG.md):**
   - Trình bày chi tiết chuẩn 100% theo mẫu của ĐH Lạc Hồng:
     - Mục 1: System / Initial Prompt về giao diện Game & Cyberpunk.
     - Mục 2: Hai lần tinh chỉnh (Semantic HTML & Thư viện Animate.css / AOS) và quá trình gỡ lỗi xung đột thuộc tính `overflow`.
     - Mục 3: Đánh giá cá nhân sâu sắc về trải nghiệm Vibe Coding.

---

## 🚀 Hướng Dẫn Kích Hoạt GitHub Pages (Dành cho Sinh Viên)

1. **Tạo Repository trên GitHub:**
   - Tên Repository bắt buộc: `An_MacThuyThien_25AI111`
   - Quyền truy cập: **Public**

2. **Đẩy mã nguồn từ máy tính lên GitHub:**
   ```bash
   git init
   git add .
   git commit -m "feat: complete Cyber-Gamified Showcase - An_MacThuyThien_25AI111"
   git branch -M main
   git remote add origin https://github.com/<your-username>/An_MacThuyThien_25AI111.git
   git push -u origin main
   ```

3. **Bật GitHub Pages:**
   - Vào **Settings** > **Pages**.
   - Tại mục **Build and deployment** > **Branch**, chọn nhánh `main` và thư mục `/ (root)`.
   - Nhấn **Save**. Đường link preview sẽ xuất hiện sau 1-2 phút.
   - Dán đường link Live Preview vào phần **About** của GitHub Repository để Giảng viên chấm thi.
