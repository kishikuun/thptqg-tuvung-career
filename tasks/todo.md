# Danh Sách Nhiệm Vụ Nâng Cấp (Task List)

## Phase 1: Kiến trúc Đa chủ đề & Định dạng Markdown (Multi-Topic Architecture)
- [x] Task 1.1: Xây dựng bộ giải mã Markdown (`js/parser.js`) hỗ trợ Frontmatter và Markdown Table linh hoạt.
- [x] Task 1.2: Chuyển đổi dữ liệu Career sang định dạng Markdown chuẩn (`data/topics/career.js` & `data/topics/career.md`).
- [x] Task 1.3: Tạo chủ đề mẫu thứ 2 Environment (`data/topics/environment.js` & `data/topics/environment.md`) để kiểm thử.
- [x] Task 1.4: Nâng cấp `js/data.js` quản lý đa chủ đề và đồng bộ biến toàn cục linh hoạt.
- [x] Task 1.5: Nâng cấp `index.html` và `css/style.css` tích hợp nút "Chuyên đề: ▾" và Modal chọn chuyên đề.
- [x] Task 1.6: Nâng cấp `js/app.js` hỗ trợ chuyển đổi chủ đề mượt mà, lưu tiến độ độc lập theo từng chủ đề.
- [x] Task 1.7: Kiểm thử toàn diện cú pháp và khả năng tự động sinh câu hỏi trắc nghiệm/điền từ cho cả 2 chủ đề.

## Phase 2: Công cụ nhập liệu cho cô giáo (Teacher Vocab Studio)
- [x] Task 2.1: Xây dựng trang `studio.html` và `js/studio.js` cho phép cô giáo copy-paste bảng từ Excel hoặc Google Sheets với bộ nhận diện tự động thông minh (Fuzzy Auto-detection).
  - **Tiêu chí chấp nhận:** Hỗ trợ dán bảng từ Excel dạng Tab-separated, tự động nhận diện các cột (kể cả khi không có tiêu đề, hoặc tiêu đề như ảnh Google Sheets của cô Trâm).
  - **Kiểm tra:** Đã kiểm thử tự động nhận diện khớp 100% các cột từ ảnh mẫu của cô Trâm.
- [x] Task 2.2: Tích hợp chức năng Xem trước (Live Preview), menu chọn cột linh hoạt và Xuất file dữ liệu `js` và `md`.
  - **Tiêu chí chấp nhận:** Cho phép tùy chỉnh chọn lại cột bằng dropdown, có nút "Tải về file .js", "Tải về file .md", "Sao chép mã" và hướng dẫn 2 bước cực kỳ dễ hiểu cho cô giáo.
- [x] Task 2.3: Thêm nút liên kết "🛠️ Studio nhập từ mới" trong Modal Chuyên đề và Footer của trang học sinh.

## Phase 3: Tính năng học tập mới cho học sinh & Bản đồ Google Maps
- [x] Task 3.1: Thêm chế độ học tập "Luyện gõ từ vựng" (Spelling / Dictation Mode).
  - **Tiêu chí chấp nhận:** Học sinh nghe phát âm / xem nghĩa tiếng Việt và câu ví dụ, gõ từ vào ô nhập, nhận phản hồi đúng/sai tức thì kèm phím Enter để tiếp tục.
- [x] Task 3.2: Thêm bộ lọc "Từ cần ôn gấp" (Weak Words Focus).
  - **Tiêu chí chấp nhận:** Ghi nhớ các từ trả lời sai vào `localStorage`, có nút lọc nhanh để học sinh chỉ ôn tập danh sách từ này bằng thẻ ghi nhớ hoặc bài trắc nghiệm.
- [x] Task 3.3: Thêm nút "Sao chép kết quả gửi Zalo" (One-Click Zalo Report) trên phiếu điểm.
  - **Tiêu chí chấp nhận:** Bấm nút sẽ copy đoạn văn bản báo cáo kết quả chi tiết có định dạng đẹp mắt để dán thẳng vào Zalo cô giáo.
- [x] Task 3.4: Tích hợp hiệu ứng âm thanh Web Audio API (Native, không cần file ngoài) kèm nút bật/tắt âm thanh (Mute/Unmute).
  - **Tiêu chí chấp nhận:** Phát âm thanh nhẹ nhàng khi chọn đúng/sai; lưu trạng thái âm thanh vào `localStorage`.
- [x] Task 3.5: Tích hợp bản đồ tĩnh Google Maps khi nhấp vào địa chỉ trung tâm (12 Lê Đình Chinh, Quy Nhơn Nam) với đúng iframe do người dùng cung cấp.

## Phase 4: Nâng cấp trải nghiệm UI/UX (Mobile, Tablet & PC) & Tích hợp 2 Cơ sở Dạy học
- [x] Task 4.1: Tích hợp nút chuyển đổi giao diện Sáng / Tối (Dark / Light Theme Toggle với MẶC ĐỊNH LÀ THEME TỐI).
  - **Tiêu chí chấp nhận:** Mặc định tải trang là Dark Theme; nút đổi theme nằm ở Header (🌙 / ☀️), lưu lựa chọn vào `localStorage`, đồng bộ màu mượt mà chống chớp tắt.
- [x] Task 4.2: Tối ưu UI cho Mobile (Thanh điều hướng dưới chân trang - Bottom Tab Bar) và phím tắt PC.
  - **Tiêu chí chấp nhận:** Mobile có thanh điều hướng nổi dễ bấm ngón cái; PC hỗ trợ phím số `1,2,3,4` hoặc `A,B,C,D` để chọn phương án trắc nghiệm, `Enter`/`Space` để chuyển câu, phím tắt `Space, ←, →, M, S` cho Flashcards.
- [x] Task 4.3: Tích hợp đầy đủ 2 cơ sở dạy học của cô giáo (12 Lê Đình Chinh & 32 Chu Văn An) với Google Maps Modal đa cơ sở.
  - **Tiêu chí chấp nhận:** Thẻ liên hệ hiển thị 2 nút xem bản đồ cho 2 cơ sở; Modal bản đồ có thanh tab chuyển đổi linh hoạt kèm đúng iframe do người dùng cung cấp.

## Phase 4.5: Tính năng Học tập Đột phá & Tiện ích Thông minh (Advanced Learning Suite)
- [x] Task 4.5.1: Mini-game "Ghép từ phản xạ" (Speed Match Pairs Game - Tab `⚡ Ghép từ`).
  - **Tiêu chí chấp nhận:** 10 ô thẻ (5 từ Anh, 5 nghĩa Việt) được xáo trộn. Ghép đúng: phát sáng xanh, âm ding, ẩn cặp; Ghép sai: rung đỏ, âm buzz. Có bấm giờ tính giây hoàn thành và chơi tiếp lượt mới.
- [x] Task 4.5.2: Chế độ Tự động lật thẻ rảnh tay (Hands-free Autoplay Slideshow) trong Thẻ ghi nhớ.
  - **Tiêu chí chấp nhận:** Nút `▶ Tự động` phát âm -> dừng 2s -> lật mặt sau -> dừng 2.5s -> sang thẻ mới; có nút ⏸️ Tạm dừng linh hoạt.
- [x] Task 4.5.3: Hệ thống Từ vựng Yêu thích / Cần lưu ý (Starred Words ⭐).
  - **Tiêu chí chấp nhận:** Cho phép bấm ⭐ trên Flashcard, Danh sách, Trắc nghiệm; có chip lọc `⭐ Đã gắn sao (N)` để ôn tập riêng.
- [x] Task 4.5.4: Tùy chỉnh tốc độ phát âm (Pronunciation Speed: 0.8x / 1.0x).
  - **Tiêu chí chấp nhận:** Nút chuyển tốc độ phát âm (0.8x Chậm rõ / 1.0x Chuẩn) giúp học sinh nghe rõ từng trọng âm và đuôi từ khó.
- [x] Task 4.5.5: Hộp thoại Thống kê học tập & Đặt lại tiến độ (Study Analytics & Reset Progress Modal).
  - **Tiêu chí chấp nhận:** Nhấp vào nấc thang tiến độ mở modal xem tổng quan tiến độ (đã thuộc, cần ôn gấp, gắn sao) kèm nút Đặt lại tiến độ (có xác nhận).
- [x] Task 4.5.6: Chế độ In ấn tài liệu & Xuất PDF A4 chuẩn đẹp (@media print).
  - **Tiêu chí chấp nhận:** Nút "🖨️ In tài liệu / Xuất PDF" trong tab Danh sách. Khi in hoặc lưu PDF, tự động ẩn giao diện web, dàn trang 2 cột A4 thanh lịch kèm logo trung tâm.

## Phase 5: Tinh chỉnh Trải nghiệm, Đồng bộ Thông tin & Sẵn sàng GitHub Pages
- [x] Task 5.1: Đồng bộ hóa chuẩn xác Hotline `0898 123 696` và Zalo `0792 951 529` trên toàn bộ website, tích hợp tính năng nhấp là tự động sao chép vào clipboard kèm Toast notification nổi.
- [x] Task 5.2: Tích hợp liên kết Fanpage Facebook `https://www.facebook.com/mstramengclass` vào dòng bản quyền Footer và Header card thông tin lớp học.
- [x] Task 5.3: Tái thiết kế giao diện hiển thị Cơ sở 1 và Cơ sở 2 ở Footer thành dạng thẻ lưới 2 cột tinh tế, gọn gàng, loại bỏ hoàn toàn cảm giác rối mắt.
- [x] Task 5.4: Tối ưu chuẩn hóa 100% cho việc triển khai GitHub Pages và mở file cục bộ (`file:///`): tạo file `.nojekyll`, tạo trang điều hướng `404.html`, rà soát 100% đường dẫn relative.
- [x] Task 5.5: Kiểm thử toàn diện giao diện và tương tác trên cả Mobile (thanh điều hướng đáy màn hình), Tablet và PC (phím tắt trắc nghiệm và flashcard).
- [x] Task 5.6: Cập nhật tài liệu hướng dẫn chi tiết trong `README.md`.


