## ethical hacker methodology

Date:  Oct 1, 2022
Course:  TCM Practical Ethical Hacker
Topics: [[peh]] [[osint]] 

---

## Five states of ethical hacking

1. Reconnaissance (Active vs Passive)
2. Scanning & Enumerations
3. Gaining Access ("Exploitation")
4. Maintaining Access
5. Covering Tracks

## Passive Recon

### Physical / Social
- Location information (images, building layout, badge readers, security, fencing)
- Job information (employees, pictures)

### Web / Host
- Target validation (whois, dnsrecon)
- Finding subdomains
- Fingerprinting
- Data breaches (haveibeenpwded, breach-parse, weleakinfo)

### Identification of Target
- Confirm correct target details

### Discovering Email Addresses
Tools
- hunter.io
- phonebook.cz
- voilanorbert.com
- Chrome extension (Clearbit Connect)
- tools.verifyemailaddress.io
- email-checker-net/validate

Consider forgot password / account recovery or email login to confirm account exists.  

### Gathering Breached Credentials
- https://github.com/hmaverickadams/breach-parse
- https://dehashed.com/ (paid)
	- Search by email, usernames, IP, name, address, phone, VIN, domain
- hashes.org (down)

### Hunting Subdomains
Tools
- sublist3r (Kali python)
- crt.sh
- OWASP Amass (https://github.com/OWASP/Amass)

### Identifying website technologies
- builtwith.com
- Firefox plugin (wappalyzer)
- whatweb (Kali)

Information gathering with Burp Suite
> Temporary project > Use Burp defaults
> Firefox > Connection settings > Manual proxy configuration
> HTTP Proxy 127.0.0.1 > Port 8080
> Alternatively use FoxyProxy
> Save certificate from https://burp 
> Firefox settings > Privacy and Security > View certificates
> Import downloaded burp certificate (check both boxes)
> View responses can provide identification of services

### Google
- Look up Google advanced search techniques
- site:thissite.com -www (site minus www)
- site:thissite.com filetype:pdf (search this site for these types of files)

Utilising Social Media
- Utilising social media photos for osint (finding people, badge photos etc.)
- Linkedin, twitter etc.

