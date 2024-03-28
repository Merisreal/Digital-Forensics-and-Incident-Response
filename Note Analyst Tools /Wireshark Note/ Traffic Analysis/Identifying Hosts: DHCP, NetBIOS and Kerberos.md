# Identifying Hosts

Khi điều tra hoạt động xâm phạm hoặc (HOST) lây nhiễm phần mềm độc hại, nhà phân tích bảo mật nên biết cách xác định các máy chủ trên mạng ngoài việc khớp địa chỉ IP với MAC. Một trong những phương pháp tốt nhất là xác định máy chủ  và người dùng (HOST & USERS) trên mạng để quyết định điểm bắt đầu điều tra và liệt kê các máy chủ và người dùng có liên quan đến lưu lượng/hoạt động độc hại.

Thông thường, mạng doanh nghiệp sử dụng mẫu được xác định trước để đặt tên cho người dùng và máy chủ. Mặc dù điều này làm cho việc biết và theo dõi dễ dàng hơn nhưng nó cũng có những mặt tốt và mặt xấu. Mặt tốt là sẽ dễ dàng xác định người dùng hoặc máy chủ bằng cách nhìn vào tên. Mặt xấu là nó sẽ dễ dàng sao chép mô hình đó và tồn tại trong mạng doanh nghiệp dành cho đối thủ. Có nhiều giải pháp để tránh những loại hoạt động này, nhưng đối với một nhà phân tích bảo mật, điều cần thiết là phải có kỹ năng nhận dạng máy chủ và người dùng.

Các giao thức có thể được sử dụng trong nhận dạng Máy chủ và Người dùng:

- Dynamic Host Configuration Protocol (DHCP) traffic
- NetBIOS (NBNS) traffic
- Kerberos traffic

**DHCP**

**DHCP** protocol, or **D**ynamic **H**ost **C**onfiguration **P**rotocol **(DHCP)** là công nghệ chịu trách nhiệm quản lý địa chỉ IP tự động và chỉ định các tham số giao tiếp bắt buộc.

**DHCP investigation in a nutshell:**

| Notes | Wireshark Filter |
| --- | --- |
| Global search. | • dhcp or bootp |
| Filtering the proper DHCP packet options is vital to finding an event of interest. 
• "DHCP Request" packets contain the hostname information
• "DHCP ACK" packets represent the accepted requests
• "DHCP NAK" packets represent denied requests
 Do tính chất của giao thức, chỉ "Option  53" (loại yêu cầu) có các giá trị tĩnh được xác định trước. Trước tiên, bạn nên lọc loại gói, sau đó bạn có thể lọc các tùy chọn còn lại bằng cách "applying as column" hoặc sử dụng các bộ lọc nâng cao như "contains" và "matches". | • Request: dhcp.option.dhcp == 3
• ACK: dhcp.option.dhcp == 5
• NAK: dhcp.option.dhcp == 6 |
| "DHCP Request" options for grabbing the low-hanging fruits:
• Option 12: Hostname.
• Option 50: Requested IP address.
• Option 51: Requested IP lease time.
• Option 61: Client's MAC address. | • dhcp.option.hostname contains "keyword" |
| "DHCP ACK" options for grabbing the low-hanging fruits:
• Option 15: Domain name.
• Option 51: Assigned IP lease time. | • dhcp.option.domain_name contains "keyword" |
| "DHCP NAK" options for grabbing the low-hanging fruits:
• Option 56: Message (rejection details/reason). | As the message could be unique according to the case/situation, It is suggested to read the message instead of filtering it. Thus, the analyst could create a more reliable hypothesis/result by understanding the event circumstances. |
![1](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/ab732b0e-2ace-4f1c-90e4-dbb2aff694d3)


# NetBIOS (NBNS) Analysis

**NetBIOS** or **Net**work **B**asic **I**nput/**O**utput **S**ystem is the technology responsible for allowing applications on different hosts to communicate with each other.

**NetBIOS** or **Net**work **B**asic **I**nput/**O**utput **S**ystem là công nghệ chịu trách nhiệm cho phép các ứng dụng trên các máy chủ khác nhau giao tiếp với nhau.

**NBNS investigation in a nutshell:**

| Notes | Wireshark Filter |
| --- | --- |
| Global search. | • nbns |
| "NBNS" options for grabbing the low-hanging fruits:
• Queries: Query details.
• Query details could contain "name, Time to live (TTL) and IP address details" | • nbns.name contains "keyword" |

![2](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/5fb799ab-8a36-40d5-8358-63d763a9e178)

nbns.flags.opcode == {the query type} if you want to look for particular NBNS packet types. You can either use the numerical value of the field, e.g. 

0 of a query, 5 for a registration,

 6 for a release, 

7 for wait for acknowledgement, 

8 for refresh, 9 for alternate refresh, 

and 15 for multi-homed registration, 

or you can put the descriptive name in quotes, e.g. "Name query", "Registration", "Release", etc..

# Kerberos

Kerberos là dịch vụ xác thực mặc định cho miền Microsoft Windows. Nó chịu trách nhiệm xác thực các yêu cầu dịch vụ giữa hai hoặc nhiều máy tính qua mạng không tin cậy. Mục đích cuối cùng là để chứng minh danh tính một cách an toàn.

**Kerberos investigation in a nutshell:**

| Notes | Wireshark Filter |
| --- | --- |
| Global search. | • kerberos |
| User account search:
• CNameString: The username.
Note: Some packets could provide hostname information in this field. To avoid this confusion, filter the "$" value. The values end with "$" are hostnames, and the ones without it are user names. | • kerberos.CNameString contains "keyword" 
• kerberos.CNameString and !(kerberos.CNameString contains "$" ) |
| "Kerberos" options for grabbing the low-hanging fruits:
• pvno: Protocol version.
• realm: Domain name for the generated ticket.
• sname: Service and domain name for the generated ticket.
• addresses: Client IP address and NetBIOS name.
Note: the "addresses" information is only available in request packets. | • kerberos.pvno == 5
• kerberos.realm contains ".org" 
• kerberos.SNameString == "krbtg" |
![3](https://github.com/Merisreal/Digital-Forensics-and-Incident-Response/assets/139641711/b7960791-a71e-4c3b-802b-98d143997dfa)

