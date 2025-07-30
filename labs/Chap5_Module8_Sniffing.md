# Chapter 5: CEH v10 Module 8 - Sniffing

Chương này tập trung vào các kỹ thuật nghe lén (sniffing) lưu lượng mạng để đánh cắp thông tin nhạy cảm. Các kỹ thuật như Man-in-the-Middle (MITM) và ARP Poisoning được trình bày chi tiết.

---

### Lab 1: Tấn công Man-in-the-Middle bằng Cain & Abel (P.4)

- **Kịch bản**: Kẻ tấn công chèn mình vào giữa luồng giao tiếp của hai thiết bị để nghe lén và đánh cắp thông tin đăng nhập không được mã hóa.
- **Mục tiêu**: Thực hành tấn công MITM bằng kỹ thuật ARP Poisoning để nghe lén và lấy mật khẩu FTP.
- **Công cụ**: Cain & Abel.
- **Tóm tắt thực hiện**:
  1. Cài đặt Cain & Abel và cấu hình nó để nghe lén trên card mạng phù hợp.
  2. Sử dụng tính năng `Sniffer` để quét mạng và tìm các host đang hoạt động.
  3. Chuyển sang tab `APR`, thực hiện đầu độc ARP (ARP Poisoning) giữa hai máy mục tiêu để chuyển hướng lưu lượng truy cập qua máy của kẻ tấn công.
  4. Khi một máy nạn nhân thực hiện đăng nhập FTP đến máy kia, Cain & Abel sẽ bắt được gói tin và giải mã mật khẩu.
- **Kết quả**: Đã bắt và giải mã thành công mật khẩu FTP được gửi qua mạng dưới dạng văn bản rõ, chứng minh sự nguy hiểm của tấn công MITM đối với các giao thức không mã hóa.

> *Để xem đầy đủ hình ảnh các bước thực hiện, vui lòng tham khảo file báo cáo gốc tại mục `report/`.*

---

### Lab 2: Giả mạo địa chỉ MAC bằng SMAC (P.16)

- **Kịch bản**: Kẻ tấn công thay đổi địa chỉ MAC của mình để trùng với một thiết bị hợp lệ trong mạng, nhằm vượt qua các cơ chế lọc MAC và chiếm đoạt danh tính.
- **Mục tiêu**: Thực hành giả mạo địa chỉ MAC (MAC Spoofing) bằng công cụ SMAC.
- **Công cụ**: SMAC.
- **Tóm tắt thực hiện**:
  1. Cài đặt và khởi chạy SMAC.
  2. Chọn card mạng cần thay đổi địa chỉ MAC.
  3. Nhập một địa chỉ MAC mới hoặc chọn một địa chỉ từ danh sách có sẵn, sau đó nhấn `Update MAC`.
  4. Công cụ sẽ khởi động lại card mạng để áp dụng địa chỉ MAC mới.
- **Kết quả**: Đã thay đổi thành công địa chỉ MAC của card mạng. Kỹ thuật này cho thấy các biện pháp bảo mật chỉ dựa vào địa chỉ MAC là không đủ an toàn và có thể dễ dàng bị vượt qua.

> *Để xem đầy đủ hình ảnh các bước thực hiện, vui lòng tham khảo file báo cáo gốc tại mục `report/`.*

---

### Lab 5, 6 & 7: Phân tích và phát hiện tấn công ARP Poisoning (P.64, P.79, P.97)

- **Kịch bản**: Một quản trị viên mạng cần giám sát lưu lượng mạng để phát hiện các cuộc tấn công ARP Poisoning, vốn thường khó bị tường lửa phát hiện.
- **Mục tiêu**: Học cách sử dụng các công cụ phân tích mạng để nghe lén lưu lượng và phát hiện các dấu hiệu của tấn công ARP.
- **Công cụ**: Omnipeek Network Analyzer, Wireshark, XArp.
- **Tóm tắt thực hiện**:
  1. **Omnipeek**: Khởi chạy một phiên bắt gói tin, duyệt web trên máy khác để tạo lưu lượng, sau đó phân tích kết quả qua các bảng điều khiển như `Packets`, `Nodes`, `Protocols`.
  2. **Wireshark**: Bắt đầu một cuộc tấn công ARP Poisoning bằng Cain & Abel, sau đó dùng Wireshark trên một máy thứ ba để bắt gói tin. Tính năng `Expert Information` của Wireshark sẽ cảnh báo về "duplicate IP address configuration".
  3. **XArp**: Chạy công cụ XArp, thiết lập mức độ bảo mật `aggressive`. Khi cuộc tấn công ARP Poisoning diễn ra, XArp sẽ ngay lập tức phát hiện và thông báo "ARP attacks detected!".
- **Kết quả**: Các công cụ phân tích mạng như Wireshark và XArp đã chứng tỏ hiệu quả cao trong việc phát hiện các hoạt động bất thường của giao thức ARP, giúp quản trị viên có thể nhận biết và phản ứng kịp thời với các cuộc tấn công MITM.

> *Để xem đầy đủ hình ảnh các bước thực hiện, vui lòng tham khảo file báo cáo gốc tại mục `report/`.*
