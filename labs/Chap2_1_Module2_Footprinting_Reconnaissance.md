# Chapter 2.1: CEH v10 - Module 2: Footprinting and Reconnaissance

Chương này tập trung vào các kỹ thuật thu thập thông tin ban đầu (Footprinting và Reconnaissance) — bước đầu tiên và quan trọng nhất trong một cuộc kiểm thử xâm nhập.

---

### Lab 6: Trích xuất dữ liệu bằng Web Data Extractor

- **Kịch bản**: Sử dụng công cụ để trích xuất các thông tin có giá trị từ một trang web mục tiêu.
- **Mục tiêu**: Học cách dùng Web Data Extractor để lấy các dữ liệu như meta tag, email, số điện thoại từ website `http://www.certifiedhacker.com`.
- **Công cụ**: Web Data Extractor Pro 4.2

**Tóm tắt thực hiện**:
1. Cài đặt và khởi chạy Web Data Extractor.
2. Tạo một phiên mới, cấu hình URL mục tiêu là `http://www.certifiedhacker.com` với độ sâu thu thập là 100.
3. Bắt đầu quá trình trích xuất và phân tích kết quả, bao gồm email, số điện thoại và các thẻ meta.

**Kết quả**: Trích xuất thành công 26 meta tag, 17 địa chỉ email và 122 số điện thoại, cung cấp cái nhìn tổng quan về dữ liệu công khai của trang web.

> *Tham khảo thêm hình ảnh các bước thực hiện tại thư mục `report/`.*

---

### Lab 9: Thu thập thông tin IP và domain bằng Whois Lookup

- **Kịch bản**: Tra cứu WHOIS trên tên miền và địa chỉ IP của mục tiêu để thu thập thông tin đăng ký.
- **Mục tiêu**: Phân tích truy vấn tên miền và IP để thu thập thông tin như tên máy chủ, địa chỉ IP, chi tiết tên miền.
- **Công cụ**: SmartWhois

**Tóm tắt thực hiện**:
1. Cài đặt và cấu hình SmartWhois.
2. Truy vấn "As Domain" với `www.google.com` để xem thông tin đăng ký.
3. Truy vấn "As IP/Hostname" với `www.facebook.com` và một địa chỉ IP nội bộ (`10.10.10.10`).

**Kết quả**: Thu thập thành công thông tin về nhà đăng ký, ngày tạo/hết hạn, máy chủ DNS của Google và Facebook. Truy vấn IP nội bộ cho thấy thuộc dải địa chỉ riêng theo chuẩn RFC1918.

> *Tham khảo thêm hình ảnh các bước thực hiện tại thư mục `report/`.*

---

### Lab 10: Theo dõi đường đi mạng bằng Path Analyzer Pro

- **Kịch bản**: Theo dõi đường đi mạng đến mục tiêu để phát hiện các router, firewall và mô hình mạng.
- **Mục tiêu**: Xác định đường dẫn và địa chỉ IP của các nút trung gian.
- **Công cụ**: Path Analyzer Pro

**Tóm tắt thực hiện**:
1. Cài đặt Path Analyzer Pro.
2. Thực hiện trace đến `www.google.com` bằng giao thức ICMP.
3. Phân tích kết quả qua các tab: Report, Synopsis, Charts và Geo.

**Kết quả**: Hiển thị trực quan hóa đường đi của gói tin qua từng hop, độ trễ (latency) tại mỗi điểm và vị trí địa lý các router trên bản đồ.

> *Tham khảo thêm hình ảnh các bước thực hiện tại thư mục `report/`.*

---

### Lab 17: Thu thập thông tin bằng Metasploit

- **Kịch bản**: Với vai trò hacker, sử dụng Metasploit để thu thập thông tin về mục tiêu.
- **Mục tiêu**: Nhận diện lỗ hổng và trích xuất thông tin hệ thống mạng.
- **Công cụ**: Metasploit Framework, Nmap tích hợp

**Tóm tắt thực hiện**:
1. Kết nối Metasploit với cơ sở dữ liệu PostgreSQL.
2. Sử dụng `nmap` trong `msfconsole` để quét host hoạt động.
3. Dùng module `scanner/portscan/syn` để quét cổng, và `scanner/smb/smb_version` để xác định phiên bản SMB & OS.

**Kết quả**: Xác định thành công máy chủ Windows trong mạng, các cổng TCP đang mở (135, 139, 445), và phiên bản hệ điều hành, cung cấp dữ liệu giá trị cho giai đoạn tấn công sau.

> *Tham khảo thêm hình ảnh các bước thực hiện tại thư mục `report/`.*
