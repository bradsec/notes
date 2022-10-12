## debian linux helpful commands

Date:  Oct 1, 2022
Topics: [[linux]] [[debian]] [[debian linux helpful commands]] [[terminal]]  

---
## Linux commands and key file locations

```bash
# Show user accounts and groups
cat /etc/passwd
```

```bash
# Show user shadow password file and hashes
sudo cat /etc/shadow
```

```bash
# Show user sudoers privileges
sudo cat /etc/sudoers

# List users in sudo group
cat /etc/group | grep 'sudo'

# Edit sudo (must be root to run visudo) su to root
visudo
```

```bash
# List network interface details
ip a
ifconfig

# List network address including MAC
ip n
arp -a

# List wireless details
iwconfig

# Show route (routing table)
ip r
route
```

```bash
# Show open network ports related programs/services
sudo netstat -tulpan

# Continuously watch for `ESTABLISHED` connections (update every 3 seconds) 
sudo watch -n 3 "netstat -tulpan | grep ESTABLISHED"
```

```bash
# curl ignore SSL certificate errors and follow redirects including 301
curl -kL https://address
```