# Autospy

### Supported Disk Image Formats:

- **Raw Single** (For example: *.img, *.dd, *.raw, *.bin)
- **Raw Split** (For example: *.001, *.002, *.aa, *.ab, etc)
- **EnCase** (For example: *.e01, *.e02, etc)
- **Virtual Machines** (For example: *.vmdk, *.vhd)

## **Workflow Overview (Tổng quan)**

### Case Analysis | Create a new case

Tạo new case. 

- Case name
- Base Directory: Thư mục gốc
- Case Type: local - singler user hay host - multi user

### Case Analysic | Open an Existing Case

*Note: case file của autospy = *.aut

Thường sẽ có một box cảnh báo - Nếu nó ko định vị được disk image - Có thể chỉ định trỏ đến vị trí đó - hoặc ấn không vẫn phân tích được

## Data Sources

Autospy có thể phân tích nhiều dạng disk image formats. 

- Raw single: *.img, *.dd, *.raw, *.bin
- Raw Split: *.001, *.002, *.003, *.aa, *.ab,…
- Encase: *.e01, *.e02, etc
- Virtual Machines: *.vmdk, *.vhd

Nếu có nhiều image file (e.i. E01,E02,E03,..) thì chỉ cần trỏ tới cái đầu tiên, còn lại để autospy lo 

## Ingest Modules (nhập Modules)

Phần lớn là các plug-ins. m

## **The User Interface I (Giao diện người dùng)**

### Tree Viewer

Five - top level nodes:

- Data Sources: Tất cả dữ liệu được sắp xếp giống như windows file explorer
- Views: file được sắp xếp dựa trên loại file, MIME types, kích thước,…
- Results: hiện kết quả sau khi Ingest Modules
- Tags: hiện các files hay kết quả được gắn thẻ ở ingest

https://sleuthkit.org/autopsy/docs/user-docs/4.12.0/tagging_page.html

- Reports: báo cáo về modules

https://sleuthkit.org/autopsy/docs/user-docs/4.12.0/reporting_page.html

### **Table Viewers**

Hiển thị nội dung của lựa chọn hiện tại dưới dạng các bảng chi tiết đã  chọn của từng chỉ mục. 

Ex: Đối với tệp sẽ có các thuộc tính: tên, ngày giờ, thay đổi, kích thước, id người dùng, id nhóm, chế độ,….

Có 3 tag

- Table
- Thumbnail: chủ yếu là ảnh
- Summary


![Untitled](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/43f3503b-345a-4133-acc5-cd6c9d65826e)

*Đặc biệt hãy chú ý đến phần này By Extension

![2Untitled](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/622c1500-37e2-471d-83b1-39c0262fbcc2)

Bởi vì attacker có thể đổi file extention, nên file sẽ bị phân loại vào miscategorised (bị phân loại sai) bởi By Extention, nhưng sẽ được phân loại phù hợp theo MIME

vd:

Ví dụ, một tệp tin có thể được đổi tên từ something.exe sang something.jpg → thực tế nó là một tệp thực thi (executable file).

Tuy nhiên, loại MIME (Multipurpose Internet Mail Extensions) là một cách để xác định loại dữ liệu của một tệp tin bằng cách xem nội dung của nó. Kỹ thuật này đặc biệt hữu ích trong việc phát hiện các loại tệp tin bị đổi tên một cách gia

**SCO Columns**
![3](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/baffe11f-6ec0-45b2-b132-f55961044acf)


- (S)core column - Cho biết mục này có đáng chú ý hay không.
    - Màu đỏ  nếu tệp khớp với tập hợp hàm băm đáng chú ý hoặc đã được gắn thẻ đáng chú ý
    - Hiển thị biểu tượng màu vàng nếu tệp có mục phù hợp thú vị hoặc đã được gắn thẻ đáng ngờ
- (C)omment column - cho biết mục này có nhận xét trong Kho lưu trữ trung tâm hay có nhận xét được liên kết với thẻ.
- (O)ther occurrences column -cho biết có bao nhiêu nguồn dữ liệu trong Kho lưu trữ trung tâm chứa mục này. Số lượng sẽ bao gồm mục đã chọn.

**Exporting to CSV**
![4](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/978f3035-5c8e-47fe-b7f7-5de6c33e02b4)


**Thumbnail Viewers**

Ảnh thôi ko có gì

### **Contents Viewer**

Từ table view, nếu ấn vào một file hay folder nào đó nó sẽ hiện rõ content 

![5](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/6aedbe11-36e9-402b-bd32-cb1a8f4ea094)

- S = score

Nếu màu đỏ

- (S)core column - Cho biết mục này có đáng chú ý hay không.
    - Màu đỏ  nếu tệp khớp với tập hợp hàm băm đáng chú ý hoặc đã được gắn thẻ đáng chú ý
    - Hiển thị biểu tượng màu vàng nếu tệp có mục phù hợp thú vị hoặc đã được gắn thẻ đáng ngờ
- (C)omment column - cho biết mục này có nhận xét trong Kho lưu trữ trung tâm hay có nhận xét được liên kết với thẻ.
- (O)ther occurrences column -cho biết có bao nhiêu nguồn dữ liệu trong Kho lưu trữ trung tâm chứa mục này. Số lượng sẽ bao gồm mục đã chọn.

https://sleuthkit.org/autopsy/docs/user-docs/4.12.0/content_viewer_page.html

### **Keyword Search**

![6](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/03c0b257-2d19-47d1-ae5b-e997c109567c)

**Exact Match:** 

Nếu từ cần tìm sẽ luôn gần đúng bới các ký tự không phải từ (space or dấu câu)

ex:

> The quick reddish-brown fox jumps over the lazy dog.
> 
- "quick", "brown", "dog" Oke
- "FOX", "Fox", "fox" Oke
- "reddish-brown fox", "brown fox", "LAZY DOG" Oke
- "rown" and "lazy do" Không được vì không bị dưới hạn bởi các từ cần tìm

**Substring Match:**

ex:

> The quick reddish-brown fox jumps over the lazy dog.
> 
- "jump" will match "jumps", and would also match "jumping", "jumped", etc.
- "dog" will match
- "UMP", "oX" will match
- "y dog", "ish-brown" will not match

**Regex match**

https://sleuthkit.org/autopsy/docs/user-docs/4.12.0/ad_hoc_keyword_search_page.html

Data Sources Summary

Tóm tắt tổng quan 9 loại khác nhau

![7](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/f8ab0703-7e2c-4280-96f3-5a8cc9a61cec)

Generate Report

Có thể tạo Report bằng nhiều format khác nhau

**
Visualisation Tools**

![8](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/4776644f-a304-456d-9193-db14c4e93b4b)

- **Images/Videos:** http://sleuthkit.org/autopsy/docs/user-docs/4.12.0/image_gallery_page.html
- **Communications:** http://sleuthkit.org/autopsy/docs/user-docs/4.12.0/communications_page.html
- **Timeline:** http://sleuthkit.org/autopsy/docs/user-docs/4.12.0/timeline_page.html

Administrator	DefaultAccount	Guest
