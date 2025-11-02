# ⚡ HƯỚNG DẪN NHANH - 5 PHÚT ĐƯA LÊN GITHUB

## 🎯 Những Gì Bạn Cần Làm

### 1️⃣ Tạo GitHub Token (2 phút)
1. Vào: https://github.com/settings/tokens
2. Click: **Generate new token (classic)**
3. Tích: **repo** (toàn bộ)
4. Click: **Generate token**
5. **Copy token** (bắt đầu bằng `ghp_...`) và lưu lại!

### 2️⃣ Tạo Repository Trên GitHub (1 phút)
1. Vào: https://github.com/new
2. Tên repo: `biolink-batdongsan` (hoặc tên khác)
3. Chọn: **Public** hoặc **Private**
4. **KHÔNG TÍCH** các ô Initialize, .gitignore, license
5. Click: **Create repository**

### 3️⃣ Chạy Lệnh Này (2 phút)

Mở Terminal trong thư mục dự án và chạy:

```bash
# Thay YOUR_USERNAME bằng tên GitHub của bạn
git remote add origin https://github.com/YOUR_USERNAME/biolink-batdongsan.git

# Đẩy code lên
git push -u origin main
```

**Khi hỏi username/password:**
- Username: Tên GitHub của bạn
- Password: Dán token (bắt đầu `ghp_...`)

### 4️⃣ Xác Nhận
Vào https://github.com/YOUR_USERNAME/biolink-batdongsan để xem code!

---

## 📝 Tùy Chỉnh Thông Tin

Sau khi đẩy lên GitHub, bạn cần đổi thông tin cá nhân trong file `src/index.tsx`:

### Những Chỗ Cần Đổi:
1. **Tên & chức vụ** (dòng 15-20)
2. **Số điện thoại** (dòng 45 và 135) - 2 chỗ
3. **Link Zalo** (dòng 50)
4. **Link Facebook** (dòng 85)
5. **Link YouTube** (dòng 95)
6. **Link TikTok** (dòng 105)
7. **Link Instagram** (dòng 115)
8. **Email** (dòng 125)
9. **Website** (dòng 135)
10. **Địa chỉ** (dòng 160)

### Sau Khi Đổi:
```bash
git add .
git commit -m "Cập nhật thông tin cá nhân"
git push origin main
```

---

## 🚀 Deploy Lên Cloudflare Pages (Miễn Phí!)

```bash
# Cài Wrangler
npm install -g wrangler

# Đăng nhập
wrangler login

# Deploy
npm run deploy
```

Nhận URL: `https://biolink-batdongsan.pages.dev`

---

## 📱 Preview Ngay

**Demo đang chạy tại:**
https://3000-ism160zw9nizm1j1e415u-ad490db5.sandbox.novita.ai

---

## ❓ Gặp Vấn Đề?

Đọc file `HUONG_DAN_GITHUB.md` để xem hướng dẫn chi tiết!

---

**🎉 Chúc mừng! Bạn đã sẵn sàng!**
