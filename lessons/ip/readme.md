## IP Addressing – Cheatsheet  

### **Key Concepts to Remember**  
- **IP addresses** are unique identifiers assigned to devices on a network.  
- **IPv4** uses 32-bit addresses, while **IPv6** uses 128-bit addresses.  
- IP addresses are classified into **public** and **private** addresses.  
- **Subnetting** divides networks into smaller subnets.  

### **IP Versions**  

| **Version** | **Length** | **Format** | **Example** |
|-------------|------------|------------|-------------|
| **IPv4** | 32-bit | Dotted-decimal (e.g., 192.168.1.1) | 192.168.0.1 |
| **IPv6** | 128-bit | Hexadecimal (e.g., 2001:db8::1) | 2001:db8::1 |

### **Address Classes (IPv4)**  

| **Class** | **Address Range** | **Subnet Mask** | **Usage** |
|-----------|-------------------|-----------------|-----------|
| **Class A** | 0.0.0.0 – 127.255.255.255 | 255.0.0.0 | Large networks |
| **Class B** | 128.0.0.0 – 191.255.255.255 | 255.255.0.0 | Medium networks |
| **Class C** | 192.0.0.0 – 223.255.255.255 | 255.255.255.0 | Small networks |
| **Class D** | 224.0.0.0 – 239.255.255.255 | N/A | Multicast |
| **Class E** | 240.0.0.0 – 255.255.255.255 | N/A | Reserved |

### **Private Address Ranges (IPv4)**  

| **Range** | **Class** |
|-----------|-----------|
| 10.0.0.0 – 10.255.255.255 | Class A |
| 172.16.0.0 – 172.31.255.255 | Class B |
| 192.168.0.0 – 192.168.255.255 | Class C |

### **CIDR Notation**  
- **CIDR (Classless Inter-Domain Routing)** eliminates class-based addressing.  
- **Subnet Mask Example:** `/24` for a mask of `255.255.255.0`.

### **Subnetting**  
- Divides an IP address into **network** and **host** portions.  
- **Subnet Mask**: Specifies which part of the address is the network and which part is the host.  
- **Example**: `192.168.1.0/24` – Network: `192.168.1.0`, Subnet Mask: `255.255.255.0`.

### **IPv6 Features**  
- **Address Space:** Vastly larger than IPv4.  
- **Auto-Configuration:** Devices can configure their own IP addresses automatically.  
- **No NAT:** IPv6 eliminates the need for Network Address Translation (NAT).

### **Special Addresses**  

| **Address** | **Usage** |
|-------------|-----------|
| **Loopback (127.0.0.1)** | Used for self-testing. |
| **Broadcast** | Sends data to all devices on the network (IPv4). |
| **Anycast** | Delivered to the nearest device (IPv6). |
| **Multicast** | Sent to multiple specific devices. |

### **Important Terms**  
- **Public IP Address:** Routable on the internet.  
- **Private IP Address:** Used within local networks, not routable on the internet.  
- **NAT (Network Address Translation):** Allows devices on a private network to communicate with the internet using a single public IP.

---

## **IP Addressing**

### **1. IPv4 and IPv6**

#### **IPv4 (Internet Protocol Version 4)**
- **Format**: IPv4 addresses are 32-bit numbers written in **dotted decimal format**, divided into four 8-bit octets. Each octet is represented by a number between **0 to 255**.
  - Example: **192.168.1.1**
- **Address Space**: With 32 bits, IPv4 can theoretically support **4.3 billion unique addresses** (2^32).
- **Address Classes**: IPv4 is divided into address classes (A, B, C, D, E) to categorize IP addresses for different uses.
  - **Class A**: 1.0.0.0 to 127.255.255.255 (Large networks)
  - **Class B**: 128.0.0.0 to 191.255.255.255 (Medium networks)
  - **Class C**: 192.0.0.0 to 223.255.255.255 (Small networks)
  - **Class D**: 224.0.0.0 to 239.255.255.255 (Multicast)
  - **Class E**: 240.0.0.0 to 255.255.255.255 (Reserved for future use)

- **Public and Private IP Addressing**: 
  - Public IPs are globally unique and assigned by ISPs.
  - Private IPs are used within private networks and are not routable over the internet.
    - **Private IP ranges**:
      - Class A: 10.0.0.0 to 10.255.255.255
      - Class B: 172.16.0.0 to 172.31.255.255
      - Class C: 192.168.0.0 to 192.168.255.255

#### **IPv6 (Internet Protocol Version 6)**
- **Format**: IPv6 addresses are 128-bit numbers written in **hexadecimal format**, divided into eight groups of four hexadecimal digits (0-9, A-F), separated by colons.
  - Example: **2001:0db8:85a3:0000:0000:8a2e:0370:7334**
- **Address Space**: IPv6 provides an incredibly large address space, with **340 undecillion unique addresses** (2^128), ensuring that IP address exhaustion is not an issue.
- **Types of IPv6 Addresses**:
  - **Unicast**: One-to-one communication.
  - **Multicast**: One-to-many communication.
  - **Anycast**: Sent to the nearest device in a group.
- **Benefits over IPv4**:
  - Larger address space
  - Built-in security features (IPsec)
  - More efficient routing

---

### **2. Subnetting**

Subnetting is the process of dividing a larger IP network into smaller, manageable sub-networks (subnets). This is useful for improving network performance, security, and organization.

- **Subnet Mask**: A subnet mask defines how the IP address is split into the network and host portions.
  - Example: For an IP address **192.168.1.1** and a subnet mask of **255.255.255.0**:
    - Network: **192.168.1.0**
    - Host: **.1** (last part of the address)

- **How Subnetting Works**:
  - **Class A**: Supports 128 networks, with 16 million hosts per network.
  - **Class B**: Supports 16,000 networks, with 65,000 hosts per network.
  - **Class C**: Supports 2 million networks, with 254 hosts per network.
  
  Subnetting helps in efficient use of available IP addresses and allows the network administrator to create more networks within the same address space.

- **CIDR and Subnetting**:
  - **Example**: The IP address **192.168.1.0/24** uses **24 bits for the network** and **8 bits for hosts**.

---

### **3. Supernetting**

Supernetting is the reverse process of subnetting. It is used when you want to combine multiple smaller networks into a larger one, effectively "borrowing" bits from the host portion to create a larger network.

- **Use Case**: This is useful when a larger organization wants to combine smaller subnetworks into one network to make routing more efficient.

- **How Supernetting Works**: You increase the size of the network address (i.e., increase the number of network bits).
  - **Example**: Combining two **192.168.1.0/24** and **192.168.2.0/24** into one **192.168.0.0/22** network.

---

### **4. CIDR (Classless Inter-Domain Routing)**

CIDR is a method for allocating IP addresses and routing IP packets, introduced to improve upon the traditional class-based system. CIDR allows for more flexible division of networks, unlike the rigid class-based system.

- **Notation**: CIDR uses the format **IP address/Prefix length** (e.g., **192.168.1.0/24**), where the prefix length (the number after the slash) indicates how many bits are used for the network address.
  - Example: **192.168.1.0/24** represents the first 24 bits for the network, leaving 8 bits for the hosts.
  
- **Benefits**:
  - More efficient use of address space.
  - Eliminates the limitations of classful addressing (A, B, C).
  - Enables smaller subnets to be created as needed.

---

### **5. NAT (Network Address Translation)**

NAT is a technique used in networking to translate private IP addresses within a local network into public IP addresses when communicating with the internet. It helps mitigate the limited number of public IP addresses available by allowing multiple devices on a private network to share a single public IP address.

- **Types of NAT**:
  - **Static NAT**: One-to-one mapping between private and public IP addresses.
  - **Dynamic NAT**: A pool of public IP addresses is mapped to private IP addresses dynamically.
  - **PAT (Port Address Translation)**: A form of dynamic NAT that uses port numbers to allow multiple private IP addresses to share a single public IP address.

- **Use Case**: NAT is used to allow private IP addresses within a network to communicate with external networks (such as the internet), while hiding the internal structure of the network from external devices.

---

### **6. Private and Public IP Addresses**

#### **Private IP Addresses**
Private IP addresses are used within internal networks and cannot be accessed directly from the public internet. They are assigned for use within a local area network (LAN) and are not routable on the global internet.

- **Private IP ranges**:
  - **Class A**: 10.0.0.0 to 10.255.255.255
  - **Class B**: 172.16.0.0 to 172.31.255.255
  - **Class C**: 192.168.0.0 to 192.168.255.255

#### **Public IP Addresses**
Public IP addresses are globally unique and assigned by ISPs. These are routable on the internet and used to identify devices or networks across the globe.

- **Use Case**: A web server with a public IP address is accessible from anywhere on the internet, whereas a device with a private IP address requires NAT to communicate with devices outside its local network.

---

### **Summary and Conclusion**

- **IPv4** is the most widely used IP addressing format, but **IPv6** is gaining traction due to the exhaustion of IPv4 addresses.
- **Subnetting** allows for more efficient use of IP addresses, whereas **supernetting** combines networks to optimize routing.
- **CIDR** provides flexibility and efficient address allocation.
- **NAT** enables multiple devices on a local network to share a single public IP address, enhancing security and conserving address space.
- **Private IPs** are used for internal communication, and **public IPs** are used for external communication.

