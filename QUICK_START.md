# ⚡ QUICK START - BẮT ĐẦU NHANH

> Hướng dẫn deploy bản dịch lên GitHub trong 10 phút!

---

## 🎯 3 BƯỚC CƠ BẢN

```
1. Tạo GitHub Repo
   ↓
2. Upload code
   ↓
3. Bật GitHub Pages
   ↓
4. Config Extension
   ↓
5. Chơi game! 🎮
```

---

## 📝 BƯỚC 1: TẠO GITHUB REPO

1. **Truy cập**: https://github.com/new

2. **Điền**:
   - Repository name: `DeepOne_translate_VN`
   - ☑️ **Public** (QUAN TRỌNG!)
   - ☐ Các checkbox khác bỏ qua

3. **Click "Create repository"**

✅ Copy URL repo: `https://github.com/YOUR_USERNAME/DeepOne_translate_VN`

---

## 📦 BƯỚC 2: UPLOAD CODE

### CÁCH NHANH NHẤT: GitHub Desktop

1. **Tải**: https://desktop.github.com/

2. **Đăng nhập** GitHub

3. **Add folder này**:
   - File → Add Local Repository
   - Browse: `DeepOne_translate_VN_Project`
   - Nếu báo lỗi → Click "Create repository"

4. **Commit**:
   - Summary: `Initial commit`
   - Click **Commit to main**

5. **Publish**:
   - Click **Publish repository**
   - Repository name: `DeepOne_translate_VN`
   - ☐ **Keep private** (BỎ TICK!)
   - Click **Publish**

✅ **Code đã lên GitHub!**

---

## 🌐 BƯỚC 3: BẬT GITHUB PAGES

1. **Vào repo**: https://github.com/YOUR_USERNAME/DeepOne_translate_VN

2. **Settings** (tab trên) → **Pages** (menu trái)

3. **Source**:
   - Branch: `main`
   - Folder: `/ (root)`
   - Click **Save**

4. **Đợi 2 phút** → Refresh page

5. **Thấy**: `✅ Your site is live at https://YOUR_USERNAME.github.io/DeepOne_translate_VN/`

✅ **GitHub Pages đã sống!**

---

## 🔧 BƯỚC 4: CONFIG EXTENSION

### A. Cài Redirector

**Chrome**: https://chrome.google.com/webstore/detail/redirector/ocgpenflpmgnfapjedencafcfakcekcd

### B. Sửa config file

1. **Mở `Redirector_online.json` bằng Notepad**

2. **Ctrl + H** (Find & Replace):
   - Find: `your-github-username`
   - Replace: `YOUR_USERNAME` (username GitHub thật của bạn)
   - Replace All

3. **Save file**

### C. Import vào Redirector

1. **Click icon Redirector** → **Edit Redirects**

2. **Import** → Chọn `Redirector_online.json` vừa sửa

3. **OK**

✅ **Extension đã config!**

---

## 🎮 BƯỚC 5: TEST GAME

1. **Mở game**: https://play.games.dmm.co.jp/play/deeponer/

2. **Đăng nhập**

3. **Vào Tutorial** → Xem có tiếng Việt không?

**Nếu thấy tiếng Việt → THÀNH CÔNG! 🎉**

---

## ❌ KHÔNG HOẠT ĐỘNG?

### Test từng bước:

#### 1. Test GitHub Pages:

```
https://YOUR_USERNAME.github.io/DeepOne_translate_VN/js/project.js
```

- ✅ Thấy code JavaScript → OK
- ❌ 404 Not Found → Kiểm tra lại Bước 3

#### 2. Test Extension:

- **F12** → **Network** tab
- Reload game (`Ctrl + R`)
- Tìm `project.js`
- Xem URL có chuyển sang GitHub không?

#### 3. Clear cache:

```
Ctrl + Shift + Delete → Clear cache → Reload game
```

---

## 📚 CHI TIẾT HƠN

Đọc: **[GITHUB_DEPLOY.md](GITHUB_DEPLOY.md)** để biết:
- Hướng dẫn chi tiết từng bước
- Troubleshooting
- Cách dịch thêm nội dung

---

## 🆘 CẦN GIÚP?

### Các file hướng dẫn:

- **[README.md](README.md)** - Tổng quan project
- **[GITHUB_DEPLOY.md](GITHUB_DEPLOY.md)** - Deploy chi tiết
- **[requirements.txt](requirements.txt)** - Dependencies

### Kiểm tra:

```powershell
# Test GitHub Pages
curl https://YOUR_USERNAME.github.io/DeepOne_translate_VN/js/project.js

# Xem file đã dịch
dir download\adv\text\ /s /b | find /c ".txt"
```

---

## ✅ CHECKLIST

Trước khi test game, kiểm tra:

- [ ] Repository đã **Public**
- [ ] GitHub Pages đã bật (`Settings → Pages`)
- [ ] URL `https://YOUR_USERNAME.github.io/DeepOne_translate_VN/js/project.js` hoạt động
- [ ] File `Redirector_online.json` đã thay `your-github-username` → `YOUR_USERNAME`
- [ ] Extension Redirector đã import config
- [ ] Game đã clear cache (`Ctrl + Shift + R`)

**Nếu tất cả ✅ → Chơi game ngay!**

---

<div align="center">

## 🚀 BẮT ĐẦU NGAY!

### Thời gian: ~10 phút

1. Tạo repo (2 phút)
2. Upload code (3 phút)
3. Bật Pages (2 phút)
4. Config Extension (2 phút)
5. Test game (1 phút)

---

**Chúc bạn thành công! 🎉🇻🇳**

</div>

