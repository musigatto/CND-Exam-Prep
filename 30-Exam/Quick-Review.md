---
type: exam
module: "bank"
tags: [exam]
topic: "Quick Review - all modules, numbered callouts"
exam_weight: unknown
status: draft
unresolved:
  - "Modules 13-20 review items are NOT included yet (decision pending). Numbering below covers modules 01-12; new items will continue the sequence."
---

# Quick Review

> [!info] What this is
> Numbered review callouts collected from every atomic note (`## Quick review` sections, ex-SR cards). Front in the title, answer inside the folded callout. Source note linked at the bottom of each card.

## Modules 01-12

### Module 01 (38 items)

> [!question]- 0001 â€” Risk formula?
> Risk = Asset + Threat + Vulnerability
> Source: [[01-LO01-Essential-Terminologies]]

> [!question]- 0002 â€” Attack formula?
> Attack = Motive (Goal) + Method (TTPs) + Vulnerability
> Source: [[01-LO01-Essential-Terminologies]]

> [!question]- 0003 â€” Why are insider attacks more dangerous than external?
> Insiders know network architecture, security policies, and regulations; defenses typically focus on external attacks.
> Source: [[01-LO01-Essential-Terminologies]]

> [!question]- 0004 â€” Three classes of security vulnerabilities?
> Technological (protocol/OS/device), Configuration (accounts, misconfig, defaults), Security policy (unwritten, gaps, awareness).
> Source: [[01-LO01-Essential-Terminologies]]

> [!question]- 0005 â€” Two types of DoS and examples?
> Bandwidth (flood traffic) and Connectivity (exhaust resources); e.g. TCP SYN flood, UDP flood, ICMP Smurf flood, intermittent flooding.
> Source: [[01-LO02-Network-Level-Attacks]]

> [!question]- 0006 â€” How does a DHCP starvation attack work and two mitigations?
> Floods DHCP server with fake DHCP requests (Gobbler) to exhaust the IP pool â†’ DoS. Mitigate with port security and DHCP snooping.
> Source: [[01-LO02-Network-Level-Attacks]]

> [!question]- 0007 â€” Vertical vs horizontal privilege escalation?
> Vertical = same account â†’ higher-privilege account; Horizontal = one user account â†’ another with equal privileges.
> Source: [[01-LO02-Network-Level-Attacks]]

> [!question]- 0008 â€” Why is ARP easy to poison?
> ARP provides no authenticity verification; hosts even accept unsolicited ARP replies.
> Source: [[01-LO02-Network-Level-Attacks]]

> [!question]- 0009 â€” XSS definition?
> Injection of client-side script into dynamic web pages viewed by other users, that executes in the victim's browser.
> Source: [[01-LO03-Application-Level-Attacks]]

> [!question]- 0010 â€” Requirement for a CSRF attack?
> Three things: a user, a trusted website, and a malicious website.
> Source: [[01-LO03-Application-Level-Attacks]]

> [!question]- 0011 â€” Which cookie attribute prevents XSS-based session hijacking?
> HttpOnly â€” if the server does not set HttpOnly on session cookies, client-side script injection can enable session hijacking.
> Source: [[01-LO03-Application-Level-Attacks]]

> [!question]- 0012 â€” Piggybacking vs tailgating?
> Piggybacking: an authorized person lets an unauthorized person pass a secure door. Tailgating: unauthorized person with fake badge follows an authorized person through a key-access door.
> Source: [[01-LO04-Social-Engineering-Attacks]]

> [!question]- 0013 â€” Two classes of social engineering attacks?
> Human-based (physical presence needed) and computer-based (remote credential extraction).
> Source: [[01-LO04-Social-Engineering-Attacks]]

> [!question]- 0014 â€” Types of malicious email redirects?
> Referrer-based, user-agent-based, cookie-based, and OS-based.
> Source: [[01-LO05-Email-Attacks]]

> [!question]- 0015 â€” Email bomb types?
> List linking, attachment, mass mailing, reply all, zip bomb.
> Source: [[01-LO05-Email-Attacks]]

> [!question]- 0016 â€” Difference between bluesnarfing and bluebugging?
> Bluesnarfing steals information via Bluetooth; bluebugging gains control over the device via Bluetooth.
> Source: [[01-LO06-Mobile-Device-Attacks]]

> [!question]- 0017 â€” How is Android rooting implemented?
> Exploiting firmware vulnerabilities and copying the su binary to a PATH location (e.g. /system/xbin/su) with executable permissions via chmod.
> Source: [[01-LO06-Mobile-Device-Attacks]]

> [!question]- 0018 â€” What is a wrapping attack?
> During SOAP message translation in the TLS layer, the attacker duplicates the body, modifies the original, and sends it as a legitimate user; the server authenticates the duplicated signature.
> Source: [[01-LO07-Cloud-Specific-Attacks]]

> [!question]- 0019 â€” What is a Man-in-the-Cloud attack?
> Advanced MITM exploiting cloud synchronization services (Google Drive, DropBox) via stolen sync tokens for data compromise, C&C, and exfiltration.
> Source: [[01-LO07-Cloud-Specific-Attacks]]

> [!question]- 0020 â€” Name five side-channel attack kinds.
> Timing attack, data remanence, acoustic cryptanalysis, power monitoring, differential fault analysis.
> Source: [[01-LO07-Cloud-Specific-Attacks]]

> [!question]- 0021 â€” Wardriving tools?
> KisMAC, NetStumbler, WaveStumbler.
> Source: [[01-LO08-Wireless-Network-Attacks]]

> [!question]- 0022 â€” What is an evil twin AP?
> A fraudulent access point that appears legitimate, used for MITM to intercept TCP sessions or SSL/SSH tunnels.
> Source: [[01-LO08-Wireless-Network-Attacks]]

> [!question]- 0023 â€” Two fragmentation attack forms?
> Ping of Death (oversized fragmented ICMP) and Tiny Fragment (small fragments leak TCP header, evade filtering).
> Source: [[01-LO08-Wireless-Network-Attacks]]

> [!question]- 0024 â€” ZTA operating components?
> Policy Engine (PE) decides permitted traffic, Policy Administrator (PA) communicates the decision, Policy Enforcement Point (PEP) blocks or permits requests.
> Source: [[01-LO09-Supply-Chain-Attacks]]

> [!question]- 0025 â€” Two methods for finding supply-chain vulnerabilities?
> Continuous (automated) vulnerability scanning and penetration testing with honeypots.
> Source: [[01-LO09-Supply-Chain-Attacks]]

> [!question]- 0026 â€” What is a honeytoken?
> A fake resource posing as private information that activates a signal when attackers interact with it, alerting the organization and detailing the breach technique.
> Source: [[01-LO09-Supply-Chain-Attacks]]

> [!question]- 0027 â€” CEH five hacking phases?
> Reconnaissance, Scanning, Gaining Access, Maintaining Access, Clearing Tracks.
> Source: [[01-LO10-Hacking-Methodologies-Frameworks]]

> [!question]- 0028 â€” Lockheed Martin Cyber Kill Chain phases?
> Reconnaissance, Weaponization, Delivery, Exploitation, Installation, Command and Control, Actions on Objectives.
> Source: [[01-LO10-Hacking-Methodologies-Frameworks]]

> [!question]- 0029 â€” MITRE ATT&CK Enterprise matrices and source of its 11 tactics?
> Enterprise, Mobile, and PRE-ATT&CK matrices; the 11 Enterprise tactics derive from the later Cyber Kill Chain stages (exploit, control, maintain, execute).
> Source: [[01-LO10-Hacking-Methodologies-Frameworks]]

> [!question]- 0030 â€” Five IA principles?
> Confidentiality, Integrity, Availability, Non-repudiation, Authentication.
> Source: [[01-LO11-Network-Defense-Goal-Benefits-Challenges]]

> [!question]- 0031 â€” Four network defense benefits?
> Increased profits, improved productivity, enhanced compliance, client confidence.
> Source: [[01-LO11-Network-Defense-Goal-Benefits-Challenges]]

> [!question]- 0032 â€” Four network security approaches?
> Preventive, Reactive, Retrospective, Proactive.
> Source: [[01-LO12a-Continual-Adaptive-Security-Strategy]]

> [!question]- 0033 â€” Four activities of adaptive security?
> Protect, Detect, Respond, Predict.
> Source: [[01-LO12a-Continual-Adaptive-Security-Strategy]]

> [!question]- 0034 â€” Which approach includes IDs/SIMS/TRS/IPS?
> Reactive approach (complements preventive for attacks it failed to avert).
> Source: [[01-LO12a-Continual-Adaptive-Security-Strategy]]

> [!question]- 0035 â€” Three categories of physical security controls with examples?
> Prevention (fences, locks, biometrics, mantraps), Deterrence (security guards, warning signs), Detection (CCTV, alarms).
> Source: [[01-LO12b-Security-Controls-Defense-Elements]]

> [!question]- 0036 â€” Major elements required for effective security strategy implementation?
> Technology, well-defined Operations, and skilled People (blue team).
> Source: [[01-LO12b-Security-Controls-Defense-Elements]]

> [!question]- 0037 â€” Seven defense-in-depth layers?
> Policies/procedures/awareness, Physical, Perimeter, Internal network, Host, Application, Data.
> Source: [[01-LO13-Defense-in-Depth-Strategy]]

> [!question]- 0038 â€” Why does defense-in-depth help after a breach?
> A break in one layer only exposes the next layer, giving defenders time to deploy new/updated countermeasures and limiting impact.
> Source: [[01-LO13-Defense-in-Depth-Strategy]]

### Module 02 (42 items)

> [!question]- 0039 â€” Order the security hierarchy from top to bottom?
> Regulatory Frameworks â†’ Policies â†’ Standards â†’ Procedures (SOP) â†’ Guidelines.
> Source: [[02-LO01-Regulatory-Frameworks-Compliance]]

> [!question]- 0040 â€” Standards vs guidelines Â· mandatory?
> Standards = specific low-level MANDATORY controls (e.g., password complexity, DES/AES/RSA). Guidelines = non-mandatory recommendations/best practices, reviewed more often.
> Source: [[02-LO01-Regulatory-Frameworks-Compliance]]

> [!question]- 0041 â€” Why is compliance not optional?
> Investment worth more than cost of risks: improved security, minimized losses, maintained trust, increased control.
> Source: [[02-LO01-Regulatory-Frameworks-Compliance]]

> [!question]- 0042 â€” What defines scope per HIPAA/SOX/FISMA/GLBA/PCI-DSS?
> HIPAA=healthcare data Â· SOX=US public companies & accounting Â· FISMA=federal agencies Â· GLBA=financial products/services Â· PCI-DSS=cardholder data.
> Source: [[02-LO01-Regulatory-Frameworks-Compliance]]

> [!question]- 0043 â€” Six high-level PCI-DSS requirements?
> Build/Maintain a Secure Network Â· Protect Cardholder Data Â· Maintain a Vulnerability Management Program Â· Implement Strong Access Control Measures Â· Regularly Monitor & Test Networks Â· Maintain an Information Security Policy.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0044 â€” HIPAA Administrative Simplification Rules?
> Electronic Transaction & Code Sets Â· Privacy Rule Â· Security Rule Â· National Provider Identifier (NPI, 10-digit intelligence-free) Â· Enforcement Rule.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0045 â€” GDPR controller vs processor?
> Controller = determines purposes/means of processing; Processor = processes data on behalf of the controller.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0046 â€” SOX Section 302 and Section 404?
> 302: senior mgmt certifies accuracy of financial statements. 404: management + auditors establish internal controls and report on their effectiveness.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0047 â€” GLBA penalty caps?
> Org â‰¤  $100,000 per violation; officers/directors personally liable â‰¤  $10,000 each; fines or imprisonment â‰¤  5 years.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0048 â€” ISO/IEC 27001 vs 27002?
> 27001 = formal ISMS specification; 27002 = information security controls catalogue.
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0049 â€” ISO/IEC 27018 and ISO/IEC 27400?
> 27018 = cloud privacy (PII by CSPs); 27400 = IoT security and privacy.
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0050 â€” DMCA Title II?
> Online Copyright Infringement Liability Limitation â€” 4 safe-harbor categories for service providers (transitory Â· caching Â· storage Â· location tools).
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0051 â€” FISMA core requirement?
> Each federal agency develops, documents, and implements an agency-wide information security program for its information/information systems.
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0052 â€” CFAA basis?
> 18 U.S.C. Â§ 1030 â€” intentionally accessing a protected computer without authorization / exceeding authorized access.
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0053 â€” Three goals of a security policy?
> (1) Reduce/eliminate legal liability; (2) protect confidential & proprietary information; (3) prevent computing resource waste.
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0054 â€” Four security requirement types?
> Discipline Â· Safeguard Â· Procedural Â· Assurance.
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0055 â€” EISP vs ISSP vs SSSP?
> EISP=enterprise scope/direction; ISSP=issue-specific (acceptable use, passwordâ€¦); SSSP=system-specific (DMZ, servers, cloud).
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0056 â€” Internet access policies â€” paranoid vs prudent?
> Paranoid forbids everything; Prudent blocks all by default then enables each safe/necessary service and logs everything.
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0057 â€” Step 3 & 4 of policy creation?
> 3 = include senior management/staff (policy without mgmt consent is illegal); 4 = set clear penalties and enforce them.
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0058 â€” Password example length & expiration (courseware)?
> 8â€“14 chars; max age 60 days; official guidance: change every 90 or 180 days.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0059 â€” Full vs incremental vs differential backup?
> Full=all data, slowest Â· Incremental=changes since last full, faster Â· Differential=selected files new/changed since last full.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0060 â€” Firewall policy â€” Telnet & FTP stance?
> No Telnet (insecure); FTP only for vendor error-log uploads; use proxy servers to avoid direct connections.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0061 â€” User access control practices?
> Prohibit unknown logins Â· monitor admin accounts Â· lock after failed attempts Â· remove unused accounts Â· strict access criteria Â· need-to-know + least privilege Â· disable unrequired features/ports.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0062 â€” Switch security â€” SSH vs Telnet, port security?
> SSH preferred over Telnet; port security limits MAC-based access.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0063 â€” Encryption key types + certs?
> Symmetric or asymmetric per org needs; verify certificate authenticity/provider; servers use trusted SSL/TLS certificates.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0064 â€” Training cadence for employees?
> On joining and periodically thereafter.
> Source: [[02-LO04-Security-Awareness-Training]]

> [!question]- 0065 â€” Two data classification top-level rules?
> Secret users access secretâ†’unclassified (NOT Top Secret); Top Secret users access all levels; unclassified = anyone, no permissions.
> Source: [[02-LO04-Security-Awareness-Training]]

> [!question]- 0066 â€” Social engineering techniques to train against?
> Tailgating/piggy-backing Â· password-change ruse Â· name-dropping Â· relaxing conversation Â· new-hire ruse.
> Source: [[02-LO04-Security-Awareness-Training]]

> [!question]- 0067 â€” Steps to implement awareness training?
> Buy-in from top â†’ gap analysis â†’ regular schedule â†’ performance review â†’ phishing simulations â†’ educate failures â†’ implement policy processes.
> Source: [[02-LO04-Security-Awareness-Training]]

> [!question]- 0068 â€” Leaving-process actions?
> Remove access rights + collect assets Â· remove org data from personal devices Â· change passwords Â· deactivate email & remote-access accounts Â· debriefing Â· remove biometric/badge codes.
> Source: [[02-LO05-Admin-Security-Measures]]

> [!question]- 0069 â€” Employee monitoring purpose?
> Detect policy-violation activity, measure & enhance productivity, and secure corporate resources (e.g., Spytech SpyAgent).
> Source: [[02-LO05-Admin-Security-Measures]]

> [!question]- 0070 â€” SpyAgent monitoring features (key)?
> Keystroke logging Â· screenshots Â· email/social/chat monitoring Â· webcam/mic recording Â· remote desktop viewing & control Â· clipboard logging Â· email/FTP log delivery.
> Source: [[02-LO05-Admin-Security-Measures]]

> [!question]- 0071 â€” Three ITAM data components?
> Financial, physical, contractual data.
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0072 â€” Six ITAM types?
> Physical/hardware, software, network, digital, mobile device, cloud asset management.
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0073 â€” ITAM process phases?
> Identification & Categorization â†’ Asset Tracking â†’ Asset Maintenance.
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0074 â€” Lansweeper discovery highlight?
> Network-wide asset discovery without installing agents/software on systems (works for IoT too).
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0075 â€” Asset categorization criteria?
> Type Â· usage Â· location Â· owner/department Â· lifecycle stage Â· vendor/manufacturer Â· criticality Â· license type.
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0076 â€” Six methods to stay up to date?
> News sources Â· conferences & webinars Â· communities/groups Â· reports & research Â· security competitions Â· network with professionals.
> Source: [[02-LO07-Security-Trends-and-Threats]]

> [!question]- 0077 â€” Most popular & up-to-date breaking news source (courseware)?
> thehackernews.com.
> Source: [[02-LO07-Security-Trends-and-Threats]]

> [!question]- 0078 â€” Key CERTs?
> US-CERT (US), CERT-EU (EU), CERT-In (India).
> Source: [[02-LO07-Security-Trends-and-Threats]]

> [!question]- 0079 â€” Oldest & largest cybersecurity conference?
> DEF CON (31 cited) â€” Las Vegas.
> Source: [[02-LO07-Security-Trends-and-Threats]]

> [!question]- 0080 â€” Competition example?
> National Cyber League (NCL) Games.
> Source: [[02-LO07-Security-Trends-and-Threats]]

### Module 03 (55 items)

> [!question]- 0081 â€” Access control terminologies?
> Subject = user/process accessing; Object = resource (file/device); Reference Monitor checks rules; Operation = action on object.
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0082 â€” Bell-LaPadula two properties?
> Simple security = no read-up; *-property = no write-down (confidentiality).
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0083 â€” Biba three axioms?
> Simple integrity = no read-down; *-integrity = no write-up; invocation = no invoking higher-level subject (integrity).
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0084 â€” RBAC rules?
> Role assignment Â· role authorization Â· transaction authorization.
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0085 â€” XACML roles?
> PDP (decision) Â· PEP (enforcement/inspect) Â· PAP (admin) Â· PIP (information).
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0086 â€” ABAC attribute types?
> Subject/user Â· object/resource Â· environmental/context Â· action.
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0087 â€” Castle-and-moat flaw?
> Inside = automatically trusted; with cloud/mobile the perimeter is indefinable and lateral movement is unchecked.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0088 â€” Zero-trust focus areas?
> Data Â· networks Â· people Â· devices Â· workloads.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0089 â€” ZTA deployment steps?
> Identify protect surface â†’ map transaction flows â†’ build ZTA â†’ create policy â†’ monitor & maintain.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0090 â€” NIST ZTA document?
> NIST SP 800-207, produced 2018 with NCCoE â€” abstract ZTA definition + roadmap.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0091 â€” ZTA logical components roles?
> PE decides Â· PA issues session tokens/credentials Â· PEP turns policy on/off between subject & resource.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0092 â€” ZTA vs DiD?
> ZTA = continuous verification, internal + external threats; DiD = layered defenses, primarily external threats.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0093 â€” Four IAM areas?
> Authentication Â· Authorization Â· User management Â· Central user (identity) repository.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0094 â€” Authentication factors?
> Something you know (password) Â· Something you have (token/card) Â· Something you are (biometrics).
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0095 â€” 2FA combos?
> Password+smart card Â· password+biometrics Â· password+OTP Â· smart card+biometrics.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0096 â€” Token-based auth advantages?
> Security, scalability, cross-origin sharing, revocation, statelessness.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0097 â€” Centralized vs decentralized authorization?
> Centralized = single DB/unit for all resources (easy, cheap); decentralized = per-resource DB, flexible but cascading/cyclic auth issues.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0098 â€” Accounting purpose?
> Track user actions â†’ trend analysis, breach detection, forensics (AAA: Authentication/Authorization/Accounting).
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0099 â€” Provierre/deprovisioning benefit?
> Eradicates idle "zombie" accounts; auto-removes access on departure.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0100 â€” Symmetric vs asymmetric for data volumes?
> Symmetric single key â†’ large data; asymmetric (public/private) keys â†’ small data.
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0101 â€” Hashing applications + limitation?
> Password storage, file/message integrity; limitation = collisions (worse with shorter hashes).
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0102 â€” Digital certificate purpose?
> Bind public key to owner via trusted CA; ensure non-repudiation.
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0103 â€” PKI components?
> CA (issue/verify) Â· RA (verifier) Â· certificate management system Â· directories.
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0104 â€” ZKP properties + elements?
> Completeness, soundness, zero-knowledge; Witness, Challenge, Response.
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0105 â€” DES vs 3DES keys?
> DES 64-bit block / 56-bit key; 3DES = DES thrice (encrypt K1, decrypt K2, encrypt K3) â€” independent keys most secure, identical keys least.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0106 â€” AES parameters?
> 128-bit block; key sizes 128/192/256; iterated block cipher (NIST).
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0107 â€” RC6 vs RC5?
> RC6 adds integer multiplication + four 4-bit working registers.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0108 â€” DSA basis + hash size?
> FIPS 186 digital signature standard; 320-bit signature, 512â€“1024-bit security.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0109 â€” RSA digital envelope?
> DES-encrypted message + RSA-encrypted DES key.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0110 â€” SHA generations?
> SHA-1 (160-bit, deprecated), SHA-2 (SHA-256/512 + truncations), SHA-3 (sponge construction).
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0111 â€” HMAC key property?
> Uses inner+outer keys; executes hash twice â†’ resists length-extension attacks.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0112 â€” Segmentation benefits?
> Improved security, better access control, improved monitoring, improved performance, better containment.
> Source: [[03-LO06-Network-Segmentation]]

> [!question]- 0113 â€” DMZ hosting rules?
> Web/email/DNS/FTP servers; internal + external can connect to DMZ; DMZ hosts cannot connect into internal network.
> Source: [[03-LO06-Network-Segmentation]]

> [!question]- 0114 â€” DMZ firewall designs?
> Single (three-legged, single point of failure) vs dual firewall (most secure, most complex).
> Source: [[03-LO06-Network-Segmentation]]

> [!question]- 0115 â€” Segmentation best practices?
> Least privilege Â· limit third-party access Â· audit & monitor Â· easy legitimate paths Â· combine similar resources Â· don't over-segment Â· visualize.
> Source: [[03-LO06-Network-Segmentation]]

> [!question]- 0116 â€” IDS vs IPS placement?
> IPS is in-line (blocks/drops/corrects); IDS sits off-side via a network tap (monitors, cannot act directly).
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0117 â€” Three detection methods in an IDS?
> Signature-based â†’ anomaly-based (statistical) â†’ stateful protocol analysis.
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0118 â€” Honeypot deployment types?
> Production (in production network, looks real) vs Research (analyze attacker steps for countermeasures).
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0119 â€” Honeypot design types?
> Pure Â· low-interaction (fake common services) Â· high-interaction (real systems via VM, costly).
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0120 â€” Proxy server main function?
> Intercepts/filters client requests and serves them on behalf of real servers, hiding internal IPs; extra defense layer.
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0121 â€” Protocol analyzer NIC mode?
> Promiscuous mode to capture all packets on the network.
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0122 â€” Web content filter protections?
> Malware, phishing, pharming; filters by keywords, URLs, contextual analysis.
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0123 â€” Load balancer purpose + example algorithms?
> Routes client traffic to least-loaded/most-available server. Algorithms: round-robin, least-connections, least-loaded.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0124 â€” UTM biggest risks?
> Single point-of-failure + single point-of-compromise; one console = overall need, but less specialized.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0125 â€” How does SIEM act on detected threats?
> Correlates/analyzes events, then communicates with + reconfigures firewall and IPS rules to respond.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0126 â€” NAC main purpose?
> Restrict/allow end-user network access based on a security policy; blocks systems lacking AV/IPS.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0127 â€” VPN tunneling protocol layers?
> Layer 2 (data link) or layer 3 (network, OSI). Common: IPsec, PPTP, L2TP, SSL.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0128 â€” SOAR three elements?
> Orchestration (connect tools), Automation (replace manual tasks), Response (single dashboard IR actions).
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0129 â€” RADIUS RFCs + transport?
> RFC 2865 (auth) / RFC 2866 (accounting); client-server on the application layer via UDP (or TCP) as transport; PAP/CHAP/EAP auth.
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0130 â€” RADIUS vs TACACS+ encryption?
> RADIUS encrypts only the password (UDP); TACACS+ encrypts the whole session including username+password (TCP 49), AAA separated.
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0131 â€” Kerberos main protection + identity proof?
> Protects against replay attacks and eavesdropping; proves identity on non-secure networks via tickets (TGT then service ticket).
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0132 â€” PGP session key handling?
> One-time session key encrypts the message; the key itself is encrypted with the recipient's public key and sent alongside.
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0133 â€” S/MIME cryptographic services?
> Authentication, message integrity, non-repudiation, privacy, data security (RSA-based, separate keys for signing and encryption).
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0134 â€” SSL channel-security properties?
> Private (encrypted after handshake), authenticated (server always, client optional), reliable (integrity check).
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0135 â€” IPsec services?
> AH = sender authentication only; ESP = sender authentication + data encryption; peer auth, data origin auth, integrity, confidentiality, replay protection.
> Source: [[03-LO08-Network-Security-Protocols]]

### Module 04 (93 items)

> [!question]- 0136 â€” Firewall core function?
> Gateway/filtering device enforcing the network security policy between private network and Internet (first line of defense).
> Source: [[04-LO01-Firewall-Concerns-Capabilities-Limitations]]

> [!question]- 0137 â€” Typical firewall capabilities?
> Prevent scanning, control traffic, user auth, filter packets/services/protocols, traffic logging, NAT, malware prevention.
> Source: [[04-LO01-Firewall-Concerns-Capabilities-Limitations]]

> [!question]- 0138 â€” Key firewall limitations vs malware?
> Not an antivirus substitute; can't stop zero-day/new viruses, backdoor/insider, social engineering, password misuse, tunneled traffic.
> Source: [[04-LO01-Firewall-Concerns-Capabilities-Limitations]]

> [!question]- 0139 â€” Packet-filtering firewall layer + bypass vector?
> Network layer; evaluates headers (IP/ports/protocol/TCP bits); bypassable via packet spoofing.
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0140 â€” Circuit-level gateway layer + limitation?
> Session layer; validates TCP handshake; hides private network; can only handle TCP, no content scanning.
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0141 â€” Application-level gateway filtering?
> Application layer: per app/protocol (e.g., web proxy blocks FTP/Telnet), filters HTTP GET/POST commands.
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0142 â€” Stateful multilayer inspection?
> Combines packet + session + application checks; tracks slots/translations; expensive, needs skilled staff.
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0143 â€” NAT translation most efficient mode?
> Dynamic address+port pair allocated per inbound connection (best external-address use).
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0144 â€” NGFW = generation + extra layer?
> Third-generation; traditional L3â€“L4 + application layer 7 (DPI, encrypted-traffic inspection, integrated IPS, threat intel).
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0145 â€” Cloud firewall alias + types?
> FaaS (firewall as a service); types: SaaS firewalls, NGFWs in virtual datacenters (PaaS/IaaS).
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0146 â€” Screened subnet alias + structure?
> "Triple-homed firewall" (single FW, 3 interfaces: Internet/DMZ/intranet); DMZ hosts public services; compromises FW can't reach intranet.
> Source: [[04-LO03-Firewall-Topologies]]

> [!question]- 0147 â€” Dual-homed host key property?
> Two NICs (untrusted + trusted); no direct routing between them â€” firewall is the intermediary.
> Source: [[04-LO03-Firewall-Topologies]]

> [!question]- 0148 â€” Topology for a simple network with no public services?
> Bastion host (single layer of protection; fine for corporate surfing, not web/email hosting).
> Source: [[04-LO03-Firewall-Topologies]]

> [!question]- 0149 â€” Topology when two or more network zones exist?
> Multi-homed firewall (per-interface security policies; trusted network stays safe if DMZ breached).
> Source: [[04-LO03-Firewall-Topologies]]

> [!question]- 0150 â€” Hardware vs software firewall cost/placement?
> Hardware: dedicated perimeter device (Cisco ASA/FortiGate), pricier, faster; software: per-host program (Windows FW/iptables/UFW), cheap, resource-heavy.
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0151 â€” Host vs network-based firewall example each?
> Host: Windows Firewall/iptables/UFW (software, per device); network: pfSense/SmoothWall/Cisco SonicWall (hardware, perimeter).
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0152 â€” Host-based firewall analysis order?
> Packet inspection (L3/L4, MAC/IP/ports) â†’ stateful filter validation â†’ application-layer validation.
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0153 â€” External firewall primary role?
> Limit protectedâ†”public traffic, protect DMZ + legacy devices without firewalls; block new externalâ†’internal connections.
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0154 â€” Internal firewalls sit where?
> Between two segments of the same org (or two orgs on the same network); segment + monitor, contain malicious spread.
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0155 â€” Two techniques of traffic normalization?
> (1) clean up malformed packets, (2) drop illegal packets â€” normalized at every protocol layer before payload inspection.
> Source: [[04-LO05-Deep-Traffic-Inspection-Selection]]

> [!question]- 0156 â€” Why stream-based inspection for fighten evasion?
> Segment/pseudo-packet-only inspection misses malicious payloads spread across boundaries; stream inspection needs more RAM+CPU.
> Source: [[04-LO05-Deep-Traffic-Inspection-Selection]]

> [!question]- 0157 â€” Exploit-based vs vulnerability-based detection?
> Exploit-based: 100% signature match (can't cover every evasion); vulnerability-based: block exploitation at network+application layers (preferred).
> Source: [[04-LO05-Deep-Traffic-Inspection-Selection]]

> [!question]- 0158 â€” Firewall deployment phases?
> Planning â†’ Configuring â†’ Testing â†’ Deploying â†’ Managing & Maintaining.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0159 â€” Firewall policy creation steps?
> 1 key apps â†’ 2 vulnerabilities â†’ 3 cost-benefit â†’ 4 app traffic matrix â†’ 5 ruleset from matrix.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0160 â€” Ruleset review cadence + implicit rule?
> Review/update every 6 months; implicit deny blocks all traffic not explicitly allowed.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0161 â€” Blacklist vs whitelist ruleset?
> Blacklist: allow all, deny listed. Whitelist: deny all, allow only listed (stricter).
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0162 â€” Firewall log placement?
> Centralized secure server/syslog; huge volumes (â‰¥10k events/s) need specialized software.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0163 â€” Test-network evaluation attributes?
> Connectivity, ruleset, app compatibility, management, logging, performance, security, component interoperability, policy sync.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0164 â€” Maintenance activities?
> Patches, policy updates on new threats, 6-month review, log analysis, regular ruleset/policy backups.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0165 â€” Firewall log backup cadence + purpose?
> Monthly to secondary storage; backup before/after rule changes; for legal/future reference after incidents.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0166 â€” Default inbound rule posture?
> Default 'deny' inbound with explicit 'allow' rules; implicit deny at end of ruleset blocks everything not allowed.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0167 â€” Secure email access design?
> Separate email network zone firewalled from DMZ + internal network; email + webmail servers placed in it.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0168 â€” Rule lifecycle management?
> Add expiration dates to temporary rules, review for cleanup; test policies before implementing.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0169 â€” Firewall audit frequency + password policy?
> Audits at least once a year; change firewall passwords regularly (â‰ˆ every 6 months).
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0170 â€” Key firewall don'ts?
> No telnet access through FW, no direct internal-clientâ†”outside-service connections, don't rely on packet filtering alone, don't skip SSL.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0171 â€” Firewall remote management protection?
> Encryption + strong user auth; HTTPS (SSL over HTTP) GUI; unique user IDs/passwords, token-based RADIUS.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0172 â€” Failover mechanism?
> Heartbeat-based services shift traffic to backup firewall; primary+backup behind a single MAC address.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0173 â€” Firewall backup policy?
> Full 'day zero' backups (not incremental) before production release; in-built backup facilities; UNIX /var holds logs+spools.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0174 â€” On security incident, first actions?
> Temporarily disable remote access + revoke user authentication; correlate events via NTP-synchronized firewall.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0175 â€” Client access to external hosts?
> Never direct â€” through firewall as proxy; a firewall combines application-level packet filtering + domain-level proxy.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0176 â€” IDS vs IPS core difference?
> IDS detects + alerts; IPS detects + actively blocks (inline); IPS also fixes CRC, defragmentation, TCP sequencing, layer options.
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0177 â€” Why implement an IDS behind the firewall?
> Firewalls allow/deny by rules but never inspect legitimate traffic content; IDS inspects it for malicious payloads/signatures.
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0178 â€” What is NOT an IDS?
> Network logging systems, vulnerability assessment tools, antivirus products, cryptographic systems (VPN/SSL/S-MIME/Kerberos/RADIUS).
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0179 â€” Common IDS deployment mistakes?
> Wrong placement (not seeing all traffic), ignoring alerts, no response plan, not tuning false pos/neg, stale signatures, inbound-only monitoring.
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0180 â€” NIDS + encrypted traffic problem?
> Without IPsec visibility, NIDS only does packet-level analysis of encrypted tunnels (app contents inaccessible) â†’ more vulnerable.
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0181 â€” IDS classification bases?
> Approach, protected system, structure, data source, behavior (after attack), analysis timing.
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0182 â€” Signature vs anomaly detection tradeoff?
> Signature: few false alarms but known attacks only; anomaly: finds unknown attacks but high false-positive rate.
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0183 â€” Active vs passive IDS?
> Active auto-blocks without admin; passive only monitors/analyzes/alerts and logs.
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0184 â€” NIDS vs HIDS placement?
> NIDS: network boundaries behind FW/routers/VPN/wireless; HIDS: on the host (sensitive public servers).
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0185 â€” Interval-based vs real-time IDS?
> Interval: offline "store and forward", no active response; real-time: on-the-fly, continuous feed, more RAM+disk.
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0186 â€” IDS data sources?
> Audit trails (system/app/user evidence) and network packets (header+payload captured pre-destination).
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0187 â€” Six IDS components?
> Network sensors, analyzer, alert systems, command console, response system, attack-signature database.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0188 â€” Alert delivery methods?
> Pop-up windows, email, sounds, mobile messages.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0189 â€” True vs false positive alert?
> True positive = correctly identified successful attack; false positive = event misidentified as attack.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0190 â€” Response system countermeasures?
> Log out user, disable account, block attacker source, restart server/service, close connections/ports, reset TCP sessions.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0191 â€” IDS detection process steps?
> Install signatures â†’ gather data â†’ alert sent â†’ IDS responds â†’ admin assesses damage â†’ escalation â†’ events logged/reviewed.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0192 â€” Where to place sensors?
> Internet gateways, between LAN connections, remote-access/dial-up servers, either side of firewall, VPN devices.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0193 â€” IDS staged deployment benefit?
> Discovers where security/sensors are needed, lets admins adapt; initial stage requires highest maintenance.
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0194 â€” NIDS sensor order of deployment?
> IDS management console first, then sensors incrementally at choke points/gateways/DMZ.
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0195 â€” Outside-firewall sensor tuning (L1)?
> Least-sensitive attacks, logs attempts only (no alerts) to avoid false alarms.
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0196 â€” DMZ sensor (L2) coverage?
> Perimeter + firewall-bypass detection; web/FTP servers; low-moderate impact attacks; also outbound.
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0197 â€” HIDS deployment approach?
> Critical servers first â†’ management console â†’ then every host, only if manageable (costly, many false alarms).
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0198 â€” Four IDS alert types?
> True positive, false positive (no attack-alert), false negative (attack-no alert â€” most dangerous), true negative.
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0199 â€” False positive rate formula?
> FP / (FP + true negative).
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0200 â€” False negative rate formula?
> FN / (FN + true positive).
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0201 â€” Sensitivity vs specificity?
> Sensitivity = legitimacy of alerts detected; specificity = filters/accuracy of detected alerts (set IDS threshold).
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0202 â€” Encrypted-traffic false-negative fix?
> Place IDS behind a VPN termination with SSL so it can inspect decrypted traffic.
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0203 â€” False-positive sources?
> Reactionary traffic (device failure), network equipment (load balancer odd packets), non-malicious software bugs, IDS software bugs.
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0204 â€” Good IDS characteristics?
> Continuous run, fault tolerant, subversion-resistant, minimal overhead, deviation detection, not easily deceived, tailored to system, copes with dynamic behavior.
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0205 â€” Five IDS product selection categories?
> General requirements, security capabilities, performance, management, lifecycle cost.
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0206 â€” IDS security capability requirements?
> Information gathering, logging, detection, prevention.
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0207 â€” NIDS vs HIDS performance measure?
> NIDS = monitor/handle network traffic; HIDS = events processed per second.
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0208 â€” Lifecycle cost categories?
> Initial (appliances, software/licensing, installation, customization, training) and maintenance (staff wages, customization, maintenance contracts, support).
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0209 â€” NIDS tools covered?
> Snort (signature/protocol/anomaly rules), Zeek/Bro (behavioral + network analysis), Suricata (IDS/IPS, multi-gigabit, Eve JSON logging).
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0210 â€” Snort capabilities?
> Real-time traffic analysis, packet logging, protocol analysis, content matching; detects DoS, OS fingerprinting, buffer overflows, stealth port scans, SMB/CGI attacks.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0211 â€” Zeek (Bro) features?
> Behavioral-based, high-performance networks, full logging, application-layer semantic analysis + state, domain-specific scripting; integrate logs with ELK for visualization.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0212 â€” Suricata features?
> IDS/IPS + NSM + offline pcap; multi-gigabit single instance; auto protocol detection; Lua scripting; Eve JSON + YAML/SIEM integration.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0213 â€” OSSEC features?
> HIDS: log analysis, integrity checking (FIM), Windows registry monitoring, rootkit detection, time-based alerting, active response.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0214 â€” Wazuh origin + role?
> Fork of OSSEC; agent-level anomaly + signature detection, monitors user activity, config assessment, vulnerability detection.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0215 â€” Why harden routers?
> Prevent info disclosure, router disablement/reconfiguration, internal/external attacks via router, traffic rerouting.
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0216 â€” Three key router disables?
> IP directed broadcasts, IP source routing, HTTP configuration (clear text); plus ARP/proxy ARP.
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0217 â€” Switch port-security MAC methods?
> Static (single MAC), dynamic (CAM default), sticky (port-assigned MAC; lost if not saved over reboot).
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0218 â€” Switch layer-2 attack types?
> MAC flooding, DHCP spoofing, ARP spoofing.
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0219 â€” Switch hardening controls?
> SSH, ACLs/VLAN ACLs, DHCP snooping, DAI, port security, port auth, STP root/BPDU guards, disable DTP/CDP/auto-trunking, AAA.
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0220 â€” SDP name + founder?
> "Black Cloud", identity-centric security framework by the Cloud Security Alliance (CSA).
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0221 â€” Three SDP pillars?
> Zero trust (micro-segmentation, least privilege), identity-centric (identity not IP), built for the cloud (scalable).
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0222 â€” How SDP defeats static firewalls?
> Dynamic logical firewall with one rule â€” deny all connections; rules added/removed per authorized user; prevents lateral movement.
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0223 â€” SDP reverse of TCP?
> SDP authenticates/authorizes first then connects; TCP connects, authenticates, then passes data.
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0224 â€” SDP three components?
> Client (initiating host), controller (auth + policy), gateway (accepting host, controller-directed).
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0225 â€” SPA in SDP?
> Single-Packet Authorization â€” client sends HMAC-based one-time password packet as first packet; invalid packets rejected (minimizes DDoS impact).
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0226 â€” SDP workflow steps?
> Controllers online â†’ gateways online+authenticate â†’ client authenticates â†’ controller picks authorized gateways â†’ instructs gateway â†’ sends list to client â†’ mutual VPN established.
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0227 â€” SDP deployment models?
> Client-to-gateway, client-to-server, server-to-server, client-to-server-to-client, client-to-gateway-to-client, gateway-to-gateway.
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0228 â€” SDP vs traditional NAC (examples)?
> Fine-grained per-user/app control vs all-or-nothing VLAN; VPN replaced vs VPN required; dynamic attr + identity integration vs 802.1X; reduced audit scope vs SIEM consolidation.
> Source: [[04-LO17-Software-Defined-Perimeter]]

### Module 05 (101 items)

> [!question]- 0229 â€” Windows ring model?
> Ring 0 = kernel (most privileged) â†’ rings 1/2 = drivers â†’ ring 3 = user mode/apps (least privileged).
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0230 â€” User mode vs kernel mode?
> User = private virtual address space, no direct HW access, isolates apps; kernel = unrestricted access, crashes can take the OS down.
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0231 â€” Environment subsystems?
> Win32 Â· OS/2 Â· POSIX (replaced by WSL on Win10/Server 2019).
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0232 â€” Integral subsystems?
> Security subsystem Â· Workstation service (redirector/client) Â· Server service (serves shares).
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0233 â€” Security Reference Monitor?
> Primary authority implementing Windows security rules; decides object/resource access via ACLs.
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0234 â€” Windows security concern root causes?
> Unpatched OS, improper configurations, unnecessary services/processes enabled, weak passwords, missing anti-malware.
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0235 â€” WSL?
> Windows Subsystem for Linux â€” compatibility layer running Linux binaries on Windows 10 / Server 2019; replaced POSIX subsystem.
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0236 â€” Windows security blocks/components?
> SRM Â· LSASS Â· SAM Â· WinLogon/NetLogon Â· Registry Â· Access control Â· Active Directory.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0237 â€” SRM function + location?
> Enforces ACL-based access control over subjectsâ†’objects, logs for auditing; kernel component `system32\Ntoskrnl.exe`.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0238 â€” LSASS role/location?
> `lsass.exe`; local-logon authentication, local security policies, issues access tokens, audit messages to Event Log.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0239 â€” SAM store + location?
> Hashed local logon credentials; `samsrv.dll`, DB in `C:\Windows\System32\config\`.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0240 â€” DC logon-database usage?
> DC uses AD database; SAM only for DSRM boot / local logon (DSRM password stored in SAM).
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0241 â€” Credential providers?
> COM objects in LogonUI collecting password/PIN/biometrics (authui.dll, SmartcardCredentialProvider.dll).
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0242 â€” NetLogon functions?
> Identify DC, set up secure channel, send auth request to DC, return result; used for AD logons.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0243 â€” KSecDD?
> Kernel-mode library `ksecdd.sys` for ALPC; kernel-mode security â†” LSASS in user mode; SecLookup*/SecMakeSPN* functions.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0244 â€” Windows object access control: DACL vs SACL?
> DACL = who is allowed/denied access; SACL = how the system audits access attempts. Part of the object's security descriptor.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0245 â€” NULL DACL vs empty DACL?
> NULL DACL grants full access to everyone, skips normal checks; empty DACL (0 ACEs) grants no access.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0246 â€” Access-check ACE accumulation?
> Access rights per ACE accumulate (read from one group + write for user = both); order matters â€” user deny-ACE must precede group allow-ACE.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0247 â€” View a user's SID?
> PsGetSid: `psgetsid <Domain>\<User>`; Process Explorer Security tab; `wmic useraccount get name,sid`; registry ProfileList.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0248 â€” Windows integrity levels (lowâ†’high)?
> Untrusted â†’ Low â†’ Medium â†’ High â†’ System â†’ Installer.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0249 â€” Integrity level of a Run As Administrator process?
> High; standard-user processes run Medium; IE protected mode (PMIE) runs Low.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0250 â€” Virtual service account name + benefit?
> `NT SERVICE\<service name>`, own SID, password auto-managed by Windows; created via `sc create ... obj="NT SERVICE\..."`.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0251 â€” Audit category for password reset?
> Audit account management.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0252 â€” Event ID 4625?
> An account failed to log on; Logon Types: 2 = interactive, 3 = network.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0253 â€” Smart App Control enforcement rule?
> Apps run only when recognized by Microsoft app intelligence or signed with a trusted cert; verify mode via `citool.exe -lp`.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0254 â€” Credential Guard protections + attack types?
> Virtualization-isolated secrets (NTLM pwds, Kerberos TGTs, app credentials); blocks pass-the-hash (PtH) and pass-the-ticket (PtT).
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0255 â€” Vulnerable Driver Blocklist registry key?
> `HKLM\SYSTEM\CurrentControlSet\Control\CI\Config` â†’ `VulnerableDriverBlocklistEnable` = 1.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0256 â€” What is a Windows security baseline?
> Group of Microsoft-recommended configuration settings; ensures user+device config compliance, updated for new vulnerabilities/misconfigurations.
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0257 â€” What replaced Security Compliance Manager (SCM)?
> Security Compliance Toolkit (SCT).
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0258 â€” SCT core tools?
> Policy Analyzer Â· LGPO.exe Â· SetObjectSecurity.exe Â· GPO2PolicyRules.
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0259 â€” Policy Analyzer function?
> Treats GPOs as one unit, finds duplicate/conflicting settings, compares system vs recommended baseline, takes config snapshots.
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0260 â€” LGPO.exe use?
> Command-line local group policy automation; import/export Registry.pol, security templates, GPO backups; manages nondomain-joined systems.
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0261 â€” SetObjectSecurity.exe use?
> Set security descriptors on securable objects (files, dirs, registry keys, event logs, services, SMB shares).
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0262 â€” Three Windows account types?
> Administrator (full access), Standard (own files only), Guest (read/write only).
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0263 â€” Disable guest account (command)?
> `net user guest /active:No`; policy: Local Policies â†’ Security Options â†’ 'Accounts: Guest account status'.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0264 â€” Disable vs delete an account?
> Disabled = restorable; deleted = cannot be restored.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0265 â€” Password complexity requirements?
> Not contain account name/2+ consecutive name chars; â‰¥6 chars; 3 of 4 categories (upper, lower, digits, non-alphabetic).
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0266 â€” Default maximum password age?
> 42 days.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0267 â€” Credential Guard protects what?
> LANMAN password hashes + Kerberos TGT; thwarts pass-the-hash; hashes can't be decrypted even if extracted.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0268 â€” Why worry about local administrator SID?
> If attackers know the admin account's SID they can compromise the system even when the account name is changed.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0269 â€” Patch vs service pack vs version upgrade?
> Patch = fix for one vulnerability; SP = fixes + functionality; upgrade = fixes + improved security features.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0270 â€” Enable automatic updates (command)?
> `sc config wuauserv start= auto`; or Services.msc â†’ Windows Update â†’ Automatic.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0271 â€” Auto-update registry key?
> `HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU` â†’ DWORD NoAutoUpdate.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0272 â€” Prevent force restarts after updates (registry)?
> `HKLM\SOFTWARE\Microsoft\Windows\Windows Update\AU` â†’ NoAutoRebootWithLoggedOnUser = 1; GPO: 'No auto-restart with logged on usersâ€¦'.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0273 â€” Which tool extends WSUS/SCCM?
> SolarWinds Patch Manager.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0274 â€” Tool that detects vulnerabilities before an attacker does?
> GFI LanGuard.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0275 â€” NTFS permission unique to folders (not files)?
> List Folder Contents (only when inherited by folders; Read & Execute applies to files too).
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0276 â€” FAT vs NTFS file permissions?
> NTFS = per-file/folder permissions + backup/restore; FAT = no per-file/folder permissions.
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0277 â€” UAC core behavior?
> Apps run at standard-user privileges until an administrator authorizes elevation; prevents malware from changing security settings/AV.
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0278 â€” What does a SID's RID enable for attackers?
> RIDs are predetermined for some accounts â€” attacker replaces RID with an administrative account's to get admin privileges (block via 'Network access: Do not allow anonymous enumeration of SAM accounts and shares').
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0279 â€” Policy to block Control Panel?
> User Configuration â†’ Admin Templates â†’ Control Panel â†’ 'Prohibit access to Control Panel and PC settings' (blocks Control.exe/SystemSettings.exe).
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0280 â€” Policy to block Command Prompt?
> User Configuration â†’ Admin Templates â†’ System â†’ 'Prevent access to the command prompt'; also governs .cmd/.bat batch files.
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0281 â€” JEA â€” what does it limit?
> The cmdlets/admin privileges of an account; needs a PS role capability file (visible cmdlets) + PS session configuration file (who may run them); uses per-session virtual account.
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0282 â€” LM vs NT hash?
> <15-char passwords â†’ LM hash, else NT hash; both brute-forceable â€” block LM storage via 'Network security: Do not store LAN Manager hash value on next password change'.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0283 â€” Example Windows services to disable when unused?
> IIS, FTP, SQL Server, proxy services, Telnet, Universal Plug and Play.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0284 â€” Disable Remote Desktop (commands)?
> `net stop termservice`, then `sc config termservice start= disabled`.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0285 â€” Windows Defender quick scan vs full scan?
> Quick = areas where malware usually hides; full = all files and applications.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0286 â€” Registry hives (key names)?
> HKLM (machine) Â· HKCU (current user; new subkey each logon) Â· HKCC (hardware profile) Â· HKCR (file extensions + COM registration).
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0287 â€” Registry monitoring tool?
> Process Monitor (Sysinternals) â€” real-time registry (and file/system) activity.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0288 â€” Firewall default rule behavior?
> Inbound connections blocked unless an allow rule matches; outbound connections allowed unless a block rule matches.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0289 â€” AD attack method that reuses the password hash instead of the plaintext against the Domain Admins account?
> Pass-the-hash (often via an infiltrated LM hash).
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0290 â€” Risk of a default Administrator account in the Domain Admins group?
> Domain Admins is tied to every domain system; privilege escalation (pass-the-hash) on one machine exposes the whole domain.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0291 â€” LAPS purpose and scope?
> Random unique local Administrator passwords stored in AD for domain-joined systems; manages only the local Administrator account; needs a client-side extension; Windows only.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0292 â€” Two AD schema attributes added by LAPS?
> Administrative password + password expiration date/time (via Update-AdmPwdADSchema).
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0293 â€” NTLM vs NTLMv2 hashing?
> NTLM = MD4 for passwords (Unicode, up to 127 chars, 128-bit MD4); NTLMv2 = MD4 for passwords and MD5 for usernames/server names, response differs each time.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0294 â€” Goal of blocking NTLM v1 in a domain?
> Force NTLMv2 (and Kerberos) so passwords are not transmitted in weaker form.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0295 â€” AD events that indicate compromise?
> Admin-group changes, wrong-password attempts, locked-out-account usage, account lockouts, AV-setting changes, privileged-account activity.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0296 â€” Event ID + logon types that reveal remote vs local logon?
> 4624; Type 2 = local logon, Type 10 = remote logon.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0297 â€” KRBTGT password best practice?
> Change every year, or whenever an AD administrator leaves.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0298 â€” WDigest hardening?
> Set `HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\WDigest` to 0.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0299 â€” UAC behavior on approved vs denied changes?
> Approved â†’ action runs with highest available privilege; denied â†’ not performed and requesting app is prevented from running.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0300 â€” Effect of a missing/invalid code signature?
> Windows prevents the file from running (legitimate cert also removes SmartScreen "Unknown Publisher" warning).
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0301 â€” What guarantees a driver can load into the Windows kernel?
> Valid digital signature (vendor certifies with Microsoft, then WHQL signs it); unsigned driver packages do not install.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0302 â€” TPM functions?
> Secure key storage, secure boot + chain of trust (PCR measurements), platform measurements, remote attestation (cryptographic "quote" of PCR values).
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0303 â€” Which Windows features use TPM?
> BitLocker (system drive), Secure Boot, Device Guard, Credential Guard.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0304 â€” WRP failure modes when an app modifies a protected resource?
> Access-denied error + install may fail; protected reg-key changes denied; apps writing into protected keys/folders/files may fail.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0305 â€” Integrity-checking tools in order for a corrupted image?
> SFC (/scannow) for system files; DISM /ScanHealth â†’ /CheckHealth â†’ /RestoreHealth for image repair; chkdsk for disk errors/bad sectors.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0306 â€” SFC /FILESONLY scope?
> Verifies/repairs only files, not registry keys.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0307 â€” chkdsk default mode?
> Read-only scan (/f not specified); add /f to fix, /r to find bad sectors and recover data.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0308 â€” Get-FileHash default algorithm + full options?
> Default SHA256; options SHA1, SHA256, SHA384, SHA512, MD5.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0309 â€” OSSEC integrity checker + hashes used?
> Syscheck â€” periodic MD5/SHA1 checksum comparison on configured files/registry entries.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0310 â€” Tripwire Enterprise core capabilities?
> File Integrity Monitoring (FIM) + Security Configuration Management (SCM), with policy compliance and remediation management.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0311 â€” PS Remoting protocol + ports?
> WSMAN/WinRM; 5985 HTTP, 5986 HTTPS; traffic encrypted even over 5985.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0312 â€” Default permission to PS Remoting endpoints?
> System administrators + Remote Management Users.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0313 â€” How are workgroups protected in PS Remoting?
> Enable SSL/HTTPS with certificates and add them to trusted hosts â€” avoids MITM. (AD uses Kerberos.)
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0314 â€” Three PS logging types?
> Module (pipeline), Transcript (every session), Script block (executed code, de-obfuscation).
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0315 â€” Execution policies, strictest to loosest?
> Restricted â†’ AllSigned â†’ RemoteSigned â†’ Unrestricted. Enforce via GPO (bypassable otherwise); Computer Configuration > User Configuration.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0316 â€” Why disable PowerShell 2.0?
> Security risk used by attackers to execute malicious code (`Disable-WindowsOptionalFeature -FeatureName MicrosoftWindowsPowerShellv2Root`).
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0317 â€” What does Constrained Language Mode block?
> COM objects, unapproved .NET types, XAML-based workflows, PowerShell classes.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0318 â€” Best enforcement of Constrained Language Mode?
> Device Guard UMCI (can't be easily disabled by admins); AppLocker script rules in Allow Mode best under least privilege.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0319 â€” RDP default port and encryption scope?
> TCP 3389; tunneling encrypts data between client and server only â€” terminal-server authentication is unencrypted (guessable â†’ MITM).
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0320 â€” Scoping the RDP firewall rule?
> Restrict the RDP rule's Scope to specific remote IP addresses; rejections happen at the firewall, freeing server resources.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0321 â€” RDP gateway encryption path?
> Internal hops use 3389; from the gateway to the client the data is encrypted over HTTPS port 443 with SSL certs.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0322 â€” Why is plain 3389 insecure?
> Password-protected only (not encrypted) â†’ susceptible to brute-force.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0323 â€” What does NLA do?
> Requires authentication before the RDP session is established, sending credentials securely via the client's security service provider.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0324 â€” Remote Credential Guard protection?
> No passwords in memory / no hashes â†’ defeats pass-the-hash and brute-force; redirects Kerberos requests to the client device. Restricted Admin = credentials not delegated.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0325 â€” DNSSEC guarantees vs non-guarantees?
> Guarantees authenticity, integrity, non-existence of name/type; does NOT guarantee confidentiality or DoS protection.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0326 â€” Threat mitigated by DNSSEC?
> DNS cache poisoning and DNS spoofing (validates the key attached to the DNS server response against TLD/root data).
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0327 â€” How to spot a malicious domain in DNS logs?
> Unusual random-character names; log via DNS Management Console â†’ Debug Logging â†’ "Log packets for debugging".
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0328 â€” SMB version to disable and why?
> SMB 1.0 â€” legacy, weak; keep SMB 2.0/3.0+ (2.02+ signing, 3.0+ encryption, 3.1.1+ pre-auth integrity). Registry: SMB1 = 0.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0329 â€” SMB encryption details?
> AES-CCM; end-to-end; no IPsec/WAN accelerators; per-share (Set-SmbShare) or server-wide (Set-SmbServerConfiguration).
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

### Module 06 (66 items)

> [!question]- 0330 â€” Core parts of the Linux system architecture?
> Hardware â†’ kernel (core, full resource control) â†’ shell (interface to kernel) â†’ applications/utilities, system libraries, daemons (background services), graphical server (X server/X).
> Source: [[06-LO01-Linux-OS-and-Security-Concerns]]

> [!question]- 0331 â€” Key Linux features (security relevant)?
> Portability, open-source, multiuser, multiprogramming, hierarchical FS, shell, security (authentication/password protection, controlled file access, data encryption).
> Source: [[06-LO01-Linux-OS-and-Security-Concerns]]

> [!question]- 0332 â€” Why is Linux considered risky despite open code?
> Open-source â†’ anyone can modify/distribute â†’ unexpected vulnerabilities; poor configuration and defender oversight; increasingly targeted by malware.
> Source: [[06-LO01-Linux-OS-and-Security-Concerns]]

> [!question]- 0333 â€” CVE-2023-42755 example?
> IPv4 RSVP classifier flaw â€” out-of-bounds read in rsvp_classify; local user can crash system â†’ DoS (CVSS 6.5).
> Source: [[06-LO01-Linux-OS-and-Security-Concerns]]

> [!question]- 0334 â€” Ubuntu minimal installation effect?
> Fewer packages (~80 removed): desktop + browser + core tools; prevents installing third-party/untrusted apps that may be vulnerable to new exploits.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0335 â€” What do BIOS + boot loader passwords block?
> BIOS: changing settings, booting system. Boot loader (GRUB/LILO): single-user mode, GRUB console, non-secure OS on dual-boot.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0336 â€” GRUB password hash command?
> `grub-mkpasswd-pbkdf2` â†’ paste hash via `password_pbkdf2 name <hash>` + `set superusers=` in `/etc/grub.d/40_custom`.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0337 â€” Debian manual patch commands?
> `apt-get update` (fetch list), `apt-get upgrade` (upgrade current), `apt-get dist-upgrade` (install new). Red Hat: `yum check-update` / `yum update`. SUSE: `zypper`.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0338 â€” Discouraged when hardening installation?
> Install more than needed; leave OS unprotected on hostile network pre-hardening; no update mechanism; single / volume for everything.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0339 â€” Why separate `/tmp` with nodev,noexec,nosuid?
> Prevents resource exhaustion, device creation, binary execution, and setuid files in /tmp; sticky bit stops cross-user file deletion.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0340 â€” systemctl service commands?
> List: `systemctl --type service`; stop: `systemctl stop [service]`; disable: `systemctl disable [service]`; kill process: `kill -9 [pid]`.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0341 â€” Five legacy services to remove from Linux servers?
> telnet-server, rsh-server, ypserv (NIS), tftp-server, talk-server â€” all unencrypted/insecure. Check `rpm -q <pkg>`, remove `yum erase <pkg>`.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0342 â€” Deborphan purpose + usage?
> Lists unused packages/libraries. `sudo apt-get install deborphan`, then `deborphan --guess-all`; remove via `deborphan --guess-data | xargs sudo aptitude -y purge`.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0343 â€” Ubuntu repository types?
> Main (Canonical-supported FOSS), Universe (community), Restricted (proprietary drivers, limited support), Multiverse (copyright/legal-restricted, paid). Not all audited; disable unsafe ones in Software & Updates.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0344 â€” ClamAV install (Debian/RHEL)?
> Debian: `apt-get update && apt-get install clamav`. RHEL/CentOS: `yum install -y epel-release && yum install -y clamav`. Fedora adds clamav-update.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0345 â€” Why remove unnecessary packages?
> Older/untrusted packages introduce vulnerabilities or waste resources; uninstalls leave dependent files. Use autoremove/clean/autoclean/purge.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0346 â€” Secure Boot requirement?
> UEFI firmware with Secure Boot; signed bootloader (e.g., GRUB2) and signed kernel with valid signatures from a trusted CA.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0347 â€” How do package managers verify integrity?
> GPG keys â€” APT (Debian/Ubuntu), YUM/DNF (/etc/yum.repos.d GPG key URL), zypper (SUSE). Manual: `rpm --checksig package.rpm`, `dpkg-sig --verify package.deb`.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0348 â€” Rootkit detection tools + commands?
> `chkrootkit` (trojans/malware in binaries; `sudo apt-get install chkrootkit`, run `./chkrootkit`) Â· `rkhunter` (backdoors, network/kernel checks; config `/etc/rkhunter.conf`, `rkhunter --check`, baseline `--propupd`).
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0349 â€” IMA vs EVM?
> IMA measures/records/evaluates hashes (serializes log of measured content). EVM extends IMA â€” monitors file extended attributes, uses public keys to verify/sign hashes.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0350 â€” Kernel integrity monitoring techniques?
> Checksums/hashing, File Integrity Monitoring, Secure Boot. Module integrity: module signing, security policies, kernel module whitelisting.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0351 â€” Why use official repositories + GPG keys?
> Untrusted sources may contain compromised or malicious packages; keys verify signature authenticity. Always use official/trusted repositories.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0352 â€” FIM working model?
> Centralized policy â†’ auto-retrieved â†’ compares local filesystem vs system baseline â†’ violations logged in report + sent to central repo; policy = JSON script with risk levels.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0353 â€” Tripwire workflow commands?
> `tripwire --init` â†’ policy `/etc/tripwire/twpol.txt` â†’ `twadmin --create-cfgfile -s site.key /etc/tripwire/twcfg.txt` â†’ cron `tripwire --check` daily.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0354 â€” AIDE commands?
> Init `sudo aide --init`; config `/etc/aide/aide.conf`; update `sudo aide --update`; check `sudo aide --check` (or `# aide --check`); cron daily.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0355 â€” Samhain config settings?
> FILE_CHECKS (monitor list), HIDE_MODIFIED, IGNORE_LIST, REPORT_LEVEL (1 min / 3 detailed), SYSLOG_FACILITY (e.g., LOG_LOCAL4); init `samhain -t init`; logs `/var/log/samhain.log`.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0356 â€” OSSEC key features?
> LIDS, file integrity monitoring (forensic copies), active response (firewall + self-healing), compliance auditing (PCI-DSS/CIS), rootkit/malware detection, system inventory; alerts via `tail -f /var/ossec/logs/alerts/alerts.log`.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0357 â€” IMA + TPM?
> IMA = measure + appraise subsystems; hashes data before load, sends hashes to TPM to protect from alteration; enable `CONFIG_INTEGRITY=y CONFIG_IMA=y`; policies `/etc/ima/ima-policy` (e.g., `func=H`).
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0358 â€” auditd rule to monitor /etc/passwd?
> `sudo auditctl -w /etc/passwd -p wa -k passwd_changes` â€” -w path, -p permissions (w write, a attribute), -k key. Query with `ausearch -i -k <key>` and `aureport -x`.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0359 â€” inotifywait usage?
> `inotifywait /path` (once), `inotifywait --monitor /path` (continuous), `inotifywait --event modify /path` (modification events).
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0360 â€” /etc/login.defs aging params?
> PASS_MAX_DAYS (max lifespan), PASS_MIN_DAYS (min interval between changes), PASS_WARN_AGE (days warned before expiry). New accounts only.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0361 â€” PAM password policy files by distro?
> Red Hat: /etc/pam.d/system-auth. Debian/Ubuntu: /etc/pam.d/common-password. Modules: pam_pwquality.so / pam_cracklib.so / pam_unix.so.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0362 â€” pam_pwquality parameters?
> `retry=3` (3 prompts), `minlength=8` (min chars), `maxrepeat=3` (max repeats). Complexity: ucredit/lcredit/dcredit/ocredit = -1 â†’ at least 1 of each class.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0363 â€” Prevent password reuse in PAM?
> pam_unix.so `remember=N` â€” history stored in /etc/security/opasswd; e.g., remember=13 blocks last 13 passwords.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0364 â€” Find empty-password accounts?
> `awk -F: '($2==""){print}' /etc/shadow`; lock with `passwd -l <account>`; remove `nullok` from PAM configs.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0365 â€” Audit + disable inactive accounts?
> `lastlog -b 90 | tail -n+2 | grep -v 'Never logged in'`; disable: `usermod -L <username>`.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0366 â€” Account lockout via PAM?
> pam_tally2.so: `auth required pam_tally2.so onerr=fail audit silent deny=5` (+ `unlock_time=900`); account line pairs the auth line.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0367 â€” chmod numeric values?
> r=4, w=2, x=1 (0 none). Common: 600 private, 644 owner-write/others-read, 755 owner-all/others-rx, 700 owner-only, 777 no restrictions, 666 all rw.
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0368 â€” chown/chgrp usage?
> `chown user file`; `chown user:group file`; `chgrp groupName file` (group only).
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0369 â€” Find SUID/SGID binaries?
> `find / -perm +4000` (SUID), `find / -perm +2000` (SGID), combined `find / \( -perm -4000 -o -perm -2000 \) -print`; remove with `chmod a-s <file>`.
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0370 â€” Standard permission for /etc/shadow vs /etc/passwd?
> /etc/shadow = 400 (encrypted passwords); /etc/passwd = 644 (account info, no passwords).
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0371 â€” Locate world-writable files?
> `find /dir -xdev -perm +o=w ! \( -type d -perm +o=t \) ! -type l -print`; fix: `chmod o-w file`, `chmod +t /path/to/dir`; prevent: `umask 002`.
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0372 â€” SUID/SGID risk?
> Programs run with owner/group owner privileges; vulnerabilities in SUID/SGID binaries â†’ privilege escalation.
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0373 â€” Disable X Windows at boot?
> Edit /etc/inittab: `id:5:initdefault:` â†’ `id:3:initdefault:`; remove via `yum groupremove "X Window System"`.
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0374 â€” Separate which partition mounts + fstab options?
> /usr, /home, /var, /var/tmp, /tmp (+Apache/FTP roots). Options: noexec (no binaries), nodev (no device files), nosuid (no SUID/SGID).
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0375 â€” Disk quota enable step sequence?
> `sudo apt install quota` â†’ verify quota_v1/v2 module â†’ edit /etc/fstab (usrquota,grpquota) + `mount -o remount /` â†’ `quotacheck -ugm /` â†’ `quotaon -v /` â†’ `edquota -u <user>` â†’ check `quota -vs <user>`.
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0376 â€” Methods to block usb-storage?
> Fake install `install usb-storage /bin/true` in /etc/modprobe.d/block_usb.conf; blacklist in /etc/modprobe.d/blacklist.conf; rename usb-storage.ko â†’ .blacklist; BIOS disable; GRUB `nousb` kernel arg.
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0377 â€” Why remove X11?
> Not needed for dedicated mail/web servers; vulnerabilities can escalate non-root users to higher privilege.
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0378 â€” Kernel hardening via which file + what default?
> /etc/sysctl.conf read at boot by sysctl. Defaults: ip_forward=0, send_redirects=0, accept_redirects=0, source_route=0, rp_filter=1, syncookies=1, log_martians=1, exec-shield=1.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0379 â€” iptables three chains?
> INPUT (incoming vs rule, IP+port), FORWARD (routes incoming to destination), OUTPUT (output allow/deny). Check `iptables -L -n -v`.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0380 â€” UFW basic workflow?
> install â†’ `ufw status verbose` â†’ `ufw enable` â†’ default deny incoming / allow outgoing â†’ add rules by service/port/proto/IP; delete with `ufw delete allow <n>`.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0381 â€” TCP Wrappers allow/deny files + order?
> Only first matching rule considered; TCPD allows via /etc/hosts.allow, denies via /etc/hosts.deny; verify support `ldd $(which sshd) | grep libwrap`.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0382 â€” netstat/ss option meanings?
> -t TCP, -u UDP, -n numeric (no DNS), -l listening only, -p PID+process name â†’ `netstat -tulpn` / `ss -tulpn`; lsof `-nP -iTCP -sTCP:LISTEN`.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0383 â€” How to disable IPv6?
> sysctl.conf disable_ipv6=1 (all/default/lo) or GRUB `ipv6.disable=1` + update-grub; or sysctl -w one-liners.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0384 â€” What can block which? firewall vs TCPD?
> Firewall = network-layer, cannot inspect encrypted connections. TCPD = app-layer ACL â†’ filters even HTTPS; complements firewall, never on firewall host.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0385 â€” Set PermitRootLogin safely?
> Edit /etc/ssh/sshd_config â†’ `PermitRootLogin no` â†’ restart sshd (systemctl/service/init.d). Create sudo-capable user first.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0386 â€” Hardening keys in sshd_config?
> PermitRootLogin no, IgnoreRhosts yes, HostbasedAuthentication no, PermitEmptyPasswords no, X11Forwarding no, MaxAuthTries 5, Ciphers aes128/192/256-ctr, ClientAliveInterval 900.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0387 â€” What is chrooted SFTP and why?
> Locks SFTP users inside their home dir (can't browse others'); steps: mkdir /sftp (root owned), dirs per user, group sftponly, useradd -s /sbin/nologin, chmod 700, sshd_config internal-sftp + Match block.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0388 â€” sshd_config settings for chroot SFTP?
> Comment out Subsystem sftp (path per distro), then add: `Subsystem sftp internal-sftp`, `Match group sftponly`, `ChrootDirectory /sftp/`, `X11Forwarding no`, `AllowTcpForwarding no`, `ForceCommand internal-sftp`.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0389 â€” Verify SFTP jail?
> `sftp alex@<server>` â†’ `sftp>` and `pwd` = `/`. SSH attempt shows "This service allows sftp connections only." Restart `systemctl restart sshd`.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0390 â€” Lynis purpose?
> Open-source security auditing + hardening + compliance testing (PCI/HIPAA/SOX); modular, uses only discovered system components â†’ keeps system clean.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0391 â€” AppArmor vs SELinux?
> Both MAC on LSM. AppArmor: per-program profiles (text in /etc/apparmor.d/), aa-enforce, apparmor_status. SELinux: kernel-level, TE + RBAC + MLS, 3 modes enforcing/permissive/disabled.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0392 â€” SELinux modes?
> enforcing (policy enforced/blocks), permissive (warnings + logs), disabled (no policy). Config /etc/selinux/config SELINUX=; status via sestatus.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0393 â€” SCAP components?
> CVE, CCE, CPE, CVSS, XCCDF, OVAL, OCIL 2.0, Asset Identification, ARF, CCSS, TMSAD â€” XML namespaced standards (NIST).
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0394 â€” OpenSCAP install + basic run?
> Ubuntu `apt-get install libopenscap8`; Fedora `dnf install openscap-scanner`; RHEL/CentOS `yum install openscap-scanner`; OVAL: `oscap oval eval --results ... --report report.html <oval.xml>`.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0395 â€” Name additional hardening tools?
> Bastille Linux, JShielder, nixarmor, bane, Grsecurity (kernel exploit prevention), Comodo Antivirus.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

### Module 07 (59 items)

> [!question]- 0396 â€” The four mobile use approaches in enterprise?
> BYOD (Bring Your Own Device) Â· COPE (Company Owned, Personally Enabled) Â· COBO (Company Owned, Business Only) Â· CYOD (Choose Your Own Device).
> Source: [[07-LO01a-Common-Mobile-Usage-Policies]]

> [!question]- 0397 â€” What three areas do the decision questions cover when choosing a mobile approach?
> Device specific (type, selection, cost, providers) Â· management and support Â· integration and application.
> Source: [[07-LO01a-Common-Mobile-Usage-Policies]]

> [!question]- 0398 â€” BYOD stands for?
> Bring Your Own Device (variants: BYOT â€” own technology, BYOP â€” own phone, BYOPC â€” own PC). Employees bring personal devices to access org resources per access privileges.
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0399 â€” Four BYOD advantages?
> Increased productivity + employee satisfaction Â· work flexibility (mobile + cloud-centric) Â· lower IT costs Â· availability of up-to-date resources.
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0400 â€” BYOD disadvantages?
> Security access issues (lost/stolen data, malware via unsecured Wi-Fi) Â· compatibility issues across platforms Â· scalability (network infrastructure limits).
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0401 â€” The 5-step BYOD implementation flow?
> 1 Define requirements â†’ 2 decide device/data management â†’ 3 develop policies â†’ 4 security â†’ 5 support.
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0402 â€” PIA in BYOD projects?
> Privacy impact assessment â€” performed at project start by the mobile governance committee (end users + IT management); documented procedure for facts, objectives, privacy risks, mitigation.
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0403 â€” CYOD vs COPE ownership?
> CYOD: employee picks from company-approved list, company purchases. COPE: company purchases + owns; personal use enabled. COBO: company-owned, business-only (often single app).
> Source: [[07-LO01c-CYOD-COPE-COBO-Policies]]

> [!question]- 0404 â€” Fastest vs slowest deployment models?
> CYOD: slower than BYOD but quicker than COPE; COPE has the slowest deployment timeframe of the models.
> Source: [[07-LO01c-CYOD-COPE-COBO-Policies]]

> [!question]- 0405 â€” COBO classic example?
> Blackberry devices; also inventory systems with embedded barcode scanners (single-application devices).
> Source: [[07-LO01c-CYOD-COPE-COBO-Policies]]

> [!question]- 0406 â€” COPE containerization purpose?
> Separate professional and personal use of a company-owned device; manage/prohibit data sharing between the two containers.
> Source: [[07-LO01c-CYOD-COPE-COBO-Policies]]

> [!question]- 0407 â€” Four enterprise mobile security risk categories?
> Physical (loss/theft, malicious flashing) Â· network-based (wireless eavesdropping) Â· system-based (vendor vulnerabilities like SwiftKey) Â· application-based (unpatched apps â†’ malware/remote control).
> Source: [[07-LO02a-Enterprise-Mobile-Security-Risks]]

> [!question]- 0408 â€” MITM-risk mitigations for mobile networks?
> WPA2 + secured protocols (IPSec, SSL, SSH, HTTPS, Kerberos) + gateways with content filtering and DLP.
> Source: [[07-LO02a-Enterprise-Mobile-Security-Risks]]

> [!question]- 0409 â€” Name the 10 policy-related mobile risks?
> Unsecured-network sharing Â· data leakage/endpoint Â· improper disposal Â· supporting many devices Â· mixing personal/private data Â· lost/stolen devices Â· lack of awareness Â· bypassing network policy Â· infrastructure issues Â· disgruntled employees.
> Source: [[07-LO02a-Enterprise-Mobile-Security-Risks]]

> [!question]- 0410 â€” Which devices are disallowed under the admin mobile guidelines?
> Jailbroken (iOS) and rooted (Android) devices; also devices with a poor security record.
> Source: [[07-LO02b-Mobile-Usage-Policy-Guidelines]]

> [!question]- 0411 â€” Access gateway authentication methods?
> No authentication Â· Domain only Â· SMS authentication Â· RSA SecurID only Â· Domain + RSA SecurID. Enforce a session timeout.
> Source: [[07-LO02b-Mobile-Usage-Policy-Guidelines]]

> [!question]- 0412 â€” BYOD employee-separation rule on leaving?
> State whether total device wipe or selective wipe of specific apps/data is required; keep organization and personal data maintained separately.
> Source: [[07-LO02b-Mobile-Usage-Policy-Guidelines]]

> [!question]- 0413 â€” MDM in one line?
> Deploy, secure, monitor, and manage company/employee-owned devices via an MDM server management console + MDM agents on the devices.
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0414 â€” MDM delivery methods?
> Premise-based (high control, larger up-front) Â· SaaS-based (no on-site servers, monthly/annual fees) Â· managed services-based (orgs lacking expertise; status reports provided).
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0415 â€” MDM key feature list?
> Security mgmt Â· device config mgmt Â· inventory/tracking Â· OTA app distribution Â· enterprise policy mgmt Â· password enforcement Â· data encryption enforcement Â· network integration Â· remote data wipe Â· blacklisting/whitelisting.
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0416 â€” MDM selection factors (short list)?
> Custom app store Â· application security scanning Â· browser filtering Â· encryption levels Â· selective wipe Â· auto-provisioning Â· architecture (sandbox/virtual/integrated) Â· inventory + reports.
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0417 â€” Example MDM vendors?
> VMware Workspace ONE, IBM MaaS360, XenMobile, Absolute, Sicap DMC, SOTI MobiControl, Scalefusion, ManageEngine, MobileIron, MediaContact, Beachhead SimplySecure, Microsoft Intune.
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0418 â€” MAM in one line?
> Secure, manage, and distribute enterprise applications on mobile devices without interfering with device ownership; separates enterprise apps/data from personal content.
> Source: [[07-LO03b-Mobile-Application-Management-Solutions]]

> [!question]- 0419 â€” Core MAM services?
> App delivery (enterprise app store), licensing, configuration, authorization, usage tracking, lifecycle mgmt, updating, performance monitoring, user auth, crash reporting, access control, version mgmt, push, reporting, usage analytics, event mgmt, app wrapping.
> Source: [[07-LO03b-Mobile-Application-Management-Solutions]]

> [!question]- 0420 â€” Intune MAM configurations?
> Intune MDM + MAM (devices enrolled in Intune MDM) and MAM-WE (MAM without device enrollment).
> Source: [[07-LO03b-Mobile-Application-Management-Solutions]]

> [!question]- 0421 â€” MAM examples?
> Microsoft Intune, MobileIron, App47, Scalefusion (resembles config/example table from courseware).
> Source: [[07-LO03b-Mobile-Application-Management-Solutions]]

> [!question]- 0422 â€” MCM main components?
> File storage + file sharing services; secure access to corporate data via authorized apps; wipe-out for specific users.
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0423 â€” MCM templating approaches?
> Multi-client (different site versions on the same domain) Â· multi-site (mobile sites on a targeted sub-domain).
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0424 â€” What does MTD add beyond MDM/MAM?
> Insights into app characteristics, threat protection, user behavior, dynamic threat reaction, continuous device-health/trust visibility â€” extends EMM/MDM.
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0425 â€” MTD protection levels in the mobile enterprise?
> Device level (OS/config/firmware checks, privilege escalation) Â· network level (traffic monitoring, spoofed certs, TLS/SSL stripping, MITM detection) Â· application level (sandboxing, code analysis, anti-malware signatures, reverse engineering, static/dynamic testing).
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0426 â€” MTD vendor examples?
> MobileIron, Lookout, Wandera.
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0427 â€” MEM purpose + key features?
> Secure corporate email infrastructure/data: preconfigure email remotely Â· only approved apps/devices access mail (S/MIME, SCEP) Â· prevent unauthorized attachment access Â· pre-install the managed email client.
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0428 â€” EMM comprehensive scope formula?
> EMM = MDM + MAM + MTM + MCM + MEM â€” comprehensive solution for safeguarding enterprise data on mobile devices.
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0429 â€” EMM deployment process phases?
> Plan (requirements + stakeholder feedback) â†’ Design (roles, visibility, actors, distribution) â†’ Deploy (cloud vs on-premise, pricing model) â†’ Implement (helpdesk preparation).
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0430 â€” UEM in one line?
> Remote provisioning, management, control, and security of all internet-enabled devices (mobile + desktop) from a single interface; extends MDM and EMM.
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0431 â€” UEM notable capabilities?
> App containerization Â· certificate-based identity Â· per-app VPN Â· DLP (open-in/copy-paste) Â· secure multi-user profiles Â· remote erase Â· API framework.
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0432 â€” UEM examples?
> Scalefusion UEM, Ivanti Unified Endpoint Manager, VMware Workspace ONE UEM (AirWatch-powered).
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0433 â€” Mobile app security best practices (short list)?
> No stored passwords Â· avoid query string Â· code obfuscation/encryption Â· 2FA Â· SSL/TLS Â· no app-data caching Â· input validation Â· secure sessions Â· server-side auth Â· enterprise app store installs Â· containerization Â· jailbreak protection.
> Source: [[07-LO04a-Mobile-App-Data-Network-Security-Best-Practices]]

> [!question]- 0434 â€” Mobile data security practices?
> Encrypt device storage + OTA (SSL/TLS/VPN/WPA2) Â· periodic backup Â· no sensitive data/PINs as contacts Â· private data centers + device auth Â· avoid public Wi-Fi Â· auto-lock Â· timely patches Â· updated AV.
> Source: [[07-LO04a-Mobile-App-Data-Network-Security-Best-Practices]]

> [!question]- 0435 â€” Network guidelines for mobile?
> Disable BT/IR/Wi-Fi when idle Â· Bluetooth non-discoverable Â· encrypted Wi-Fi only Â· no public hotspots Â· secure web accounts Â· segment users via SSIDs/VLANs Â· per-group firewall rules.
> Source: [[07-LO04a-Mobile-App-Data-Network-Security-Best-Practices]]

> [!question]- 0436 â€” Passcode recommendations?
> Strong passcode, max length Â· idle-timeout auto-lock Â· lockout/wipe after attempts Â· eight-character passcodes Â· erase data ON to prevent guessing.
> Source: [[07-LO04b-General-Mobile-Platform-Security-Guidelines]]

> [!question]- 0437 â€” Remote wipe service examples?
> Find My Device (Android) and Find My iPhone / FindMyPhone (iOS); report loss/theft to IT to disable certificates + access methods.
> Source: [[07-LO04b-General-Mobile-Platform-Security-Guidelines]]

> [!question]- 0438 â€” Access gateway authentication methods?
> No authentication Â· Domain only Â· SMS authentication Â· RSA SecurID only Â· Domain + RSA SecurID.
> Source: [[07-LO04b-General-Mobile-Platform-Security-Guidelines]]

> [!question]- 0439 â€” SMS phishing countermeasures (top items)?
> Don't reply without verifying source Â· don't click links Â· don't reply to requests for personal/financial info Â· review bank's SMS policy Â· block texts from the internet Â· never call numbers from SMS Â· avoid non-telephonic numbers.
> Source: [[07-LO04b-General-Mobile-Platform-Security-Guidelines]]

> [!question]- 0440 â€” Android Device Administration API origin + purpose?
> Introduced in Android 2.2; system-level device administration for security-aware enterprise apps; device-admin apps enforce policies (email clients, remote-wipe security apps, device management).
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0441 â€” Key Android Device Admin policies?
> Password enabled Â· min password length Â· alphanumeric/complex password (Android 3.0) Â· password expiration/history Â· max failed attempts (wipe) Â· inactivity lock (1â€“60 min) Â· storage encryption (3.0) Â· disable camera (4.0).
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0442 â€” Which policy wipes the device?
> Maximum failed password attempts â€” device wipes its data after the allowed number of wrong entries; remotely resettable to factory defaults.
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0443 â€” Android hardening top countermeasures?
> Screen locks Â· never root Â· official market only Â· Google Android AV Â· no direct APK downloads Â· OS updates Â· encryption Â· AppLock Â· GPS on Â· remote-erase apps (Lookout, 3cX, SeekDroid) Â· per-app permissions review.
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0444 â€” Settings path for disabling visible passwords/secure credentials?
> Settings â†’ Connections or Settings â†’ More â†’ Security (most Android devices).
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0445 â€” Find My Device prerequisites?
> On Â· signed into Google account Â· mobile-data/Wi-Fi connected Â· visible on Google Play Â· location enabled Â· Find My Device on.
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0446 â€” Find My Device actions?
> Play sound (full volume 5 min) Â· Lock (PIN/pattern/password + message/phone number) Â· Erase (permanent; SD card may survive; service stops working).
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0447 â€” X-Ray function?
> Scans Android device for unpatched (carrier-level) vulnerabilities; lists CVEs with per-vulnerability check; auto-updates for new disclosures.
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0448 â€” Where's My Droid tracking methods?
> Text-message attention word or the online control center "Commander"; features GPS, GPS Flare, SIM-change notification, stealth mode.
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0449 â€” Kaspersky VPN & Antivirus feature set?
> Anti-virus cleaner Â· background check Â· app lock Â· find my phone Â· anti-theft Â· anti-phishing Â· call blocker Â· web filter Â· data leak checker Â· smart home monitor.
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0450 â€” iOS passcode/erase configuration paths?
> Settings â†’ Touch ID and Passcode (Turn Passcode On, Erase Data, Voice Dial OFF); Auto-Lock: Settings â†’ General â†’ Auto-Lock.
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

> [!question]- 0451 â€” Default iPhone root password and the fix?
> Default root password is "Alpine" â€” must be changed. Never jailbreak/root in enterprise environments.
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

> [!question]- 0452 â€” Find My iPhone Lost Mode?
> iOS 6+ feature: locks the device with a passcode + custom message (e.g., contact number); tracks whereabouts and recent location history.
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

> [!question]- 0453 â€” Find My iPhone setup path?
> Settings â†’ [your name] â†’ iCloud â†’ Find My iPhone â†’ turn on Find My iPhone + Send Last Location (iOS 10.2-: Settings â†’ iCloud).
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

> [!question]- 0454 â€” Key iOS hardening items?
> App Store only Â· no sensitive data on client-side DB or iCloud Â· no jailbreak Â· trusted third-party apps Â· ask-to-join Wi-Fi Â· Safari privacy settings + Do Not Track Â· disable BT/Wi-Fi when idle Â· regular Apple patches.
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

### Module 08 (72 items)

> [!question]- 0455 â€” IoT definition in one line?
> Internet of Things (IoT) / Internet of Everything (IoE) â€” web-enabled devices that sense, collect, and send data via embedded sensors, communication hardware, and processors.
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0456 â€” What is a "thing" in IoT?
> A device implanted on natural, man-made, or machine-made objects that can communicate over a network.
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0457 â€” IoT interaction types?
> H2H (human-to-human, without PC), H2T (human-to-things), T2T (things-to-things).
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0458 â€” Four primary IoT technology systems?
> Sensing technology Â· IoT gateways Â· cloud server/data storage Â· remote control via mobile apps.
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0459 â€” IIoT three growth approaches?
> Increased production (revenue) Â· intelligent technology changing how goods are made Â· new hybrid business models.
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0460 â€” Four layers of the IoT architecture (top-down)?
> Device â†’ Communication â†’ Cloud Platform â†’ Process.
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0461 â€” IoT device-layer components?
> Sensors (temp, gyroscope, pressure, light, GPS, electrochemical, RFID) Â· mobile devices Â· microcontroller units Â· networking gear Â· single-board computers.
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0462 â€” Four IoT communication models?
> Device-to-Device Â· Device-to-Cloud Â· Device-to-Gateway Â· Back-end Data-Sharing (cloud-to-cloud).
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0463 â€” Protocols characteristic of device-to-gateway communication?
> ZigBee, Z-Wave (local), IEEE 802.11 (Wi-Fi), IEEE 802.15.4 (LR-WPAN).
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0464 â€” Back-end data-sharing model?
> Extends device-to-cloud: device data is accessed/analyzed later by authorized third parties (HTTPS, OAuth 2.0, JSON).
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0465 â€” Cloud gateway functions?
> Authenticate/authorize devices Â· data compression Â· secure deviceâ†”cloud transfer Â· protocol compatibility gateway.
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0466 â€” Key inherent IoT issues (top 6)?
> No security/privacy Â· vulnerable web interfaces Â· legal/regulatory gaps Â· default/weak/hardcoded credentials Â· cleartext protocols + open ports Â· coding errors (buffer overflow).
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0467 â€” Why are IoT DDoS/cryptojacking effective?
> IoT devices are usually never turned off, and many use default/hardcoded credentials.
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0468 â€” OWASP #1 IoT vulnerability?
> Weak, guessable, or hardcoded passwords.
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0469 â€” DDoS-from-hacked-IoT four phases?
> Identify + take over â†’ reprogram device â†’ activate â†’ launch DDoS.
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0470 â€” Process-layer IoT threat impacts?
> Intellectual property theft, theft, repudiation â†’ lawsuits, reputational damage.
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0471 â€” IoT stack-wise security principle for device layer?
> Tamper detection, encryption at rest, TLS v1.2/1.3, IoT-specific authentication protocols; Zero Trust per-device keys.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0472 â€” Communication edge layer countermeasures?
> Edge firewalls, IPsec ESP, traffic shaping (DNS/ICMP/ARP), out-of-band appliances.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0473 â€” Cloud platform IoT countermeasures?
> SIEM, IDPS, security analytics, federated access / bring-your-own-key.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0474 â€” Example IoT attack scenario target?
> Smart-building CCTV/security system â€” attacker spoofs cameras and AC/humidity sensors, maps the plant, causes damage.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0475 â€” IoT system management components?
> Device management Â· user management Â· security monitoring.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0476 â€” Top IoT device-layer attacks?
> Node tampering, jamming/RF interference, malicious node/tag injection, spoofing, tag cloning, replay, timing/Side-Channel, eavesdropping, hardware trojan, outage.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0477 â€” RFID relay attack countermeasures?
> Timers, challenge-response, distance-bounding protocols.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0478 â€” Bluesnarfing vs BlueBugging?
> Bluesnarfing = gains access to data via OBEX Push; BlueBugging = remote control of device via OBEX Push/FTP (place calls, AT commands).
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0479 â€” Bluetooth KNOB attack?
> Weakens Bluetooth encryption entropy from 8 to 1 byte.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0480 â€” WEP attack tools?
> Korek, Chopchop, Fragmentation, FMS, PTW; Google Replay attack.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0481 â€” Michael attack target?
> TKIP countermeasure flaw â†’ forge fragmented packets (fix: CCMP/AES).
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0482 â€” KillerBee?
> ZigBee exploitation tool suite: zbdump, zbconvert, zbreplay, zbstumbler, zbfind, zbinject.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0483 â€” RPL attacks?
> DOG (denial-of-game), global repair attack, version-number modification, DAO inconsistencies.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0484 â€” IoT cloud-layer attacks?
> Account/theft, data-in-transit compromise, key/cert storage attacks, malware injection, botnets, backdoor/DoS, cloud service interruption.
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0485 â€” IoT data-at-rest encryption standard?
> AES-256 (ex: RSA 2048 + AES-256; TLS 1.2 across web).
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0486 â€” Cloud data-transit countermeasures?
> TLS v1.2, IPsec, DTLS, subnet-firewall ACLs, network redundancy.
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0487 â€” Process-layer IoT counters?
> Governance/policies, audit programs, user training, incident response, continuous improvement.
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0488 â€” Mirai?
> Botnet that exploits default credentials in IoT devices.
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0489 â€” Security measures M01â€“M05?
> Complete visibility â†’ IoT asset maps â†’ behavior monitoring â†’ ecosystem-interface understanding â†’ network segmentation.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0490 â€” Asset discovery tools for IoT (M01)?
> AssetExplorer (ManageEngine), ServiceNow ITSM, Azure IoT Hub, AWS IoT Device Management.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0491 â€” IoT asset map tool (M02)?
> Oracle IoT Asset Monitoring Cloud Service.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0492 â€” IoT behavior monitoring tools (M03)?
> Domotz Pro, TeamViewer IoT, Azure IoT Hub, AWS IoT Device Management.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0493 â€” OWASP #3 â€” insecure ecosystem interfaces?
> Web/mobile/cloud â†’ weak authentication, weak encryption, missing filtering.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0494 â€” Security measures M06â€“M10?
> Limit access (ACL/PACL/VACL) â†’ monitor malware/ransomware â†’ vulnerability scan â†’ firmware updates â†’ close insecure network services.
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0495 â€” PACL vs VACL?
> PACL = Policy-based access control list; VACL = VLAN access control lists.
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0496 â€” IoT malware to monitor (M07)?
> Mirai, Echobot, Torii, Dark Nexus, WannaCry (EternalBlue).
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0497 â€” IoT vuln scanners (M08)?
> RloT Scanner, beSTORM; also Nexpose, Qualys, Tenable, Cloudpassage Halo, AlienVault USM.
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0498 â€” Firmware update best practice (M09)?
> Vet in sandbox, OTA where supported, sign updates, rollback plan.
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0499 â€” Port/service closure command (M10)?
> ```
> sudo nmap -sS -sU -O `<target>` Â· netstat -tulpn Â· nmap --top-ports 1000 `<target>`.```
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0500 â€” Security measures M11â€“M15?
> E2E encryption â†’ E2E security & identity mgmt â†’ strong authentication â†’ chip-level security â†’ hardware security.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0501 â€” E2EE protocols for IoT (M11)?
> TLS v1.2/1.3, IPsec ESP, DTLS, AES-256; no plaintext HTTP/Telnet/MQTT.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0502 â€” IoT identity mgmt (M12)?
> X.509 / mTLS device identity, PKI/private CA, certificate rotation.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0503 â€” Strong authentication for IoT (M13)?
> Unique credentials, MFA/2FA, smartcards/FIDO2, biometrics; per-device secrets.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0504 â€” Chip-level security (M14)?
> Secure SoC, cryptoprocessors, TPM 2.0, protected secure boot, Root of Trust.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0505 â€” Hardware security modules (M15)?
> HSM (key mgmt), Intel SGX / ARM TrustZone secure enclaves, secure elements, tamper-evidence.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0506 â€” Security measures M16â€“M19?
> Secure gateways â†’ secure control server â†’ secure remote administration â†’ router security.
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0507 â€” "Unplug n' Pray" (M18)?
> Physically disconnect an IoT device when it is physically compromised.
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0508 â€” SSH default port?
> Port 22 (use instead of Telnet port 23).
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0509 â€” Router hardening basics for IoT (M19)?
> WPA2/WPA3, disable WPS/UPnP/SNMP, change defaults, disable remote mgmt, zenmap/ShieldsUP scan.
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0510 â€” Control server (M17)?
> Sends commands to IoT devices; protect with MFA, RBAC, audited commands, SIEM, HSM signing.
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0511 â€” Security measures M20â€“M27?
> Wi-Fi isolation â†’ Ethernet isolation â†’ internet-access control â†’ network monitoring â†’ bandwidth monitoring â†’ log centralization â†’ public Wi-Fi security â†’ shadow IoT management.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0512 â€” VLAN port mapping example (M21)?
> X1 = trunk/gateway, X2 = main LAN, X3 = IoT subnet.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0513 â€” Guest-network client isolation tool?
> pcWRT guest network (isolate IoT traffic from LAN).
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0514 â€” Bandwidth monitoring tools (M24)?
> SolarWinds (NPM / NetFlow Traffic Analyzer), Paessler PRTG.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0515 â€” Logarithm centralization (M25)?
> Cloud IoT Core + Stackdriver Logging (GCP); SIEM.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0516 â€” Shadow IoT discovery tool (M27)?
> Shodan â€” Internet-facing IoT devices outside IT control.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0517 â€” IoT device-check best practices?
> Secure boot, change defaults, disable unused services, firmware updates, disable Telnet port 23, monitor port 48101.
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0518 â€” SeaCat.io?
> Open-source mutual-TLS (mTLS) tunnel from Teskalabs; gateway + client for constrained devices.
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0519 â€” SeaCat port?
> 48101 (SeaCat mTLS gateway tunnel), Nginx 443.
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0520 â€” DigiCert IoT?
> Mutually-authenticated TLS for constrained IoT devices + cloud.
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0521 â€” Additional IoT security tools (top 4)?
> PwnPulse Â· Allot Â· Cisco IoT Threat Defense Â· AWS IoT Device Defender (also SecEdge, net-Shield, Noddos, Trustwave, Subex, libsecurity-go).
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0522 â€” AIOTI?
> Alliance for Internet of Things Innovation â€” EU multi-stakeholder platform; 17+2 WGs (WG09 = IoT Privacy/Security).
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

> [!question]- 0523 â€” NIST IAIP for IoT â€” 8 feature areas?
> Asset identification Â· device config Â· data protection Â· logical access Â· firmware updates Â· event monitoring Â· interface access Â· hardening.
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

> [!question]- 0524 â€” DHS IoT strategic principles (6)?
> Security-by-design Â· updates/vuln mgmt Â· recognized security practices Â· prioritize by impact Â· transparency Â· connect carefully.
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

> [!question]- 0525 â€” GSMA IoT security â€” 8 assessment areas?
> Secure boot Â· storage Â· key mgmt Â· OTA updates Â· app isolation Â· DDoS protection Â· user-data privacy Â· attack mitigation.
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

> [!question]- 0526 â€” Common Criteria standard for IoT eval?
> ISO/IEC 15408 â€” EAL 1â€“7 evaluation (FIPS 140-3 = crypto modules).
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

### Module 09 (47 items)

> [!question]- 0527 â€” Whitelisting = ? / philosophy?
> Allow-list control (trust-centric): allow only approved apps, deny by default â†’ blocks everything not whitelisted.
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0528 â€” Whitelisting mitigates which attack class?
> Zero-day attacks (blocks vuln code execution while patches/signatures lag).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0529 â€” Blacklisting = ? / philosophy?
> Deny-list control (threat-centric): block known-bad apps, allow by default (AV, spam filters, IDS/IPS).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0530 â€” Blacklisting's main weakness?
> Cannot stop zero-day attacks and is never comprehensive (unknown theats slip through).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0531 â€” SRP rule types (4)?
> Path Â· Hash Â· Certificate Â· Internet Zone rules (of the default Disallowed level).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0532 â€” Most common whitelisting via SRP â€” two big caveats?
> A Disallowed app can still be run by copying it elsewhere; internet zone rules apply only to .msi.
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0533 â€” AppLocker controls which files?
> Executables, Windows Installer files, and DLLs (default rules = folder paths).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0534 â€” AppLocker rule collections?
> Executable Â· Script Â· Windows Installer Â· Packaged app rules.
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0535 â€” Endpoint Central block methods?
> Path rule (by name/extension) and hash value (blocks even renamed exe); two policies per exe allowed.
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0536 â€” Endpoint Central two blacklisting features?
> Block Executable (targeted block) + Prohibit Software (auto detect/uninstall + approvals + reports).
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0537 â€” PUA PowerShell command?
> Set-MpPreference -PUAProtection 1 (admin; alternatives: Block / AuditMode / Disable / Not configured).
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0538 â€” Turn off Windows Installer options?
> Never (users can install/upgrade) Â· For non-managed apps only (admin-assigned) Â· Always (disables).
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0539 â€” Registry DisallowRun steps (hash)?
> HKCU\...\Policies â†’ key Explorer â†’ DWORD DisallowRun=1 â†’ key DisallowRun â†’ strings 1,2,3 = exe names â†’ restart.
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0540 â€” McAfee Application Control whitelisting modes?
> default-Deny Â· Detect-and-Deny Â· Verify-and-Deny whitelisting.
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0541 â€” Sandboxing definition / goal?
> Run untrusted or untested third-party programs in a sealed container that blocks access to critical system resources; extra layer over host/OS.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0542 â€” Sandbox limitation (important)?
> Not robust against advanced malware targeting the OS kernel.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0543 â€” Two sandbox approaches?
> Isolation-based (program isolated from system). Rule-based (shares resources per policies).
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0544 â€” Windows UAC integrity levels vs sandbox?
> Edge Protected Mode runs low integrity; standard user = medium; elevated admin = high.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0545 â€” Chrome site-isolation flag methods?
> chrome://flags Strict-Origin-Isolation Enabled, or Chrome shortcut Target --site-per-process.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0546 â€” Firefox sandbox preference?
> about:support (Sandbox listing) or about:config security.sandbox.content.level.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0547 â€” Acrobat Protected Mode?
> Security (Enhanced) â†’ Sandbox protections: Protected Mode at startup, AppContainer, Protected View modes.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0548 â€” Windows Sandbox prerequisite?
> Virtualization enabled (Task Manager â†’ Virtualization: Enabled); Windows Sandbox feature via Windows Features.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0549 â€” Firejail mechanism + examples?
> SUID + Linux namespaces + seccomp-bpf; private network stack/process table/mount table; `firejail firefox`, `firejail vlc`.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0550 â€” Sandboxie (Sophos) isolation?
> Blocks malware, viruses, ransomware, zero-day; stops websites from modifying system files/folders.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0551 â€” Shadow Defender behavior?
> Virtualizes drives; rebooting discards changes; Commit Now persists.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0552 â€” WDAG isolates?
> Microsoft Edge â€” blocks access to local storage, memory, installed apps, corporate network endpoints.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0553 â€” WDAG enable command?
> Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0554 â€” WDAG enterprise-mode trusted/neutral config?
> *.microsoft.com (enterprise cloud), bing.com (neutral), then enable Application Guard in Enterprise Mode.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0555 â€” Patch management definition?
> Process of monitoring + deploying new or missing patches to keep applications on hosts secure.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0556 â€” Patch management flow?
> Scan for new/missing â†’ download centrally â†’ select relevant client patch â†’ test â†’ deploy if pass.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0557 â€” Why apply patches urgently?
> Hackers build exploits from each patch's disclosed vulnerabilities; unpatched apps get compromised.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0558 â€” Dashboard (patch status detection) shows?
> Patched + malicious software Â· unrecognized-app flags Â· unknown patch status Â· compliance reports.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0559 â€” Why test before org-wide deploy?
> Ensure patches don't break apps; tests on a few systems â†’ deploy if successful.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0560 â€” SolarWinds Patch Manager features?
> WSUS + SCCM integration, vulnerability mgmt, pre-tested packages, compliance reports, dashboard; patched 3rd-party apps (Adobe, Java, etc.).
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0561 â€” WAF working + layer?
> Rule-based filter before the web app; protects at layer 7 where standard firewalls/IDS-IPS fall short.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0562 â€” Three WAF types?
> Network/hardware-based Â· Host/software-based Â· Cloud-hosted.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0563 â€” Host vs network WAF granularity?
> Host gives more control (single server, any server, no hardware); network covers all apps/network via IP/port but less granular + pricey hardware.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0564 â€” WAF deployment options (5)?
> Reverse proxy Â· Layer-2 bridge Â· Out of band Â· Server resident Â· Internet hosted/cloud.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0565 â€” Out-of-band WAF advantage?
> Least impact (not in-line); copies traffic via monitoring port; avoids false-positive outages.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0566 â€” WAF benefits list?
> Cookie encryption/signature Â· CSRF protection + URL encryption (parameter tampering) Â· data-validation depth-testing Â· compliance (PCI, HIPAA, GDPR).
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0567 â€” WAF limits?
> Not replacement for auth/input filtering Â· can't read DB commands Â· partial session-fixation/anti-automation Â· no false-positive protection Â· needs ongoing management.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0568 â€” URLScan purpose?
> IIS WAF tool filtering HTTP requests; SQL injection + XSS protection; rejects risky requests with HTTP 404.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0569 â€” URLScan reject criteria list?
> Request verb Â· file extension Â· suspicious URL encoding Â· non-ASCII chars Â· specified char sequences Â· specified headers.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0570 â€” NAXSI model?
> Open-source positive-model WAF for Nginx; no signature updates needed, low rule maintenance.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0571 â€” WebKnight placement?
> ISAPI filter for Microsoft IIS; blocks bad requests.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0572 â€” AppWall special coverage?
> Behind-CDN attacks, API manipulation, Slowloris, dynamic floods, brute-force on login pages.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0573 â€” Wallarm scope?
> APIs, microservices, web apps; OWASP API Top 10, API abuse, automated threats, real-time.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

### Module 10 (98 items)

> [!question]- 0574 â€” What are the three states of data?
> Data at rest (inactive, stored) Â· data in use (RAM/CPU/database, actively processed) Â· data in transit (moving across the network).
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0575 â€” Which state does SSL/TLS and email encryption (PGP, S/MIME) protect?
> Data in transit.
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0576 â€” How is business-critical data identified?
> Business impact analysis â†’ identify critical functions/data + dependent processes â†’ evaluate impact of data damage on the business.
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0577 â€” What makes data "secured" (3 provisions)?
> Restrict destruction/modification/disclosure Â· recover lost/modified data after incidents Â· retention + destruction policies.
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0578 â€” Name the 7 data security technologies.
> Access control Â· encryption Â· masking Â· resilience/backup Â· destruction Â· retention Â· hardware-based security.
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0579 â€” Name the logical access control mechanisms.
> Access control lists (ACLs) Â· group policies Â· account restrictions Â· passwords / access tokens.
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0580 â€” How many ACE types exist and under which ACLs?
> 6 â€” 3 generic (access-denied, access-allowed in DACL; system-audit in system ACL) + 3 object-specific variants.
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0581 â€” Linux: how to mount a filesystem with ACL support?
> `mount -t ext3 -o acl [device] [mount]` (install with `yum install acl`; persist via /etc/fstab acl option).
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0582 â€” Linux: how to set a default ACL granting others rx on /Testdir?
> `setfacl -m d:o:rx /Testdir`.
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0583 â€” What does the pam_time rule `Login;*;!Martin;MoTuWeThFr0800-2000` mean?
> All services/tty, user Martin barred except weekdays 08:00â€“20:00.
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0584 â€” Name the 4 categories of data-at-rest encryption.
> Disk Â· file-level Â· removable media Â· database.
> Source: [[10-LO03a-Windows-Disk-Encryption-BitLocker-Device-Encryption-TPM]]

> [!question]- 0585 â€” Which two prereqs does Windows device encryption require?
> TPM + UEFI.
> Source: [[10-LO03a-Windows-Disk-Encryption-BitLocker-Device-Encryption-TPM]]

> [!question]- 0586 â€” How to check TPM status?
> `tpm.msc` â†’ "The TPM is ready for use"; spec version shown.
> Source: [[10-LO03a-Windows-Disk-Encryption-BitLocker-Device-Encryption-TPM]]

> [!question]- 0587 â€” BitLocker cipher support?
> AES-CBC and AES-XTS, 128-bit or 256-bit.
> Source: [[10-LO03a-Windows-Disk-Encryption-BitLocker-Device-Encryption-TPM]]

> [!question]- 0588 â€” FileVault: how to enable and what unlocks it?
> System Preferences â†’ Security & Privacy â†’ FileVault â†’ Turn On; unlock via login password or recovery key.
> Source: [[10-LO03b-OS-Encryption-Linux-Mac-Android-iOS]]

> [!question]- 0589 â€” What algorithm/state set does Android dm-crypt use?
> AES-128-CBC; states Default, PIN, Password, Pattern.
> Source: [[10-LO03b-OS-Encryption-Linux-Mac-Android-iOS]]

> [!question]- 0590 â€” LUKS over plain dm-crypt: key benefits?
> Change password without re-encrypting data; multiple keys; brute-force protection (header + encrypted master key).
> Source: [[10-LO03b-OS-Encryption-Linux-Mac-Android-iOS]]

> [!question]- 0591 â€” Command to encrypt a file / wipe free space with EFS?
> `cipher /e <file>`; `cipher /w:dir` wipes deleted-data area (free-space cleaning).
> Source: [[10-LO03c-File-Level-and-Removable-Media-Encryption]]

> [!question]- 0592 â€” Which Windows editions lack EFS?
> Windows Home (and similar low-tier editions).
> Source: [[10-LO03c-File-Level-and-Removable-Media-Encryption]]

> [!question]- 0593 â€” Two ways Windows guards USB removable media?
> BitLocker To Go (TPM-less password/PIN) + third-party USB encryption.
> Source: [[10-LO03c-File-Level-and-Removable-Media-Encryption]]

> [!question]- 0594 â€” macOS encrypted disk image: default cipher?
> AES-128 (Disk Utility New Image from Folder).
> Source: [[10-LO03c-File-Level-and-Removable-Media-Encryption]]

> [!question]- 0595 â€” TDE: key hierarchy order and default algorithm?
> DEK â†’ certificate â†’ master key; default AES-128 (also AES-192/256, 3DES).
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0596 â€” Which statement turns on TDE for a database?
> `ALTER DATABASE <db> SET ENCRYPTION ON`.
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0597 â€” Always Encrypted randomized vs deterministic?
> Randomized = different ciphertext each time, no equality ops; Deterministic = same ciphertext for same plaintext, enables equality lookups/joins.
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0598 â€” Where are Always Encrypted keys held, and what does the engine see?
> Keys stored client-side (Column Master Key/Column Encryption Key); engine never sees plaintext or keys â†’ protects at rest + in transit.
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0599 â€” Oracle TDE: what can be encrypted and what enables the keystore?
> Specific table columns or entire tablespace; wallet opened via `ALTER SYSTEM SET ENCRYPTION WALLET OPEN`.
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0600 â€” What does the browser verify during the SSL handshake before showing the green padlock?
> Server certificate authenticity â€” Issued To/By, validity, CA signature â€” preventing MITM.
> Source: [[10-LO04a-Browser-WebServer-TLS-Certificates]]

> [!question]- 0601 â€” In Chrome Details tab, which fingerprint types appear on a cert?
> SHA-256 (and MD5/SHA-1 for legacy) fingerprints; public key size (e.g., 2048-bit RSA).
> Source: [[10-LO04a-Browser-WebServer-TLS-Certificates]]

> [!question]- 0602 â€” EV vs standard SSL difference in what the user sees?
> EV â†’ green-bar address bar + organization verified; standard â†’ HTTPS padlock only.
> Source: [[10-LO04a-Browser-WebServer-TLS-Certificates]]

> [!question]- 0603 â€” In the IIS CSR Distinguished Name, what is the common name field filled with?
> Fully-qualified server domain â€” e.g. www.luxurytreats.com.
> Source: [[10-LO04b-IIS-SSL-Certificate-Lifecycle]]

> [!question]- 0604 â€” Default IIS cryptographic service provider for an SSL CSR?
> Microsoft RSA SChannel Cryptographic Provider.
> Source: [[10-LO04b-IIS-SSL-Certificate-Lifecycle]]

> [!question]- 0605 â€” How does IIS bind the cert to a site?
> Site â†’ Bindings â†’ https :443 â†’ select certificate.
> Source: [[10-LO04b-IIS-SSL-Certificate-Lifecycle]]

> [!question]- 0606 â€” How do you move the same cert to an additional web server?
> IIS â†’ Server Certificates â†’ Export to .pfx (with private key + password), then import on the other node and bind.
> Source: [[10-LO04b-IIS-SSL-Certificate-Lifecycle]]

> [!question]- 0607 â€” Which two DB platforms get transport encryption in this subsection?
> MS SQL Server (Force Encryption) and Oracle (Advanced Security SSL).
> Source: [[10-LO04c-Database-Server-Web-Server-Encryption]]

> [!question]- 0608 â€” SQL Server: where is Force Encryption enabled?
> SQL Server Configuration Manager â†’ Protocols for MSSQLSERVER â†’ Flags â†’ Force Encryption = Yes â†’ Apply â†’ restart SQL Server service.
> Source: [[10-LO04c-Database-Server-Web-Server-Encryption]]

> [!question]- 0609 â€” Where is the Outlook "Encrypt contents and attachments for outgoing messages" toggle?
> File â†’ Options â†’ Trust Center â†’ Trust Center Settings â†’ Email Security.
> Source: [[10-LO04d-Email-Encryption]]

> [!question]- 0610 â€” What three cert/algorithm settings does Outlook S/MIME let you change?
> Signing certificate, encryption certificate, hash/encryption algorithms (+ format, send-cert-with-sign).
> Source: [[10-LO04d-Email-Encryption]]

> [!question]- 0611 â€” What must S/MIME recipients have to read encrypted incoming mail?
> Your public certificate (available to them) and their own private key; Exchange publishes certs to GAL.
> Source: [[10-LO04d-Email-Encryption]]

> [!question]- 0612 â€” What is data masking?
> Hiding original data with random characters/other data, minimizing exposure of PII, PHI, PCI card data, IP while keeping a realistic format.
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0613 â€” SDM vs DDM vs on-the-fly masking?
> SDM = mask at rest (DB copy); DDM = mask in transit (role-based, proxy alters SQL); on-the-fly = transform between source and target environments.
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0614 â€” 4 reasons to include masking in data security?
> Nonproduction data protection Â· insider threats Â· third-party sharing Â· regulatory compliance (GDPR).
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0615 â€” Masked card example `2424 6789 4545 3421`?
> `2424 XXXX XXXX 3421` â€” format preserved, key values changed.
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0616 â€” What factors guide data masking type selection?
> Organization size Â· location (cloud vs on-premise) Â· complexity of data to secure.
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0617 â€” Name the 4 data masking types by environment.
> Static (at rest), Dynamic (in transit/role-based), On-the-fly (between environments); plus DB proxies for DDM.
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0618 â€” Three distinguishing masking algorithms for numbers/dates/IQ.
> Number/Date Variance (random %), Date Aging (policy per field), Averaging/Data Generalization (average values).
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0619 â€” What technique replaces card numbers w/ valid-looking but fake numbers?
> Substitution (meets card-provider validation rules).
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0620 â€” Tokenization vs format-preserving encryption?
> Tokenization = unique tokens map back to original (IDs, cards); FPE = encrypts preserving length/character set (phones, cards).
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0621 â€” What does the F.A.S.T. acronym in Oracle data masking mean?
> Find â†’ Access â†’ Secure â†’ Test.
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0622 â€” Which SQL Server DDM mask function masks the entire field per data type?
> `default()` â€” e.g., `alter table employee alter column empname ... masked with (Function='default()')`.
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0623 â€” Primary purposes of a data backup?
> Reinstate a system to its normal working state after damage, or recover data/information following data loss or corruption.
> Source: [[10-LO06a-Backup-Strategy-Basics]]

> [!question]- 0624 â€” Four categories of data-loss causes.
> Human error Â· crimes Â· natural causes (power/software/hardware) Â· natural disaster.
> Source: [[10-LO06a-Backup-Strategy-Basics]]

> [!question]- 0625 â€” 8-step data backup strategy?
> Identify critical data â†’ select backup media â†’ backup technology â†’ RAID levels â†’ backup method â†’ backup types â†’ right solution â†’ recovery drill test.
> Source: [[10-LO06a-Backup-Strategy-Basics]]

> [!question]- 0626 â€” Backup media selection factors?
> Cost, reliability, speed, availability, usability.
> Source: [[10-LO06a-Backup-Strategy-Basics]]

> [!question]- 0627 â€” Which RAID level offers striping with NO fault tolerance?
> RAID 0 (minimum 2 disks).
> Source: [[10-LO06b-RAID-Technology]]

> [!question]- 0628 â€” RAID 50 = what combination, minimum disks?
> Striping across mirrored pairs (RAID 0 over RAID 1); minimum 6 disks.
> Source: [[10-LO06b-RAID-Technology]]

> [!question]- 0629 â€” RAID 3 vs RAID 5 parity placement?
> RAID 3 = dedicated parity disk; RAID 5 = parity distributed across all disks.
> Source: [[10-LO06b-RAID-Technology]]

> [!question]- 0630 â€” Minimum disks for RAID 10?
> 4 (2 mirrored pairs, striped).
> Source: [[10-LO06b-RAID-Technology]]

> [!question]- 0631 â€” NAS = which protocol layer and example file protocols?
> File-level; CIFS/SMB and NFS.
> Source: [[10-LO06c-SAN-and-NAS-Storage]]

> [!question]- 0632 â€” SAN serves data at what level?
> Block-level (Fibre Channel / iSCSI); presented as raw disk to servers.
> Source: [[10-LO06c-SAN-and-NAS-Storage]]

> [!question]- 0633 â€” Typical NAS capacity split high-end/mid-market/low-end?
> Enterprise (TB-scale, clustered) Â· mid-market (~100 TB) Â· desktop/low-end (~8 TB).
> Source: [[10-LO06c-SAN-and-NAS-Storage]]

> [!question]- 0634 â€” Difference between incremental and differential backup?
> Incremental backs up changes since last full OR incremental; differential backs up all changes since the last full backup.
> Source: [[10-LO06d-Backup-Methods-Types-and-Locations]]

> [!question]- 0635 â€” Which type makes the restore longest (needs most media)?
> Incremental restores (must replay full + every incremental since).
> Source: [[10-LO06d-Backup-Methods-Types-and-Locations]]

> [!question]- 0636 â€” What is a snapshot?
> A near-instant point-in-time copy of data used for quick rollback/recovery.
> Source: [[10-LO06d-Backup-Methods-Types-and-Locations]]

> [!question]- 0637 â€” File History frequency range?
> Every 10 minutes up to daily (saved versions browsable by time).
> Source: [[10-LO06e-OS-and-App-Backups-Windows-Linux-Mac]]

> [!question]- 0638 â€” Time Machine retention schedule?
> Hourly (past 24 h), daily (past month), weekly (all remaining history); supports encrypted backups.
> Source: [[10-LO06e-OS-and-App-Backups-Windows-Linux-Mac]]

> [!question]- 0639 â€” Two CLI tools for Linux file backup?
> `tar` (archives) and `rsync` (incremental sync); `dd` for raw block images.
> Source: [[10-LO06e-OS-and-App-Backups-Windows-Linux-Mac]]

> [!question]- 0640 â€” Cold (offline) Oracle backup procedure order.
> SHUTDOWN IMMEDIATE â†’ STARTUP MOUNT â†’ BACKUP DATABASE â†’ ALTER DATABASE OPEN.
> Source: [[10-LO06f-Database-Email-Web-Backups]]

> [!question]- 0641 â€” What is required for a hot backup of Oracle via RMAN?
> ARCHIVELOG mode enabled; use `BACKUP DATABASE PLUS ARCHIVELOG`.
> Source: [[10-LO06f-Database-Email-Web-Backups]]

> [!question]- 0642 â€” What does a full cPanel backup include besides files?
> MySQL databases, email configuration, and related config; plus website files.
> Source: [[10-LO06f-Database-Email-Web-Backups]]

> [!question]- 0643 â€” What is a data retention policy?
> Rules for preserving/maintaining data for operational or regulatory compliance â€” defines retention periods per data type + minimum destruction standards.
> Source: [[10-LO06g-Data-Retention]]

> [!question]- 0644 â€” Name regulatory/legal drivers of data retention named in courseware.
> HIPAA, SOX, IRS, COPPA, EU GDPR.
> Source: [[10-LO06g-Data-Retention]]

> [!question]- 0645 â€” 5 steps to create a data retention policy.
> Build team â†’ identify applicable regulatory compliances â†’ specify included data types â†’ develop policy â†’ inform all employees.
> Source: [[10-LO06g-Data-Retention]]

> [!question]- 0646 â€” 3 best practices for a data retention policy.
> Simple and easy to implement Â· different policies per data type Â· retain customer/user info only as long as necessary Â· move infrequently accessed files to lower-level archive.
> Source: [[10-LO06g-Data-Retention]]

> [!question]- 0647 â€” What is data destruction and its main purpose?
> Destroying stored data into an unreadable form so it can't be accessed/exploited; purpose = restrict unauthorized disclosure via proper disposal/destruction of media.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0648 â€” Name the 4 data destruction techniques.
> Clearing Â· Purging Â· Destroying Â· Disposal.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0649 â€” Clearing protects against which attack? Purging?
> Clearing vs keyboard/simple recovery attacks; purging vs laboratory (signal-processing) attacks.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0650 â€” Degaussing applies to which media and what side-effect?
> Magnetic media only (not optical CD/DVD); typically makes the HDD inoperable and can damage nearby devices.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0651 â€” Shredding requirement for destroyed pieces?
> Pieces no larger than 2 mm.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0652 â€” Sequence for wiping a disk with Windows DiskPart.
> `diskpart` â†’ `list disk` â†’ `select disk 1` â†’ `clean` â†’ `create partition primary` â†’ `select partition 1` â†’ `active` â†’ `format FS=NTFS label=Data quick` â†’ `assign letter=w` â†’ `exit`.
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0653 â€” Why is DBAN unsuitable for full sanitization/audit?
> May not fully sanitize the entire drive, cannot detect/erase SSDs, and provides no certificate of data removal for audits/compliance.
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0654 â€” What are the 3 NIST SP 800-88 sanitization methods?
> Clear (overwrite user-addressable memory) Â· Purge (including SSD-specific vendor commands) Â· Destroy (physical).
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0655 â€” The three passes of DoD 5220.22-M?
> Pass 1 binary zeros â†’ Pass 2 binary ones â†’ Pass 3 random bit pattern (final pass verified).
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0656 â€” PCI DSS requirement for disposed card data?
> Req 9.10 â€” render cardholder data (CHD) unreadable and unrecoverable once no longer needed.
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0657 â€” What is DLP?
> Software products + processes that prevent users from sending confidential corporate data outside the organization.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0658 â€” Name the 3 DLP types and what data phase each protects.
> Endpoint DLP = data in use Â· Network DLP = data in transit Â· Storage DLP = data at rest.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0659 â€” Where is Network DLP typically installed and what does it scan?
> At the network perimeter; scans all data in transit â€” email, social media, SSL, IM across ports/protocols.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0660 â€” What inspection channels does MyDLP (open source) support?
> Web, email, instant messaging, printers, removable storage devices, screenshots.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0661 â€” Key DLP implementation best practice regarding false positives?
> Implement with a minimal base to reduce false positives, then enhance gradually as sensitive data is identified.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0662 â€” Which Microsoft solution provides endpoint DLP and integrates with AIP?
> Windows Information Protection (WIP); Windows Defender ATP evaluates content, Azure Information Protection aggregates labeled files.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0663 â€” What is data integrity?
> Accuracy, consistency, and reliability of data throughout its lifecycle â€” unaltered/trustworthy from creation to deletion.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0664 â€” Name the characteristics of data integrity.
> Complete, Accurate, Safe, Compliance, Consistent, Reliable, Timeliness.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0665 â€” Two main categories of data integrity and the 4 logical sub-types.
> Physical and Logical; logical = entity, referential, domain, user-defined.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0666 â€” Three hash methods named for integrity checking?
> MD5, SHA-256, SHA-3 (checksums/hash functions).
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0667 â€” What additive redundancy detects/corrects errors in memory and storage?
> Error-correcting codes (ECC); parity checks + CRC for transmission/storage error detection.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0668 â€” How does a digital signature verify integrity?
> Sender signs data with private key; recipient verifies with sender's public key; any alteration invalidates the signature.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0669 â€” Integrity-preservation checklist items?
> Validate input Â· validate data Â· remove duplicate data Â· perform regular backups Â· control access (least privilege) Â· prepare audit trail.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0670 â€” Give one countermeasure per physical-integrity threat.
> Error-correcting memory, battery-protected write cache, redundant storage (RAID) for hardware/power/storage threats.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0671 â€” Difference between data security and data integrity?
> Security = protect against unauthorized access/disclosure/modification/destruction (privacy); integrity = data stays unaltered and correct (reliability).
> Source: [[10-LO09-Data-Integrity]]

### Module 11 (207 items)

> [!question]- 0672 â€” ``` / Traditional network management activities, in courseware order?
> Evaluation, selection, procurement, installation, configuration - plus managing security of network devices. _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0673 â€” ``` / Two consequences of protracted procurement cycles in the traditional model?
> Installing a device in a remote location was difficult; combined with purpose-built hardware it gave no adequate flexibility. _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0674 â€” ``` / Dynamic requirements the traditional network paradigm could not fulfill?
> Provisioning and de-provisioning of infrastructure such as servers, security policy modification, and performance monitoring. _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0675 â€” ``` / Which virtualization-enabled network technologies do organizations transition to?
> Software-defined networking (SDN) and network function virtualization (NFV). _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0676 â€” ``` / Application classes driving dynamic throughput demand?
> Commerce, media, voice, mobile and IoT applications - alongside geographic expansion. _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0677 â€” ``` / Seven benefits the courseware claims for virtualization-enabled technologies?
> Greater flexibility; centralized control of organizational resources; fine granularity in policy enforcement; protection of data and applications; security of resources; improved management of processing demands with network automation; enhanced network efficiency. _(Mod 11 p6)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0678 â€” ``` / List the ten risks the courseware associates with virtual environments.
> VM sprawling; sensitive data within a VM; security of offline and dormant VMs; security of pre-configured/active VMs; lack of visibility and control over virtual networks; resource exhaustion; hypervisor security; account or service hijacking; workloads of different trust levels on the same server; cloud service provider APIs. _(Mod 11 p7-p8)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0679 â€” ``` / Why can one breach in a virtualized environment spread beyond the VM?
> Multiple virtualized environments may be physically collocated in a single host and each environment's isolation is software-based - so a breach can wreak havoc across the entire targeted host, possibly outside the virtual environment. _(Mod 11 p7)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0680 â€” ``` / VM sprawling - courseware definition and consequence?
> VMs are easily created, so their number can rise to a point the administrator can no longer manage them effectively; it can increase the number of unpatched VMs in the network environment. _(Mod 11 p7)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0681 â€” ``` / Why are offline and dormant VMs dangerous?
> They may lag behind the baseline security of the environment and, if started, can serve as potential entry points for breaches. _(Mod 11 p8)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0682 â€” ``` / Hypervisor security risk - what and why it matters?
> Unauthorized access to the hypervisor can change the security of a device or server on it, so the hypervisor is potentially a single point of failure for the VMs on the host. _(Mod 11 p8)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0683 â€” ``` / Account or service hijacking vector in a virtual environment?
> The virtual environment and hypervisor are often accessed through a self-service portal; compromise of an account on that portal has significant security consequences. _(Mod 11 p8)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0684 â€” Courseware definition of virtualization
> Software-based **virtual representation** of an IT infrastructure (network, devices, applications, storage, etc.); the framework divides physical resources into multiple individual simulated environments.
> Source: [[11-LO02a-Virtualization-Fundamentals]]

> [!question]- 0685 â€” Who converts commands to binary instructions in full virtualization?
> The **VMM** â€” it translates the guest's commands to binary instructions and forwards them to the host OS; resources reach the guest through the VMM.
> Source: [[11-LO02a-Virtualization-Fundamentals]]

> [!question]- 0686 â€” In the virtualization architecture, who interacts with the hardware directly?
> The **host OS**. The **guest OSes interact through the virtualization layer**, which acts as middleware and logically partitions hardware resources.
> Source: [[11-LO02a-Virtualization-Fundamentals]]

> [!question]- 0687 â€” Cardinality rule for virtual vs physical resources
> N virtual resources may be created from **one** physical resource, **or** one virtual resource from **one or more** physical resources.
> Source: [[11-LO02a-Virtualization-Fundamentals]]

> [!question]- 0688 â€” Full virtualization â€” guest awareness, request path, translator
> Guest is **unaware**; guest â†’ **VMM** â†’ host OS; the **VMM** translates to binary and forwards, and allocates resources to the guest.
> Source: [[11-LO02b-Virtualization-Approaches]]

> [!question]- 0689 â€” OS-assisted / para virtualization â€” who translates, and is the VMM involved?
> The **guest OS** translates its own commands to binary for the hardware; the **VMM is not involved** in the request and response operations.
> Source: [[11-LO02b-Virtualization-Approaches]]

> [!question]- 0690 â€” Hardware-assisted virtualization â€” what enables it?
> **Special instructions in modern microprocessor architectures** let the guest OS execute privileged instructions directly on the processor; the OS treats system calls as user programs.
> Source: [[11-LO02b-Virtualization-Approaches]]

> [!question]- 0691 â€” Hybrid virtualization â€” what does the guest use, and what does the VMM still do?
> The guest **adopts para-virtualization functionality**; the **VMM is still used for binary translation** to different types of hardware resources.
> Source: [[11-LO02b-Virtualization-Approaches]]

> [!question]- 0692 â€” Levels of virtualization â€” list the four
> **Storage Device** (striping/mirroring; RAID) Â· **File System** Â· **Server** (partition of the server OS environment / hard drive) Â· **Fabric** (virtual devices independent of physical hardware; SAN).
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0693 â€” Which technologies achieve fabric-level virtualization, and what do they create?
> **SAN** (storage area network); a **massive pool of storage areas** for the different VMs on the hardware, with virtual devices independent of the physical computer hardware.
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0694 â€” Types of virtualization â€” list the four
> **Operating System** Â· **Network** Â· **Server** Â· **Desktop**.
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0695 â€” Network virtualization â€” the two directions
> Multiple physical networks **combined into a single software-based virtual network**, **or** a single physical network **divided into multiple independent virtual networks**. Both are an abstraction of network resources.
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0696 â€” Desktop virtualization â€” where does the desktop and the data live?
> The desktop OS instance lives in a **central server on the cloud** (hosted on a remote central server, possibly a cluster) and is accessed from **any device**; the data and files are **not stored on the user's system** but in the cloud.
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0697 â€” Virtualization components â€” list the seven
> Hypervisor / VMM Â· Guest machine Â· Host / physical machine Â· Management Server Â· Management Console Â· Network Components Â· Virtual Storage.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0698 â€” Which two components decouple the control and forwarding planes?
> **Software Defined Network (SDN)** and **Network Function Virtualization (NFV)** â€” not NV.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0699 â€” What do SDN and NFV combine, and what does that produce?
> They **combine hardware and software** to create a **completely software-defined network** â†’ simpler provisioning and management of network resources.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0700 â€” Enablers â€” how do the virtual networks relate to the physical network and to virtual environments?
> They are **decoupled from the underlying network hardware**, **integrate with virtual environments**, and can **run independently over a physical network in a hypervisor**.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0701 â€” What does virtual storage do, and what is an example network component?
> Virtual storage **abstracts physical storage into a single storage device** so the systems on the host can share it. Network components include **firewalls, load balancers, storage, switches, network interface cards**.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0702 â€” ``` / What single administrative unit is at the heart of the courseware NV definition?
> NV = combining all available network resources and sharing them among network users under a single administrative unit; hardware-allocated resources are abstracted into software. _(Mod 11 p17â€“p18)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0703 â€” ``` / How does NV handle the available bandwidth?
> It splits it into independent channels, assigned or reassigned to a particular server or device in real time. _(Mod 11 p18)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0704 â€” ``` / What does the "Benefits of Network Virtualization" side panel list?
> Efficient, flexible, scalable usage Â· logically segregates underlay administrative from overlay domain Â· automates network and security protocols Â· security by resource isolation Â· enhanced application delivery and reduced overall cost. _(Mod 11 p18)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0705 â€” ``` / What are the building blocks of a virtual network in an NVE?
> A collection of virtual nodes and virtual links â€” a subset of the underlying physical network resources. _(Mod 11 p19)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0706 â€” ``` / Name the five virtual-network examples listed by the courseware.
> VLAN Â· virtual service network (VSN) Â· virtual private network (VPN) Â· active and programmable networks Â· overlay networks. _(Mod 11 p19)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0707 â€” ``` / What determines whether virtual network software goes inside or outside the virtual server?
> The size and type of the virtualization platform. Software placed inside = Internal Virtual Network; outside = External Virtual Network. _(Mod 11 p19, p20)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0708 â€” ``` / Which component acts as the virtual network software for an internal virtual network?
> The hypervisor â€” it provides the abstraction layer that lets internal virtual network types mimic physical networks, and implements virtualization at the server or cluster level. _(Mod 11 p21)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0709 â€” ``` / What hardware/software relationship makes external network virtualization possible?
> Managed/intelligent (layer 3) switches run virtualization software modules that abstract the physical switch ports and the surrounding network. _(Mod 11 p25)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0710 â€” ``` / Which virtualization type combines multiple physical LANs into one, or subdivides one physical LAN into isolated virtual networks?
> External network virtualization (e.g. VLAN + switch technology). _(Mod 11 p25)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0711 â€” ``` / Which hypervisor products does the courseware list, and what licence is VirtualBox under?
> VMware ESXi, Citrix Hypervisor 8.2 (formerly XenServer), Virtual Iron, Microsoft Hyper-V Server, VirtualBox â€” VirtualBox is free open source under GPL version 2. _(Mod 11 p22â€“p23)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0712 â€” ``` / How does VMware ESX Server 3 start up, and which component runs as the first VM?
> The vmkernel starts first and loads the virtualization components; the service console invokes the Linux kernel as the primary VM and runs as the first virtual machine. Type-I, bare metal. _(Mod 11 p24)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0713 â€” ``` / Name the three threat classes the courseware uses to classify hypervisor/VMM vulnerabilities.
> Disclosure, Deception, Disruption. _(Mod 11 p30)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0714 â€” ``` / Which hypervisor security features do its vulnerabilities attach to, and what else is affected besides the hypervisor itself?
> VM isolation and the internal software-based channels used to communicate with VMs; the weaknesses also affect VMMs and their management tools. _(Mod 11 p30)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0715 â€” ``` / Give the Xen example of improper input validation in the hypervisor and its impact.
> The intercept function in a software library uses an improper range â†’ local HVM guests read data from the hypervisor or other guest machines; can also cause DoS or crash the host. _(Mod 11 p30)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0716 â€” ``` / What is an off-by-one error in the hypervisor's data handling, and what does it expose?
> An iterative loop iterates too many or too few times â†’ local users obtain sensitive information from hypervisor memory; can also cause DoS or crash of the host. _(Mod 11 p30)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0717 â€” ``` / Define VM escape per the courseware and list its consequences.
> Attackers run code on a VM to directly communicate with the hypervisor, exploiting hypervisor coding or management errors â†’ DoS, out-of-bounds writes, guest crash, and execution of arbitrary code. _(Mod 11 p31)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0718 â€” ``` / How does injection in hypervisor software libraries hurt, and what address type is named?
> Local guest users cause DoS and crash the host via a non-canonical guest address. _(Mod 11 p31)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0719 â€” List the four threat classes the courseware uses to classify virtual network vulnerabilities.
> Disclosure, Deception, Disruption, Usurpation. _(Mod 11 p32)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0720 â€” Insufficient verification of data authenticity in a virtual network: what does it produce?
> Misbehaving virtual routers repeatedly resend old control messages (reply attacks), corrupting the data plane and causing DoS. _(Mod 11 p32â€“p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0721 â€” Why does rollback of networking activity logs stored in a VM matter (Deception)?
> It causes the loss of network entity activities and subsequently impacts the non-repudiation of actions. _(Mod 11 p32â€“p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0722 â€” Improper validation in a virtual network: how is the DoS produced?
> Incorrect throwing of exceptions when handling malformed, truncated, or maliciously crafted packets. _(Mod 11 p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0723 â€” Usurpation: give the three weakness and effect pairs.
> Injection -> privilege escalation; privileges and permissions -> controlling virtual network nodes like virtual routers; credentials management -> brute-force password guessing against the network management console. _(Mod 11 p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0724 â€” Which weakness sits under both Deception and Usurpation, and how do the effects differ?
> Injection. Deception: messages made to look as if from a legitimate entity -> identity fraud. Usurpation: messages from a fake source with high privileges -> privilege escalation. _(Mod 11 p32â€“p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0725 â€” MAC flooding: mechanism and effect.
> The attacker sends a large number of fake MAC addresses to overflow the CAM table; once it is full, traffic without MAC entries floods out to all ports of the VLAN, making it easy to view and retrieve the traffic. _(Mod 11 p34â€“p35)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0726 â€” ARP attack: mechanism and the two stated effects.
> Fake ARP messages over the LAN bind the attacker's MAC to the IP of a legitimate host and poison the ARP table; it tricks the switch into forwarding packets with forged identities to a device in a different VLAN, and in the same VLAN it tricks end nodes such as routers and workstations. _(Mod 11 p34â€“p35)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0727 â€” Give the mechanism and effect of the DHCP starvation and multicast brute-force attacks.
> DHCP starvation: multiple DHCP requests with spoofed MAC addresses cause DoS at the DHCP server. Multicast brute-force: several multicast frames injected into a VLAN in quick succession leak frames from the original VLAN to other VLANs. _(Mod 11 p35â€“p36)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0728 â€” Double tagging: how are the two 802.1Q tags arranged and what follows?
> The inner tag is the VLAN the user wants to reach, the outer tag is the native VLAN; the switch removes the native VLAN and forwards the second frame to the trunk interface(s), so the attacker jumps from native VLAN to user VLAN and can conduct a DoS attack. _(Mod 11 p35)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0729 â€” Switch spoofing: what does the attacker exploit and what does it emulate?
> The default 'dynamic auto' or 'dynamic desirable' port mode plus an incorrectly configured trunk port to spoof itself as a switch; it then emulates 802.1Q and DTP messages. _(Mod 11 p35â€“p36)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0730 â€” Spanning-tree attack: the two variants and their outcomes.
> After obtaining the port ID information, send STP configuration/topology change acknowledgement BPDUs claiming to be the new root bridge with lower priority to gain access to network traffic; or install a new STP device and transmit junk data to flood packets and shut services down for a short period. _(Mod 11 p36)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0731 â€” Front: Inconsistent time between Hyper-V guests and the host causes what failures?
> Authentication failures, and it affects security protocols such as Kerberos, certificate-dependent technologies that rely on time synchronization, and billing processes. Time sync also provides security and event correlation. _(Mod 11 p37, p39)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0732 â€” Front: How is time synchronization enabled in Hyper-V?
> Windows start menu â†’ Hyper-V Manager â†’ select the VM â†’ right-click â†’ Settings â†’ Management section â†’ Integration Services â†’ check Time synchronization â†’ Apply â†’ OK. _(Mod 11 p39â€“p41)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0733 â€” Front: Besides controlling user access, what does setting Hyper-V access privileges achieve?
> It reduces the attack surface area, preventing damage from external and internal attacks. By default Hyper-V provides a group of admins with all administrative rights for the VMs. _(Mod 11 p41)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0734 â€” Front: Set-SmbServerConfiguration: which -MaxChannelPerSession value is paired with -Force?
> 32 with -Force; 16 is the variant that prompts for confirmation. _(Mod 11 p39)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0735 â€” Front: Name the three VMware hypervisor security measures.
> Time synchronization Â· Restrict user access Â· Encrypting guest virtual machines. _(Mod 11 p51â€“p52)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0736 â€” Front: Which two Windows services must be disabled on Windows Server 2016, and what else alongside them?
> Xbox Live Auth Manager and Xbox Live Game Save â€” plus their respective scheduled tasks. _(Mod 11 p46)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0737 â€” Front: Isolated User Mode: what is it and which two Windows virtualization-security siblings share its role?
> A virtualization-based security feature using secure kernels, separating business data/processes from the OS. Siblings: Credential Guard and Device Guard. Stops pass-the-hash attacks. _(Mod 11 p48)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0738 â€” Front: How is the VMware decryption password related to the VM password?
> They need not be the same. _(Mod 11 p52â€“p53)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0739 â€” Front: Which CVE IDs make disabling hyperthreading mandatory on affected hosts?
> CVE-2018-12126 and CVE-2018-12127. _(Mod 11 p56)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0740 â€” Front: What is the stated trade-off of disabling nested paging in VirtualBox?
> It makes AVX, XSVAE and POPCNT unavailable to guests, causing stability issues (especially during SMP configuration). _(Mod 11 p56)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0741 â€” Front: List the four virtual-network recommendations that concern identity, standards, data and accountability.
> Assure a robust identity Â· Ensure security on open standards Â· Protect operational reference data Â· Provide accountability and traceability. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0742 â€” Front: Which recommendation covers data in transit between hosts and clients?
> Use cryptographic controls like SSL encryption on the network traffic between the hosts and the clients. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0743 â€” Front: How do the recommendations counter MAC spoofing?
> Enable MAC address filtering on the switches. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0744 â€” Front: What physical-layer recommendation prevents unauthorized device connections?
> Disconnect network interface controllers (NIC) to prevent outsiders from connecting to the network easily. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0745 â€” Front: Name the four network-architecture recommendations.
> Use segregation in networks Â· clearly define security dependencies and trust boundaries Â· make systems secure by default Â· provide manageable security controls. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0746 â€” Front: Port security: two limitations/conditions the courseware states.
> It also protects against DHCP starvation attacks, and it works only for access ports - not for trunk ports. _(Mod 11 p60)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0747 â€” Front: How does 802.1X port-based authentication work once configured?
> The AAA server explicitly installs packet filtering rules based on dynamically learned information about users and MAC addresses. _(Mod 11 p60)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0748 â€” Front: What makes VLAN hopping possible, per the courseware?
> The ports of some switches automatically turn into trunks when they receive DTP frames. _(Mod 11 p61)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0749 â€” Front: Match the STP countermeasure to the problem: BPDU Filter vs Loop Guard and UDLD.
> BPDU Filter disables STP on selected ports by stopping BPDU send/receive; Loop Guard and UDLD prevent bridging loops caused by unidirectional links. _(Mod 11 p61)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0750 â€” Front: Two countermeasures against double tagging / native-VLAN abuse.
> Disable trunking on non-trunk ports and disable DTP on ports that may become trunks; never send user traffic on the native VLAN. _(Mod 11 p60â€“p61)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0751 â€” Front: ARPWatch: what does it do and what is the caveat on static ARP tables?
> It tracks IP/MAC pairing and checks forwarded ARP packets for identity correctness. Static entries only stop an adversary ARP response if the table holds correct MAC/IP pairs. _(Mod 11 p60â€“p61)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0752 â€” SDN definition â€” control plane vs forwarding
> Network virtualization approach that centralizes the network controller by separating the network's control functions from its packet forwarding functions
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0753 â€” Three SDN architecture layers
> SDN Application layer Â· SDN Controller Â· SDN Networking Devices
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0754 â€” SDN conceptual components (6)
> Data Plane Â· Control Plane Â· Application Plane Â· Northbound API Â· Southbound API Â· OpenFlow
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0755 â€” Which SDN benefit delivers voice-over-IP / multimedia QoS?
> Implements quality of service (QoS) for voice over IP and multimedia transmissions, by controlling data traffic
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0756 â€” SDN vs traditional control architecture
> Traditional = distributed control architecture with only low-level awareness of network state. SDN = logically centralized network topologies enabling intelligent control and management of network resources
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0757 â€” SDN "Openness" benefit â€” which application classes do the open APIs support?
> OSS/BSS, SaaS, cloud orchestration, and business-related applications
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0758 â€” SDN data plane â€” the three major attacks
> Device Attack (SDN switch software/hardware vulns: firmware, TCAM) Â· Protocol Attack (network protocol vulns of the forwarding device) Â· Side Channel Attack (deduce forwarding policy from performance metrics)
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0759 â€” SDN control plane â€” the three major attacks
> Manipulation Attack (controller's understanding of the data plane) Â· Availability Attack (e.g. numerous unauthenticated packet-in messages) Â· Software Hack (commodity server; e.g. altering a system variable like time)
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0760 â€” SDN southbound API â€” the three major attack types
> Interception Attacks (modify exchanged messages) Â· Eavesdropping Attacks (info between control and data plane) Â· Availability Attacks (numerous requests fail network policy implementation)
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0761 â€” Why is a compromised northbound API worse than a compromised southbound API?
> The data exchanged between application plane and control plane affects network policies, so impact is potentially higher; also OpenFlow standardises the southbound API whereas the northbound API has no standard
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0762 â€” SDN application plane â€” policy attacks
> Storage Attack Â· Control Message Attack Â· Resource Attack Â· Access Control Attacks
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0763 â€” SDN security limitation per layer (p67 figure)
> Data Plane: insecure implementation of the management application. Control Plane: potential for compromise of the control of network flow. Application Plane: no proper authentication mechanism for the application to access the control plane
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0764 â€” Data plane â€” which protocol versions replace the insecure ones?
> SNMPv3 instead of SNMPv2c; secured shell (SSH) instead of telnet; TLS 1.2 (or UDP/DTLS) between network device agent and controller
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0765 â€” Data plane â€” anti-replay and tunnel options
> Use protocols within TLS sessions Â· use shared secret passwords or use nonce to avoid replay attacks Â· use passwords and shared-secrets to authenticate tunnel endpoints and secure tunneled traffic with the DCI protocol in use
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0766 â€” Controller layer â€” the five measures
> Secure + authenticated administrator access Â· RBAC policies Â· logging and audit trails Â· HA controller architecture if DoS risk exists Â· avoid SDN systems with redundant controllers
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0767 â€” Which two techniques protect the tunnel / control path?
> Authorize tunnel endpoints and protect tunneled traffic using data center interconnect (DCI) protocols; separate control protocol traffic from primary data flows through an out-of-band (OOB) network
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0768 â€” FlowChecker â€” what does it do?
> Validates flows in network device tables against controller policy, identifying malicious traffic and discrepancies caused by an attack
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0769 â€” Why avoid SDN systems with redundant controllers?
> It may enable an attacker to cause DoS in all the controllers in the SDN system, while leaving the attacker undetected
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0770 â€” Courseware definition of NFV
> A network virtualization approach that **decouples network functions from proprietary hardware appliances** so they run as software on standardized hardware / in virtual resources. Decoupled functions named: firewalls, traffic control, virtual routing. Benefit: minimizes OPEX and CAPEX, enables easy deployment of new services.
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0771 â€” Three principal elements of the NFV architecture
> **NFVI** (infrastructure) Â· **VNFs** (virtualized network functions) Â· **NFV MANO** (management and orchestration).
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0772 â€” Three subparts of NFVI
> **Hardware resources** (network devices, servers, storage) Â· **Virtualization layer** (contains the hypervisor) Â· **Virtual resources** (virtual networks, virtual storages, virtual servers).
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0773 â€” EMS: what does it manage and over what kind of interface?
> Accounting, configuration, performance and security management of a VNF, over a **proprietary interface**; a single EMS can manage **multiple VNFs**.
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0774 â€” MANO's three components and their jobs
> **VIM** â€” control/manage communication from the VNF to computing, storage and network resources plus virtualization Â· **VNF Manager** â€” life-cycle actions: updates, query, installation, termination, scale-up/down Â· **Orchestrator** â€” controls orchestration, manages software resources and NFV infrastructure.
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0775 â€” How is a VNF deployed onto VMs, and how does MANO reach the operator's OSS/BSS?
> A VNF can run on **multiple VMs** (one function per VM) or **entirely on a single VM**. MANO combines with the decoupled **OSS/BSS** using **standard interfaces**.
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0776 â€” NFVI: list its vulnerabilities and its attack types
> Vulnerabilities: **shared resources Â· insecure interfaces Â· improper control and monitoring Â· design flaws Â· improper security enforcements**. Attacks: **conventional (DoS/DDoS) Â· manipulation of VM OS Â· data destruction Â· hypervisor-level attacks Â· hardware attacks**.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0777 â€” MANO: what does the adversary do, and what are the MANO vulnerabilities and attacks?
> Eavesdrops or modifies communications **inside MANO** and **between NFVI and MANO**. Vulnerabilities: inconsistent orchestration and management, insecure interfaces, data theft, compromised policies, isolation. Attacks: conventional, orchestration and control plane â€” targeting the **orchestrator or VNF manager**.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0778 â€” Why can a VNF be a source of attack, and what are its vulnerabilities?
> It is a **vendor-provided software component** â€” it can carry software vulnerabilities or **may even be malware designed to execute an attack**. Vulnerabilities: software crashes, software design flaws, software bugs. At-risk: shared resources, third party networks, other tenants on the server.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0779 â€” What can malicious NaaS providers do, and how is it mitigated?
> **DoS attacks and extraction of secret information** (RFA / resource consumption attacks). The **hypervisor** must detect **excessive resource consumption** and **malicious virtual networks**.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0780 â€” Side-channel example and mitigation
> An attacker VM **extracts a private ElGamal decryption key** from a **co-resident victim VM running GnuPG**. Mitigation: **hide access management from the VNFs**.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0781 â€” Mitigation for a compromised live migration
> Use a **virtual trusted platform module (vTPM)** that **uses the TLS protocol** to provide confidentiality and authentication.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0782 â€” NFV infrastructure security by domain
> **Hypervisor** â€” authentication controlled/managed by the VMs (prevents unauthorized access, data leaks) Â· **Compute** â€” encrypt data, accessible only by the VNFs sharing the resources Â· **Network** â€” TLS, IPSec, SSH.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0783 â€” MANO: how should the security mechanisms be delivered, and where are they deployed?
> **Automated and agile** for all NFV MANO functions, enabling **quick deployment at different security policy enforcement points (PEPs)**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0784 â€” Why is controller availability a MANO priority?
> The controller is the **centralized decision point**; if compromised it causes a **wide network impact**, so its access must be **stringently monitored and controlled**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0785 â€” Orchestrator attack: what does the adversary do and what mitigates it?
> It **instantiates a modified VNF**, breaking **access privileges and VNF isolation**. Mitigations: **predefine user authentication, user privilege control, network configuration**; **security monitoring system to detect and separate the defective VNF**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0786 â€” What is sVirt, and which two tools harden the Linux kernel?
> **sVirt** = a **new form of SELinux** that **separates VM processes and data files** and safeguards **Linux-based hypervisors**. Tools: **`hidepid`** and **`GRSecurity`**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0787 â€” NFV best practice: TPM, launch control policy, security zoning
> Use a **TPM as a hardware basis of trust**; its **launch control policy (LCP)** requires **validation of platform measurements**. Zoning: **separate VM from management traffic**, group same-function VMs into **isolated zones**, protect each zone with **access control policies and firewalls such as a DMZ**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0788 â€” OS virtualization (Module 11 LO06) â€” what is replicated, and what are the instances called?
> The **host operating system's kernel is virtually replicated in multiple instances of isolated user space**, called **containers**, **software containers**, or **virtualization engines** â€” each instance gets (virtualized) OS functionality.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0789 â€” CaaS â€” what is it, and what can a subscriber build with it?
> Services that enable the **deployment of containers and container management through orchestrators**. Subscribers can develop **rich, scalable containerized applications through the cloud or on-site data centers**.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0790 â€” Container engine vs container orchestration â€” define each.
> **Container engine** = managed environment for deploying containerized applications; creates, adds, and removes containers. **Container orchestration** = **automated process of managing the lifecycles of software containers and their dynamic environment**.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0791 â€” Orchestrators named by the courseware â€” which are open source, which is commercial?
> **Open source:** Kubernetes, Docker Swarm. **Commercial:** **OpenShift by Red Hat**.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0792 â€” OS containers vs application containers â€” definition and examples.
> **OS containers** = virtual environments **sharing the kernel of the host**; run multiple services/processes; install libraries, databases. Examples: LXC, OpenVZ, Linux Vserver, BSD Jails, Solaris Zones. **Application containers** = run a **single application/service**, layered file system, built on OS container tech. Examples: Docker, Rocket.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0793 â€” Container technology architecture â€” the five tiers in order.
> **Developer** creates images â†’ **testing/accreditation systems** validate, verify, sign â†’ **registry** stores and distributes images on request from an orchestrator â†’ **orchestrator** converts images to containers and deploys to hosts â†’ **host** runs and stops containers on the orchestrator's direction.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0794 â€” Container vs virtual machine â€” the four differentiators that are stated consistently.
> **Weight** lightweight vs heavyweight Â· **Virtualization** OS-level vs hardware-level Â· **Memory** less vs more Â· **Start-up** milliseconds vs minutes. Plus: container **shares the host OS**, VM **has its own OS**.
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0795 â€” Table 11.2 (p93) â€” what security/isolation does the *table* assign to a container and to a VM?
> Container = **process-level isolation (less secure)**. VM = **fully isolated (more secure)**. (Note: the figure on the same page states the reverse â€” the courseware is self-contradictory here.)
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0796 â€” Container vs virtual machine â€” start-up time and memory footprint.
> Container: start-up in **milliseconds**, **requires less memory space**. Virtual machine: start-up in **minutes**, **requires more memory space**.
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0797 â€” Which products does the courseware give as container and VM examples (p93)?
> Containers: **LXC, LXD, CGManager, Docker**. Virtual machines: **VMware, Hyper-V, vSphere, Virtual Box** (Table 11.2 lists the same four).
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0798 â€” Container stack, bottom to top (Fig. p93).
> **Infrastructure > Host Operating System > Container Engine (Docker) > Containers > Bins/Libs** â€” note there is no Guest OS layer; the VM stack inserts **Virtual Machines > Guest OS**.
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0799 â€” Docker client â†” daemon â€” how do they talk, and where can each run?
> The client interacts with the daemon using the **REST API through Unix sockets or a network interface**. Client and daemon can run on the same system, or the client can connect to a **remote** Docker daemon.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0800 â€” CNM â€” what are the three objects the courseware itemizes, and what is each for?
> **Sandbox** = the container's network stack (routing table, interfaces, DNS; multiple endpoints). **Endpoint** = joins a sandbox to a network and abstracts the actual connection from the application. **Network** = a collection of endpoints with connectivity between them.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0801 â€” Docker native network drivers â€” list them and the host-bridge one.
> **Host, Bridge, Overlay, MACVLAN, None**. The **bridge** driver creates a **Linux bridge on the host, managed by the Docker**.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0802 â€” What do the Host, Overlay, MACVLAN and None drivers do (p97)?
> **Host** = container uses the host networking stack Â· **Overlay** = container-to-container communication over the physical network infrastructure Â· **MACVLAN** = connection between container interfaces and the parent host interface (or sub-interfaces) Â· **None** = container implements its own networking stack, isolated from the host networking stack.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0803 â€” CNM drivers â€” the two types, and who writes each.
> **Native network drivers** are **provided by Docker** and used through **Docker network commands**; **remote network drivers** are **created by the community and vendors**. Multiple drivers can coexist on an engine/cluster, but each Docker network is represented by **a single driver**.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0804 â€” What do IPAM drivers do, and how can an IP be set manually (p97)?
> IPAM drivers provide **default subnets or IP addressing to the network and the endpoints**. A user can assign an IP address manually through the **network, container, and service create commands**.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0805 â€” Container security challenges â€” how much shorter is a container's lifespan than a VM's, and why does that matter?
> On average a container's lifespan is **four times less** than a virtual machine's â€” it is created instantly, runs briefly, is stopped and removed. This **ephemerality lets an attacker execute an attack and disappear quickly**.
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0806 â€” Name the three container challenges that create network exposure.
> **Network-based attacks** (a jeopardized container, especially on **outbound networks with unrestricted raw sockets**), **bypassing / lack of isolation** (compromising one container gives access to another on the same host), and **unbounded network access from containers** (in the default state containers reach other containers and the host OS over the network).
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0807 â€” Image threats â€” list the five.
> **Image vulnerabilities** (static archive, missing updates) Â· **configuration defects** (runs with more privilege than required â†’ privilege escalation) Â· **embedded malware** (same privileges as the rest of the image) Â· **embedded clear text secrets** (image can be parsed to extract them) Â· **use of untrusted images** (malware, data leak, vulnerable components).
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0808 â€” Container risks â€” the two that involve the runtime itself.
> **Vulnerabilities within the runtime software** â†’ attacker compromises the runtime and can then attack other containers and monitor container-to-container communication. **Insecure container runtime configurations** â†’ too many configurable options; improper settings lower the security of the system.
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0809 â€” Orchestrator risks â€” why is mixing workload sensitivity levels dangerous?
> The orchestrator optimizes **workload density** and by default places **different-sensitivity workloads on the same host** â€” e.g. a public web server next to a container processing financial data. The sensitive container **can then be easily compromised**.
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0810 â€” Host OS risks â€” why is the shared kernel a risk if the container OS has a smaller attack surface?
> Because a container has **only software-level isolation of resources**, and **usage of a shared kernel increases the inter-object attack surface** â€” so a host OS component vulnerability or a shared-kernel flaw hits **every container on that host**.
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0811 â€” Docker â€” name the four security threats and what each is.
> **Escaping** = escape the container and gain **root on the host server**, then reach other machines on the local network. **Cross-container attacks** = use a compromised container to attack other containers on the same host or local network. **Inner-container attacks** = unauthorized access to a **single** container. **Docker registry attacks** = **image forgery** (tamper with the image) and **replay attack** (provide outdated content).
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0812 â€” List the five factors that may facilitate container breakouts (escaping).
> **Insecure defaults and weak configuration** Â· **information disclosure** Â· **weak network defaults** Â· **working with the root user (UID 0)** Â· **mounting host directories inside containers**.
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0813 â€” Kubernetes data exfiltration from a pod â€” which two techniques does the courseware name?
> **A reverse shell in a pod connecting to a command/control server**, and **network tunneling for hiding sensitive information**.
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0814 â€” Compromised container â€” which malicious processes may it run, and what enables it?
> **Cryptomining, network scanning, and port scanning** â€” a container normally runs a well-defined set of processes, so extra processes are the tell. Reached via **application misconfiguration** â†’ access the container â†’ hunt for weaknesses in the **network, process controls, or file system**.
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0815 â€” How is a Kubernetes worker node compromised, and what does it give the attacker (p110)?
> Through vulnerabilities such as the **dirty cow Linux kernel vulnerability**, which enables **user privilege escalation to root** â€” taking the whole host running the containers. Vulnerable components listed: management server, UI/API services, etcd, kubelets, compromised nodes/pods/accounts, exposed dashboard.
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0816 â€” What is Kubernetes, and who developed it?
> An open-source, portable, extensible **orchestration platform developed by Google** for managing containerized applications and microservices. It provides a resilient framework to manage distributed containers, generate deployment patterns, and perform failover and redundancy.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0817 â€” Which component is the Kubernetes backing store, and what happens when a pod instance dies?
> **etcd.** It stores cluster data such as "run three instances of this pod"; that stored data determines how many instances are running, and if an instance is not working Kubernetes creates an additional instance of the same pod.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0818 â€” What does kube-scheduler do?
> Monitors newly created pods that have **no assigned node** and assigns each of them a node to run on.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0819 â€” Name the five control-plane components of a Kubernetes cluster.
> kube-apiserver Â· etcd Â· kube-scheduler Â· kube-controller-manager Â· cloud-controller-manager
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0820 â€” What are the three services on a Kubernetes node, and what does each do?
> **kubelet** â€” node agent ensuring the containers in a pod's PodSpec are running and healthy. **kube-proxy** â€” network proxy running and maintaining network rules on each node. **Container runtime** â€” software that downloads images and runs the containers (Docker, CRI-O, CRI).
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0821 â€” How do you stop cloud-controller-manager from running the cloud-provider controller loops?
> Set the `-cloud-provider` flag to `external`. The controllers with cloud-provider dependencies are the node, route, service and volume controllers.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0822 â€” Which Kubernetes storage backends does the courseware list under storage orchestration?
> Local storage, public cloud providers (**AWS or GCP**), or a network storage system.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0823 â€” Container hardening: which two measures use segmentation and firewall technology, and what do they prevent?
> Limit container communications to defined segments - prevents unauthorized connections; prevent unauthorized network connections with network firewall technology - protects running containers. _(Mod 11 p112)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0824 â€” Container hardening: what does "alerts based on security baseline" mean per the courseware?
> Create a runtime security policy for the prompting of alerts and remedies when suspicious activity is observed. Audit container activity separately, from operational logs, configuration data and process documents. _(Mod 11 p112)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0825 â€” Two hardening items that reduce the attack surface directly.
> Disable unused OS capabilities - reduces vectors of attack to a significant extent; enforce fine-grained access control for granting and managing permissions. _(Mod 11 p112)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0826 â€” Container image security: what does Docker content trust (DCT) do?
> It lets image publishers (individuals or organizations) sign the image and assure consumers the image is authentic; sign the tagged version with default Docker options so Docker image integrity is implemented. _(Mod 11 p113)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0827 â€” Runtime security: why keep only a few running processes and mount read-only?
> Many processes complicate manage/troubleshoot. Read-only mount ensures writing prevention when only reading is required, makes the container filesystem immutable and reduces unauthorized change or tampering with critical files at runtime. _(Mod 11 p115â€“p116)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0828 â€” Runtime security: list the boot trust chain examples and the privilege-grant rule.
> Create a trust chain based on hardware: Intel TXT, Bootloader, Initrd, etc. Limit privileges to those required - provide fine-grained privileges by granting specific capabilities instead. _(Mod 11 p116)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0829 â€” Which three container secrets does the courseware name as needing protection?
> Passwords, access tokens, and API keys - they must be secured to prevent them from being accessed by unauthorized users with malicious intent. _(Mod 11 p114)_
> Source: [[11-LO07b-Container-Secrets-Management]]

> [!question]- 0830 â€” Container secrets: give the full handling chain from transfer to revocation.
> Transfer through a secure channel, encrypt and decrypt with the container's private key, store in a secret store created and managed with third-party credential-management tools, rotate on a regular basis, revoke immediately if exposed - and log all secret operations. _(Mod 11 p114)_
> Source: [[11-LO07b-Container-Secrets-Management]]

> [!question]- 0831 â€” Two placement rules for secrets: where must they never live?
> Not in environment variables, and not inside the container image (nor in the container file / Dockerfile). _(Mod 11 p114)_
> Source: [[11-LO07b-Container-Secrets-Management]]

> [!question]- 0832 â€” One secrets-management responsibility the courseware assigns to the application itself.
> Each application must assume responsibility for authentication and authorization. _(Mod 11 p114)_
> Source: [[11-LO07b-Container-Secrets-Management]]

> [!question]- 0833 â€” NIST's six container recommendations, condensed.
> Tailor operational culture and technical processes; use container-specific host OSes instead of general-purpose; group only same-purpose, same-sensitivity, same-threat-posture containers per host kernel; adopt container-specific vulnerability management for images; consider hardware-based countermeasures for trusted computing; use container-aware runtime defense tools. _(Mod 11 p117)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0834 â€” The closing best-practice list: four items about the container's own environment and permissions.
> Control root access; check the container runtime; lock down the operating system; embrace isolation and least privilege - plus centrally managed access controls. _(Mod 11 p118)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0835 â€” Hardening bullet: list the six concrete configuration rules.
> Configure against benchmarks, adopt control features for host/daemon/kernel, avoid privileged mode execution, avoid noisy neighbors, limit resources such as CPU/memory, permit network traffic only on default bridge. _(Mod 11 p118)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0836 â€” Health-check and sprawl items in the best-practice prose.
> Ensure appropriate life cycle management, delete drifted containers, control container sprawl, adopt continuous monitoring of container traffic, ensure service log management. _(Mod 11 p118)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0837 â€” Two process/file/device restrictions named in the best-practice prose.
> Avoid using the AUFS driver, and enable user namespace - with privileges based on roles, RBAC, and authentication/authorization. _(Mod 11 p118)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0838 â€” Docker ships five security features - name them and say what capabilities gives you.
> Cgroups, LSMs (AppArmor/SELinux via runc), capabilities, seccomp, userns. Capabilities split root privileges on a thread basis; Docker allows only 14 of the 37 Linux capability groups by default, and more can be added or removed. _(Mod 11 p120)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0839 â€” Seccomp and userns: what does each control?
> Seccomp gives fine-grained per-syscall control - the default profile limits many syscalls and specific syscalls can be blocked from being used by container binaries. Userns remaps root to unprivileged IDs on the host, isolating the process and limiting access to system resources; Docker supports global uid/gid mapping. _(Mod 11 p120)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0840 â€” Docker content trust: what does it verify, what is its default state, and how is it enabled?
> It verifies the authenticity, integrity and publication date of images in the Docker Hub registry; it is disabled by default. Enable with sudo export DOCKER_CONTENT_TRUST=1, then only signed images are retrieved by docker pull. _(Mod 11 p121)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0841 â€” Resource limits: why does an uncapped container endanger the host, and what two limit types does Docker impose?
> A container can consume as much as the host scheduler provides; the kernel may throw an OOME and kill other processes, potentially collapsing the system. Docker imposes hard memory limits (only a set amount of system memory) or soft memory limits (unconstrained use under conditions such as overall low memory usage). _(Mod 11 p122)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0842 â€” Which container resource is limited with which stated option?
> CPU - add the --cpus=2 option to the run command to limit a container to 2 CPUs. The 1 GB memory limit is the other example, but its option string is not legible in the courseware figure. _(Mod 11 p122)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0843 â€” Third-party tool selection: what is the risk and how is an official image recognized?
> Containers pulled from public repositories may have been created insecurely and may contain malicious or corrupt files, so pull only from reliable sources such as the Docker Hub. In the search results the first entry is the official image - that flag distinguishes official from third-party sources and tools. _(Mod 11 p123)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0844 â€” Docker Bench Security: what is it and what does it check?
> A script that enables checking of host configuration, Docker daemon configuration, Docker daemon configuration files, container images and build files, and container runtime. Referred to on p.118 as the Docker bench audit tool for facilitating configuration best practices. _(Mod 11 p124, p118)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0845 â€” Name the two tools whose Kubernetes integrations are structural rather than just monitoring.
> Anchore integrates with Kubernetes using admission controllers, ensuring only images that meet the organization's policies are deployed. StackRox collects system-level events - process execution, network connections and flows, privilege escalation, files launched within each container in Kubernetes environments. _(Mod 11 p125, p126)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0846 â€” StackRox: what does it protect, and which threats do its pre-defined policies detect?
> Cloud-native apps across the full life cycle including build, deploy and runtime. Pre-defined policies detect cryptocurrency mining, privilege escalation and various exploits. _(Mod 11 p126)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0847 â€” Which tool's stated function is a true layer 7 container firewall, and what does it block?
> NeuVector - end-to-end Kubernetes platform with a true layer 7 container firewall; detects and blocks suspicious processes and file system activity to prevent exploits and breakouts, plus automated segmentation, DPI, and detection for DDoS, DNS, SQL injection and DLP breaches. _(Mod 11 p125)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0848 â€” Three tools and their one-line identity, from distinct layers of the pipeline.
> Anchore - image analysis in the build pipeline, creates software container bills of materials, Kubernetes admission controllers. CloudPassage Halo - cloud/container/serverless security posture and continuous CIS-benchmark compliance. Capsule8 - attack detection and response for Linux environments, containerized, virtualized or bare-metal, on-premises or cloud. _(Mod 11 p125)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0849 â€” Which tools work by blocking, whitelisting or real-time intervention, and what is each mechanism?
> Aqua - least-privilege whitelisting to detect and prevent anomalous behavior, privilege escalation or code injection. Twistlock - real-time intervention, blocking and prevention for in-process runtime attacks, plus granular access control. Tenable.io - vulnerability assessment, malware detection and policy enforcement across development to operation. _(Mod 11 p124â€“p125)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0850 â€” Why favor minimal and alpine base images?
> Choose images with fewer OS libraries and tools - this decreases risk and reduces the attack surface area of the container. Favor alpine-based images over full-blown system OS images. _(Mod 11 p127â€“p128)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0851 â€” COPY versus ADD: what does the courseware say, and how is it worded twice?
> ADD is vulnerable to MITM attacks because arbitrary URLs specified could be malicious data sources, and it implicitly unpacks local archives, which could result in path traversal or Zip Slip vulnerabilities. Use COPY instead of ADD - use COPY unless ADD is specifically required. _(Mod 11 p127â€“p128)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0852 â€” The three measures to stop secrets leaking into images during build, and the version constraint.
> Use multi-stage builds; use the Docker secrets feature to mount sensitive files without caching them - supported only from Docker 18.04; use a .dockerignore file to avoid a hazardous COPY instruction that may pull sensitive files from the build context. _(Mod 11 p128)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0853 â€” Fixed tags for immutability: what goes wrong, and what are the two fixes?
> Image owners can push new versions to the same tags, giving inconsistent images during builds and making it hard to track whether a vulnerability is fixed. Fix with a verbose tag carrying version and OS, for example node:8-alpine, plus an image hash to pin the exact content. _(Mod 11 p128)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0854 â€” Least privileged policy on an image, and the multi-stage build payoff.
> Create the dedicated user and group on the image with minimal permissions to run the application, and use the same user to run the process - the Node.js image has a built-in generic node user. Multi-stage builds create small, clean images with minimized attack surface and vulnerabilities. _(Mod 11 p127, p129)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0855 â€” Which two tools does the courseware name for image scanning and Dockerfile linting, and what is each for?
> Snyk - scan Docker images and open-source application libraries for vulnerabilities as part of CI, and monitor for newly disclosed ones. hadolint - a static code analyzer linter that detects and alerts on issues in a Dockerfile and enforces Dockerfile best practices. _(Mod 11 p127, p129)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0856 â€” Kubernetes RBAC: why is privilege escalation blocked even when the RBAC authorizer is not in use?
> Because the RBAC API enforces it at the API level - editing roles or role bindings is blocked regardless of the active authorizer. _(Mod 11 p134)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0857 â€” Condition for creating or updating a role in Kubernetes RBAC.
> The user must already hold all the permissions contained in the role AND at the same scope - cluster-wide for a ClusterRole, within the same namespace for a Role. _(Mod 11 p134)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0858 â€” The three parts of Kubernetes RBAC permissions.
> Role or ClusterRole (rules = resources + verbs; Role = namespace, ClusterRole = cluster) Â· Subject (User, Group, ServiceAccount) Â· RoleBinding or ClusterRoleBinding joining them (namespace-scoped vs cluster-wide). _(Mod 11 p135)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0859 â€” How to disable ABAC on the API server.
> Kubernetes' ABAC is swapped with RBAC since release 1.6. Use --authorization-mode=RBAC, or in GKE --no-enable-legacy-authorization. _(Mod 11 p135)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0860 â€” PodSecurityPolicy fields that take a list of Linux capabilities, and the naming rule.
> AllowedCapabilities, RequiredDropCapabilities, DefaultAddCapabilities - capability name in ALL CAPS without the CAP_ prefix. _(Mod 11 p133)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0861 â€” Kubernetes container image guidelines for a small image, and the :latest tag.
> Minimal base image, few components restrict attack vectors, check for vulnerabilities regularly (BusyBox, Alpine given as examples); do not depend on :latest - use the specific version number as the tag and update it. _(Mod 11 p131)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0862 â€” Kubernetes audit logs: what do they record?
> A record of the activities of users, administrators, or system components that have affected the system. Audit logging customizes API logging at the metadata level and at the payload (request and response), set per organizational policy. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0863 â€” What is stored in the audit logs for read requests (get, list, watch) versus for Secret and ConfigMap requests?
> Read requests: the request object is exported. Secret and ConfigMap: only the metadata is saved. All remaining requests are exported. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0864 â€” List the seven questions Kubernetes audit logs must let cluster administrators answer.
> What happened Â· When did it happen Â· Who initiated it Â· What did it happen on Â· Where was it observed Â· Where was it initiated Â· Where was it going. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0865 â€” Minimal audit policy file: what are the apiVersion, kind and rule level?
> apiVersion audit.k8s.io/v1, kind Policy, rules with a single entry - level: Metadata (Figure 11.36) - logs all requests at the Metadata level. _(Mod 11 p140)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0866 â€” Which of these is NOT stated in the Kubernetes audit-policy guidance of Module 11?
> Audit-log rotation, retention and backends - the slice only gives the minimal Metadata-level policy file. See unresolved. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0867 â€” Audit logging in Kubernetes customizes API logging at which two levels?
> At the metadata level and at the payload (for example, request and response); the levels can be set as per the policy of the organization. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0868 â€” Kubernetes NetworkPolicy: what is the default state, and what changes when a policy selects a pod?
> By default all pods can talk to all other pods - pods are non-isolated. If a NetworkPolicy in the namespace selects a pod, that pod rejects any communication not allowed by the policy. _(Mod 11 p141, p142)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0869 â€” Are Kubernetes NetworkPolicy resources additive or overriding?
> Additive - if multiple policies select a pod, the pod is isolated based on the union of the policies' rules. _(Mod 11 p141)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0870 â€” restrict-root.yaml: what does it block, and how is it activated?
> privileged: false plus runAsUser rule mustRunAsNonRoot, so containers cannot run privileged or as root. Saved as restrict-root.yaml and activated with kubectl create -f restrict-root.yaml. _(Mod 11 p146)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0871 â€” How do you restrict the volume/storage types a container may use?
> Specify the allowed volume types in the volumes key of a pod security policy (for example only nfs) and install the policy - this reduces costs or avoids accessing information. _(Mod 11 p146)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0872 â€” Which Kubernetes secret encryption provider is recommended for enhanced security, and why?
> kms - envelope encryption with DEKs (AES-CBC/PKCS#7) wrapped by KEKs per the KMS configuration, simplifying key rotation; EncryptionConfig alone only gives moderate security for stored keys, and the KMS provider must be configured. _(Mod 11 p150)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0873 â€” How do you verify that secrets are encrypted at rest in etcd, and what proves it?
> ETCDCTL_API=3 etcdctl get /registry/secrets/default/secret1 --hexdump -C, then check the stored secret is prefixed with k8s:enc:aescbc:v1:, and that kubectl describe secret secret1 -n default decrypts it correctly. Configuration is enabled with the kube-apiserver --encryption-provider-config argument. _(Mod 11 p149, p151)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0874 â€” Istio: source and what it does for Kubernetes security.
> Source www.istio.io. It helps connect, secure, control and observe services, creating a service mesh for service-to-service communication including routing, authentication and encryption, and encrypting pod-to-pod communication with mutual TLS. _(Mod 11 p152)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

> [!question]- 0875 â€” Grafeas: source and scope.
> Source www.github.com. An open source initiative defining a best practice for auditing and governing the modern software supply chain, with an API spec for metadata about software resources - container images, virtual machine images, JAR files, scripts. _(Mod 11 p152)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

> [!question]- 0876 â€” What does the CIS Kubernetes benchmark give you, and what is the module's example check?
> Instructions to audit a configuration against the recommendation and to remediate setups that fail the audit test. Example: basic authentication uses plaintext credentials, so ensure --basic-auth-file is not set, checked with ps -ef | grep kube-apiserver on the master node. _(Mod 11 p153)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

> [!question]- 0877 â€” Which tools are named for updating a manually managed Kubernetes cluster, and what must also be updated?
> kubeadm and kops. Update both the control plane components (API server, scheduler) and the worker nodes, and check that plugins, add-ons and extensions are compatible with the new version. _(Mod 11 p154)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

> [!question]- 0878 â€” Before and after updating a Kubernetes cluster, what do the best practices require?
> Before: reliable backup of the entire cluster - configurations, applications, data. After: run container tests, thoroughly test all applications and services, and update the documentation with the changes. _(Mod 11 p154, p155)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

### Module 12 (293 items)

> [!question]- 0879 â€” Courseware definition of cloud computing â€” the three qualifiers
> On-demand delivery of IT capabilities where the IT infrastructure and applications are provided to subscribers as a metered service over a network
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0880 â€” The 12 characteristics of cloud computing, in courseware order
> On-demand self service Â· Distributed storage Â· Broad network access Â· Rapid elasticity Â· Automated management Â· Resource pooling Â· Measured service Â· Virtualization technology Â· Multi-tenancy Â· Resilient computing Â· Flexible pricing models Â· Sustainability
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0881 â€” Measured service â€” what exactly is metered?
> Pay-per-use â€” monthly subscription or per usage (storage levels, processing power, bandwidth); the CSP monitors, controls, reports and charges with complete transparency
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0882 â€” Limitations of cloud computing (courseware list)
> Limited control and flexibility Â· Prone to outage and other technical issues Â· Security, privacy and compliance issues Â· Contracts and lock-ins Â· Dependence on network connections
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0883 â€” Cloud computing benefits â€” the four groups and their item counts
> Economic 8 Â· Operational 7 Â· Staffing 7 Â· Security 8 = 30 items
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0884 â€” Which benefits group carries "Standardized open interface for managed security services (MSS)"?
> Security
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0885 â€” IaaS â€” what does the subscriber get, and who runs the underlying infrastructure?
> VMs and other abstracted hardware and OSes controlled through a service API; the CSP manages the underlying cloud-computing infrastructure, so the subscriber avoids human capital and hardware costs
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0886 â€” IaaS â€” the two disadvantages the courseware lists
> Software security is at high risk (third-party providers are more prone to attacks) Â· Performance issues and slow connection speeds
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0887 â€” PaaS â€” three disadvantages
> Vendor lock-in Â· Data privacy Â· Integration with other system applications
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0888 â€” SaaS â€” three disadvantages
> Security and latency issues Â· Total dependency on the internet Â· Switching between SaaS vendors is difficult
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0889 â€” SaaS â€” how do providers charge for the service?
> Pay-per-use basis via subscription, advertising, or sharing among multiple users
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0890 â€” Why must subscriber and service-provider responsibilities be separated in cloud computing?
> Separation of duties prevents conflicts of interest, illegal acts, fraud, abuse and errors; helps identify security control failures (information theft, security breaches, invasion of security controls); restricts the influence held by an individual
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0891 â€” Deployment-model selection is driven by which five factors?
> Where cloud computing services are hosted Â· Security requirements Â· Sharing cloud services Â· Ability to manage some or all cloud services Â· Customization capabilities
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0892 â€” Public cloud â€” disadvantages
> Security is not guaranteed Â· Lack of control (third-party providers are in charge) Â· Slow speed (relies on internet connections, data transfer rate is limited)
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0893 â€” Private cloud â€” advantages
> Enhance security (dedicated to a single organization) Â· More control over resources Â· Greater performance (inside the firewall) Â· Customizable hardware, network and storage Â· Sarbanes-Oxley, PCI DSS and HIPAA compliance data significantly easier to acquire
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0894 â€” Community cloud â€” what makes it different from a private cloud?
> Multi-tenant infrastructure shared among organizations from a specific community with common computing concerns; on-premise or off-premise; governed by the participating organizations or a third-party managed service provider
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0895 â€” Hybrid cloud â€” courseware definition and example
> Two or more clouds (private, public, community) that remain unique entities but are bound together; example â€” critical activities such as operational customer data on a private cloud, non-critical activities on a public cloud
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0896 â€” Does multi-cloud mix private and public clouds?
> No â€” multi-cloud is a combination of only two or more public cloud services; it does not mix public and private cloud services
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0897 â€” The five significant actors in the NIST cloud reference architecture
> Cloud consumer Â· Cloud provider Â· Cloud carrier Â· Cloud auditor Â· Cloud broker
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0898 â€” What does a cloud carrier do?
> Acts as an intermediary providing connectivity and transport services between the cloud service providers and cloud consumers; provides access to consumers via networks, telecommunication and other access devices
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0899 â€” What does a cloud auditor examine, and what does an audit verify?
> It independently examines the cloud service controls to express a corresponding opinion; audits verify adherence to standards by reviewing objective evidence
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0900 â€” The three service categories a cloud broker provides
> Service intermediation (improves a given function, value-added) Â· Service aggregation (combines multiple services into new services) Â· Service arbitrage (like aggregation but the services are not fixed)
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0901 â€” SLA in cloud computing â€” who specifies what?
> The consumer specifies the technical performance requirements â€” quality of service, security and remedies for performance failure; the CSP may also define limitations and obligations the consumer must accept
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0902 â€” Which actor steps out when the consumer buys directly from the CSP, and what stack does Figure 12.1 show?
> Cloud broker; Service Layer (SaaS/PaaS/IaaS) â†’ Resource Abstraction and Control Layer â†’ Physical Resource Layer â†’ Hardware Facility, with Cloud Service Management, Business Support and Portability/Interoperability across it
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0903 â€” Traditional security measures in the cloud â€” what changes and what does not
> The security protocols do not change; the security focus of the cloud consumers does
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0904 â€” Shared responsibility â€” the failure condition stated by the courseware
> If the consumers do not secure their functions, the entire cloud security model will fail
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0905 â€” Shared responsibility matrix â€” the four columns, left to right
> On-premises (for reference) Â· Infrastructure-as-a-service (IaaS) Â· Platform-as-a-service (PaaS) Â· Software-as-a-service (SaaS)
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0906 â€” Cloud service consumers are responsible for
> User security and monitoring (IAM) Â· information securityâ€”data (encryption and key management) Â· application-level security Â· data storage security Â· monitoring, logging and compliance
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0907 â€” Cloud service providers are responsible for
> Securing the shared infrastructure: routers Â· switches Â· load balancers Â· firewalls Â· hypervisors Â· storage networks Â· management consoles Â· DNS Â· directory services Â· cloud API
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0908 â€” IAM â€” why MFA is enabled and the preferred device types
> To control access to cloud service APIs; best option is a virtual MFA or a hardware device
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0909 â€” Main challenge in cloud network security, per the courseware
> Lack of network visibility in monitoring and managing suspicious activities by the consumer
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0910 â€” Five data storage security techniques
> Local data encryption Â· Key management Â· Strong password management Â· Periodic security assessment of data security controls Â· Cloud data backup
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0911 â€” Why must organizations keep local backups of cloud data?
> Loss of data may imply financial loss as well as legal actions, so a local backup is essential to prevent possible data loss
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0912 â€” Two-step verification and updated patches â€” what do they defend against?
> They prevent hackers from attacking the systems easily
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0913 â€” Which network security control does each cloud use â€” AWS vs Azure?
> AWS: Network Access Control List (NACL) Â· Azure: Endpoint and NSG
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0914 â€” Cloud network security â€” what does the firewall usage guarantee?
> Isolation between multiple zones
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0915 â€” Security logs â€” the three uses stated in the courseware
> Threat detection Â· Data analysis Â· Compliance audits
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0916 â€” Five questions that determine whether the right log data was captured
> Who is accessing the network? Â· What assets are they accessing? Â· From where are they accessing the asset? Â· When are they doing this? Â· Are there established permissions to allow their activity?
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0917 â€” Data monitoring â€” the two rule requirements
> Define thresholds and rules for normal activity, and alert the data owner if data activity exceeds the defined thresholds
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0918 â€” Where should aggregated logs be sent?
> To log analytics or a security information and event management (SIEM) system, giving a database of valuable information to access and analyze on demand
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0919 â€” Cloud monitoring plan â€” the seven essential aspects
> Identify metrics and events Â· Use one platform to report all data Â· Monitor cloud service usage and fees Â· Monitor user experience Â· Trigger rules with data Â· Separate and centralize data Â· Try failure
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0920 â€” Consequences of compliance failure
> Regulatory fines Â· Lawsuits Â· Cyber security incidents Â· Reputational damage
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0921 â€” Which three CSP market shares are printed on the Q2 2023 spend figure?
> AWS 30% Â· Microsoft Azure 26% Â· Others 35% (the Google Cloud slice label carries no legible percentage)
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0922 â€” What must be done before consuming a cloud service?
> Perform a gap analysis on the security capabilities and services provided by the cloud service providers
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0923 â€” Gap analysis â€” the three benchmark axes
> Maturity Â· Transparency Â· Compliance
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0924 â€” Enterprise security standard and regulatory standards named for the gap analysis
> ISO 27001 Â· PCI DSS Â· HIPAA Â· SOX
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0925 â€” CSP security maturity â€” the five evaluation points
> Disclosure of security policies, compliance and practices Â· Disclosure when mandated Â· Security architecture Â· Security automation Â· Governance and security responsibility
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0926 â€” The three closing questions for evaluating a CSP
> How many security tools are currently required in the organization? Â· What risks can the security tools reduce/address? Â· Rationalize the existing security vendors and tools
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0927 â€” When are third-party security tools required in cloud?
> For the security controls that are not provided by the CSP
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0928 â€” What must be checked about third-party products before choosing a provider?
> That they can be integrated with the cloud platform; then combine third-party controls with the CSP's own controls
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0929 â€” Approach used to review CSP tools before a technology decision
> A self-check or requirement-driven approach â€” review requirements and each CSP's existing tools
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0930 â€” Control categories the on-premise column is measured against
> Firewall and ACLS Â· IPS/IDS Â· WAF Â· SIEM Â· Log Analytics Â· Antimalware Â· PAM Â· DLP Â· Vulnerability Assessment Â· Email Protection Â· SSL Decryption Â· Reverse Proxy Â· Key Management Â· Encryption at rest Â· DDOS Â· MFA Â· Centralized logging/auditing Â· Load balancer Â· LAN/WAN Â· Endpoint protection Â· Certificate management Â· Container security Â· GRC Â· Monitoring Â· Backup and recovery
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0931 â€” AWS shared responsibility â€” who secures what
> Customers decide the access levels they give from and to their resources; AWS secures the cloud. "In the cloud" = customer band Â· "of the cloud" = AWS band
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0932 â€” The two control types the AWS shared responsibility model uses
> Inherited Controls â€” inherited completely from AWS to customers (e.g. physical and environmental) Â· Shared Controls â€” applied to both the infrastructure and the customer layer with separate perspectives
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0933 â€” Shared Control: Patch Management split
> AWS patches and fixes flaws within the infrastructure; customers patch their guest OS and applications
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0934 â€” Shared Control: Configuration Management split
> AWS configures the infrastructure devices; the customer configures their guest OSes, databases, and applications
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0935 â€” Shared Control: Awareness and Training split
> AWS trains the AWS employees; customers train their employees
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0936 â€” Client-Side Data Encryption â€” which keys may the customer use
> Either an AWS-managed encryption key or a personal key not provided by AWS
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0937 â€” AWS IAM â€” the four attributes it ties together
> Who = workforce users and workloads with IAM Â· Can access = permissions with IAM policies Â· What = AWS services Â· Resources = within organization
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0938 â€” What AWS IAM Identity Center was formerly called
> AWS Single Sign-On
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0939 â€” IAM Identity Center â€” the five key features
> Workforce identities Â· application assignments for SAML applications (SAML 2.0) Â· Identity Center enabled applications Â· multi-account permissions Â· AWS access portal
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0940 â€” IAM Access Analyzer â€” the twelve resource types it generates findings for
> IAM roles Â· KMS keys Â· S3 buckets Â· Secrets Manager secrets Â· Lambda functions and layers Â· EBS volume snapshots Â· SQS queues Â· SNS topics Â· RDS DB snapshots Â· RDS DB cluster snapshots Â· ECR repositories Â· EFS file systems
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0941 â€” IAM Access Analyzer â€” what does policy validation produce
> Findings containing security errors, warnings, suggestions and general warnings, each with actionable recommendations; checked with more than 100 policy checks
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0942 â€” What Access Analyzer analyses to generate a policy
> AWS CloudTrail logs â€” the actions and services used by an IAM entity (user or role) within a specified date range; the generated policy can then be attached to a user or role
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0943 â€” Preventive guardrails â€” the three ways to cap what an IAM role can be granted
> Service control policies Â· permission boundaries Â· session policies
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0944 â€” Definition of an AWS IAM role
> An entity that you define and provide specific permissions to, allowing trusted identities such as workforce identities and applications to conduct actions in AWS â€” a security best practice because it gives temporary credentials that need not be rotated
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0945 â€” Which product gives temporary AWS access to applications running outside AWS
> IAM Roles Anywhere
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0946 â€” Name the five IAM role scenarios
> Federate workforce identities into AWS Â· access workloads within AWS Â· access workloads that run outside of AWS Â· enable cross-account access Â· grant access to AWS services
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0947 â€” Why root user access keys are not recommended
> They grant complete access to all resources for all AWS services including billing information, and the permissions associated with them cannot be reduced
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0948 â€” AWS password requirements
> Minimum 8 and maximum 128 characters Â· at least three of the four character types (uppercase, lowercase, numbers, symbols) Â· not identical to the AWS account name or email address
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0949 â€” The three stated objectives for creating individual IAM users
> 01 Do not allow a user to use the root user account â€” create individual user accounts instead Â· 02 give each IAM user a unique set of security credentials and appropriate permissions Â· 03 this lets you change or revoke their permissions as required
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0950 â€” Why create an IAM user for yourself instead of using root
> Create an IAM user, give it administrative permissions, and use it for all your work
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0951 â€” During user creation, which option is selected by default
> Add user to group â€” the new user is placed in a newly created group automatically (the example group is Training_Group)
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0952 â€” Which setting is optional on a new IAM user but recommended
> Require password reset â€” "The Require password reset is optional; however, enable this setting"
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0953 â€” Three stated advantages of using groups
> Create groups with similar job functions Â· assigning and reassigning rights to groups is easy and less time consuming Â· reduces accidental assignment of greater privileges to users
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0954 â€” Why do individual users still keep credentials when IAM groups exist
> The group policy governs access, but individual users still possess their own credentials
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0955 â€” The three phases IAM Access Analyzer drives toward least privilege
> Set fine-grained permissions Â· verify intended permissions Â· refine permissions by removing unused access
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0956 â€” Generating a policy from CloudTrail â€” what does Access Analyzer read
> AWS CloudTrail events for the chosen role, over a specified time period â€” choose the shortest, up to 90 days, to reduce generation time Â· status is reported on the role page; then View generated policy in the Permissions tab
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0957 â€” The five IAM access levels
> List Â· Read Â· Write Â· Permissions management Â· Tagging
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0958 â€” The five features of a managed policy
> Reusability Â· central change management Â· versioning and rolling back Â· delegating permission management Â· automatic updates (AWS-managed)
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0959 â€” Three AWS-managed policy classes with their named examples
> Full access â€” AmazonDynamoDBFullAccess, IAMFullAccess Â· Power user â€” AWSCodeCommitPowerUser, AWSKeyManagementServicePowerUser Â· Partial access â€” AmazonEC2ReadOnlyAccess, AmazonMobileAnalyticsWriteOnlyAccess
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0960 â€” The three policy summary tables
> Policy summary â€” services and permission summaries for the policy Â· Service summary â€” actions and permission summaries for one service Â· Action summary â€” resources and the conditions for one action
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0961 â€” The elements a strong AWS password policy must contain
> Minimum length in the range 6 to 128 Â· at least one uppercase (Aâ€“Z) Â· at least one lowercase (aâ€“z) Â· at least one numeric (0â€“9) Â· at least one non-alphanumeric Â· allow users to change their own password Â· enable password expiration Â· prevent password reuse Â· password expiration requires administrator reset
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0962 â€” The four IAM MFA methods as listed in the courseware
> FIDO security keys Â· Virtual authenticator apps Â· TOTP hardware tokens Â· TOTP hardware tokens for the AWS GovCloud (US) Regions
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0963 â€” The named TOTP hardware-token providers, by scope
> Thales â€” TOTP hardware tokens used exclusively with AWS accounts Â· Hypersecu â€” TOTP hardware tokens compatible with AWS GovCloud (US) Regions, used exclusively by IAM users with AWS GovCloud (US) accounts
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0964 â€” The two MFA response styles and how each finishes the sign-in
> Virtual/hardware MFA devices â€” generate a code that the user types on the sign-in screen Â· U2F security keys â€” generate a response when the device is tapped and the sign-in completes automatically
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0965 â€” How FIDO security keys are characterised
> FIDO-certified hardware keys from third-party providers such as Yubico; based on public key cryptography; strong, phishing-resistant authentication; a single key supports multiple root accounts and IAM users
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0966 â€” Assigning a virtual MFA device â€” the whole wizard in order
> Seed the app with Show QR code (scan it) or Show secret key (type it in) Â· type the OTP currently shown in MFA code 1 Â· wait 30 seconds for a new OTP Â· type the second OTP in MFA code 2 Â· select Assign MFA
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0967 â€” Why an IAM role is preferred over credentials on an EC2 instance
> A role is not a user or group and has no permanent credentials â€” IAM dynamically provides temporary credentials to the instance and they are automatically rotated; the role is set as a launch parameter and its permissions decide what the app may do
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0968 â€” The two policies attached to a delegation role, and the permission swap
> Permission policy â€” what the role's user may do on the resources (half the permissions) Â· Trust policy â€” which trusted-account members may assume the role (the other half) Â· assuming the role temporarily replaces the user's own permissions; they return when the user stops
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0969 â€” The permissions boundary, as the courseware defines it
> A more advanced feature that lets you use a managed policy to limit the maximum permissions that an identity-based policy can provide to an IAM role
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0970 â€” Zero-downtime key rotation â€” order of operations and the stale-key threshold
> Deactivate keys used more than 90 days ago, identified with Access Key Last Used Â· create the second access key (active by default) â†’ update all applications and tools to use it â†’ wait several days and check Last Used on the old key â†’ Make inactive on the old key â†’ confirm applications work â†’ delete the old key
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0971 â€” Two trust-policy hardening options when creating a cross-account role
> Require external ID â€” adds a trust-policy condition that the request include the correct sts:ExternalId, any word or number agreed with the third-party administrator Â· Require MFA â€” adds a trust-policy condition that checks for an MFA sign-in
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0972 â€” How a service-linked role is named, and how it is marked
> The role name prefix is auto-populated and you type only the suffix; leave the suffix blank for services such as Amazon Lex that do not support custom suffixes; service-linked roles are marked with a cube-shaped icon in the IAM console
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0973 â€” The ABAC rule and the condition keys it uses
> Define policies that use tag condition keys to grant permissions to principals based on their tags â€” session tags are passed when a principal assumes a role or federates a user Â· the access-assume-role policy string-equals iam:ResourceTag/access-project, iam:ResourceTag/access-team and iam:ResourceTag/cost-center against the same-named aws:PrincipalTag values
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0974 â€” The two policy variants in the ABAC walkthrough
> access-assume-role â€” wildcard on the role name (`access-*`) plus a tag-match Condition, so a user can assume only roles whose tags match their own Â· access-assume-specific-roles â€” no Condition; an explicit list of role ARNs the user may assume
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0975 â€” The ABAC secret-viewing decision rule
> Compare the role name to the secret name â€” if they share the same team name the access-team tags match and access is allowed; if they do not match, access is denied
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0976 â€” What the Condition element does in an IAM policy
> Specifies the conditions under which a policy statement is in force â€” allow access to resources and actions only if the request satisfies the criteria, expressed with condition operators (equal, less than, etc.) comparing condition keys and values in the policy against the request context
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0977 â€” The two console columns for finding stale credentials
> Console last sign-in â€” days since the user last signed into the console; Never = password never used, None = no password Â· password_last_used in the credentials report â€” N/A = no password, no_information = never used since tracking began
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0978 â€” The credential-to-purpose pruning rule
> Remove the console password for users who use the application but not the console Â· remove the access keys for users who only use the console
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0979 â€” What the AWS log files display
> Time and date of actions Â· source IP for an action Â· actions that failed owing to inadequate permissions, among others
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0980 â€” The five logging services and what each is for
> Amazon CloudFront â€” user requests received, web and RTMP distributions Â· AWS CloudTrail â€” account activities and events, event history plus a trail for the ongoing record Â· AWS Config â€” detailed historical configuration of AWS resources Â· Amazon S3 â€” details of access requests to buckets, plus Audit Logs Â· Amazon CloudWatch logs â€” centralize logs from EC2, CloudTrail, and Route 53
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0981 â€” CloudTrail â€” data events, management events, Insights and log encryption
> Data events â€” resource ('data plane') operations on or within the resource itself Â· management events â€” management ('control plane') operations on resources in the account Â· CloudTrail Insights â€” identifies unusual activities Â· log file encryption â€” Amazon S3 server-side encryption (SSE) on log files delivered to S3 buckets
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0982 â€” The three IAM Identity Center identity sources
> Identity Center directory â€” the default when Identity Center is first enabled Â· Active Directory â€” AWS Managed Microsoft AD via AWS Directory Service, or a self-managed AD Â· External identity provider â€” e.g. Okta or Azure Active Directory
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0983 â€” The six steps to implement SSO with IAM Identity Center
> Step 1 enable IAM Identity Center (root user) Â· Step 2 select the identity source Â· Step 3 create an administrative permission set Â· Step 4 set up AWS account access for an administrative user Â· Step 5 sign in to the AWS access portal Â· Step 6 set up access to AWS applications
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0984 â€” How SSO to an EC2 Windows instance works
> AWS IAM Identity Center user portal â†’ Management console â†’ Fleet Manager â†’ Instance actions â†’ Connect with Remote Desktop â†’ select IAM Identity Center and Connect; on first connect a new local user is created and AWS Fleet Manager uses the credentials it created to sign in â€” the All sessions tab then shows up to four concurrent sessions in a single view
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0985 â€” The three AWS data-at-rest encryption models â€” who does what
> Model A â€” customer manages the encryption, key storage and key management Â· Model B â€” AWS provides the key storage layer, customer manages the encryption algorithm and key management Â· Model C â€” AWS provides the key storage layer, encryption algorithm and key management (transparent server-side encryption)
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0986 â€” In AWS data-at-rest Model B, where are the keys stored and who controls the algorithm?
> Keys are stored in the AWS environment (AWS CloudHSM) and are inaccessible to any AWS employee; the customer provides the KMI (on-premise or in Amazon EC2) and manages the encryption algorithm and key management, communicating with CloudHSM over SSL
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0987 â€” The three Amazon S3 server-side encryption key-management options
> SSE-S3 â€” Amazon S3-managed keys Â· SSE-KMS â€” AWS KMS-managed keys (CMKs in AWS Key Management Service) Â· SSE-C â€” customer-provided keys, never stored by S3
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0988 â€” Amazon S3 SSE-S3 as described by the courseware
> Each object is encrypted with a unique key, and that key is additionally encrypted with a master key; Amazon S3 SSE uses 256-bit AES (AES-256); a bucket policy can enforce SSE for all objects in the bucket
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0989 â€” Which Amazon S3 APIs support the `x-amz-server-side-encryption` request header
> PUT operations (uploading with the PUT API) Â· Initiate Multipart Upload (header in the initiate request for large objects) Â· COPY operations (source and target object)
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0990 â€” Amazon S3 SSE-KMS â€” the printed highlights
> Select a customer-managed CMK you create/manage or an AWS-managed CMK that Amazon S3 creates and manages for you Â· create, rotate and disable auditable customer-managed CMKs from the AWS KMS console Â· provides encryption of the data keys that encrypt customer data Â· provides encryption-related compliance requirements Â· the ETag in the response is not the MD5 of the object data
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0991 â€” The two key components of the Bouncy Castle architecture, and what the rest build on
> Light-weight API and the Java Cryptography Extension (JCE) provider support cryptography; the remaining components built on the JCE provider add extra functionality (PGP support, S/MIME). Bouncy Castle supplies APIs for both Java and C#, from J2ME to JDK 1.11
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0992 â€” The two CloudHSM claims that give separation of duties
> AWS has administrative credentials to manage and maintain the appliance, but administrative credentials cannot access the HSM partitions; AWS monitors HSM health and network availability while users control the HSMs and the generation and use of their encryption keys
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0993 â€” The six AWS Certificate Manager best practices
> AWS CloudFormation Â· Certificate Pinning Â· Domain Validation Â· Adding or Deleting Domain Names Â· Opting Out of Certificate Transparency Logging Â· Turn on AWS CloudTrail
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0994 â€” Certificate pinning, as the courseware defines it
> Also called SSL pinning â€” validate a remote host by associating it directly with its X.509 certificate or public key, then use pinning to bypass the SSL/TLS certificate chain validation
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0995 â€” s2n â€” what it is and what it supports
> An open-source C99 implementation of the TLS/SSL protocols, designed to be simple, small, fast and security-first. Implements SSLv3, TLS1.0, TLS1.1, TLS1.2 Â· 128-bit and 256-bit AES, ChaCha20, 3DES and RC4 in CBC and GCM Â· DHE and ECDHE for forward secrecy Â· SNI, ALPN and OCSP TLS extensions
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0996 â€” What CloudFront does with the SSL/TLS connection in the ACM architecture
> Users communicate with CloudFront over HTTPS and CloudFront terminates the SSL/TLS connection at the edge location; CloudFront then communicates to the origin over HTTP or HTTPS as configured
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0997 â€” Security groups vs network ACLs â€” the two distinctions the courseware makes
> Security groups have no "Deny" rule, so a packet is dropped unless a rule explicitly permits it, and they apply at instance and subnet level Â· network ACLs do have an Allow/Deny list, are stateless traffic filters on subnets, are evaluated by rule number, and their changes apply automatically to the associated subnets
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 0998 â€” The five fields of a security group rule
> Type Â· Protocol Â· Port Range Â· Source Â· Description â€” the same five apply to both the Inbound and the Outbound table
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 0999 â€” Why customers must create their own VPC security groups
> Because Amazon EC2 security groups would not work inside Amazon VPC; VPC security groups add capabilities EC2 security groups lack â€” changing the security group after the instance is launched, and specifying any protocol with a standard protocol number
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 1000 â€” The four AWS VPC architecture templates, by level of public access
> VPC with only a single public subnet Â· VPC with public and private subnets Â· VPC with public and private subnets including hardware VPN access Â· VPC with only a private subnet along with hardware VPN access
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 1001 â€” Virtual Private Gateway (VPG) vs Internet Gateway
> VPG establishes private connections between an Amazon VPC and another network, with traffic isolation per VPG and each VPN connection secured by a pre-shared key plus the customer gateway device's IP address Â· an internet gateway is attached to a VPC to enable direct connectivity with the internet, Amazon S3 and other AWS services, and each instance needs an Elastic IP or to route traffic through a NAT instance
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 1002 â€” The five DMZ / isolation measures the courseware lists for AWS network security
> Use a demilitarized zone exposing external services to an untrusted network Â· isolate resources with subnets, firewalls and routing tables Â· secure DNS configurations Â· limit inbound/outbound traffic Â· secure accidental exposures
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 1003 â€” The two AWS DDoS detection inputs Shield Standard combines
> Traffic signatures and anomaly algorithms (plus analysis techniques) â€” it detects malicious traffic in real time, and automatically mitigates basic network layer attacks using deterministic packet filtering and priority-based traffic techniques
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1004 â€” AWS Shield Standard vs AWS Shield Advanced
> Shield Standard â€” threat protection for the first point of entry from outside the AWS network, automatic protection for all AWS customers at no additional charge, always on, pre-configured, static, no reporting or analytics, and the services CloudFront, Global Accelerator and Route 53 are part of it Â· Shield Advanced (optional) â€” available for CloudFront, Route 53 and Global Accelerator, and can be used with Elastic IP addresses to secure Network Load Balancers or Amazon EC2 instances
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1005 â€” What Amazon S3 Block Public Access does
> It ensures that the objects do not have public permissions â€” if a user writes an object in a bucket with S3 Block Public Access enabled and that object has public permissions through an ACL or any other policy, then that permission will be blocked
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1006 â€” How to restrict access to Amazon S3 resources
> Combine bucket policies, ACLs and IAM policies Â· enforce the VPC endpoint policy for private VPC-endpoint connections to S3 Â· use IAM policies to implement TLS encryption for S3 requests or S3 SSE with KMS keys Â· S3 Object Lock sets a specific retention date to prevent object deletion
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1007 â€” The two S3 metadata classes and the user-defined prefix
> System-defined metadata (add via Properties > Metadata > Add Metadata, picking a key and a value from the menus) and user-defined metadata, whose keys start with the `x-amz-meta-` prefix â€” e.g. custom name `alt-name` becomes `x-amz-meta-alt-name`
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1008 â€” Data classification by sensitivity, and Amazon Macie
> Public Data â€” not sensitive, available to everyone, unencrypted Â· Critical Data â€” not accessible directly on the internet, requires authentication and authorization, encrypted Â· Amazon Macie automatically discovers, classifies and protects sensitive data in AWS using machine learning, identifying PII and providing dashboards and alerts
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1009 â€” What Amazon GuardDuty is and how it works
> A threat detection service that monitors AWS accounts, instances, users, databases and workloads continuously for malicious activity; it delivers detailed security findings for visibility and remediation, using anomaly detection, ML, threat intelligence feeds and behavioral modeling to expose threats
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1010 â€” Amazon VPC Flow Logs vs Amazon CloudWatch Events
> VPC Flow Logs collect and store information about the incoming and outgoing IP traffic from Amazon VPC network interfaces, for debugging or where network flow data are required by legal or security policies Â· CloudWatch Events deliver system events describing changes in AWS resources, matched and routed to target functions or streams using simple rules
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1011 â€” Amazon Inspector â€” what it is
> An automated security assessment service that improves the security and compliance of applications deployed on AWS, working application-by-application; it automatically evaluates applications for vulnerabilities, exposures and deviations from best practices and lists security findings by severity level
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1012 â€” The four CloudTrail-related checklist items
> Permit CloudTrail logging across all Amazon Web Services Â· set (establish) CloudTrail log file validation Â· permit CloudTrail multi-region logging Â· combine CloudTrail with CloudWatch
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1013 â€” The credential and root-account hygiene items in the AWS security checklist
> Set MFA for the root account and for IAM users Â· avoid use of root user accounts Â· do not use access keys with root accounts Â· link IAM policies to groups or roles Â· rotate IAM access keys regularly and standardize the number of days Â· establish strict password policies and set password termination session to 90 days Â· reduce the number of IAM groups Â· disable unused or inactive IAM users Â· remove unused IAM access keys Â· terminate available access keys
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1014 â€” The encryption-at-rest and transport items in the AWS security checklist
> Encrypt the CloudTrail log files at rest Â· encrypt Amazon RDS Â· EBS must be encrypted Â· SSL secure ciphers and versions between client and ELB Â· use secure CloudFront SSL versions and HTTPS for CloudFront distributions Â· do not use expired SSL/TLS certificates Â· permit the required SSL parameters in all Redshift clusters Â· minimize the number of discrete security groups Â· use a standard naming (tagging) convention for EC2
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1015 â€” Which layers does the Azure service provider own completely under SaaS?
> Applications Â· network controls Â· operating system Â· physical hosts Â· physical network Â· physical data
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1016 â€” Which Azure service model has the customer completely retaining identity and directory infrastructure, applications and network controls?
> IaaS â€” plus information and data, devices, accounts and identities and the OS; the provider keeps only physical hosts, physical network and physical data center
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1017 â€” What is shared between the customer and Azure under SaaS?
> Identity and directory infrastructure â€” only; data, devices and identities stay with the customer, applications/network/OS/physical layers go to the provider
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1018 â€” Under PaaS, which layers are shared between customer and Azure?
> Identity and directory infrastructure Â· applications Â· network controls
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1019 â€” What is the responsibility split under the Azure on-premises data center model?
> All responsibilities are retained by the customer
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1020 â€” Shared responsibility items enumerated by the Azure courseware
> Data classification and accountability Â· client and endpoint protection Â· identity and access management Â· application-level controls Â· network controls Â· host infrastructure Â· physical security
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1021 â€” The two rules that govern Azure AD Conditional Access policies
> Implemented after first-factor authentication Â· configured on group, location and application sensitivity for SaaS apps and Azure AD-connected apps, and applied to on-premise and Azure cloud applications
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1022 â€” What does Azure AD Conditional Access do, as printed?
> It is the tool Azure AD uses for enforcing organizational policies to manage and control access to corporate resources, giving security and right access control
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1023 â€” The Azure single sign-on click path
> Azure AD Active Directory settings â†’ Azure AD connect â†’ under USER SIGN-IN enable Seamless single sign-on
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1024 â€” The 12 Azure IAM best practices listed on p159
> Enable SSO Â· turn on conditional access Â· enable password management Â· enforce MFA Â· enforce cloud-based MFA Â· enforce Azure AD identity protection Â· implement RBAC Â· restrict exposure of privileged accounts Â· centralize identity management Â· use Azure AD for storage authentication Â· treat identity as the primary security perimeter Â· plan for routine security improvements
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1025 â€” Why is the Azure AD Connect "staged rollout of cloud authentication" feature used?
> It allows you to test cloud authentication and migrate gradually from federated authentication
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1026 â€” The four advantages the courseware claims for Azure AD self-service password reset
> Reduced cost â€” support-assisted reset accounts for 20% of an organization's IT expenditure Â· improved user experience (no helpdesk call) Â· lower helpdesk volume Â· mobility â€” reset from any location
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1027 â€” What do Azure AD password protection agents add on-premise?
> They extend the banned password lists to the existing Windows Server AD infrastructure, so organizations can block common local words in addition to the global banned password list
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1028 â€” The SSPR areas the walkthrough configures
> Properties â€” enable SSPR and select Selected, then Save Â· Authentication methods â€” number of methods and available methods Â· Registration â€” who registers at sign-in and the re-confirmation days Â· Notifications â€” option, then Save
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1029 â€” What does Security Defaults enforce, and what is the printed effectiveness claim?
> It enforces MFA to block 99.9% of identity-related attacks, and users must register for and use Azure AD MFA with the Microsoft Authenticator app using notifications; it blocks attacks such as password spray, replay and phishing
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1030 â€” Steps to enable Security Defaults
> Azure portal â†’ Azure Active Directory â†’ Properties â†’ Manage security defaults â†’ set Enable security defaults to Yes â†’ Save
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1031 â€” The four RBAC best practices stated for Azure
> Use RBAC for least privilege and granular access control Â· assign permissions on a subscription, resource group or single resource scope Â· use built-in roles to segregate duties and grant only the access required for the job Â· grant the RBAC security reader role to security teams
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1032 â€” Azure RBAC scopes named by the courseware
> Rules: subscription Â· resource group Â· single resource â€” the walkthrough step 1 additionally searches Management groups, Subscriptions and Resource groups
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1033 â€” Azure RBAC security principal types
> User Â· group Â· service principal Â· managed identity, and managed identity splits into user-assigned and system-assigned
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1034 â€” When does Azure RBAC use a custom role instead of a built-in role?
> When the built-in roles do not meet the requirements of the organization â€” the customer then creates custom roles for the Azure resources
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1035 â€” The Add role assignment click path, in order
> Search the scope â†’ open the resource â†’ Access control (IAM) â†’ Role assignments tab â†’ Add > Add role assignment â†’ pick the role on the Roles tab â†’ Members tab: user, group or service principal, or managed identity â†’ Select members â†’ optional Description â†’ Next â†’ optional Add condition â†’ Review + assign
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1036 â€” The six best practices the courseware gives for securing privileged Azure accounts
> Turn on Azure AD PIM (limits excessive, unnecessary or misused access) Â· define at least two emergency access accounts on the *.onmicrosoft.com domain Â· make all critical administrator accounts passwordless or require MFA Â· use Microsoft Authenticator for passwordless sign-in Â· give admins a separate workstation where production tasks are not allowed Â· use privileged access workstations
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1037 â€” What makes an Azure AD emergency access account, and when is it needed?
> Highly privileged, not assigned to an individual, cloud-only on the *.onmicrosoft.com domain, at least two of them â€” used when admins' devices or the MFA service are unavailable, when MFA cannot be completed to activate a role, when the Global Administrator has left, and in a natural disaster
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1038 â€” The four emergency access account settings configured at creation
> Username Â· Name Â· a long and complex password Â· Global Administrator role (under Roles) Â· usage location â€” then Create
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1039 â€” Azure AD PIM role settings touched in the Global Administrator walkthrough
> Activation: on activation require Azure MFA, duration 2 hours, plus require justification / ticket information / approval to activate â€” Assignment: expire eligible after 1 year, expire active after 6 months, require Azure MFA and justification on active assignment
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1040 â€” The Microsoft Authenticator authentication-mode options and the consequence of one of them
> Any or Passwordless â€” each added group or user defaults to "Any" (passwordless and push notification); choosing Push prevents the use of the passwordless phone sign-in credential
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1041 â€” What is a PAW and what protects it
> The highest security configuration for extremely sensitive roles â€” a hardened workstation on a dedicated OS where local administrators are restricted from access and only sensitive job tasks run, featuring application control, application guard, credential guard, app guard, device guard and exploit guard
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1042 â€” The three advantages the courseware gives for Azure centralized identity management
> Provide a common identity for accessing both cloud and on-premise resources Â· enable administrators to manage accounts from one location Â· enhance security by preventing configuration errors
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1043 â€” Which tool does the courseware name to implement centralized identity management, and what must happen first?
> Azure AD Connect â€” it synchronizes the on-premise directory with the cloud directory. Prerequisite: users must synchronize the on-premise and cloud identity directories
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1044 â€” What the courseware prints as the benefits of using Azure AD Connect
> A common accessing identity to both cloud and on-premise resources (productivity) Â· a common hybrid identity leveraging Windows Server AD connected to Azure AD Â· conditional access by application resource, network location, device and user identity, and MFA Â· common identity reused for Office 365, SaaS and third-party apps
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1045 â€” Two reasons the courseware gives for using AD FS with the cloud directory
> AD FS overcome the authentication challenges created by the AD, and resolve the third-party authentication challenges â€” it also provides Web SSO to multiple web apps with a single account
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1046 â€” Password hash synchronization â€” what moves, in which direction, and why
> User password hashes move from an on-premise AD instance to a cloud-based Azure AD instance, to protect against leaked credentials; users keep one password for multiple Azure accounts, raising productivity and cutting helpdesk cost, and PHS can act as backup if on-premise servers fail
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1047 â€” Site-to-Site VPN in Azure â€” the three security benefits the courseware states
> Secure Connectivity (all traffic encrypted, protected against modification and eavesdropping) Â· Simplified Network Architecture (no internal-to-external IP conversion) Â· Access Control (admin defines rules simply because S2S VPN users are internal users)
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1048 â€” The two data encryption models in Microsoft Azure and who performs the crypto
> 1. Server-side â€” the Azure resource provider performs encryption and decryption; 2. Client-side â€” encryption is performed outside the Azure service provider by the service or calling application, and the provider receives data it cannot decrypt
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1049 â€” The three sub-models under the server-side encryption model
> SSE with service-managed keys (Microsoft manages the keys) Â· SSE with customer-managed keys in Azure Key Vault Â· SSE with customer-managed keys on customer-controlled hardware
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1050 â€” What the courseware warns about when you manage your own keys in Azure Key Vault
> Loss of encryption keys leads to loss of data â€” do not delete the encryption keys, but keep a backup of the creation or rotation of keys
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1051 â€” What Azure Key Vault is used for, and the three concerns it addresses plus HSM backing
> A secure storage for the keys used to encrypt data at rest in Azure services â€” secrets management (tokens, passwords, API keys), key management, certificate management (SSL/TLS), and secrets/keys protected by software or FIPS 140-2 Level 2 validated HSMs
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1052 â€” Azure Storage Service Encryption â€” the algorithm and the encryption point
> 256-bit AES â€” data is encrypted before storing and decrypted upon retrieval; it is applied to the entire Azure storage system, users can enable or disable it, and data is encrypted only when SSE is enabled
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1053 â€” Transparent Data Encryption in Azure â€” what it is and what it covers
> An SQL Azure feature that encrypts data at both the database and server levels, covering the database, backups and transaction log files at rest without modifying the application; protects Azure SQL Database, SQL Managed Instance and Data Warehouse; it must be enabled per database
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1054 â€” The five practices the courseware gives for encrypting data in transit in Azure
> Use HTTPS for Azure Storage objects and REST APIs Â· use Shared Access Signatures and enable Secure Transfer Required on storage accounts Â· use SMB 3.x for Azure File Storage Â· use client-side encryption before transfer into Azure Storage and decrypt on receipt Â· use Azure Site-to-Site (or point-to-site) VPN to encrypt between the corporate network and the Azure VNet
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1055 â€” What does "secure transfer required" actually do on an Azure storage account
> It enforces the HTTPS protocol â€” including when Shared Access Signatures and the REST APIs are used â€” so storage traffic cannot fall back to unencrypted HTTP
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1056 â€” What the courseware states about SMB 3.x in Azure File Storage
> SMB 3.0 uses encryption during transit, is available in Windows Server 2012 R2, Windows 8, Windows 8.1 and Windows 10, and allows cross-region access
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1057 â€” Site-to-Site VPN versus Point-to-Site VPN in Azure â€” the scope difference
> Site-to-Site connects the entire network (e.g., on-premise) to the Azure virtual network over a highly secure IPsec tunnel mode; Point-to-Site connects a single device to the Azure virtual network; both enable cross connectivity
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1058 â€” The values printed in the Azure Add-connection form for a Site-to-Site VPN
> Name VNet1toSite2 Â· connection type Site-to-site (IPsec) Â· virtual network gateway VNet1GW Â· local network gateway Site2 Â· shared key (PSK) â€” then click OK to create the connection
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1059 â€” What the courseware says you must do to secure inbound internet communications to an Azure VM, and the four application-level steps
> Implement SSL encryption to secure data transfer â€” get an SSL certificate, modify the service definition and configuration files, upload the certificate, then connect to the role instance via HTTPS
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1060 â€” What an endpoint ACL in Azure is used for, and what the two tool options are
> To restrict access on public endpoint IP addresses and restrict traffic to specific IP address sources â€” created and managed with PowerShell or through the Azure Management Portal (which can add, modify or remove an ACL on an endpoint)
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1061 â€” The two-step risk the courseware gives for exposing RDP/SSH to the internet
> An attacker using brute-force techniques over RDP/SSH over the internet can gain access to an Azure VM; once in, that VM becomes a launch point to compromise other VMs on the virtual network or attack network devices outside the Azure cloud
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1062 â€” The three alternatives the courseware offers instead of direct RDP/SSH over the internet
> Point-to-Site VPN, Site-to-Site VPN, and ExpressRoute â€” the protocols printed for Point-to-Site are SSTP, Open VPN and IKEv2
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1063 â€” The three security benefits the courseware states for Site-to-Site VPN
> Secure Connectivity â€” all traffic encrypted, protected against data modification and eavesdropping Â· Simplified Network Architecture â€” no internal-to-external IP address conversion Â· Access Control â€” rules defined simply because S2S VPN users are internal users
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1064 â€” ExpressRoute versus Site-to-Site VPN as the courseware describes it
> It works like Site-to-Site VPN but over a dedicated WAN link that does not go through the internet, so it is stable, faster, lower latency and more reliable, and it creates private connections between on-premises/co-located infrastructure and Azure data centers
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1065 â€” The three load-balancing options the courseware names and what each is for
> Azure Application Gateway â€” an HTTP web traffic load balancer doing end-to-end SSL encryption and SSL termination at the gateway Â· Azure Traffic Manager â€” load balances connections to services based on user locations (global, nearest data center) Â· external or internal Azure Load Balancer â€” distributes incoming requests across multiple VMs for higher availability
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1066 â€” What Azure Application Gateway offloads from the back-end web servers
> Encryption and decryption overhead â€” it terminates SSL at the gateway, implements end-to-end SSL encryption, and ensures unencrypted traffic flows to the back-end servers
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1067 â€” The Azure Application Gateway creation steps actually printed
> On the Azure homepage click Application Gateways, click create application gateway, fill in the details and click Review + create â€” no further create or Go to resource step is given
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1068 â€” The Azure Load Balancer creation steps actually printed
> On the Azure homepage click Load balancers, click Create load balancer, fill in the details and click Review + create, after validation click create, click Go to resource â€” then the load balancer is created
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1069 â€” How the courseware justifies Azure Traffic Manager performance
> Global Load Balancing routes to the nearest data center, and connectivity to the nearest data center is faster than to a distant one
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1070 â€” What do Azure NSGs control, and how many subnets/VMs can one NSG cover?
> Inbound and outbound access to subnets, VMs, and network interfaces (NICs) â€” and an NSG can be applied to multiple subnets or VMs
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1071 â€” Can Azure's default NSG rules be deleted?
> No â€” they cannot be deleted, but they can be overruled by the customers
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1072 â€” What does Azure Firewall do inside the virtual network?
> It is an easily manageable cloud-based network security service that protects Azure virtual resources, implements network connectivity policies in virtual networks, and lets customers create allow or deny network filtering rules
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1073 â€” Which rule set is a WAF on an application gateway based on, and how is it kept current?
> The OWASP Core Rule Set (CRS) 3.1, 3.0 or 2.2.9 â€” WAFs are automatically updated to protect against new vulnerabilities
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1074 â€” The Azure Firewall creation steps actually printed
> Azure homepage > create a resource > type Firewall in the search box > Create > fill details and Review + create > after validation click Create > after deployment Go to resource â€” then the firewall is created
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1075 â€” The NSG creation steps actually printed
> Azure homepage > Network security group > Create network security group > details and Review + create > after validation Create > after deployment Go to resource > Inbound security rules > Add > enter details and Save
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1076 â€” What does Microsoft Antimalware for Azure provide, and when does it alert?
> Real-time protection â€” it generates alerts on the installation and execution of malicious or unwanted software
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1077 â€” Name three Microsoft Antimalware features that are about updates
> Signature updates (automatic installation of protection signatures) Â· Antimalware Engine updates Â· Antimalware Platform updates
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1078 â€” What does the Azure Guest Agent (Fabric Agent) do in the antimalware chain?
> It runs the antimalware extension and configures its parameters, enabling the Antimalware service with default or custom configuration â€” default settings apply when no custom configuration is provided
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1079 â€” Where do Microsoft Antimalware events end up?
> The service writes them to the system OS event log under the "Microsoft Antimalware" event source; antimalware monitoring writes them as produced to the Azure Storage account, where the Azure Diagnostics extension collects and stores them in tables
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1080 â€” The four components of the Azure datacenter network topology
> Edge network Â· Wide area network Â· Regional gateways network Â· Datacenter network
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1081 â€” What is blocked by default when an Azure VM is created, and who adds the exceptions?
> All incoming and outgoing traffic is blocked by default; rules and exceptions to allow authorized traffic are added in the hypervisor packet filter by the FC agent
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1082 â€” How does the courseware characterise a network security group?
> A simple, stateful packet inspection device that creates allow/deny rules for network traffic â€” used to protect Azure subnets against uninvited traffic
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1083 â€” Name the nine Azure network security best practices printed on the slide
> Strong network controls Â· logically segment subnets Â· adopt a Zero-Trust approach Â· control routing behaviour Â· deploy perimeter networks for security zones Â· avoid internet exposure with dedicated WAN links Â· disable RDP/SSH access to VMs Â· secure critical service resources to only virtual networks Â· use virtual network appliances
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1084 â€” Why does the courseware tell you to configure user-defined routes?
> Because VMs on different subnets can still connect to other VMs on a similar virtual network â€” user-defined routes plus a security appliance stop that
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1085 â€” What does the Zero-Trust best practice combine?
> Azure AD Conditional Access based on devices, identity and network location, plus just-in-time VM access in Microsoft Defender for Cloud to lock down inbound traffic to Azure VMs
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1086 â€” What is Azure ExpressRoute, per the courseware?
> A dedicated WAN link between the Microsoft Exchange hosting provider and the on-premises location, letting connectivity providers build a private connection of on-premises networks into the Microsoft cloud â€” reaching Azure, Microsoft 365 and Dynamics 365
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1087 â€” What happens on an active geo-replication failover?
> The application starts failover to a secondary database; after the failover the secondary becomes the primary, with different connection endpoints
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1088 â€” What does the Azure Activity Log give you, and what is it scoped to?
> Insights into subscription-level events â€” it is used to collect, view and analyze the activity log
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1089 â€” Name the Activity Log filter fields printed on p239
> Timespan Â· Category Â· Subscription Â· Resource group Â· Resource (name) Â· Resource type Â· Operation name Â· Severity Â· Event initiated by Â· Open search
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1090 â€” The five VM statistics the Azure portal is said to track
> CPU percentage Â· Disk Read Bytes/s Â· Disk Write Bytes/s Â· Network in Â· Network out
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1091 â€” What is Microsoft Defender for Cloud, in the courseware's own framing?
> A cloud security posture management (CSPM) and cloud workload protection (CWP) solution that continuously assesses, secures and defends workloads across multi-cloud (AWS and GCP), Azure and on-premises
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1092 â€” Name the seven Network Watcher operational security features
> Audit Logs Â· IP Flow Verifies Â· Next Hop Â· Security Group View Â· NSG Flow Logging Â· Remote Network Monitoring Â· VPN Connectivity Issues
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1093 â€” What 5-tuple does IP Flow Verifies check, and what is it for?
> Source IP, Destination IP, Protocol, Source Port and Destination Port â€” to check if a packet is denied or allowed according to flow information
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1094 â€” How many Azure security checklist items does the courseware print in the body, and what do they cover?
> 19 items, all Azure AD identity, access, consent and guest-user settings â€” no network, data, encryption, antimalware or monitoring item is printed on pp243-244
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1095 â€” The first three checklist items
> Ensure MFA is enabled for all users Â· ensure there are no guest users Â· use RBAC to manage the access to resources
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1096 â€” Which checklist settings control password-reset behaviour, and to what values
> Memorize multi-factor authentication on devices they trust = disabled Â· number of processes required to reset = two Â· number of days before users are asked to re-confirm their authentication report = not zero Â· caution users on password resets = yes Â· notify all admins when other admins reset their password = yes
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1097 â€” The guest-user checklist items
> No guest users Â· guest user agreements are limited = yes Â· members can request = no Â· guests can invite = no
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1098 â€” The group and administration checklist items
> Entrance to the Azure AD administration portal is limited Â· users can create security associations = none Â· self-service group administration enabled = no Â· users who can handle security groups = none Â· users can create Office 365 groups = no
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1099 â€” Features listed under LO#06
> GCP shared responsibility model Â· GCP IAM features and best practice to implement IAM securely Â· GCP encryption and key management (data at rest / data in transit) Â· GCP network security measures Â· GCP data storage security Â· GCP monitoring and logging
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1100 â€” In Google's shared responsibility model, which rows stay with the **user** at each layer
> IaaS: guest OS/data/content down to content (everything above network) Â· PaaS: deployment Â· usage Â· access policies Â· content Â· SaaS: access policies Â· content â€” content and access policies are the customer's at all three layers
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1101 â€” The three divisions of the GCP IAM model
> Principal (an identity â€” an email address) Â· Roles (a collection of permissions) Â· Policy (binds a set of members to a role, via one or more bindings)
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1102 â€” The seven GCP IAM members
> Google account Â· Service account Â· Google group Â· Google Workspace account Â· Cloud Identity domain Â· All authenticated users Â· All users
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1103 â€” GCP IAM stated purpose
> Granular access to specific Google Cloud resources, preventing unauthorized access, under POLP (principle of least privilege) â€” administrators control access by implementing IAM policies
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1104 â€” Definition of a GCP service account
> A special account that belongs to an application or VM instance, but not to end-user, to run the specified account code hosted in Google cloud â€” multiple service accounts can be created for different logical components of an application
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1105 â€” GCP permission format and the printed examples
> `<service>.<resource>.<verb>` â€” e.g. `pubsub.subscriptions.consume`; calling `topics.publish()` needs `pubsub.topics.publish`; permissions correlate one-to-one with REST API methods
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1106 â€” The 8 GCP IAM security best practices
> Grant least privileges to avoid primitive roles Â· Create separate service account Â· Check granted policy on each resource Â· Restrict who acts as service accounts Â· Rotate service account keys Â· Restrict access to create and manage service accounts Â· Grant predefined roles Â· Use logging roles for log auditing
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1107 â€” Project-level vs fine-grained grant
> Fine-grained â€” grant at the resource instead of the project (e.g. a single bucket â†’ Storage Admin `roles/storage.admin`); Project level â€” the grant is inherited by all resources of that project, e.g. all buckets or all Compute Engine instances instead of individual ones
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1108 â€” Google group vs Cloud Identity domain
> Google group = collection of Google accounts and service accounts with one email address but no login credentials, so policies apply to the whole group without editing the IAM policy; Cloud Identity domain = virtual group of all Google accounts whose users cannot access the G Suite domain applications
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1109 â€” When is a GCP **basic role** acceptable
> When a predefined role is not offered by the service Â· when you want to give a project broader permission Â· in test/development environments Â· for a small team that does not need granular permissions â€” otherwise assign the minimum predefined or custom role
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1110 â€” The four service-account-key rotation steps, in order
> Create a new key â†’ switch apps to utilize the new key â†’ disable the old key â†’ delete the old key if certain it is no longer required
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1111 â€” Service account keys vs encryption keys
> Distinct â€” data is normally encrypted using encryption keys, and safe access to Google Cloud APIs is achieved via service account keys; never check the keys into source code or leave them in the Downloads directory
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1112 â€” Service Account User role: project-level vs single-account grant
> Project level â†’ access to all service accounts in the project including any future ones; single account â†’ access only to that account, and the principal can pretend to be it (roles/iam.serviceAccountUser)
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1113 â€” How does the courseware grant temporary access
> Conditional role binding for time-bounded access, so a user cannot reach the resource after the stated expiration date and time â€” add an IAM condition to an existing binding via the Condition Builder (condition type Expiring Access, by From, Time Date range) or the Condition Editor (CEL expression, Run Linter to validate)
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1114 â€” Which GCP roles let you change permissions without full administrative access
> Project IAM Admin and Folder IAM Admin â€” grant them only to those who must change permissions; grant owner (roles/owner) only when universal access is necessary
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1115 â€” The three GCP primitive roles and what each grants
> Owner â€” all editor permissions plus project billing setup and management of all project resources Â· Editor â€” viewer permissions plus, for most GCP services, permission to modify resources Â· Viewer â€” read-only and viewing
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1116 â€” When may a primitive role be granted
> Only when the GCP service does not provide a predefined role Â· to grant broader permissions for a project (e.g. development or test environments) Â· for small teams that do not require granular permissions
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1117 â€” Separate-service-account rules
> One service account per service that needs a different permission set Â· treat every application component as a separate trust boundary Â· grant only the required permissions to each service account Â· minimum permission based on requirement Â· up to 100 service accounts per project
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1118 â€” Service account creation click path, in order
> IAM & admin â†’ service accounts â†’ CREATE SERVICE ACCOUNT â†’ enter details â†’ Create â†’ select the role â†’ CONTINUE â†’ CREATE KEY and choose the JSON file with the private key â†’ DONE (viewable in the IAM PERMISSIONS tab)
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1119 â€” Why caution is needed when granting a service account user role
> At project level it reaches all service accounts in the project, including future ones; at service account level it reaches that account â€” and the service account users indirectly have access to all resources of the service account
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1120 â€” The two categories of GCP service account key
> GCP-managed â€” cannot be downloaded or automatically rotated, used within two weeks, utilized by GCP services such as App Engine and Compute Engine; User-managed â€” the user creates, downloads and manages them, and they expire after ten years
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1121 â€” The courseware's definition of key rotation
> Generate a new key version of the key and mark that version as the primary version â€” done periodically; the user needs roles/cloudkms.admin, roles/owner or roles/editor
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1122 â€” Automatic vs manual key rotation
> Automatic â€” set a rotation schedule that determines when the key is rotated (gcloud kms keys update) Â· Manual â€” generate a new key version, disable automatic rotation, and set the new version as primary (gcloud kms keys versions create â€¦ primary)
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1123 â€” What happens to previous key versions after rotation
> They are neither disabled nor destroyed â€” this prevents data loss, so data encrypted under the old version is NOT automatically re-encrypted; the user must decrypt and re-encrypt with the new version, and may schedule the old version for destruction only once it protects no data
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1124 â€” Which service account API methods automate rotation
> serviceAccount.keys.create() and serviceAccount.keys.delete()
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1125 â€” The four levels at which a GCP IAM policy can be set, and what each is inherited by
> Organization â€” policies are inherited by all resources Â· Folder â€” the highest folder level's roles are inherited by the projects and other folders in the parent folder Â· Project â€” the trust boundary; its roles are inherited by all resources Â· Resource â€” lowest-level roles, e.g. Genomics data, Compute Engine instances and Pub/Sub topics, apart from Cloud Storage
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1126 â€” The two constraint names printed for disabling service account creation
> Figure and both snippets: constraints/iam.disableServiceAccountCreation Â· body sentence: iam.disableServiceAccountKeyCreation (which "will not allow the creation of user-managed credentials") â€” the courseware prints both
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1127 â€” How to centralize the management of service accounts
> Disable the creation of new service accounts by enforcing the boolean constraint in an organization policy â€” console: IAM & Admin â†’ Organization policies â†’ select the organization â†’ Disable Service Account Creation â†’ Edit â†’ Applies to Customize â†’ Enforcement On â†’ Save
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1128 â€” What does `Inherit parent's policy` do
> It lets the resource inherit the rules of the parent's policy, so a child no longer carries its own overridden policy â€” the policy summary then shows the Inherited policy / Google-managed default alongside the Current policy
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1129 â€” How is an effective IAM policy formed for a resource
> By combining the policy inherited from the parent with the policy set at the resource itself â€” so the hierarchy is organization (root) â†’ projects (children) â†’ other resources (descendants)
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1130 â€” Why grant pre-defined roles instead of primitive roles
> To implement granular access to specific GCP resources and prevent unwanted access to other resources â€” predefined roles provide fine-grained access control, and a specific role is given to a resource type (multiple roles may be given to the same user); e.g. roles/pubsub.publisher only allows publishing messages for a Pub/Sub topic
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1131 â€” At which levels can a GCP custom role be created, and what is the drawback
> Organization and project level only â€” never at the folder level. Drawback: because Google does not maintain custom roles, they are not updated automatically by the GCP. Needed when predefined roles do not satisfy the organization's requirements
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1132 â€” `roles/logging.viewer` vs `roles/logging.privateLogViewer`
> viewer = read-only access to logging features, and does NOT give access to Access Transparency logs or Data Access audit logs Â· privateLogViewer = the log viewer role PLUS read access to Access Transparency logs and Data Access audit logs
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1133 â€” Which logging role is granted to service accounts for writing logs, and which for log metrics and export sinks
> `roles/logging.logWriter` â€” to service accounts, giving applications permission to write logs Â· `roles/logging.configWriter` â€” log metrics, log exclusion, and exporting log entries to a sink Â· `roles/logging.admin` â€” all logging permissions
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1134 â€” Which roles can read Data Access audit logs
> Only `roles/logging.privateLogViewer` and `roles/owner` (full access to logging, Access Transparency logs and Data Access audit logs) â€” `roles/viewer`, `roles/logging.viewer` and `roles/editor` are all excluded, and `roles/editor` also cannot create export sinks
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1135 â€” Where do you pick permissions from when building a custom role with logging permissions
> Select an API permission for the logging API role; select from console permissions for the role that grants Log Viewer; browse the `gcloud` tool for the role that grants `gcloud` logging
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1136 â€” At which layer does Google encrypt data at rest, and what protects what
> Several layers: Application â†’ Platform â†’ Infrastructure â†’ Hardware. At the hardware device layer Google encrypts hard disks and solid-state drives with a device-level key; at the storage level data are broken into chunks of different sizes and each chunk is encrypted with a distinct encryption key, and those keys do not match each other even for the same customer on the same system
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1137 â€” KEK vs DEK in Google Cloud KMS â€” who stores what
> KMS stores the Key Encryption Keys (KEKs); the DEKs are generated locally, encrypt the data, and are then wrapped by the KEKs. The encrypted data chunk is stored with the wrapped DEK. Because one key envelops another this is called Envelope Encryption
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1138 â€” The Cloud KMS hierarchy, top to bottom
> Project (run KMS in a separate project, because primitive cloud IAM roles can otherwise reach all its resources) â†’ Location (geographical region where requests are processed and keys are stored) â†’ Key Ring (collection of keys for an organizational purpose, specific to a project; keys inherit the property from the key rings) â†’ Key (the actual bits used for encryption) â†’ Key version
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1139 â€” Customer-supplied vs customer-managed encryption keys
> Customer-supplied = the customer supplies their own keys as an extra layer over standard cloud storage encryption, and creates/manages them Â· Customer-managed = the customer uses keys generated by KMS as the additional layer, and generates/manages them
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1140 â€” `gcloud` commands to create a key ring and an encryption key (as printed on pp280-281)
> `gcloud kms keyrings create $KEYRING_NAME --location global` then `gcloud kms keys create $CRYPTOKEY_NAME --location global --keyring $KEYRING_NAME --purpose encryption` â€” the p281 body prints the key name as `democode` while p280's text prints `demolab`
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1141 â€” How is Cloud KMS enabled, in the console and on the command line
> CLI: `gcloud services enable cloudkms.googleapis.com`. Console: Google console dropdown menu, IAM & admin, Audit Logs; go to the Filter Table and select Title: Cloud Key Management Service (KMS) API; check the Cloud Key Management Service (KMS) API box, select the required service, and click Save
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1142 â€” The three defense-in-depth network security principles
> Secure internet-facing services Â· Secure VPC for private deployments Â· Micro-segment access to applications and services
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1143 â€” Which two GCP services together protect against Layer 3 and Layer 4 volumetric DDoS on publicly exposed data
> Place the services behind the Google Cloud HTTP(S) Load Balancer and deploy Google Cloud Armor â€” together they provide protection from Layer 3 and Layer 4 volumetric DDoS attacks
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1144 â€” What do WAF policies at the edge prevent, and what range of attributes do WAF custom rules filter
> Preconfigured WAF rules prevent cyberattacks such as SQL injection and cross-site scripting; WAF custom rules filter internet traffic across Layer 3 through Layer 7 attributes
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1145 â€” Host project vs service project in a shared VPC
> A shared-VPC organization consists of host projects connected to service projects; the host project network IS the shared VPC network, which is centrally managed across multiple projects over internal IPs. Run the setup from the host project â€” Shared VPC plus IAM separates network administration from project administration
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1146 â€” Firewall rules vs routes in GCP
> Firewall rules allow or deny traffic to and from VPC-attached resources (Compute Engine VMs, GKE clusters) and are targeted at specific VMs with network tags; incoming traffic from outside the network is blocked by default. Routes define the paths network traffic takes from a VM instance to another destination, inside or outside the VPC, resolved by the VM instance controller to a next hop in routing order
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1147 â€” How do you micro-segment in GCP
> VM-based applications â€” Google VPC firewall rules regulate communication between them; GKE-based applications â€” network policies set on the Google GKE clusters control container-to-container communication. Note VPC networks are global resources, not tied to a zone or region, and a project can hold several of them depending on the set organizational policy
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1148 â€” How does GCP mitigate a DoS attack by default
> The data centers' fiber-optic Internet connection passes through several layers of software and hardware load balancers; the load balancers report incoming traffic to a central DoS service, which on detecting an attack configures the load balancers to drop or throttle the attack traffic. The central DoS service also gets application-layer information from the GFE instances (which the load balancers cannot see) and configures them to drop or throttle attack traffic
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1149 â€” What does the Google Front End (GFE) provide and do
> GFEs provide public IP address hosting of a public DNS name, DoS protection, and TLS termination; GFE applies DoS protections that terminate user traffic and automatically scale to absorb attacks before they reach the user's compute instances
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1150 â€” The ten GCP DDoS mitigation best practices
> Reduce the attack surface (Google Cloud Virtual Network, subnets/networks, firewall rules, tags, IAM, anti-spoofing, inter-VPC isolation) Â· isolate internal traffic (no public IPs, NAT gateway or SSH bastion, internal load balancing) Â· enable proxy-based load balancing (HTTP(S) or SSL proxy, multi-region) Â· scale to absorb (GFE, Anycast load balancing, autoscaling) Â· protect with CDN offloading (Google Cloud CDN, CDN Interconnect) Â· deploy third-party DDoS protection or Google Cloud Launcher solutions Â· deploy App Engine with a dos.yaml IP/IP-network blocklist Â· restrict Google Cloud Storage with signed URLs Â· API rate limits on the Compute Engine API Â· enforce Compute Engine resource quotas
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1151 â€” Which GCP best practice is stated as avoiding IP address conflicts
> Disable default networks â€” disable creation of default networks in new projects, delete them in existing projects, avoid IP address conflicts by first planning network and IP address allocation across connected deployments and projects, and limit multiple VPCs to one per project to enforce access control effectively
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1152 â€” The four network monitoring tools named as telemetry
> VPC Flow Logs and Firewall Rules Logging (real-time visibility into traffic) Â· Firewall Insights (reviewing firewall rules) Â· Network Intelligence Center (how network topology and architecture are performing) Â· Connectivity Tests (insight into the firewall rules and policies applied to the network path)
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1153 â€” Why use service accounts in firewall rules
> To enforce isolation without depending on an IP address as the sole identifier of a workload â€” combine with hierarchical firewall policies (rules applying to all networks regardless of network-level rules) and define folder-level rules to cover only portions of an organization
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1154 â€” Which three tools does the courseware name for monitoring logs
> GCP Logging from Console Â· Cloud Audit Logs Â· Google Cloud's operations suite â€” and Google Cloud services generate structured logs that can be easily queried
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1155 â€” The four GCP Logging console features
> Predefined or custom queries Â· create metrics from logs Â· a live stream of logs from multiple resources across the deployed cloud Â· export logs to other destinations (Google Cloud Storage, Google BigQuery, or Google Cloud Pub/Sub)
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1156 â€” The three Cloud Audit Logs types and the roles that read them
> Admin Activity Audit logs â€” Logging/Logs Viewer or Project/Viewer Â· Data Access Audit logs â€” Logging/Private Logs Viewer or Project/Owner Â· System Event Audit logs â€” Logging/Logs Viewer or Project/Viewer. Audit the access to service account keys regularly, and view them from the console by clicking Activity
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1157 â€” What is Google Cloud's Operation Suite and what does the log router do
> A collection of management tools that integrate monitoring, logging and trace managed services for applications and systems on Google Cloud and beyond, used to collect metrics, traces and logs and build dashboards, charts and alerts. All logs â€” audit, platform and user â€” are sent to the Cloud Logging API and pass through the log router, which checks each entry against existing rules to decide which to discard, which to ingest, and which to include in exports
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1158 â€” Which compliance standards are printed for GCP
> SSAE16/ISAE 3402 Type II (including SOC2 and 3) Â· ISO 27001, 27017, 27018 Â· FedRamp Â· PCI-DSS Â· HIPAA â€” with the note that GCP supports HIPAA compliance but it must be calculated by the customer
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1159 â€” The four administrative-hygiene items on the Google security checklist
> Enforce two-step verification for users Â· do not use a super admin account for daily activities Â· do not remain signed into an idle super admin account Â· do not automatically share the contact information
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1160 â€” The seven NIST recommendations for cloud security
> Assess risks posed to client data, software, and infrastructure Â· select appropriate deployment model according to the requirements Â· ensure audit procedures for data protection and software isolation Â· renew SLAs if security gaps are found between the security requirements of an organization and the standards of the cloud provider Â· establish appropriate incident detection and reporting mechanisms Â· analyze the security objectives of the organization Â· determine who is responsible for data privacy and security issues in the cloud
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1161 â€” The four organization/provider compliance checklists and their axes
> Table 12.5 Security Team (8 rows, p308) Â· Table 12.6 Operations (18 rows, pp309-310) Â· Table 12.7 Technology (8 rows, p310) Â· Table 12.8 Management (9 rows, pp310-311)
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1162 â€” Table 12.6 â€” the operational rows about forensics, multi-tenancy and exit
> Does the CSP have clear policies and procedures to handle digital evidence in the cloud infrastructure Â· does the CSP have defined procedures to support the organization in the case of incidents involving several clients in a multi-tenant environment Â· does the CSP provide flexibility of service relocation and switchovers Â· does the CSP provide 24/7 support for cloud operations and security-related issues
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1163 â€” Table 12.7 â€” the four failure modes of cloud network design
> Network congestion Â· misconnection Â· misconfiguration Â· lack of resource isolation. Plus: appropriate access controls such as federated SSO, data separation between the organization and customer information at runtime and during backup including data disposal, and authentication/authorization/key management mechanisms in a cloud environment
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1164 â€” Table 12.8 â€” the governance rows
> Is everyone aware of their cloud security responsibilities Â· is there a mechanism for assessing the security of a cloud service Â· does business governance mitigate the security risks from cloud-based "shadow IT" Â· does the organization know the jurisdictions within which its data can reside Â· is there a mechanism for managing cloud-related risks Â· does the organization understand the data architecture required to operate with appropriate security at all levels Â· can the organization be confident regarding end-to-end service continuity across several cloud service providers Â· does the provider comply with all relevant industry standards such as the UK Data Protection Act Â· does the compliance function understand the specific regulatory issues related to the adoption of cloud services
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1165 â€” Five best practices that target identity and access
> Prohibit user credential sharing among users, applications, and services Â· implement strong authentication, authorization, and auditing mechanisms Â· leverage strong two-factor authentication techniques where possible Â· enforce stringent registration and validation processes Â· use VPNs to secure the client data
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1166 â€” Scout Suite â€” the entire description the courseware gives
> An open source multi-cloud security-auditing tool that enables the security posture assessment of cloud environments. Using the APIs exposed by cloud providers it gathers configuration data for manual inspection and highlights risk areas. Source: https://github.com
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1167 â€” Qualys Cloud Platform â€” description, supported clouds, and readable features
> An end-to-end IT security solution providing a continuous, always-on assessment of the global security and compliance posture, with visibility across all IT assets irrespective of location. Supported/planned: Amazon Web Services Â· Microsoft Azure (beta) Â· Google Cloud Platform Â· Alibaba Cloud (early alpha) Â· Oracle Cloud Infrastructure (early alpha). Features: sensors provide continuous visibility Â· all data can be analyzed in real time Â· respond to threats immediately Â· visualize results in one place with AssetView
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1168 â€” CloudPassage Halo â€” the ten printed features
> Workload firewall management Â· multifactor network authentication Â· configuration security monitoring Â· software vulnerability assessment Â· file integrity monitoring Â· server account management Â· event logging and alerting Â· Halo REST API
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1169 â€” Core CloudInspect â€” what it is and what it enables
> Validates when a cloud deployment is secure and gives actionable remediation information when it is not, using proactive real-world security tests with the techniques attackers use to breach AWS systems. Enables users to verify AWS deployments against current attack techniques Â· pinpoint OS and service vulnerabilities with no false positives Â· measure susceptibility to SQL injection, cross-site scripting and other web-application attacks Â· validate controls required by industry and government regulations Â· get actionable information to apply patches and code fixes Â· certify systems before they go live
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1170 â€” The nine tools listed with no description
> Nessus Enterprise for AWS Â· Symantec Cloud Workload Protection Â· Alert Logic Â· Deep Security Â· SecludIT Â· Panda Cloud Office Protection Â· Data Security Cloud Â· Cloud Application Control Â· Intuit Data Protection Services â€” the courseware prints each with a vendor URL and nothing else
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1171 â€” What the p316 module summary claims about AWS shared responsibility
> Three models â€” shared responsibility model for infrastructure services, for container services, and for abstract services. Note this conflicts with pp. 40-43, which teach one AWS model split into Inherited Controls and Shared Controls plus a six-item customer responsibility list
> Source: [[12-LO07b-Cloud-Security-Tools]]

## Verified external items

> Cards matched word-for-word against the module PDFs during the external-set audit. Set ids recorded per item below.

> [!question]- V001 â€” Public key infrastructure
> is treated as the most effective method for providing verification during electronic transactions  _(Mod 03 p82)_
> Source: [[03-LO04-Cryptographic-Techniques]] Â· verified set 617277655

> [!question]- V002 â€” Secure Hashing Algorithm (SHA)
> generate a cryptographically one-way hash and is published by NIST as a Federal Information Standard  _(Mod 03 p94)_
> Source: [[03-LO05-Cryptographic-Algorithms]] Â· verified set 617277655

> [!question]- V003 â€” Digital Signature Algorithm
> It is a Federal Information Processing Standard (FIPS) for digital signatures.  _(Mod 03 p90)_
> Source: [[03-LO05-Cryptographic-Algorithms]] Â· verified set 617277655

> [!question]- V004 â€” Network Address Translation (NAT)
> firewall technology helps hide the internal network's configuration and thereby reduces the success of attacks on the network or system. It can act as a firewall filtering technique where it allows only those connections that originate inside a network and can block the connections that originate outside the network.  _(Mod 04 p23)_
> Source: [[04-LO02-Firewall-Technologies]] Â· verified set 617277655

> [!question]- V005 â€” Application proxy
> An application-level proxy works as a proxy server. It correlates with the gateway server and separates the enterprise network from the Internet.  _(Mod 04 p20)_
> Source: [[04-LO02-Firewall-Technologies]] Â· verified set 617277655

> [!question]- V006 â€” Stateful multi-layer inspection
> These firewalls filter packets at the network layer, determine whether session packets are legitimate, and evaluate the contents of packets at the application layer.  _(Mod 04 p19)_
> Source: [[04-LO02-Firewall-Technologies]] Â· verified set 617277655

> [!question]- V007 â€” Firewalk
> is used for reconnaissance purpose where it discovers firewall rules using an IP TTL expiration technique.  _(Mod 04 p62)_
> Source: [[04-LO06-Firewall-Implementation-Deployment]] Â· verified set 617277655

> [!question]- V008 â€” Security Reference Monitor (SRM)
> enforces an access control policy (ACL) over the ability of subjects to carry out operations on objects in a system. It is responsible for controlling access of a user to Windows resources.  _(Mod 05 p17)_
> Source: [[05-LO02-Windows-Security-Components]] Â· verified set 617277655

> [!question]- V009 â€” Local Security Authority Subsystem (LSASS)
> implements local security policies privileges granted to users and groups, system security auditing settings, user authentication, and sends security audit messages to the event log.  _(Mod 05 p19)_
> Source: [[05-LO02-Windows-Security-Components]] Â· verified set 617277655

> [!question]- V010 â€” Security Accounts Manager (SAM)
> is a database that stores the logon credentials of local users and groups. It is a user-mode component that saves the data that is used by LSASS.  _(Mod 05 p21)_
> Source: [[05-LO02-Windows-Security-Components]] Â· verified set 617277655

> [!question]- V011 â€” Network logon service (NetLogon)
> a service or a dynamic-link library file that runs continuously in the background. Therefore, it will not stop running unless it is forcibly stopped, or it incurs a runtime error. It can be stopped or restarted using the command-line terminal. It is used for AD logons.  _(Mod 05 p30)_
> Source: [[05-LO02-Windows-Security-Components]] Â· verified set 617277655

> [!question]- V012 â€” Windows logon application (WinLogon)
> used when a user wants to login to system locally. It is a user-mode running process and is responsible for managing user authorization sessions. It is activated when the system is turned on and runs in the background  _(Mod 05 p27)_
> Source: [[05-LO02-Windows-Security-Components]] Â· verified set 617277655

> [!question]- V013 â€” CPs
> a Windows security component. Credential providers (CPs) are in-process component object model (COM) objects. They run in the LogonUI process and are used to get username and password, smartcard PIN, or biometric data.  _(Mod 05 p29)_
> Source: [[05-LO02-Windows-Security-Components]] Â· verified set 617277655

> [!question]- V014 â€” Windows Integrity Control (WIC)
> is an access control mechanism for controlling the interactions between objects based on their integrity or level of trustworthiness.  _(Mod 05 p41)_
> Source: [[05-LO03-Windows-Security-Features]] Â· verified set 617277655

> [!question]- V015 â€” Microsoft Windows Defender Credential Guard (WDCG)
> protects login credentials by restricting their interaction with the components of the system. When Credential Guard is enabled, only privileged software can access the credentials.  _(Mod 05 p81)_
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]] Â· verified set 617277655

> [!question]- V016 â€” User Account Control (UAC)
> is a key access control enforcement feature in Windows that improves the security of the OS by limiting application software to standard user privileges until an administrator authorizes an elevation  _(Mod 05 p98)_
> Source: [[05-LO07-User-Access-Management]] Â· verified set 617277655

> [!question]- V017 â€” Just Enough administration (JEA)
> a security technology used to limit the number of cmdlets or administration privileges of administrator, user, or service accounts.  _(Mod 05 p106)_
> Source: [[05-LO07-User-Access-Management]] Â· verified set 617277655

> [!question]- V018 â€” IoT User applications
> These applications help change the behavior of the application controls.  _(Mod 08 p13)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V019 â€” IoT Control applications
> Control applications send automatic commands and alerts to actuators and helps in investigating problematic cases and enhancing security by identifying security breaches.  _(Mod 08 p12)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V020 â€” IoT Gateways
> Gateways are devices through which data are transmitted from things to the cloud and vice versa.  _(Mod 08 p11)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V021 â€” IoT Streaming data processors
> These processors ensure that no data can be lost or corrupted  _(Mod 08 p11)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V022 â€” IoT Cloud layer
> his layer consists of servers hosted in the cloud that accept, store, and process the sensor data received from IoT gateways.  _(Mod 08 p15)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V023 â€” IoT Communication layer
> The communication layer includes the components of communication protocols and networks used for connectivity and edge computing.  _(Mod 08 p14)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V024 â€” IoT Process Layer
> The process layer gathers information and processes the received information. It includes decision making based on the information derived from policies and procedures of IoT computing.  _(Mod 08 p15)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V025 â€” Device-to-Device model
> In this type of communication, connected devices interact with each other through the Internet but primarily use protocols such as ZigBee, Z-Wave, or Bluetooth.  _(Mod 08 p16)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V026 â€” Device-to-Cloud model
> In this type of communication, devices communicate with the cloud, rather than directly communicating with the client, to send or receive data or commands.  _(Mod 08 p17)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V027 â€” Device-to-Gateway model
> In the device-to-gateway communication model, the IoT device communicates with an intermediate device called a gateway, which in turn communicates with a cloud service.  _(Mod 08 p17)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] Â· verified set 617277655

> [!question]- V028 â€” JTAG
> It is a standard interface to test and debug chips with debugging software to know how a chip respond to multiple commands.  _(Mod 08 p31)_
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]] Â· verified set 617277655

> [!question]- V029 â€” DigiCert IoT Security Solutions
> It protect private data and home networks while preventing unauthorized access using PKI-based security solutions for consumer IoT devices.  _(Mod 08 p116)_
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]] Â· verified set 617277655

> [!question]- V030 â€” AT&T
> AT&T developed The CEO's Guide to Securing the Internet of Things  _(Mod 08 p135)_
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]] Â· verified set 617277655

> [!question]- V031 â€” U.S Department of Homeland Security
> U.S DHS developed Strategic Principles for Securing the Internet of Things.  _(Mod 08 p128)_
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]] Â· verified set 617277655

> [!question]- V032 â€” ENISA
> ENISA developed 'Baseline Security Recommendations for Internet of Things  _(Mod 08 p135)_
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]] Â· verified set 617277655

> [!question]- V033 â€” Application Patch Management
> Application patch management is the process of ensuring the security of applications on hosts by regularly deploying new or missing patches.  _(Mod 09 p68)_
> Source: [[09-LO03-Application-Patch-Management]] Â· verified set 617277655

> [!question]- V034 â€” # setfacl -x u:guest test
> remove all access ACL rules of test file for the guest user.  _(Mod 10 p18)_
> Source: [[10-LO02-Data-Access-Controls]] Â· verified set 617277655

> [!question]- V035 â€” # setfacl -m u:user1:rwx test
> set read and write permission in the ACL of test file for the guest.  _(Mod 10 p18)_
> Source: [[10-LO02-Data-Access-Controls]] Â· verified set 617277655

> [!question]- V036 â€” # setfacl -m d:o:rx /Testdir
> This command is used to set default ACL for test directory.  _(Mod 10 p18)_
> Source: [[10-LO02-Data-Access-Controls]] Â· verified set 617277655

