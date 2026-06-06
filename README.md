# wireshark-dns-investigation

OBJECTIVE

The objective of this lab was to gain hands-on experience using Wireshark to capture and analyse network traffic. The focus was on understanding how DNS requests are generated and how domain names are resolved into IP addresses.

TOOLS USED
 - Wireshark
 - Windows 11
 - Web Browser
 - Home Network

METHODOLOGY

- Started a packet capture on the active WiFi adapter.
- Generated network traffic by browsing several websites.
- Applied DNS filters to isolate DNS traffic.
- Examined DNS queries and responses.
- Identified source and destination IP addresses.
- Investigated HTTPS traffic associated with visited websites.

FINDINGS:

DNS Queries observed:
- play.google.com
- github.com
- openai.com
- tryhackme.com

- play.Google.com -
# DNS Server:
# The DNS capture shows communication between the client (192.168.0.68) and the local DNS resolver (192.168.0.1).

# PROTOCOL USED:
# UDP, src port: 53, dst Port:: 51479

# RETURNED IP ADDRESS:
# 142.250.183.46

- GitHub.com -
# DNS Server:
# The DNS capture shows communication between the client (192.168.0.68) and the local DNS resolver (192.168.0.1).

# PROTOCOL USED:
# UDP, src port: 53, Dst Port: 59230

# RETURNED IP ADDRESS:
# 4.237.22.38

- openai.com -
# DNS Server:
# The DNS capture shows communication between the client (192.168.0.68) and the local DNS resolver (192.168.0.1).

# PROTOCOL USED:
# UDP, Src Port: 53, Dst Port: 53225

# RETURNED IP ADDRESS:
# 172.64.148.235 & 104.18.39.21

- tryhackme.com -
# DNS Server:
# The DNS capture shows communication between the client (192.168.0.68) and the local DNS resolver (192.168.0.1).

# PROTOCOL USED:
# UDP, Src Port: 53, Dst Port: 50937

# RETURNED IP ADDRESS:
# 52.92.18.97, 52.92.3.169, 52.92.35.105, 3.5.69.5, 3.5.73.50, 3.5.71.109, 3.5.64.209, 52.92.32.153

ANALYSIS
- play.Google.com
- The DNS capture showed a successful query for play.google.com.au, which was resolved to the IPv4 address 142.250.183.46. The response was received over UDP port 53, demonstrating the standard DNS resolution process. This highlights how DNS translates human-readable domain names into IP addresses, allowing devices to locate and communicate with web services on the internet.

- GitHub.com:
- GitHub resolved to a single IPv4 address (4.237.22.38), demonstrating how DNS translates human-readable domain names into routable IP addresses. 

- Openai.com:
- OpenAi returned multiple IPv4 addresses (172.64.148.235 and 104.18.39.21), indicating the use of load balancing and distributed infrastructure.

- tryhackme.com:
- TryHackMe returned multiple IP addresses hosted within AWS infrastructure, suggesting the use of cloud-based content delivery and redundancy mechanisms.

SECURITY RELEVANCE
- DNS traffic is valuable during security investigations because it can reveal which domains a user or system has attempted to access. Threat actors may abuse DNS through techniques such as DNS tunnelling, command-and-control communications, domain generation algorithms (DGAs), and DNS cache poisoning. Monitoring DNS activity can help security teams identify malicious behaviour and investigate incidents.

LESSONS LEARNED
1. DNS queries generally use UDP port 53
2. A single domain may resolve to multiple IP addresses
3. Cloud services frequently use load balancing and multiple DNS records
4. Wireshark filters make traffic analysis significantly easier
5. DNS resolution is the first step before establishing many internet connections

FUTURE IMPROVEMENTS
1. Investigate DNSSEC
2. Capture and analyse HTTPS traffic
3. Compare  DNS traffic using different DNS providers
4. Explore DNS tunnelling techniques in a lab environment
5. Analyse IPv6 DNS responses

SCREENSHOTS
Figure 1 - play.google.com DNS Resolution
<img width="1328" height="704" alt="annotated google com au" src="https://github.com/user-attachments/assets/f0a8f0da-552e-48a3-8715-94f10596139a" />

Figure 2 - github.com DNS Resolution
<img width="1333" height="698" alt="annotated github com" src="https://github.com/user-attachments/assets/2f789387-adb5-4d61-a0cf-669c79258920" />

Figure 3 - openai.com DNS Resolution
<img width="1328" height="665" alt="annotated openai com" src="https://github.com/user-attachments/assets/79063d51-06e0-4d52-b740-d517d5dd65dc" />

Figure 4 - tryhackme.com DNS Resolution (CNAME)
<img width="1331" height="693" alt="annotated tryhackme com 260606 1" src="https://github.com/user-attachments/assets/a9b1d34c-fa1e-4675-a33b-a441e78e3f1a" />

Figure 5 - tryhackme.com DNS Resolution (AWS Infrastructure)
<img width="1330" height="678" alt="annotated tryhackme com 260606 2" src="https://github.com/user-attachments/assets/aed7e4c0-6ab4-4c2b-9144-a6e942eada55" />
