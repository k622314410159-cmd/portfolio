# Portfolio cá nhân — Vũ Quỳnh Trang (Tracy)

Website portfolio song ngữ (Việt - Anh) theo phong cách "Bubble Fairytale", dùng để ứng tuyển vị trí **Sales Logistics**.

- Sinh viên: Vũ Quỳnh Trang (Tracy)
- Trường: Đại học Ngoại thương (FTU), Hà Nội — Kinh tế quốc tế, 2023-2027
- Định hướng: Sales Logistics

---

## 1. Công nghệ sử dụng

Trang web là **một file HTML tĩnh duy nhất**, không cần cài đặt hay build:

- HTML5 (semantic: `header`, `nav`, `main`-equivalent sections, `footer`)
- CSS3 thuần (CSS variables, Grid, Flexbox, keyframe animation, `prefers-reduced-motion`)
- JavaScript thuần (vanilla JS) — không dùng framework, không cần `npm install`
- Font: Google Fonts (Playfair Display + Nunito Sans)

Vì không có bước build, đây là lựa chọn đơn giản hơn so với hướng Vite + React trong bản brief gốc — phù hợp để giáo viên/mọi người mở trực tiếp bằng trình duyệt mà không cần cài công cụ gì.

## 2. Cấu trúc thư mục

```
.
├── index.html                     # Toàn bộ trang web (HTML + CSS + JS)
├── README.md                      # File này
├── CONTENT-CHECKLIST.md           # Danh sách kiểm tra nội dung trước khi công bố
└── assets/
    ├── cv/
    │   └── CV_Vu_Quynh_Trang.pdf          # CV để tải xuống
    ├── documents/
    │   ├── Nhom16-Kinh-te-chinh-tri-quoc-te.docx
    │   ├── Tieu-luan-KTPT.docx
    │   └── Nhom5-Tiem-nang-giam-phat-thai-khi-nha-kinh.docx
    ├── images/
    │   ├── tracy-photo.jpg        # Ảnh cá nhân dùng trong Hero/About
    │   └── og-image.jpg           # Ảnh xem trước khi chia sẻ link (1200x630)
    └── icons/
        └── favicon.svg            # Biểu tượng tab trình duyệt (bong bóng + ngôi sao)
```

> Lưu ý: ảnh cá nhân và CV đã được **nhúng sẵn (base64)** ngay trong `index.html`, nên trang vẫn hiển thị đầy đủ kể cả khi chỉ mở mỗi file `index.html`. Thư mục `assets/` được giữ lại để đúng chuẩn cấu trúc dự án và để 3 bài tiểu luận có thể tải xuống được (link trỏ tới các file trong `assets/documents/`).

## 3. Cách xem trên máy

Không cần cài đặt gì — chỉ cần bấm đúp vào `index.html` để mở bằng trình duyệt (Chrome, Edge, Firefox...).

Nếu muốn chạy qua local server (để đường link tải tiểu luận hoạt động đúng như khi deploy):

```bash
# Cách 1: dùng Python có sẵn
python3 -m http.server 8000
# rồi mở http://localhost:8000

# Cách 2: dùng VS Code, cài extension "Live Server" rồi bấm "Go Live"
```

## 4. Đưa lên GitHub Pages

```bash
git init
git add .
git commit -m "Create Tracy portfolio"
git branch -M main
git remote add origin https://github.com/k622314410159-cmd/k622314410159-cmd.github.io.git
git push -u origin main
```

Sau đó vào **Settings > Pages** của repository, chọn nguồn là nhánh `main`, thư mục `/ (root)`. Sau vài phút trang sẽ chạy tại:

```
https://k622314410159-cmd.github.io/
```

Nếu dùng repo dạng project page (không phải trang cá nhân), thay tên repo và cập nhật lại đường dẫn `og:url` / `canonical` trong `index.html` cho khớp.

Cập nhật sau này:

```bash
git add .
git commit -m "Update portfolio content"
git push
```

## 5. Cách chỉnh sửa nội dung

- Toàn bộ chữ tiếng Anh nằm trong thẻ có class `lang-en`, chữ tiếng Việt nằm trong `lang-vi` — sửa trực tiếp trong `index.html`, ngay cạnh nhau nên rất dễ tìm và đối chiếu hai bản.
- Nút chuyển ngôn ngữ EN|VI ở góc phải thanh menu; lựa chọn ngôn ngữ được ghi nhớ qua `localStorage`.
- Muốn đổi ảnh cá nhân: thay file `assets/images/tracy-photo.jpg`, đồng thời cập nhật lại chuỗi base64 trong biến `PHOTO_SRC` ở cuối `index.html` (hoặc đơn giản hơn là sửa `src="assets/images/tracy-photo.jpg"` trực tiếp nếu chạy qua server thay vì mở file offline).
- Muốn đổi CV: thay file `assets/cv/CV_Vu_Quynh_Trang.pdf`.
- Muốn thêm/xoá bài tiểu luận: thêm file vào `assets/documents/` và sửa đường dẫn `href` trong thẻ `<a class="dl-link">` tương ứng ở phần "Projects & Research".

## 6. Khả năng truy cập & hiệu năng

- Điều hướng đầy đủ bằng bàn phím, có viền focus rõ ràng (Deep Rose).
- Tôn trọng `prefers-reduced-motion` — tắt hiệu ứng chuyển động khi người dùng bật chế độ giảm chuyển động.
- Tương phản màu chữ đạt chuẩn WCAG AA (chữ dùng màu Ink/Deep Rose trên nền sáng).
- Responsive đầy đủ ở các mốc 360px, 768px, 1024px, 1440px.
- Không dùng nhạc nền tự phát, không có hiệu ứng nhấp nháy gây khó chịu.

## 7. Ghi chú

Bố cục, màu sắc, cấu trúc nội dung được xây dựng dựa trên bản brief thiết kế "Tracy Portfolio · Bubble Fairytale", với sự hỗ trợ soạn thảo mã nguồn từ Claude (Anthropic). Toàn bộ thông tin cá nhân, kinh nghiệm, học vấn được lấy trực tiếp từ CV và do Tracy xác nhận trước khi công bố — không có số liệu, kết quả nghiên cứu hay thành tích nào được tự thêm vào.

---

Vũ Quỳnh Trang (Tracy) · trangvu8405@gmail.com · github.com/k622314410159-cmd
