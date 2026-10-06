# README - LAB 3 pfSense

## Thông tin sinh viên
- Họ và tên: **Nguyễn Trường Thoại**
- MSSV: **1050080203**
- Lớp: **11_THMT**

## Các nhiệm vụ đã thực hiện

- Cài đặt pfSense CE 2.7.2 trên VMware Workstation.
- Cấu hình 3 card mạng:
  - WAN: Bridged
  - LAN: VMnet1
  - DMZ: LAN Segment `dmz-net`
- Cấu hình địa chỉ:
  - pfSense LAN: `10.0.0.1/8`
  - pfSense DMZ: `172.16.0.1/16`
  - Domain Controller: `10.0.0.2/8`
  - DMZ-Web: `172.16.0.2/16`
- Cấu hình VMnet1 Host-only, tắt DHCP.
- Tạo và cấu hình Domain Controller.
- Cài Active Directory Domain Services và promote thành Domain Controller.
- Cấu hình DNS Forwarder `8.8.8.8`.
- Tạo máy DMZ-Web và cài IIS.
- Kiểm tra DMZ-Web:
  - Ping pfSense DMZ thành công.
  - Ping Internet `8.8.8.8` thành công.
  - Phân giải DNS thành công.
  - IIS hoạt động với `curl http://localhost`.
- Cấu hình rule DMZ cho phép DMZ ra Internet.
- Kiểm tra Outbound NAT tự động.
- Chuẩn hóa LAN rules:
  - Disable Default allow LAN IPv4/IPv6.
  - Giữ Anti-Lockout Rule.
  - Tạo rule LAN to Internet.
- Kiểm tra rule LAN:
  - Enable rule: Internet hoạt động.
  - Disable rule + Reset States: Internet bị chặn.
- Hoàn thành **Tình huống 1**:
  - Chặn ICMP.
  - Cho phép DNS TCP/UDP 53.
  - Cho phép HTTP 80.
  - Cho phép HTTPS 443.
  - Ping `8.8.8.8` thất bại.
  - DNS và HTTPS vẫn hoạt động.

## Trạng thái hiện tại
- [x] Cấu hình pfSense cơ bản
- [x] LAN
- [x] DMZ
- [x] Domain Controller
- [x] DNS
- [x] IIS
- [x] Outbound NAT
- [x] Rule LAN nền tảng
- [x] Tình huống 1
- [ ] Tình huống 2
- [ ] Tình huống 3
- [ ] Tình huống 4
- [ ] Tình huống 5
