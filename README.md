### Digital Forensic and Incident reponse

### The need for DFIR

Tìm evidence (bằng chứng) về hoạt động của attacker và sàng lọc các thông báo sai từ các sự cố thực tế

Loại bỏ attacker ra khỏi hệ thống network

Xác định mức độ - thời gian vi phạm

Tìm ra sơ hở dẫn đến vi phạm - biện pháp

hiểu hành vi của attacker

### Artifact

bằng chứng hoạt động diễn ra trên hệ thống. Khi tiến hành DFIR, Artifact được thu nhập để hỗ trợ các giải thuyết về hoạt động của attacker trên hệ thống.

EX: 

Nếu chúng ta khẳng định Attacker sử dụng Window register key để duy trì (**PERSISTENCE**), thì chúng ta có thể sử dụng lại key nói trên để hỗ trợ cho quá trình ứng phó sự cố. Trong trường hợp này, Window register Key chính là Artifact

Artifact có thể được thu nhập thông qua các thiết bị Endpoint, Server’s file system, memory, network activity

### **Evidence Preservation**

Khi tiếnh hành DFIR, chúng ta phải đảm bảo duy trì sự toàn vẹn (**integrity**) của bằng chứng thu nhập được,

Vì mọi tiến trình điều tra, hay phân tích đều ảnh hưởng đến bằng chứng (Evidence). Cho nên cần copy chứng cứ, và tiến hành điều tra chỉ phần copy, để bảo đảm tính toàn vẹn cho bằng chứng

### **Chain of custody:**

Một khía cạnh khác của tính toàn vẹn (**integrity**) bằng chứng đó là Chuỗi hành trình (Chain of custody). Khi bằng chứng được thu nhập, nó phải chắc chắn được giám hộ an toàn. Ai không liên quan không có quyền với bằng chứng

### **Order of volatility:**

Các bằng chứng kỹ thuật số (**Digital evidence**) thường không ổn định, có thể biến mất bất kỳ lúc nào nếu không bắt kịp thời

Ex: Dữ liệu trong ram sẽ biến mất khi máy tính shut down, bởi vì Ram chỉ dữ data khi máy tính bật, Còn dữ liệu cho đĩa cứng sẽ được duy trì kể cả khi ko có điện, Do đó khi tiến hành DFIR, chúng ta phải hiểu thứ tự biến động của dữ liệu để thu nhập kịp thời, Trong ví dụ trên, chúng ta cần thu nhập dữ liệu của RAM trước, sau đó mới tới đĩa cứng

### **Timeline creation:**

Khi tiến hành thu nhập Artifacts và duy trì tính toàn vẹnn, chúng ta cần trình bày chúng một cách dễ hiểu những thông tin đã thu nhập được. Một dòng thời gian về các sự kiện diễn ra rất cần thiết để tăng độ hiệu quả và chính xác khi phân tích. Timeline of Event này sẽ đẩy các sự kiện vào một dòng thời gian thống nhất → Timeline creation

→ cung cấp góc nhìn cho cuộc điều tra và giúp đối chiếu thông tin từ nhiều nguồn khác nhau để hiểu về cách mọi việc đã xảy ra.

### The Incident Response process

1. Preparation  (Chuẩn bị): Chuẩn bị sẵn sàng trong trường hợp ảy ra sự cố, về mặt con người, quy trình, công nghệ
2. Identification (Nhận dạng): qua một số chỉ số, rồi lấy nó phân tích
3. Containment (Ngăn chặn): Sự cố được ngăn chặn và hạn chế ảnh hưởng của nó, biện pháp ở đây có thể dài hạn hoặc ngắn hạn
4. Eradication (Loại bỏ): Mối đe dọa sẽ bị xóa khỏi mạng. Phải đảm bảo rằng phân tích nó trước khi xóa
5. Recovery (Phục hồi): hệ thống hay các dịch vụ phải được quay về tình trạng ban đầu trước khi xảy ra sự cố
6. Lessons Learned (Rút kinh nghiêm):  có thể là tài liệu về sự cố dựa trên cách tìm ra sự cố để chuẩn bị tốt hơn cho các lần sau

⇒ **PICERL**