## Link Layer – Cheatsheet  

### **Key Concepts to Remember**  
- Ensures **node-to-node data transfer** within a single network.  
- Handles **framing, error detection, flow control, and MAC addressing**.  
- Works on the **physical link** level for data transfer.  

### **Key Protocols & Technologies**  

| **Protocol/Technology** | **Purpose** |
|------------------------|------------|
| **Ethernet** | Common LAN technology with MAC addressing and framing. |
| **PPP (Point-to-Point Protocol)** | Point-to-point communication, often used in dial-up. |
| **Frame Relay** | WAN technology for leased line data transfer. |
| **HDLC (High-Level Data Link Control)** | Point-to-point and multipoint communication. |
| **Wi-Fi (Wireless LAN)** | Wireless communication using IEEE 802.11 standards. |
| **MAC (Media Access Control)** | Controls how devices access the shared medium (Ethernet, Wi-Fi). |

### **Key Components**  
- **MAC Address:** Unique hardware address (e.g., 00:1A:2B:3C:4D:5E).  
- **Frame:** Data encapsulated with headers, error-checking, and MAC addresses.  
- **Switch:** Forwards frames based on MAC addresses.  

### **Error Detection**  
- **CRC (Cyclic Redundancy Check):** Common method for detecting errors in frames.  
- **Checksums:** Ensures data integrity through a calculated value.

### **Flow Control Mechanisms**  
- **Backpressure:** Slows transmission to prevent congestion.  
- **Windowing:** Uses sliding window mechanism to control data flow.  

### **MAC Methods**  
- **CSMA/CD (Ethernet):** Avoids collisions in a shared wired medium.  
- **CSMA/CA (Wi-Fi):** Avoids collisions in a shared wireless medium.  
- **TDMA (Time Division Multiple Access):** Allocates specific time slots to users.  

---

## Link Layer in Computer Networks  

### Overview  
The **Link Layer** (also known as **Data Link Layer**) is responsible for **node-to-node data transfer** within a single network or link. It ensures that data is transferred correctly across a physical link, handling **error detection, flow control, and frame synchronization**.  

### Functions  
- **Framing:** Packages data from the Network Layer into frames for transmission.  
- **Error Detection & Correction:** Detects and corrects errors in frames (e.g., CRC, checksums).  
- **Flow Control:** Manages data rate to prevent buffer overflow.  
- **Media Access Control (MAC):** Determines how devices access and share the physical medium (e.g., Ethernet).  
- **Link Establishment & Termination:** Manages connections between devices over the link.  

### Key Protocols & Technologies  

| **Protocol/Technology** | **Purpose** |
|------------------------|------------|
| **Ethernet** | Common LAN technology, provides MAC addressing and framing. |
| **PPP (Point-to-Point Protocol)** | Provides point-to-point communication, commonly used in dial-up connections. |
| **Frame Relay** | WAN technology for efficient data transfer, typically used in leased lines. |
| **HDLC (High-Level Data Link Control)** | Used in both point-to-point and multipoint configurations. |
| **Wi-Fi (Wireless LAN)** | Provides wireless communication using IEEE 802.11 standards. |
| **MAC (Media Access Control)** | Defines how devices access the shared medium (Ethernet, Wi-Fi). |

### Key Components  
- **MAC Address:** Unique identifier assigned to network interfaces (e.g., 00:1A:2B:3C:4D:5E).  
- **Frame:** A packet of data encapsulated with header information, error-checking, and addressing details.  
- **Switch:** Operates at the Link Layer, forwarding frames based on MAC addresses.  

### Types of Error Detection  
- **CRC (Cyclic Redundancy Check):** Common method for detecting errors in frames.  
- **Checksums:** Used to ensure data integrity by checking data against a calculated value.  

### Flow Control Mechanisms  
- **Backpressure:** Used to prevent congestion by slowing down the transmission rate.  
- **Windowing:** Controls the flow of data using a sliding window mechanism (common in protocols like PPP).  

### Media Access Control (MAC) Methods  
- **CSMA/CD (Carrier Sense Multiple Access with Collision Detection):** Used in Ethernet to manage access to the shared medium.  
- **CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance):** Used in Wi-Fi to avoid collisions in wireless communication.  
- **TDMA (Time Division Multiple Access):** Allocates specific time slots to each user in a shared medium.  

### Important Concepts  
- **Link Layer Addressing:** Identifies devices using MAC addresses.  
- **Switching:** Switches operate at the Link Layer and forward frames based on MAC addresses.  
- **Error Handling:** Link Layer ensures data integrity through error detection and correction mechanisms like CRC.  
