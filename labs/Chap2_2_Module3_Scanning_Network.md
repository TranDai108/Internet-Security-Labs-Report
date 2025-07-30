# Chapter 2.2: CEH v10 - Module 3: Scanning Network

Chương này đi sâu vào các kỹ thuật quét mạng để xác định các host đang hoạt động, các cổng mở và các dịch vụ đang chạy trên hệ thống mục tiêu.

---

### Lab 1: Quét mạng bằng Colasoft Packet Builder

- **Kịch bản**: Kiểm tra mạng và quét các thiết bị đang hoạt động bằng kỹ thuật ARP Ping Scanning.
- **Mục tiêu**: Phát hiện các thiết bị đang hoạt động trong mạng bằng cách tạo và gửi các gói tin ARP.
- **Công cụ**: Colasoft Packet Builder

**Tóm tắt thực hiện**:
1. Cài đặt Colasoft Packet Builder và chọn network adapter phù hợp.
2. Tạo một gói tin ARP mới (ARP Packet) và cấu hình các thông số.
3. Gửi gói tin ARP lên mạng. Các máy đang hoạt động sẽ phản hồi lại bằng gói ARP Reply.

**Kết quả**: Công cụ cho phép tạo và gửi các gói tin tùy chỉnh hiệu quả. Có thể sử dụng Wireshark để bắt và xác nhận các gói ARP Reply từ các host đang hoạt động trong mạng.

> *Tham khảo hình ảnh các bước thực hiện tại thư mục `report/`.*

---

### Lab 2: Tạo gói tin UDP và TCP bằng HPING3

- **Kịch bản**: Sử dụng kỹ thuật packet crafting để quét mạng và vượt qua hệ thống phòng thủ như firewall hoặc IDS.
- **Mục tiêu**: Thực hiện quét mạng và tạo gói tin bằng các lệnh của hping3.
- **Công cụ**: Hping3, Wireshark

**Tóm tắt thực hiện**:
1. Sử dụng `hping3` để thực hiện SYN scan, quét các cổng từ 1–3000 trên máy mục tiêu.
2. Tạo và gửi các gói UDP với địa chỉ IP nguồn giả mạo (`--rand-source`) đến máy đích.
3. Thực hiện tấn công TCP Flooding với tùy chọn `--flood` để làm quá tải tài nguyên của máy mục tiêu.

**Kết quả**: Quét thành công các cổng đang mở (135, 139, 445). Cuộc tấn công TCP Flooding tạo lượng lớn gói tin gửi đến máy nạn nhân, có thể quan sát được bằng Wireshark.

> *Tham khảo hình ảnh các bước thực hiện tại thư mục `report/`.*

---

### Lab 3: Xử lý sự cố mạng bằng MegaPing

- **Kịch bản**: Theo dõi đường đi mạng mục tiêu để phát hiện router, firewall và mô hình mạng.
- **Mục tiêu**: Sử dụng MegaPing để phát hiện các máy chủ đang hoạt động và các cổng đang mở trong mạng.
- **Công cụ**: MegaPing

**Tóm tắt thực hiện**:
1. Sử dụng công cụ `IP Scanner` để quét dải địa chỉ IP và xác định các host "Alive".
2. Thực hiện `Traceroute` đến máy chủ mục tiêu (Windows Server 2012) để xem đường đi mạng.
3. Sử dụng `Port Scanner` để quét các cổng mở trên máy chủ đó.

**Kết quả**: MegaPing phát hiện thành công 3 cổng mở trên máy chủ Windows Server 2012: 135 (loc-srv), 139 (netbios-ssn), và 445 (microsoft-ds), đồng thời đưa ra đánh giá mức độ rủi ro của các cổng này.

> *Tham khảo hình ảnh các bước thực hiện tại thư mục `report/`.*

---

### Lab 5: Quét mạng bằng NetScanTools Pro

- **Kịch bản**: Thực hiện nhiều loại quét khác nhau trong đánh giá bảo mật, gồm ARP Ping, DHCP Discovery và Port Scan.
- **Mục tiêu**: Học cách thực hiện các kỹ thuật quét này bằng NetScanTools Pro.
- **Công cụ**: NetScanTools Pro

**Tóm tắt thực hiện**:
1. **ARP Ping**: "Ping" một địa chỉ IPv4 bằng gói ARP để kiểm tra phản hồi.
2. **ARP Scan**: Quét một dải IP để tìm các thiết bị đang hoạt động và địa chỉ MAC tương ứng.
3. **DHCP Server Discovery**: Tìm kiếm các máy chủ DHCP hiện diện trong mạng.
4. **Ping Scan**: Kiểm tra các host có phản hồi ICMP ping hay không.
5. **Port Scan**: Quét các cổng TCP trên một máy mục tiêu.

**Kết quả**: NetScanTools Pro chứng tỏ là công cụ đa năng cho phép thực hiện nhiều kiểu quét mạng từ một giao diện duy nhất, cung cấp thông tin chi tiết về thiết bị và dịch vụ trong mạng.

> *Tham khảo hình ảnh các bước thực hiện tại thư mục `report/`.*

---

### Lab 6: Quét lưu lượng mạng bằng IP-Tools

- **Kịch bản**: Phát hiện các host đang hoạt động và các cổng đang mở trong mạng con bằng IP-Tools.
- **Mục tiêu**: Học cách sử dụng IP-Tools để phát hiện host, cổng mở và các dịch vụ trong mạng.
- **Công cụ**: IP-Tools

**Tóm tắt thực hiện**:
1. Sử dụng các tính năng như `Name Scanner`, `Port Scanner`, `UDP Scanner`, và `Ping Scanner` để quét dải IP từ 192.168.1.1 đến 192.168.1.20.
2. Dùng `WhoIs` để thu thập thông tin về tên miền `certifiedhacker.com`.
3. Dùng công cụ `HTTP` để trích xuất thông tin từ một URL cụ thể.

**Kết quả**: IP-Tools là bộ công cụ TCP/IP mạnh mẽ và dễ sử dụng, giúp thực hiện nhanh các tác vụ quét và thu thập thông tin mạng.

> *Tham khảo hình ảnh các bước thực hiện tại thư mục `report/`.*
