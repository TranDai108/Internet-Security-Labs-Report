# Chapter 7: CEH v10 Module 10 - Denial of Service

Chương này tập trung vào các cuộc tấn công Từ chối dịch vụ (Denial of Service - DoS) và Từ chối dịch vụ phân tán (DDoS), trong đó kẻ tấn công làm cạn kiệt tài nguyên của hệ thống mục tiêu, khiến nó không thể phục vụ người dùng hợp lệ.

---

### Lab 1 & 2: Tấn công SYN Flooding bằng Metasploit và hping3 (P.4, P.11)

- **Kịch bản**: Kẻ tấn công khai thác cơ chế bắt tay ba bước của TCP bằng cách gửi một loạt yêu cầu SYN nhưng không hoàn tất kết nối, khiến máy chủ phải giữ các kết nối "nửa mở" và dần cạn kiệt tài nguyên.
- **Mục tiêu**: Học cách thực hiện một cuộc tấn công SYN Flooding bằng các công cụ khác nhau và quan sát tác động của nó lên máy mục tiêu.
- **Công cụ**: Metasploit Framework, hping3, Wireshark.
- **Tóm tắt thực hiện**:
  1. **Metasploit**: Sử dụng module `auxiliary/dos/tcp/synflood`, cấu hình địa chỉ IP của máy mục tiêu (RHOST), cổng đích (RPORT), và giả mạo địa chỉ IP nguồn (SHOST). Sau đó, khởi chạy cuộc tấn công bằng lệnh `exploit`.
  2. **hping3**: Sử dụng lệnh `hping3` với tùy chọn `-S` (gói SYN) và `--flood` để gửi liên tục các gói tin đến máy nạn nhân.
  3. **Quan sát**: Trên máy nạn nhân, sử dụng Wireshark để thấy một lượng lớn gói tin SYN được gửi đến, và dùng Task Manager để quan sát mức sử dụng CPU tăng đột biến.
- **Kết quả**: Cả hai công cụ đều thực hiện thành công cuộc tấn công SYN Flooding, làm quá tải tài nguyên của máy nạn nhân và cho thấy hiệu quả của phương pháp tấn công DoS này.

> *Để xem đầy đủ hình ảnh các bước thực hiện, vui lòng tham khảo file báo cáo gốc tại mục `report/`.*

---

### Lab 5: Tấn công DDoS bằng HOIC (P.15)

- **Kịch bản**: Một cuộc tấn công DDoS sử dụng nhiều máy tính (botnet) để đồng loạt tấn công vào một mục tiêu duy nhất, tạo ra một lượng truy cập khổng lồ và làm hệ thống sụp đổ.
- **Mục tiêu**: Tìm hiểu cách phát động một cuộc tấn công DDoS (cụ thể là HTTP Flooding) bằng công cụ HOIC.
- **Công cụ**: High Orbit Ion Cannon (HOIC), Wireshark.
- **Tóm tắt thực hiện**:
  1. Trên nhiều máy tấn công, khởi chạy công cụ HOIC.
  2. Thêm URL của máy nạn nhân, thiết lập mức công suất (Power) là `High` và đặt số lượng luồng (Threads) là 20.
  3. Trên tất cả các máy tấn công, nhấn nút "FIRE THE LAZER!" để đồng loạt bắt đầu cuộc tấn công.
  4. Trên máy nạn nhân, sử dụng Wireshark để quan sát một lượng lớn gói tin HTTP được gửi đến liên tục và kiểm tra hiệu năng hệ thống.
- **Kết quả**: Cuộc tấn công DDoS đã tạo ra một lượng lớn lưu lượng truy cập đến máy nạn nhân, làm giảm hiệu suất của máy. Điều này cho thấy sức mạnh của các cuộc tấn công phân tán khi có nhiều nguồn tấn công cùng lúc.

> *Để xem đầy đủ hình ảnh các bước thực hiện, vui lòng tham khảo file báo cáo gốc tại mục `report/`.*
