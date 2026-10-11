# Ms Trâm English Hub · Ôn Từ Vựng THPTQG & ĐGNL

Ứng dụng web ôn tập từ vựng tiếng Anh chuyên đề cho học sinh luyện thi THPTQG và ĐGNL, thiết kế riêng cho **Ms Trâm English Hub**. Chạy trực tiếp trên trình duyệt, không cần cài đặt phần mềm, dùng mượt mà cả trên điện thoại lẫn máy tính.

---

## 👩‍🏫 HƯỚNG DẪN DÀNH CHO CÔ TRÂM (Đọc là làm được ngay)

### 1. Cách mở ứng dụng để dạy học hoặc cho học sinh dùng
* **Dùng trên máy tính:** Chỉ cần **nhấp đúp chuột vào file `index.html`**. Trang web sẽ tự mở trên trình duyệt (Chrome, Cốc Cốc, Edge). Hoàn toàn không cần nối mạng Internet, không cần cài đặt gì thêm.
* **Dùng trên điện thoại:** Khi cô đưa lên mạng (xem mục 4 bên dưới), học sinh chỉ cần mở đường link trên điện thoại là học được ngay.

---

### 2. Cách tạo một bộ từ vựng mới (Chỉ 4 bước đơn giản)

Cô không cần biết viết code, chỉ cần làm theo 4 bước sau:

* **Bước 1: Soạn từ vựng trên Excel hoặc Google Sheets**
  * Bảng gồm các cột quen thuộc: `Từ vựng | Phiên âm | Từ loại | Nghĩa tiếng Việt | Bài số | Câu ví dụ | Dạng từ đúng | Từ đồng nghĩa | Từ trái nghĩa`.
  * *(Mẹo: Thứ tự cột thế nào cũng được, hệ thống sẽ tự nhận diện thông minh).*

* **Bước 2: Mở công cụ nhập liệu**
  * Nhấp đúp mở file `studio.html` trên máy tính (hoặc bấm chữ **"Teacher Studio"** ở cuối trang `index.html`).

* **Bước 3: Dán bảng và kiểm tra**
  * Quét chọn toàn bộ bảng trên Excel, nhấn `Ctrl + C` (Sao chép).
  * Sang trang `studio.html`, nhấn `Ctrl + V` (Dán) vào ô lớn rồi bấm nút **"Kiểm tra & Tạo dữ liệu"**.
  * Cô điền thêm tên chủ đề (ví dụ: *Environment & Green Energy*).

* **Bước 4: Lưu vào web để học sinh thấy ngay**
  * Bấm nút **"💾 Tải về file .js"** và lưu file vào thư mục: `data/topics/` (ví dụ đặt tên là `environment.js`).
  * Mở file `index.html` bằng Notepad, kéo xuống dòng cuối cùng và thêm 1 dòng nạp file:
    ```html
    <script src="data/topics/environment.js"></script>
    ```
  * Nhấn `Ctrl + S` để lưu `index.html`. Xong! Mở lại `index.html` là cô và học sinh sẽ thấy chuyên đề mới xuất hiện ngay trên nút chọn chủ đề.

---

### 3. Tóm tắt các tính năng học tập cho học sinh

* 📇 **Thẻ ghi nhớ (Flashcards):** Nhấp vào thẻ để lật xem nghĩa, phát âm giọng chuẩn. Có nút **`▶ Tự động`** để thẻ tự đọc và tự lật rảnh tay.
* ❓ **Trắc nghiệm 4 lựa chọn:** 10 câu hỏi ngẫu nhiên bám sát đề thi. Bấm phím `1, 2, 3, 4` hoặc `A, B, C, D` trên máy tính để chọn nhanh.
* ✏️ **Điền từ vào câu:** Luyện ngữ cảnh bài đọc thực tế với câu trích dẫn chuẩn đề thi.
* ⌨️ **Luyện gõ từ (Chính tả):** Nghe phát âm, xem nghĩa tiếng Việt rồi gõ từ vào ô để tránh bị sai chính tả khi làm bài thi.
* ⚡ **Ghép từ phản xạ:** Trò chơi nối nhanh 5 từ tiếng Anh với 5 nghĩa tiếng Việt có đồng hồ bấm giờ tính giây.
* 📋 **Danh sách từ & In ấn:** Xem toàn bộ từ vựng; có nút **`🖨️ In / Lưu PDF`** để tự động dàn trang 2 cột A4 in ra giấy phát cho cả lớp.
* ⭐ **Từ vựng gắn sao:** Bấm ngôi sao trên từ để lưu lại các từ khó nhớ và luyện tập riêng nhóm từ này.
* 📸 **Báo cáo kết quả gửi Zalo:** Làm xong bài có nút bấm tự sao chép kết quả (kèm điểm số và các từ làm sai) để học sinh dán gửi thẳng vào Zalo cô.
* 📞 **Hotline & Zalo:** Bấm vào số điện thoại trên web là hệ thống tự copy số để dán vào Zalo tiện lợi.

---

### 4. Cách đưa trang web lên mạng miễn phí (GitHub Pages)

Để cả lớp có thể mở link học trên điện thoại mọi lúc mọi nơi:
1. Đăng tải toàn bộ thư mục này lên tài khoản GitHub của cô (hoặc nhờ người hỗ trợ đẩy mã nguồn lên).
2. Vào mục **Settings** của kho mã nguồn trên GitHub > chọn mục **Pages** ở cột bên trái.
3. Ở phần **Branch**, chọn nhánh `main` (thư mục `/root`) rồi bấm **Save**.
4. Chờ khoảng 1 phút, GitHub sẽ cung cấp cho cô một đường link miễn phí (ví dụ: `https://ten-cua-co.github.io/thptqg-tuvung-career/`). Cô chỉ cần gửi link này vào nhóm Zalo lớp là học sinh vào học được ngay!

---

## 📁 Cấu trúc thư mục dự án

```text
thptqg-tuvung-career/
├── index.html          # Trang học tập chính dành cho học sinh
├── studio.html         # Công cụ nhập từ vựng từ Excel dành cho cô giáo
├── 404.html            # Trang báo lỗi đường dẫn tự động chuyển về trang chủ
├── .nojekyll           # File cấu hình giúp GitHub Pages chạy mượt mà 100%
├── assets/
│   └── logo.svg        # Logo thương hiệu Ms Trâm English Hub
├── css/
│   ├── style.css       # Giao diện trang học tập (Dark/Light mode, Mobile bottom bar)
│   └── studio.css      # Giao diện công cụ nhập liệu cho cô giáo
├── data/
│   └── topics/         # Thư mục chứa các bộ từ vựng (Định dạng Markdown / JS)
│       ├── career.js   # Bộ từ Career Paths & Future Jobs
│       └── environment.js # Bộ từ Environment & Green Energy
└── js/
    ├── parser.js       # Bộ giải mã bảng Markdown thông minh
    ├── data.js         # Bộ quản lý nạp đa chuyên đề
    ├── app.js          # Logic học tập (Thẻ nhớ, Trắc nghiệm, Điền từ, Gõ từ, Ghép từ)
    └── studio.js       # Logic nhận diện bảng Excel tự động
```

---

## 📍 Thông tin trung tâm & 2 Cơ sở học

* **Cơ sở 1:** 12 Lê Đình Chinh – Quy Nhơn Nam, Gia Lai
* **Cơ sở 2:** 32 Chu Văn An – Quy Nhơn, Gia Lai
* **Hotline tư vấn:** 0898 123 696
* **Zalo cô Trâm:** 0792 951 529
* **Fanpage Facebook:** [Ms Trâm English Class](https://www.facebook.com/mstramengclass)
