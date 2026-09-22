# LAB3 - Windows Security Monitoring & Evidence Collection

## Thông tin sinh viên
- Sinh viên: Nguyễn Trường Thoại
- MSSV: 1050080203
- Lớp: 11_THMT

## Môi trường
- Windows Server 2025 Standard Evaluation
- VMware Workstation

## Công cụ
- Windows Defender
- Windows Firewall
- Sysinternals Sysmon
- Sysinternals Autoruns
- Wireshark
- PowerShell

## Nội dung thực hiện

### Defender và Firewall
Kiểm tra Antivirus, Real-time Protection, Tamper Protection và Firewall Profiles.

Evidence:
- baseline_defender.txt
- baseline_firewall.txt

### EICAR Antivirus Test
Tạo file kiểm tra EICAR để xác nhận Windows Defender phát hiện và cách ly.

Evidence:
- eicar.com.txt

### Sysmon Monitoring
Kiểm tra:
- Event ID 1: Process Create
- Event ID 5: Process Terminate

Evidence:
- sysmon.evtx

### Wireshark Network Monitoring
Thu thập:
- ICMP
- ARP
- Network packets

Evidence:
- capture.pcapng

### Persistence Detection
Registry Run Key:

`HKCU\Software\Microsoft\Windows\CurrentVersion\Run`

Tên:
`LAB3_Run_Demo`

Giá trị:
`notepad.exe`

Kiểm tra bằng Sysinternals Autoruns.

## Cấu trúc thư mục

LAB3/
- Evidence/
- Tools/
- README.md
- Report.docx
- evidence_sha256.csv

## Kết quả
Đã hoàn thành các bước kiểm tra Defender, Firewall, Sysmon, Wireshark và Registry persistence.

## Lưu ý
Chỉ sử dụng trong môi trường học tập LAB. Không chứa password, token, API key hoặc dữ liệu nhạy cảm.
