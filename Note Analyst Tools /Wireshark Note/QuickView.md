Dữ liệu gói tin (packet) sẽ từ **Layer 5 đến layer 7** dựa trên mô hình OSI 
![Untitled](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/cae68f14-56b6-415e-b413-c42328b462dd)


![Untitled 1](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/d7a79b3c-cafe-449c-950b-35ca771536d4)

**The Frame (Layer 1):**Thể hiện đang xem khung/gói tin ( frame/packet ) nào và các chi tiết cho layer physical OSI model 
![9d23e2081fa68e7d6f602aa8b0d316d9](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/04b96f75-c9bf-47f8-b062-514601fe2e41)


**Source [MAC] (Layer 2):**  Thể hiện địa chỉ nguồn và địa chỉ đích của Mac từ layer Data link của OSI

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/a5cfa9b7-fdaa-4383-8695-22a2b2b1a320)

**Source [IP] (Layer 3):** . Thể hiện địa chỉ IPv4 của nguồn và đích, từ tần Network

![Untitled 2](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/c8896a15-8047-4d6e-b623-e3ebe89c598e)

**Protocol (Layer 4):** Thể hiện thông tin chi tiết về giao thức sử dụng (UDP/TCP) cũng như cổng nguồn và đích, từ lớp Transport

![c373f8492470524a8f01fded43856a27](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/ffb27b39-d0da-493e-a9e0-ca2bc8c82731)

**Protocol Errors:**  Phần tiếp theo của layer 4 hiển thị các phân đoạn cụ thể từ TCP cần được tập hợp lại trong giao thức TCP, dữ liệu được chia thành các phân đoạn (segments) để truyền đi và sau đó được tập hợp lại tại điểm đích.
![23bbe6ae6e8168cd0662998ff444b067](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/89c1b875-cd29-49f7-bcc9-a16c7a728300)


**Application Protocol (Layer 5):**. Thể hiện thông tin cụ thể về giao thức sử dụng, HTTP,FTP & SMP. Từ lớp Application 

![879aea2816018d27769fc8490e4af51b](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/005f9f41-a581-4d9d-9e4a-444eb3a4799b)

**Application Data:**  Phần mở rộng, thể hiện dữ liệu dành riêng cho ứng dụng 
![c2d9c3ce498c6f9044413b68df287c14](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/b7539166-ad5f-4066-bd64-0e012490c9b2)

