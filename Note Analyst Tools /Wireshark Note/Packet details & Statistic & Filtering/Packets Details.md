# Packets details

Owner: Mer

## Packet number

Wireshark, tính toán và gán số thứ tự độc nhất cho một packet

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/a49ccd67-83e9-4e44-9916-47c6d753252d)


## Go to Packet

Sử dụng “GO” menu để xem các gói cụ thể

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/db8cdb8b-533d-44ae-b1ef-9f5255fded61)


## Find Packet

Ngoài stt của packet, wireshark cũng có thể tìm theo nội dung của gói. 

```c
 **Edit --> Find Packet.** 
```

4 loại  dữ liệu có thể tìm

1. Bộ lọc hiển thị
2. Hex
3. String
4. Regex (biểu thức)

String và regex phổ biến nhất. Tìm kiếm sẽ ko phân biệt hoa và thường, nếu muốn có thể chọn radio để phân biệt

CHỌN TRƯỜNG TÌM KIẾM:

Có 3 trường

- Packet list
- Packet details
- Packet bytes

Cần biết thông tin có sẵn trong khung nào để dễ tìm kiếm. Ví dụ cần tìm kiếm Packet detais trong Packet list, wireshark ko tìm được

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/ef91b4c6-30b2-4f26-ad0d-670c8672e718)


# Mark Packets

Đánh dấu gói tin, các gói tin sẽ được đánh dấu màu đen bất kể màu gốc là màu gì. 

LƯU Ý: các gói đưuọc đánh dấu sẽ làm mới mỗi phiên, cho nên sẽ mất sau khi đóng capture file

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/5395754d-5b55-4632-bca9-cb12a4767d78)


# Packet Comments

Giống với Marking, nhưng ko bị mất khi đóng tệp trừ khi xóa

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/f022d2b3-d1ee-47ad-8429-f342539ada6c)


# Export Packets

Capture file có thể chứa hàng nghìn gói trong một tệp. Wireshark ko phải IDS, cho nên đôi khi cần tách gói cụ thể ra khỏi tệp và tìm hiểu sâu hơn, sẽ giúp các nahf phân tích chia sẻ các gói tin supicious duy nhất. Do đó, thông tin dư thừa không được đưa vào quá trình phân tích

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/a6f7084b-481e-4c4b-b671-dff06661485b)


# Export Objects (Files)

Wireshark có thể trích xuất các tập tin được truyền qua dây. Đối với một nhà phân tích bảo mật, điều quan trọng là khám phá các tệp được chia sẻ và lưu chúng để điều tra thêm. Đối tượng xuất chỉ khả dụng cho các luồng của giao thức đã chọn (DICOM, HTTP, IMF, SMB và TFTP).

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/136c6601-5147-408d-b37e-8e98653f0e0e)


# Time Display Format

Hiển thị thời gian bằng giây kể từ lúc bắt đầu Capture

```c
View --> Time Display Format
```

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/13559cf4-e0a9-4a94-a49d-b0233ca9f211)

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/70b0fc03-8787-457e-a404-e6b74315f519)


# Expert Info

Phát hiện các trạng thái của giao thức để giúp tìm ra các vấn đề hay sự cố bất thường 

| Severity | Colour | Info |
| --- | --- | --- |
| Chat | Blue | Thông tin về quy trình làm việc thông thường. |
| Note | Cyan | Notable events like application error codes. (Các sự kiện đáng chú ý như mã lỗi ứng dụng.) |
| Warn | Yellow | Warnings like unusual error codes or problem statements. (Các cảnh báo như mã lỗi bất thường hoặc báo cáo vấn đề.) |
| Error | Red | Problems like malformed packets. (Các vấn đề như gói không đúng định dạng.) |

| Group | Info | Group | Info |
| --- | --- | --- | --- |
| Checksum | Checksum errors. | Deprecated | Deprecated protocol usage. |
| Comment | Packet comment detection. | Malformed | Malformed packet detection. |

```c
Lower left bottom section 
OR
Analyse --> Expert Information
```

nó sẽ hiện ra hộp thoại

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/0bd43950-0a46-46e4-8e2d-da4dccb49872)
