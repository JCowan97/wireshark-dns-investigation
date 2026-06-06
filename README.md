# wireshark-dns-investigation

OBJECTIVE
The objective of this lab was to gain hands-on experience using Wireshark to capture and analyse network traffic. The focus was on understanding how DNS requests are generated and how domain names are resolved into IP addresses.

TOOLS USED
 - Wireshark
 - Windows 11
 - Web Browser
 - Home Network

METHODOLOGY
Started a packet capture on the active WiFi adapter.
Generated network traffic by browsing several websites.
Applied DNS filters to isolate DNS traffic.
Examined DNS queries and responses.
Identified source and destination IP addresses.
Investigated HTTPS traffic associated with visited websites.

FINDINGS:
DNS Queries observed:
google.com.au
github.com
openai.com
tryhackme.com

- Google.com -
DNS Server Requests were sent to:
192.168.0.68

PROTOCOL USED:
UDP, src port: 53, dst Port:: 51479

RETURNED IP ADDRESS:
142.250.183.46

- GitHub.com -
DNS Server Requests were sent to:
192.168.0.68

PROTOCOL USED:
UDP, src port: 53, Dst Port: 59230

RETURNED IP ADDRESS:
4.237.22.38

- openai.com -
DNS Server Requests were sent to:
192.168.0.68

PROTOCOL USED:
UDP, Src Port: 53, Dst Port: 53225

RETURNED IP ADDRESS:
172.64.148.235 & 104.18.39.21

- tryhackme.com -
DNS Server Requests were sent to:
192.168.0.68

PROTOCOL USED:
UDP, Src Port: 53, Dst Port: 50937

RETURNED IP ADDRESS:
52.92.18.97, 52.92.3.169, 52.92.35.105, 3.5.69.5, 3.5.73.50, 3.5.71.109, 3.5.64.209, 52.92.32.153


