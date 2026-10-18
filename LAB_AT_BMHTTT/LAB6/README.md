README - LAB 6 PFSENSE, ACTIVE DIRECTORY VÀ CHÍNH SÁCH TRUY CẬP

Họ và tên: NGUYỄN TRƯỜNG THOẠI
MSSV: 1050080203
Lớp: 11_THMT

1. Nội dung đã thực hiện

Đã tạo và cấu hình máy ảo pfSense trên VMware Workstation với 4 card mạng.

WAN:
Nhận IP DHCP từ mạng NAT 192.168.250.0/24.
Địa chỉ WAN đã nhận: 192.168.250.128/24.

LAN:
IP pfSense: 10.6.0.1/24.
Dùng làm gateway cho Domain Controller và các máy client.

MGMT:
IP pfSense: 192.168.56.254/24.
Dùng để quản trị WebGUI pfSense.

DMZ:
IP pfSense: 172.16.6.1/24.
Dùng cho mạng DMZ của bài lab.

2. Cấu hình VMware

Đã cấu hình các mạng ảo cho pfSense.

WAN dùng VMnet8 NAT.
Mạng quản trị dùng Host-only 192.168.56.0/24.
LAN dùng LAN Segment lab6-lan.
DMZ dùng LAN Segment lab6-dmz.

Đã xử lý lỗi VMware DHCP và NAT để pfSense WAN nhận được IP và truy cập Internet.

3. Domain Controller

Đã cấu hình Windows Server làm Domain Controller.

IP: 10.6.0.10/24
Gateway: 10.6.0.1
DNS: 10.6.0.10

Đã cài đặt:
Active Directory Domain Services
DNS Server

Domain hiện đang sử dụng:
vietnam.local

Đã kiểm tra kết nối giữa Domain Controller và pfSense LAN thành công.

4. Active Directory

Đã tạo OU:
LAB6-Users

Đã tạo các tài khoản:
sv_a
sv_b

Đã tạo tài khoản dịch vụ LDAP:
svc_pfsense_ldap

Tài khoản svc_pfsense_ldap được dùng để pfSense kết nối và truy vấn Active Directory.

5. Tích hợp LDAP trên pfSense

Đã tạo Authentication Server tên:
LAB6-AD

Cấu hình chính:

LDAP Server: 10.6.0.10
Port: 389
Protocol version: 3
Search scope: Entire Subtree

Base DN:
DC=vietnam,DC=local

Authentication Container:
OU=LAB6-Users,DC=vietnam,DC=local

Bind DN:
CN=svc_pfsense_ldap,CN=Users,DC=vietnam,DC=local

User Naming Attribute:
samAccountName

Group Naming Attribute:
cn

Group Member Attribute:
memberOf

Đã điều chỉnh cấu hình LDAP signing trên Windows Server để phù hợp với môi trường lab.

6. Kiểm tra LDAP

Đã kiểm tra xác thực tại pfSense trong:
Diagnostics > Authentication

Tài khoản sv_a đã xác thực thành công với LAB6-AD.

7. WebGUI pfSense

Đã truy cập WebGUI pfSense từ mạng LAN bằng địa chỉ:
http://10.6.0.1

Tài khoản quản trị pfSense:
admin

Đã xử lý lỗi WebGUI, firewall và webConfigurator trong quá trình cấu hình.

8. Kiểm tra mạng

pfSense ping 8.8.8.8 thành công.
Domain Controller ping pfSense LAN thành công.
WAN pfSense hoạt động bình thường.
LDAP giữa pfSense và Domain Controller hoạt động.

9. Các phần tiếp theo của bài lab

Cần tạo Client-A:
IP: 10.6.0.21/24
Gateway: 10.6.0.1
DNS: 10.6.0.10

Cần tạo Client-B:
IP: 10.6.0.22/24
Gateway: 10.6.0.1
DNS: 10.6.0.10

Cần cấu hình Captive Portal trên LAN sử dụng LAB6-AD.

Cần tạo máy DMZ-WEB và các địa chỉ:
172.16.6.10
172.16.6.20
172.16.6.30
172.16.6.40

Cần tạo các Alias và Schedule.

Cần thực hiện các kịch bản firewall của LAB 6 và chụp ảnh minh chứng.

10. Kết luận

Phần hạ tầng pfSense, WAN, LAN, MGMT, DMZ, Domain Controller và LDAP đã được cấu hình.
pfSense đã xác thực được tài khoản Active Directory.
Các bước còn lại tập trung vào Client-A, Client-B, Captive Portal, DMZ-WEB và các kịch bản firewall.
