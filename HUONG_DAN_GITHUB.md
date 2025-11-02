# 📘 HƯỚNG DẪN ĐẨY DỰ ÁN LÊN GITHUB

## 🎯 Mục Tiêu
Đẩy toàn bộ code dự án biolink bất động sản lên GitHub để:
- ✅ Lưu trữ và backup code an toàn
- ✅ Version control (quản lý phiên bản)
- ✅ Chia sẻ với người khác
- ✅ Deploy lên GitHub Pages hoặc Cloudflare Pages

---

## 📋 YÊU CẦU TRƯỚC KHI BẮT ĐẦU

### 1. Tài Khoản GitHub
- Đã có tài khoản GitHub (nếu chưa, đăng ký tại: https://github.com/signup)
- Đã đăng nhập vào tài khoản GitHub

### 2. Git Đã Cài Đặt
Kiểm tra Git đã cài chưa:
```bash
git --version
```

Nếu chưa có, tải tại: https://git-scm.com/downloads

### 3. Xác Thực GitHub
Cần có một trong hai:
- **Personal Access Token** (khuyên dùng)
- **SSH Key**

---

## 🚀 CÁCH 1: SỬ DỤNG PERSONAL ACCESS TOKEN (Đơn giản nhất)

### Bước 1: Tạo Personal Access Token

1. Vào GitHub: https://github.com/settings/tokens
2. Click **"Generate new token"** → **"Generate new token (classic)"**
3. Đặt tên: `biolink-token` (hoặc tên bất kỳ)
4. Chọn quyền:
   - ✅ `repo` (toàn bộ quyền repository)
   - ✅ `workflow` (nếu dùng GitHub Actions)
5. Click **"Generate token"**
6. **LƯU LẠI TOKEN NGAY** (chỉ hiện 1 lần duy nhất!)
   - Ví dụ: `ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxx`

### Bước 2: Tạo Repository Mới Trên GitHub

**QUAN TRỌNG: Đừng tạo repository có sẵn README/License/gitignore!**

1. Vào: https://github.com/new
2. Điền thông tin:
   - **Repository name**: `biolink-batdongsan` (hoặc tên bạn muốn)
   - **Description**: "Trang biolink chuyên nghiệp cho bất động sản"
   - **Public** hoặc **Private** (tùy chọn)
   - **KHÔNG TÍCH** các ô: Initialize with README, Add .gitignore, Add license
3. Click **"Create repository"**

### Bước 3: Kết Nối Local Repository Với GitHub

Mở Terminal/CMD trong thư mục dự án (`/home/user/webapp`) và chạy:

```bash
# 1. Thêm remote origin (thay YOUR_USERNAME và YOUR_REPO_NAME)
git remote add origin https://github.com/YOUR_USERNAME/biolink-batdongsan.git

# Ví dụ: git remote add origin https://github.com/nguyenvana/biolink-batdongsan.git

# 2. Kiểm tra remote đã add chưa
git remote -v

# 3. Đổi tên branch thành main (nếu đang là master)
git branch -M main

# 4. Push code lên GitHub (lần đầu)
git push -u origin main
```

**Khi được hỏi username và password:**
- **Username**: Tên GitHub của bạn
- **Password**: Dán Personal Access Token (không phải mật khẩu GitHub!)

### Bước 4: Xác Nhận Thành Công

Vào https://github.com/YOUR_USERNAME/biolink-batdongsan để xem code đã lên chưa!

---

## 🔐 CÁCH 2: SỬ DỤNG SSH KEY (Cho người có kinh nghiệm)

### Bước 1: Kiểm Tra SSH Key Hiện Có

```bash
ls -al ~/.ssh
```

Nếu thấy file `id_rsa.pub` hoặc `id_ed25519.pub` → đã có SSH key, nhảy qua Bước 3.

### Bước 2: Tạo SSH Key Mới

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

- Nhấn Enter 3 lần (không cần passphrase nếu muốn đơn giản)
- Key được tạo tại: `~/.ssh/id_ed25519`

### Bước 3: Thêm SSH Key Vào GitHub

1. Copy public key:
```bash
cat ~/.ssh/id_ed25519.pub
```

2. Vào GitHub: https://github.com/settings/keys
3. Click **"New SSH key"**
4. Dán nội dung key vào, đặt tên: `My Computer`
5. Click **"Add SSH key"**

### Bước 4: Test SSH Connection

```bash
ssh -T git@github.com
```

Nếu thấy: `Hi YOUR_USERNAME! You've successfully authenticated...` → Thành công!

### Bước 5: Push Code

```bash
# Tạo repo trên GitHub trước (như Cách 1)
# Sau đó:

git remote add origin git@github.com:YOUR_USERNAME/biolink-batdongsan.git
git branch -M main
git push -u origin main
```

---

## 📝 CÁC LỆNH GIT CƠ BẢN

### Sau Khi Chỉnh Sửa Code

```bash
# Kiểm tra file đã thay đổi
git status

# Thêm tất cả file thay đổi
git add .

# Hoặc thêm file cụ thể
git add src/index.tsx

# Commit với message
git commit -m "Cập nhật thông tin liên hệ"

# Push lên GitHub
git push origin main
```

### Kiểm Tra Lịch Sử

```bash
# Xem commit history
git log --oneline

# Xem thay đổi chưa commit
git diff
```

### Quản Lý Remote

```bash
# Xem remote hiện tại
git remote -v

# Xóa remote
git remote remove origin

# Đổi URL remote
git remote set-url origin https://github.com/NEW_USERNAME/NEW_REPO.git
```

---

## 🌐 DEPLOY LÊN GITHUB PAGES (Tùy chọn)

**Lưu ý:** GitHub Pages chỉ phù hợp với static sites. Với Hono app, nên dùng **Cloudflare Pages** (xem phần dưới).

### Nếu Muốn Thử GitHub Pages:

1. Vào Settings → Pages
2. Source: Deploy from a branch
3. Branch: `main`, folder: `/ (root)`
4. Save

URL: `https://YOUR_USERNAME.github.io/biolink-batdongsan/`

---

## ☁️ DEPLOY LÊN CLOUDFLARE PAGES (KHUYÊN DÙNG!)

Cloudflare Pages miễn phí, nhanh hơn và hỗ trợ Hono app tốt hơn!

### Bước 1: Đăng Ký Cloudflare

Nếu chưa có tài khoản, đăng ký tại: https://dash.cloudflare.com/sign-up

### Bước 2: Cài Wrangler CLI

```bash
npm install -g wrangler
```

### Bước 3: Đăng Nhập

```bash
wrangler login
```

Trình duyệt sẽ mở, đăng nhập Cloudflare và cho phép.

### Bước 4: Build Dự Án

```bash
npm run build
```

### Bước 5: Deploy

```bash
wrangler pages deploy dist --project-name biolink-batdongsan
```

Hoặc đơn giản hơn:

```bash
npm run deploy
```

### Bước 6: Nhận URL

Sau khi deploy thành công, bạn sẽ nhận được URL:
- Production: `https://biolink-batdongsan.pages.dev`
- Preview: `https://xxx.biolink-batdongsan.pages.dev`

---

## 🔄 QUY TRÌNH LÀM VIỆC HÀNG NGÀY

```bash
# 1. Chỉnh sửa code
# (Mở file src/index.tsx, đổi số điện thoại, link Facebook, v.v.)

# 2. Test local
npm run build
pm2 restart biolink-batdongsan
# Truy cập: http://localhost:3000

# 3. Commit thay đổi
git add .
git commit -m "Cập nhật số điện thoại mới"

# 4. Push lên GitHub
git push origin main

# 5. Deploy lên Cloudflare (nếu muốn)
npm run deploy
```

---

## ❓ TROUBLESHOOTING (Xử Lý Lỗi)

### Lỗi: "remote origin already exists"
```bash
git remote remove origin
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
```

### Lỗi: "failed to push some refs"
```bash
# Pull code mới nhất trước
git pull origin main --allow-unrelated-histories

# Sau đó push lại
git push origin main
```

### Lỗi: Authentication failed
- Kiểm tra lại Personal Access Token
- Hoặc thử SSH key

### Lỗi: Permission denied
```bash
# Với HTTPS: Kiểm tra token
# Với SSH: Kiểm tra SSH key đã add vào GitHub chưa
```

### Muốn Xóa Commit Cuối Cùng
```bash
# Xóa commit nhưng giữ thay đổi
git reset --soft HEAD~1

# Xóa commit và thay đổi
git reset --hard HEAD~1
```

---

## 📚 TÀI NGUYÊN HỌC THÊM

- **Git Documentation**: https://git-scm.com/doc
- **GitHub Guides**: https://guides.github.com/
- **Cloudflare Pages Docs**: https://developers.cloudflare.com/pages/

---

## ✅ CHECKLIST HOÀN THÀNH

- [ ] Đã tạo tài khoản GitHub
- [ ] Đã tạo Personal Access Token hoặc SSH Key
- [ ] Đã tạo repository trên GitHub
- [ ] Đã push code thành công
- [ ] Đã test trên GitHub (xem code đã lên chưa)
- [ ] (Tùy chọn) Đã deploy lên Cloudflare Pages
- [ ] Đã lưu lại các URLs quan trọng

---

**🎉 CHÚC MỪNG! Bạn đã hoàn thành việc đẩy code lên GitHub!**

Nếu gặp vấn đề, hãy đọc lại phần Troubleshooting hoặc Google lỗi cụ thể.

---

**Made with ❤️ for Real Estate Professionals**
