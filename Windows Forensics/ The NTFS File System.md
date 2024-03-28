# The NTFS File System

### Journaling

Lưu log với những thay đổi trong ổ đĩa → GIúp recover lại khi bị crash hay data movement do phân mảnh

⇒ $LOGFILE

### Access Controls

Dựa trên owner của file/directory và đặc quyền cho mỗi user

### Volume Shadow copy

Theo dõi các thay đổi với tệp bằng Volume Shadow Copy → có thể restore lại phiên bản trước đó của hệ thống

⇒ Do đó ransomware hiện nay thường xóa đi các bảng volume shadow copy

### Alternate Data Streams

⇒ nhiều luồng dữ liệu được lưu trong một tệp duy nhất

## Master File Table

Giống với File Allocation table, nhưng nó ngon hơn. Các thông tin sau có thể tìm ở MFT

$MFT

Bản ghi đầu tiên của ổ đĩa. The Volume Boot Record (VBR) trỏ tới cluster nơi nó được đặt. 

Chứa các thông tin về các cụm nơi đặt tất cả các object đang hiện tại trên tệp. Tệp này chứa một thư mục của các file đang trên ổ đĩa

$LOGFILE

Nhật ký logging của hệ thống. Duy trì tính toàn vẹn khi hệ thống xảy ra sự cố

$UsnJrnl

Update sequence number (USN) journal → Ở $extend record.

Chứa thông tin về tất cả thay đổi của file và lí do khi thay đổi → change journey

$Boot

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/db9f337f-0218-4c3a-a5c2-11d496aa7dc0)
