
## Terminologies
## Networking
### Introduction
- Protocols : set of rules to communicate
- TCP/IP Stack
    - TCP/IP Family
        - Application Layer : FTP, SMTP, DNS, User-Processes
        - Transport Layer : TCP, UDP
        - Network Layer : IP, ICMP, ARP, RARP
        - Data Link & Hardware Layer
    - Encapsulation : Header - Payload
    - Port Number : 
        - Well Known ports : 0-1023
        - SMTP (25) FTP(21) SSH (22) Telnet(23) POP3(110) RDP(3389) NetBios(137, 138, 139) HTTP(80) HTTPs(443)
        
    - To check listening ports and the current (TCP Connection)
        - Windows ``` netstat -ano ```
        - Linux ``` netstat -tunp ```
    - Session : Store user information on server-side.
    - Cookies : Store user info. on client-side
    - Query Strings : one-time info passing mechanism.
    
### IPv4 Addressing
    - Public IP
    - Private
    - Static IP vs Dynamic IP
- Representation : Octate (8bit values * 4 = 32)
    - Range 0 to 2^8
    - 123.41.53.64
- IPv4 Header
    - VER: Version of IP protocol in use
    - HLEN: Length of Header
    - Total Length: Length of datagram, including headers in bytes
    - Service Type: Allows a packet to be assigned a priority
    - Time to Live: Decreaments at each HOP, if zero, packet is discarded.
    - Protocol: Identifies the layer protocol being used.
    - Source IP : IP address of sender
    - Destination IP : IP address of receiver
    - Identification, flags, fragment offset : Used for handling fragmentation
    - Options : for router support (eg. Source Routing :- Source Route Attack)
    - Header Checksum : To verify datagram, if does not match, the packet is discarded.
- Reserved IP-Address
    • 127.0.0.0 – 127.255.255.255 representing the local
    host (e.g., your computer).
    • 192.168.0.0 – 192.168.255.255 is reserved for
    private networks.
    - https://datatracker.ietf.org/doc/html/rfc5735
- Subnetting
    - CIDR
- Examples
### IPv6 Addressing
- Representation
- IPv4 Header
    - Version
    - Priority
    - Flow Label : Used with applications that requires performance guarentee.
    - Payload Length : Total length of the extension header and the Transport layer PDU.
    - Next Header : identifies the type of information that immediately follows the current header(IP extension, TCP or UDP)
    - HOP limit 
    - Source/Destination Address
- Address Types
    - Unicast : Corresponding to single computer
    - Multicast : Refers to a set of computers, possibly at different locations. Packets delivered to every member of the set.
    - Anycast : Refers to a set of computers with the same address prefix. Packets delivered to exactly one of the computers in the set.
- Reserved Address
- Tunneling
    - Done automatically by the OS Kernel when IPv4 compatible IPv6 addresses are used.
    - Encapsulates IPv6 packets in IPv4 packets
    - Use IPv4 network for packet delivery.
### Routing
- Router: Forward IP packets(through one of its interface*) from one network to another. Forwarding policy is based on routing protocol.
- Protocols
    - A) Interior
        - Routing Information Protocol
        - Open Shortest Path First (OSPF)
    - B) Exterior
        - Border Gateway Protocol(BGP)
- Routing Metrics : to make routing decission : fastest route (Bandwith/Congestion).
    - Linux : ``` ip route ```
    - Windows : ``` route print ```

### Link Layer
- Mac Addresses : uniquely identify a network card(NIC). Also called Physical Addresses(6-bytes long hexadecimal value)
    - Windows : ``` ipconfig /all ```
    - linux : ``` ip addr ``` 

- ARP : Address Resolution Protocol
    - IP Address + Mac Address need for communication.
    - When a host(A) wants to send traffic to another(B) and it only knows the IP Address of B:
        - 1. "A" builds an ARP Request containing IP Address of "B" and FF:FF:FF:FF:FF:FF as destination MAC Address.
        - 2. Every host on the network will receive the request.
        - 3. B replies with an ARP reply, telling A its MAC Address.
        - 4. ‘A’ will save the IP – MAC binding in its ARP cache
    - To check the ARP Cache
        - Windows : ``` arp -a ```
        - *nix : ``` arp ```
        - Linux : ``` ip neighbour ```
    
    - Arp Poisoning(MITM-Attack), Mac Flooding (Forwarding Table)

- Firewalls
    - Firewalls are specialized hardware and software to filter packets (much more functioning) comming in and out of a network.
    - Common Action 
        - Allow
        - Drop 
        - Deny
    - Not sufficient to prevent all layers attacks (eg. XSS, etc or Trojen configured on port 80). Need for  Application level Firewalls

- IDS 
    - Inspect application payload trying to detect any potential attack
    - It checks for attack vectors like ping sweeps, port scans, sql injection, buffer overflows, etc.
    - IDS cannot detect something if it does not already know.
    - IDS does not subsitute firewalls. They add further layer of security.
    - Two main categories of IDSs
        - Network Intrusion Detection System (NIDS) : inspect network traffic.
        - Host Intrusion Detection System (HIDS) : monitor application logs, file system changes and OS configuration changes
    - Suspicious activity is logged for analysis, but it is not blocked

- IPS
    - drops malicious request when risk is above defined threshold.

- NAT : Network Address Translation
    - Every device in a (private/internal) network will use the NAT device as its defualt gateway.
    - NAT device make changes in every packets (source address)

### DNS
- DNS name such as www.admin.hackerscommunity.com can be broken down into
    - Top level Domain (TLD) (com)
    - Domain Part (hackerscommunity)
    - Sub-Domain (admin)
    - Host Part (www)
- DNS Resolution
    - Root Name Server -> TLD Server name -> domain -> subdomains -> host
    - Reverse DNS : ping

### Wireshark
    - Network Sniffer
   
### Network Attacks
1. TCP Session Hijacking
2. ARP Poisoning/ ARP spoofing/  - MITM Attack
3. Mac-Flooding
