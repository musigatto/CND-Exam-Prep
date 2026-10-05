---
type: exam
module: "mock"
tags: [exam, mod/01]
topic: "CND Mock Exam — 100 shuffled, no answers"
exam_weight: high
status: draft
unresolved:
  - "Shuffle seed 31238 over bank order Q001–Q100; item order only, stems/options/letters untouched so [[Answer-Key]] grades by Q number."
  - "No pass mark is applied when self-grading; official cut score is form-dependent (60-85%), see [[Exam-Facts]]."
---
# Mock Exam 100

> [!warning] No answers here.
> 4 hours · 100 single-best-answer · official format is Multiple Choice.
> **There is no fixed pass score** — EC-Council's cut score varies by form (60%–85%).
> Self-grade as a percentage and compare against your own target. See [[Exam-Facts]].
> Grade via [[Answer-Key]].

## Instructions
- Same 100 items as the [[Question-Bank]], shuffled (seed 31238).
- Each item keeps its bank Q number — grade with [[Answer-Key]].
- Mark your sheet, grade with [[Answer-Key]].

## Questions

**1.** [Q040] The GSMA IoT Security Assessment scores a device across eight areas. Which of the following is one of those eight areas?
- A) Asset identification (via MUD/DMA)
- B) Secure boot
- C) Interface logical access (per EAP)
- D) Device configuration (via SENSEI)

**2.** [Q096] How many threat-intelligence types are described in full, and what is the catch?
- A) Three — Strategic, Tactical, and Operational — and the module never mentions any other type
- B) Two — Strategic for executives and Technical for security teams — and the rest are vendor terms
- C) Five — Strategic, Tactical, Operational, Technical, and Professional Services — all defined in prose
- D) Four with prose each — Strategic, Tactical, Operational, and Technical — but the p9/p10 framing announces only three, with Technical printed unannounced on p14

**3.** [Q055] Under Kubernetes RBAC, a user wants to create a ClusterRole that grants read access to pods across the entire cluster. When may that user do so?
- A) When they already hold every permission contained in the role, at the same scope as the role - which for a ClusterRole means cluster-wide
- B) When they hold read access to pods in at least one namespace
- C) Whenever they are authenticated to the cluster, because the RBAC API already prevents privilege escalation
- D) Only after a cluster administrator assigns that ClusterRole to them

**4.** [Q013] A technician must centrally administer switches, routers, and firewalls while encrypting the entire client–server communication including the username and password. Which AAA protocol fits?
- A) RADIUS over UDP ports 1812/1813
- B) TACACS+ over TCP port 49
- C) Kerberos as a Ticket-Granting Service
- D) S/MME with a CA-issued certificate

**5.** [Q066] Which of the following packet patterns is flagged as illegal?
![IMG-NEEDED: assets/14-illegal-packet-flags.png — illegal TCP flag combinations, Wireshark-style capture]
- A) A TCP packet carrying FIN ACK, followed by an ACK
- B) A TCP packet carrying RST and RST ACK
- C) A TCP packet carrying PSH FIN and ACK
- D) A packet with only the SYN bit set and any other data present

**6.** [Q053] Attacks on the SDN Data Plane fall into exactly three attack types. Which set is correct?
- A) Device Attack, Protocol Attack, Side Channel Attack
- B) Device Attack, Protocol Attack, Northbound API Attack
- C) Device Attack, Protocol Attack, Control Plane Attack
- D) Firmware Attack, TCAM Attack, Timing Attack

**7.** [Q021] A Windows service is installed so that it runs under its own dedicated account with its own SID, and Windows sets the password and changes it periodically. Which Windows security feature is this, and under what name form does it run?
- A) Mandatory Integrity Control — named by its integrity level
- B) Virtual service account — `NT SERVICE\<service name>`
- C) Securable object — named by the Kernel Object Manager
- D) Local Security Authority — `NT AUTHORITY\SYSTEM`

**8.** [Q015] A network defender wants a single security console that provides firewall, IDS, anti-malware, spam filtering, content filtering, DLP, and VPN, while accepting the risk of a single point of failure. Which solution is described?
- A) Load balancer with round-robin algorithm
- B) SIEM with correlated events
- C) UTM (Unified Threat Management)
- D) Network Access Control appliance

**9.** [Q062] A security team discovers several wireless access points inside the office. What is the rule for deciding whether a discovered AP is rogue?
- A) An AP is rogue if its SSID matches the corporate SSID, because the corporate APs use a hidden SSID
- B) An AP is rogue if it is broadcasting an SSID, because the corporate APs are configured not to broadcast theirs
- C) An AP is rogue if it does not support the strongest available encryption mode, and it should be upgraded in place
- D) The detected wireless APs are compared with the wireless device inventory for the environment; if an AP that is not listed in the inventory is found, it can generally be considered a rogue AP

**10.** [Q020] In a Software-Defined Perimeter, which component is the authentication point that evaluates the policy, grants access to the client, and determines which gateways the client may communicate with?
- A) SDP gateway (accepting host)
- B) SDP client (initiating host)
- C) Single-Packet Authorization service
- D) SDP controller

**11.** [Q065] Which sequence orders wireless encryption modes from most to least preferred?
- A) WPA3 → WPA2 Enterprise with RADIUS → WPA2 Enterprise → WPA Enterprise → WPA2 PSK → WPA → WEP
- B) WPA3 → WPA2 Enterprise → WPA2 Enterprise with RADIUS → WPA2 PSK → WPA Enterprise → WPA → WEP
- C) WPA2 Enterprise with RADIUS → WPA3 → WPA2 Enterprise → WPA2 PSK → WPA Enterprise → WPA → WEP
- D) WPA3 → WPA2 Enterprise with RADIUS → WPA2 Enterprise → WPA2 PSK → WPA Enterprise → WPA → WEP

**12.** [Q075] Which statement about the two types of log correlation is correct?
- A) Micro-level correlation relates events across multiple systems to validate the event stream; macro-level correlation correlates the fields within a single event
- B) Micro-level correlation is performed only after raw event data has been normalized, is also known as atomic correlation, and is divided into field correlation and rule correlation; macro-level correlation is performed on raw data **before** normalization
- C) Micro-level correlation is performed only when raw event data has been normalized, is also known as atomic correlation, and is divided into field correlation and rule correlation; macro-level correlation gains information from rule correlation, vulnerability correlation, profile (fingerprint) correlation and anti-port correlation to validate and gain intelligence on the event stream
- D) Macro-level correlation is the only type the module defines, because micro-level correlation requires normalized data that log sources do not provide

**13.** [Q016] A firewall checks each packet's header against a rule set and makes its decision independently at the network level of the OSI model, without tracking session state. Which firewall technology is this?
- A) Application-level gateway
- B) Packet filtering firewall
- C) Circuit-level gateway
- D) Stateful multilayer inspection firewall

**14.** [Q039] A network defender monitors the IoT fleet managed with SeaCat.io. Which port carries the SeaCat mutual-TLS gateway tunnel (alongside Nginx on 443)?
- A) 23
- B) 161
- C) 48101
- D) 8080

**15.** [Q005] an intrusion is mapped to MITRE ATT&CK for Enterprise. The 11 tactic categories used are derived from which sources?
- A) The Reconnaissance, Weaponization, and Delivery stages of the Cyber Kill Chain
- B) The Exploit, Control, Maintain, and Execute stages of the Cyber Kill Chain
- C) The five phases of the CEH hacking methodology
- D) The OWASP Top 10 risk list

**16.** [Q008] An organization wants to block all Internet services by default and only enable each service that the network defender individually deems safe and necessary, while logging everything. Which Internet access policy type is this?
- A) Promiscuous
- B) Permissive
- C) Paranoid
- D) Prudent

**17.** [Q078] According to Table 16.1, how does MDR differ from EDR and XDR in nature, data, and response?
- A) MDR is a technology that monitors endpoints only, uses signature-based detection, and automates isolating endpoints
- B) MDR is a technology extending EDR to cloud services and networks, uses ML and AI over multiple sources, and automates blocking malicious network connections
- C) MDR is a managed security service running on analytics and human expertise, but it is usually less automated than EDR and XDR because vendors only advise
- D) MDR is a managed security service drawing data from networks, applications, endpoints and cloud services, running on analytics and human expertise, and usually more automated than EDR/XDR because third-party vendors manage it

**18.** [Q004] Which security approach uses methods such as IDS, SIMS, TRS, and IPS to address attacks that the preventive approach failed to avert?
- A) Preventive
- B) Reactive
- C) Retrospective
- D) Proactive

**19.** [Q011] An enterprise deploys honeypots to study attacker behavior in isolation. The network defenders discover exactly how attacks unfold step by step in order to develop new countermeasures. Which honeypot type is this?
- A) Production honeypot
- B) Low-interaction honeypot
- C) Research honeypot
- D) Pure honeypot

**20.** [Q082] Comparing BCP and DRP goals, which goal belongs to the DRP rather than the BCP?
- A) Providing staff training, building awareness, and promoting disaster preparedness with pre-defined communications
- B) Maintaining vital documents and details such as telephone numbers and employee, vendor, and client details
- C) Restoring business conditions to pre-disaster levels and minimising infrastructural damage
- D) Alleviating concerns of senior management, with goals and scope aligned to their expectations and submitted for approval

**21.** [Q064] Which two issues are listed only under WPA2?
- A) A predictable group temporal key from an insecure RNG, and TKIP vulnerabilities that allow subnet IP guessing and small-packet injection
- B) A wireless denial of service in which attackers exploit replay-attack detection to send forged group-addressed data frames with a large PN, and Wi-Fi protected setup PIN recovery that discloses the WPA2 key
- C) Known-plaintext attacks on an IV collision, and dictionary attacks because WEP is password based
- D) CRC-32 being insufficient to ensure complete cryptographic integrity, and the initialization vector being sent in the cleartext portion of a message

**22.** [Q018] An IDS cannot detect intrusions when they are encapsulated in encrypted traffic because encrypted payloads cannot be matched to signatures. What is the recommended fix?
- A) Place the IDS behind a VPN termination with SSL encryption
- B) Increase the IDS sensitivity threshold
- C) Disable stateful protocol analysis on the sensor
- D) Deploy the sensor outside the firewall in stealth mode

**23.** [Q045] Which of the following is a documented LIMITATION of a web application firewall (WAF)?
- A) It inspects traffic at layer 7 and can therefore detect database-command attacks even those a misconfigured SQL parser missed
- B) It provides out-of-band protection against false positives
- C) It cannot read database commands and therefore does not provide complete protection against web-application attacks
- D) It replaces the need for user authentication and input filtering in the web application

**24.** [Q036] In IoT, two connected devices exchange data directly using Bluetooth, Z-Wave, ZigBee, or Wi-Fi, without the cloud being in the flow during the interaction. Which IoT communication model is this?
- A) Device-to-Cloud
- B) Device-to-Gateway
- C) Device-to-Device
- D) Back-end Data-Sharing

**25.** [Q044] What is the correct sequence of the automated application patch-management process?
- A) Scan for new/missing patches → download patches to a central location → select the relevant patch → test the patch → deploy if the test succeeds
- B) Download patches → scan for new/missing patches → deploy → test
- C) Test → scan → select → download → deploy
- D) Scan → select → deploy → test → verify

**26.** [Q090] In the DPIA process, which sequence is correct?
- A) Identify need → describe the processing → consider consultation → assess necessity and proportionality → identify and assess risks → identify mitigation measures → sign off and record → integrate outcome into plan → keep under review, repeating the DPIA on substantial changes
- B) Describe the processing → identify need → integrate outcome into plan → sign off and record → keep under review → assess necessity → identify risks → identify measures → consider consultation
- C) Identify need → keep under review → describe the processing → integrate outcome → assess risks → sign off → consider consultation → identify measures → assess necessity
- D) Consider consultation → identify need → describe the processing → sign off and record → integrate outcome → identify risks → identify measures → assess necessity → archive the DPIA permanently

**27.** [Q033] An organization wants MDM capabilities without maintaining servers on its premises; it accepts monthly/annual fees to negate the up-front cost while still having management and admission. Which MDM delivery method fits this need?
- A) Premise-based MDM
- B) SaaS-based MDM
- C) Managed services-based MDM
- D) Host-based MDM

**28.** [Q093] Which IoE tool belongs to each attack surface?
- A) System: amass; Application: AttackSurfaceMapper; Network: SPF and SET; Human: Attack Surface Analyzer
- B) System: Attack Surface Analyzer and the Windows Sandbox Attack Surface Analysis Tool; Application: OWASP Attack Surface Detector; Network: AttackSurfaceMapper and amass; Human: phishing frameworks such as SPF, SoSafe, and SET
- C) System: ThreatPath; Application: Skybox; Network: Infection Monkey; Human: Cymulate
- D) System: Nmap and Netcat; Application: Unicornscan; Network: Angry IP Scanner; Human: PhishThreat

**29.** [Q010] Which access rule applies when a user holds the "Secret" data classification level?
- A) Access to Secret, Confidential, Restricted, and Unclassified (but not Top Secret)
- B) Access to all levels including Top Secret
- C) Access limited to Secret only
- D) Access to Unclassified only unless explicitly granted

**30.** [Q042] A network defender wants a Software Restriction Policy rule that keeps applying to an executable no matter where it is moved or renamed on the disk. Which SRP rule type provides this behavior?
- A) Path rule
- B) Certificate rule
- C) Hash rule
- D) Internet zone rule

**31.** [Q037] An attacker exploits the OBEX Push profile to gain access to data on a nearby phone; a second attacker remotely controls a compromised device to execute AT commands, connect to the Internet, and place calls. Which Bluetooth attacks are described, respectively?
- A) Bluejacking then BlueSmack
- B) Car Whisperer then KNOB
- C) BlueBugging then Bluesnarfing
- D) Bluesnarfing then BlueBugging

**32.** [Q071] Log severity levels are numbered 0 to 7. Which statement about that scale is correct?
- A) Severity level 0 indicates a debugging message of the least importance, and severity level 7 indicates an emergency of the greatest importance
- B) Each severity level is given only a name, because the numeric value is optional; the names run from least to most severe
- C) Severity level 7 indicates an emergency of the greatest importance, and severity level 0 indicates a debugging message of the least importance
- D) Severity level 0 indicates an emergency of the greatest importance, and severity level 7 indicates a debugging message of the least importance; the lower severity number represents a higher severity and vice-versa

**33.** [Q025] Which of the following does DNSSEC guarantee by adding digital signatures to DNS information?
- A) Confidentiality and Denial-of-Service protection
- B) Authenticity, integrity, and the non-existence of a domain name or type
- C) Availability and load balancing of Authoritative DNS servers
- D) Encryption of DNS queries between client and resolver

**34.** [Q087] How do mitigation, remediation, and verification differ?
- A) Mitigation corrects the discovered vulnerability; remediation proves the vulnerabilities are solved; verification identifies issues before attackers find them
- B) Mitigation proves the vulnerabilities are solved; remediation acts without fixing; verification corrects the discovered vulnerability
- C) Mitigation, remediation, and verification are three names for the same step: correcting a discovered vulnerability and proving it solved
- D) Mitigation acts without fixing the vulnerability — the printed example is installing a web application firewall instead of fixing the web application vulnerability; remediation corrects the discovered vulnerability; verification ensures the vulnerabilities have been solved

**35.** [Q001] Which of the following best represents how risk is calculated in network security?
- A) Risk = Asset + Threat + Vulnerability
- B) Risk = Motive + Method + Vulnerability
- C) Risk = Asset + Motive + TTPs
- D) Risk = Threat + Vulnerability + Motive

**36.** [Q097] According to Table 20.1 in the module, which row correctly contrasts IOCs with IOAs?
- A) IOCs are proactive indicators used in real time focusing on code execution and persistence; IOAs are reactive indicators usable only after a point in time focusing on malware and signatures
- B) IOCs monitor what (who) is known, are reactive and usable only after a point in time, focus on malware, signatures, exploits, vulnerabilities, and IP addresses, and miss new threats; IOAs are proactive, real-time, behavior-focused, and catch new unknown threats — with two IOA cells too garbled to read for meaning
- C) IOCs and IOAs are identical in every row; the table exists only to show that both detect new unknown threats proactively
- D) IOCs focus on code execution and lateral movement while IOAs focus on file hashes and IP addresses

**37.** [Q091] Which statement correctly defines the attack surface and states the standard practice for it?
- A) The sum of all possible security exposures — known, unknown, and potential — through which an unauthorized user can reach assets; standard practice keeps it as minimum as possible
- B) The sum of all known vulnerabilities listed in the asset inventory; standard practice keeps the inventory as large as possible for visibility
- C) The sum of all possible exposures, counting only unknown and potential ones since known ones are already patched; standard practice maximizes monitoring of the unknown set
- D) The sum of all user input fields in web applications; standard practice validates them once at deployment

**38.** [Q009] During the first phase of IT asset management, the team discovers and documents all assets and then groups them. Which grouping basis is used?
- A) By KPI and SLA thresholds
- B) By type, usage, location, owner/department, lifecycle stage, criticality, and license type
- C) By threat severity and vulnerability score
- D) By procurement cost and depreciation

**39.** [Q052] An attacker with a foothold on a switch floods the CAM table with a large number of fake MAC addresses. Once the table is full, what happens, and what is this attack called?
- A) The switch drops all frames with unknown destinations; this is DHCP starvation
- B) Traffic that has no MAC entry floods out to all ports of the VLAN, making it easier for the attacker to view and retrieve traffic; this is MAC flooding
- C) The ARP table is poisoned so the attacker impersonates the gateway; this is an ARP attack
- D) The attacker becomes the new root bridge and installs junk data; this is a spanning-tree attack

**40.** [Q049] An Oracle DBA takes a consistent, closed-database backup so the files can be restored without the archive logs. Which sequence matches the cold-backup procedure?
- A) STARTUP MOUNT → BACKUP DATABASE → SHUTDOWN IMMEDIATE → ALTER DATABASE OPEN
- B) SHUTDOWN IMMEDIATE → STARTUP MOUNT → BACKUP DATABASE → ALTER DATABASE OPEN
- C) SHUTDOWN NORMAL → BACKUP DATABASE PLUS ARCHIVELOG → STARTUP
- D) ALTER DATABASE OPEN → BACKUP DATABASE → SHUTDOWN IMMEDIATE

**41.** [Q022] A network defender must stop the built-in Guest account from being used for password-less, unauthenticated Internet access on a workstation. Which command disables it?
- A) `net user guest /active:No`
- B) `net user Guest *`
- C) `sc config Guest start= disabled`
- D) `Disable-ADAccount -Identity Guest`

**42.** [Q070] Why is passive OS fingerprinting difficult for defenders to detect, and which IP/TCP header fields does it rely on?
- A) It is difficult because the attacker encrypts the probes; it relies on the MAC address, the IP TTL and the port number
- B) It is difficult because the target's TTL changes when a packet traverses two routers; it relies on the TCP sequence number, the window size and the checksum
- C) It is difficult because it requires the target to answer an ICMP echo request; it relies on the ICMP timestamp request (13), information request (15) and address mask request (17)
- D) It is difficult because the attacker sends no packets at all, so firewalls and other security devices cannot detect it and the defender must find it manually with packet sniffing tools; it relies on the initial TTL, the do-not-fragment flag, the maximum segment size, the window size and the selective ACK (SACK) OK

**43.** [Q051] In OS-assisted (para) virtualization, who translates the guest's commands into binary instructions for the computer hardware, and is the VMM involved in the request and response operations?
- A) The VMM translates the commands and forwards the result to the host OS
- B) The guest OS translates its own commands, and the VMM is not involved in the request and response operations
- C) The microprocessor translates the commands using special virtualization instructions, and the VMM still allocates resources
- D) The guest OS and the VMM each translate, depending on the type of resource being requested

**44.** [Q030] To confine SFTP users inside a chroot jail so they cannot browse other users' directories, which configuration must be appended to `/etc/ssh/sshd_config`?
- A) `Subsystem sftp /usr/libexec/openssh/sftp-server`
- B) `PermitRootLogin no` and `AllowUsers sftponly`
- C) `Subsystem sftp internal-sftp` with a `Match group sftponly` block setting `ChrootDirectory /sftp/`, `X11Forwarding no`, `AllowTcpForwarding no`, and `ForceCommand internal-sftp`
- D) `UsePAM yes` and `LogLevel VERBOSE`

**45.** [Q050] A hard disk must be prepared for a vendor's laboratory-grade forensic attempt to recover data with signal-processing tools. Which destruction technique and documented characteristic is correct?
- A) Clearing — an overwrite defends against laboratory attacks
- B) Purging — degaussing/Secure Erase defends against laboratory attacks
- C) Disposal — guarantees complete erasure of non-confidential media
- D) Destroying — applies only to software-based erasure

**46.** [Q067] According to Table 14.2, UEBA can detect threats involving a wider class of actors than UBA. Which pairing is correct?
- A) UBA detects threats involving malware, human actors or machine actors; UEBA detects only human actors or malware
- B) UBA detects only human actors or malware and provides **more** visibility into network activity; UEBA detects malware, human actors or machine actors and provides **limited** visibility
- C) UBA detects only human actors or malware and provides **limited** visibility into network activity; UEBA detects threats involving malware, human actors or machine actors and provides **more** visibility into network activity and context
- D) UBA and UEBA detect the same classes of actor; they differ only in data sources — event logs versus multiple sources

**47.** [Q019] A network defender wants to allow only a single MAC address per port on an access switch. Which port-security method is this?
- A) Dynamic — MAC held in CAM
- B) Sticky — MAC saved across reboot
- C) Static — only a single MAC allowed
- D) AAA-based port authentication

**48.** [Q095] Which pair correctly matches an IoT area to its printed example vulnerabilities?
- A) Device Firmware: SQL injection, cross-site scripting, and username enumeration
- B) Device Firmware: hardcoded and default credentials never reset by the consumer, and botnets exploiting default credentials; Update Mechanism: updates sent without encryption, unsigned updates, writable update location
- C) Local Data Storage: weak authentication, weak access control, and injection attacks
- D) Ecosystem Communication: clear-text credentials in memory and monitoring of cipher keys

**49.** [Q072] Which pairing of log-transfer mechanism to example is correct?
- A) Push-based — Check Point's OPSEC C library; pull-based — syslog and SNMP
- B) Push-based — syslog and SNMP; pull-based — syslog and SNMP, because either protocol can be initiated by either end
- C) Push-based — syslog and SNMP, which send log records over the network to a log collector; pull-based — Check Point's OPSEC C library, because a pulling system usually reads the source's proprietary format
- D) Push-based — Windows Event Viewer, which saves records to the local disk; pull-based — SNMP, which retrieves records from a proprietary-format store

**50.** [Q086] In the risk treatment list, which pairing of option to printed definition is correct?
- A) Eliminate the Risk means applying controls to reduce the threat of exploiting the vulnerability to zero; Accept the Risk applies when the factor is at an acceptable level, accepted when efforts to address, transfer, or mitigate exceed the impact on the network
- B) Mitigate the Risk means avoiding the factor that enhances business-process risk, for example not allowing laptops; Risk Avoidance means reducing risks through direct or competing controls
- C) Transfer the Risk means reducing the likelihood rate to an acceptable level through safety controls; Reduce the Risk means shifting responsibilities to another party through insurance or partnership
- D) Accept the Risk means applying controls to reduce the threat of exploiting the vulnerability to zero; Eliminate the Risk applies when efforts to address the risk exceed its impact

**51.** [Q099] In the threat-hunting maturity model, which level description is correct?
- A) Level 0 Initial (HMMO): full collection with automated hunting; most organizations are Leading
- B) Level 4 Leading: no collection at all, lives entirely on open-source feeds
- C) Level 0 Initial (HMMO): no data collection, relies on open-source TI indicators and lower-Pyramid data; Level 2 Procedural (others' processes) is where most organizations sit; Level 4 Leading automates the majority of successful procedures
- D) Level 2 Procedural: creates brand-new procedures with ML fluency; Level 3 Innovative: follows others' processes

**52.** [Q079] In the alert-classification table, which definition appears under the True Negative row?
- A) No alarm is raised when an actual attack occurred, caused by rules not defined properly
- B) An alarm is raised when an actual attack occurred, so act immediately to stop it continuing
- C) An alarm is raised when no attack is detected, with non-malicious files rejected successfully — the False Positive wording printed under the True Negative name
- D) No alarm is raised and no attack occurred, so the event is registered with no further action

**53.** [Q026] A Linux administrator runs `find / -perm +4000` and receives a long list of binaries such as `chfn`, `gpasswd`, and `sudo`. What is the purpose of this command?
- A) To list all files that are world-writable
- B) To view all files with the SUID (set-user-id) bit set
- C) To locate all directories with the SGID bit set
- D) To find all files owned by the root user

**54.** [Q060] Which security principal types can be members of an Azure role assignment, and at which scopes may a role be assigned?
- A) Only user and group, and only at management-group scope
- B) User, group and service principal — at subscription, resource group or single resource scope
- C) User, group, service principal and managed identity — at tenant and management-group scope
- D) User, group, service principal and managed identity — at subscription, resource group or single resource scope

**55.** [Q003] A web application uses SSL/TLS only for the login page, and a packet sniffer is used to intercept the session cookie afterwards. Which session hijacking method is used?
- A) Session fixation
- B) Cookie theft by malware
- C) Session side-jacking
- D) CSRF injection

**56.** [Q054] Docker provides five native network drivers, used through Docker network commands. Which set lists them correctly?
- A) Host, Bridge, Overlay, MACVLAN, None
- B) Host, Bridge, Overlay, macvlan, ipvlan
- C) Host, Bridge, MACVLAN, Overlay, macvtap
- D) Bridge, Overlay, MACVLAN, macvtap, IPAM

**57.** [Q085] Which statement about the BC/DR standards is correct?
- A) ISO 22313:2012 states the BCMS requirements, while ISO 22301:2019 only guides their implementation
- B) ASIS is a government-authorized body whose ORM.1 standard members must enforce under FINRA Rule 4370
- C) FINRA Rule 4370 requires each member to keep a written BCP and report one emergency contact to FINRA
- D) ISO 22301:2019 states the generic BCMS requirements while ISO 22313:2012 guides ISO 22301 with good international practice; FINRA members report two emergency contacts, at least one a senior-management registered principal

**58.** [Q048] During an Oracle data-masking project, an Enterprise Manager discovery job locates columns holding 15/16-digit credit-card and 9-digit Social Security numbers, assigning them a sensitive-column type such as CREDITCARDNUMBER. Which step of the F.A.S.T. data-masking methodology does this correspond to?
- A) Find
- B) Access
- C) Secure
- D) Test

**59.** [Q063] Which pair of figures quantifies how quickly WEP encryption fails?
- A) An AP broadcasting 1500-byte packets at 11 Mb/s exhausts the entire IV space in **five hours**, and about **24 GB** of reconstructed key stream allows an attacker to decrypt WEP packets in real time
- B) An AP exhausts the entire IV space in five years, and about 24 MB of reconstructed key stream allows real-time decryption
- C) An AP broadcasting 1500-byte packets at 11 Mb/s exhausts the IV space in 224 hours, and about 24 GB of key stream allows decryption of a single packet only
- D) WEP's 24-bit IV space allows 2^24 values, which the module states is large enough that exhaustion is not a practical concern

**60.** [Q014] Which IPsec service authenticates the sender but does NOT encrypt the data?
- A) Authentication Header (AH)
- B) Encapsulating Security Payload (ESP)
- C) Tunnel mode only
- D) The TLS Record Protocol

**61.** [Q092] In the four-step analysis pipeline, what happens in the Simulate step, and what answers it?
- A) Mapping all devices, paths, and networks to understand the surface; it answers where the assets are
- B) Implementing controls and countermeasures to close unneeded doors; it answers how the fix performed on retest
- C) Collecting potential risk exposures from firewalls and logs; it answers which events are worth alerting on
- D) Recognizing how identified IoEs could turn into exploits and how the organization looks from the attacker's perspective, via virtual pentesting; a small input or change answers exploit paths, asset-move, topology, policy, and directional effects

**62.** [Q038] A security tester wants to enumerate and attack ZigBee/IEEE 802.15.4 networks and needs tools such as `zbdump`, `zbconvert`, `zbreplay`, and `zbstumbler`. Which framework provides these?
- A) KillerBee
- B) Aircrack-ng
- C) beSTORM
- D) RloT Scanner

**63.** [Q058] In AWS data-at-rest encryption Model B, who stores the keys, who controls the encryption algorithm, and can AWS employees read the keys?
- A) AWS provides the key storage layer — keys sit in AWS CloudHSM and are inaccessible to any AWS employee — while the customer provides the KMI and manages the encryption algorithm and key management, communicating with CloudHSM over SSL
- B) The customer provides the key storage layer, while AWS provides the encryption algorithm and manages key management
- C) AWS provides key storage, the encryption algorithm and key management; the customer only holds the data
- D) The customer provides the KMI and manages encryption, key storage and key management entirely on-premises, with no AWS component

**64.** [Q089] According to Table 18.1 in the module, what action does the Extreme/High risk level require?
- A) Stop the activity unless the risk is reduced to a low or medium level
- B) Immediate measures: isolate, eliminate, and substitute the risk through effective risk controls
- C) Take preventive steps and ignore the risk with periodical review, since it poses no significant problem
- D) Identify and impose controls with strict timelines while the existing system continues to operate

**65.** [Q076] Which sequence is the nine-step forensics investigation methodology?
- A) Evaluate and secure the scene → obtain a search warrant → collect the evidence → acquire the data → secure the evidence → analyze the data → prepare the final report → assess the evidence → testify as an expert witness
- B) Obtain a search warrant → collect the evidence → evaluate and secure the scene → acquire the data → secure the evidence → assess the evidence → analyze the data → testify as an expert witness → prepare the final report
- C) Obtain a search warrant → evaluate and secure the scene → acquire the data → collect the evidence → analyze the data → secure the evidence → assess the evidence → prepare the final report → testify as an expert witness
- D) Obtain a search warrant → evaluate and secure the scene → collect the evidence → secure the evidence → acquire the data → analyze the data → assess the evidence and the case → prepare the final report → testify as an expert witness

**66.** [Q032] A vulnerability unintentionally introduced by a manufacturer into a mobile keyboard such as SwiftKey belongs to which risk category?
- A) Physical risks and challenges
- B) Network-based risks and challenges
- C) System-based risks and challenges
- D) Application-based risks and challenges

**67.** [Q041] Which statement correctly contrasts whitelisting and blacklisting?
- A) Whitelisting is threat-centric (allow by default, deny known-bad); blacklisting is trust-centric (deny by default, allow approved)
- B) Whitelisting is trust-centric (deny by default, allow only approved); blacklisting is threat-centric (allow by default, deny known-bad)
- C) Both approaches constantly rely on signature and application updates to stay secure
- D) Whitelisting cannot mitigate zero-day attacks, while blacklisting can

**68.** [Q024] Which Windows access-management approach grants users only the specific cmdlets, scripts, and functions they need, defined through role capability files and session configuration files?
- A) Just Enough Administration (JEA)
- B) User Account Control elevation
- C) Smart App Control
- D) Local Security Policy assignments

**69.** [Q006] A security consultant is building an organization's compliance program. Which of the following represents the correct hierarchy?
- A) Standards → Policies → Frameworks → Procedures
- B) Frameworks → Policies → Standards → Procedures
- C) Policies → Frameworks → Guidelines → Standards
- D) Frameworks → Guidelines → Policies → Standards

**70.** [Q023] An administrator must configure the Windows Update service to start automatically so automatic updates continue. Which command accomplishes this?
- A) `sc config wuauserv start= auto`
- B) `net start wuauserv /persistent`
- C) `Enable-WindowsOptionalFeature -Online -FeatureName wuauserv`
- D) `Restart-Service wuauserv`

**71.** [Q084] Which sequence is the printed order of the five BC/DR activities?
- A) Prevention → Resumption → Response → Recovery → Restoration
- B) Prevention → Response → Resumption → Recovery → Restoration
- C) Response → Prevention → Recovery → Resumption → Restoration
- D) Prevention → Response → Recovery → Resumption → Restoration

**72.** [Q069] In a UDP port scan, what does an **open** UDP port return to the probe, and why is UDP scanning more difficult to probe than TCP scanning?
- A) An open UDP port returns an ICMP Type-3 Code-3 packet, because UDP scanning relies on the acknowledgements it receives
- B) An open UDP port returns RST or RST+ACK, because a UDP connection is terminated by a reset
- C) An open UDP port sends no response at all, because UDP scanning does not depend on the acknowledgements received — it instead gathers all the ICMP errors sent back by closed ports
- D) An open UDP port sends a SYN+ACK packet, because a UDP scan completes a three-way handshake

**73.** [Q059] Which statement about GCP service account keys is correct?
- A) GCP-managed keys can be downloaded by the customer and must be rotated every two weeks
- B) GCP-managed keys cannot be downloaded or automatically rotated and are used within two weeks, while user-managed keys are created, downloaded and managed by the user and expire after ten years
- C) Both key types are downloaded by the user, and both expire after ten years
- D) User-managed keys cannot be rotated — automatic rotation is available only for GCP-managed keys

**74.** [Q098] In the Pyramid of Pain, which order runs from least to most painful for the attacker, and what is the rule?
![IMG-NEEDED: assets/20-pyramid-of-pain.png — Pyramid of Pain, bottom hash values to apex TTPs]
- A) TTPs → Tools → Artifacts → Domains → IPs → Hashes, and defenders should move down for resilience
- B) Trivial Hash Values → Easy IP Addresses → Simple Domain Names → Annoying Network/Host Artifacts → Challenging Tools → Tough! TTPs, and moving up brings greater resilience at greater attacker cost
- C) IP Addresses → Hash Values → Domain Names → Tools → Artifacts → TTPs, and pain is equal at every level
- D) Hash Values → Domain Names → IP Addresses → TTPs → Tools → Artifacts, and defenders should focus on the bottom two levels only

**75.** [Q073] Which sequence is the printed process of centralized logging, monitoring, and analysis?
- A) Log Collection → Log Transmission → Log **Normalization** → Log **Storage** → Log Correlation → Log Analysis → Alerting and Reporting
- B) Log Collection → Log **Storage** → Log **Transmission** → Normalization → Log Correlation → Log Analysis → Alerting and Reporting
- C) Log Collection → Log Transmission → Log Storage → Normalization → Log **Analysis** → Log **Correlation** → Alerting and Reporting
- D) Log Collection → Log Transmission → Log Storage → Normalization → Log Correlation → Log Analysis → Alerting and Reporting

**76.** [Q012] Which NAC detection check is NOT performed for admission?
- A) Search for an antivirus program and check whether it has been updated
- B) Check if the end system has a configured firewall or intrusion prevention software
- C) Verify that the end user's device is on the latest Wi-Fi password
- D) Search for viruses and check whether the operating system has been updated

**77.** [Q081] Which pairing of RTO and RPO definitions is correct?
- A) RTO is the maximum tolerable length of time a computer, system, network, or application can be down after a failure or disaster; RPO is the maximum time frame for which an organisation loses data after a major IT outage
- B) RTO is the maximum time frame for which an organisation loses data after a major IT outage; RPO is the maximum tolerable length of time a system can be down after a failure or disaster
- C) RTO is the minimum time a system must stay down to guarantee a clean restore; RPO is the minimum backup frequency that guarantees zero data loss
- D) RTO is the maximum tolerable length of time a system can be down, determined by the backup time frame; RPO is the maximum time frame for data loss, established by the process owner

**78.** [Q017] An IDS sensor is placed outside the perimeter firewall.
![IMG-NEEDED: assets/04-ids-sensor-placement.png — IDS sensor outside the perimeter firewall] The team tunes it to the least-sensitive attacks so it logs attack attempts only, without raising alerts. Which deployment location is this?
- A) L1 — outside the perimeter firewall
- B) L2 — behind the external firewall in the DMZ
- C) L3 — major network backbone
- D) L4 — critical subnets

**79.** [Q061] According to Table 13.2 in the module, which set correctly matches each wireless security scheme to its integrity-check mechanism?
- A) WEP — Michael algorithm and CRC-32 · WPA — CRC-32 · WPA2 — CBC-MAC · WPA3 — BIP-GMAC-256
- B) WEP — CRC-32 · WPA — CBC-MAC · WPA2 — Michael algorithm and CRC-32 · WPA3 — CRC-32
- C) WEP — CRC-32 · WPA — Michael algorithm and CRC-32 · WPA2 — CBC-MAC · WPA3 — BIP-GMAC-256
- D) WEP — BIP-GMAC-256 · WPA — CRC-32 · WPA2 — Michael algorithm and CRC-32 · WPA3 — CBC-MAC

**80.** [Q094] Which cloud attack surface is called the most critical, and why?
- A) User to Cloud, because fake usage bills are the costliest incident class in the module
- B) Cloud to User, because the control plane is the hardest interface to define
- C) Service to Cloud — all types of attacks by the provider on a service running on it, easy to exploit with high impact
- D) Service to User, because every client-server attack in existence applies to it

**81.** [Q088] Which set lists the four features of effective KRIs?
- A) Measurable, predictive, historical, and financial — a KRI must attach a monetary value to every risk event
- B) Automated, continuous, centralised, and predictive — a KRI must feed directly into the SIEM without human review
- C) Quantifiable (number, count, or percentage), predictable (early warning signals), comparable (trackable over time), and informational (risk and control status)
- D) Qualitative, retrospective, static, and descriptive — a KRI looks backward at losses already booked

**82.** [Q002] An attacker floods a DHCP server with a large number of DHCP requests carrying spoofed MAC addresses, exhausting the available IP address pool. Which type of attack is this, and which tool is commonly used?
- A) DHCP spoofing, using a rogue DHCP server
- B) DHCP starvation, using Gobbler
- C) ARP poisoning, using Cain & Abel
- D) MAC flooding, using SMAC

**83.** [Q047] An application must perform equality comparisons on an encrypted column: the same plaintext value must always yield the same ciphertext. The database engine must never see the encryption keys. Which SQL Server encryption feature and mode fits this requirement?
- A) Always Encrypted with randomized encryption
- B) Always Encrypted with deterministic encryption
- C) Transparent Data Encryption (TDE) with encryption only at rest
- D) Column-level encryption stored with the key in the database

**84.** [Q035] The Android Device Administration API supports a policy by which the device wipes its data if the user enters the wrong password too many times. Which policy is this?
- A) Maximum inactivity time lock
- B) Password history restriction
- C) Maximum failed password attempts
- D) Disable camera

**85.** [Q027] A network defender must drop packets that have the characteristics of an XMAS scan. Which iptables rule blocks this scan?
- A) `iptables -A INPUT -p tcp --syn -m state --state NEW -j DROP`
- B) `iptables -A INPUT -p tcp --tcp-flags ALL ALL -j DROP`
- C) `iptables -A INPUT -f -j DROP`
- D) `iptables -A OUTPUT -p tcp --dports 25,465,587 -j REJECT`

**86.** [Q068] Which sequence is the printed seven-step process of network anomaly detection and behavior analysis?
- A) Data collection → baseline establishment → **alert correlation** → anomaly detection → alert generation → incident investigation → response and mitigation
- B) Data collection → baseline establishment → anomaly detection → alert generation → alert correlation → incident investigation → response and mitigation
- C) Baseline establishment → data collection → anomaly detection → alert generation → alert **investigation** → incident **correlation** → response and mitigation
- D) Data collection → anomaly detection → baseline establishment → alert generation → alert correlation → response and mitigation → incident investigation

**87.** [Q007] Which of the following is responsible for determining the purposes and means of processing personal data, while the other handles data on its behalf, under the GDPR?
- A) Data controller vs. data processor
- B) Data owner vs. data custodian
- C) Information owner vs. system admin
- D) DPO vs. DPO assistant

**88.** [Q083] In the BIA process, which statement is correct?
- A) Phase 4 (Risk modelling) follows Phase 3 and produces the prioritised process list
- B) Phase 1 is Presentation of the BIA Report, which management uses for DRP strategies
- C) The printed phases are Initiation, Acquisition of Information, Analysis of Information, and Presentation of the BIA Report — no Phase 4 is printed anywhere in the source
- D) Phase 2 is Analysis of Information, evaluated manually or by computer into a prioritised list

**89.** [Q034] According to the general mobile platform security guidelines, "Find My Device" (Android) and "Find My iPhone" or "FindMyPhone" (Apple iOS) are examples of which service?
- A) MDM blacklisting
- B) Application certification rules
- C) Secure backup-and-restore
- D) Remote wipe services

**90.** [Q031] An organization lets employees select their own smartphone or tablet from a list of devices approved by the company; the company purchases the selected device. Which mobile usage policy is this?
- A) BYOD
- B) COPE
- C) CYOD
- D) COBO

**91.** [Q043] An endpoint must surf the web in an isolated environment that blocks websites from reaching local storage, memory, other installed applications, and corporate network endpoints, using hardware virtualization with SLAT support. Which technology is described?
- A) Windows Sandbox
- B) Windows Defender Application Guard (WDAG) for Microsoft Edge
- C) Just Enough Administration (JEA)
- D) Software Restriction Policies

**92.** [Q029] Ubuntu's "minimal installation" option restricts the packages installed during the OS install, keeping only the desktop, web browser, and core system tools. Approximately how many packages does it remove compared with the default install?
- A) 20 packages
- B) 40 packages
- C) 80 packages
- D) 200 packages

**93.** [Q057] Which set lists exactly the four multi-factor authentication methods for AWS IAM?
- A) Virtual authenticator apps, TOTP hardware tokens, SMS one-time passcodes, email one-time passcodes
- B) FIDO security keys, TOTP hardware tokens, Thales tokens, Hypersecu tokens
- C) FIDO security keys, virtual authenticator apps, hardware TOTP tokens for standard AWS Regions, Windows Hello
- D) FIDO security keys, virtual authenticator apps, TOTP hardware tokens, and TOTP hardware tokens for the AWS GovCloud (US) Regions

**94.** [Q077] Under the First Response Rule, who may collect or recover data from a system holding electronic information, and how must everything inside collected devices be treated?
- A) Under no circumstances should anyone except forensic analysts collect or recover data, and everything inside collected devices is probable evidence that must be treated accordingly
- B) The first responder should collect data immediately to close the time gap, and everything inside collected devices is working evidence that may be freely examined
- C) Any member of the IRT may collect data once management is notified, and everything inside collected devices is internal evidence exempt from chain-of-custody rules
- D) The system administrator should collect data before the forensic team arrives to preserve running services, and everything inside collected devices is preliminary evidence for triage only

**95.** [Q028] Which SELinux mode "prints warnings instead of enforcing" the security policy?
- A) Enforcing
- B) Permissive
- C) Disabled
- D) Targeted

**96.** [Q056] A company buys directly from a cloud provider and separately engages an independent party to examine the provider's security controls and express an opinion on whether they meet the company's stated requirements. In the NIST cloud reference architecture, which actor performs that role, and what does the audit actually verify?
- A) Cloud broker — it combines multiple cloud services into a new service and audits the combined offering
- B) Cloud carrier — it provides connectivity and transport services and audits the data passing over them
- C) Cloud auditor — it independently examines the cloud service controls to express a corresponding opinion, and audits verify adherence to standards by reviewing objective evidence
- D) Cloud consumer — it examines the controls, expresses the opinion, and then renews the SLA if a security gap is found

**97.** [Q074] According to Table 15.16 and its surrounding text, which pairing of log file format to its printed characteristics is correct?
- A) IIS log file format — fixed, comma-separated, local time, and used for websites and not for FTP sites; NCSA Common — fixed, comma-separated, **UTC** time
- B) IIS log file format — fixed, **space**-separated, **UTC** time; NCSA Common — fixed, comma-separated, local time
- C) NCSA Common — fixed, comma-separated, local time; IIS log file format — fixed, **space**-separated, local time
- D) IIS log file format — fixed, comma-separated, local time; NCSA Common — fixed, **space**-separated, local time, and used for websites and not for FTP sites

**98.** [Q046] A security analyst must map safeguards to the state of a data asset. Which control pairing corresponds to the two listed data states — data in transit and data in use?
- A) In transit → SSL/TLS, PGP/S-MIME ; in use → memory encryption, strong identity
- B) In transit → tokenization ; in use → password protection
- C) In transit → brief form only ; in use → discard methods
- D) In transit → DLP only ; in use → audit trail

**99.** [Q100] Which statement about AI/ML for threat intelligence is correct?
- A) TI is most effective when used alone, and AI models are never biased so supervision is unnecessary
- B) LLMs can only summarize volumes; IOC and TTP extraction from unstructured sources is impossible by design
- C) AI/ML uses include summarization with LLMs, IOC extraction from unstructured social and dark-web sources, TTP extraction from long research documents, predictive intelligence, alert generation, LLM-streamlined exchange, decision support, and real-time TI — with guidelines demanding proactive use, tooling integration, alert quality, provenance transparency, CIA-prioritized resilience, and bias supervision
- D) The only printed AI use is guideline transparency; no AI capabilities or tools appear anywhere in the module

**100.** [Q080] According to the do's and don'ts, who decides whether to disconnect a suspected device, and what are the printed device-state and antivirus rules?
- A) The forensic examiner or IR team decides disconnect versus stay connected; ON stays ON and OFF stays OFF; disable virus protection as soon as possible because antivirus can change timestamps and auto-delete hacking tools
- B) The first responder must disconnect the device at once; ON stays ON and OFF stays OFF; keep antivirus running so it cleans malware before forensics arrives
- C) Management decides after the investigation concludes; devices may be restarted to preserve volatile evidence; disable virus protection only after imaging completes
- D) The forensic examiner or IR team decides disconnect versus stay connected; devices should be shut down to freeze evidence in place; keep antivirus running to log further attacker activity
