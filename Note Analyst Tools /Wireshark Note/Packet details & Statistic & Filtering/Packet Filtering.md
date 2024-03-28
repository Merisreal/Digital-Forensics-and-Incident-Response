# Packet Filtering

có hai loại bộ lọc trong Wireshark. Mặc dù cả hai đều sử dụng cú pháp giống nhau nhưng chúng được sử dụng cho các mục đích khác nhau. 

| Capture Filters |  Loại bộ lọc này được sử dụng để chỉ lưu một phần lưu lượng cụ thể. Nó được đặt trước khi capture lưu lượng truy cập và không thể thay đổi trong quá trình chụp. |
| --- | --- |
| Display Filters | Loại bộ lọc này được sử dụng để điều tra các gói bằng cách giảm số lượng gói hiển thị và nó có thể thay đổi trong quá trình chụp. |

không thể sử dụng biểu thức bộ lọc hiển thị để nắm bắt lưu lượng truy cập và ngược lại.

→ Thông thường → Capturing mọi thứ → filtering các gói theo sự kiện đang quan tâm 

hay

→ Capture filter and sniff traffic → khó hơn

# Capture Filter Syntax

- **Scope**: host, net, port and portrange.
- Direction: src, dst, src or dst, src and dst,
- Protocol: ether, wlan, ip, ip6, arp, rarp, tcp and udp.
- **Sample filter to capture port 80 traffic:** `tcp port 80`

```c
Capture --> Capture Filters
```

https://gitlab.com/wireshark/wireshark/-/wikis/CaptureFilters#useful-filters

https://www.wireshark.org/docs/man-pages/pcap-filter.html

```c
Examples
Capture only traffic to or from IP address 172.18.5.4:

host 172.18.5.4

Capture traffic to or from a range of IP addresses:

net 192.168.0.0/24

or

net 192.168.0.0 mask 255.255.255.0

Capture traffic from a range of IP addresses:

src net 192.168.0.0/24

or

src net 192.168.0.0 mask 255.255.255.0

Capture traffic to a range of IP addresses:

dst net 192.168.0.0/24

or

dst net 192.168.0.0 mask 255.255.255.0

Capture only DNS (port 53) traffic:

port 53

Capture non-HTTP and non-SMTP traffic on your server (both are equivalent):

host www.example.com and not (port 80 or port 25)

host www.example.com and not port 80 and not port 25

Capture except all ARP and DNS traffic:

port not 53 and not arp

Capture traffic within a range of ports

(tcp[0:2] > 1500 and tcp[0:2] < 1550) or (tcp[2:2] > 1500 and tcp[2:2] < 1550)

or, with newer versions of libpcap (0.9.1 and later):

tcp portrange 1501-1549

Capture only Ethernet type EAPOL:

ether proto 0x888e

Reject ethernet frames towards the Link Layer Discovery Protocol Multicast group:

not ether dst 01:80:c2:00:00:0e

Capture only IPv4 traffic - the shortest filter, but sometimes very useful to get rid of lower layer protocols like ARP and STP:

ip

Capture only unicast traffic - useful to get rid of noise on the network if you only want to see traffic to and from your machine, not, for example, broadcast and multicast announcements:

not broadcast and not multicast

Capture IPv6 "all nodes" (router and neighbor advertisement) traffic. Can be used to find rogue RAs:

dst host ff02::1

Capture HTTP GET requests. This looks for the bytes 'G', 'E', 'T', and ' ' (hex values 47, 45, 54, and 20) just after the TCP header. "tcp[12:1] & 0xf0) >> 2" figures out the TCP header length. From Jefferson Ogata via the tcpdump-workers mailing list.

port 80 and tcp[((tcp[12:1] & 0xf0) >> 2):4] = 0x47455420
```

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/183da800-c81d-4bf6-843c-20a350d713e5)

# Display Filter Syntax

https://www.wireshark.org/docs/dfref/

- **Sample filter to capture port 80 traffic: `tcp.port == 80`**

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/a3bb4ec9-870b-44fc-b1c6-7eeffc8e079c)

**Comparison Operators**

| English | C-Like | Description | Example |
| --- | --- | --- | --- |
| eq | == | Bằng | ip.src == 10.10.10.100 |
| ne | != | Ko bằng | ip.src != 10.10.10.100 |
| gt | > | Lớn hơn | ip.ttl > 250 |
| lt | < | Nhỏ hơn  | ip.ttl < 10 |
| ge | >= | Lớn hơn hoặc bằng  | ip.ttl >= 0xFA |
| le | <= | Nhỏ hơn hoặc bằng | ip.ttl <= 0xA |

| English | C-Like | Description | Example |
| --- | --- | --- | --- |
| and | && | AND | (ip.src == 10.10.10.100) AND (ip.src == 10.10.10.111) |
| or | || | OR | (ip.src == 10.10.10.100) OR (ip.src == 10.10.10.111) |
| not | ! | NOT | !(ip.src == 10.10.10.222)
Note: ko nên dùng !=value  → nên dùng !(value) |

**Note:** Wireshark supports decimal and hexadecimal values in filtering. You can use any format you want according to the search you will conduct.

# Packet Filter Toolbar

| Green | Hợp lí  |
| --- | --- |
| Red | Ko ổn |
| Yellow | hơi hợp lí á nhưng cần sửa lại cho hợp lí |

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/a715521e-9487-4a8e-a804-7c1b2f445ffc)

Filter toolbar features are shown below.

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/74471e73-dcc6-4cd9-857b-fe33848744df)

# Protocol Filters

Wireshark supports 3000 protocols and allows packet-level investigation by filtering the protocol fields. 

# IP Filters

- IP address
- Version
- Time to live TTP
- Type of service
- Flag
- checksum value

| Filter | Description |
| --- | --- |
| ip | Hiện IP packet |
| ip.addr == 10.10.10.111 | Hiển thị tất cả các packet chứa địa chỉ IP 10.10.10.111. |
| ip.addr == 10.10.10.0/24 | Hiển thị tất cả các gói chứa địa chỉ IP từ mạng con 10.10.10.0/24. |
| ip.src == 10.10.10.111 | Hiển thị tất cả các gói có nguồn gốc từ 10.10.10.111
 |
| ip.dst == 10.10.10.111 | Hiển thị tất cả các gói được gửi đến 10.10.10.111
 |
| ip.addr vs ip.src/ip.dst | Note: ip.addr lọc lưu lượng ko cần xem hướng - ip.src/ip.dst lọc theo hướng gói |

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/f86627ea-5f44-4474-af0b-d035adab686c)

# **TCP and UDP Filters**

Transport in OSI

- Source & des ports
- sequence number
- acknowledgement number
- windows size
- timestamps
- flags
- length
- protocol errors.

| Filter | Description | Filter | Expression |
| --- | --- | --- | --- |
| tcp.port == 80 | Hiện tất cả  TCP packet ở port 80 | udp.port == 53 | Hiện tất cả  UDP packet ở port 53 |
| tcp.srcport == 1234 | Hiển thị tất cả các gói TCP có nguồn gốc từ cổng 1234
 | udp.srcport == 1234 | Hiển thị tất cả các gói UDP có nguồn gốc từ cổng 1234
 |
| tcp.dstport == 80 | Hiển thị tất cả các gói TCP được gửi tới cổng 80
 | udp.dstport == 5353 | Hiển thị tất cả các gói UDP được gửi tới cổng 5353
 |

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/637d5f0b-503f-48c0-adb0-80c7fe561a2c)

# Application Level Protocol Filters | and DNS

Application layer of the OSI model 

- payload
- linked data
- depending on the protocol type

| Filter | Description | Filter | Description |
| --- | --- | --- | --- |
| http | Show all HTTP packets | dns | Show all DNS packets |
| http.response.code == 200 | Show all packets with HTTP response code "200" | dns.flags.response == 0 | Show all DNS requests |
| http.request.method == "GET" | Show all HTTP GET requests | dns.flags.response == 1 | Show all DNS responses |
| http.request.method == "POST" | Show all HTTP POST requests | dns.qry.type == 1 | Show all DNS "A" records |

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/22fdc116-1b8e-44fb-9c9e-92729297be24)

# Display Filter Expressions

Wireshark có bộ Built-in option (Display filter experesstions)

```c
Analyse --> Display Filter Expression
```

![image](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/73399c4d-5a86-46ad-994f-1cb8dac1cd9e)
