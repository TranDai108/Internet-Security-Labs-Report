# Báo cáo Thực hành Môn Bảo mật Internet (NT405.P21)

Đây là kho lưu trữ chứa các ghi chú và báo cáo cá nhân từ các buổi thực hành môn **Bảo mật Internet (NT405.P21)**. Các bài lab được xây dựng dựa trên chương trình của **CEHv10 (Certified Ethical Hacker)**.

## 🔍 Nội dung chính

- 🧪 **Báo cáo chi tiết từng Module**: Xem tại thư mục `labs/`
- 📄 **File báo cáo tổng hợp**: `report/Nhom09_BaoCaoThucHanh_NT405.P21.docx`
- 🛠️ **Ghi chú về công cụ và môi trường thực hành**: `tools/Tools_And_Environment.md`

## ⚠️ Giới hạn & Lưu ý

- Một số công cụ sử dụng trong các bài lab đã lỗi thời hoặc không còn được hỗ trợ, gây khó khăn khi cài đặt. Ví dụ: `Web Data Extractor Pro 4.2`, `Colasoft Packet Builder 2.0`.
- Các bài thực hành được triển khai trong môi trường máy ảo cụ thể (Windows Server 2012/2016, Windows 8/10, Kali Linux), có thể khó tái hiện đầy đủ trong môi trường khác.
- Một số kỹ thuật như SSLStrip không còn hiệu quả trên các nền tảng hiện đại do các biện pháp bảo mật tiên tiến như HSTS đã được áp dụng.

## 💡 Mục đích chia sẻ

Dù có một số hạn chế về công cụ và môi trường triển khai, kho lưu trữ này được chia sẻ với mục tiêu phục vụ học tập, tham khảo cho những người quan tâm đến các kỹ thuật và khái niệm trong lĩnh vực **an toàn thông tin** và **bảo mật mạng**.

## 📚 Các chủ đề đã thực hành (theo CEHv10)

- **Module 2**: Thu thập thông tin (Footprinting and Reconnaissance)
- **Module 3**: Quét mạng (Scanning Networks)
- **Module 6**: Tấn công hệ thống (System Hacking)
- **Module 7**: Mã độc và mối đe dọa (Malware Threats)
- **Module 8**: Nghe lén mạng (Sniffing)
- **Module 9**: Tấn công phi kỹ thuật (Social Engineering)
- **Module 10**: Tấn công từ chối dịch vụ (Denial of Service)
- **Module 11**: Chiếm quyền phiên (Session Hijacking)

## 🧰 Một số công cụ đã sử dụng

- **Metasploit Framework**: Thu thập thông tin, khai thác lỗ hổng, thực hiện tấn công DoS
- **Wireshark**: Phân tích lưu lượng mạng, phát hiện tấn công như ARP Poisoning
- **Cain & Abel**: Thực hiện tấn công MITM và ARP Spoofing
- **Hping3**: Tạo gói tin TCP/UDP, tấn công SYN Flood
- **Social Engineering Toolkit (SET)**: Tấn công giả mạo, nhân bản website
- **L0phtCrack**: Kiểm tra, bẻ khóa mật khẩu hệ thống
- **BetterCAP**: Thực hiện SSLStrip và chặn bắt lưu lượng HTTP
- **njRAT, TheFatRat, HTTP RAT**: Tạo mã độc Trojan và điều khiển từ xa

---

📌 *Mọi góp ý, cải tiến hoặc chia sẻ thêm nội dung đều được hoan nghênh!*
