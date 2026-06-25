# Biểu Đồ Vàng PNJ - GitHub Pages Static Build

Bộ source này được chuyển từ file HTML bạn gửi sang bản chạy trực tiếp trên GitHub Pages.

## Cấu trúc

```text
.
├── index.html
├── 404.html
└── assets/
    ├── css/github-fixes.css
    └── js/github-fixes.js
```

## Cách deploy GitHub Pages

1. Tạo repository mới trên GitHub.
2. Upload toàn bộ file trong thư mục này lên repository.
3. Vào **Settings → Pages**.
4. Chọn **Deploy from a branch**.
5. Branch: `main`, folder: `/root`.
6. Bấm **Save**.

## Những lỗi đã fix

- Sửa toàn bộ `type="...-text/javascript"` do Cloudflare Rocket Loader tạo ra, khiến JavaScript không chạy trên GitHub Pages.
- Xóa script `/cdn-cgi/...` và Cloudflare Beacon vì GitHub không có đường dẫn này.
- Giải mã email bị Cloudflare che thành `mailto:contact@bieudovang.com`.
- Thêm Tailwind CDN fallback để layout render đúng khi chạy static.
- Thêm `github-fixes.css` để vá overlay loading, brand color, mobile menu và chart container.
- Thêm `github-fixes.js` để menu mobile, submenu và ô tìm kiếm hoạt động.
- Thêm `404.html` giống `index.html` để hạn chế lỗi khi refresh đường dẫn trên GitHub Pages.

## Lưu ý

Trang vẫn đang dùng một số asset gốc từ `https://bieudovang.com/` như CSS/JS/logo/API chart. Nếu muốn chạy độc lập 100%, cần tải các asset đó về repo và đổi đường dẫn sang local.
