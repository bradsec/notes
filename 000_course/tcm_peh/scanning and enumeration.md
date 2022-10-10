## scanning and enumeration

Date:  Oct 1, 2022
Course:  
Topics: [[peh]]  

---
### Tools for testing
- vulnhub.com
	- Kioptix

### Scanning with NMAP

Device network discovery: 
- `sudo arp-scan -l`
- `sudo netdiscover -r 192.168.0.0/24`

NMAP Commands
`nmap -T4 -p- -A`
`nmap -sS`
`nmap -sU`

### Enumerating HTTP and HTTPS

- If ports are open use web browser to connect to ip and port
- View page source code for information
- Default page may provide information of web server or host
- Not found page may give further information ie. Apache version
- Terminal tools - 
	- `nikto`
	- `dirbuster`
	- `dirb`
- Save outputs of scans in notes.
- dirbuster wordlists
	- `/usr/share/wordlists/dirbuster/`
