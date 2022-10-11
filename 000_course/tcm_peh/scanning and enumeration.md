## scanning and enumeration

Date:  Oct 1, 2022
Course:  TCM Practical Ethical Hacker
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

### Enumerating SMB

- Server Message Block (SMB)
- Port 139
- allows systems within same network to share files
- Get version with metasploit
- `msf6 > use auxiliary/scanner/smb/smb_version`
- Other tool Kali `smbclient`
- `smbclient -L \\\\192.168.0.1\\`
- `smbclient -L \\\\192.168.0.1\\ADMIN$

### Enumerating SSH
- Test connection - banner may give away additional information
- Fix for kex error 
- Edit `~/.ssh/config`
- Include lines:
```shell
HostKeyAlgorithms ssh-rsa
PubkeyAcceptedKeyTypes ssh-rsa
```

### Researching Potential Vulnerabilities
- https://www.exploit-db.com/
- kali - `searchsploit Samba`
- kali - `searchsploit mod ssl`

### Scanning with Nessus
- https://www.tenable.com/downloads/nessus