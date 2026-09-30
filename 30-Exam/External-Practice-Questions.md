---
type: exam
module: "ext"
tags: [exam]
topic: "External Practice Questions — third-party harvested, PDF-derived answers"
exam_weight: unknown
status: draft
unresolved:
  - "AguidetoCloud CND-V3 domain weights (14/18/20/14/14/20%) are third-party and CONTRADICT the official blueprint v4.0. Rejected. See [[Exam-Facts]]."
  - "AguidetoCloud 'Pass Score 70%' is third-party and WRONG. Handbook p65 sec 1.6: passing criteria 'may vary from exam to exam'; EC-Council states 60-85% by form."
  - "OpenExamPrep 200 items retrieved in full but NOT imported: answer key is A39/B58.5/C2.5/D0 and the correct option is the longest 78% of the time. See the section below."
  - "Quizlet set 617277655 returned HTTP 403 (anti-bot). Not retrieved. No bypass attempted."
  - "32 items originally had no published answer key. 23 now answered from the module PDFs. 9 remain unanswerable — see 'Not answerable from the PDFs'."
  - "C02 reverse-proxy WAF topology: mod09 WAF section lists hardware/network, software, host-based and layer-2 bridge. No reverse proxy. Unanswerable."
  - "C12 OWE / Pairwise Master Key: 'OWE' and 'Opportunistic Wireless Encryption' appear in NONE of the 20 modules. Unanswerable."
  - "C14 BYOD remote-wipe legal/ethical challenge: mod02:219 design considerations cover allowed devices, resources, disabled features, data storage. No liability/privacy statement about remote wipe. Unanswerable."
  - "C17 account lockout duration / 'Reset account lockout counter after': mod05 password policy covers complexity, age and length only. No lockout-duration setting named. Unanswerable."
  - "C19 CVSS metric groups: 'CVSS Score' appears only as a column header (mod06:27). No Base/Temporal/Environmental metric groups described. Unanswerable."
  - "D03 'kill -9[PID]': no process-termination command appears anywhere in the 20 modules. Unanswerable."
  - "D04 tree topology failure behaviour: 'Tree Topology' does not appear in the corpus. Unanswerable."
  - "D07 DR as 'business-centric strategy': 'business-centric' does not appear. mod17 defines BC/DR but never uses the term. Unanswerable."
  - "D10 Apache log subdirectory: PDF mod15:327 gives /var/log/apache2/access.log (Debian/Ubuntu). NO option matches — /var/log/httpd is the RHEL convention and is not in the PDF. Option/term mismatch. Unanswerable."
---
# External Practice Questions — third-party

> [!warning] Provenance
> These items come from **public third-party sites**, not from the 20 module PDFs.
> Per `AGENTS.md` ("never invent facts not in the PDFs") they are kept **out** of [[Question-Bank]] and [[Answer-Key]].
> Use them to cross-check the PDF-derived bank and to spot weak spots.
> Verbatim as published — typos preserved (`Hateful inspection`, `muIti-layer`).

> [!info] Answer provenance
> 14 answers are **published by the source site**. 23 are **derived here from the 20 module PDFs**
> and carry a `> Derived from courseware` citation. 9 have **no defensible answer from the PDFs**
> and are listed in [[#Not answerable from the PDFs]] instead of being guessed.

## Harvest summary

| Source | Items | Answers given | Version | URL |
|--------|-------|---------------|---------|-----|
| Edusum | 10 | Yes (bare key) | 312-38 | https://www.edusum.com/ec-council/ec-council-cnd-312-38-certification-sample-questions |
| CertificationPractice | 20 | No | 312-38 | https://certificationpractice.com/practice-exams/ec-council-certified-network-defender-cnd |
| Daypo "CND 2" | 12 | No | CND v2 (2022) | https://www.daypo.com/cnd-2.html |
| PracticeTestGeeks PDF | 4 | Yes (all B) | generic | https://practicetestgeeks.com/pdf/Certified_Network_Defender_Practice_Test_Questions_and_Answers.pdf |
| A Guide to Cloud | 0 | — | CND v3 | paywalled — exam facts only, see [[#A Guide to Cloud — exam facts (third-party, partly wrong)]] |
| Quizlet | 0 | — | — | HTTP 403 anti-bot, not retrieved |
| OpenExamPrep | **200** | Yes (index + explanation) | CND v3 | `open-exam-prep.com/data/question-bank/cnd.json` — **rejected, see below** |

---

## OpenExamPrep — 200 questions, retrieved but REJECTED for drilling

> [!danger] Do not drill these. The answer key is positionally broken.
> Retrieved in full (JSON, 200 items, 4 options each, correct answer + explanation, no
> registration). The questions are *well-formed and the answers are defensible*, but the
> **key distribution is unusable**, so practising on it teaches two wrong heuristics.

| Position | Correct | Expected on a real 4-option exam |
|----------|---------|-----------------------------------|
| A | 78 (39.0%) | ~50 (25%) |
| B | **117 (58.5%)** | ~50 |
| C | 5 (2.5%) | ~50 |
| D | **0 (0.0%)** | ~50 |

**Not one of the 200 has D as the correct answer.** Two exploitable artefacts:

| Heuristic | Score on this set | Score on a real exam |
|-----------|-------------------|----------------------|
| Always pick the **longest** option | 157/200 = **78%** | ~25% |
| Always pick **B** | 117/200 = **58%** | ~25% |
| Pick **B**, else the longest | 174/200 = **87%** | ~25% |

The correct answer is the longest option **78%** of the time (chance = 25%) and the shortest only
**5%**. The generator writes qualified, multi-clause answers and short confident distractors.

> [!warning] Their own disclaimer
> "our practice questions are **independently developed simulations, not actual, recalled, or
> sponsor-provided exam items**." That is consistent with the handbook's item-confidentiality
> clause — see [[Exam-Facts]]. No site can legitimately hold real 312-38 items.

**Kept for one reason only:** its 200 items are distributed across the 8 blueprint domains in
exactly the published proportions (10/10/20/10/15/10/10/15), which independently corroborated the
official weights now recorded in [[Exam-Facts]]. That is now confirmed against the official PDF,
so this source adds nothing further and **its items are not imported into the vault.**

Other notes: all 200 are stamped `lastUpdated: 2026-03-10`; difficulty split 60 easy / 100 medium /
40 hard; 19 topics. Data path was found in the site's JS bundle
(`/data/question-bank/{exam}.json`), not linked from the page HTML.

**Total harvested: 46 questions.**
**Answers: 14 published · 23 PDF-derived · 9 not answerable from the PDFs.**

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

**Answer: Application-level gateway**
> Derived from courseware — Mod 04 pp17-20 — "Application level gateways can filter packets at the application layer of the OSI model"; "An application-level proxy works as a proxy server and filters connections for specific services"

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

**Answer: Recovery Point Objective (RPO)**
> Derived from courseware — Mod 17 p14 — "Recovery point objective (RPO) is the maximum time frame for which an organization loses data after a major IT outage"

**C04.** A network administrator discovers that internal users are bypassing port-based blocking rules by tunneling Peer-to-Peer (P2P) file-sharing traffic over port 443. Which firewall technology should be deployed to identify and block this traffic based on the application signature within the payload?
- Next-Generation Firewall (NGFW)
- Circuit-Level Gateway
- Packet Filtering Firewall
- Stateful Inspection Firewall

**Answer: Next-Generation Firewall (NGFW)**
> Derived from courseware — Mod 04 pp26-27 — "Next generation firewall (NGFW) ... moves beyond port/protocol inspection"; "Multilayered protection: It provides multilayered protection by inspecting traffic from layers 2–7"

**C05.** Executive management is deciding on the budget allocation for cybersecurity insurance and requires an assessment of high-level trends regarding the financial motives of global threat actors and the potential impact on business continuity. Which type of threat intelligence provides this non-technical, long-term context?
- Operational Threat Intelligence
- Tactical Threat Intelligence
- Technical Threat Intelligence
- Strategic Threat Intelligence

**Answer: Strategic Threat Intelligence**
> Derived from courseware — Mod 20 p10 — "Strategic threat intelligence provides high-level information regarding the cyber security posture, threats, and their impact on the business ... consumed by high-level executives"

**C06.** An administrator wants to prevent brute-force attacks against the root account on a Linux server by disabling direct root login over SSH. Which directive in the `/etc/ssh/sshd_config` file should be modified to achieve this?
- `RestrictUser root`
- `ProtocolAuthentication 2`
- `AllowRootAccess false`
- `PermitRootLogin no`

**Answer: `PermitRootLogin no`**
> Derived from courseware — Mod 06 p107 — "Search for the line in the file - #PermitRootLogin no / Remove the '#' from the beginning of the line. PermitRootLogin no"

**C07.** A financial institution determines that the cost of implementing a redundant data center to mitigate the risk of a regional outage significantly exceeds the potential financial loss from such an event. Consequently, the board formally documents the decision to operate without the redundancy and absorb the potential cost if an outage occurs. Which risk management strategy has the organization adopted?
- Risk Acceptance
- Risk Transference
- Risk Avoidance
- Risk Mitigation

**Answer: Risk Acceptance**
> Derived from courseware — Mod 18 p21 — "Risks are accepted when the effort to address, transfer, or mitigate has exceeded the impact of the risk on the network"

**C08.** A network administrator arrives at a workstation that is suspected of being controlled by a remote attacker. To ensure the preservation of volatile evidence, which action should be avoided immediately?
- Photographing the screen
- Disconnecting the network cable
- Restarting the system
- Documenting the current state

**Answer: Restarting the system**
> Derived from courseware — Mod 16 p26 — "Do not change the state of suspected device ... If the suspected device is ON, then leave it ON ... Changing the state may destroy" (evidence). Restart is the only option that changes state and destroys volatile evidence.

**C09.** While monitoring network traffic, an administrator observes a large volume of data being transferred to a suspicious external IP address from a critical finance server. To halt the exfiltration while retaining the ability to analyze the contents of the system's RAM, which action should be taken immediately?
- Disconnect the network cable
- Perform a normal system shutdown
- Unplug the server's power cord
- Reboot the server into safe mode

**Answer: Disconnect the network cable**
> Derived from courseware — Mod 16 pp15-26 — "Do not change the state of suspected device" + "Do not perform actions that will damage the integrity of the evidence". Pulling the cable halts exfiltration without powering down, so RAM survives. Shutdown / power-off / safe-mode all destroy it.

**C10.** During the deployment of full disk encryption on corporate laptops, the security team mandates that the decryption keys must only be released if the boot sequence remains unmodified. Which component facilitates this integrity check?
- Hardware Security Module (HSM)
- Self-Encrypting Drive (SED)
- Trusted Platform Module (TPM)
- Unified Extensible Firmware Interface (UEFI)

**Answer: Trusted Platform Module (TPM)**
> Derived from courseware — Mod 05 p153 — "TPM in conjunction with Secure Boot ensures the integrity of the boot process. BitLocker, Windows' native encryption feature, leverages TPM to safeguard the system drive."

**C11.** Organizations often define the maximum acceptable amount of data loss measured in time, such as losing no more than four hours of work. Which metric is used to specify this data tolerance limit?
- Recovery Time Objective (RTO)
- Mean Time to Repair (MTTR)
- Maximum Tolerable Downtime (MTD)
- Recovery Point Objective (RPO)

**Answer: Recovery Point Objective (RPO)**
> Derived from courseware — Mod 17 p14 — "Recovery point objective (RPO) is the maximum time frame for which an organization loses data after a major IT outage"

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

**Answer: Attack Surface Analysis**
> Derived from courseware — Mod 19 p5 — "The attack surface is the sum of all possible security exposures ... through which attackers can gain access"

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

**Answer: Risk Transfer**
> Derived from courseware — Mod 18 p21 — "Transferring the risk treatment responsibility to another party or organization". PCI DSS context: Mod 12 p45

**C16.** A multinational corporation is implementing a Single Sign-On (SSO) solution to allow employees to access third-party SaaS applications using their internal Active Directory credentials. Which XML-based standard is primarily used to exchange authentication and authorization data between the Identity Provider (IdP) and the Service Provider (SP) in this scenario?
- RADIUS
- SAML
- LDAP
- TACACS+

**Answer: SAML**
> Derived from courseware — Mod 12 pp92-94 — "Use SAML Session Tags for Attribute-based Access Control"; "Create and configure the SAML role". SSO: Mod 03 p55 SAML is the only XML-based IdP↔SP option.

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

**Answer: Screened subnet**
> Derived from courseware — Mod 04 p32 — "The screened subnet architecture consists of two screening routers: one is placed between the perimeter net and the internal network and the other is placed between the perimeter net and the external network ... If the firewall is compromised, access to the intranet will not be possible."

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

**Answer: Device-to-Gateway**
> Derived from courseware — Mod 08 pp15-16 — — IoT Communication Models: "Device-to-Gateway Model"; "Gateways help manage traffic between IoT devices and connected networks". Contrast Device-To-Cloud (Mod 08) where the device talks to the cloud directly.

---

## Daypo "CND 2" — 12 items (CND **v2**, 2022, no answer key)

> [!caution] Legacy version
> This set predates v3. Terminology may not match current courseware. Use as weak-signal only.

**D01.** Management decides to implement a risk management system to reduce and maintain the organization's risk at an acceptable level. Which of the following is the correct order in the risk management phase?
- Risk Identification, Risk Assessment, Risk Treatment, Risk Monitoring & Review
- Risk Treatment, Risk Monitoring & Review, Risk Identification, Risk Assessment
- Risk Assessment, Risk Treatment, Risk Monitoring & Review, Risk Identification
- Risk Identification, Risk Assessment, Risk Monitoring & Review, Risk Treatment

**Answer: Risk Identification, Risk Assessment, Risk Treatment, Risk Monitoring & Review**
> Derived from courseware — Mod 18 pp13-24 — — phases in order: "Risk Management Phase: Risk Identification" → "Risk Assessment" → "Risk Treatment" → "Risk Tracking & Review"

**D02.** John has implemented \_\_\_\_\_\_\_\_ in the network to restrict the limit of public IP addresses in his organization and to enhance the firewall filtering technique.
- DMZ
- Proxies
- VPN
- NAT

**Answer: NAT**
> Derived from courseware — Mod 04 p8 — — Firewall Capabilities list: "Performs network address Translation (NAT)"

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

**Answer: Data Integrity**
> Derived from courseware — Mod 03 p77 — "Digital signatures use the asymmetric key algorithms to provide data integrity"

**D06.** Phishing-like attempts that present users a fake usage bill of the cloud provider is an example of a
- Cloud to service attack surface
- User to service attack surface
- User to cloud attack surface
- Cloud to user attack surface

**Answer: Cloud to user attack surface**
> Derived from courseware — Mod 19 p50 — Cloud Attack Surface table includes "Cloud to User — Cloud interface exposed to User"

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

**Answer: Asymmetric encryption; public key**
> Derived from courseware — Mod 03 pp75-78 — "asymmetric encryption uses two separate keys ... the public key is used for encrypting messages"; "With the help of the public key and the new result, the verifier checks whether the digital signature was created with the related private key". Hashing only DETECTS tampering (Mod 03), it does not prevent it.

**D09.** Which BC/DR activity includes action taken toward resuming all services that are dependent on business-critical applications?
- Response
- Recovery
- Resumption
- Restoration

**Answer: Resumption**
> Derived from courseware — Mod 17 p15 — "The objective of this section is to discuss the prevention, response, resumption, recovery, and restoration activities". Restoration (Mod 17) is repair of the primary site, only for physical damage.

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

**Answer: Seccomp**
> Derived from courseware — Mod 11 p120 — — Docker Security Features: "Fine grained per-syscall control (via seccomp)"; "Default profile limits many syscalls"

**D12.** Which of the following things need to be identified during attack surface visualization?
- Attacker's tools, techniques, and procedures
- Authentication, authorization, and auditing in networks
- Regulatory frameworks, standards, and procedures for organizations
- Assets, topologies, and policies of the organization

**Answer: Assets, topologies, and policies of the organization**
> Derived from courseware — Mod 19 p11 — — Attack Surface Visualization: "Identify the assets, topologies, and policies of the organization"

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

## Not answerable from the PDFs

> [!failure] No answer recorded — by design
> Per `AGENTS.md` ground rule 2, a missing/ambiguous topic goes to `unresolved:`, **never a guess**.
> Each item keeps its original options in place. The gap is recorded, not filled.

| ID | Asked | Why the PDFs can't answer it | Closest courseware content |
|----|-------|------------------------------|------------------------------|
| C02 | WAF topology that terminates the client session and opens a new one to the server | `reverse proxy` appears in **none** of the 20 modules | Mod 09 WAF: hardware/network-based, software, host-based, and **Layer-2 bridge** in-line mode |
| C12 | How OWE derives the PMK without a PSK or 802.1X | `OWE` / `Opportunistic Wireless Encryption` appear in **none** of the 20 modules | Mod 13: "the only way to crack WPA is to sniff the password pairwise master key (PMK)"; encryption order WPA3 > WPA2-Enterprise+RADIUS > … |
| C14 | Legal/ethical obstacle to remote-wiping personal BYOD devices | No liability/privacy statement about remote wipe | Mod 02:219 BYOD design considerations (allowed devices, resources, features to disable, data storage); Mod 07:96 "Securely wipe or delete the data while disposing of devices" |
| C17 | Policy setting for automatic unlock after a defined timeframe | No lockout-**duration** setting is named | Mod 05 password policy covers complexity, age, length only; Mod 08:339 "Use the 'Lock Out' feature to lock out accounts in the case of excessive invalid login attempts" |
| C19 | CVSS metric group for environment-specific severity | Only a `CVSS Score` column header exists; no metric groups described | Mod 06:27 CVE search view exposes `CVSS Scores` and `EPSS scores` as filter columns only |
| D03 | Command to terminate a process in Ubuntu | No process-termination command anywhere in the corpus | Mod 06: "Disabling Unnecessary Services" covers service removal, not `kill` |
| D04 | Effect of a main-node failure in a tree topology | `Tree Topology` does not appear in the corpus | Mod 06:24 "Hierarchical File System — arranges directories and files in a tree like structure" (filesystem, not network) |
| D07 | Disaster Recovery as a "business-centric" strategy | `business-centric` does not appear | Mod 17: "BC ... ensure the continuity of an organization's critical business functions"; "DR refers to an organization's ability to restore the data and applications critical to an organization's operations" |
| D10 | Which `/var/log` subdirectory holds Apache logs | **No option matches the PDF.** The courseware says `/var/log/apache2/access.log`; `/var/log/httpd` is the RHEL/CentOS path and is not in the courseware | Mod 15: `sudo tail -100 /var/log/apache2/access.log` (Debian/Ubuntu) |

---

## A Guide to Cloud — exam facts (third-party, partly wrong)

> [!danger] Superseded by official source
> These claims come from a **third-party vendor page**, not EC-Council.
> The official facts now live in [[Exam-Facts]]. **Do not use this section for anything.**

| Detail | Third-party claim | Official (EC-Council) |
|--------|-------------------|----------------------|
| Exam Code | CND-V3 | 312-38 |
| Duration | 240 minutes | 4 hours - agrees |
| Questions | 100 | 100 - agrees |
| Pass Score | **70%** | **WRONG** - cut score varies **60%-85%** by exam form |
| Question Types | Multiple choice | Multiple Choice - agrees |
| Cost | $450 USD | not sourced here |
| Provider | Pearson VUE / ECC Exam | EC-Council Exam Portal / Pearson VUE (Mod 01 p13) |
| Validity | 3 years (ECE required) | not sourced here |

Vendor-claimed domain weights - **rejected**, they contradict the official blueprint:

| Domain (vendor wording) | Vendor weight | Official blueprint v4.0 |
|-------------------------|---------------|------------------------|
| Network Defense Fundamentals & Strategies | 14% | Network Defense Management 10% |
| Network Perimeter Security | 18% | Network Perimeter Protection 10% |
| Endpoint Security - Windows, Linux, Mobile, IoT | 20% | Endpoint Protection 20% |
| Application & Data Security | 14% | Application and Data Protection 10% |
| Enterprise Virtual, Cloud & Wireless Security | 14% | Enterprise Virtual, Cloud, and Wireless Network Protection 15% |
| Incident Detection, Response & Threat Intelligence | 20% | Incident Detection 10% |

Only the 6-domain grouping shape is similar; **every weight differs**. Use [[Exam-Facts]].

Practice questions on that site are paywalled ($9, 20 free without account). Not retrieved.
