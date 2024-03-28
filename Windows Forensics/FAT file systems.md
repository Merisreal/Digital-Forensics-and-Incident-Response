# FAT file systems

Các thiết bị lưu trữ trong máy tính, usb,hard disk,.. chỉ là một tập hợp các bit → Cần phải được tổ chức lại để ra thông tin → Tạo ra hệ thống các tệp khác nhau sắp xếp các bit trong ổ theo 1 tiêu chuẩn, để có thể hiểu được thông tin đang lưu trữ

## **The File Allocation Table (FAT):**

Tạo ra một bảng chỉ mục vị trí của các bit được phân bổ cho các tệp khác nhau

Data Structures of FAT file system

Cluster:

Cụm hay Cluster đơn vị lưu trữ cơ bản của FAT file systems. Mỗi tệp được lưu trữ trên các thiết bị có thể coi là một nhóm các cụm (Cluster) chứa các bit thông tin 

Directory:

Chứa thông tin về nhận dạng file: Tên file, nơi bắt đầu của Cluster, chiều dài filename

File Allocation Table:

Là một linked list của tất cả các cụm. Chứa trạng thái của cụm và con trỏ tới cụm tiếp theo trong chain

Tóm lại: 

- Các bit → Tập tin → Lưu trong các Cluster
- Tất cả tên tập, cụm bắt đầu, độ dại → Lưu trong Directory
- Vị trí của từng cụm → lưu trong File Allocation Table

![a](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/9db87a86-7bcb-4d47-a4a9-982fe22c280c)

⇒ MAXIMUN FILE SIZE IN FAT 32 = 4Gb

ExFAT được sử dụng cho SD cards
