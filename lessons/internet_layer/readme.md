## Internet Layer – Cheatsheet  

### **Key Concepts to Remember**  
- Handles **routing, addressing, packet forwarding, and error handling**.  
- Uses **IP addresses** for device identification.  
- **Routers** operate at this layer to direct packets between networks.  

### **Key Protocols & Functions**  

| **Protocol** | **Purpose** |
|-------------|------------|
| **IP (Internet Protocol)** | Defines addressing and routing for packet delivery. |
| **ICMP (Internet Control Message Protocol)** | Sends error messages (e.g., TTL expired, unreachable host). |
| **ARP (Address Resolution Protocol)** | Resolves IP addresses to MAC addresses. |
| **RARP (Reverse ARP)** | Maps MAC addresses to IP addresses (obsolete, replaced by DHCP). |
| **IGMP (Internet Group Management Protocol)** | Manages multicast group memberships. |

### **IP Addressing**  

| **Version** | **Features** |
|------------|------------|
| **IPv4** | 32-bit, dot-decimal notation (e.g., 192.168.1.1), supports subnetting & NAT. |
| **IPv6** | 128-bit, hexadecimal notation (e.g., 2001:db8::1), larger address space, IPSec, auto-configuration. |

### **Routing Types**  
- **Direct Routing:** Within the same network.  
- **Indirect Routing:** Passes through multiple routers.  

### **Routing Protocols**  

| **Type** | **Examples** |
|---------|------------|
| **IGPs (Interior Gateway Protocols)** | RIP, OSPF, EIGRP |
| **EGPs (Exterior Gateway Protocols)** | BGP |

### **Important Concepts**  
- **Subnetting & CIDR:** Efficient IP allocation.  
- **NAT (Network Address Translation):** Allows multiple devices to share one public IP.  
- **TTL (Time-to-Live):** Limits packet lifetime to prevent looping.  
- **MTU (Maximum Transmission Unit):** Defines the largest packet size allowed for transmission.  

---

## Internet Layer in Computer Networks  

### Overview  
The **Internet Layer** (also called the **Network Layer** in the OSI model) is responsible for **routing, addressing, and packet forwarding** across networks. It ensures that data packets travel from the source to the destination, even across multiple networks.  

### Functions  
- **Logical Addressing:** Assigns unique IP addresses to devices.  
- **Routing:** Determines the best path for data transmission.  
- **Fragmentation & Reassembly:** Breaks large packets into smaller ones for transmission.  
- **Packet Forwarding:** Moves packets between networks using routers.  
- **Error Handling & ICMP Messaging:** Manages network errors and diagnostics.  

### Key Protocols  

| **Protocol** | **Purpose** |
|-------------|------------|
| **IP (Internet Protocol)** | Defines addressing and routing for packet delivery. |
| **ICMP (Internet Control Message Protocol)** | Sends error messages (e.g., unreachable host, TTL expired). |
| **ARP (Address Resolution Protocol)** | Resolves IP addresses to MAC addresses in a local network. |
| **RARP (Reverse ARP)** | Maps MAC addresses to IP addresses (obsolete, replaced by DHCP). |
| **IGMP (Internet Group Management Protocol)** | Manages multicast group memberships. |

### IP Addressing  

| **Version** | **Features** |
|------------|------------|
| **IPv4** | 32-bit, uses dot-decimal notation (e.g., 192.168.1.1), supports subnetting, NAT. |
| **IPv6** | 128-bit, uses hexadecimal notation (e.g., 2001:db8::1), supports larger address space, security (IPSec), and auto-configuration. |

### Routing  
- **Direct Routing:** Communication within the same network.  
- **Indirect Routing:** Data passes through multiple routers before reaching its destination.  
- **Routing Protocols:**  
  - **Interior Gateway Protocols (IGPs):** Used within an organization (e.g., RIP, OSPF, EIGRP).  
  - **Exterior Gateway Protocols (EGPs):** Used between organizations (e.g., BGP).  

### Packet Structure  
- **IPv4 Packet Fields:** Source IP, Destination IP, TTL, Protocol, Header Checksum.  
- **IPv6 Packet Fields:** Source IP, Destination IP, Traffic Class, Flow Label, Hop Limit.  

### Important Concepts  
- **Subnetting:** Divides networks into smaller subnetworks.  
- **CIDR (Classless Inter-Domain Routing):** Efficient IP allocation without relying on class-based addresses.  
- **NAT (Network Address Translation):** Allows multiple devices to share a single public IP address.  
- **TTL (Time-to-Live):** Prevents infinite loops by limiting packet lifetime.  
- **MTU (Maximum Transmission Unit):** Defines the largest packet size allowed for transmission.  
