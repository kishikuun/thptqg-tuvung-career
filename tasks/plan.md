# Kế Hoạch Nâng Cấp Toàn Diện: Ứng Dụng Ôn Từ Vựng THPTQG (Ms Trâm English Hub)

## 1. Tổng quan dự án & Mục tiêu (Overview)
Nâng cấp ứng dụng ôn từ vựng tĩnh hiện tại từ quy mô **1 chủ đề đơn lẻ** thành **Hệ thống ôn luyện từ vựng đa chủ đề (Multi-Topic Vocab Hub)** chuyên sâu cho kỳ thi THPTQG & ĐGNL. 
Mục tiêu cốt lõi:
1. **Dễ dàng cho cô giáo (10/10 Convenience):** Cung cấp công cụ hỗ trợ giáo viên nhập từ vựng từ Excel / Google Sheets một cách trực quan, không cần biết lập trình, không sợ lỗi cú pháp code, xuất ra file dữ liệu tức thì.
2. **Hiệu quả tối đa cho học sinh (High Learning Efficiency):** Thêm các chế độ học tập thông minh (Luyện gõ từ vựng, Gom từ hay sai để ôn tập trọng tâm, Sao chép kết quả gửi Zalo nhanh chóng, Âm thanh phản hồi trực quan).
3. **Giữ nguyên tắc web tĩnh 100% (Pure Static Website):** Chạy trực tiếp mọi lúc mọi nơi bằng cách nhấp đúp file `index.html` hoặc tải lên GitHub Pages / Vercel không cần backend hay database phức tạp.
4. **Giao diện tinh tế & không rối rắm (Clean UI/UX):** Phân cấp thông tin mạch lạc, tối ưu chuẩn Mobile First, Tablet và PC.

---

## 2. Kiến trúc & Giải pháp kỹ thuật (Architecture Decisions)

### 2.1. Kiến trúc dữ liệu Đa chủ đề (Multi-Topic Architecture)
Chuyển đổi dữ liệu từ dạng phẳng 1 chủ đề sang cấu trúc quản lý đa chủ đề linh hoạt:
```text
thptqg-tuvung-career/
├── index.html                  # Giao diện học tập chính
├── studio.html                 # Công cụ nhập từ vựng cho cô giáo (Teacher Studio)
├── css/
│   ├── style.css               # Giao diện chính, theme, dark mode, responsive
│   └── studio.css              # Giao diện công cụ nhập liệu
├── js/
│   ├── data.js                 # Chỉ mục các chủ đề (Topics Index) & bộ từ vựng
│   ├── app.js                  # Logic ứng dụng học tập
│   └── studio.js               # Logic chuyển đổi từ Excel -> Dữ liệu web
└── assets/
    └── logo.svg                # Logo và biểu tượng
```

Cấu trúc đối tượng dữ liệu trong `js/data.js`:
```javascript
const TOPICS = {
  "career": {
    id: "career",
    title: "Career Paths & Future Jobs",
    eyebrow: "Education & Careers · B2 – C1 · Practice Test 01",
    desc: "Ôn từ vựng trọng tâm từ 4 bài đọc: AI và việc làm sinh viên, kỹ năng xanh, tương lai việc làm 2030, tuyển dụng theo kỹ năng.",
    passages: { 1: "AI & graduate jobs", 2: "Green skills", 3: "Future of jobs 2030", 4: "Skills-based hiring" },
    clusters: [ ... ],
    words: [ ... ]
  },
  "environment": {
    id: "environment",
    title: "Environment & Green Energy",
    eyebrow: "Global Warming · Biodiversity · Practice Test 02",
    ...
  }
};
```

### 2.2. Giải pháp cho cô giáo: "Teacher Vocab Studio" (Công cụ nhập liệu không cần code)
- **Vấn đề của cô giáo:** Không quen viết code JavaScript, dễ bị lỗi thiếu dấu phẩy `,`, dấu ngoặc nhọn `{}` hay ngoặc kép `"`.
- **Giải pháp:** Tích hợp file công cụ `studio.html` ngay trong dự án.
  - Cô giáo chỉ cần chuẩn bị file Excel / Google Sheets với các cột đơn giản: `Từ | Phiên âm | Từ loại | Nghĩa tiếng Việt | Bài số | Câu ví dụ | Dạng chia đúng | Đồng nghĩa | Trái nghĩa`.
  - Cô giáo copy toàn bộ bảng trong Excel và dán thẳng vào ô văn bản trên `studio.html` (hỗ trợ phân tách Tab của Excel tự động).
  - Bấm nút **"Kiểm tra & Tạo dữ liệu"** -> Hệ thống hiển thị bảng xem trước (Preview) trực quan các thẻ từ vựng và nấc thang tiến độ.
  - Bấm nút **"Tải về file data.js"** hoặc **"Sao chép mã"** -> Cô chỉ cần chép đè vào thư mục `js/` là website tự động cập nhật chủ đề mới ngay lập tức!

### 2.3. Các tính năng mới cho học sinh (Đảm bảo 100% dễ dùng, không rối mắt)
1. **Bộ chọn chủ đề dạng Card/Modal nhẹ nhàng (Topic Selector):**
   - Học sinh có thể bấm vào tiêu đề chủ đề để mở danh sách chọn chủ đề ôn thi với nấc thang tiến độ riêng cho từng chủ đề.
2. **Chế độ Luyện gõ từ vựng (Spelling & Dictation Practice):**
   - Cực kỳ hữu ích cho kỳ thi THPTQG để học sinh không bị mất điểm chính tả trong bài viết hoặc bài điền từ.
   - Hiển thị nghĩa, nghe phát âm, học sinh gõ từ tiếng Anh vào ô nhập -> Kiểm tra tức thì.
3. **Bộ lọc "Từ cần ôn gấp" (Weak Words Focus):**
   - Tự động ghi nhớ các từ mà học sinh đã chọn sai trong các bài Quiz hoặc Gap-fill.
   - Thêm nút lọc nhanh `[Chỉ ôn từ hay sai]` bên cạnh các nút chọn bài đọc để học sinh ôn trúng trọng tâm.
4. **Nút "Sao chép báo cáo kết quả gửi Zalo" (One-Click Zalo Report):**
   - Ngoài việc chụp màn hình vé điểm, học sinh có nút bấm sao chép sẵn đoạn tin nhắn:
     `"Em: Nguyễn Thị Lan - Lớp 12A1 nộp bài trắc nghiệm Chủ đề: Career Paths. Kết quả: 9/10 (90%). Thời gian làm: 3 phút 15 giây. Từ làm sai: obsolete, culprit."`
   - Gửi Zalo cho cô giáo cực kỳ tiện lợi và nhanh chóng.
5. **Âm thanh phản hồi & Nút Tắt/Bật âm thanh (Sound Effects & Mute Toggle):**
   - Hiệu ứng âm thanh vui nhộn, êm dịu khi trả lời đúng / sai, có biểu tượng chiếc loa để bật/tắt khi học ở thư viện hoặc ban đêm.
6. **Nút gạt Sáng / Tối (Dark / Light Theme Toggle):**
   - Đặt ở góc phải header, cho phép học sinh chủ động đổi màu giao diện phù hợp với mắt mà không cần đổi cài đặt máy tính.

---

## 3. Danh sách các giai đoạn triển khai (Phased Implementation Plan)

### Giai đoạn 1: Kiến trúc Đa chủ đề & Nâng cấp mô hình dữ liệu
- [x] Chuyển đổi mô hình dữ liệu sang cấu trúc `TOPICS` linh hoạt, giữ nguyên vẹn 100% dữ liệu chủ đề Career hiện tại.
- [x] Bổ sung cơ chế chọn chủ đề đang học (Active Topic), lưu chủ đề đã chọn vào `localStorage`.
- [x] Nâng cấp nấc thang tiến độ (Ladder Progress) thích ứng tự động theo từng chủ đề.

### Giai đoạn 2: Xây dựng công cụ "Teacher Vocab Studio" (studio.html)
- [x] Thiết kế trang `studio.html` với giao diện chuyên nghiệp, thanh lịch, dễ dùng cho giáo viên.
- [x] Tạo parser thông minh nhận diện dữ liệu copy-paste từ Excel / Google Sheets / CSV.
- [x] Tích hợp bộ kiểm tra lỗi tự động (báo rõ dòng nào bị thiếu nghĩa hoặc thiếu câu ví dụ).
- [x] Tạo nút "Xuất file data.js" tự động tải file về máy.

### Giai đoạn 3: Bổ sung các tính năng nâng cao cho học sinh
- [x] Thêm Tab chế độ thứ 5: "Luyện gõ từ vựng" (Spelling / Dictation).
- [x] Thêm tính năng lưu danh sách từ hay làm sai và nút lọc "Ôn từ hay sai".
- [x] Thêm nút "Sao chép kết quả gửi Zalo" tại phiếu điểm (Ticket).
- [x] Thêm nút gạt chế độ Sáng/Tối chủ động (Theme Switcher).
- [x] Tích hợp hiệu ứng âm thanh Web Audio API (không phụ thuộc file ngoài) + nút Mute.
- [x] Tích hợp bản đồ Google Maps cơ sở 1 (12 Lê Đình Chinh).

### Giai đoạn 4: Tối ưu UI/UX Mobile, Tablet & PC & Tích hợp 2 Cơ sở Dạy học
- [x] Mobile: Thiết kế thanh điều hướng dưới cùng (Bottom Navigation) tiện lợi cho ngón tay cái.
- [x] Tablet & PC: Bố cục lưới cân đối, hỗ trợ phím tắt điều hướng nhanh (`1,2,3,4`, `Space`, `Enter`).
- [x] Tích hợp 2 cơ sở dạy học (12 Lê Đình Chinh & 32 Chu Văn An) với modal đa cơ sở.
- [x] Thiết lập giao diện tối (Dark Theme) làm mặc định tải trang.

### Giai đoạn 4.5: Tính năng Học tập Đột phá & Tiện ích Thông minh (Advanced Learning Suite)
- [x] Mini-game "Ghép từ phản xạ" (Speed Match Pairs Game - Tab `⚡ Ghép từ` với bấm giờ và hiệu ứng âm thanh).
- [x] Chế độ Tự động lật thẻ rảnh tay (Hands-free Autoplay Slideshow) trong Thẻ ghi nhớ.
- [x] Hệ thống Từ vựng Yêu thích / Cần lưu ý (Starred Words ⭐) và chip lọc ôn tập riêng.
- [x] Tùy chỉnh tốc độ phát âm (Pronunciation Speed: 0.8x Chậm / 1.0x Chuẩn).
- [x] Hộp thoại Thống kê học tập & Đặt lại tiến độ (Study Analytics & Reset Progress Modal).
- [x] Chế độ In ấn tài liệu & Xuất PDF A4 chuẩn đẹp (@media print).

### Giai đoạn 5: Tinh chỉnh Trải nghiệm, Đồng bộ Thông tin & Sẵn sàng GitHub Pages
- [x] Đồng bộ hóa Hotline `0898 123 696` và Zalo `0792 951 529`, bổ sung tính năng click tự động sao chép kèm Toast notification.
- [x] Tích hợp liên kết Fanpage Facebook `https://www.facebook.com/mstramengclass` vào Footer và Header card.
- [x] Tái thiết kế giao diện Cơ sở 1 và Cơ sở 2 tinh gọn, trực quan, loại bỏ hoàn toàn cảm giác rối mắt.
- [x] Tối ưu chuẩn hóa 100% tĩnh cho GitHub Pages (tạo `.nojekyll`, `404.html`, kiểm tra relative paths).
- [x] Kiểm thử kiểm tra cú pháp và khả năng chạy offline trực tiếp (`file:///`) cũng như trên GitHub Pages.
- [x] Cập nhật file `README.md` với đầy đủ tính năng và hướng dẫn triển khai.
