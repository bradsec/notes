## networking refresher

Date:  Oct 1, 2022
Course:  TCM Practical Ethical Hacker
Topics: [[peh]] [[networking]]  

---
### IP Addresses
- IPV4 32 bit addressing
- 4 octets
- Must be a decimal value between 0 and 255

| 128 | 64 | 32 | 16 | 8 | 4 | 2| 1 |
|---|---|---|---|---|---|---|---|
	| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

### MAC Addresses
- Media access control
- 48 bit address (6 octets)
- First three pair or 24 bits is Organisationally Unique Identifier
- Remaining pairs / 24 bits Network interface controller specific

### TCP, UDP and the Three-Way Handshake
- Transmission Control Protocol
	- Connection oriented protocol 
	- SYN > SYN ACK > ACK
- User Datagram Protocol
	- Connection-less

### Ports

| Name | Port | Protocol |
|---|---|---|
| FTP | 21 | TCP |
| SSH | 22 | TCP |
| Telnet | 23 | TCP |
| SMTP | 25 | TCP |
| DNS | 53 | TCP / UDP 
| HTTP / HTTPS | 80 / 443 | TCP |
| POP3 | 110 | TCP |
| SMB | 139 / 445 | TCP |
| IMAP | 143 | TCP |
| DHCP | 67, 68 | UDP |
| TFTP | 69 | UDP |
| SNMP | 161 | UDP |


### The OSI Model
| Layer | Name | Description |
|---|---|---|
| 1 | Physical | Raw bit stream over physical medium - data cabling etc. |
| 2 | Datalink | MAC addressing switching |
| 3 | Network | Path of data - IP addressing routing |
| 4 | Transport | TCP / UDP |
| 5 | Session | Maintains connections controls ports and sessions |
| 6 | Presentation | Ensures data is usable format (jpeg, mov) and where encryption occurs |
| 7 | Application | Human-computer interaction layer ie. HTTP and SMTP |

Additional information / reference: https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/
