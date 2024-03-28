# Evidence of Execution

### **UserAssist:**

Các ứng dụng chạy bởi người dùng sử dụng Windows Explorer 

- Khi nào áp chạy
- Thời gian sử dụng
- Số lần nó executed

⇒ Tuy nhiên nếu sử dụng command line nó sẽ ko thể tìm được ở đây

`NTUSER.DAT\Software\Microsoft\Windows\Currentversion\Explorer\UserAssist\{GUID}\Count`

### **ShimCache (Application Compatibility Cache (AppCompatCache).)**

Theo dõi khả năng tương thích của ứng dụng với hệ điều hành → Đảm bảo khả năng tương thích ngược của các ứng dụng 

Ví dụ: khi một ứng dụng chạy trên win 7, nhưng vẫn muốn nó chạy trên win 10 → Xảy ra vấn đề tương thích trong cách các API xử lý → Cần ShimCache để phân tích và điều chỉnh phù hợp với HDH hiện tại

`SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache`

→ Chứa file name, size, lần cuối chỉnh sửa 

### **AmCache:**

Liên quan đến Shimcache, lưu trữ giống Shimcahe → liên quan đến việc excutions của ứng dụng 

- Excution path
- íntallation
- excution
- deletion times
- SHA1h

`C:\Windows\appcompat\Programs\Amcache.hve`

Last Executed:

`Amcache.hve\Root\File\{Volume GUID}\`

### **BAM/DAM: (Full path of ex programs)**

BAM: Hoạt động của các ứng dụng nền. 

DAM: tối ưu mức tiêu thụ điện của thiết bị

`SYSTEM\CurrentControlSet\Services\bam\UserSettings\{SID}`'

`SYSTEM\CurrentControlSet\Services\dam\UserSettings\{SID}`
