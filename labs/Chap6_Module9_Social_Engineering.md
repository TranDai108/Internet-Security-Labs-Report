# Chapter 6: CEH v10 Module 9 - Social Engineering

Chương này tập trung vào các hình thức tấn công phi kỹ thuật (Social Engineering), trong đó kẻ tấn công lợi dụng tâm lý và hành vi của con người để lừa đảo, đánh cắp thông tin.

---

### Lab 1 & 2: Phát hiện lừa đảo (Phishing) bằng Netcraft và PhishTank (P.4, P.27)

- **Kịch bản**: Tấn công lừa đảo (phishing) ngày càng tinh vi, trong đó kẻ tấn công giả mạo các tổ chức uy tín để lừa người dùng cung cấp thông tin nhạy cảm.
- **Mục tiêu**: Học cách sử dụng các công cụ trực tuyến để kiểm tra và phát hiện các trang web lừa đảo.
- **Công cụ**: Netcraft Toolbar, PhishTank.
- **Tóm tắt thực hiện**:
  1. **Netcraft**: Cài đặt extension Netcraft Toolbar trên trình duyệt. Khi truy cập một trang web, extension sẽ hiển thị các thông tin như mức độ rủi ro, quốc gia, và ngày ra mắt. Nó cũng sẽ chặn và cảnh báo nếu người dùng truy cập một trang web đã bị báo cáo là lừa đảo.
  2. **PhishTank**: Truy cập trang web PhishTank, nhập URL của một trang web đáng ngờ vào thanh tìm kiếm. PhishTank sẽ trả về kết quả xác minh từ cộng đồng xem trang đó có phải là trang lừa đảo hay không.
- **Kết quả**: Cả hai công cụ đều cung cấp những phương pháp hiệu quả để người dùng tự bảo vệ mình bằng cách kiểm tra độ tin cậy của một trang web trước khi cung cấp thông tin, dựa trên dữ liệu được đóng góp và xác minh bởi cộng đồng.

> *Để xem đầy đủ hình ảnh các bước thực hiện, vui lòng tham khảo file báo cáo gốc tại mục `report/`.*

---

### Lab 3: Đánh cắp thông tin đăng nhập Facebook bằng Social Engineering Toolkit (SET) (P.16)

- **Kịch bản**: Kẻ tấn công sử dụng bộ công cụ SET để tạo một trang web giả mạo (clone) một trang đăng nhập nổi tiếng, sau đó lừa nạn nhân nhập thông tin tài khoản.
- **Mục tiêu**: Học cách nhân bản một trang web và thực hiện tấn công thu thập thông tin đăng nhập (Credential Harvester).
- **Công cụ**: Social Engineering Toolkit (SET).
- **Tóm tắt thực hiện**:
  1. Khởi chạy SET trên Kali Linux và chọn phương thức tấn công `Social-Engineering Attacks` -> `Website Attack Vectors` -> `Credential Harvester Attack Method` -> `Site Cloner`.
  2. Nhập địa chỉ IP của máy tấn công và URL của trang web cần nhân bản (ví dụ: `https://www.facebook.com`).
  3. SET sẽ tạo một trang web giả mạo và khởi chạy một web server để lắng nghe.
  4. Gửi một email lừa đảo chứa đường link đến trang giả mạo cho nạn nhân.
  5. Khi nạn nhân truy cập link và nhập thông tin đăng nhập, thông tin đó sẽ bị gửi về máy của kẻ tấn công.
- **Kết quả**: Đã đánh cắp thành công thông tin đăng nhập của người dùng khi họ nhập vào trang Facebook giả mạo. Cuộc tấn công cho thấy sự nguy hiểm của kỹ thuật lừa đảo kết hợp với việc nhân bản trang web.

> *Để xem đầy đủ hình ảnh các bước thực hiện, vui lòng tham khảo file báo cáo gốc tại mục `report/`.*
