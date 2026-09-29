---
type: exam
module: "bank"
tags: [exam, mod/01]
topic: "CND Question Bank — 100 Single-Best-Answer"
exam_weight: high
status: draft
unresolved:
  - "Blueprint per-module weights not in courseware → equal 5/module used until weights are sourced."
---
# Question Bank

> [!info] Rules
> 100 single-best-answer items, answerable strictly from PDF content. Distribution: equal 5 per module (weights unknown). Answers + justifications live in [[Answer-Key]].

## Index by module
| Module | Items | Key |
|--------|-------|-----|
| 01 — Network Attack and Defense Strategies | Q001–Q005 | [[Answer-Key#Module 01]] |
| 02 — Administrative Network Security | Q006–Q010 | [[Answer-Key#Module 02]] |
| 03 — Technical Network Security | Q011–Q015 | [[Answer-Key#Module 03]] |
| 04 — Network Perimeter Security | Q016–Q020 | [[Answer-Key#Module 04]] |
| 05 — Endpoint Security - Windows Systems | Q021–Q025 | [[Answer-Key#Module 05]] |
| 06 — Endpoint Security - Linux Systems | Q026–Q030 | [[Answer-Key#Module 06]] |
| 07 — Endpoint Security - Mobile Devices | Q031–Q035 | [[Answer-Key#Module 07]] |
| 08 — Endpoint Security - IoT Devices | Q036–Q040 | [[Answer-Key#Module 08]] |
| 09 — Administrative Application Security | Q041–Q045 | [[Answer-Key#Module 09]] |
| 10 — Data Security | Q046–Q050 | [[Answer-Key#Module 10]] |

## Module 01 — Network Attack and Defense Strategies (Q001–Q005)

**Q001.** Which of the following best represents how risk is calculated in network security?
- A) Risk = Asset + Threat + Vulnerability
- B) Risk = Motive + Method + Vulnerability
- C) Risk = Asset + Motive + TTPs
- D) Risk = Threat + Vulnerability + Motive

**Q002.** An attacker floods a DHCP server with a large number of DHCP requests carrying spoofed MAC addresses, exhausting the available IP address pool. Which type of attack is this, and which tool is commonly used?
- A) DHCP spoofing, using a rogue DHCP server
- B) DHCP starvation, using Gobbler
- C) ARP poisoning, using Cain & Abel
- D) MAC flooding, using SMAC

**Q003.** A web application uses SSL/TLS only for the login page, and a packet sniffer is used to intercept the session cookie afterwards. Which session hijacking method is used?
- A) Session fixation
- B) Cookie theft by malware
- C) Session side-jacking
- D) CSRF injection

**Q004.** Which security approach uses methods such as IDS, SIMS, TRS, and IPS to address attacks that the preventive approach failed to avert?
- A) Preventive
- B) Reactive
- C) Retrospective
- D) Proactive

**Q005.** According to the courseware, the 11 tactic categories in MITRE ATT&CK for Enterprise are derived from which sources?
- A) The Reconnaissance, Weaponization, and Delivery stages of the Cyber Kill Chain
- B) The Exploit, Control, Maintain, and Execute stages of the Cyber Kill Chain
- C) The five phases of the CEH hacking methodology
- D) The OWASP Top 10 risk list

## Module 02 — Administrative Network Security (Q006–Q010)

**Q006.** A security consultant is building an organization's compliance program. Which of the following represents the correct hierarchy as given in the courseware?
- A) Standards → Policies → Frameworks → Procedures
- B) Frameworks → Policies → Standards → Procedures
- C) Policies → Frameworks → Guidelines → Standards
- D) Frameworks → Guidelines → Policies → Standards

**Q007.** Which of the following is responsible for determining the purposes and means of processing personal data, while the other handles data on its behalf, under the GDPR?
- A) Data controller vs. data processor
- B) Data owner vs. data custodian
- C) Information owner vs. system admin
- D) DPO vs. DPO assistant

**Q008.** An organization wants to block all Internet services by default and only enable each service that the network defender individually deems safe and necessary, while logging everything. Which Internet access policy type is this?
- A) Promiscuous
- B) Permissive
- C) Paranoid
- D) Prudent

**Q009.** During the first phase of IT asset management, the team discovers and documents all assets and then groups them. Which grouping basis is used?
- A) By KPI and SLA thresholds
- B) By type, usage, location, owner/department, lifecycle stage, criticality, and license type
- C) By threat severity and vulnerability score
- D) By procurement cost and depreciation

**Q010.** Which access rule applies when a user holds the "Secret" data classification level, according to the courseware?
- A) Access to Secret, Confidential, Restricted, and Unclassified (but not Top Secret)
- B) Access to all levels including Top Secret
- C) Access limited to Secret only
- D) Access to Unclassified only unless explicitly granted

## Module 03 — Technical Network Security (Q011–Q015)

**Q011.** An enterprise deploys honeypots to study attacker behavior in isolation. The network defenders discover exactly how attacks unfold step by step in order to develop new countermeasures. Which honeypot type is this?
- A) Production honeypot
- B) Low-interaction honeypot
- C) Research honeypot
- D) Pure honeypot

**Q012.** Which NAC detection check is NOT among those the courseware lists for admission?
- A) Search for an antivirus program and check whether it has been updated
- B) Check if the end system has a configured firewall or intrusion prevention software
- C) Verify that the end user's device is on the latest Wi-Fi password
- D) Search for viruses and check whether the operating system has been updated

**Q013.** A technician must centrally administer switches, routers, and firewalls while encrypting the entire client–server communication including the username and password. Which AAA protocol fits?
- A) RADIUS over UDP ports 1812/1813
- B) TACACS+ over TCP port 49
- C) Kerberos as a Ticket-Granting Service
- D) S/MME with a CA-issued certificate

**Q014.** Which IPsec service authenticates the sender but does NOT encrypt the data?
- A) Authentication Header (AH)
- B) Encapsulating Security Payload (ESP)
- C) Tunnel mode only
- D) The TLS Record Protocol

**Q015.** A network defender wants a single security console that provides firewall, IDS, anti-malware, spam filtering, content filtering, DLP, and VPN, while accepting the risk of a single point of failure. Which solution is described?
- A) Load balancer with round-robin algorithm
- B) SIEM with correlated events
- C) UTM (Unified Threat Management)
- D) Network Access Control appliance

## Module 04 — Network Perimeter Security (Q016–Q020)

**Q016.** A firewall checks each packet's header against a rule set and makes its decision independently at the network level of the OSI model, without tracking session state. Which firewall technology is this?
- A) Application-level gateway
- B) Packet filtering firewall
- C) Circuit-level gateway
- D) Stateful multilayer inspection firewall

**Q017.** An IDS sensor is placed outside the perimeter firewall. The team tunes it to the least-sensitive attacks so it logs attack attempts only, without raising alerts. Which deployment location is this?
- A) L1 — outside the perimeter firewall
- B) L2 — behind the external firewall in the DMZ
- C) L3 — major network backbone
- D) L4 — critical subnets

**Q018.** An IDS cannot detect intrusions when they are encapsulated in encrypted traffic because encrypted payloads cannot be matched to signatures. What does the courseware recommend to fix this?
- A) Place the IDS behind a VPN termination with SSL encryption
- B) Increase the IDS sensitivity threshold
- C) Disable stateful protocol analysis on the sensor
- D) Deploy the sensor outside the firewall in stealth mode

**Q019.** A network defender wants to allow only a single MAC address per port on an access switch. Which port-security method is this?
- A) Dynamic — MAC held in CAM
- B) Sticky — MAC saved across reboot
- C) Static — only a single MAC allowed
- D) AAA-based port authentication

**Q020.** In a Software-Defined Perimeter, which component is the authentication point that evaluates the policy, grants access to the client, and determines which gateways the client may communicate with?
- A) SDP gateway (accepting host)
- B) SDP client (initiating host)
- C) Single-Packet Authorization service
- D) SDP controller

## Module 05 — Endpoint Security - Windows Systems (Q021–Q025)

**Q021.** A Windows service is installed so that it runs under its own dedicated account with its own SID, and Windows sets the password and changes it periodically. Which Windows security feature is this, and under what name form does it run?
- A) Mandatory Integrity Control — named by its integrity level
- B) Virtual service account — `NT SERVICE\<service name>`
- C) Securable object — named by the Kernel Object Manager
- D) Local Security Authority — `NT AUTHORITY\SYSTEM`

**Q022.** A network defender must stop the built-in Guest account from being used for password-less, unauthenticated Internet access on a workstation. Which command disables it?
- A) `net user guest /active:No`
- B) `net user Guest *`
- C) `sc config Guest start= disabled`
- D) `Disable-ADAccount -Identity Guest`

**Q023.** An administrator must configure the Windows Update service to start automatically so automatic updates continue. Which command does the courseware use?
- A) `sc config wuauserv start= auto`
- B) `net start wuauserv /persistent`
- C) `Enable-WindowsOptionalFeature -Online -FeatureName wuauserv`
- D) `Restart-Service wuauserv`

**Q024.** Which Windows access-management approach grants users only the specific cmdlets, scripts, and functions they need, defined through role capability files and session configuration files?
- A) Just Enough Administration (JEA)
- B) User Account Control elevation
- C) Smart App Control
- D) Local Security Policy assignments

**Q025.** According to the courseware, which of the following does DNSSEC guarantee by adding digital signatures to DNS information?
- A) Confidentiality and Denial-of-Service protection
- B) Authenticity, integrity, and the non-existence of a domain name or type
- C) Availability and load balancing of Authoritative DNS servers
- D) Encryption of DNS queries between client and resolver

## Module 06 — Endpoint Security - Linux Systems (Q026–Q030)

**Q026.** A Linux administrator runs `find / -perm +4000` and receives a long list of binaries such as `chfn`, `gpasswd`, and `sudo`. According to the courseware, what is the purpose of this command?
- A) To list all files that are world-writable
- B) To view all files with the SUID (set-user-id) bit set
- C) To locate all directories with the SGID bit set
- D) To find all files owned by the root user

**Q027.** A network defender must drop packets that have the characteristics of an XMAS scan. Which iptables rule does the courseware list for this task?
- A) `iptables -A INPUT -p tcp --syn -m state --state NEW -j DROP`
- B) `iptables -A INPUT -p tcp --tcp-flags ALL ALL -j DROP`
- C) `iptables -A INPUT -f -j DROP`
- D) `iptables -A OUTPUT -p tcp --dports 25,465,587 -j REJECT`

**Q028.** Which SELinux mode "prints warnings instead of enforcing" the security policy?
- A) Enforcing
- B) Permissive
- C) Disabled
- D) Targeted

**Q029.** Ubuntu's "minimal installation" option restricts the packages installed during the OS install, keeping only the desktop, web browser, and core system tools. Approximately how many packages does it remove compared with the default install?
- A) 20 packages
- B) 40 packages
- C) 80 packages
- D) 200 packages

**Q030.** To confine SFTP users inside a chroot jail so they cannot browse other users' directories, which configuration must be appended to `/etc/ssh/sshd_config`?
- A) `Subsystem sftp /usr/libexec/openssh/sftp-server`
- B) `PermitRootLogin no` and `AllowUsers sftponly`
- C) `Subsystem sftp internal-sftp` with a `Match group sftponly` block setting `ChrootDirectory /sftp/`, `X11Forwarding no`, `AllowTcpForwarding no`, and `ForceCommand internal-sftp`
- D) `UsePAM yes` and `LogLevel VERBOSE`

## Module 07 — Endpoint Security - Mobile Devices (Q031–Q035)

**Q031.** An organization lets employees select their own smartphone or tablet from a list of devices approved by the company; the company purchases the selected device. Which mobile usage policy is this?
- A) BYOD
- B) COPE
- C) CYOD
- D) COBO

**Q032.** The courseware categorizes enterprise mobile device security challenges. A vulnerability unintentionally introduced by a manufacturer into a mobile keyboard such as SwiftKey belongs to which risk category?
- A) Physical risks and challenges
- B) Network-based risks and challenges
- C) System-based risks and challenges
- D) Application-based risks and challenges

**Q033.** An organization wants MDM capabilities without maintaining servers on its premises; it accepts monthly/annual fees to negate the up-front cost while still having management and admission. Which MDM delivery method fits this need?
- A) Premise-based MDM
- B) SaaS-based MDM
- C) Managed services-based MDM
- D) Host-based MDM

**Q034.** According to the general mobile platform security guidelines, "Find My Device" (Android) and "Find My iPhone" or "FindMyPhone" (Apple iOS) are examples of which service?
- A) MDM blacklisting
- B) Application certification rules
- C) Secure backup-and-restore
- D) Remote wipe services

**Q035.** The Android Device Administration API supports a policy by which the device wipes its data if the user enters the wrong password too many times. Which policy is this?
- A) Maximum inactivity time lock
- B) Password history restriction
- C) Maximum failed password attempts
- D) Disable camera

## Module 08 — Endpoint Security - IoT Devices (Q036–Q040)

**Q036.** In IoT, two connected devices exchange data directly using Bluetooth, Z-Wave, ZigBee, or Wi-Fi, without the cloud being in the flow during the interaction. Which IoT communication model is this?
- A) Device-to-Cloud
- B) Device-to-Gateway
- C) Device-to-Device
- D) Back-end Data-Sharing

**Q037.** An attacker exploits the OBEX Push profile to gain access to data on a nearby phone; a second attacker remotely controls a compromised device to execute AT commands, connect to the Internet, and place calls. Which Bluetooth attacks are described, respectively?
- A) Bluejacking then BlueSmack
- B) Car Whisperer then KNOB
- C) BlueBugging then Bluesnarfing
- D) Bluesnarfing then BlueBugging

**Q038.** A security tester wants to enumerate and attack ZigBee/IEEE 802.15.4 networks and needs tools such as `zbdump`, `zbconvert`, `zbreplay`, and `zbstumbler`. Which framework provides these?
- A) KillerBee
- B) Aircrack-ng
- C) beSTORM
- D) RloT Scanner

**Q039.** A network defender monitors the IoT fleet managed with SeaCat.io. Which port carries the SeaCat mutual-TLS gateway tunnel (alongside Nginx on 443)?
- A) 23
- B) 161
- C) 48101
- D) 8080

**Q040.** The GSMA IoT Security Assessment scores a device across eight areas. Which of the following is one of those eight areas?
- A) Asset identification (via MUD/DMA)
- B) Secure boot
- C) Interface logical access (per EAP)
- D) Device configuration (via SENSEI)

## Module 09 — Administrative Application Security (Q041–Q045)

**Q041.** Which statement correctly contrasts whitelisting and blacklisting?
- A) Whitelisting is threat-centric (allow by default, deny known-bad); blacklisting is trust-centric (deny by default, allow approved)
- B) Whitelisting is trust-centric (deny by default, allow only approved); blacklisting is threat-centric (allow by default, deny known-bad)
- C) Both approaches constantly rely on signature and application updates to stay secure
- D) Whitelisting cannot mitigate zero-day attacks, while blacklisting can

**Q042.** A network defender wants a Software Restriction Policy rule that keeps applying to an executable no matter where it is moved or renamed on the disk. Which SRP rule type provides this behavior?
- A) Path rule
- B) Certificate rule
- C) Hash rule
- D) Internet zone rule

**Q043.** An endpoint must surf the web in an isolated environment that blocks websites from reaching local storage, memory, other installed applications, and corporate network endpoints, using hardware virtualization with SLAT support. Which technology is described?
- A) Windows Sandbox
- B) Windows Defender Application Guard (WDAG) for Microsoft Edge
- C) Just Enough Administration (JEA)
- D) Software Restriction Policies

**Q044.** According to the courseware, what is the correct sequence of the automated application patch-management process?
- A) Scan for new/missing patches → download patches to a central location → select the relevant patch → test the patch → deploy if the test succeeds
- B) Download patches → scan for new/missing patches → deploy → test
- C) Test → scan → select → download → deploy
- D) Scan → select → deploy → test → verify

**Q045.** Which of the following is a documented LIMITATION of a web application firewall (WAF)?
- A) It inspects traffic at layer 7 and can therefore detect database-command attacks even those a misconfigured SQL parser missed
- B) It provides out-of-band protection against false positives
- C) It cannot read database commands and therefore does not provide complete protection against web-application attacks
- D) It replaces the need for user authentication and input filtering in the web application

## Module 10 — Data Security (Q046–Q050)

**Q046.** A security analyst must map safeguards to the state of a data asset. According to the courseware, which control pairing corresponds to the two listed data states — data in transit and data in use?
- A) In transit → SSL/TLS, PGP/S-MIME ; in use → memory encryption, strong identity
- B) In transit → tokenization ; in use → password protection
- C) In transit → brief form only ; in use → discard methods
- D) In transit → DLP only ; in use → audit trail

**Q047.** An application must perform equality comparisons on an encrypted column: the same plaintext value must always yield the same ciphertext. The database engine must never see the encryption keys. Which SQL Server encryption feature and mode fits this requirement?
- A) Always Encrypted with randomized encryption
- B) Always Encrypted with deterministic encryption
- C) Transparent Data Encryption (TDE) with encryption only at rest
- D) Column-level encryption stored with the key in the database

**Q048.** During an Oracle data-masking project, an Enterprise Manager discovery job locates columns holding 15/16-digit credit-card and 9-digit Social Security numbers, assigning them a sensitive-column type such as CREDITCARDNUMBER. Which step of the courseware's F.A.S.T. data-masking methodology does this correspond to?
- A) Find
- B) Access
- C) Secure
- D) Test

**Q049.** An Oracle DBA takes a consistent, closed-database backup so the files can be restored without the archive logs. Which sequence matches the courseware's cold-backup procedure?
- A) STARTUP MOUNT → BACKUP DATABASE → SHUTDOWN IMMEDIATE → ALTER DATABASE OPEN
- B) SHUTDOWN IMMEDIATE → STARTUP MOUNT → BACKUP DATABASE → ALTER DATABASE OPEN
- C) SHUTDOWN NORMAL → BACKUP DATABASE PLUS ARCHIVELOG → STARTUP
- D) ALTER DATABASE OPEN → BACKUP DATABASE → SHUTDOWN IMMEDIATE

**Q050.** A hard disk must be prepared for a vendor's laboratory-grade forensic attempt to recover data with signal-processing tools. Which destruction technique and documented characteristic is correct?
- A) Clearing — an overwrite defends against laboratory attacks
- B) Purging — degaussing/Secure Erase defends against laboratory attacks
- C) Disposal — guarantees complete erasure of non-confidential media
- D) Destroying — applies only to software-based erasure

## Draft scaffold
- Modules 09–20: one 5-item block each, generated from the corresponding module OCR content.
