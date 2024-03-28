Menu này cho nhiều thống kê điểu điều tra như

- Protocol
- endpoints
- conversations
- DHCP, DNS, HTTP
- Một bản tóm tắt nhanh về PCAP đã xử lý

# **Resolved Addresses**

Nhận dạng địa chỉ IP và DNS trong file capture → cung cấp các địa chỉ đã phân giải và hostname của nó

```c
Statistics --> Resolved Addresses
```

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/bbdcde51-19e9-428c-b56b-e13d6bc57a7b)

# **Protocol Hierarchy (Protocol Hierarchy)**

Chia nhỏ  tất cả giao thức có sẵn từ capture file → xem ở chế độ xem dạng cây dựa trên packet counters và phần trăm

```c
Statistics --> Protocol Hierarchy
```

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/a740c7e3-2453-49a2-aa96-25570106cdba)

# **Conversations**

Lưu lượng truy cập giữa 2 endpoints 

ở 5 định dạng

- IPv4
- IPv6
- TCP
- UDP
- Ethernet

```c
Statistic --> Conversations
```

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/8104ee52-eb8f-40dc-8915-15a1c8bbbc40)

# Endpoints

Giống conversations, nhưng cung cấp thông tin độc nhất cho mỗi thông tin của 5 trường trên 

```c
"Statistics --> Endpoints"
```

- Nó cũng hỗ trợ phân giải địa chỉ MAC thành tên có thể đọc Name Resolution

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/35550f8a-07b9-4989-8f56-4dee156b8f24)

Name Resolution cung cấp cho cả IP và port name

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/0430db88-9fd6-46fc-8602-0d2d712bf728)

Endpoint menu view with name resolution:

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/08dfb3c2-c253-48c3-9730-f2ec33c96868)

IP Geolocation mapping 

```c
 "Edit --> Preferences --> Name Resolution --> MaxMind database directories"
```

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/389dbf7d-fdd4-4f26-9e9a-bc06269c5fc3)

Endpoints and GeoIP view.

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/3f7447ec-78bf-43ee-a9fe-76d41b29cc11)


# IPv4 and IPv6

```c
"Statistics --> IPvX Statistics"
```
![1](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/3b59c313-7c4d-47bc-9018-d60b73ae3fc1)


**DNS**

- rcode
- opcode
- class
- query type
- service
- querty stats

```c
Statistics --> DNS
```
![2](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/fe057e29-0c24-42e8-9eae-f832320f1374)


**HTTP**

```c
Statistics --> HTTP
```

- Request
- reponse code
- original request
![3](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/1b1275fc-4f7c-4fb8-bbbb-f0d8482fe119)

