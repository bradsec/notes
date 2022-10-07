## common cyber infosec security terminology

Topics: [[cybersecurity]]  [[terminology]]

---
# Common Terminology

### AAA
Authentication, Authorization, and Accounting
- **Authentication** - Authentication provides a method of identifying a user, typically by having the user enter a valid username and password before access to the network is granted. Authentication is based on each user having a unique set of login credentials for gaining network access.
- **Authorization** - Following authentication, a user must gain authorization for doing certain tasks. After logging in to a system, for instance, the user may try to issue commands. The authorization process determines whether the user has the authority to issue such commands. Authorization is the process of enforcing policies—determining what types or qualities of activities, resources, or services a user is permitted. Usually authorization occurs within the context of authentication. After you have authenticated a user, they may be authorized for different types of access or activity.
- **Accounting** - The final piece in the AAA framework is accounting, which monitors the resources a user consumes during network access. This can include the amount of system time or the amount of data sent and received during a session.

Source: https://www.arubanetworks.com/techdocs/ClearPass/6.7/Aruba_DeployGd_HTML/Content/802.1X%20Authentication/About_AAA.htm

### MFA
Multi-factor authentication (MFA) is method of authentication that uses two or more authentication factors.  
**Five main types of multi-factor authentication**
1. Knowledge (Something you know) - Passwords, passphrase, passcode, answer to a secret question
2. Possession (Something you have) - Mobile devices, key fobs, access cards, security tokens
3. Inheritance (Something you are) - Fingerprint scans, iris or retina scans, voice recognition 
4. Behavioural (Something you do) - Patterns in the way that we behave such as in our typing.
5. Location (Somewhere you are) - Geographical location information, such as where are you logging in from.  
   
Source: https://www.mitnicksecurity.com/blog/what-is-multi-factor-authentication-how-does-it-work

### AirGap
- An airgap isolates a computer from the network as it has no physical or wireless connections. The only way to extract data is by removable media.  
Source: Neil, Ian. CompTIA Security+: SY0-601 Certification Guide

- An interface between two systems at which (a) they are not connected physically and (b) any logical connection is not automated (i.e., data is transferred through the interface only manually, under human control).  Source: https://csrc.nist.gov/glossary/term/air_gap  

### CIA Triad Concept
The three pillars of information security - Confidentiality, Integrity and Availability (CIA). 
- **Confidentiality** – preserving authorized restrictions on information access and disclosure, including means for protecting personal privacy and proprietary information  
- **Integrity** — guarding against improper information modification or destruction and ensuring information non-repudiation and authenticity  
- **Availability** – ensuring timely and reliable access to and use of information  
Source: https://www.nccoe.nist.gov/publication/1800-25/VolA/index.html  

### EDR
**Endpoint detection and response (EDR)**, also known as endpoint threat detection and response (ETDR), is an integrated endpoint security solution that combines real-time continuous monitoring and collection of endpoint data with rules-based automated response and analysis capabilities. The term was suggested by Anton Chuvakin at Gartner to describe emerging security systems that detect and investigate suspicious activities on hosts and endpoints, employing a high degree of automation to enable security teams to quickly identify and respond to threats.  
Source: https://www.mcafee.com/enterprise/en-au/security-awareness/endpoint/what-is-endpoint-detection-and-response.html  


### XDR
**Extended detection and response (XDR)** delivers visibility into data across networks, clouds, endpoints, and applications while applying analytics and automation to detect, analyze, hunt, and remediate today's and tomorrow's threats. XDR collects and correlates data across email, endpoints, servers, cloud workloads, and networks, enabling visibility and context into advanced threats. Threats can then be analyzed, prioritized, hunted, and remediated to prevent data loss and security breaches.
Source: https://www.cisco.com/c/en/us/products/security/what-is-xdr.html  

### Hardening  
System hardening is the process of securing a server or computer system by minimizing its attack surface, or surface of vulnerability, and potential attack vectors. It’s a form of cyberattack protection that involves closing system loopholes that cyberattackers frequently use to exploit the system and gain access to users’ sensitive data.
Source: https://www.trentonsystems.com/blog/system-hardening-overview  
 

A process intended to eliminate a means of attack by patching vulnerabilities and turning off nonessential services.
Source: https://csrc.nist.gov/glossary/term/Hardening  


### OSINT
**Open Source Intelligence (OSINT)** methods of obtaining information about a person or organisation through publicly available information, records, websites and social media.

### Playbook
A playbook is a list of required steps and actions needed to successfully respond to any incident or threat. Playbooks provide a step-by-step approach to orchestration, helping security teams to establish standardized incident response processes and ensuring the steps are followed in compliance with regulatory frameworks.  
Source: https://cyware.com/educational-guides/security-orchestration-automation-and-response/what-is-the-difference-between-a-security-playbook-and-a-runbook-ddc4/  

### Runbook
Runbooks can automate and carry out the early-stage processes of evaluating and examining security incidents until a human analyst is needed to intervene. They can automate the threat management operations from detection and triage to investigation and containment. For example, in a spearphishing runbook, indicators are extracted from the phishing email, checked through different threat services, and subsequently, blocked if they are found malicious.  
Source: https://cyware.com/educational-guides/security-orchestration-automation-and-response/what-is-the-difference-between-a-security-playbook-and-a-runbook-ddc4/  

### SOAR
**Security orchestration, automation, and response (SOAR)** seeks to alleviate the strain on IT teams by incorporating automated responses to a variety of events. SOAR combines three software capabilities: the management of threats and vulnerabilities, responding to security incidents, and *automating security operations*. SOAR security, therefore, provides a top-to-bottom threat management system. Threats are identified and then a response strategy is implemented. The system is then automated—to the extent possible to make it run more efficiently. An effective SOAR system can be used as a valuable tool to alleviate the strain on IT teams. SOAR collects data and alerts security teams using a centralized platform similar to SIEM, but SIEM only sends alerts to security analysts. SOAR security, on the other hand, takes it a step further by automating the responses. It uses artificial intelligence (AI) to learn pattern behaviors, which enable it to predict similar threats before they happen. This makes it easier for IT security staff to detect and address threats.    
Source: https://www.fortinet.com/resources/cyberglossary/what-is-soar  

### SIEM
A Security Information and Event Management (SIEM) is an application that provides the ability to gather security data from information system components and present that data as actionable information via a single interface.
Source: https://csrc.nist.gov/glossary/term/security_information_and_event_management_tool  

### SOC
The function of the **security operations center (SOC)** is to monitor, prevent, detect, investigate, and respond to cyber threats around the clock. SOC teams are charged with monitoring and protecting the organization’s assets including intellectual property, personnel data, business systems, and brand integrity. The SOC team implements the organization’s overall cybersecurity strategy and acts as the central point of collaboration in coordinated efforts to monitor, assess, and defend against cyberattacks.  
Source: https://www.checkpoint.com/cyber-hub/threat-prevention/what-is-soc/
