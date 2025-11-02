# 🏢 Biolink Bất Động Sản - Trang Liên Kết Chuyên Nghiệp

## 📋 Tổng Quan Dự Án

Trang biolink chuyên nghiệp dành cho chuyên viên tư vấn bất động sản, được xây dựng với Hono framework và Cloudflare Pages. Thiết kế hiện đại, responsive, tối ưu cho mobile và tải nhanh toàn cầu.

## ✨ Tính Năng Chính

### 🎯 Đã Hoàn Thành
- ✅ Giao diện hiện đại với Tailwind CSS
- ✅ Responsive 100% trên mọi thiết bị
- ✅ Thông tin cá nhân với avatar chuyên nghiệp
- ✅ Hiển thị thống kê (khách hàng, giao dịch, kinh nghiệm)
- ✅ 2 nút liên hệ nhanh (Gọi điện & Zalo)
- ✅ Phần dịch vụ chuyên nghiệp (4 loại dịch vụ)
- ✅ Liên kết đến các nền tảng mạng xã hội:
  - Facebook (tin BĐS mới nhất)
  - YouTube (review dự án)
  - TikTok (video ngắn)
  - Instagram (hình ảnh dự án)
  - Email
  - Website
- ✅ Thông tin liên hệ đầy đủ (SĐT, địa chỉ, giờ làm việc)
- ✅ Animation mượt mà, hiệu ứng hover chuyên nghiệp
- ✅ Icons Font Awesome đầy đủ
- ✅ Gradient màu sắc bắt mắt (xanh dương & cam)

### 📱 Các Link Có Sẵn
- `/` - Trang chủ biolink

## 🎨 Giao Diện

### Các Phần Chính
1. **Profile Section**: Avatar, tên, chức vụ, giới thiệu ngắn
2. **Stats Section**: 3 thẻ thống kê (Khách hàng, Giao dịch, Kinh nghiệm)
3. **Quick Contact**: 2 nút lớn (Gọi điện & Zalo)
4. **Services**: 4 dịch vụ chính (Mua bán, Cho thuê, Tư vấn, Định giá)
5. **Social Links**: 6 nút liên kết mạng xã hội với icon đẹp
6. **Contact Info**: Thông tin liên hệ chi tiết
7. **Footer**: Copyright & credit

### Màu Sắc
- Xanh dương (#2563eb) - Chủ đạo
- Cam (#ea580c) - Điểm nhấn
- Trắng & xám - Background
- Gradient hiện đại

## 🚀 Hướng Dẫn Cài Đặt

### 1. Clone Repository
```bash
git clone https://github.com/yourusername/biolink-batdongsan.git
cd biolink-batdongsan
```

### 2. Cài Đặt Dependencies
```bash
npm install
```

### 3. Chỉnh Sửa Thông Tin Cá Nhân

Mở file `src/index.tsx` và thay đổi các thông tin sau:

```typescript
// Thông tin cá nhân (dòng ~15-20)
<h1>Nguyễn Văn A</h1>  // Đổi tên của bạn
<p>Chuyên Viên Tư Vấn Bất Động Sản</p>  // Chức vụ

// Số điện thoại (dòng ~45 và ~135)
<a href="tel:0123456789">  // Đổi số điện thoại
<a href="https://zalo.me/0123456789">  // Đổi số Zalo

// Link mạng xã hội (dòng ~80-140)
href="https://facebook.com/yourpage"  // Đổi Facebook
href="https://youtube.com/@yourchannel"  // Đổi YouTube
href="https://tiktok.com/@yourusername"  // Đổi TikTok
href="https://instagram.com/yourusername"  // Đổi Instagram
href="mailto:contact@example.com"  // Đổi Email
href="https://yourwebsite.com"  // Đổi Website

// Địa chỉ (dòng ~160)
<span>TP. Hồ Chí Minh, Việt Nam</span>  // Đổi địa chỉ
```

### 4. Build Dự Án
```bash
npm run build
```

### 5. Test Local
```bash
npm run preview
# Hoặc sử dụng PM2
pm2 start ecosystem.config.cjs
```

## 🌐 Deploy Lên GitHub Pages

### Bước 1: Tạo Repository Trên GitHub
1. Vào https://github.com/new
2. Tạo repository mới tên `biolink-batdongsan`
3. Chọn Public
4. **KHÔNG** tích "Initialize with README"

### Bước 2: Push Code Lên GitHub
```bash
# Đã có git init rồi, chỉ cần add remote
git remote add origin https://github.com/yourusername/biolink-batdongsan.git

# Commit các thay đổi (nếu có)
git add .
git commit -m "Cập nhật thông tin cá nhân"

# Push lên GitHub
git push -u origin main
```

### Bước 3: Deploy Lên Cloudflare Pages (Khuyên dùng)

Cloudflare Pages miễn phí, nhanh hơn GitHub Pages rất nhiều!

```bash
# Cài Wrangler CLI (nếu chưa có)
npm install -g wrangler

# Login Cloudflare
wrangler login

# Deploy
npm run deploy
# Hoặc
wrangler pages deploy dist --project-name biolink-batdongsan
```

Bạn sẽ nhận được URL dạng: `https://biolink-batdongsan.pages.dev`

## 📦 Cấu Trúc Dự Án

```
webapp/
├── src/
│   ├── index.tsx          # Main app với biolink layout
│   └── renderer.tsx       # HTML template với Tailwind & Font Awesome
├── public/
│   └── static/
│       └── style.css      # Custom CSS & animations
├── dist/                  # Build output (sau khi npm run build)
├── package.json          # Dependencies
├── wrangler.jsonc        # Cloudflare config
├── vite.config.ts        # Vite config
├── tsconfig.json         # TypeScript config
└── README.md            # File này
```

## 🛠️ Tech Stack

- **Framework**: Hono (lightweight web framework)
- **Runtime**: Cloudflare Workers
- **Build**: Vite
- **Styling**: Tailwind CSS (CDN)
- **Icons**: Font Awesome 6.4.0
- **Font**: Inter (Google Fonts)
- **Language**: TypeScript

## 📱 Tính Năng Responsive

- ✅ Mobile First Design
- ✅ Tối ưu cho iPhone, Android
- ✅ Tablet & Desktop
- ✅ Touch-friendly buttons
- ✅ Fast loading

## 🎯 Tùy Chỉnh Thêm

### Thêm Link Mới
Thêm code này vào phần Social Links trong `src/index.tsx`:

```tsx
<a href="https://your-new-link.com" target="_blank" class="block bg-white hover:bg-gray-50 rounded-xl shadow-md hover:shadow-lg transition-all duration-300 p-4 transform hover:-translate-y-1">
  <div class="flex items-center justify-between">
    <div class="flex items-center space-x-4">
      <div class="w-12 h-12 bg-blue-500 rounded-full flex items-center justify-center">
        <i class="fas fa-star text-white text-xl"></i>
      </div>
      <div>
        <p class="font-semibold text-gray-800">Tên Link</p>
        <p class="text-sm text-gray-500">Mô tả ngắn</p>
      </div>
    </div>
    <i class="fas fa-chevron-right text-gray-400"></i>
  </div>
</a>
```

### Đổi Màu Chủ Đạo
Tìm các class trong `src/index.tsx`:
- `from-blue-600 to-orange-500` → Đổi gradient chính
- `text-blue-600` → Đổi màu text
- `bg-blue-500` → Đổi màu background

## 🔥 URLs Sau Khi Deploy

### GitHub Pages
`https://yourusername.github.io/biolink-batdongsan/`

### Cloudflare Pages (Khuyên dùng)
`https://biolink-batdongsan.pages.dev`

### Custom Domain
Bạn có thể kết nối domain riêng miễn phí trên Cloudflare Pages!

## 📞 Hỗ Trợ

Nếu cần hỗ trợ, hãy:
1. Đọc kỹ README này
2. Check file `src/index.tsx` để xem cấu trúc
3. Google "Hono framework docs" hoặc "Tailwind CSS docs"

## 📄 License

MIT License - Dùng tự do cho mục đích cá nhân và thương mại

---

**Made with ❤️ using Hono + Cloudflare Pages**

🎉 Chúc bạn thành công với biolink bất động sản!
