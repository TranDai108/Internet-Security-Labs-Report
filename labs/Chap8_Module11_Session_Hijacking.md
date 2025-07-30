# Chapter 8: CEH v10 Module 11 - Session Hijacking

Chương này đi sâu vào các kỹ thuật chiếm quyền điều khiển phiên làm việc (Session Hijacking), trong đó kẻ tấn công xen vào một phiên hợp lệ giữa người dùng và máy chủ để đánh cắp thông tin hoặc chiếm quyền tài khoản.

---

### Lab 2: Thực hiện sslstrip để chặn bắt lưu lượng HTTP bằng BetterCAP (P.15)

- **Kịch bản**: Kẻ tấn công chèn mình vào giữa người dùng và web server (MITM), sau đó sử dụng kỹ thuật SSLStrip để hạ cấp kết nối từ HTTPS an toàn xuống HTTP không mã hóa, nhằm mục đích nghe lén và đánh cắp thông tin đăng nhập.
- **Mục tiêu**: Học cách chặn bắt lưu lượng HTTP/HTTPS và bóc tách (sniff) thông tin đăng nhập từ mạng.
- **Công cụ**: BetterCAP, Wireshark.
- **Tóm tắt thực hiện**:
  1. Trên máy tấn công Kali Linux, khởi chạy BetterCAP và bật các module cần thiết: `net.recon` (dò tìm thiết bị), `arp.spoof` (đầu độc ARP), và `https.proxy` (proxy để thực hiện SSLStrip).
  2. Thiết lập mục tiêu cho cuộc tấn công ARP spoofing là địa chỉ IP của máy nạn nhân.
  3. Bật `net.sniff` để bắt đầu quá trình nghe lén và lưu các gói tin vào file `.pcap`.
  4. Trên máy nạn nhân, truy cập một trang web đăng nhập sử dụng giao thức HTTP.
  5. Trên máy tấn công, mở file `.pcap` bằng Wireshark, lọc các gói `http` và tìm gói tin có phương thức POST. Thông tin đăng nhập (username, password) sẽ hiện rõ trong phần payload của gói tin.
- **Kết quả**: Đã đánh cắp thành công thông tin đăng nhập được gửi qua giao thức HTTP không mã hóa. Bài lab cũng cho thấy tấn công SSLStrip có thể hạ cấp kết nối của các trang web không có HSTS, chuyển từ HTTPS về HTTP, tạo điều kiện cho việc nghe lén.

> *Để xem đầy đủ hình ảnh các bước thực hiện, vui lòng tham khảo file báo cáo gốc tại mục `report/`.*
