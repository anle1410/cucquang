# ✨ CỰC QUANG — Aurora in Motion

<p align="center">
  <strong>Một dải cực quang chuyển động giữa bầu trời đêm đầy sao.</strong><br>
  Được tạo nên từ HTML, CSS và JavaScript thuần — gọn nhẹ, không cần thư viện ngoài.
</p>

<p align="center">
  <img alt="HTML5" src="https://img.shields.io/badge/HTML5-markup-E34F26?style=for-the-badge&logo=html5&logoColor=white">
  <img alt="CSS3" src="https://img.shields.io/badge/CSS3-visuals-1572B6?style=for-the-badge&logo=css3&logoColor=white">
  <img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-animation-F7DF1E?style=for-the-badge&logo=javascript&logoColor=111111">
  <img alt="Dependencies" src="https://img.shields.io/badge/dependencies-none-39C98A?style=for-the-badge">
</p>

---

## 🌌 Giới thiệu

**CỰC QUANG — Aurora in Motion** là một trải nghiệm đồ họa web nhỏ gọn, tái hiện bầu trời xanh đêm với các vì sao và một vệt cực quang màu tím – xanh chuyển động liên tục. Hiệu ứng được dựng hoàn toàn bằng CSS và bộ lọc SVG, trong khi JavaScript thay đổi nhiễu theo từng khung hình để làm dải sáng trở nên sống động.

> Không framework. Không cài đặt gói. Chỉ mở trang và ngắm cực quang.

## ✨ Điểm nổi bật

- 🌠 **Bầu trời sao** với nhiều điểm sáng được tạo bằng `box-shadow`.
- 💜 **Dải cực quang chuyển sắc** tím và xanh ngọc, hòa trộn vào nền đêm.
- 🌊 **Chuyển động hữu cơ** nhờ bộ lọc SVG turbulence và displacement.
- 🎞️ **Hoạt ảnh liên tục** được cập nhật bằng `requestAnimationFrame`.
- 🪶 **Nhẹ và độc lập** — không có dependency, framework hay bước build.
- 🧩 **Dễ tùy chỉnh** màu sắc, kích thước khung cảnh và nhịp biến đổi.

## 👀 Trải nghiệm hiện tại

Trang web tập trung vào một khung cảnh đồ họa duy nhất:

1. Nền xanh đậm tạo không gian bầu trời đêm.
2. Các ngôi sao trắng nhỏ rải khắp khung cảnh.
3. Một dải sáng tím – xanh xuất hiện gần phía trên.
4. Dải sáng biến dạng nhẹ theo thời gian để mô phỏng chuyển động của cực quang.

Hiệu ứng chạy tự động khi mở trang; phiên bản hiện tại không có nút điều khiển hoặc nội dung điều hướng.

## 🚀 Bắt đầu

### Yêu cầu

- Trình duyệt hiện đại có hỗ trợ CSS, SVG filters và JavaScript.
- Không cần cài Node.js, package hay công cụ build.

### Cách 1: Mở trực tiếp

Mở tệp `15\aurora.html` bằng trình duyệt.

### Cách 2: Chạy qua máy chủ tĩnh

Từ thư mục gốc của dự án, mở PowerShell hoặc Terminal:

```powershell
py -m http.server 8000
```

Sau đó truy cập:

```text
http://localhost:8000/15/aurora.html
```

Dừng máy chủ bằng `Ctrl + C`.

## 🗂️ Cấu trúc dự án

```text
.
├── README.md
└── 15/
    ├── aurora.html    # Khung trang, SVG filter và liên kết tài nguyên
    ├── aurora.css     # Bố cục, bầu trời sao và kiểu cực quang
    └── aurora.js      # Cập nhật nhiễu để tạo chuyển động
```

### Vai trò từng tệp

| Tệp | Trách nhiệm |
| --- | --- |
| [`15/aurora.html`](15/aurora.html) | Khai báo tài liệu HTML, kết nối CSS/JavaScript và định nghĩa SVG filter `wave`. |
| [`15/aurora.css`](15/aurora.css) | Tạo khung cảnh 350 × 500 px, nền trời, sao và dải sáng cực quang. |
| [`15/aurora.js`](15/aurora.js) | Thay đổi thuộc tính `baseFrequency` của SVG turbulence theo từng khung hình. |

## ⚙️ Cách hiệu ứng hoạt động

1. Phần tử `.g-wrap` tạo khung cảnh có nền xanh đêm; pseudo-element `::before` dùng nhiều lớp `box-shadow` để vẽ các vì sao.
2. Pseudo-element `.g-aurora::before` tạo dải sáng bằng radial gradient màu tím và xanh ngọc.
3. Bộ lọc SVG `wave` kết hợp `feTurbulence` và `feDisplacementMap` để làm biến dạng dải sáng.
4. JavaScript dao động giá trị `baseFrequency` theo hàm sin/cos và yêu cầu khung hình kế tiếp bằng `requestAnimationFrame`.

## 🎨 Tùy chỉnh nhanh

Mọi thay đổi dưới đây thực hiện trong `15\aurora.css`, trừ phần được ghi chú:

| Muốn thay đổi | Vị trí gợi ý |
| --- | --- |
| Kích thước khung cảnh | `.g-wrap` — chỉnh `width` và `height`. |
| Màu bầu trời | `background` trong `.g-wrap`. |
| Màu cực quang | Các điểm màu trong `radial-gradient` của `.g-aurora::before`. |
| Độ rộng và chiều cao dải sáng | `width`, `height` trong `.g-aurora::before`. |
| Độ biến dạng | `scale` trên `feDisplacementMap` trong `15\aurora.html`. |
| Tốc độ và biên độ biến đổi | Các giá trị trong `freqAnimation()` ở `15\aurora.js`. |
| Số lượng và vị trí ngôi sao | Danh sách `box-shadow` trong `.g-wrap::before`. |

## 🧰 Công nghệ

- **HTML5** — cấu trúc trang.
- **CSS3** — bố cục, gradient, hòa trộn màu và hiệu ứng thị giác.
- **SVG filters** — turbulence và displacement cho chuyển động dạng sóng.
- **JavaScript thuần** — hoạt họa cập nhật theo khung hình trình duyệt.

## 📝 Ghi chú

- Dải sáng phụ thuộc vào hỗ trợ CSS `filter: url(#wave)`, SVG filters và `mix-blend-mode`; kết quả có thể khác nhau giữa các trình duyệt.
- Kích thước khung cảnh hiện được đặt cố định trong CSS; nếu thay đổi kích thước, hãy cân nhắc điều chỉnh vị trí các điểm sao.
- Dự án là trang minh họa hiệu ứng, chưa bao gồm backend, giao diện điều khiển hay quy trình build.

## 👤 Tác giả

**Lê Phú An**

---

<p align="center">
  <strong>Made with ✨ and a little CSS magic</strong><br>
  <sub>Ngước nhìn bầu trời — ngay trong trình duyệt của bạn.</sub>
</p>
