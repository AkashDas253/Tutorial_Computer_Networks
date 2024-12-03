# Computer Networks


## OSI and TCP/IP

| TCP/IP Model Layer | OSI Model Layer   | Data Units (OSI) | Function (OSI)                                      | DoD Model (TCP/IP) | Protocols (TCP/IP)                    | Devices/Applications (TCP/IP)       |
|--------------------|-------------------|------------------|-----------------------------------------------------|--------------------|---------------------------------------|-------------------------------------|
| Application        | Application       | Data             | Mail Services, Directory Services, FTAM             | Process/Application| HTTP, [FTP](lessons/ftp/readme.md), SMTP, DNS, Telnet          | Web browsers, Email clients         |
|                    | Presentation      | Data             | Encryption/Decryption, Compression                  |                    | SSL/TLS, JPEG, GIF, MPEG              |                                     |
|                    | Session           | Data             | Session Establishment, Synchronization, Dialog Controller |                    | NetBIOS, PPTP                         |                                     |
| Transport          | Transport         | Segments, Datagram| Segmentation                                        | Host-to-Host       | TCP, UDP                              | Gateways, Firewalls                 |
| Internet           | Network           | Packets          | Traffic control, Fragmentation, Routing             | Internet           | IP, ICMP, ARP, RARP                   | Routers                             |
| Network Access     | Data Link         | Frames           | Flow control, Error control, Access control         | Network Access     | Ethernet, PPP, Switches, Bridges      | Switches, Bridges                   |
|                    | Physical          | Bits             | Bit Synchronization, Bit rate control, Physical Topologies |                    | DSL, ISDN, 802.11 (Wi-Fi)             | Hubs, Network Interface Cards (NICs)|

## Physical Layer

### Network Topologies

- **Mesh Topology**: Every device is connected to another device via a particular channel. If $N$ devices are connected, the total number of links required is $\binom{N}{2}$.
- **Bus Topology**: Every computer and network device is connected to a single cable. If $N$ devices are connected, the number of cables required is 1 (backbone cable) and $N$ drop lines.
- **Star Topology**: All devices are connected to a single hub through a cable. If $N$ devices are connected, the number of cables required is $N$.
- **Ring Topology**: Devices form a ring, connecting with exactly two neighboring devices.

### Transmission Modes

- **Simplex Mode**: Communication is unidirectional, like a one-way street. Only one device can transmit, and the other can only receive.
- **Half-duplex Mode**: Each station can both transmit and receive, but not simultaneously.
- **Full-duplex Mode**: Both stations can transmit and receive simultaneously.

### Manchester Encoding

When there is a long sequence of 0s and 1s, synchronization can be lost due to a lack of transitions.

- **NRZ-level encoding**: The polarity of signals changes when the incoming signal changes from ‘1’ to ‘0’ or from ‘0’ to ‘1’. The first bit of data is considered as a polarity change.
- **NRZ-Inverted/Differential encoding**: Transitions at the beginning of the bit interval represent 1, and no transition at the beginning of the bit interval represents 0.

## Data Link Layer

### Flow Control

Methods to maintain the flow of data during transmission:

- **Stop & Wait**: Only one data packet can be sent at a time. The sender waits for a positive acknowledgment before sending another packet. This leads to poor efficiency and resource utilization.
- **Sliding Window Protocol**:
  - **Go Back N**: Known as the "conservative protocol," it uses cumulative/piggybacking acknowledgments. The receiver window size is 1, and the sender window size is $2^k - 1$ where $k$ is the number of bits for the window size in the header.
  - **Selective Repeat**: Accepts out-of-order packets and uses cumulative/independent/piggybacking acknowledgments.

### Round Trip Time

The overall time taken to transmit a packet, also known as the minimum acknowledgment waiting time.

### Efficiency Formulas

- **Sequence Number**: $\text{Sequence Number} \leq (\text{Sender’s Window Size}) + (\text{Receiver’s Window Size})$
- **Efficiency in TDM (polling)**: $\text{Efficiency} = \frac{T_t}{T_{\text{poll}} + T_t}$
- **CSMA/CD**: $T_t \geq 2T_p$ Hence, $\text{min frame length} = 2T_p \cdot B$ and $\text{Efficiency in CSMA} = \frac{1}{1 + 6.44a}$
- **Back-off Algorithm for CSMA/CD**: $\text{Waiting time} = \text{back–off time}$ Let $n$ be the collision number or re-transmission serial number. Then, $\text{Waiting time} = K \cdot T_{\text{slot}}$ where $K = [0, 2^n – 1]$
- **Early Token Reinsertion**: $\text{Efficiency} = \frac{1}{1 + \frac{a}{N}}$
- **Delayed Token Reinsertion**: $\text{Efficiency} = \frac{1}{1 + \frac{(N+1)a}{N}}$
- **Pure Aloha Efficiency**: 18.4%
- **Slotted Aloha Efficiency**: 36.8%

### Maximum Data Rate (Channel Capacity)

- **Noiseless Channel (Nyquist Bit Rate)**: $\text{BitRate} = 2 \cdot \text{Bandwidth} \cdot \log_2(L)$ where $L$ is the number of signal levels used to represent data.
- **Noisy Channel (Shannon Capacity)**: $\text{Capacity} = \text{bandwidth} \cdot \log_2(1 + \text{SNR})$ where $\text{SNR}$ is the signal-to-noise ratio.

### Error Control

- **Hamming Code**: A set of error-correction codes used to detect and correct errors during data transmission.
  - **Redundant bits**: $2^r \geq m + r + 1$ where $r$ is the redundant bit and $m$ is the data bit.
- **CRC (Cyclic Redundancy Check)**: Uses a polynomial generator on both the sender and receiver sides to detect errors in transmitted data.
- **Checksum**: More reliable than other error detection modes, it uses a checksum generator on the sender side and a checksum checker on the receiver side.

### Framing in DLL

Provides a way for a sender to transmit a set of bits that are meaningful to the receiver.

- **Character/Byte Stuffing**: Used when frames consist of characters. If data contains ED, a byte is stuffed into the data to differentiate it from ED.
- **Bit Stuffing**: The sender stuffs a bit to break the pattern, e.g., appends a 0 in data = 0111 0 1.

## Network Layer

### Class Full Addressing Table

### IPv4 Header Datagram

### IP Version 6 Header Format

### Subnetting
Dividing a bigger network into a smaller network to maintain the security of the network.

### Supernetting
Combining multiple smaller networks to form a bigger network, mainly used in router summarization.

### VLSM (Variable Length Subnet Mask)
Using more than one mask in the same network, allowing different subnets of a single class A, B, or C network to have variable sizes. It increases the usability of subnets.

### Internet Control Message Protocol (ICMP)
Since IP does not have an inbuilt mechanism for sending error and control messages, it depends on ICMP to provide error control.

- Source quench message
- Parameter problem
- Time exceeded message
- Destination unreachable

### Difference between DVR and LSR

- The router with the highest priority is declared as DR.
- If there is a tie in priority, the highest router is considered. First, the highest loopback address is considered. If no loopback is configured, the highest active IP address on the router’s interface is considered.

### Hop Count
The number of routers between the source and destination network. The path with the lowest hop count is considered the best route and is placed in the routing table. The maximum hop count allowed for RIP is 15; a hop count of 16 is considered network unreachable.

### Open Shortest Path First (OSPF)
A link-state routing protocol used to find the best path between the source and destination router using its own SPF algorithm. DR and BDR election takes place in the broadcast or multi-access network.

### Routing Information Protocol (RIP)
A dynamic routing protocol that uses hop count as a routing metric to find the best path between the source and destination network. It is a distance vector routing protocol with an AD value of 120 and works on the application layer of the OSI model. RIP uses port number 520.

## Transport Layer

### TCP Header

### TCP Congestion Control Algorithm

- When Time Out Occurs: Algorithm enters Slow Start Phase.
- When 3 Duplicate ACKs occur: Algorithm enters the Congestion Avoidance Phase.

### TCP 3-Way Handshake Process

1. **SYN**: Client sends a segment with SYN (Synchronize Sequence Number) to start communication.
2. **SYN + ACK**: Server responds with SYN-ACK. ACK acknowledges the received segment, and SYN indicates the sequence number to start with.
3. **ACK**: Client acknowledges the server's response, establishing a reliable connection for data transfer.

### UDP Header

## Session & Presentation Layer

### Session Layer

- Responsible for establishing, maintaining, and terminating sessions.
- Manages data transmission for a certain time period.
- Identifies entities participating in a session.
- Provides synchronization services to the data stream.

### Presentation Layer

- Translates data packets between the network layer and the application layer.
- Responsible for protocol conversion, data encryption/decryption, character conversion, and data compression.
- Sets standards for different systems to ensure flawless communication.

## Application Layer

### Application Layer

- Topmost layer of the OSI model, directly interacting with web applications or services.
- Facilitates email sending and storing features.
- Allows users to access, retrieve, and manage files from a remote computer.
- Provides services like email, file transfer, directory services, and network resources.

### Domain Name Server (DNS)

- DNS translates hostnames to IP addresses.
- It is a distributed database implemented in a hierarchy of name servers.
- DNS is an application layer protocol for message exchange between clients and servers.

### Protocols in Application Layer

- **Dynamic Host Configuration Protocol (DHCP)**: Provides subnet mask, router address, DNS address, and vendor class identifier.
- **Simple Network Management Protocol (SNMP)**: Uses UDP port 161/162 to monitor networks, detect faults, and configure remote devices.
- **Simple Mail Transfer Protocol (SMTP)**: Uses TCP port 25 for sending emails.
- **File Transfer Protocol ([FTP](lessons/ftp/readme.md))**: Moves files between local and remote systems using two TCP connections.
- **Hypertext Transfer Protocol (HTTP)**: Uses TCP port 80 for web communication, is stateless.

### Port Numbers and Transport Modes

| Port Number | TCP/UDP       | Protocol Name                                      |
|-------------|---------------|----------------------------------------------------|
| 20, 21      | TCP           | File Transfer Protocol ([FTP](lessons/ftp/readme.md))                       |
| 22          | TCP and UDP   | Secure Shell (SSH)                                 |
| 23          | TCP           | Telnet                                             |
| 25          | TCP           | Simple Mail Transfer Protocol (SMTP)               |
| 53          | TCP and UDP   | Domain Name Server (DNS)                           |
| 67, 68      | UDP           | Dynamic Host Configuration Protocol (DHCP)         |
| 69          | UDP           | Trivial File Transfer Protocol (T[FTP](lessons/ftp/readme.md))              |
| 80          | TCP           | HyperText Transfer Protocol (HTTP)                 |
| 110         | TCP           | Post Office Protocol (POP3)                        |
| 119         | TCP           | Network News Transport Protocol (NNTP)             |
| 123         | UDP           | Network Time Protocol (NTP)                        |
| 135-139     | TCP and UDP   | NetBIOS                                            |
| 143         | TCP and UDP   | Internet Message Access Protocol (IMAP4)           |
| 161, 162    | TCP and UDP   | Simple Network Management Protocol (SNMP)          |
| 179         | TCP           | Border Gateway Protocol (BGP)                      |
| 389         | TCP and UDP   | Lightweight Directory Access Protocol (LDAP)       |
| 443         | TCP and UDP   | HTTP with Secure Sockets Layer (SSL)               |
| 500         | UDP           | Internet Security Association and Key Management Protocol (ISAKMP) / Internet Key Exchange (IKE) |
| 636         | TCP and UDP   | Lightweight Directory Access Protocol over TLS/SSL (LDAPS) |
| 989/990     | TCP           | [FTP](lessons/ftp/readme.md) over TLS/SSL                                   |