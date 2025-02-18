## Transport Layer – Cheatsheet  

### **Key Concepts to Remember**  
- Ensures **end-to-end communication** between applications.  
- Manages **segmentation, flow control, error detection, and multiplexing**.  
- Uses **port numbers** to identify applications.  
- Supports **connection-oriented (TCP) and connectionless (UDP) communication**.  

### **Protocols & Differences**  

| **Protocol** | **Type** | **Reliability** | **Usage** |
|-------------|---------|---------------|----------|
| **TCP** | Connection-oriented | Reliable (ack, retransmission) | Web, Email, File Transfer |
| **UDP** | Connectionless | Unreliable | Streaming, VoIP, DNS, Gaming |

### **TCP Features**  
- **3-Way Handshake:** SYN → SYN-ACK → ACK  
- **4-Way Termination:** FIN → ACK → FIN → ACK  
- **Flow Control:** Sliding window mechanism  
- **Congestion Control:** Slow start, congestion avoidance, fast retransmit  

### **UDP Features**  
- **No connection establishment, no retransmission**  
- **Faster and lightweight**, used in real-time applications  

### **Port Numbers**  

| **Type** | **Range** | **Examples** |
|----------|--------|------------|
| **Well-Known** | 0 – 1023 | HTTP (80), FTP (21), SMTP (25) |
| **Registered** | 1024 – 49151 | Custom applications |
| **Dynamic/Private** | 49152 – 65535 | Temporary connections |

### **Important Terms**  
- **Socket:** IP address + Port number  
- **Multiplexing:** Multiple apps use the same protocol via different ports  
- **Checksum:** Error detection in TCP & UDP  

---

## Transport Layer in Computer Networks  

### Overview  
The **Transport Layer** is responsible for **end-to-end communication**, ensuring reliable or efficient data transfer between devices. It operates between the Application and Network layers and manages **segmentation, flow control, error handling, and multiplexing**.  

### Functions  
- **Segmentation & Reassembly:** Divides large messages into smaller segments and reassembles them at the receiver.  
- **Flow Control:** Prevents data overflow by managing data transmission rate (e.g., TCP sliding window).  
- **Error Detection & Correction:** Ensures data integrity through checksums.  
- **Multiplexing & Demultiplexing:** Uses port numbers to differentiate multiple communication sessions.  
- **Connection Management:** Establishes, maintains, and terminates connections (e.g., TCP 3-way handshake).  

### Key Protocols  

| **Protocol** | **Type** | **Reliability** | **Usage** |
|-------------|---------|---------------|----------|
| **TCP** (Transmission Control Protocol) | Connection-oriented | Reliable | Web browsing, emails, file transfer |
| **UDP** (User Datagram Protocol) | Connectionless | Unreliable | Streaming, VoIP, DNS, gaming |

### TCP vs. UDP  

| Feature | **TCP** | **UDP** |
|---------|--------|--------|
| **Connection** | Connection-oriented | Connectionless |
| **Reliability** | Reliable (acknowledgments, retransmission) | Unreliable (no retransmission) |
| **Speed** | Slower due to overhead | Faster due to minimal overhead |
| **Error Handling** | Yes (checksums, retransmission) | Limited (only checksum) |
| **Flow Control** | Yes (sliding window) | No |
| **Example Use** | HTTP, FTP, SMTP | VoIP, DNS, Video Streaming |

### TCP Operations  
- **3-Way Handshake:** Establishes a connection (SYN → SYN-ACK → ACK).  
- **4-Way Termination:** Closes a connection (FIN → ACK → FIN → ACK).  
- **Congestion Control:** Manages network traffic using **slow start, congestion avoidance, fast retransmit**.  

### UDP Characteristics  
- **No handshake, no retransmission**, making it lightweight.  
- Best for **real-time applications** like VoIP, DNS, and online gaming.  

### Port Numbers  

| **Type** | **Port Range** | **Example Usage** |
|----------|--------------|------------------|
| Well-Known Ports | 0 – 1023 | HTTP (80), FTP (21), SMTP (25) |
| Registered Ports | 1024 – 49151 | Custom applications |
| Dynamic/Private Ports | 49152 – 65535 | Temporary connections |

### Important Concepts  
- **Socket:** Combination of IP address and port number.  
- **Multiplexing:** Multiple apps use the same transport protocol by assigning unique ports.  
- **Checksum:** Used for error detection in both TCP and UDP.  
