# 🚀 HƯỚNG DẪN DEPLOY LÊN GITHUB PAGES

## 📋 TÓM TẮT

Hướng dẫn từng bước để host bản dịch trên GitHub Pages và test trong game.

---

## 🎯 CÁC BƯỚC

### ✅ Bước 1: Tạo GitHub Repository

1. **Đăng nhập GitHub**: https://github.com
   - Nếu chưa có tài khoản, đăng ký tại: https://github.com/signup

2. **Tạo repository mới**:
   - Click nút **"+"** góc phải trên → **New repository**
   - Hoặc truy cập: https://github.com/new

3. **Điền thông tin**:
   ```
   Repository name: DeepOne_translate_VN
   Description: Vietnamese translation for DeepOne game
   
   ☑️ Public (QUAN TRỌNG - phải Public để dùng GitHub Pages miễn phí)
   ☐ Add a README file (bỏ qua, ta đã có)
   ☐ Add .gitignore (không cần)
   ☐ Choose a license (không cần)
   ```

4. **Click "Create repository"**

---

### ✅ Bước 2: Upload code lên GitHub

#### **CÁCH 1: Dùng GitHub Desktop (Dễ nhất)**

1. **Tải GitHub Desktop**: https://desktop.github.com/

2. **Cài đặt và đăng nhập**

3. **Add repository**:
   - File → Add Local Repository
   - Choose: `C:\Users\Admin\Downloads\Compressed\DeepOne_translate_CN-main\DeepOne_translate_VN_Project`
   - Nếu báo "not a git repository" → Click "Create a repository"

4. **Commit files**:
   - Trong GitHub Desktop:
   - Summary: `Initial commit - Tutorial + Chapter 1`
   - Description: `Translated 52 files using Google Translate`
   - Click **Commit to main**

5. **Publish repository**:
   - Click **Publish repository**
   - Repository name: `DeepOne_translate_VN`
   - ☐ Keep this code private (BỎ TICK - phải public)
   - Click **Publish repository**

✅ **Done! Code đã lên GitHub!**

---

#### **CÁCH 2: Dùng Git Command Line (Cho dev)**

```bash
# 1. Mở PowerShell trong thư mục project
cd "C:\Users\Admin\Downloads\Compressed\DeepOne_translate_CN-main\DeepOne_translate_VN_Project"

# 2. Khởi tạo git
git init

# 3. Add remote (thay YOUR_USERNAME bằng username GitHub của bạn)
git remote add origin https://github.com/YOUR_USERNAME/DeepOne_translate_VN.git

# 4. Add files
git add .

# 5. Commit
git commit -m "Initial commit - Tutorial + Chapter 1 translation"

# 6. Push
git branch -M main
git push -u origin main
```

Nếu báo lỗi authentication:
```bash
# Tạo Personal Access Token tại:
# https://github.com/settings/tokens
# Permissions: repo (full control)

# Khi git push hỏi password, nhập token thay vì password
```

---

#### **CÁCH 3: Upload qua Web (Đơn giản nhất)**

1. **Vào repo vừa tạo**: https://github.com/YOUR_USERNAME/DeepOne_translate_VN

2. **Click "uploading an existing file"**

3. **Kéo thả các file/folder**:
   - Kéo toàn bộ nội dung trong folder `DeepOne_translate_VN_Project`
   - **LƯU Ý:** GitHub web chỉ upload được tối đa 100 files 1 lần
   - Nếu quá nhiều, chia nhỏ:
     - Lần 1: `download/`, `js/`, `assets/`
     - Lần 2: `image/`, `README.md`, `*.json`

4. **Commit changes**:
   ```
   Commit message: Initial commit - Tutorial + Chapter 1
   ```

5. **Click "Commit changes"**

⚠️ **Cách này không phù hợp nếu có quá nhiều file (>100). Nên dùng Cách 1 hoặc 2.**

---

### ✅ Bước 3: Bật GitHub Pages

1. **Vào Settings**:
   - Repo → **Settings** (tab trên cùng)

2. **Mục Pages** (menu bên trái):
   - Click **Pages**

3. **Cấu hình Source**:
   ```
   Source: Deploy from a branch
   Branch: main
   Folder: / (root)
   ```

4. **Click "Save"**

5. **Đợi 1-2 phút**

6. **Refresh page** → Sẽ thấy thông báo:
   ```
   ✅ Your site is live at https://YOUR_USERNAME.github.io/DeepOne_translate_VN/
   ```

---

### ✅ Bước 4: Kiểm tra GitHub Pages hoạt động

#### Test các URL quan trọng:

1. **Test project.js** (QUAN TRỌNG NHẤT):
   ```
   https://YOUR_USERNAME.github.io/DeepOne_translate_VN/js/project.js
   ```
   - Phải thấy nội dung file JavaScript (167,834 dòng)
   - Nếu thấy "404 Not Found" → Kiểm tra lại folder `js/` đã upload chưa

2. **Test file dịch Tutorial**:
   ```
   https://YOUR_USERNAME.github.io/DeepOne_translate_VN/download/adv/text/tutorial/adultr/600010001.txt
   ```
   - Phải thấy nội dung file text đã dịch tiếng Việt

3. **Test file dịch Chapter 1**:
   ```
   https://YOUR_USERNAME.github.io/DeepOne_translate_VN/download/adv/text/quest/10001/100101001.txt
   ```
   - Phải thấy nội dung file text đã dịch

**Nếu tất cả URL trên hoạt động → GitHub Pages đã sẵn sàng! ✅**

---

### ✅ Bước 5: Cấu hình Browser Extension

#### **CÁCH 1: Redirector (Khuyến nghị)**

1. **Cài extension**:
   - Chrome: https://chrome.google.com/webstore/detail/redirector/ocgpenflpmgnfapjedencafcfakcekcd
   - Firefox: https://addons.mozilla.org/firefox/addon/redirector/

2. **Sửa file config**:
   - Mở `Redirector_online.json` bằng Notepad
   - Tìm và thay `[your-github-username]` bằng username của bạn
   - **VÍ DỤ:** Nếu username là `trungnguyen`:
     ```json
     "redirectUrl": "https://trungnguyen.github.io/DeepOne_translate_VN/..."
     ```

3. **Import vào Redirector**:
   - Click icon Redirector → **Edit Redirects**
   - Click **Import** → Chọn file `Redirector_online.json` đã sửa
   - Click **OK**

4. **Verify**:
   - Trong Redirector, bạn sẽ thấy 2 rules:
     ```
     Rule 1: project.js (tonofura-r-cdn...)
     Rule 2: project.js (tonofura-w-cdn...)
     ```

---

#### **CÁCH 2: Gooreplacer**

1. **Cài extension**:
   - Chrome: https://chrome.google.com/webstore/detail/gooreplacer/jnlkjeecojckkigmchmfoigphmgkgbip

2. **Thêm rules**:
   - Click icon Gooreplacer → **Edit**
   - Paste 2 rules sau (thay `YOUR_USERNAME`):

   ```
   ^https:\/\/tonofura-r-cdn-client\.deepone-online\.com\/client\/[0-9]+\.[0-9]+\.[0-9]+\/src\/project\.js,regex,redirect
   url:https://YOUR_USERNAME.github.io/DeepOne_translate_VN/js/project.js
   
   ^https:\/\/tonofura-w-cdn-client\.deepone-online\.com\/client\/[0-9]+\.[0-9]+\.[0-9]+\/src\/project\.js,regex,redirect
   url:https://YOUR_USERNAME.github.io/DeepOne_translate_VN/js/project.js
   ```

3. **Click "Save"**

---

### ✅ Bước 6: Test trong game

1. **Mở game**:
   - PC: https://play.games.dmm.co.jp/play/deeponer/
   - Mobile: https://sp-play.games.dmm.co.jp/play/deeponer/

2. **Đăng nhập**

3. **Kiểm tra Tutorial**:
   - Tạo tài khoản mới hoặc vào Tutorial
   - Nếu thấy **tiếng Việt** → **THÀNH CÔNG!** 🎉

4. **Kiểm tra Chapter 1**:
   - Vào Main Quest → Chapter 1
   - Kiểm tra dialogue có tiếng Việt không

---

## 🐛 TROUBLESHOOTING

### ❌ Lỗi 1: GitHub Pages hiển thị 404

**Nguyên nhân:** Pages chưa được bật hoặc đang build

**Cách fix:**
1. Vào repo → **Settings** → **Pages**
2. Kiểm tra `Source` đã chọn đúng `main` branch chưa
3. Đợi thêm 2-3 phút
4. Hard refresh: `Ctrl + Shift + R`

---

### ❌ Lỗi 2: File project.js không load được

**Nguyên nhân:** File quá lớn (>25MB) hoặc path sai

**Cách fix:**
1. Kiểm tra URL:
   ```
   https://YOUR_USERNAME.github.io/DeepOne_translate_VN/js/project.js
   ```
2. Kiểm tra file `js/project.js` có trong repo không
3. Nếu file quá lớn:
   - GitHub Pages free có giới hạn 100MB/repo
   - Nén file hoặc dùng Git LFS

---

### ❌ Lỗi 3: Game vẫn hiện tiếng Trung/Nhật

**Nguyên nhân:** Extension chưa hoạt động hoặc chưa config đúng

**Cách fix:**
1. **Kiểm tra extension đã bật chưa:**
   - Click icon extension → Xem có "Enabled" không

2. **Kiểm tra rules:**
   - Redirector: Edit Redirects → Xem có 2 rules không
   - Gooreplacer: Edit → Xem có 2 rules không

3. **Clear cache:**
   - `Ctrl + Shift + Delete` → Clear cache
   - Reload game: `Ctrl + R`

4. **Test bằng DevTools:**
   - `F12` → **Network** tab
   - Reload game
   - Tìm `project.js`
   - Xem có redirect sang GitHub Pages không?

---

### ❌ Lỗi 4: Một số dialogue vẫn chưa dịch

**Nguyên nhân:** Chỉ dịch Tutorial + Chapter 1, phần khác chưa dịch

**Cách fix:**
- Đây là bình thường! Bạn mới dịch 52/7,628 file (0.68%)
- Để dịch thêm, chạy script với file khác:
  ```bash
  python translate_tutorial_chapter1.py
  ```

---

### ❌ Lỗi 5: Git push bị lỗi authentication

**Nguyên nhân:** GitHub không cho dùng password nữa, phải dùng token

**Cách fix:**
1. Tạo Personal Access Token:
   - https://github.com/settings/tokens
   - **Generate new token (classic)**
   - Permissions: ☑️ `repo` (full control)
   - Expiration: `90 days` hoặc `No expiration`
   - Copy token (chỉ hiện 1 lần!)

2. Khi git push hỏi password:
   - Username: `YOUR_USERNAME`
   - Password: `<paste token ở đây>`

3. Lưu credential:
   ```bash
   git config --global credential.helper store
   ```

---

## 📊 KIỂM TRA CUỐI CÙNG

### Checklist:

- ✅ Repository đã public
- ✅ GitHub Pages đã bật
- ✅ URL `https://YOUR_USERNAME.github.io/DeepOne_translate_VN/js/project.js` hoạt động
- ✅ URL file .txt hoạt động
- ✅ Extension đã cài và config đúng username
- ✅ Game hiển thị tiếng Việt ở Tutorial

**Nếu tất cả đều ✅ → BẠN ĐÃ THÀNH CÔNG! 🎉**

---

## 🎯 BƯỚC TIẾP THEO

### 1. Dịch thêm nội dung

```bash
# Chỉnh sửa script để dịch chapter khác
python translate_tutorial_chapter1.py
```

### 2. Hiệu đính bằng tay

- Mở file .txt đã dịch
- Sửa các chỗ dịch sai/khó hiểu
- Commit lên GitHub:
  ```bash
  git add .
  git commit -m "Fix translation for tutorial"
  git push
  ```

### 3. Chia sẻ với cộng đồng

- Share link repo trên forum/group game
- Mời người khác contribute

---

## 🔄 CẬP NHẬT BẢN DỊCH SAU NÀY

Mỗi khi dịch thêm file mới:

### Cách 1: GitHub Desktop
1. Mở GitHub Desktop
2. Các file mới sẽ hiện trong "Changes"
3. Commit: `Add translation for chapter X`
4. Click **Push origin**
5. Đợi 1-2 phút → GitHub Pages tự động update

### Cách 2: Git Command
```bash
git add .
git commit -m "Add chapter 2 translation"
git push
```

### Cách 3: Web upload
1. Vào repo trên GitHub
2. Upload file mới
3. Commit changes

---

## 📞 HỖ TRỢ

Nếu gặp vấn đề:

1. **Đọc lại phần Troubleshooting**
2. **Kiểm tra GitHub Pages status**:
   - Repo → **Actions** → Xem có lỗi không
3. **Tạo Issue**:
   - https://github.com/YOUR_USERNAME/DeepOne_translate_VN/issues

---

<div align="center">

## 🎉 CHÚC MỪNG!

**Bạn đã hoàn thành việc deploy bản dịch lên GitHub Pages!**

---

### 🎮 BÂY GIỜ HÃY CHƠI GAME VÀ KIỂM TRA!

https://play.games.dmm.co.jp/play/deeponer/

---

**Nếu thấy hữu ích, đừng quên cho repo 1 ⭐ Star!**

</div>

