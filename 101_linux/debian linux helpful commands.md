## debian linux helpful commands

Date:  Oct 1, 2022
Topics: [[linux]] [[debian]] [[debian linux helpful commands]] [[terminal]]  

---
## Linux commands and key file locations

- Show user accounts and groups
`cat /etc/passwd`

- Show user shadow password file and hashes
`sudo cat /etc/shadow`

- Show user sudoers privileges
`sudo cat /etc/sudoers`

- List users in sudo group
	`cat /etc/group | grep 'sudo'`

- List network addresses
	`ip a`
	`ifconfig`

- List wireless
	`iwconfig`

- List network address including MAC
	`ip n` or `arp -a`

- Show route (routing table)
	`ip r` or `route`

- Locate a file
	`locate thisfile`
	- Update locate database / search
		`updatedb`

- Open ports and services
	`sudo netstat -tulpan`

- Continuously watch for `ESTABLISHED` connections (update every 3 seconds) 
	`sudo watch -n 3 "netstat -tulpan | grep ESTABLISHED"`