With Registry Viewer tool:

### OS Version:

`SOFTWARE\Microsoft\Windows NT\CurrentVersion`

### **Current control set:**

dữ liệu config để khởi động máy tính:

2 Control Sets:

- ControlSet001: Trỏ đến Control Set mà máy khởi động
    
    `SYSTEM\ControlSet001`
    
- ControlSet002: Last know good thiết lập được lưu lại từ lần tắt máy gần đây nhất
    
    `SYSTEM\ControlSet002`
    

CurrentControlSet: bộ Control Set sẽ mất khi máy đang chạy

HKLM\SYSTEM\CurrentControlSet

Tìm ra Bộ Control Set đang được sử dụng :

`SYSTEM\Select\Current`

The Last known good:
SYSTEM\Select\LastKnownGood

### **Computer Name:**

`SYSTEM\CurrentControlSet\Control\ComputerName\ComputerName`

### **Time Zone Information:**

`SYSTEM\CurrentControlSet\Control\TimeZoneInformation`

### **Network Interfaces and Past Networks:**

`SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

→ IP addresss, DHCP IP addres, subnet Mask, dns Sever,…

Pass network: 

`SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Unmanaged`

`SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Managed`

### **Autostart Programs (Autoruns):**

`NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Run`

`NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\RunOnce`

`SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce`

`SOFTWARE\Microsoft\Windows\CurrentVersion\policies\Explorer\Run`

`SOFTWARE\Microsoft\Windows\CurrentVersion\Ru`

Service:

`SYSTEM\CurrentControlSet\Services`

⇒ Nếu Registry Key, bắt đầu Start key set = 0x02, có nghĩa service đó chạy từ lúc boot

### **SAM hive and user information:**

User account information, login information, group infomation

`SAM\Domains\Account\Users`

- SID 500 = Admin

⇒ Gồm RID ( mã định danh của user), số lần đăng nhập, thời gian đăng nhập lần cuói, lần đăng nhập thất bại gần nhất, lần thay đổi mk cuối, hết hạn mk, policy của pass và hint

sam SAM1 - security SECURITY1 - system SYSTEM1 local

## **Windows NT CurrentVersion**

```c
ROOT/Microsoft/Windows NT/CurrentVersion
```

1. **BuildBranch**: Nhánh xây dựng của hệ điều hành, chẳng hạn như "th1" cho Threshold 1, "rs5_release" cho Redstone 5.
2. **BuildGUID**: GUID (Global Unique Identifier) của bản dựng hiện tại của hệ điều hành.
3. **BuildLabEx**: Thông tin bổ sung về nhánh xây dựng và số hiệu xây dựng.
4. **CurrentBuild**: Số hiệu xây dựng hiện tại của hệ điều hành.
5. **CurrentBuildNumber**: Số hiệu xây dựng hiện tại, thường được sử dụng để xác định phiên bản cụ thể.
6. **CurrentMajorVersionNumber**: Số phiên bản chính hiện tại của hệ điều hành, chẳng hạn như "10" cho Windows 10.
7. **CurrentMinorVersionNumber**: Số phiên bản phụ hiện tại của hệ điều hành, chẳng hạn như "0" cho Windows 10.
8. **CurrentType**: Loại xây dựng hiện tại của hệ điều hành, chẳng hạn như "Multiprocessor Free" hoặc "Checked".
9. **PathName**: Đường dẫn của thư mục hệ thống hiện tại của Windows.
10. **SystemRoot**: Đường dẫn của thư mục hệ thống gốc, thường là **`C:\Windows`**.
11. **ProductIdEx**: Mã sản phẩm mở rộng.
12. **SystemBootDevice**: Thiết bị khởi động hệ thống, thường là ổ cứng chứa hệ điều hành.
13. **SystemStartOptions**: Các tùy chọn khởi động hệ thống, chẳng hạn như "Safe Mode".
14. *BuildLab`: Thông tin về nhánh xây dựng và số hiệu xây dựng.
15. *PathName`: Đường dẫn của thư mục hệ thống hiện tại của Windows.
16. **SystemRoot**: Đường dẫn của thư mục hệ thống gốc, thường là **`C:\Windows`**.
17. **ProductIdEx**: Mã sản phẩm mở rộng.
18. **SystemBootDevice**: Thiết bị khởi động hệ thống, thường là ổ cứng chứa hệ điều hành.
19. **SystemStartOptions**: Các tùy chọn khởi động hệ thống, chẳng hạn như "Safe Mode".
20. **InstallationType**: Loại cài đặt của hệ điều hành, chẳng hạn như "Client" hoặc "Server".

1. **NetworkProvider**: Thông tin về các nhà cung cấp dịch vụ mạng đã được cấu hình trên hệ thống.
2. **Profiles**: Thông tin về các hồ sơ mạng đã được cấu hình trên hệ thống, bao gồm cài đặt mạng không dây và mạng có dây.
3. **Connections**: Cấu hình kết nối mạng, bao gồm các kết nối LAN và Wi-Fi, thông tin về DHCP, DNS, và các cài đặt khác.
4. **LAN**: Thông tin cấu hình cho kết nối mạng LAN (Local Area Network), bao gồm cài đặt IP, cài đặt proxy, và các cài đặt khác.
5. **WAN**: Thông tin cấu hình cho kết nối mạng WAN (Wide Area Network), bao gồm cài đặt kết nối Internet và VPN.
6. **Diagnostics**: Thông tin về các công cụ chẩn đoán mạng, như trạng thái kết nối và thông tin lỗi.
7. **RemoteAccess**: Cài đặt và cấu hình kết nối từ xa, bao gồm các cài đặt VPN và Remote Desktop.
8. **Internet Settings**: Cài đặt liên quan đến trình duyệt Internet Explorer hoặc Microsoft Edge, bao gồm cài đặt proxy và cài đặt kết nối mạng.
