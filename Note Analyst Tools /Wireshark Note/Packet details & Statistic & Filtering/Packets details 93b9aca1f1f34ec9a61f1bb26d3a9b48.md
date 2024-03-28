# Packets details

Owner: Mer

## Packet number

Wireshark, tính toán và gán số thứ tự độc nhất cho một packet

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/d52507e87088deb1597042d50900eef0.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/d52507e87088deb1597042d50900eef0.png)

## Go to Packet

Sử dụng “GO” menu để xem các gói cụ thể

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/cdb1e1d12c63fc831c7d94db634bbe0d.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/cdb1e1d12c63fc831c7d94db634bbe0d.png)

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

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/c8811df8ea0fa2b70fa90831d1ec9278.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/c8811df8ea0fa2b70fa90831d1ec9278.png)

# Mark Packets

Đánh dấu gói tin, các gói tin sẽ được đánh dấu màu đen bất kể màu gốc là màu gì. 

LƯU Ý: các gói đưuọc đánh dấu sẽ làm mới mỗi phiên, cho nên sẽ mất sau khi đóng capture file

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/2c290f2f3c7b07223c86cd066751d19b.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/2c290f2f3c7b07223c86cd066751d19b.png)

# Packet Comments

Giống với Marking, nhưng ko bị mất khi đóng tệp trừ khi xóa

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/844bedc49bdd7dcaf26861a9cd2658fd.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/844bedc49bdd7dcaf26861a9cd2658fd.png)

# Export Packets

Capture file có thể chứa hàng nghìn gói trong một tệp. Wireshark ko phải IDS, cho nên đôi khi cần tách gói cụ thể ra khỏi tệp và tìm hiểu sâu hơn, sẽ giúp các nahf phân tích chia sẻ các gói tin supicious duy nhất. Do đó, thông tin dư thừa không được đưa vào quá trình phân tích

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/86daa70b6cb8b93cb11535787222fb26.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/86daa70b6cb8b93cb11535787222fb26.png)

# Export Objects (Files)

Wireshark có thể trích xuất các tập tin được truyền qua dây. Đối với một nhà phân tích bảo mật, điều quan trọng là khám phá các tệp được chia sẻ và lưu chúng để điều tra thêm. Đối tượng xuất chỉ khả dụng cho các luồng của giao thức đã chọn (DICOM, HTTP, IMF, SMB và TFTP).

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/16c22447c36bff2e415ea75a764854c8.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/16c22447c36bff2e415ea75a764854c8.png)

# Time Display Format

Hiển thị thời gian bằng giây kể từ lúc bắt đầu Capture

```c
View --> Time Display Format
```

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/53bb9769af677eede39a3ec9e1b368a3.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/53bb9769af677eede39a3ec9e1b368a3.png)

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/d2333318ff4df99df252c6ee1c236619.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/d2333318ff4df99df252c6ee1c236619.png)

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

![https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/31917b6f1e846d3383218cabf1c07caf.png](https://tryhackme-images.s3.amazonaws.com/user-uploads/6131132af49360005df01ae3/room-content/31917b6f1e846d3383218cabf1c07caf.png)