---
type: exam
module: "ext"
tags: [exam]
topic: "External Practice Questions — third-party harvested"
exam_weight: unknown
status: draft
unresolved:
  - "AguidetoCloud CND-V3 domain weights (14/18/20/14/14/20%) are third-party, NOT in the courseware PDFs → not used for exam_weight or blueprint distribution."
  - "Quizlet set 617277655 returned HTTP 403 (anti-bot). Not retrieved. No bypass attempted."
  - "Edusum/CertificationPractice items have no official answer key → answer column marked ? where unknown."
---
# External Practice Questions — third-party

> [!warning] Provenance
> These items come from **public third-party sites**, not from the 20 module PDFs.
> Per `AGENTS.md` ("never invent facts not in the PDFs") they are kept **out** of [[Question-Bank]] and [[Answer-Key]].
> Use them to cross-check the PDF-derived bank and to spot weak spots.
> Verbatim as published — typos preserved (`Hateful inspection`, `muIti-layer`).

## Harvest summary

| Source | Items | Answers given | Version | URL |
|--------|-------|---------------|---------|-----|
| Edusum | 10 | Yes (bare key) | 312-38 | https://www.edusum.com/ec-council/ec-council-cnd-312-38-certification-sample-questions |
| CertificationPractice | 20 | No | 312-38 | https://certificationpractice.com/practice-exams/ec-council-certified-network-defender-cnd |
| Daypo "CND 2" | 12 | No | CND v2 (2022) | https://www.daypo.com/cnd-2.html |
| PracticeTestGeeks PDF | 4 | Yes (all B) | generic | https://practicetestgeeks.com/pdf/Certified_Network_Defender_Practice_Test_Questions_and_Answers.pdf |
| A Guide to Cloud | 0 | — | CND v3 | paywalled — exam facts only, see [[#A Guide to Cloud — exam facts (not PDF-sourced)]] |
| Quizlet | 0 | — | — | HTTP 403 anti-bot, not retrieved |

**Total harvested: 46 questions.**

---

## Edusum — 10 items (312-38)

**E01.** A company wants to implement a data backup method that allows them to encrypt the data ensuring its security as well as access it at any time and from any location. What is the appropriate backup method that should be implemented?
- A) Cloud backup
- B) Hot site backup
- C) Offsite backup
- D) Onsite backup
**Answer: A**

**E02.** How is application whitelisting different from application blacklisting?
- A) It allows all applications other than the undesirable applications
- B) It allows execution of trusted applications in a unified environment
- C) It rejects all applications other than the allowed applications
- D) It allows execution of untrusted applications in an isolated environment
**Answer: C**

**E03.** Mark is monitoring the network traffic on his organization's network. He wants to detect TCP and UDP ping sweeps on his network. Which type of filter will be used to detect this?
- A) `tcp.dstport==7 and udp.srcport==7`
- B) `tcp.srcport==7 and udp.dstport==7`
- C) `tcp.dstport==7 and udp.dstport==7`
- D) `tcp.srcport==7 and udp.srcport==7`
**Answer: D**

**E04.** Which among the following tools can help in identifying IoEs to evaluate human attack surface?
- A) Amass
- B) securiCAD
- C) SET
- D) Skybox
**Answer: B**

**E05.** Which firewall can a network administrator use for better bandwidth management, deep packet inspection, and Hateful inspection?
- A) Next generation firewall
- B) Circuit-level gateway firewall
- C) Network address translation
- D) Stateful muIti-layer inspection firewall
**Answer: A**

**E06.** Which of the following is a database encryption feature that secures sensitive data by encrypting it in client applications without revealing the encrypted keys to the data engine in MS SQL Server?
- A) IsEncrypted Enabled
- B) Allow Encrypted
- C) Always Encrypted
- D) NeverEncrypted disabled
**Answer: C**

**E07.** Which of the following is a tool that runs on the Windows OS and analyzes iptables log messages to detect port scans and other suspicious traffic?
- A) Nmap
- B) Hping
- C) NetRanger
- D) PSAD
**Answer: D**

**E08.** Which of the following refers to the data that is stored or processed by RAM, CPUs, or databases?
- A) Data in Use
- B) Data at Rest
- C) Data in Transit
- D) Data in Backup
**Answer: A**

**E09.** Which risk management phase helps in establishing context and quantifying risks?
- A) Risk treatment
- B) Risk Identification
- C) Risk assessment
- D) Risk review
**Answer: C**

**E10.** An IDS or IDPS can be deployed in two modes. Which deployment mode allows the IDS to both detect and stop malicious traffic?
- A) promiscuous mode
- B) passive mode
- C) firewall mode
- D) inline mode
**Answer: D**

---

## CertificationPractice — 20 items (312-38, no answer key published)

**C01.** A security architect designs a perimeter defense that requires the firewall to act as an intermediary, terminating the client connection so it can inspect the application payload before forwarding it over a separate connection to the destination. Which firewall technology implements this architecture?
- Circuit-level gateway
- Packet filtering firewall
- Application-level gateway
- Stateful inspection firewall

**C02.** Which deployment topology allows a Web Application Firewall (WAF) to inspect traffic by sitting directly in the path of the connection, terminating the session from the client, and initiating a new separate connection to the web server?
- Port Mirroring
- Transparent Bridge
- Reverse Proxy
- Out-of-band monitoring

**C03.** The board of directors establishes a requirement that in the event of a ransomware attack, the organization must not lose more than four hours of transactional data. Which metric represents this constraint?
- Recovery Time Objective (RTO)
- Work Recovery Time (WRT)
- Maximum Tolerable Downtime (MTD)
- Recovery Point Objective (RPO)

**C04.** A network administrator discovers that internal users are bypassing port-based blocking rules by tunneling Peer-to-Peer (P2P) file-sharing traffic over port 443. Which firewall technology should be deployed to identify and block this traffic based on the application signature within the payload?
- Next-Generation Firewall (NGFW)
- Circuit-Level Gateway
- Packet Filtering Firewall
- Stateful Inspection Firewall

**C05.** Executive management is deciding on the budget allocation for cybersecurity insurance and requires an assessment of high-level trends regarding the financial motives of global threat actors and the potential impact on business continuity. Which type of threat intelligence provides this non-technical, long-term context?
- Operational Threat Intelligence
- Tactical Threat Intelligence
- Technical Threat Intelligence
- Strategic Threat Intelligence

**C06.** An administrator wants to prevent brute-force attacks against the root account on a Linux server by disabling direct root login over SSH. Which directive in the `/etc/ssh/sshd_config` file should be modified to achieve this?
- `RestrictUser root`
- `ProtocolAuthentication 2`
- `AllowRootAccess false`
- `PermitRootLogin no`

**C07.** A financial institution determines that the cost of implementing a redundant data center to mitigate the risk of a regional outage significantly exceeds the potential financial loss from such an event. Consequently, the board formally documents the decision to operate without the redundancy and absorb the potential cost if an outage occurs. Which risk management strategy has the organization adopted?
- Risk Acceptance
- Risk Transference
- Risk Avoidance
- Risk Mitigation

**C08.** A network administrator arrives at a workstation that is suspected of being controlled by a remote attacker. To ensure the preservation of volatile evidence, which action should be avoided immediately?
- Photographing the screen
- Disconnecting the network cable
- Restarting the system
- Documenting the current state

**C09.** While monitoring network traffic, an administrator observes a large volume of data being transferred to a suspicious external IP address from a critical finance server. To halt the exfiltration while retaining the ability to analyze the contents of the system's RAM, which action should be taken immediately?
- Disconnect the network cable
- Perform a normal system shutdown
- Unplug the server's power cord
- Reboot the server into safe mode

**C10.** During the deployment of full disk encryption on corporate laptops, the security team mandates that the decryption keys must only be released if the boot sequence remains unmodified. Which component facilitates this integrity check?
- Hardware Security Module (HSM)
- Self-Encrypting Drive (SED)
- Trusted Platform Module (TPM)
- Unified Extensible Firmware Interface (UEFI)

**C11.** Organizations often define the maximum acceptable amount of data loss measured in time, such as losing no more than four hours of work. Which metric is used to specify this data tolerance limit?
- Recovery Time Objective (RTO)
- Mean Time to Repair (MTTR)
- Maximum Tolerable Downtime (MTD)
- Recovery Point Objective (RPO)

**C12.** An organization deploys Opportunistic Wireless Encryption (OWE) on its guest wireless network to protect against passive eavesdropping without requiring users to enter credentials. Because OWE does not use a pre-shared password or 802.1X authentication, which mechanism does it use to generate the Pairwise Master Key (PMK) used to derive traffic-encryption keys?
- An unauthenticated Diffie-Hellman key exchange using public keys carried in the 802.11 Association Request and Response frames.
- An anonymous EAP-TLS tunnel established prior to the 4-Way Handshake.
- A Simultaneous Authentication of Equals (SAE) handshake using a null or blank password string.
- A well-known, public Pre-Shared Key (PSK) that is rotated automatically by the controller.

**C13.** A security specialist maps all potential entry points and exposed services to quantify an organization's total exposure across its digital footprint. What is this process called?
- Risk Assessment
- Incident Response Planning
- Attack Surface Analysis
- Threat Modeling

**C14.** A Chief Information Security Officer (CISO) is hesitant to authorize full remote wipes for employee-owned devices suspected of being compromised. What is the primary legal and ethical challenge driving this hesitation in a Bring Your Own Device (BYOD) environment?
- The high cost of licensing required to issue wipe commands to non-corporate devices
- The inability of remote wipe protocols to function over cellular networks
- Liability concerns regarding the permanent deletion of the employee's personal data
- Technical incompatibility between the MDM solution and consumer-grade operating systems

**C15.** The Chief Information Security Officer (CISO) of a retail chain declines to host their own e-commerce payment gateway and instead contracts a PCI DSS-compliant payment service provider to handle all credit card transactions. Which risk management strategy does this decision best illustrate?
- Risk Avoidance
- Risk Acceptance
- Risk Mitigation
- Risk Transfer

**C16.** A multinational corporation is implementing a Single Sign-On (SSO) solution to allow employees to access third-party SaaS applications using their internal Active Directory credentials. Which XML-based standard is primarily used to exchange authentication and authorization data between the Identity Provider (IdP) and the Service Provider (SP) in this scenario?
- RADIUS
- SAML
- LDAP
- TACACS+

**C17.** After failed authentication attempts, locked-out accounts currently remain locked indefinitely, requiring a manual administrator reset. Which policy setting enables automatic unlocking after a defined timeframe?
- Enforce password history
- Account lockout duration
- Reset account lockout counter after
- Account lockout threshold

**C18.** A network architect designs a perimeter defense that places web and email servers in a network segment isolated between an external packet-filtering router and an internal firewall. This configuration ensures that a compromise of the public servers does not provide direct access to the internal LAN. What is this topology called?
- Dual-homed gateway
- Bastion host
- Screened host
- Screened subnet

**C19.** A security analyst is calculating a CVSS v3.x score for a vulnerability found on a legacy server that is physically air-gapped and isolated from the rest of the network. To calculate an environment-specific severity score that reflects this deployment context, which CVSS metric group must be adjusted?
- Environmental Metrics
- Temporal Metrics
- Impact Metrics
- Base Metrics

**C20.** In an industrial setting, sensors collect temperature data and transmit it to a local edge node for aggregation and protocol translation before the data is finally sent to the cloud service. Which IoT communication model is primarily being utilized in this architecture?
- Back-End Data-Sharing
- Device-to-Gateway
- Device-to-Device
- Device-to-Cloud

---

## Daypo "CND 2" — 12 items (CND **v2**, 2022, no answer key)

> [!caution] Legacy version
> This set predates v3. Terminology may not match current courseware. Use as weak-signal only.

**D01.** Management decides to implement a risk management system to reduce and maintain the organization's risk at an acceptable level. Which of the following is the correct order in the risk management phase?
- Risk Identification, Risk Assessment, Risk Treatment, Risk Monitoring & Review
- Risk Treatment, Risk Monitoring & Review, Risk Identification, Risk Assessment
- Risk Assessment, Risk Treatment, Risk Monitoring & Review, Risk Identification
- Risk Identification, Risk Assessment, Risk Monitoring & Review, Risk Treatment

**D02.** John has implemented \_\_\_\_\_\_\_\_ in the network to restrict the limit of public IP addresses in his organization and to enhance the firewall filtering technique.
- DMZ
- Proxies
- VPN
- NAT

**D03.** What command is used to terminate certain processes in an Ubuntu system?
- `#grep Kill [Target Process]`
- `#kill-9[PID]`
- `#ps ax Kill`
- `# netstat Kill [Target Process]`

**D04.** Consider a scenario consisting of a tree network. The root Node N is connected to two main nodes N1 and N2. N1 is connected to N11 and N12. N2 is connected to N21 and N22. What will happen if any one of the main nodes fail?
- Failure of the main node affects all other child nodes at the same level irrespective of the main node.
- Does not cause any disturbance to the child nodes or its transmission.
- Failure of the main node will affect all related child nodes connected to the main node.
- Affects the root node only.

**D05.** Stephanie is currently setting up email security so all company data is secured when passed through email. Stephanie first sets up encryption to make sure that a specific user's email is protected. Next, she needs to ensure that the incoming and the outgoing mail has not been modified or altered using digital signatures. What is Stephanie working on?
- Confidentiality
- Availability
- Data Integrity
- Usability

**D06.** Phishing-like attempts that present users a fake usage bill of the cloud provider is an example of a
- Cloud to service attack surface
- User to service attack surface
- User to cloud attack surface
- Cloud to user attack surface

**D07.** Disaster Recovery is a \_\_\_\_\_\_\_\_\_.
- Operation-centric strategy
- Security-centric strategy
- Data-centric strategy
- Business-centric strategy

**D08.** The CEO of Max Rager wants to send a confidential message regarding the new formula for its coveted soft drink, SuperMax, to its manufacturer in Texas. However, he fears the message could be altered in transit. How can he prevent this incident from happening and what element of the message ensures the success of this method?
- Hashing; hash code
- Symmetric encryption; secret key
- Hashing; public key
- Asymmetric encryption; public key

**D09.** Which BC/DR activity includes action taken toward resuming all services that are dependent on business-critical applications?
- Response
- Recovery
- Resumption
- Restoration

**D10.** Which subdirectory in `/var/log` directory stores information related to Apache web server?
- `/var/log/maillog`
- `/var/log/httpd`
- `/var/log/apachelog`
- `/var/log/lighttpd`

**D11.** John is a senior network security administrator working at a multinational company. He wants to block specific syscalls from being used by container binaries. Which Linux kernel feature restricts actions within the container?
- Cgroups
- LSMs
- Seccomp
- Userns

**D12.** Which of the following things need to be identified during attack surface visualization?
- Attacker's tools, techniques, and procedures
- Authentication, authorization, and auditing in networks
- Regulatory frameworks, standards, and procedures for organizations
- Assets, topologies, and policies of the organization

---

## PracticeTestGeeks PDF — 4 items (generic, all answers **B**)

> [!caution] Low signal
> Generic wording, not CND-specific. Published answers are `1-B 2-B 3-B 4-B`.

**P01.** Which tool is most effective for detecting network intrusions in real-time?
- A) Packet sniffer only
- B) Intrusion Detection System (IDS) with behavioral analysis
- C) Basic firewall logs
- D) Manual network monitoring
**Answer: B**

**P02.** What is the primary difference between a signature-based and anomaly-based detection system?
- A) Cost and implementation complexity
- B) Signature-based detects known threats, anomaly-based detects unusual behavior patterns
- C) Hardware requirements
- D) Network speed compatibility
**Answer: B**

**P03.** Which technique is most effective for preventing DDoS attacks?
- A) Installing antivirus software only
- B) Rate limiting, traffic filtering, and distributed mitigation services
- C) Changing network passwords frequently
- D) Using only wireless connections
**Answer: B**

**P04.** What should be the first step when responding to a confirmed network security incident?
- A) Immediately shut down all systems
- B) Contain the threat while preserving evidence and maintaining business operations
- C) Delete all suspicious files
- D) Change all user passwords
**Answer: B**

---

## A Guide to Cloud — exam facts (not PDF-sourced)

> [!danger] Third-party weights — do NOT promote to blueprint
> These domain percentages come from a third-party vendor page, **not** the EC-Council courseware. `AGENTS.md` requires exam weights to be traceable to source. Keep out of [[00-Home]] progress tables until independently confirmed.

| Detail | Value |
|--------|-------|
| Exam Code | CND-V3 |
| Duration | 240 minutes |
| Questions | 100 |
| Pass Score | 70% |
| Cost | $450 USD |
| Provider | Pearson VUE / ECC Exam |
| Validity | 3 years (ECE required) |
| Question Types | Multiple choice |

Vendor-claimed domain weights:

| Domain | Weight |
|--------|--------|
| Network Defense Fundamentals & Strategies | 14% |
| Network Perimeter Security | 18% |
| Endpoint Security — Windows, Linux, Mobile, IoT | 20% |
| Application & Data Security | 14% |
| Enterprise Virtual, Cloud & Wireless Security | 14% |
| Incident Detection, Response & Threat Intelligence | 20% |

Practice questions on that site are paywalled ($9, 20 free without account). Not retrieved.
