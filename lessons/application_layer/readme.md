## Application Layer – Cheatsheet  

### **Key Concepts to Remember**  
- **Topmost layer** in OSI and TCP/IP models, interacting with user applications.  
- Provides **network services** like web browsing, email, and file transfer.  
- Uses **protocols** for communication between processes on different hosts.  
- Handles **data formatting, encryption, compression, and authentication.**  

### **Common Protocols & Ports**  

| **Protocol** | **Purpose** | **Port(s)** |
|-------------|------------|-------------|
| **HTTP** | Web browsing | 80 |
| **HTTPS** | Secure web browsing | 443 |
| **FTP** | File transfer | 20, 21 |
| **SFTP** | Secure file transfer | 22 |
| **SMTP** | Sending emails | 25, 465, 587 |
| **POP3** | Retrieving emails | 110, 995 |
| **IMAP** | Email retrieval with sync | 143, 993 |
| **DNS** | Resolves domain names | 53 |
| **DHCP** | Assigns IP addresses dynamically | 67, 68 |
| **Telnet** | Remote login (unencrypted) | 23 |
| **SSH** | Secure remote login | 22 |
| **SNMP** | Network management | 161, 162 |

### **Service Models**  
- **Client-Server:** Clients request services from a central server (e.g., web browsing).  
- **Peer-to-Peer (P2P):** Devices communicate directly without a central server (e.g., BitTorrent).  

### **Key Differences**  
- **Stateless Protocols:** Do not retain session info (e.g., HTTP).  
- **Stateful Protocols:** Maintain session state (e.g., FTP).  

### **Important Concepts**  
- **Encapsulation:** Application data is encapsulated into transport layer segments.  
- **DNS Resolution:** Converts domain names to IP addresses.  
- **Email Services:** SMTP (sending), POP3/IMAP (retrieving).  
- **File Transfers:** FTP (unencrypted), SFTP (secure).  

---

## Application Layer in Computer Networks  

### Overview  
The **Application Layer** is the topmost layer of the OSI and TCP/IP models, responsible for providing network services to end-users and applications. It enables communication between software applications running on different hosts.  

### Functions  
- Provides **interface** between user applications and the network  
- Supports **message exchange** between processes on different hosts  
- Uses **protocols** for communication (HTTP, FTP, SMTP, etc.)  
- Handles **data encoding, encryption, and compression**  
- Supports **authentication and authorization** mechanisms  

### Key Protocols  

| **Protocol** | **Purpose** | **Port(s)** |
|-------------|------------|-------------|
| **HTTP** (Hypertext Transfer Protocol) | Web browsing | 80 |
| **HTTPS** (HTTP Secure) | Secure web browsing (TLS/SSL) | 443 |
| **FTP** (File Transfer Protocol) | File transfer | 20, 21 |
| **SFTP** (Secure FTP) | Secure file transfer (SSH-based) | 22 |
| **SMTP** (Simple Mail Transfer Protocol) | Sending emails | 25, 465 (SSL), 587 (TLS) |
| **POP3** (Post Office Protocol v3) | Retrieving emails | 110, 995 (SSL) |
| **IMAP** (Internet Message Access Protocol) | Email retrieval with sync | 143, 993 (SSL) |
| **DNS** (Domain Name System) | Resolves domain names to IP addresses | 53 |
| **DHCP** (Dynamic Host Configuration Protocol) | Assigns IP addresses dynamically | 67 (server), 68 (client) |
| **Telnet** | Remote login (unencrypted) | 23 |
| **SSH** (Secure Shell) | Secure remote login | 22 |
| **SNMP** (Simple Network Management Protocol) | Network device management | 161 (queries), 162 (traps) |

### Services Provided  
- **Network Virtual Terminal:** Allows remote login via protocols like SSH, Telnet  
- **File Transfer, Access, and Management:** Supported via FTP, SFTP, TFTP  
- **Mail Services:** Handled by SMTP, POP3, IMAP  
- **Directory Services:** Maintained by DNS, LDAP  
- **Remote Administration:** Enabled via SSH, Telnet  

### Key Concepts  
- **Client-Server Model:** Most application layer protocols follow a client-server architecture (e.g., web browsers and web servers).  
- **Peer-to-Peer Model:** Direct communication between devices without a central server (e.g., BitTorrent).  
- **Stateless vs. Stateful Protocols:**  
  - Stateless: Server does not maintain session information (e.g., HTTP).  
  - Stateful: Server maintains client session (e.g., FTP).  
- **Encapsulation:** Application layer data is encapsulated into transport layer segments before transmission.  
