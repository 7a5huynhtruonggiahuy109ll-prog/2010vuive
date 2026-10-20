# Một khu vườn dành tặng bạn · 20/10/2026

Một website chúc mừng Ngày Phụ nữ Việt Nam theo dạng trình chiếu nhiều cảnh, được viết bằng HTML, CSS và JavaScript thuần. Giao diện và hình minh họa được triển khai lại như một dự án mới, kết hợp ý tưởng trang chào mừng 20/10 với các trải nghiệm bó hoa/vườn hoa, thiệp cá nhân hóa và album ảnh. Hai repository tham khảo ý tưởng là [huyndcv/20102026](https://github.com/huyndcv/20102026) và [IdeaToCodee/flowers-20-10](https://github.com/IdeaToCodee/flowers-20-10); source của gói này được viết lại, không nhúng nguyên văn hai repository đó.

**Creator:** Huỳnh Trương Gia Huy · 12 Tin

## Chạy website

1. Giải nén toàn bộ thư mục ZIP.
2. Mở `index.html` bằng Chrome, Edge, Safari hoặc Firefox.
3. Không cần cài thư viện, không cần build, không cần Internet. Giữ nguyên cấu trúc thư mục khi chạy.

Để chạy qua local server (khuyến nghị khi thử trên máy tính):

```bash
python -m http.server 8080
```

Sau đó mở `http://localhost:8080`.

## Trải nghiệm

- **05 cảnh trình chiếu:** mở đầu, vườn hoa, lời chúc, album kỷ niệm và tấm thiệp cuối hành trình.
- **Chuyển cảnh:** nút trái/phải, chấm điều hướng, phím mũi tên, Page Up/Page Down, Home/End và vuốt ngang trên màn hình cảm ứng.
- **Vườn hoa chân thực:** ảnh nền khu vườn bình minh được tối ưu WebP, các lớp phủ màu điện ảnh, năm bông hoa nở lần lượt với hiệu ứng phát sáng và điểm chạm tương tác để đọc lời chúc. Cảnh mở đầu và cảnh thiệp kết thúc dùng khu vườn Canvas; nhịp vẽ được giới hạn để giảm tải CPU.
- **Lời chúc:** lời chúc ngẫu nhiên và các thiệp riêng cho mẹ, cô giáo, bạn bè và chính mình.
- **Album cá nhân:** thay 3 ảnh mẫu bằng ảnh trên thiết bị. Ảnh được thu nhỏ trước khi lưu vào `localStorage` trên trình duyệt hiện tại.
- **Thiệp tùy chỉnh:** sửa tên người nhận, lời mở đầu, nội dung và chữ ký. Nội dung được lưu trên trình duyệt hiện tại.
- **Không phụ thuộc thư viện ngoài:** không dùng CDN hoặc tải hình từ bên thứ ba; có thể mở offline.
- **Responsive và accessibility:** bố cục điện thoại/máy tính bảng/máy tính, điều hướng bằng phím mũi tên/Home/End/Page Up/Page Down, hỗ trợ Enter/Space cho nút, trạng thái hoa được thông báo bằng `aria-pressed`, và tôn trọng `prefers-reduced-motion`. Font Noto Sans và Noto Serif đã được nhúng trực tiếp dưới dạng WOFF2 có hỗ trợ đầy đủ dấu tiếng Việt, vì vậy không phụ thuộc font cài sẵn trên máy. Font được tải từ thư mục assets khi chạy offline; tiêu đề cũng có khoảng cách chữ và cỡ chữ thích ứng với cửa sổ thấp để tránh dấu bị chạm, chồng hoặc bị cắt.

## Cấu trúc

```text
20-10-flower-journey/
├── index.html
├── README.md
├── css/
│   └── styles.css
├── js/
│   └── app.js
└── assets/
    ├── fonts/
    │   ├── NotoSans-Regular.woff2
    │   ├── NotoSans-Bold.woff2
    │   ├── NotoSerif-Regular.woff2
    │   ├── NotoSerif-Italic.woff2
    │   ├── NotoSerif-Bold.woff2
    │   └── OFL-and-copyright.txt
    ├── favicon.svg
    ├── memory-rose.svg
    ├── memory-meadow.svg
    ├── memory-tulip.svg
    └── realistic-garden.webp
```

## Cá nhân hóa

- Thay tên/chữ ký mặc định tại phần cuối `index.html`, hoặc dùng nút **Viết lời chúc riêng** ngay trên website.
- Thay ảnh trực tiếp bằng nút **Thay ảnh của bạn** ở cảnh Album. Ảnh cá nhân chỉ được lưu trong trình duyệt và không được nhúng ngược vào source ZIP.
- Nội dung thư và ảnh album sử dụng các khóa `localStorage` có tiền tố `flowerJourney20_10_`.

## Lưu ý kỹ thuật

Website không có backend hay đồng bộ đám mây. Lời chúc tùy chỉnh và ảnh thay thế được lưu cục bộ trên trình duyệt/thiết bị hiện tại. Xóa dữ liệu website của trình duyệt có thể xóa các nội dung này. Nếu cần chia sẻ cùng một nội dung cho tất cả người truy cập, hãy sửa file nguồn trực tiếp trước khi xuất bản GitHub Pages.
