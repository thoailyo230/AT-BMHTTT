LAB 4 - Khảo sát và đánh giá bề mặt mạng bằng Nmap

Thông tin sinh viên
- Họ tên: Nguyễn Trường Thoại
- MSSV: 1050080203
- Lớp: 11_THMT

Môi trường thực hành
- Kali Linux: `192.168.56.129`
- Metasploitable 2: `192.168.56.128`
- Windows VM: `192.168.56.130`
- Mạng lab: `192.168.56.0/24`
- Chế độ mạng: Host-Only

Nội dung đã thực hiện
- Host discovery bằng Nmap
- TCP Connect scan (`-sT`) và SYN scan (`-sS`)
- FIN / Xmas / NULL / ACK scan
- UDP scan
- Nhận diện phiên bản dịch vụ (`-sV`)
- Nhận diện hệ điều hành (`-O`)
- Aggressive scan (`-A`)
- NSE SMB và kiểm tra MS17-010
- Xuất kết quả `.txt`, `.xml`, `.html`
- So sánh trước/sau hardening trên Windows VM

Kết quả chính
- Metasploitable 2 phát hiện nhiều dịch vụ mở như FTP, SSH, Telnet, HTTP, SMB, MySQL, PostgreSQL, VNC...
- Nmap nhận diện hệ điều hành thuộc Linux 2.6.x.
- `smb-os-discovery` nhận diện Samba 3.0.20-Debian.
- Kiểm tra MS17-010 không trả về trạng thái `VULNERABLE`.
- Sau hardening Windows, cổng `5985/tcp` không còn ở trạng thái `open`.

File trong thư mục LAB4
text
LAB4/
├── README.md
├── scan_normal.txt
├── scan.xml
├── scan.html
├── smb.txt
├── before_windows.txt
├── after_windows.txt
└──screenshots/


Lưu ý
Bài lab chỉ thực hiện trên các máy ảo do sinh viên tự dựng trong mạng Host-Only, không quét hệ thống bên ngoài khi chưa được phép.
