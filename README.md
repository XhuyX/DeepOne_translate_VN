# 🎮 DeepOne Bản Dịch Tiếng Việt

> Vietnamese Translation Project for DeepOne Game

## 📖 Giới thiệu

Bản dịch tiếng Việt cho game **DeepOne** - một visual novel/RPG về thế giới Cthulhu Mythos.

---

## 🚀 HƯỚNG DẪN CHO NGƯỜI DÙNG

### Bước 1: Cài Extension

Chọn 1 trong 2 extension sau:

**Redirector (Khuyến nghị):**
- Chrome: https://chrome.google.com/webstore/detail/redirector/ocgpenflpmgnfapjedencafcfakcekcd
- Firefox: https://addons.mozilla.org/firefox/addon/redirector/

**Gooreplacer:**
- Chrome: https://chrome.google.com/webstore/detail/gooreplacer/jnlkjeecojckkigmchmfoigphmgkgbip

### Bước 2: Nhập cấu hình

#### Với Redirector:

1. Tải file: [Redirector_online.json](Redirector_online.json)
2. Mở extension Redirector → **Edit Redirects**
3. Click **Import** → Chọn file vừa tải
4. Done!

#### Với Gooreplacer:

1. Mở extension → Click **Edit**
2. Dán cấu hình sau vào:

```
^https:\/\/tonofura-r-cdn-client\.deepone-online\.com\/client\/[0-9]+\.[0-9]+\.[0-9]+\/src\/project\.js,regex,redirect
url:https://xhuy.github.io/DeepOne_translate_VN/js/project.js

^https:\/\/tonofura-w-cdn-client\.deepone-online\.com\/client\/[0-9]+\.[0-9]+\.[0-9]+\/src\/project\.js,regex,redirect
url:https://xhuy.github.io/DeepOne_translate_VN/js/project.js
```

3. Click **Save**

### Bước 3: Chơi game

- **PC**: https://play.games.dmm.co.jp/play/deeponer/
- **Mobile**: https://sp-play.games.dmm.co.jp/play/deeponer/

Game sẽ tự động load bản dịch tiếng Việt!

---

## 📊 Tiến độ dịch

| Phần | Số file | Tiến độ | Trạng thái |
|------|---------|---------|------------|
| Tutorial | 18 | 100% | ✅ Hoàn thành |
| Prologue & Chapter 1 | 34 | 100% | ✅ Hoàn thành |
| Main Quest | ~2000 | 0% | ⏳ Chưa bắt đầu |
| Character Stories | ~3000 | 0% | ⏳ Chưa bắt đầu |
| Events | ~1500 | 0% | ⏳ Chưa bắt đầu |
| Gacha | ~20 | 0% | ⏳ Chưa bắt đầu |

**Tổng cộng: 52/7,628 file (0.68%)**

> ⚠️ **Lưu ý:** Đây là bản dịch máy sơ bộ từ Google Translate. Cần hiệu đính thủ công để cải thiện chất lượng.

---

## 🤝 Đóng góp

### Muốn giúp dịch?

1. Fork repo này
2. Chọn file cần dịch trong thư mục `download/`
3. Dịch theo hướng dẫn trong `docs/HUONG_DAN_DICH.md`
4. Tạo Pull Request

### Báo lỗi:

Tạo [Issue](../../issues) với thông tin:
- File nào bị lỗi
- Lỗi gì (dịch sai, lỗi hiển thị, etc.)
- Screenshot nếu có

---

## 🛠️ HƯỚNG DẪN CHO DEVELOPER

Xem thư mục `docs/` để biết chi tiết:

- **[SETUP.md](docs/SETUP.md)** - Thiết lập môi trường
- **[PROJECT_STRUCTURE.md](docs/PROJECT_STRUCTURE.md)** - Cấu trúc project
- **[TRANSLATION_GUIDE.md](docs/TRANSLATION_GUIDE.md)** - Hướng dẫn dịch
- **[DEPLOYMENT.md](docs/DEPLOYMENT.md)** - Deploy lên GitHub Pages

### Quick Start cho Dev:

```bash
# Clone repo
git clone https://github.com/[username]/DeepOne_translate_VN.git
cd DeepOne_translate_VN

# Cài dependencies
pip install -r requirements.txt

# Dịch file test
python tools/translate.py download/adv/text/tutorial/adultr/600010001.txt

# Generate MD5
python tools/generate_md5.py download

# Commit
git add .
git commit -m "Translate tutorial 600010001"
git push
```

---

## 📁 Cấu trúc Project

```
DeepOne_translate_VN/
│
├── download/              # File dịch
│   └── adv/text/
│       ├── quest/         # Nhiệm vụ
│       ├── character/     # Nhân vật
│       ├── event/         # Sự kiện
│       └── tutorial/      # Hướng dẫn
│
├── js/
│   └── project.js         # ⭐ FILE QUAN TRỌNG - Game code
│
├── assets/
│   └── fonts/             # Font chữ
│
├── tools/                 # Scripts hỗ trợ
│   ├── translate.py       # Dịch tự động
│   ├── generate_md5.py    # Tạo checksum
│   └── validate.py        # Kiểm tra lỗi
│
├── docs/                  # Tài liệu
│   ├── SETUP.md
│   ├── TRANSLATION_GUIDE.md
│   └── ...
│
├── Redirector_online.json # Config Redirector
├── gooreplacer.json      # Config Gooreplacer
├── md5.json              # File checksum
└── README.md             # File này
```

---

## ⚙️ Cơ chế hoạt động

### Sơ đồ:

```
┌──────────────┐
│   Browser    │ Game request file
└──────┬───────┘
       │
       ▼
┌──────────────────────────────────────┐
│  Browser Extension                   │
│  (Redirector / Gooreplacer)          │
│                                       │
│  Chặn: cdn.deepone-online.com/...    │
│  Chuyển: github.io/DeepOne_VN/...    │
└──────────────┬───────────────────────┘
               │
               ▼
┌──────────────────────────────────────┐
│  GitHub Pages                         │
│  Load file dịch tiếng Việt           │
└──────────────┬───────────────────────┘
               │
               ▼
┌──────────────────────────────────────┐
│  Game hiển thị tiếng Việt            │
└──────────────────────────────────────┘
```

### Chi tiết:

1. **Extension chặn request** tới file `project.js` gốc
2. **Redirect** sang `project.js` đã modified trên GitHub
3. **project.js mới** chứa code redirect các file text
4. **Game load file .txt** đã dịch từ GitHub Pages

**⚠️ QUAN TRỌNG:** File `js/project.js` là file game gốc (167,834 dòng) đã được modify để redirect. Không được xóa file này!

---

## 🔧 Tools

Trong thư mục `tools/`:

### 1. translate.py
Dịch file tự động

```bash
# Dịch 1 file
python tools/translate.py input.txt -o output.txt

# Dịch cả thư mục
python tools/translate.py input_dir/ -o output_dir/

# Dùng API khác
python tools/translate.py input.txt -a claude -k YOUR_API_KEY
```

### 2. generate_md5.py
Tạo checksum tracking

```bash
python tools/generate_md5.py download -o md5.json
```

### 3. validate.py
Kiểm tra lỗi format

```bash
python tools/validate.py download/
```

---

## 📜 Credits

### Translator Team:
- [Tên bạn] - Lead Translator
- [Contributor 1]
- [Contributor 2]

### Based on:
- **DeepOne_translate_CN** by lisanjin & team
- Method from [IrisMysteria-Translate](https://github.com/game-reverse/IrisMysteria-Translate)

### Tools:
- **GalTransl** by cx2333-gt
- **Claude AI** / **GPT-4** - Machine Translation
- **GitHub Pages** - Free Hosting

### Special Thanks:
- Cộng đồng dịch thuật game Việt Nam
- Beta testers
- Contributors

---

## ⚠️ Disclaimer

Project này được tạo ra cho mục đích **học tập và nghiên cứu**.

- ❌ Không sử dụng cho mục đích thương mại
- ✅ Hỗ trợ nhà phát hành bằng cách mua game chính thức
- ✅ Tôn trọng bản quyền của DMM Games

Tác giả không chịu trách nhiệm về việc sử dụng project này.

---

## 📞 Liên hệ

- **GitHub Issues**: [Report bugs](../../issues)
- **Discussions**: [Join discussion](../../discussions)
- **Email**: your-email@example.com
- **Discord/Telegram**: [Link nếu có]

---

## 📝 License

Chỉ dùng cho mục đích học tập và nghiên cứu. Không thương mại.

---

<div align="center">

**Chúc bạn chơi game vui vẻ! 🎮🇻🇳**

*Nếu project hữu ích, đừng quên cho 1 ⭐ Star!*

[⬆️ Back to Top](#-deepone-bản-dịch-tiếng-việt)

</div>





