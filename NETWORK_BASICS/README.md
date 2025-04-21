# Ethical Hacking

- _This is the documentation for the Ethical Hacking learning path._
- _It will entail writing research and documenting the commands used to perform the tasks in each quest._
- _Without much say, let us get into it_

## 1. Network Basics

### I. Understanding the OSI Model

- _The OSI Model is a conceptual framework for describing how data is transmitted over a network._
- [The OSI Model](OSI_MODEL_Raymond_Martin.pdf)

### The Layers

#### Layer 1: Physical Layer

- _The physical layer is responsible for the physical transmission of data over the network._
- _It deals with the physical characteristics of the network, such as the physical medium, the physical addressing, and the physical transmission of data._
- _The physical layer is the lowest layer of the OSI model and is responsible for the physical transmission of data over the network._
- _Some of the protocols in the physical layer include Ethernet, Wi-Fi, PPP(Point-to-point Protocol), and Token Ring._

#### Layer 2: Data Link Layer

- _The data link layer is responsible for the transmission of error-free data over the network._
- _It deals with the transmission of data frames over the network, including the addressing, error detection, and error correction._
- _Some of the protocols in the data link layer include Ethernet, Wi-Fi, PPP(Point-to-point Protocol), and Token Ring._

#### Layer 3: Network Layer

- _The network layer is responsible for the transmission of data over the network._
- _It deals with the routing of data packets over the network, including the addressing, error detection, and error correction._
- _Some of the protocols in the network layer include IP(Internet Protocol), ICMP(Internet Control Message Protocol), and ARP(Address Resolution Protocol)._

#### Layer 4: Transport Layer

- _The transport layer is responsible for the transmission of data over the network._
- _It deals with the transmission of data segments over the network, including the addressing, error detection, and error correction._
- _Some of the protocols in the transport layer include TCP(TCP/IP), UDP(UDP/IP), and SCTP(Simple Communications Transport Protocol)._

#### Layer 5: Session Layer

- _the session layer is responsible for the establishment and termination of sessions over the network._
- _It deals with the establishment and termination of sessions over the network, including the addressing, error detection, and error correction._
- _Some of the protocols in the session layer include TCP(TCP/IP), UDP(UDP/IP), and SCTP(Simple Communications Transport Protocol)._
- _Protocols: NetBIOS, SSH (Secure Shell)_
- _It provides a way for applications to communicate with each other over the network._

#### Layer 6: Presentation Layer

- _In this layer the model is tasked with the presentation of data to the user._
- _The model converts the data into a format that can be understood by the receiving device_
- _It uses the following protocols: SSL/TLS (Secure Sockets Layer/Transport Layer Security), MIME (Multipurpose Internet Mail Extensions)_
- _This layer provides data encryption, compression, and formatting._

#### Layer 7: Application Layer

- _This layer provides services to the end0user applications_
- _It uses the protocols: HTTP (Hypertext Transfer Protocol), FTP (File Transfer Protocol), SMTP (Simple Mail Transfer Protocol)_

## Key Takeaways

- _some code to start off with some cool stuff_

```sh
# Identify all open ports on localhost
sudo netstat -tulpn

# Get the IP of your machine
ip a

# Display routing table
route -n

# Scan a host for open ports
nmap -sS 192.168.0.105
```

### Importance of port scanning

- _When scanning for an open ports on a localhost, using tools like `Nmap` it is possible to detect the servics running on those ports. For instance:_
- Port 22, `SSH` Secure Shell: _Vulnerable for weak authentication or misconfiguration_
- Port 80`HTTPS` _and Port 443`HTTP` are vulnerable in cross-site scripting (XSS) and SQL injections_
- Port 21 `FTP`: _File Transfer Protocol. Misconfigured FTP servers can allow unauthorized access to sensitive files_
- Port 3389 `RDP`: Remote Desktop Protocol. _Weak passwords or misconfigured security settings can be exploited through brute-force attacks_

- _Some vulnerabilities that might be found from port-scans include:_
  - _**EternalBlue**: A vulnerability in the SMB protocol on port 445, famously exploited by the WannaCry ransomware._
  - _**Brute-Forcing SMB Login Credentials**: Systematically trying different username and password combinations to gain access._

### Understanding the difference between a UDP and TCP

- _UDP (User Datagram Protocol) and TCP (Transmission Control Protocol) are two fundamental transport layer protocols used in the Internet Protocol (IP) suite. They serve different purposes and have distinct characteristics, making them suitable for different types of applications._

#### TCP

**Characteristics:**

- _Connection-Oriented: TCP establishes a connection between the sender and receiver before data transmission begins. This connection is maintained throughout the communication session._
- _Reliable: TCP ensures that data is delivered reliably and in the correct order. It uses acknowledgments, sequence numbers, and retransmissions to guarantee data integrity._
- _Flow Control: TCP uses windowing to manage the flow of data, ensuring that the sender does not overwhelm the receiver with too much data too quickly._
- _Congestion Control: TCP implements mechanisms to avoid network congestion, such as slow start, congestion avoidance, and fast retransmit._
- _Error Checking: TCP includes checksums to detect and correct errors in data transmission._
- _Use Cases:
- _Web Browsing (HTTP/HTTPS): Ensures that web pages and data are transmitted reliably._
- _Email (SMTP, POP3, IMAP): Ensures that emails are delivered correctly and in the right order._
- _File Transfers (FTP, SFTP): Ensures that files are transferred without corruption._
- _Remote Desktop (RDP): Ensures that remote desktop sessions are stable and reliable._

#### UDP

**Characteristics:**

- _Connectionless: UDP does not establish a connection before sending data. Each datagram is sent independently, and there is no guarantee of delivery or order._
- _Unreliable: UDP does not provide error checking, retransmission, or flow control. It is a "best-effort" delivery service._
- _Faster: UDP has lower overhead compared to TCP, making it faster and more efficient for certain applications._
- _No Flow Control: UDP does not manage the flow of data, so the sender can send data as fast as it wants, potentially overwhelming the receiver._
- _No Congestion Control: UDP does not implement mechanisms to avoid network congestion._
- _Use Cases:
- _Real-Time Applications (VoIP, Online Gaming, Video Streaming): These applications can tolerate some packet loss and require low latency. UDP's speed and efficiency make it suitable for real-time data transmission._
- _DNS (Domain Name System): DNS queries are typically small and can be sent using UDP, which is faster and more efficient for this purpose._
- _Network Games: Online games often use UDP to transmit player movements and actions, as some packet loss is acceptable for smooth gameplay._
- _Broadcast and Multicast: UDP is used for broadcasting and multicasting data to multiple recipients, as it does not require a connection for each recipient._
