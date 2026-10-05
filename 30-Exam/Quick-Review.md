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

> [!question]- 0001 — Risk formula?
> Risk = Asset + Threat + Vulnerability
> Source: [[01-LO01-Essential-Terminologies]]

> [!question]- 0002 — Attack formula?
> Attack = Motive (Goal) + Method (TTPs) + Vulnerability
> Source: [[01-LO01-Essential-Terminologies]]

> [!question]- 0003 — Why are insider attacks more dangerous than external?
> Insiders know network architecture, security policies, and regulations; defenses typically focus on external attacks.
> Source: [[01-LO01-Essential-Terminologies]]

> [!question]- 0004 — Three classes of security vulnerabilities?
> Technological (protocol/OS/device), Configuration (accounts, misconfig, defaults), Security policy (unwritten, gaps, awareness).
> Source: [[01-LO01-Essential-Terminologies]]

> [!question]- 0005 — Two types of DoS and examples?
> Bandwidth (flood traffic) and Connectivity (exhaust resources); e.g. TCP SYN flood, UDP flood, ICMP Smurf flood, intermittent flooding.
> Source: [[01-LO02-Network-Level-Attacks]]

> [!question]- 0006 — How does a DHCP starvation attack work and two mitigations?
> Floods DHCP server with fake DHCP requests (Gobbler) to exhaust the IP pool → DoS. Mitigate with port security and DHCP snooping.
> Source: [[01-LO02-Network-Level-Attacks]]

> [!question]- 0007 — Vertical vs horizontal privilege escalation?
> Vertical = same account → higher-privilege account; Horizontal = one user account → another with equal privileges.
> Source: [[01-LO02-Network-Level-Attacks]]

> [!question]- 0008 — Why is ARP easy to poison?
> ARP provides no authenticity verification; hosts even accept unsolicited ARP replies.
> Source: [[01-LO02-Network-Level-Attacks]]

> [!question]- 0009 — XSS definition?
> Injection of client-side script into dynamic web pages viewed by other users, that executes in the victim's browser.
> Source: [[01-LO03-Application-Level-Attacks]]

> [!question]- 0010 — Requirement for a CSRF attack?
> Three things: a user, a trusted website, and a malicious website.
> Source: [[01-LO03-Application-Level-Attacks]]

> [!question]- 0011 — Which cookie attribute prevents XSS-based session hijacking?
> HttpOnly — if the server does not set HttpOnly on session cookies, client-side script injection can enable session hijacking.
> Source: [[01-LO03-Application-Level-Attacks]]

> [!question]- 0012 — Piggybacking vs tailgating?
> Piggybacking: an authorized person lets an unauthorized person pass a secure door. Tailgating: unauthorized person with fake badge follows an authorized person through a key-access door.
> Source: [[01-LO04-Social-Engineering-Attacks]]

> [!question]- 0013 — Two classes of social engineering attacks?
> Human-based (physical presence needed) and computer-based (remote credential extraction).
> Source: [[01-LO04-Social-Engineering-Attacks]]

> [!question]- 0014 — Types of malicious email redirects?
> Referrer-based, user-agent-based, cookie-based, and OS-based.
> Source: [[01-LO05-Email-Attacks]]

> [!question]- 0015 — Email bomb types?
> List linking, attachment, mass mailing, reply all, zip bomb.
> Source: [[01-LO05-Email-Attacks]]

> [!question]- 0016 — Difference between bluesnarfing and bluebugging?
> Bluesnarfing steals information via Bluetooth; bluebugging gains control over the device via Bluetooth.
> Source: [[01-LO06-Mobile-Device-Attacks]]

> [!question]- 0017 — How is Android rooting implemented?
> Exploiting firmware vulnerabilities and copying the su binary to a PATH location (e.g. /system/xbin/su) with executable permissions via chmod.
> Source: [[01-LO06-Mobile-Device-Attacks]]

> [!question]- 0018 — What is a wrapping attack?
> During SOAP message translation in the TLS layer, the attacker duplicates the body, modifies the original, and sends it as a legitimate user; the server authenticates the duplicated signature.
> Source: [[01-LO07-Cloud-Specific-Attacks]]

> [!question]- 0019 — What is a Man-in-the-Cloud attack?
> Advanced MITM exploiting cloud synchronization services (Google Drive, DropBox) via stolen sync tokens for data compromise, C&C, and exfiltration.
> Source: [[01-LO07-Cloud-Specific-Attacks]]

> [!question]- 0020 — Name five side-channel attack kinds.
> Timing attack, data remanence, acoustic cryptanalysis, power monitoring, differential fault analysis.
> Source: [[01-LO07-Cloud-Specific-Attacks]]

> [!question]- 0021 — Wardriving tools?
> KisMAC, NetStumbler, WaveStumbler.
> Source: [[01-LO08-Wireless-Network-Attacks]]

> [!question]- 0022 — What is an evil twin AP?
> A fraudulent access point that appears legitimate, used for MITM to intercept TCP sessions or SSL/SSH tunnels.
> Source: [[01-LO08-Wireless-Network-Attacks]]

> [!question]- 0023 — Two fragmentation attack forms?
> Ping of Death (oversized fragmented ICMP) and Tiny Fragment (small fragments leak TCP header, evade filtering).
> Source: [[01-LO08-Wireless-Network-Attacks]]

> [!question]- 0024 — ZTA operating components?
> Policy Engine (PE) decides permitted traffic, Policy Administrator (PA) communicates the decision, Policy Enforcement Point (PEP) blocks or permits requests.
> Source: [[01-LO09-Supply-Chain-Attacks]]

> [!question]- 0025 — Two methods for finding supply-chain vulnerabilities?
> Continuous (automated) vulnerability scanning and penetration testing with honeypots.
> Source: [[01-LO09-Supply-Chain-Attacks]]

> [!question]- 0026 — What is a honeytoken?
> A fake resource posing as private information that activates a signal when attackers interact with it, alerting the organization and detailing the breach technique.
> Source: [[01-LO09-Supply-Chain-Attacks]]

> [!question]- 0027 — CEH five hacking phases?
> Reconnaissance, Scanning, Gaining Access, Maintaining Access, Clearing Tracks.
> Source: [[01-LO10-Hacking-Methodologies-Frameworks]]

> [!question]- 0028 — Lockheed Martin Cyber Kill Chain phases?
> Reconnaissance, Weaponization, Delivery, Exploitation, Installation, Command and Control, Actions on Objectives.
> Source: [[01-LO10-Hacking-Methodologies-Frameworks]]

> [!question]- 0029 — MITRE ATT&CK Enterprise matrices and source of its 11 tactics?
> Enterprise, Mobile, and PRE-ATT&CK matrices; the 11 Enterprise tactics derive from the later Cyber Kill Chain stages (exploit, control, maintain, execute).
> Source: [[01-LO10-Hacking-Methodologies-Frameworks]]

> [!question]- 0030 — Five IA principles?
> Confidentiality, Integrity, Availability, Non-repudiation, Authentication.
> Source: [[01-LO11-Network-Defense-Goal-Benefits-Challenges]]

> [!question]- 0031 — Four network defense benefits?
> Increased profits, improved productivity, enhanced compliance, client confidence.
> Source: [[01-LO11-Network-Defense-Goal-Benefits-Challenges]]

> [!question]- 0032 — Four network security approaches?
> Preventive, Reactive, Retrospective, Proactive.
> Source: [[01-LO12a-Continual-Adaptive-Security-Strategy]]

> [!question]- 0033 — Four activities of adaptive security?
> Protect, Detect, Respond, Predict.
> Source: [[01-LO12a-Continual-Adaptive-Security-Strategy]]

> [!question]- 0034 — Which approach includes IDs/SIMS/TRS/IPS?
> Reactive approach (complements preventive for attacks it failed to avert).
> Source: [[01-LO12a-Continual-Adaptive-Security-Strategy]]

> [!question]- 0035 — Three categories of physical security controls with examples?
> Prevention (fences, locks, biometrics, mantraps), Deterrence (security guards, warning signs), Detection (CCTV, alarms).
> Source: [[01-LO12b-Security-Controls-Defense-Elements]]

> [!question]- 0036 — Major elements required for effective security strategy implementation?
> Technology, well-defined Operations, and skilled People (blue team).
> Source: [[01-LO12b-Security-Controls-Defense-Elements]]

> [!question]- 0037 — Seven defense-in-depth layers?
> Policies/procedures/awareness, Physical, Perimeter, Internal network, Host, Application, Data.
> Source: [[01-LO13-Defense-in-Depth-Strategy]]

> [!question]- 0038 — Why does defense-in-depth help after a breach?
> A break in one layer only exposes the next layer, giving defenders time to deploy new/updated countermeasures and limiting impact.
> Source: [[01-LO13-Defense-in-Depth-Strategy]]

### Module 02 (42 items)

> [!question]- 0039 — Order the security hierarchy from top to bottom?
> Regulatory Frameworks → Policies → Standards → Procedures (SOP) → Guidelines.
> Source: [[02-LO01-Regulatory-Frameworks-Compliance]]

> [!question]- 0040 — Standards vs guidelines · mandatory?
> Standards = specific low-level MANDATORY controls (e.g., password complexity, DES/AES/RSA). Guidelines = non-mandatory recommendations/best practices, reviewed more often.
> Source: [[02-LO01-Regulatory-Frameworks-Compliance]]

> [!question]- 0041 — Why is compliance not optional?
> Investment worth more than cost of risks: improved security, minimized losses, maintained trust, increased control.
> Source: [[02-LO01-Regulatory-Frameworks-Compliance]]

> [!question]- 0042 — What defines scope per HIPAA/SOX/FISMA/GLBA/PCI-DSS?
> HIPAA=healthcare data · SOX=US public companies & accounting · FISMA=federal agencies · GLBA=financial products/services · PCI-DSS=cardholder data.
> Source: [[02-LO01-Regulatory-Frameworks-Compliance]]

> [!question]- 0043 — Six high-level PCI-DSS requirements?
> Build/Maintain a Secure Network · Protect Cardholder Data · Maintain a Vulnerability Management Program · Implement Strong Access Control Measures · Regularly Monitor & Test Networks · Maintain an Information Security Policy.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0044 — HIPAA Administrative Simplification Rules?
> Electronic Transaction & Code Sets · Privacy Rule · Security Rule · National Provider Identifier (NPI, 10-digit intelligence-free) · Enforcement Rule.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0045 — GDPR controller vs processor?
> Controller = determines purposes/means of processing; Processor = processes data on behalf of the controller.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0046 — SOX Section 302 and Section 404?
> 302: senior mgmt certifies accuracy of financial statements. 404: management + auditors establish internal controls and report on their effectiveness.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0047 — GLBA penalty caps?
> Org ≤  $100,000 per violation; officers/directors personally liable ≤  $10,000 each; fines or imprisonment ≤  5 years.
> Source: [[02-LO02a-Regulatory-Frameworks-Laws]]

> [!question]- 0048 — ISO/IEC 27001 vs 27002?
> 27001 = formal ISMS specification; 27002 = information security controls catalogue.
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0049 — ISO/IEC 27018 and ISO/IEC 27400?
> 27018 = cloud privacy (PII by CSPs); 27400 = IoT security and privacy.
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0050 — DMCA Title II?
> Online Copyright Infringement Liability Limitation — 4 safe-harbor categories for service providers (transitory · caching · storage · location tools).
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0051 — FISMA core requirement?
> Each federal agency develops, documents, and implements an agency-wide information security program for its information/information systems.
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0052 — CFAA basis?
> 18 U.S.C. § 1030 — intentionally accessing a protected computer without authorization / exceeding authorized access.
> Source: [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]

> [!question]- 0053 — Three goals of a security policy?
> (1) Reduce/eliminate legal liability; (2) protect confidential & proprietary information; (3) prevent computing resource waste.
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0054 — Four security requirement types?
> Discipline · Safeguard · Procedural · Assurance.
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0055 — EISP vs ISSP vs SSSP?
> EISP=enterprise scope/direction; ISSP=issue-specific (acceptable use, password…); SSSP=system-specific (DMZ, servers, cloud).
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0056 — Internet access policies — paranoid vs prudent?
> Paranoid forbids everything; Prudent blocks all by default then enables each safe/necessary service and logs everything.
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0057 — Step 3 & 4 of policy creation?
> 3 = include senior management/staff (policy without mgmt consent is illegal); 4 = set clear penalties and enforce them.
> Source: [[02-LO03a-Security-Policy-Fundamentals]]

> [!question]- 0058 — Password example length & expiration (courseware)?
> 8–14 chars; max age 60 days; official guidance: change every 90 or 180 days.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0059 — Full vs incremental vs differential backup?
> Full=all data, slowest · Incremental=changes since last full, faster · Differential=selected files new/changed since last full.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0060 — Firewall policy — Telnet & FTP stance?
> No Telnet (insecure); FTP only for vendor error-log uploads; use proxy servers to avoid direct connections.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0061 — User access control practices?
> Prohibit unknown logins · monitor admin accounts · lock after failed attempts · remove unused accounts · strict access criteria · need-to-know + least privilege · disable unrequired features/ports.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0062 — Switch security — SSH vs Telnet, port security?
> SSH preferred over Telnet; port security limits MAC-based access.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0063 — Encryption key types + certs?
> Symmetric or asymmetric per org needs; verify certificate authenticity/provider; servers use trusted SSL/TLS certificates.
> Source: [[02-LO03b-Security-Policy-Documents]]

> [!question]- 0064 — Training cadence for employees?
> On joining and periodically thereafter.
> Source: [[02-LO04-Security-Awareness-Training]]

> [!question]- 0065 — Two data classification top-level rules?
> Secret users access secret→unclassified (NOT Top Secret); Top Secret users access all levels; unclassified = anyone, no permissions.
> Source: [[02-LO04-Security-Awareness-Training]]

> [!question]- 0066 — Social engineering techniques to train against?
> Tailgating/piggy-backing · password-change ruse · name-dropping · relaxing conversation · new-hire ruse.
> Source: [[02-LO04-Security-Awareness-Training]]

> [!question]- 0067 — Steps to implement awareness training?
> Buy-in from top → gap analysis → regular schedule → performance review → phishing simulations → educate failures → implement policy processes.
> Source: [[02-LO04-Security-Awareness-Training]]

> [!question]- 0068 — Leaving-process actions?
> Remove access rights + collect assets · remove org data from personal devices · change passwords · deactivate email & remote-access accounts · debriefing · remove biometric/badge codes.
> Source: [[02-LO05-Admin-Security-Measures]]

> [!question]- 0069 — Employee monitoring purpose?
> Detect policy-violation activity, measure & enhance productivity, and secure corporate resources (e.g., Spytech SpyAgent).
> Source: [[02-LO05-Admin-Security-Measures]]

> [!question]- 0070 — SpyAgent monitoring features (key)?
> Keystroke logging · screenshots · email/social/chat monitoring · webcam/mic recording · remote desktop viewing & control · clipboard logging · email/FTP log delivery.
> Source: [[02-LO05-Admin-Security-Measures]]

> [!question]- 0071 — Three ITAM data components?
> Financial, physical, contractual data.
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0072 — Six ITAM types?
> Physical/hardware, software, network, digital, mobile device, cloud asset management.
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0073 — ITAM process phases?
> Identification & Categorization → Asset Tracking → Asset Maintenance.
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0074 — Lansweeper discovery highlight?
> Network-wide asset discovery without installing agents/software on systems (works for IoT too).
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0075 — Asset categorization criteria?
> Type · usage · location · owner/department · lifecycle stage · vendor/manufacturer · criticality · license type.
> Source: [[02-LO06-Asset-Management]]

> [!question]- 0076 — Six methods to stay up to date?
> News sources · conferences & webinars · communities/groups · reports & research · security competitions · network with professionals.
> Source: [[02-LO07-Security-Trends-and-Threats]]

> [!question]- 0077 — Most popular & up-to-date breaking news source (courseware)?
> thehackernews.com.
> Source: [[02-LO07-Security-Trends-and-Threats]]

> [!question]- 0078 — Key CERTs?
> US-CERT (US), CERT-EU (EU), CERT-In (India).
> Source: [[02-LO07-Security-Trends-and-Threats]]

> [!question]- 0079 — Oldest & largest cybersecurity conference?
> DEF CON (31 cited) — Las Vegas.
> Source: [[02-LO07-Security-Trends-and-Threats]]

> [!question]- 0080 — Competition example?
> National Cyber League (NCL) Games.
> Source: [[02-LO07-Security-Trends-and-Threats]]

### Module 03 (55 items)

> [!question]- 0081 — Access control terminologies?
> Subject = user/process accessing; Object = resource (file/device); Reference Monitor checks rules; Operation = action on object.
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0082 — Bell-LaPadula two properties?
> Simple security = no read-up; *-property = no write-down (confidentiality).
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0083 — Biba three axioms?
> Simple integrity = no read-down; *-integrity = no write-up; invocation = no invoking higher-level subject (integrity).
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0084 — RBAC rules?
> Role assignment · role authorization · transaction authorization.
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0085 — XACML roles?
> PDP (decision) · PEP (enforcement/inspect) · PAP (admin) · PIP (information).
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0086 — ABAC attribute types?
> Subject/user · object/resource · environmental/context · action.
> Source: [[03-LO01-Access-Control-Models]]

> [!question]- 0087 — Castle-and-moat flaw?
> Inside = automatically trusted; with cloud/mobile the perimeter is indefinable and lateral movement is unchecked.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0088 — Zero-trust focus areas?
> Data · networks · people · devices · workloads.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0089 — ZTA deployment steps?
> Identify protect surface → map transaction flows → build ZTA → create policy → monitor & maintain.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0090 — NIST ZTA document?
> NIST SP 800-207, produced 2018 with NCCoE — abstract ZTA definition + roadmap.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0091 — ZTA logical components roles?
> PE decides · PA issues session tokens/credentials · PEP turns policy on/off between subject & resource.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0092 — ZTA vs DiD?
> ZTA = continuous verification, internal + external threats; DiD = layered defenses, primarily external threats.
> Source: [[03-LO02-Zero-Trust-and-Distributed-Access]]

> [!question]- 0093 — Four IAM areas?
> Authentication · Authorization · User management · Central user (identity) repository.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0094 — Authentication factors?
> Something you know (password) · Something you have (token/card) · Something you are (biometrics).
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0095 — 2FA combos?
> Password+smart card · password+biometrics · password+OTP · smart card+biometrics.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0096 — Token-based auth advantages?
> Security, scalability, cross-origin sharing, revocation, statelessness.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0097 — Centralized vs decentralized authorization?
> Centralized = single DB/unit for all resources (easy, cheap); decentralized = per-resource DB, flexible but cascading/cyclic auth issues.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0098 — Accounting purpose?
> Track user actions → trend analysis, breach detection, forensics (AAA: Authentication/Authorization/Accounting).
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0099 — Provierre/deprovisioning benefit?
> Eradicates idle "zombie" accounts; auto-removes access on departure.
> Source: [[03-LO03-IAM-Authentication-Authorization]]

> [!question]- 0100 — Symmetric vs asymmetric for data volumes?
> Symmetric single key → large data; asymmetric (public/private) keys → small data.
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0101 — Hashing applications + limitation?
> Password storage, file/message integrity; limitation = collisions (worse with shorter hashes).
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0102 — Digital certificate purpose?
> Bind public key to owner via trusted CA; ensure non-repudiation.
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0103 — PKI components?
> CA (issue/verify) · RA (verifier) · certificate management system · directories.
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0104 — ZKP properties + elements?
> Completeness, soundness, zero-knowledge; Witness, Challenge, Response.
> Source: [[03-LO04-Cryptographic-Techniques]]

> [!question]- 0105 — DES vs 3DES keys?
> DES 64-bit block / 56-bit key; 3DES = DES thrice (encrypt K1, decrypt K2, encrypt K3) — independent keys most secure, identical keys least.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0106 — AES parameters?
> 128-bit block; key sizes 128/192/256; iterated block cipher (NIST).
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0107 — RC6 vs RC5?
> RC6 adds integer multiplication + four 4-bit working registers.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0108 — DSA basis + hash size?
> FIPS 186 digital signature standard; 320-bit signature, 512–1024-bit security.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0109 — RSA digital envelope?
> DES-encrypted message + RSA-encrypted DES key.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0110 — SHA generations?
> SHA-1 (160-bit, deprecated), SHA-2 (SHA-256/512 + truncations), SHA-3 (sponge construction).
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0111 — HMAC key property?
> Uses inner+outer keys; executes hash twice → resists length-extension attacks.
> Source: [[03-LO05-Cryptographic-Algorithms]]

> [!question]- 0112 — Segmentation benefits?
> Improved security, better access control, improved monitoring, improved performance, better containment.
> Source: [[03-LO06-Network-Segmentation]]

> [!question]- 0113 — DMZ hosting rules?
> Web/email/DNS/FTP servers; internal + external can connect to DMZ; DMZ hosts cannot connect into internal network.
> Source: [[03-LO06-Network-Segmentation]]

> [!question]- 0114 — DMZ firewall designs?
> Single (three-legged, single point of failure) vs dual firewall (most secure, most complex).
> Source: [[03-LO06-Network-Segmentation]]

> [!question]- 0115 — Segmentation best practices?
> Least privilege · limit third-party access · audit & monitor · easy legitimate paths · combine similar resources · don't over-segment · visualize.
> Source: [[03-LO06-Network-Segmentation]]

> [!question]- 0116 — IDS vs IPS placement?
> IPS is in-line (blocks/drops/corrects); IDS sits off-side via a network tap (monitors, cannot act directly).
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0117 — Three detection methods in an IDS?
> Signature-based → anomaly-based (statistical) → stateful protocol analysis.
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0118 — Honeypot deployment types?
> Production (in production network, looks real) vs Research (analyze attacker steps for countermeasures).
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0119 — Honeypot design types?
> Pure · low-interaction (fake common services) · high-interaction (real systems via VM, costly).
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0120 — Proxy server main function?
> Intercepts/filters client requests and serves them on behalf of real servers, hiding internal IPs; extra defense layer.
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0121 — Protocol analyzer NIC mode?
> Promiscuous mode to capture all packets on the network.
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0122 — Web content filter protections?
> Malware, phishing, pharming; filters by keywords, URLs, contextual analysis.
> Source: [[03-LO07a-Essential-Security-Solutions]]

> [!question]- 0123 — Load balancer purpose + example algorithms?
> Routes client traffic to least-loaded/most-available server. Algorithms: round-robin, least-connections, least-loaded.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0124 — UTM biggest risks?
> Single point-of-failure + single point-of-compromise; one console = overall need, but less specialized.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0125 — How does SIEM act on detected threats?
> Correlates/analyzes events, then communicates with + reconfigures firewall and IPS rules to respond.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0126 — NAC main purpose?
> Restrict/allow end-user network access based on a security policy; blocks systems lacking AV/IPS.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0127 — VPN tunneling protocol layers?
> Layer 2 (data link) or layer 3 (network, OSI). Common: IPsec, PPTP, L2TP, SSL.
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0128 — SOAR three elements?
> Orchestration (connect tools), Automation (replace manual tasks), Response (single dashboard IR actions).
> Source: [[03-LO07b-Security-Platforms-VPN]]

> [!question]- 0129 — RADIUS RFCs + transport?
> RFC 2865 (auth) / RFC 2866 (accounting); client-server on the application layer via UDP (or TCP) as transport; PAP/CHAP/EAP auth.
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0130 — RADIUS vs TACACS+ encryption?
> RADIUS encrypts only the password (UDP); TACACS+ encrypts the whole session including username+password (TCP 49), AAA separated.
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0131 — Kerberos main protection + identity proof?
> Protects against replay attacks and eavesdropping; proves identity on non-secure networks via tickets (TGT then service ticket).
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0132 — PGP session key handling?
> One-time session key encrypts the message; the key itself is encrypted with the recipient's public key and sent alongside.
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0133 — S/MIME cryptographic services?
> Authentication, message integrity, non-repudiation, privacy, data security (RSA-based, separate keys for signing and encryption).
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0134 — SSL channel-security properties?
> Private (encrypted after handshake), authenticated (server always, client optional), reliable (integrity check).
> Source: [[03-LO08-Network-Security-Protocols]]

> [!question]- 0135 — IPsec services?
> AH = sender authentication only; ESP = sender authentication + data encryption; peer auth, data origin auth, integrity, confidentiality, replay protection.
> Source: [[03-LO08-Network-Security-Protocols]]

### Module 04 (93 items)

> [!question]- 0136 — Firewall core function?
> Gateway/filtering device enforcing the network security policy between private network and Internet (first line of defense).
> Source: [[04-LO01-Firewall-Concerns-Capabilities-Limitations]]

> [!question]- 0137 — Typical firewall capabilities?
> Prevent scanning, control traffic, user auth, filter packets/services/protocols, traffic logging, NAT, malware prevention.
> Source: [[04-LO01-Firewall-Concerns-Capabilities-Limitations]]

> [!question]- 0138 — Key firewall limitations vs malware?
> Not an antivirus substitute; can't stop zero-day/new viruses, backdoor/insider, social engineering, password misuse, tunneled traffic.
> Source: [[04-LO01-Firewall-Concerns-Capabilities-Limitations]]

> [!question]- 0139 — Packet-filtering firewall layer + bypass vector?
> Network layer; evaluates headers (IP/ports/protocol/TCP bits); bypassable via packet spoofing.
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0140 — Circuit-level gateway layer + limitation?
> Session layer; validates TCP handshake; hides private network; can only handle TCP, no content scanning.
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0141 — Application-level gateway filtering?
> Application layer: per app/protocol (e.g., web proxy blocks FTP/Telnet), filters HTTP GET/POST commands.
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0142 — Stateful multilayer inspection?
> Combines packet + session + application checks; tracks slots/translations; expensive, needs skilled staff.
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0143 — NAT translation most efficient mode?
> Dynamic address+port pair allocated per inbound connection (best external-address use).
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0144 — NGFW = generation + extra layer?
> Third-generation; traditional L3–L4 + application layer 7 (DPI, encrypted-traffic inspection, integrated IPS, threat intel).
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0145 — Cloud firewall alias + types?
> FaaS (firewall as a service); types: SaaS firewalls, NGFWs in virtual datacenters (PaaS/IaaS).
> Source: [[04-LO02-Firewall-Technologies]]

> [!question]- 0146 — Screened subnet alias + structure?
> "Triple-homed firewall" (single FW, 3 interfaces: Internet/DMZ/intranet); DMZ hosts public services; compromises FW can't reach intranet.
> Source: [[04-LO03-Firewall-Topologies]]

> [!question]- 0147 — Dual-homed host key property?
> Two NICs (untrusted + trusted); no direct routing between them — firewall is the intermediary.
> Source: [[04-LO03-Firewall-Topologies]]

> [!question]- 0148 — Topology for a simple network with no public services?
> Bastion host (single layer of protection; fine for corporate surfing, not web/email hosting).
> Source: [[04-LO03-Firewall-Topologies]]

> [!question]- 0149 — Topology when two or more network zones exist?
> Multi-homed firewall (per-interface security policies; trusted network stays safe if DMZ breached).
> Source: [[04-LO03-Firewall-Topologies]]

> [!question]- 0150 — Hardware vs software firewall cost/placement?
> Hardware: dedicated perimeter device (Cisco ASA/FortiGate), pricier, faster; software: per-host program (Windows FW/iptables/UFW), cheap, resource-heavy.
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0151 — Host vs network-based firewall example each?
> Host: Windows Firewall/iptables/UFW (software, per device); network: pfSense/SmoothWall/Cisco SonicWall (hardware, perimeter).
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0152 — Host-based firewall analysis order?
> Packet inspection (L3/L4, MAC/IP/ports) → stateful filter validation → application-layer validation.
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0153 — External firewall primary role?
> Limit protected↔public traffic, protect DMZ + legacy devices without firewalls; block new external→internal connections.
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0154 — Internal firewalls sit where?
> Between two segments of the same org (or two orgs on the same network); segment + monitor, contain malicious spread.
> Source: [[04-LO04-Firewall-Placement-Types]]

> [!question]- 0155 — Two techniques of traffic normalization?
> (1) clean up malformed packets, (2) drop illegal packets — normalized at every protocol layer before payload inspection.
> Source: [[04-LO05-Deep-Traffic-Inspection-Selection]]

> [!question]- 0156 — Why stream-based inspection for fighten evasion?
> Segment/pseudo-packet-only inspection misses malicious payloads spread across boundaries; stream inspection needs more RAM+CPU.
> Source: [[04-LO05-Deep-Traffic-Inspection-Selection]]

> [!question]- 0157 — Exploit-based vs vulnerability-based detection?
> Exploit-based: 100% signature match (can't cover every evasion); vulnerability-based: block exploitation at network+application layers (preferred).
> Source: [[04-LO05-Deep-Traffic-Inspection-Selection]]

> [!question]- 0158 — Firewall deployment phases?
> Planning → Configuring → Testing → Deploying → Managing & Maintaining.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0159 — Firewall policy creation steps?
> 1 key apps → 2 vulnerabilities → 3 cost-benefit → 4 app traffic matrix → 5 ruleset from matrix.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0160 — Ruleset review cadence + implicit rule?
> Review/update every 6 months; implicit deny blocks all traffic not explicitly allowed.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0161 — Blacklist vs whitelist ruleset?
> Blacklist: allow all, deny listed. Whitelist: deny all, allow only listed (stricter).
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0162 — Firewall log placement?
> Centralized secure server/syslog; huge volumes (≥10k events/s) need specialized software.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0163 — Test-network evaluation attributes?
> Connectivity, ruleset, app compatibility, management, logging, performance, security, component interoperability, policy sync.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0164 — Maintenance activities?
> Patches, policy updates on new threats, 6-month review, log analysis, regular ruleset/policy backups.
> Source: [[04-LO06-Firewall-Implementation-Deployment]]

> [!question]- 0165 — Firewall log backup cadence + purpose?
> Monthly to secondary storage; backup before/after rule changes; for legal/future reference after incidents.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0166 — Default inbound rule posture?
> Default 'deny' inbound with explicit 'allow' rules; implicit deny at end of ruleset blocks everything not allowed.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0167 — Secure email access design?
> Separate email network zone firewalled from DMZ + internal network; email + webmail servers placed in it.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0168 — Rule lifecycle management?
> Add expiration dates to temporary rules, review for cleanup; test policies before implementing.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0169 — Firewall audit frequency + password policy?
> Audits at least once a year; change firewall passwords regularly (≈ every 6 months).
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0170 — Key firewall don'ts?
> No telnet access through FW, no direct internal-client↔outside-service connections, don't rely on packet filtering alone, don't skip SSL.
> Source: [[04-LO07-Secure-Firewall-Implementation-Best-Practices]]

> [!question]- 0171 — Firewall remote management protection?
> Encryption + strong user auth; HTTPS (SSL over HTTP) GUI; unique user IDs/passwords, token-based RADIUS.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0172 — Failover mechanism?
> Heartbeat-based services shift traffic to backup firewall; primary+backup behind a single MAC address.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0173 — Firewall backup policy?
> Full 'day zero' backups (not incremental) before production release; in-built backup facilities; UNIX /var holds logs+spools.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0174 — On security incident, first actions?
> Temporarily disable remote access + revoke user authentication; correlate events via NTP-synchronized firewall.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0175 — Client access to external hosts?
> Never direct — through firewall as proxy; a firewall combines application-level packet filtering + domain-level proxy.
> Source: [[04-LO08-Firewall-Administration]]

> [!question]- 0176 — IDS vs IPS core difference?
> IDS detects + alerts; IPS detects + actively blocks (inline); IPS also fixes CRC, defragmentation, TCP sequencing, layer options.
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0177 — Why implement an IDS behind the firewall?
> Firewalls allow/deny by rules but never inspect legitimate traffic content; IDS inspects it for malicious payloads/signatures.
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0178 — What is NOT an IDS?
> Network logging systems, vulnerability assessment tools, antivirus products, cryptographic systems (VPN/SSL/S-MIME/Kerberos/RADIUS).
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0179 — Common IDS deployment mistakes?
> Wrong placement (not seeing all traffic), ignoring alerts, no response plan, not tuning false pos/neg, stale signatures, inbound-only monitoring.
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0180 — NIDS + encrypted traffic problem?
> Without IPsec visibility, NIDS only does packet-level analysis of encrypted tunnels (app contents inaccessible) → more vulnerable.
> Source: [[04-LO09-IDS-Role-Capabilities-Limitations]]

> [!question]- 0181 — IDS classification bases?
> Approach, protected system, structure, data source, behavior (after attack), analysis timing.
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0182 — Signature vs anomaly detection tradeoff?
> Signature: few false alarms but known attacks only; anomaly: finds unknown attacks but high false-positive rate.
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0183 — Active vs passive IDS?
> Active auto-blocks without admin; passive only monitors/analyzes/alerts and logs.
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0184 — NIDS vs HIDS placement?
> NIDS: network boundaries behind FW/routers/VPN/wireless; HIDS: on the host (sensitive public servers).
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0185 — Interval-based vs real-time IDS?
> Interval: offline "store and forward", no active response; real-time: on-the-fly, continuous feed, more RAM+disk.
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0186 — IDS data sources?
> Audit trails (system/app/user evidence) and network packets (header+payload captured pre-destination).
> Source: [[04-LO10-IDS-Classification]]

> [!question]- 0187 — Six IDS components?
> Network sensors, analyzer, alert systems, command console, response system, attack-signature database.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0188 — Alert delivery methods?
> Pop-up windows, email, sounds, mobile messages.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0189 — True vs false positive alert?
> True positive = correctly identified successful attack; false positive = event misidentified as attack.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0190 — Response system countermeasures?
> Log out user, disable account, block attacker source, restart server/service, close connections/ports, reset TCP sessions.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0191 — IDS detection process steps?
> Install signatures → gather data → alert sent → IDS responds → admin assesses damage → escalation → events logged/reviewed.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0192 — Where to place sensors?
> Internet gateways, between LAN connections, remote-access/dial-up servers, either side of firewall, VPN devices.
> Source: [[04-LO11-IDS-Components]]

> [!question]- 0193 — IDS staged deployment benefit?
> Discovers where security/sensors are needed, lets admins adapt; initial stage requires highest maintenance.
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0194 — NIDS sensor order of deployment?
> IDS management console first, then sensors incrementally at choke points/gateways/DMZ.
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0195 — Outside-firewall sensor tuning (L1)?
> Least-sensitive attacks, logs attempts only (no alerts) to avoid false alarms.
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0196 — DMZ sensor (L2) coverage?
> Perimeter + firewall-bypass detection; web/FTP servers; low-moderate impact attacks; also outbound.
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0197 — HIDS deployment approach?
> Critical servers first → management console → then every host, only if manageable (costly, many false alarms).
> Source: [[04-LO12-IDs-Deployment-Network-Host]]

> [!question]- 0198 — Four IDS alert types?
> True positive, false positive (no attack-alert), false negative (attack-no alert — most dangerous), true negative.
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0199 — False positive rate formula?
> FP / (FP + true negative).
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0200 — False negative rate formula?
> FN / (FN + true positive).
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0201 — Sensitivity vs specificity?
> Sensitivity = legitimacy of alerts detected; specificity = filters/accuracy of detected alerts (set IDS threshold).
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0202 — Encrypted-traffic false-negative fix?
> Place IDS behind a VPN termination with SSL so it can inspect decrypted traffic.
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0203 — False-positive sources?
> Reactionary traffic (device failure), network equipment (load balancer odd packets), non-malicious software bugs, IDS software bugs.
> Source: [[04-LO13-False-Positive-Negative-Alerts]]

> [!question]- 0204 — Good IDS characteristics?
> Continuous run, fault tolerant, subversion-resistant, minimal overhead, deviation detection, not easily deceived, tailored to system, copes with dynamic behavior.
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0205 — Five IDS product selection categories?
> General requirements, security capabilities, performance, management, lifecycle cost.
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0206 — IDS security capability requirements?
> Information gathering, logging, detection, prevention.
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0207 — NIDS vs HIDS performance measure?
> NIDS = monitor/handle network traffic; HIDS = events processed per second.
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0208 — Lifecycle cost categories?
> Initial (appliances, software/licensing, installation, customization, training) and maintenance (staff wages, customization, maintenance contracts, support).
> Source: [[04-LO14-IDS-IPS-Selection-Considerations]]

> [!question]- 0209 — NIDS tools covered?
> Snort (signature/protocol/anomaly rules), Zeek/Bro (behavioral + network analysis), Suricata (IDS/IPS, multi-gigabit, Eve JSON logging).
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0210 — Snort capabilities?
> Real-time traffic analysis, packet logging, protocol analysis, content matching; detects DoS, OS fingerprinting, buffer overflows, stealth port scans, SMB/CGI attacks.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0211 — Zeek (Bro) features?
> Behavioral-based, high-performance networks, full logging, application-layer semantic analysis + state, domain-specific scripting; integrate logs with ELK for visualization.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0212 — Suricata features?
> IDS/IPS + NSM + offline pcap; multi-gigabit single instance; auto protocol detection; Lua scripting; Eve JSON + YAML/SIEM integration.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0213 — OSSEC features?
> HIDS: log analysis, integrity checking (FIM), Windows registry monitoring, rootkit detection, time-based alerting, active response.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0214 — Wazuh origin + role?
> Fork of OSSEC; agent-level anomaly + signature detection, monitors user activity, config assessment, vulnerability detection.
> Source: [[04-LO15-NIDS-HIDS-Solutions]]

> [!question]- 0215 — Why harden routers?
> Prevent info disclosure, router disablement/reconfiguration, internal/external attacks via router, traffic rerouting.
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0216 — Three key router disables?
> IP directed broadcasts, IP source routing, HTTP configuration (clear text); plus ARP/proxy ARP.
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0217 — Switch port-security MAC methods?
> Static (single MAC), dynamic (CAM default), sticky (port-assigned MAC; lost if not saved over reboot).
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0218 — Switch layer-2 attack types?
> MAC flooding, DHCP spoofing, ARP spoofing.
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0219 — Switch hardening controls?
> SSH, ACLs/VLAN ACLs, DHCP snooping, DAI, port security, port auth, STP root/BPDU guards, disable DTP/CDP/auto-trunking, AAA.
> Source: [[04-LO16-Router-Switch-Security]]

> [!question]- 0220 — SDP name + founder?
> "Black Cloud", identity-centric security framework by the Cloud Security Alliance (CSA).
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0221 — Three SDP pillars?
> Zero trust (micro-segmentation, least privilege), identity-centric (identity not IP), built for the cloud (scalable).
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0222 — How SDP defeats static firewalls?
> Dynamic logical firewall with one rule — deny all connections; rules added/removed per authorized user; prevents lateral movement.
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0223 — SDP reverse of TCP?
> SDP authenticates/authorizes first then connects; TCP connects, authenticates, then passes data.
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0224 — SDP three components?
> Client (initiating host), controller (auth + policy), gateway (accepting host, controller-directed).
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0225 — SPA in SDP?
> Single-Packet Authorization — client sends HMAC-based one-time password packet as first packet; invalid packets rejected (minimizes DDoS impact).
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0226 — SDP workflow steps?
> Controllers online → gateways online+authenticate → client authenticates → controller picks authorized gateways → instructs gateway → sends list to client → mutual VPN established.
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0227 — SDP deployment models?
> Client-to-gateway, client-to-server, server-to-server, client-to-server-to-client, client-to-gateway-to-client, gateway-to-gateway.
> Source: [[04-LO17-Software-Defined-Perimeter]]

> [!question]- 0228 — SDP vs traditional NAC (examples)?
> Fine-grained per-user/app control vs all-or-nothing VLAN; VPN replaced vs VPN required; dynamic attr + identity integration vs 802.1X; reduced audit scope vs SIEM consolidation.
> Source: [[04-LO17-Software-Defined-Perimeter]]

### Module 05 (101 items)

> [!question]- 0229 — Windows ring model?
> Ring 0 = kernel (most privileged) → rings 1/2 = drivers → ring 3 = user mode/apps (least privileged).
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0230 — User mode vs kernel mode?
> User = private virtual address space, no direct HW access, isolates apps; kernel = unrestricted access, crashes can take the OS down.
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0231 — Environment subsystems?
> Win32 · OS/2 · POSIX (replaced by WSL on Win10/Server 2019).
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0232 — Integral subsystems?
> Security subsystem · Workstation service (redirector/client) · Server service (serves shares).
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0233 — Security Reference Monitor?
> Primary authority implementing Windows security rules; decides object/resource access via ACLs.
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0234 — Windows security concern root causes?
> Unpatched OS, improper configurations, unnecessary services/processes enabled, weak passwords, missing anti-malware.
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0235 — WSL?
> Windows Subsystem for Linux — compatibility layer running Linux binaries on Windows 10 / Server 2019; replaced POSIX subsystem.
> Source: [[05-LO01-Windows-OS-Security-Concerns]]

> [!question]- 0236 — Windows security blocks/components?
> SRM · LSASS · SAM · WinLogon/NetLogon · Registry · Access control · Active Directory.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0237 — SRM function + location?
> Enforces ACL-based access control over subjects→objects, logs for auditing; kernel component `system32\Ntoskrnl.exe`.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0238 — LSASS role/location?
> `lsass.exe`; local-logon authentication, local security policies, issues access tokens, audit messages to Event Log.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0239 — SAM store + location?
> Hashed local logon credentials; `samsrv.dll`, DB in `C:\Windows\System32\config\`.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0240 — DC logon-database usage?
> DC uses AD database; SAM only for DSRM boot / local logon (DSRM password stored in SAM).
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0241 — Credential providers?
> COM objects in LogonUI collecting password/PIN/biometrics (authui.dll, SmartcardCredentialProvider.dll).
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0242 — NetLogon functions?
> Identify DC, set up secure channel, send auth request to DC, return result; used for AD logons.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0243 — KSecDD?
> Kernel-mode library `ksecdd.sys` for ALPC; kernel-mode security ↔ LSASS in user mode; SecLookup*/SecMakeSPN* functions.
> Source: [[05-LO02-Windows-Security-Components]]

> [!question]- 0244 — Windows object access control: DACL vs SACL?
> DACL = who is allowed/denied access; SACL = how the system audits access attempts. Part of the object's security descriptor.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0245 — NULL DACL vs empty DACL?
> NULL DACL grants full access to everyone, skips normal checks; empty DACL (0 ACEs) grants no access.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0246 — Access-check ACE accumulation?
> Access rights per ACE accumulate (read from one group + write for user = both); order matters — user deny-ACE must precede group allow-ACE.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0247 — View a user's SID?
> PsGetSid: `psgetsid <Domain>\<User>`; Process Explorer Security tab; `wmic useraccount get name,sid`; registry ProfileList.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0248 — Windows integrity levels (low→high)?
> Untrusted → Low → Medium → High → System → Installer.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0249 — Integrity level of a Run As Administrator process?
> High; standard-user processes run Medium; IE protected mode (PMIE) runs Low.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0250 — Virtual service account name + benefit?
> `NT SERVICE\<service name>`, own SID, password auto-managed by Windows; created via `sc create ... obj="NT SERVICE\..."`.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0251 — Audit category for password reset?
> Audit account management.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0252 — Event ID 4625?
> An account failed to log on; Logon Types: 2 = interactive, 3 = network.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0253 — Smart App Control enforcement rule?
> Apps run only when recognized by Microsoft app intelligence or signed with a trusted cert; verify mode via `citool.exe -lp`.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0254 — Credential Guard protections + attack types?
> Virtualization-isolated secrets (NTLM pwds, Kerberos TGTs, app credentials); blocks pass-the-hash (PtH) and pass-the-ticket (PtT).
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0255 — Vulnerable Driver Blocklist registry key?
> `HKLM\SYSTEM\CurrentControlSet\Control\CI\Config` → `VulnerableDriverBlocklistEnable` = 1.
> Source: [[05-LO03-Windows-Security-Features]]

> [!question]- 0256 — What is a Windows security baseline?
> Group of Microsoft-recommended configuration settings; ensures user+device config compliance, updated for new vulnerabilities/misconfigurations.
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0257 — What replaced Security Compliance Manager (SCM)?
> Security Compliance Toolkit (SCT).
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0258 — SCT core tools?
> Policy Analyzer · LGPO.exe · SetObjectSecurity.exe · GPO2PolicyRules.
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0259 — Policy Analyzer function?
> Treats GPOs as one unit, finds duplicate/conflicting settings, compares system vs recommended baseline, takes config snapshots.
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0260 — LGPO.exe use?
> Command-line local group policy automation; import/export Registry.pol, security templates, GPO backups; manages nondomain-joined systems.
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0261 — SetObjectSecurity.exe use?
> Set security descriptors on securable objects (files, dirs, registry keys, event logs, services, SMB shares).
> Source: [[05-LO04-Windows-Security-Baseline-Configurations]]

> [!question]- 0262 — Three Windows account types?
> Administrator (full access), Standard (own files only), Guest (read/write only).
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0263 — Disable guest account (command)?
> `net user guest /active:No`; policy: Local Policies → Security Options → 'Accounts: Guest account status'.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0264 — Disable vs delete an account?
> Disabled = restorable; deleted = cannot be restored.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0265 — Password complexity requirements?
> Not contain account name/2+ consecutive name chars; ≥6 chars; 3 of 4 categories (upper, lower, digits, non-alphabetic).
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0266 — Default maximum password age?
> 42 days.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0267 — Credential Guard protects what?
> LANMAN password hashes + Kerberos TGT; thwarts pass-the-hash; hashes can't be decrypted even if extracted.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0268 — Why worry about local administrator SID?
> If attackers know the admin account's SID they can compromise the system even when the account name is changed.
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]]

> [!question]- 0269 — Patch vs service pack vs version upgrade?
> Patch = fix for one vulnerability; SP = fixes + functionality; upgrade = fixes + improved security features.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0270 — Enable automatic updates (command)?
> `sc config wuauserv start= auto`; or Services.msc → Windows Update → Automatic.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0271 — Auto-update registry key?
> `HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU` → DWORD NoAutoUpdate.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0272 — Prevent force restarts after updates (registry)?
> `HKLM\SOFTWARE\Microsoft\Windows\Windows Update\AU` → NoAutoRebootWithLoggedOnUser = 1; GPO: 'No auto-restart with logged on users…'.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0273 — Which tool extends WSUS/SCCM?
> SolarWinds Patch Manager.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0274 — Tool that detects vulnerabilities before an attacker does?
> GFI LanGuard.
> Source: [[05-LO06-Windows-Patch-Management]]

> [!question]- 0275 — NTFS permission unique to folders (not files)?
> List Folder Contents (only when inherited by folders; Read & Execute applies to files too).
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0276 — FAT vs NTFS file permissions?
> NTFS = per-file/folder permissions + backup/restore; FAT = no per-file/folder permissions.
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0277 — UAC core behavior?
> Apps run at standard-user privileges until an administrator authorizes elevation; prevents malware from changing security settings/AV.
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0278 — What does a SID's RID enable for attackers?
> RIDs are predetermined for some accounts — attacker replaces RID with an administrative account's to get admin privileges (block via 'Network access: Do not allow anonymous enumeration of SAM accounts and shares').
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0279 — Policy to block Control Panel?
> User Configuration → Admin Templates → Control Panel → 'Prohibit access to Control Panel and PC settings' (blocks Control.exe/SystemSettings.exe).
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0280 — Policy to block Command Prompt?
> User Configuration → Admin Templates → System → 'Prevent access to the command prompt'; also governs .cmd/.bat batch files.
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0281 — JEA — what does it limit?
> The cmdlets/admin privileges of an account; needs a PS role capability file (visible cmdlets) + PS session configuration file (who may run them); uses per-session virtual account.
> Source: [[05-LO07-User-Access-Management]]

> [!question]- 0282 — LM vs NT hash?
> <15-char passwords → LM hash, else NT hash; both brute-forceable — block LM storage via 'Network security: Do not store LAN Manager hash value on next password change'.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0283 — Example Windows services to disable when unused?
> IIS, FTP, SQL Server, proxy services, Telnet, Universal Plug and Play.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0284 — Disable Remote Desktop (commands)?
> `net stop termservice`, then `sc config termservice start= disabled`.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0285 — Windows Defender quick scan vs full scan?
> Quick = areas where malware usually hides; full = all files and applications.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0286 — Registry hives (key names)?
> HKLM (machine) · HKCU (current user; new subkey each logon) · HKCC (hardware profile) · HKCR (file extensions + COM registration).
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0287 — Registry monitoring tool?
> Process Monitor (Sysinternals) — real-time registry (and file/system) activity.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0288 — Firewall default rule behavior?
> Inbound connections blocked unless an allow rule matches; outbound connections allowed unless a block rule matches.
> Source: [[05-LO08-Windows-OS-Security-Hardening]]

> [!question]- 0289 — AD attack method that reuses the password hash instead of the plaintext against the Domain Admins account?
> Pass-the-hash (often via an infiltrated LM hash).
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0290 — Risk of a default Administrator account in the Domain Admins group?
> Domain Admins is tied to every domain system; privilege escalation (pass-the-hash) on one machine exposes the whole domain.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0291 — LAPS purpose and scope?
> Random unique local Administrator passwords stored in AD for domain-joined systems; manages only the local Administrator account; needs a client-side extension; Windows only.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0292 — Two AD schema attributes added by LAPS?
> Administrative password + password expiration date/time (via Update-AdmPwdADSchema).
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0293 — NTLM vs NTLMv2 hashing?
> NTLM = MD4 for passwords (Unicode, up to 127 chars, 128-bit MD4); NTLMv2 = MD4 for passwords and MD5 for usernames/server names, response differs each time.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0294 — Goal of blocking NTLM v1 in a domain?
> Force NTLMv2 (and Kerberos) so passwords are not transmitted in weaker form.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0295 — AD events that indicate compromise?
> Admin-group changes, wrong-password attempts, locked-out-account usage, account lockouts, AV-setting changes, privileged-account activity.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0296 — Event ID + logon types that reveal remote vs local logon?
> 4624; Type 2 = local logon, Type 10 = remote logon.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0297 — KRBTGT password best practice?
> Change every year, or whenever an AD administrator leaves.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0298 — WDigest hardening?
> Set `HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\WDigest` to 0.
> Source: [[05-LO09a-Windows-Active-Directory-Security]]

> [!question]- 0299 — UAC behavior on approved vs denied changes?
> Approved → action runs with highest available privilege; denied → not performed and requesting app is prevented from running.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0300 — Effect of a missing/invalid code signature?
> Windows prevents the file from running (legitimate cert also removes SmartScreen "Unknown Publisher" warning).
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0301 — What guarantees a driver can load into the Windows kernel?
> Valid digital signature (vendor certifies with Microsoft, then WHQL signs it); unsigned driver packages do not install.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0302 — TPM functions?
> Secure key storage, secure boot + chain of trust (PCR measurements), platform measurements, remote attestation (cryptographic "quote" of PCR values).
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0303 — Which Windows features use TPM?
> BitLocker (system drive), Secure Boot, Device Guard, Credential Guard.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0304 — WRP failure modes when an app modifies a protected resource?
> Access-denied error + install may fail; protected reg-key changes denied; apps writing into protected keys/folders/files may fail.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0305 — Integrity-checking tools in order for a corrupted image?
> SFC (/scannow) for system files; DISM /ScanHealth → /CheckHealth → /RestoreHealth for image repair; chkdsk for disk errors/bad sectors.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0306 — SFC /FILESONLY scope?
> Verifies/repairs only files, not registry keys.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0307 — chkdsk default mode?
> Read-only scan (/f not specified); add /f to fix, /r to find bad sectors and recover data.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0308 — Get-FileHash default algorithm + full options?
> Default SHA256; options SHA1, SHA256, SHA384, SHA512, MD5.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0309 — OSSEC integrity checker + hashes used?
> Syscheck — periodic MD5/SHA1 checksum comparison on configured files/registry entries.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0310 — Tripwire Enterprise core capabilities?
> File Integrity Monitoring (FIM) + Security Configuration Management (SCM), with policy compliance and remediation management.
> Source: [[05-LO09b-Windows-System-Integrity]]

> [!question]- 0311 — PS Remoting protocol + ports?
> WSMAN/WinRM; 5985 HTTP, 5986 HTTPS; traffic encrypted even over 5985.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0312 — Default permission to PS Remoting endpoints?
> System administrators + Remote Management Users.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0313 — How are workgroups protected in PS Remoting?
> Enable SSL/HTTPS with certificates and add them to trusted hosts — avoids MITM. (AD uses Kerberos.)
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0314 — Three PS logging types?
> Module (pipeline), Transcript (every session), Script block (executed code, de-obfuscation).
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0315 — Execution policies, strictest to loosest?
> Restricted → AllSigned → RemoteSigned → Unrestricted. Enforce via GPO (bypassable otherwise); Computer Configuration > User Configuration.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0316 — Why disable PowerShell 2.0?
> Security risk used by attackers to execute malicious code (`Disable-WindowsOptionalFeature -FeatureName MicrosoftWindowsPowerShellv2Root`).
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0317 — What does Constrained Language Mode block?
> COM objects, unapproved .NET types, XAML-based workflows, PowerShell classes.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0318 — Best enforcement of Constrained Language Mode?
> Device Guard UMCI (can't be easily disabled by admins); AppLocker script rules in Allow Mode best under least privilege.
> Source: [[05-LO10a-Secure-PowerShell-Remoting]]

> [!question]- 0319 — RDP default port and encryption scope?
> TCP 3389; tunneling encrypts data between client and server only — terminal-server authentication is unencrypted (guessable → MITM).
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0320 — Scoping the RDP firewall rule?
> Restrict the RDP rule's Scope to specific remote IP addresses; rejections happen at the firewall, freeing server resources.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0321 — RDP gateway encryption path?
> Internal hops use 3389; from the gateway to the client the data is encrypted over HTTPS port 443 with SSL certs.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0322 — Why is plain 3389 insecure?
> Password-protected only (not encrypted) → susceptible to brute-force.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0323 — What does NLA do?
> Requires authentication before the RDP session is established, sending credentials securely via the client's security service provider.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0324 — Remote Credential Guard protection?
> No passwords in memory / no hashes → defeats pass-the-hash and brute-force; redirects Kerberos requests to the client device. Restricted Admin = credentials not delegated.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0325 — DNSSEC guarantees vs non-guarantees?
> Guarantees authenticity, integrity, non-existence of name/type; does NOT guarantee confidentiality or DoS protection.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0326 — Threat mitigated by DNSSEC?
> DNS cache poisoning and DNS spoofing (validates the key attached to the DNS server response against TLD/root data).
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0327 — How to spot a malicious domain in DNS logs?
> Unusual random-character names; log via DNS Management Console → Debug Logging → "Log packets for debugging".
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0328 — SMB version to disable and why?
> SMB 1.0 — legacy, weak; keep SMB 2.0/3.0+ (2.02+ signing, 3.0+ encryption, 3.1.1+ pre-auth integrity). Registry: SMB1 = 0.
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

> [!question]- 0329 — SMB encryption details?
> AES-CCM; end-to-end; no IPsec/WAN accelerators; per-share (Set-SmbShare) or server-wide (Set-SmbServerConfiguration).
> Source: [[05-LO10b-Network-Services-Protocol-Security]]

### Module 06 (66 items)

> [!question]- 0330 — Core parts of the Linux system architecture?
> Hardware → kernel (core, full resource control) → shell (interface to kernel) → applications/utilities, system libraries, daemons (background services), graphical server (X server/X).
> Source: [[06-LO01-Linux-OS-and-Security-Concerns]]

> [!question]- 0331 — Key Linux features (security relevant)?
> Portability, open-source, multiuser, multiprogramming, hierarchical FS, shell, security (authentication/password protection, controlled file access, data encryption).
> Source: [[06-LO01-Linux-OS-and-Security-Concerns]]

> [!question]- 0332 — Why is Linux considered risky despite open code?
> Open-source → anyone can modify/distribute → unexpected vulnerabilities; poor configuration and defender oversight; increasingly targeted by malware.
> Source: [[06-LO01-Linux-OS-and-Security-Concerns]]

> [!question]- 0333 — CVE-2023-42755 example?
> IPv4 RSVP classifier flaw — out-of-bounds read in rsvp_classify; local user can crash system → DoS (CVSS 6.5).
> Source: [[06-LO01-Linux-OS-and-Security-Concerns]]

> [!question]- 0334 — Ubuntu minimal installation effect?
> Fewer packages (~80 removed): desktop + browser + core tools; prevents installing third-party/untrusted apps that may be vulnerable to new exploits.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0335 — What do BIOS + boot loader passwords block?
> BIOS: changing settings, booting system. Boot loader (GRUB/LILO): single-user mode, GRUB console, non-secure OS on dual-boot.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0336 — GRUB password hash command?
> `grub-mkpasswd-pbkdf2` → paste hash via `password_pbkdf2 name <hash>` + `set superusers=` in `/etc/grub.d/40_custom`.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0337 — Debian manual patch commands?
> `apt-get update` (fetch list), `apt-get upgrade` (upgrade current), `apt-get dist-upgrade` (install new). Red Hat: `yum check-update` / `yum update`. SUSE: `zypper`.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0338 — Discouraged when hardening installation?
> Install more than needed; leave OS unprotected on hostile network pre-hardening; no update mechanism; single / volume for everything.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0339 — Why separate `/tmp` with nodev,noexec,nosuid?
> Prevents resource exhaustion, device creation, binary execution, and setuid files in /tmp; sticky bit stops cross-user file deletion.
> Source: [[06-LO02-Linux-Installation-and-Patching]]

> [!question]- 0340 — systemctl service commands?
> List: `systemctl --type service`; stop: `systemctl stop [service]`; disable: `systemctl disable [service]`; kill process: `kill -9 [pid]`.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0341 — Five legacy services to remove from Linux servers?
> telnet-server, rsh-server, ypserv (NIS), tftp-server, talk-server — all unencrypted/insecure. Check `rpm -q <pkg>`, remove `yum erase <pkg>`.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0342 — Deborphan purpose + usage?
> Lists unused packages/libraries. `sudo apt-get install deborphan`, then `deborphan --guess-all`; remove via `deborphan --guess-data | xargs sudo aptitude -y purge`.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0343 — Ubuntu repository types?
> Main (Canonical-supported FOSS), Universe (community), Restricted (proprietary drivers, limited support), Multiverse (copyright/legal-restricted, paid). Not all audited; disable unsafe ones in Software & Updates.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0344 — ClamAV install (Debian/RHEL)?
> Debian: `apt-get update && apt-get install clamav`. RHEL/CentOS: `yum install -y epel-release && yum install -y clamav`. Fedora adds clamav-update.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0345 — Why remove unnecessary packages?
> Older/untrusted packages introduce vulnerabilities or waste resources; uninstalls leave dependent files. Use autoremove/clean/autoclean/purge.
> Source: [[06-LO03a-Linux-Services-Software-Antivirus]]

> [!question]- 0346 — Secure Boot requirement?
> UEFI firmware with Secure Boot; signed bootloader (e.g., GRUB2) and signed kernel with valid signatures from a trusted CA.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0347 — How do package managers verify integrity?
> GPG keys — APT (Debian/Ubuntu), YUM/DNF (/etc/yum.repos.d GPG key URL), zypper (SUSE). Manual: `rpm --checksig package.rpm`, `dpkg-sig --verify package.deb`.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0348 — Rootkit detection tools + commands?
> `chkrootkit` (trojans/malware in binaries; `sudo apt-get install chkrootkit`, run `./chkrootkit`) · `rkhunter` (backdoors, network/kernel checks; config `/etc/rkhunter.conf`, `rkhunter --check`, baseline `--propupd`).
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0349 — IMA vs EVM?
> IMA measures/records/evaluates hashes (serializes log of measured content). EVM extends IMA — monitors file extended attributes, uses public keys to verify/sign hashes.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0350 — Kernel integrity monitoring techniques?
> Checksums/hashing, File Integrity Monitoring, Secure Boot. Module integrity: module signing, security policies, kernel module whitelisting.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0351 — Why use official repositories + GPG keys?
> Untrusted sources may contain compromised or malicious packages; keys verify signature authenticity. Always use official/trusted repositories.
> Source: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

> [!question]- 0352 — FIM working model?
> Centralized policy → auto-retrieved → compares local filesystem vs system baseline → violations logged in report + sent to central repo; policy = JSON script with risk levels.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0353 — Tripwire workflow commands?
> `tripwire --init` → policy `/etc/tripwire/twpol.txt` → `twadmin --create-cfgfile -s site.key /etc/tripwire/twcfg.txt` → cron `tripwire --check` daily.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0354 — AIDE commands?
> Init `sudo aide --init`; config `/etc/aide/aide.conf`; update `sudo aide --update`; check `sudo aide --check` (or `# aide --check`); cron daily.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0355 — Samhain config settings?
> FILE_CHECKS (monitor list), HIDE_MODIFIED, IGNORE_LIST, REPORT_LEVEL (1 min / 3 detailed), SYSLOG_FACILITY (e.g., LOG_LOCAL4); init `samhain -t init`; logs `/var/log/samhain.log`.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0356 — OSSEC key features?
> LIDS, file integrity monitoring (forensic copies), active response (firewall + self-healing), compliance auditing (PCI-DSS/CIS), rootkit/malware detection, system inventory; alerts via `tail -f /var/ossec/logs/alerts/alerts.log`.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0357 — IMA + TPM?
> IMA = measure + appraise subsystems; hashes data before load, sends hashes to TPM to protect from alteration; enable `CONFIG_INTEGRITY=y CONFIG_IMA=y`; policies `/etc/ima/ima-policy` (e.g., `func=H`).
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0358 — auditd rule to monitor /etc/passwd?
> `sudo auditctl -w /etc/passwd -p wa -k passwd_changes` — -w path, -p permissions (w write, a attribute), -k key. Query with `ausearch -i -k <key>` and `aureport -x`.
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0359 — inotifywait usage?
> `inotifywait /path` (once), `inotifywait --monitor /path` (continuous), `inotifywait --event modify /path` (modification events).
> Source: [[06-LO03c-Linux-File-Integrity-Tools]]

> [!question]- 0360 — /etc/login.defs aging params?
> PASS_MAX_DAYS (max lifespan), PASS_MIN_DAYS (min interval between changes), PASS_WARN_AGE (days warned before expiry). New accounts only.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0361 — PAM password policy files by distro?
> Red Hat: /etc/pam.d/system-auth. Debian/Ubuntu: /etc/pam.d/common-password. Modules: pam_pwquality.so / pam_cracklib.so / pam_unix.so.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0362 — pam_pwquality parameters?
> `retry=3` (3 prompts), `minlength=8` (min chars), `maxrepeat=3` (max repeats). Complexity: ucredit/lcredit/dcredit/ocredit = -1 → at least 1 of each class.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0363 — Prevent password reuse in PAM?
> pam_unix.so `remember=N` — history stored in /etc/security/opasswd; e.g., remember=13 blocks last 13 passwords.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0364 — Find empty-password accounts?
> `awk -F: '($2==""){print}' /etc/shadow`; lock with `passwd -l <account>`; remove `nullok` from PAM configs.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0365 — Audit + disable inactive accounts?
> `lastlog -b 90 | tail -n+2 | grep -v 'Never logged in'`; disable: `usermod -L <username>`.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0366 — Account lockout via PAM?
> pam_tally2.so: `auth required pam_tally2.so onerr=fail audit silent deny=5` (+ `unlock_time=900`); account line pairs the auth line.
> Source: [[06-LO04a-Linux-Password-Management]]

> [!question]- 0367 — chmod numeric values?
> r=4, w=2, x=1 (0 none). Common: 600 private, 644 owner-write/others-read, 755 owner-all/others-rx, 700 owner-only, 777 no restrictions, 666 all rw.
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0368 — chown/chgrp usage?
> `chown user file`; `chown user:group file`; `chgrp groupName file` (group only).
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0369 — Find SUID/SGID binaries?
> `find / -perm +4000` (SUID), `find / -perm +2000` (SGID), combined `find / \( -perm -4000 -o -perm -2000 \) -print`; remove with `chmod a-s <file>`.
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0370 — Standard permission for /etc/shadow vs /etc/passwd?
> /etc/shadow = 400 (encrypted passwords); /etc/passwd = 644 (account info, no passwords).
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0371 — Locate world-writable files?
> `find /dir -xdev -perm +o=w ! \( -type d -perm +o=t \) ! -type l -print`; fix: `chmod o-w file`, `chmod +t /path/to/dir`; prevent: `umask 002`.
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0372 — SUID/SGID risk?
> Programs run with owner/group owner privileges; vulnerabilities in SUID/SGID binaries → privilege escalation.
> Source: [[06-LO04b-Linux-File-Permissions-SUID]]

> [!question]- 0373 — Disable X Windows at boot?
> Edit /etc/inittab: `id:5:initdefault:` → `id:3:initdefault:`; remove via `yum groupremove "X Window System"`.
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0374 — Separate which partition mounts + fstab options?
> /usr, /home, /var, /var/tmp, /tmp (+Apache/FTP roots). Options: noexec (no binaries), nodev (no device files), nosuid (no SUID/SGID).
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0375 — Disk quota enable step sequence?
> `sudo apt install quota` → verify quota_v1/v2 module → edit /etc/fstab (usrquota,grpquota) + `mount -o remount /` → `quotacheck -ugm /` → `quotaon -v /` → `edquota -u <user>` → check `quota -vs <user>`.
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0376 — Methods to block usb-storage?
> Fake install `install usb-storage /bin/true` in /etc/modprobe.d/block_usb.conf; blacklist in /etc/modprobe.d/blacklist.conf; rename usb-storage.ko → .blacklist; BIOS disable; GRUB `nousb` kernel arg.
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0377 — Why remove X11?
> Not needed for dedicated mail/web servers; vulnerabilities can escalate non-root users to higher privilege.
> Source: [[06-LO04c-X11-Partitions-Quota-USB]]

> [!question]- 0378 — Kernel hardening via which file + what default?
> /etc/sysctl.conf read at boot by sysctl. Defaults: ip_forward=0, send_redirects=0, accept_redirects=0, source_route=0, rp_filter=1, syncookies=1, log_martians=1, exec-shield=1.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0379 — iptables three chains?
> INPUT (incoming vs rule, IP+port), FORWARD (routes incoming to destination), OUTPUT (output allow/deny). Check `iptables -L -n -v`.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0380 — UFW basic workflow?
> install → `ufw status verbose` → `ufw enable` → default deny incoming / allow outgoing → add rules by service/port/proto/IP; delete with `ufw delete allow <n>`.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0381 — TCP Wrappers allow/deny files + order?
> Only first matching rule considered; TCPD allows via /etc/hosts.allow, denies via /etc/hosts.deny; verify support `ldd $(which sshd) | grep libwrap`.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0382 — netstat/ss option meanings?
> -t TCP, -u UDP, -n numeric (no DNS), -l listening only, -p PID+process name → `netstat -tulpn` / `ss -tulpn`; lsof `-nP -iTCP -sTCP:LISTEN`.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0383 — How to disable IPv6?
> sysctl.conf disable_ipv6=1 (all/default/lo) or GRUB `ipv6.disable=1` + update-grub; or sysctl -w one-liners.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0384 — What can block which? firewall vs TCPD?
> Firewall = network-layer, cannot inspect encrypted connections. TCPD = app-layer ACL → filters even HTTPS; complements firewall, never on firewall host.
> Source: [[06-LO05a-Kernel-Firewall-TCPWrappers-Ports]]

> [!question]- 0385 — Set PermitRootLogin safely?
> Edit /etc/ssh/sshd_config → `PermitRootLogin no` → restart sshd (systemctl/service/init.d). Create sudo-capable user first.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0386 — Hardening keys in sshd_config?
> PermitRootLogin no, IgnoreRhosts yes, HostbasedAuthentication no, PermitEmptyPasswords no, X11Forwarding no, MaxAuthTries 5, Ciphers aes128/192/256-ctr, ClientAliveInterval 900.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0387 — What is chrooted SFTP and why?
> Locks SFTP users inside their home dir (can't browse others'); steps: mkdir /sftp (root owned), dirs per user, group sftponly, useradd -s /sbin/nologin, chmod 700, sshd_config internal-sftp + Match block.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0388 — sshd_config settings for chroot SFTP?
> Comment out Subsystem sftp (path per distro), then add: `Subsystem sftp internal-sftp`, `Match group sftponly`, `ChrootDirectory /sftp/`, `X11Forwarding no`, `AllowTcpForwarding no`, `ForceCommand internal-sftp`.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0389 — Verify SFTP jail?
> `sftp alex@<server>` → `sftp>` and `pwd` = `/`. SSH attempt shows "This service allows sftp connections only." Restart `systemctl restart sshd`.
> Source: [[06-LO05b-SSH-Hardening-Chroot-SFTP]]

> [!question]- 0390 — Lynis purpose?
> Open-source security auditing + hardening + compliance testing (PCI/HIPAA/SOX); modular, uses only discovered system components → keeps system clean.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0391 — AppArmor vs SELinux?
> Both MAC on LSM. AppArmor: per-program profiles (text in /etc/apparmor.d/), aa-enforce, apparmor_status. SELinux: kernel-level, TE + RBAC + MLS, 3 modes enforcing/permissive/disabled.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0392 — SELinux modes?
> enforcing (policy enforced/blocks), permissive (warnings + logs), disabled (no policy). Config /etc/selinux/config SELINUX=; status via sestatus.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0393 — SCAP components?
> CVE, CCE, CPE, CVSS, XCCDF, OVAL, OCIL 2.0, Asset Identification, ARF, CCSS, TMSAD — XML namespaced standards (NIST).
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0394 — OpenSCAP install + basic run?
> Ubuntu `apt-get install libopenscap8`; Fedora `dnf install openscap-scanner`; RHEL/CentOS `yum install openscap-scanner`; OVAL: `oscap oval eval --results ... --report report.html <oval.xml>`.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

> [!question]- 0395 — Name additional hardening tools?
> Bastille Linux, JShielder, nixarmor, bane, Grsecurity (kernel exploit prevention), Comodo Antivirus.
> Source: [[06-LO06-Linux-Security-Tools-and-Frameworks]]

### Module 07 (59 items)

> [!question]- 0396 — The four mobile use approaches in enterprise?
> BYOD (Bring Your Own Device) · COPE (Company Owned, Personally Enabled) · COBO (Company Owned, Business Only) · CYOD (Choose Your Own Device).
> Source: [[07-LO01a-Common-Mobile-Usage-Policies]]

> [!question]- 0397 — What three areas do the decision questions cover when choosing a mobile approach?
> Device specific (type, selection, cost, providers) · management and support · integration and application.
> Source: [[07-LO01a-Common-Mobile-Usage-Policies]]

> [!question]- 0398 — BYOD stands for?
> Bring Your Own Device (variants: BYOT — own technology, BYOP — own phone, BYOPC — own PC). Employees bring personal devices to access org resources per access privileges.
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0399 — Four BYOD advantages?
> Increased productivity + employee satisfaction · work flexibility (mobile + cloud-centric) · lower IT costs · availability of up-to-date resources.
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0400 — BYOD disadvantages?
> Security access issues (lost/stolen data, malware via unsecured Wi-Fi) · compatibility issues across platforms · scalability (network infrastructure limits).
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0401 — The 5-step BYOD implementation flow?
> 1 Define requirements → 2 decide device/data management → 3 develop policies → 4 security → 5 support.
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0402 — PIA in BYOD projects?
> Privacy impact assessment — performed at project start by the mobile governance committee (end users + IT management); documented procedure for facts, objectives, privacy risks, mitigation.
> Source: [[07-LO01b-BYOD-Policy-Implementation]]

> [!question]- 0403 — CYOD vs COPE ownership?
> CYOD: employee picks from company-approved list, company purchases. COPE: company purchases + owns; personal use enabled. COBO: company-owned, business-only (often single app).
> Source: [[07-LO01c-CYOD-COPE-COBO-Policies]]

> [!question]- 0404 — Fastest vs slowest deployment models?
> CYOD: slower than BYOD but quicker than COPE; COPE has the slowest deployment timeframe of the models.
> Source: [[07-LO01c-CYOD-COPE-COBO-Policies]]

> [!question]- 0405 — COBO classic example?
> Blackberry devices; also inventory systems with embedded barcode scanners (single-application devices).
> Source: [[07-LO01c-CYOD-COPE-COBO-Policies]]

> [!question]- 0406 — COPE containerization purpose?
> Separate professional and personal use of a company-owned device; manage/prohibit data sharing between the two containers.
> Source: [[07-LO01c-CYOD-COPE-COBO-Policies]]

> [!question]- 0407 — Four enterprise mobile security risk categories?
> Physical (loss/theft, malicious flashing) · network-based (wireless eavesdropping) · system-based (vendor vulnerabilities like SwiftKey) · application-based (unpatched apps → malware/remote control).
> Source: [[07-LO02a-Enterprise-Mobile-Security-Risks]]

> [!question]- 0408 — MITM-risk mitigations for mobile networks?
> WPA2 + secured protocols (IPSec, SSL, SSH, HTTPS, Kerberos) + gateways with content filtering and DLP.
> Source: [[07-LO02a-Enterprise-Mobile-Security-Risks]]

> [!question]- 0409 — Name the 10 policy-related mobile risks?
> Unsecured-network sharing · data leakage/endpoint · improper disposal · supporting many devices · mixing personal/private data · lost/stolen devices · lack of awareness · bypassing network policy · infrastructure issues · disgruntled employees.
> Source: [[07-LO02a-Enterprise-Mobile-Security-Risks]]

> [!question]- 0410 — Which devices are disallowed under the admin mobile guidelines?
> Jailbroken (iOS) and rooted (Android) devices; also devices with a poor security record.
> Source: [[07-LO02b-Mobile-Usage-Policy-Guidelines]]

> [!question]- 0411 — Access gateway authentication methods?
> No authentication · Domain only · SMS authentication · RSA SecurID only · Domain + RSA SecurID. Enforce a session timeout.
> Source: [[07-LO02b-Mobile-Usage-Policy-Guidelines]]

> [!question]- 0412 — BYOD employee-separation rule on leaving?
> State whether total device wipe or selective wipe of specific apps/data is required; keep organization and personal data maintained separately.
> Source: [[07-LO02b-Mobile-Usage-Policy-Guidelines]]

> [!question]- 0413 — MDM in one line?
> Deploy, secure, monitor, and manage company/employee-owned devices via an MDM server management console + MDM agents on the devices.
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0414 — MDM delivery methods?
> Premise-based (high control, larger up-front) · SaaS-based (no on-site servers, monthly/annual fees) · managed services-based (orgs lacking expertise; status reports provided).
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0415 — MDM key feature list?
> Security mgmt · device config mgmt · inventory/tracking · OTA app distribution · enterprise policy mgmt · password enforcement · data encryption enforcement · network integration · remote data wipe · blacklisting/whitelisting.
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0416 — MDM selection factors (short list)?
> Custom app store · application security scanning · browser filtering · encryption levels · selective wipe · auto-provisioning · architecture (sandbox/virtual/integrated) · inventory + reports.
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0417 — Example MDM vendors?
> VMware Workspace ONE, IBM MaaS360, XenMobile, Absolute, Sicap DMC, SOTI MobiControl, Scalefusion, ManageEngine, MobileIron, MediaContact, Beachhead SimplySecure, Microsoft Intune.
> Source: [[07-LO03a-Mobile-Device-Management-Solutions]]

> [!question]- 0418 — MAM in one line?
> Secure, manage, and distribute enterprise applications on mobile devices without interfering with device ownership; separates enterprise apps/data from personal content.
> Source: [[07-LO03b-Mobile-Application-Management-Solutions]]

> [!question]- 0419 — Core MAM services?
> App delivery (enterprise app store), licensing, configuration, authorization, usage tracking, lifecycle mgmt, updating, performance monitoring, user auth, crash reporting, access control, version mgmt, push, reporting, usage analytics, event mgmt, app wrapping.
> Source: [[07-LO03b-Mobile-Application-Management-Solutions]]

> [!question]- 0420 — Intune MAM configurations?
> Intune MDM + MAM (devices enrolled in Intune MDM) and MAM-WE (MAM without device enrollment).
> Source: [[07-LO03b-Mobile-Application-Management-Solutions]]

> [!question]- 0421 — MAM examples?
> Microsoft Intune, MobileIron, App47, Scalefusion (resembles config/example table from courseware).
> Source: [[07-LO03b-Mobile-Application-Management-Solutions]]

> [!question]- 0422 — MCM main components?
> File storage + file sharing services; secure access to corporate data via authorized apps; wipe-out for specific users.
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0423 — MCM templating approaches?
> Multi-client (different site versions on the same domain) · multi-site (mobile sites on a targeted sub-domain).
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0424 — What does MTD add beyond MDM/MAM?
> Insights into app characteristics, threat protection, user behavior, dynamic threat reaction, continuous device-health/trust visibility — extends EMM/MDM.
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0425 — MTD protection levels in the mobile enterprise?
> Device level (OS/config/firmware checks, privilege escalation) · network level (traffic monitoring, spoofed certs, TLS/SSL stripping, MITM detection) · application level (sandboxing, code analysis, anti-malware signatures, reverse engineering, static/dynamic testing).
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0426 — MTD vendor examples?
> MobileIron, Lookout, Wandera.
> Source: [[07-LO03c-Mobile-Content-and-Threat-Management-Solutions]]

> [!question]- 0427 — MEM purpose + key features?
> Secure corporate email infrastructure/data: preconfigure email remotely · only approved apps/devices access mail (S/MIME, SCEP) · prevent unauthorized attachment access · pre-install the managed email client.
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0428 — EMM comprehensive scope formula?
> EMM = MDM + MAM + MTM + MCM + MEM — comprehensive solution for safeguarding enterprise data on mobile devices.
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0429 — EMM deployment process phases?
> Plan (requirements + stakeholder feedback) → Design (roles, visibility, actors, distribution) → Deploy (cloud vs on-premise, pricing model) → Implement (helpdesk preparation).
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0430 — UEM in one line?
> Remote provisioning, management, control, and security of all internet-enabled devices (mobile + desktop) from a single interface; extends MDM and EMM.
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0431 — UEM notable capabilities?
> App containerization · certificate-based identity · per-app VPN · DLP (open-in/copy-paste) · secure multi-user profiles · remote erase · API framework.
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0432 — UEM examples?
> Scalefusion UEM, Ivanti Unified Endpoint Manager, VMware Workspace ONE UEM (AirWatch-powered).
> Source: [[07-LO03d-MEM-EMM-UEM-Solutions]]

> [!question]- 0433 — Mobile app security best practices (short list)?
> No stored passwords · avoid query string · code obfuscation/encryption · 2FA · SSL/TLS · no app-data caching · input validation · secure sessions · server-side auth · enterprise app store installs · containerization · jailbreak protection.
> Source: [[07-LO04a-Mobile-App-Data-Network-Security-Best-Practices]]

> [!question]- 0434 — Mobile data security practices?
> Encrypt device storage + OTA (SSL/TLS/VPN/WPA2) · periodic backup · no sensitive data/PINs as contacts · private data centers + device auth · avoid public Wi-Fi · auto-lock · timely patches · updated AV.
> Source: [[07-LO04a-Mobile-App-Data-Network-Security-Best-Practices]]

> [!question]- 0435 — Network guidelines for mobile?
> Disable BT/IR/Wi-Fi when idle · Bluetooth non-discoverable · encrypted Wi-Fi only · no public hotspots · secure web accounts · segment users via SSIDs/VLANs · per-group firewall rules.
> Source: [[07-LO04a-Mobile-App-Data-Network-Security-Best-Practices]]

> [!question]- 0436 — Passcode recommendations?
> Strong passcode, max length · idle-timeout auto-lock · lockout/wipe after attempts · eight-character passcodes · erase data ON to prevent guessing.
> Source: [[07-LO04b-General-Mobile-Platform-Security-Guidelines]]

> [!question]- 0437 — Remote wipe service examples?
> Find My Device (Android) and Find My iPhone / FindMyPhone (iOS); report loss/theft to IT to disable certificates + access methods.
> Source: [[07-LO04b-General-Mobile-Platform-Security-Guidelines]]

> [!question]- 0438 — Access gateway authentication methods?
> No authentication · Domain only · SMS authentication · RSA SecurID only · Domain + RSA SecurID.
> Source: [[07-LO04b-General-Mobile-Platform-Security-Guidelines]]

> [!question]- 0439 — SMS phishing countermeasures (top items)?
> Don't reply without verifying source · don't click links · don't reply to requests for personal/financial info · review bank's SMS policy · block texts from the internet · never call numbers from SMS · avoid non-telephonic numbers.
> Source: [[07-LO04b-General-Mobile-Platform-Security-Guidelines]]

> [!question]- 0440 — Android Device Administration API origin + purpose?
> Introduced in Android 2.2; system-level device administration for security-aware enterprise apps; device-admin apps enforce policies (email clients, remote-wipe security apps, device management).
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0441 — Key Android Device Admin policies?
> Password enabled · min password length · alphanumeric/complex password (Android 3.0) · password expiration/history · max failed attempts (wipe) · inactivity lock (1–60 min) · storage encryption (3.0) · disable camera (4.0).
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0442 — Which policy wipes the device?
> Maximum failed password attempts — device wipes its data after the allowed number of wrong entries; remotely resettable to factory defaults.
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0443 — Android hardening top countermeasures?
> Screen locks · never root · official market only · Google Android AV · no direct APK downloads · OS updates · encryption · AppLock · GPS on · remote-erase apps (Lookout, 3cX, SeekDroid) · per-app permissions review.
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0444 — Settings path for disabling visible passwords/secure credentials?
> Settings → Connections or Settings → More → Security (most Android devices).
> Source: [[07-LO05a-Android-Device-Admin-and-Security]]

> [!question]- 0445 — Find My Device prerequisites?
> On · signed into Google account · mobile-data/Wi-Fi connected · visible on Google Play · location enabled · Find My Device on.
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0446 — Find My Device actions?
> Play sound (full volume 5 min) · Lock (PIN/pattern/password + message/phone number) · Erase (permanent; SD card may survive; service stops working).
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0447 — X-Ray function?
> Scans Android device for unpatched (carrier-level) vulnerabilities; lists CVEs with per-vulnerability check; auto-updates for new disclosures.
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0448 — Where's My Droid tracking methods?
> Text-message attention word or the online control center "Commander"; features GPS, GPS Flare, SIM-change notification, stealth mode.
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0449 — Kaspersky VPN & Antivirus feature set?
> Anti-virus cleaner · background check · app lock · find my phone · anti-theft · anti-phishing · call blocker · web filter · data leak checker · smart home monitor.
> Source: [[07-LO05b-Android-Security-Tools]]

> [!question]- 0450 — iOS passcode/erase configuration paths?
> Settings → Touch ID and Passcode (Turn Passcode On, Erase Data, Voice Dial OFF); Auto-Lock: Settings → General → Auto-Lock.
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

> [!question]- 0451 — Default iPhone root password and the fix?
> Default root password is "Alpine" — must be changed. Never jailbreak/root in enterprise environments.
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

> [!question]- 0452 — Find My iPhone Lost Mode?
> iOS 6+ feature: locks the device with a passcode + custom message (e.g., contact number); tracks whereabouts and recent location history.
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

> [!question]- 0453 — Find My iPhone setup path?
> Settings → [your name] → iCloud → Find My iPhone → turn on Find My iPhone + Send Last Location (iOS 10.2-: Settings → iCloud).
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

> [!question]- 0454 — Key iOS hardening items?
> App Store only · no sensitive data on client-side DB or iCloud · no jailbreak · trusted third-party apps · ask-to-join Wi-Fi · Safari privacy settings + Do Not Track · disable BT/Wi-Fi when idle · regular Apple patches.
> Source: [[07-LO06-iOS-Security-Guidelines-and-Tools]]

### Module 08 (72 items)

> [!question]- 0455 — IoT definition in one line?
> Internet of Things (IoT) / Internet of Everything (IoE) — web-enabled devices that sense, collect, and send data via embedded sensors, communication hardware, and processors.
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0456 — What is a "thing" in IoT?
> A device implanted on natural, man-made, or machine-made objects that can communicate over a network.
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0457 — IoT interaction types?
> H2H (human-to-human, without PC), H2T (human-to-things), T2T (things-to-things).
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0458 — Four primary IoT technology systems?
> Sensing technology · IoT gateways · cloud server/data storage · remote control via mobile apps.
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0459 — IIoT three growth approaches?
> Increased production (revenue) · intelligent technology changing how goods are made · new hybrid business models.
> Source: [[08-LO01-IoT-Basics-and-Application-Areas]]

> [!question]- 0460 — Four layers of the IoT architecture (top-down)?
> Device → Communication → Cloud Platform → Process.
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0461 — IoT device-layer components?
> Sensors (temp, gyroscope, pressure, light, GPS, electrochemical, RFID) · mobile devices · microcontroller units · networking gear · single-board computers.
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0462 — Four IoT communication models?
> Device-to-Device · Device-to-Cloud · Device-to-Gateway · Back-end Data-Sharing (cloud-to-cloud).
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0463 — Protocols characteristic of device-to-gateway communication?
> ZigBee, Z-Wave (local), IEEE 802.11 (Wi-Fi), IEEE 802.15.4 (LR-WPAN).
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0464 — Back-end data-sharing model?
> Extends device-to-cloud: device data is accessed/analyzed later by authorized third parties (HTTPS, OAuth 2.0, JSON).
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0465 — Cloud gateway functions?
> Authenticate/authorize devices · data compression · secure device↔cloud transfer · protocol compatibility gateway.
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]]

> [!question]- 0466 — Key inherent IoT issues (top 6)?
> No security/privacy · vulnerable web interfaces · legal/regulatory gaps · default/weak/hardcoded credentials · cleartext protocols + open ports · coding errors (buffer overflow).
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0467 — Why are IoT DDoS/cryptojacking effective?
> IoT devices are usually never turned off, and many use default/hardcoded credentials.
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0468 — OWASP #1 IoT vulnerability?
> Weak, guessable, or hardcoded passwords.
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0469 — DDoS-from-hacked-IoT four phases?
> Identify + take over → reprogram device → activate → launch DDoS.
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0470 — Process-layer IoT threat impacts?
> Intellectual property theft, theft, repudiation → lawsuits, reputational damage.
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]]

> [!question]- 0471 — IoT stack-wise security principle for device layer?
> Tamper detection, encryption at rest, TLS v1.2/1.3, IoT-specific authentication protocols; Zero Trust per-device keys.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0472 — Communication edge layer countermeasures?
> Edge firewalls, IPsec ESP, traffic shaping (DNS/ICMP/ARP), out-of-band appliances.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0473 — Cloud platform IoT countermeasures?
> SIEM, IDPS, security analytics, federated access / bring-your-own-key.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0474 — Example IoT attack scenario target?
> Smart-building CCTV/security system — attacker spoofs cameras and AC/humidity sensors, maps the plant, causes damage.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0475 — IoT system management components?
> Device management · user management · security monitoring.
> Source: [[08-LO04a-IoT-Attack-Scenario-Security-Principles-and-System-Mgmt]]

> [!question]- 0476 — Top IoT device-layer attacks?
> Node tampering, jamming/RF interference, malicious node/tag injection, spoofing, tag cloning, replay, timing/Side-Channel, eavesdropping, hardware trojan, outage.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0477 — RFID relay attack countermeasures?
> Timers, challenge-response, distance-bounding protocols.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0478 — Bluesnarfing vs BlueBugging?
> Bluesnarfing = gains access to data via OBEX Push; BlueBugging = remote control of device via OBEX Push/FTP (place calls, AT commands).
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0479 — Bluetooth KNOB attack?
> Weakens Bluetooth encryption entropy from 8 to 1 byte.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0480 — WEP attack tools?
> Korek, Chopchop, Fragmentation, FMS, PTW; Google Replay attack.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0481 — Michael attack target?
> TKIP countermeasure flaw → forge fragmented packets (fix: CCMP/AES).
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0482 — KillerBee?
> ZigBee exploitation tool suite: zbdump, zbconvert, zbreplay, zbstumbler, zbfind, zbinject.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0483 — RPL attacks?
> DOG (denial-of-game), global repair attack, version-number modification, DAO inconsistencies.
> Source: [[08-LO04b-IoT-Device-and-Communication-Layer-Attacks]]

> [!question]- 0484 — IoT cloud-layer attacks?
> Account/theft, data-in-transit compromise, key/cert storage attacks, malware injection, botnets, backdoor/DoS, cloud service interruption.
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0485 — IoT data-at-rest encryption standard?
> AES-256 (ex: RSA 2048 + AES-256; TLS 1.2 across web).
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0486 — Cloud data-transit countermeasures?
> TLS v1.2, IPsec, DTLS, subnet-firewall ACLs, network redundancy.
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0487 — Process-layer IoT counters?
> Governance/policies, audit programs, user training, incident response, continuous improvement.
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0488 — Mirai?
> Botnet that exploits default credentials in IoT devices.
> Source: [[08-LO04c-IoT-Cloud-and-Process-Layer-Attacks]]

> [!question]- 0489 — Security measures M01–M05?
> Complete visibility → IoT asset maps → behavior monitoring → ecosystem-interface understanding → network segmentation.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0490 — Asset discovery tools for IoT (M01)?
> AssetExplorer (ManageEngine), ServiceNow ITSM, Azure IoT Hub, AWS IoT Device Management.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0491 — IoT asset map tool (M02)?
> Oracle IoT Asset Monitoring Cloud Service.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0492 — IoT behavior monitoring tools (M03)?
> Domotz Pro, TeamViewer IoT, Azure IoT Hub, AWS IoT Device Management.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0493 — OWASP #3 — insecure ecosystem interfaces?
> Web/mobile/cloud → weak authentication, weak encryption, missing filtering.
> Source: [[08-LO05a-IoT-Security-Measures-Visibility-and-Segmentation]]

> [!question]- 0494 — Security measures M06–M10?
> Limit access (ACL/PACL/VACL) → monitor malware/ransomware → vulnerability scan → firmware updates → close insecure network services.
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0495 — PACL vs VACL?
> PACL = Policy-based access control list; VACL = VLAN access control lists.
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0496 — IoT malware to monitor (M07)?
> Mirai, Echobot, Torii, Dark Nexus, WannaCry (EternalBlue).
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0497 — IoT vuln scanners (M08)?
> RloT Scanner, beSTORM; also Nexpose, Qualys, Tenable, Cloudpassage Halo, AlienVault USM.
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0498 — Firmware update best practice (M09)?
> Vet in sandbox, OTA where supported, sign updates, rollback plan.
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0499 — Port/service closure command (M10)?
> sudo nmap -sS -sU -O <target> · netstat -tulpn · nmap --top-ports 1000 <target>.
> Source: [[08-LO05b-IoT-Security-Measures-Access-Vulnerabilities-Firmware]]

> [!question]- 0500 — Security measures M11–M15?
> E2E encryption → E2E security & identity mgmt → strong authentication → chip-level security → hardware security.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0501 — E2EE protocols for IoT (M11)?
> TLS v1.2/1.3, IPsec ESP, DTLS, AES-256; no plaintext HTTP/Telnet/MQTT.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0502 — IoT identity mgmt (M12)?
> X.509 / mTLS device identity, PKI/private CA, certificate rotation.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0503 — Strong authentication for IoT (M13)?
> Unique credentials, MFA/2FA, smartcards/FIDO2, biometrics; per-device secrets.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0504 — Chip-level security (M14)?
> Secure SoC, cryptoprocessors, TPM 2.0, protected secure boot, Root of Trust.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0505 — Hardware security modules (M15)?
> HSM (key mgmt), Intel SGX / ARM TrustZone secure enclaves, secure elements, tamper-evidence.
> Source: [[08-LO05c-IoT-Security-Measures-Crypto-Identity-Hardware]]

> [!question]- 0506 — Security measures M16–M19?
> Secure gateways → secure control server → secure remote administration → router security.
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0507 — "Unplug n' Pray" (M18)?
> Physically disconnect an IoT device when it is physically compromised.
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0508 — SSH default port?
> Port 22 (use instead of Telnet port 23).
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0509 — Router hardening basics for IoT (M19)?
> WPA2/WPA3, disable WPS/UPnP/SNMP, change defaults, disable remote mgmt, zenmap/ShieldsUP scan.
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0510 — Control server (M17)?
> Sends commands to IoT devices; protect with MFA, RBAC, audited commands, SIEM, HSM signing.
> Source: [[08-LO05d-IoT-Security-Measures-Gateway-Control-RemoteAdmin-Router]]

> [!question]- 0511 — Security measures M20–M27?
> Wi-Fi isolation → Ethernet isolation → internet-access control → network monitoring → bandwidth monitoring → log centralization → public Wi-Fi security → shadow IoT management.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0512 — VLAN port mapping example (M21)?
> X1 = trunk/gateway, X2 = main LAN, X3 = IoT subnet.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0513 — Guest-network client isolation tool?
> pcWRT guest network (isolate IoT traffic from LAN).
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0514 — Bandwidth monitoring tools (M24)?
> SolarWinds (NPM / NetFlow Traffic Analyzer), Paessler PRTG.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0515 — Logarithm centralization (M25)?
> Cloud IoT Core + Stackdriver Logging (GCP); SIEM.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0516 — Shadow IoT discovery tool (M27)?
> Shodan — Internet-facing IoT devices outside IT control.
> Source: [[08-LO05e-IoT-Security-Measures-Isolation-Monitoring-ShadowIoT]]

> [!question]- 0517 — IoT device-check best practices?
> Secure boot, change defaults, disable unused services, firmware updates, disable Telnet port 23, monitor port 48101.
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0518 — SeaCat.io?
> Open-source mutual-TLS (mTLS) tunnel from Teskalabs; gateway + client for constrained devices.
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0519 — SeaCat port?
> 48101 (SeaCat mTLS gateway tunnel), Nginx 443.
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0520 — DigiCert IoT?
> Mutually-authenticated TLS for constrained IoT devices + cloud.
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0521 — Additional IoT security tools (top 4)?
> PwnPulse · Allot · Cisco IoT Threat Defense · AWS IoT Device Defender (also SecEdge, net-Shield, Noddos, Trustwave, Subex, libsecurity-go).
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]]

> [!question]- 0522 — AIOTI?
> Alliance for Internet of Things Innovation — EU multi-stakeholder platform; 17+2 WGs (WG09 = IoT Privacy/Security).
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

> [!question]- 0523 — NIST IAIP for IoT — 8 feature areas?
> Asset identification · device config · data protection · logical access · firmware updates · event monitoring · interface access · hardening.
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

> [!question]- 0524 — DHS IoT strategic principles (6)?
> Security-by-design · updates/vuln mgmt · recognized security practices · prioritize by impact · transparency · connect carefully.
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

> [!question]- 0525 — GSMA IoT security — 8 assessment areas?
> Secure boot · storage · key mgmt · OTA updates · app isolation · DDoS protection · user-data privacy · attack mitigation.
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

> [!question]- 0526 — Common Criteria standard for IoT eval?
> ISO/IEC 15408 — EAL 1–7 evaluation (FIPS 140-3 = crypto modules).
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]]

### Module 09 (47 items)

> [!question]- 0527 — Whitelisting = ? / philosophy?
> Allow-list control (trust-centric): allow only approved apps, deny by default → blocks everything not whitelisted.
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0528 — Whitelisting mitigates which attack class?
> Zero-day attacks (blocks vuln code execution while patches/signatures lag).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0529 — Blacklisting = ? / philosophy?
> Deny-list control (threat-centric): block known-bad apps, allow by default (AV, spam filters, IDS/IPS).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0530 — Blacklisting's main weakness?
> Cannot stop zero-day attacks and is never comprehensive (unknown theats slip through).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0531 — SRP rule types (4)?
> Path · Hash · Certificate · Internet Zone rules (of the default Disallowed level).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0532 — Most common whitelisting via SRP — two big caveats?
> A Disallowed app can still be run by copying it elsewhere; internet zone rules apply only to .msi.
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0533 — AppLocker controls which files?
> Executables, Windows Installer files, and DLLs (default rules = folder paths).
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0534 — AppLocker rule collections?
> Executable · Script · Windows Installer · Packaged app rules.
> Source: [[09-LO01a-Application-Whitelisting-Blacklisting-SRP-AppLocker]]

> [!question]- 0535 — Endpoint Central block methods?
> Path rule (by name/extension) and hash value (blocks even renamed exe); two policies per exe allowed.
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0536 — Endpoint Central two blacklisting features?
> Block Executable (targeted block) + Prohibit Software (auto detect/uninstall + approvals + reports).
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0537 — PUA PowerShell command?
> Set-MpPreference -PUAProtection 1 (admin; alternatives: Block / AuditMode / Disable / Not configured).
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0538 — Turn off Windows Installer options?
> Never (users can install/upgrade) · For non-managed apps only (admin-assigned) · Always (disables).
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0539 — Registry DisallowRun steps (hash)?
> HKCU\...\Policies → key Explorer → DWORD DisallowRun=1 → key DisallowRun → strings 1,2,3 = exe names → restart.
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0540 — McAfee Application Control whitelisting modes?
> default-Deny · Detect-and-Deny · Verify-and-Deny whitelisting.
> Source: [[09-LO01b-Application-Blacklisting-Tools-and-Blocking-Methods]]

> [!question]- 0541 — Sandboxing definition / goal?
> Run untrusted or untested third-party programs in a sealed container that blocks access to critical system resources; extra layer over host/OS.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0542 — Sandbox limitation (important)?
> Not robust against advanced malware targeting the OS kernel.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0543 — Two sandbox approaches?
> Isolation-based (program isolated from system). Rule-based (shares resources per policies).
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0544 — Windows UAC integrity levels vs sandbox?
> Edge Protected Mode runs low integrity; standard user = medium; elevated admin = high.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0545 — Chrome site-isolation flag methods?
> chrome://flags Strict-Origin-Isolation Enabled, or Chrome shortcut Target --site-per-process.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0546 — Firefox sandbox preference?
> about:support (Sandbox listing) or about:config security.sandbox.content.level.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0547 — Acrobat Protected Mode?
> Security (Enhanced) → Sandbox protections: Protected Mode at startup, AppContainer, Protected View modes.
> Source: [[09-LO02a-Application-Sandboxing-Approaches-and-Examples]]

> [!question]- 0548 — Windows Sandbox prerequisite?
> Virtualization enabled (Task Manager → Virtualization: Enabled); Windows Sandbox feature via Windows Features.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0549 — Firejail mechanism + examples?
> SUID + Linux namespaces + seccomp-bpf; private network stack/process table/mount table; `firejail firefox`, `firejail vlc`.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0550 — Sandboxie (Sophos) isolation?
> Blocks malware, viruses, ransomware, zero-day; stops websites from modifying system files/folders.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0551 — Shadow Defender behavior?
> Virtualizes drives; rebooting discards changes; Commit Now persists.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0552 — WDAG isolates?
> Microsoft Edge — blocks access to local storage, memory, installed apps, corporate network endpoints.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0553 — WDAG enable command?
> Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0554 — WDAG enterprise-mode trusted/neutral config?
> *.microsoft.com (enterprise cloud), bing.com (neutral), then enable Application Guard in Enterprise Mode.
> Source: [[09-LO02b-Sandbox-Tools-Windows-Sandbox-Firejail-Sandboxie-WDAG]]

> [!question]- 0555 — Patch management definition?
> Process of monitoring + deploying new or missing patches to keep applications on hosts secure.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0556 — Patch management flow?
> Scan for new/missing → download centrally → select relevant client patch → test → deploy if pass.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0557 — Why apply patches urgently?
> Hackers build exploits from each patch's disclosed vulnerabilities; unpatched apps get compromised.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0558 — Dashboard (patch status detection) shows?
> Patched + malicious software · unrecognized-app flags · unknown patch status · compliance reports.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0559 — Why test before org-wide deploy?
> Ensure patches don't break apps; tests on a few systems → deploy if successful.
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0560 — SolarWinds Patch Manager features?
> WSUS + SCCM integration, vulnerability mgmt, pre-tested packages, compliance reports, dashboard; patched 3rd-party apps (Adobe, Java, etc.).
> Source: [[09-LO03-Application-Patch-Management]]

> [!question]- 0561 — WAF working + layer?
> Rule-based filter before the web app; protects at layer 7 where standard firewalls/IDS-IPS fall short.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0562 — Three WAF types?
> Network/hardware-based · Host/software-based · Cloud-hosted.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0563 — Host vs network WAF granularity?
> Host gives more control (single server, any server, no hardware); network covers all apps/network via IP/port but less granular + pricey hardware.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0564 — WAF deployment options (5)?
> Reverse proxy · Layer-2 bridge · Out of band · Server resident · Internet hosted/cloud.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0565 — Out-of-band WAF advantage?
> Least impact (not in-line); copies traffic via monitoring port; avoids false-positive outages.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0566 — WAF benefits list?
> Cookie encryption/signature · CSRF protection + URL encryption (parameter tampering) · data-validation depth-testing · compliance (PCI, HIPAA, GDPR).
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0567 — WAF limits?
> Not replacement for auth/input filtering · can't read DB commands · partial session-fixation/anti-automation · no false-positive protection · needs ongoing management.
> Source: [[09-LO04a-Web-Application-Firewall-Types-Deployment-Benefits-Limitations]]

> [!question]- 0568 — URLScan purpose?
> IIS WAF tool filtering HTTP requests; SQL injection + XSS protection; rejects risky requests with HTTP 404.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0569 — URLScan reject criteria list?
> Request verb · file extension · suspicious URL encoding · non-ASCII chars · specified char sequences · specified headers.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0570 — NAXSI model?
> Open-source positive-model WAF for Nginx; no signature updates needed, low rule maintenance.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0571 — WebKnight placement?
> ISAPI filter for Microsoft IIS; blocks bad requests.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0572 — AppWall special coverage?
> Behind-CDN attacks, API manipulation, Slowloris, dynamic floods, brute-force on login pages.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

> [!question]- 0573 — Wallarm scope?
> APIs, microservices, web apps; OWASP API Top 10, API abuse, automated threats, real-time.
> Source: [[09-LO04b-WAF-Implementation-URLScan-and-Solutions]]

### Module 10 (98 items)

> [!question]- 0574 — What are the three states of data?
> Data at rest (inactive, stored) · data in use (RAM/CPU/database, actively processed) · data in transit (moving across the network).
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0575 — Which state does SSL/TLS and email encryption (PGP, S/MIME) protect?
> Data in transit.
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0576 — How is business-critical data identified?
> Business impact analysis → identify critical functions/data + dependent processes → evaluate impact of data damage on the business.
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0577 — What makes data "secured" (3 provisions)?
> Restrict destruction/modification/disclosure · recover lost/modified data after incidents · retention + destruction policies.
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0578 — Name the 7 data security technologies.
> Access control · encryption · masking · resilience/backup · destruction · retention · hardware-based security.
> Source: [[10-LO01-Importance-of-Data-Security]]

> [!question]- 0579 — Name the logical access control mechanisms.
> Access control lists (ACLs) · group policies · account restrictions · passwords / access tokens.
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0580 — How many ACE types exist and under which ACLs?
> 6 — 3 generic (access-denied, access-allowed in DACL; system-audit in system ACL) + 3 object-specific variants.
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0581 — Linux: how to mount a filesystem with ACL support?
> `mount -t ext3 -o acl [device] [mount]` (install with `yum install acl`; persist via /etc/fstab acl option).
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0582 — Linux: how to set a default ACL granting others rx on /Testdir?
> `setfacl -m d:o:rx /Testdir`.
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0583 — What does the pam_time rule `Login;*;!Martin;MoTuWeThFr0800-2000` mean?
> All services/tty, user Martin barred except weekdays 08:00–20:00.
> Source: [[10-LO02-Data-Access-Controls]]

> [!question]- 0584 — Name the 4 categories of data-at-rest encryption.
> Disk · file-level · removable media · database.
> Source: [[10-LO03a-Windows-Disk-Encryption-BitLocker-Device-Encryption-TPM]]

> [!question]- 0585 — Which two prereqs does Windows device encryption require?
> TPM + UEFI.
> Source: [[10-LO03a-Windows-Disk-Encryption-BitLocker-Device-Encryption-TPM]]

> [!question]- 0586 — How to check TPM status?
> `tpm.msc` → "The TPM is ready for use"; spec version shown.
> Source: [[10-LO03a-Windows-Disk-Encryption-BitLocker-Device-Encryption-TPM]]

> [!question]- 0587 — BitLocker cipher support?
> AES-CBC and AES-XTS, 128-bit or 256-bit.
> Source: [[10-LO03a-Windows-Disk-Encryption-BitLocker-Device-Encryption-TPM]]

> [!question]- 0588 — FileVault: how to enable and what unlocks it?
> System Preferences → Security & Privacy → FileVault → Turn On; unlock via login password or recovery key.
> Source: [[10-LO03b-OS-Encryption-Linux-Mac-Android-iOS]]

> [!question]- 0589 — What algorithm/state set does Android dm-crypt use?
> AES-128-CBC; states Default, PIN, Password, Pattern.
> Source: [[10-LO03b-OS-Encryption-Linux-Mac-Android-iOS]]

> [!question]- 0590 — LUKS over plain dm-crypt: key benefits?
> Change password without re-encrypting data; multiple keys; brute-force protection (header + encrypted master key).
> Source: [[10-LO03b-OS-Encryption-Linux-Mac-Android-iOS]]

> [!question]- 0591 — Command to encrypt a file / wipe free space with EFS?
> `cipher /e <file>`; `cipher /w:dir` wipes deleted-data area (free-space cleaning).
> Source: [[10-LO03c-File-Level-and-Removable-Media-Encryption]]

> [!question]- 0592 — Which Windows editions lack EFS?
> Windows Home (and similar low-tier editions).
> Source: [[10-LO03c-File-Level-and-Removable-Media-Encryption]]

> [!question]- 0593 — Two ways Windows guards USB removable media?
> BitLocker To Go (TPM-less password/PIN) + third-party USB encryption.
> Source: [[10-LO03c-File-Level-and-Removable-Media-Encryption]]

> [!question]- 0594 — macOS encrypted disk image: default cipher?
> AES-128 (Disk Utility New Image from Folder).
> Source: [[10-LO03c-File-Level-and-Removable-Media-Encryption]]

> [!question]- 0595 — TDE: key hierarchy order and default algorithm?
> DEK → certificate → master key; default AES-128 (also AES-192/256, 3DES).
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0596 — Which statement turns on TDE for a database?
> `ALTER DATABASE <db> SET ENCRYPTION ON`.
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0597 — Always Encrypted randomized vs deterministic?
> Randomized = different ciphertext each time, no equality ops; Deterministic = same ciphertext for same plaintext, enables equality lookups/joins.
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0598 — Where are Always Encrypted keys held, and what does the engine see?
> Keys stored client-side (Column Master Key/Column Encryption Key); engine never sees plaintext or keys → protects at rest + in transit.
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0599 — Oracle TDE: what can be encrypted and what enables the keystore?
> Specific table columns or entire tablespace; wallet opened via `ALTER SYSTEM SET ENCRYPTION WALLET OPEN`.
> Source: [[10-LO03d-Database-Encryption-and-Best-Practices]]

> [!question]- 0600 — What does the browser verify during the SSL handshake before showing the green padlock?
> Server certificate authenticity — Issued To/By, validity, CA signature — preventing MITM.
> Source: [[10-LO04a-Browser-WebServer-TLS-Certificates]]

> [!question]- 0601 — In Chrome Details tab, which fingerprint types appear on a cert?
> SHA-256 (and MD5/SHA-1 for legacy) fingerprints; public key size (e.g., 2048-bit RSA).
> Source: [[10-LO04a-Browser-WebServer-TLS-Certificates]]

> [!question]- 0602 — EV vs standard SSL difference in what the user sees?
> EV → green-bar address bar + organization verified; standard → HTTPS padlock only.
> Source: [[10-LO04a-Browser-WebServer-TLS-Certificates]]

> [!question]- 0603 — In the IIS CSR Distinguished Name, what is the common name field filled with?
> Fully-qualified server domain — e.g. www.luxurytreats.com.
> Source: [[10-LO04b-IIS-SSL-Certificate-Lifecycle]]

> [!question]- 0604 — Default IIS cryptographic service provider for an SSL CSR?
> Microsoft RSA SChannel Cryptographic Provider.
> Source: [[10-LO04b-IIS-SSL-Certificate-Lifecycle]]

> [!question]- 0605 — How does IIS bind the cert to a site?
> Site → Bindings → https :443 → select certificate.
> Source: [[10-LO04b-IIS-SSL-Certificate-Lifecycle]]

> [!question]- 0606 — How do you move the same cert to an additional web server?
> IIS → Server Certificates → Export to .pfx (with private key + password), then import on the other node and bind.
> Source: [[10-LO04b-IIS-SSL-Certificate-Lifecycle]]

> [!question]- 0607 — Which two DB platforms get transport encryption in this subsection?
> MS SQL Server (Force Encryption) and Oracle (Advanced Security SSL).
> Source: [[10-LO04c-Database-Server-Web-Server-Encryption]]

> [!question]- 0608 — SQL Server: where is Force Encryption enabled?
> SQL Server Configuration Manager → Protocols for MSSQLSERVER → Flags → Force Encryption = Yes → Apply → restart SQL Server service.
> Source: [[10-LO04c-Database-Server-Web-Server-Encryption]]

> [!question]- 0609 — Where is the Outlook "Encrypt contents and attachments for outgoing messages" toggle?
> File → Options → Trust Center → Trust Center Settings → Email Security.
> Source: [[10-LO04d-Email-Encryption]]

> [!question]- 0610 — What three cert/algorithm settings does Outlook S/MIME let you change?
> Signing certificate, encryption certificate, hash/encryption algorithms (+ format, send-cert-with-sign).
> Source: [[10-LO04d-Email-Encryption]]

> [!question]- 0611 — What must S/MIME recipients have to read encrypted incoming mail?
> Your public certificate (available to them) and their own private key; Exchange publishes certs to GAL.
> Source: [[10-LO04d-Email-Encryption]]

> [!question]- 0612 — What is data masking?
> Hiding original data with random characters/other data, minimizing exposure of PII, PHI, PCI card data, IP while keeping a realistic format.
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0613 — SDM vs DDM vs on-the-fly masking?
> SDM = mask at rest (DB copy); DDM = mask in transit (role-based, proxy alters SQL); on-the-fly = transform between source and target environments.
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0614 — 4 reasons to include masking in data security?
> Nonproduction data protection · insider threats · third-party sharing · regulatory compliance (GDPR).
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0615 — Masked card example `2424 6789 4545 3421`?
> `2424 XXXX XXXX 3421` — format preserved, key values changed.
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0616 — What factors guide data masking type selection?
> Organization size · location (cloud vs on-premise) · complexity of data to secure.
> Source: [[10-LO05a-Data-Masking-Concepts-and-Types]]

> [!question]- 0617 — Name the 4 data masking types by environment.
> Static (at rest), Dynamic (in transit/role-based), On-the-fly (between environments); plus DB proxies for DDM.
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0618 — Three distinguishing masking algorithms for numbers/dates/IQ.
> Number/Date Variance (random %), Date Aging (policy per field), Averaging/Data Generalization (average values).
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0619 — What technique replaces card numbers w/ valid-looking but fake numbers?
> Substitution (meets card-provider validation rules).
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0620 — Tokenization vs format-preserving encryption?
> Tokenization = unique tokens map back to original (IDs, cards); FPE = encrypts preserving length/character set (phones, cards).
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0621 — What does the F.A.S.T. acronym in Oracle data masking mean?
> Find → Access → Secure → Test.
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0622 — Which SQL Server DDM mask function masks the entire field per data type?
> `default()` — e.g., `alter table employee alter column empname ... masked with (Function='default()')`.
> Source: [[10-LO05b-Data-Masking-Algorithms-and-Database-Implementation]]

> [!question]- 0623 — Primary purposes of a data backup?
> Reinstate a system to its normal working state after damage, or recover data/information following data loss or corruption.
> Source: [[10-LO06a-Backup-Strategy-Basics]]

> [!question]- 0624 — Four categories of data-loss causes.
> Human error · crimes · natural causes (power/software/hardware) · natural disaster.
> Source: [[10-LO06a-Backup-Strategy-Basics]]

> [!question]- 0625 — 8-step data backup strategy?
> Identify critical data → select backup media → backup technology → RAID levels → backup method → backup types → right solution → recovery drill test.
> Source: [[10-LO06a-Backup-Strategy-Basics]]

> [!question]- 0626 — Backup media selection factors?
> Cost, reliability, speed, availability, usability.
> Source: [[10-LO06a-Backup-Strategy-Basics]]

> [!question]- 0627 — Which RAID level offers striping with NO fault tolerance?
> RAID 0 (minimum 2 disks).
> Source: [[10-LO06b-RAID-Technology]]

> [!question]- 0628 — RAID 50 = what combination, minimum disks?
> Striping across mirrored pairs (RAID 0 over RAID 1); minimum 6 disks.
> Source: [[10-LO06b-RAID-Technology]]

> [!question]- 0629 — RAID 3 vs RAID 5 parity placement?
> RAID 3 = dedicated parity disk; RAID 5 = parity distributed across all disks.
> Source: [[10-LO06b-RAID-Technology]]

> [!question]- 0630 — Minimum disks for RAID 10?
> 4 (2 mirrored pairs, striped).
> Source: [[10-LO06b-RAID-Technology]]

> [!question]- 0631 — NAS = which protocol layer and example file protocols?
> File-level; CIFS/SMB and NFS.
> Source: [[10-LO06c-SAN-and-NAS-Storage]]

> [!question]- 0632 — SAN serves data at what level?
> Block-level (Fibre Channel / iSCSI); presented as raw disk to servers.
> Source: [[10-LO06c-SAN-and-NAS-Storage]]

> [!question]- 0633 — Typical NAS capacity split high-end/mid-market/low-end?
> Enterprise (TB-scale, clustered) · mid-market (~100 TB) · desktop/low-end (~8 TB).
> Source: [[10-LO06c-SAN-and-NAS-Storage]]

> [!question]- 0634 — Difference between incremental and differential backup?
> Incremental backs up changes since last full OR incremental; differential backs up all changes since the last full backup.
> Source: [[10-LO06d-Backup-Methods-Types-and-Locations]]

> [!question]- 0635 — Which type makes the restore longest (needs most media)?
> Incremental restores (must replay full + every incremental since).
> Source: [[10-LO06d-Backup-Methods-Types-and-Locations]]

> [!question]- 0636 — What is a snapshot?
> A near-instant point-in-time copy of data used for quick rollback/recovery.
> Source: [[10-LO06d-Backup-Methods-Types-and-Locations]]

> [!question]- 0637 — File History frequency range?
> Every 10 minutes up to daily (saved versions browsable by time).
> Source: [[10-LO06e-OS-and-App-Backups-Windows-Linux-Mac]]

> [!question]- 0638 — Time Machine retention schedule?
> Hourly (past 24 h), daily (past month), weekly (all remaining history); supports encrypted backups.
> Source: [[10-LO06e-OS-and-App-Backups-Windows-Linux-Mac]]

> [!question]- 0639 — Two CLI tools for Linux file backup?
> `tar` (archives) and `rsync` (incremental sync); `dd` for raw block images.
> Source: [[10-LO06e-OS-and-App-Backups-Windows-Linux-Mac]]

> [!question]- 0640 — Cold (offline) Oracle backup procedure order.
> SHUTDOWN IMMEDIATE → STARTUP MOUNT → BACKUP DATABASE → ALTER DATABASE OPEN.
> Source: [[10-LO06f-Database-Email-Web-Backups]]

> [!question]- 0641 — What is required for a hot backup of Oracle via RMAN?
> ARCHIVELOG mode enabled; use `BACKUP DATABASE PLUS ARCHIVELOG`.
> Source: [[10-LO06f-Database-Email-Web-Backups]]

> [!question]- 0642 — What does a full cPanel backup include besides files?
> MySQL databases, email configuration, and related config; plus website files.
> Source: [[10-LO06f-Database-Email-Web-Backups]]

> [!question]- 0643 — What is a data retention policy?
> Rules for preserving/maintaining data for operational or regulatory compliance — defines retention periods per data type + minimum destruction standards.
> Source: [[10-LO06g-Data-Retention]]

> [!question]- 0644 — Name regulatory/legal drivers of data retention named in courseware.
> HIPAA, SOX, IRS, COPPA, EU GDPR.
> Source: [[10-LO06g-Data-Retention]]

> [!question]- 0645 — 5 steps to create a data retention policy.
> Build team → identify applicable regulatory compliances → specify included data types → develop policy → inform all employees.
> Source: [[10-LO06g-Data-Retention]]

> [!question]- 0646 — 3 best practices for a data retention policy.
> Simple and easy to implement · different policies per data type · retain customer/user info only as long as necessary · move infrequently accessed files to lower-level archive.
> Source: [[10-LO06g-Data-Retention]]

> [!question]- 0647 — What is data destruction and its main purpose?
> Destroying stored data into an unreadable form so it can't be accessed/exploited; purpose = restrict unauthorized disclosure via proper disposal/destruction of media.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0648 — Name the 4 data destruction techniques.
> Clearing · Purging · Destroying · Disposal.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0649 — Clearing protects against which attack? Purging?
> Clearing vs keyboard/simple recovery attacks; purging vs laboratory (signal-processing) attacks.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0650 — Degaussing applies to which media and what side-effect?
> Magnetic media only (not optical CD/DVD); typically makes the HDD inoperable and can damage nearby devices.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0651 — Shredding requirement for destroyed pieces?
> Pieces no larger than 2 mm.
> Source: [[10-LO07a-Data-Destruction-Concepts-and-Techniques]]

> [!question]- 0652 — Sequence for wiping a disk with Windows DiskPart.
> `diskpart` → `list disk` → `select disk 1` → `clean` → `create partition primary` → `select partition 1` → `active` → `format FS=NTFS label=Data quick` → `assign letter=w` → `exit`.
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0653 — Why is DBAN unsuitable for full sanitization/audit?
> May not fully sanitize the entire drive, cannot detect/erase SSDs, and provides no certificate of data removal for audits/compliance.
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0654 — What are the 3 NIST SP 800-88 sanitization methods?
> Clear (overwrite user-addressable memory) · Purge (including SSD-specific vendor commands) · Destroy (physical).
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0655 — The three passes of DoD 5220.22-M?
> Pass 1 binary zeros → Pass 2 binary ones → Pass 3 random bit pattern (final pass verified).
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0656 — PCI DSS requirement for disposed card data?
> Req 9.10 — render cardholder data (CHD) unreadable and unrecoverable once no longer needed.
> Source: [[10-LO07b-Data-Destruction-Standards-and-Tools]]

> [!question]- 0657 — What is DLP?
> Software products + processes that prevent users from sending confidential corporate data outside the organization.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0658 — Name the 3 DLP types and what data phase each protects.
> Endpoint DLP = data in use · Network DLP = data in transit · Storage DLP = data at rest.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0659 — Where is Network DLP typically installed and what does it scan?
> At the network perimeter; scans all data in transit — email, social media, SSL, IM across ports/protocols.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0660 — What inspection channels does MyDLP (open source) support?
> Web, email, instant messaging, printers, removable storage devices, screenshots.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0661 — Key DLP implementation best practice regarding false positives?
> Implement with a minimal base to reduce false positives, then enhance gradually as sensitive data is identified.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0662 — Which Microsoft solution provides endpoint DLP and integrates with AIP?
> Windows Information Protection (WIP); Windows Defender ATP evaluates content, Azure Information Protection aggregates labeled files.
> Source: [[10-LO08-Data-Loss-Prevention]]

> [!question]- 0663 — What is data integrity?
> Accuracy, consistency, and reliability of data throughout its lifecycle — unaltered/trustworthy from creation to deletion.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0664 — Name the characteristics of data integrity.
> Complete, Accurate, Safe, Compliance, Consistent, Reliable, Timeliness.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0665 — Two main categories of data integrity and the 4 logical sub-types.
> Physical and Logical; logical = entity, referential, domain, user-defined.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0666 — Three hash methods named for integrity checking?
> MD5, SHA-256, SHA-3 (checksums/hash functions).
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0667 — What additive redundancy detects/corrects errors in memory and storage?
> Error-correcting codes (ECC); parity checks + CRC for transmission/storage error detection.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0668 — How does a digital signature verify integrity?
> Sender signs data with private key; recipient verifies with sender's public key; any alteration invalidates the signature.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0669 — Integrity-preservation checklist items?
> Validate input · validate data · remove duplicate data · perform regular backups · control access (least privilege) · prepare audit trail.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0670 — Give one countermeasure per physical-integrity threat.
> Error-correcting memory, battery-protected write cache, redundant storage (RAID) for hardware/power/storage threats.
> Source: [[10-LO09-Data-Integrity]]

> [!question]- 0671 — Difference between data security and data integrity?
> Security = protect against unauthorized access/disclosure/modification/destruction (privacy); integrity = data stays unaltered and correct (reliability).
> Source: [[10-LO09-Data-Integrity]]

### Module 11 (207 items)

> [!question]- 0672 — ``` / Traditional network management activities, in courseware order?
> Evaluation, selection, procurement, installation, configuration - plus managing security of network devices. _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0673 — ``` / Two consequences of protracted procurement cycles in the traditional model?
> Installing a device in a remote location was difficult; combined with purpose-built hardware it gave no adequate flexibility. _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0674 — ``` / Dynamic requirements the traditional network paradigm could not fulfill?
> Provisioning and de-provisioning of infrastructure such as servers, security policy modification, and performance monitoring. _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0675 — ``` / Which virtualization-enabled network technologies do organizations transition to?
> Software-defined networking (SDN) and network function virtualization (NFV). _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0676 — ``` / Application classes driving dynamic throughput demand?
> Commerce, media, voice, mobile and IoT applications - alongside geographic expansion. _(Mod 11 p5)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0677 — ``` / Seven benefits the courseware claims for virtualization-enabled technologies?
> Greater flexibility; centralized control of organizational resources; fine granularity in policy enforcement; protection of data and applications; security of resources; improved management of processing demands with network automation; enhanced network efficiency. _(Mod 11 p6)_
> ```
> Source: [[11-LO01a-Evolution-of-Network-Management]]

> [!question]- 0678 — ``` / List the ten risks the courseware associates with virtual environments.
> VM sprawling; sensitive data within a VM; security of offline and dormant VMs; security of pre-configured/active VMs; lack of visibility and control over virtual networks; resource exhaustion; hypervisor security; account or service hijacking; workloads of different trust levels on the same server; cloud service provider APIs. _(Mod 11 p7-p8)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0679 — ``` / Why can one breach in a virtualized environment spread beyond the VM?
> Multiple virtualized environments may be physically collocated in a single host and each environment's isolation is software-based - so a breach can wreak havoc across the entire targeted host, possibly outside the virtual environment. _(Mod 11 p7)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0680 — ``` / VM sprawling - courseware definition and consequence?
> VMs are easily created, so their number can rise to a point the administrator can no longer manage them effectively; it can increase the number of unpatched VMs in the network environment. _(Mod 11 p7)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0681 — ``` / Why are offline and dormant VMs dangerous?
> They may lag behind the baseline security of the environment and, if started, can serve as potential entry points for breaches. _(Mod 11 p8)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0682 — ``` / Hypervisor security risk - what and why it matters?
> Unauthorized access to the hypervisor can change the security of a device or server on it, so the hypervisor is potentially a single point of failure for the VMs on the host. _(Mod 11 p8)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0683 — ``` / Account or service hijacking vector in a virtual environment?
> The virtual environment and hypervisor are often accessed through a self-service portal; compromise of an account on that portal has significant security consequences. _(Mod 11 p8)_
> ```
> Source: [[11-LO01b-Virtualization-Security-Risks]]

> [!question]- 0684 — Courseware definition of virtualization
> Software-based **virtual representation** of an IT infrastructure (network, devices, applications, storage, etc.); the framework divides physical resources into multiple individual simulated environments.
> Source: [[11-LO02a-Virtualization-Fundamentals]]

> [!question]- 0685 — Who converts commands to binary instructions in full virtualization?
> The **VMM** — it translates the guest's commands to binary instructions and forwards them to the host OS; resources reach the guest through the VMM.
> Source: [[11-LO02a-Virtualization-Fundamentals]]

> [!question]- 0686 — In the virtualization architecture, who interacts with the hardware directly?
> The **host OS**. The **guest OSes interact through the virtualization layer**, which acts as middleware and logically partitions hardware resources.
> Source: [[11-LO02a-Virtualization-Fundamentals]]

> [!question]- 0687 — Cardinality rule for virtual vs physical resources
> N virtual resources may be created from **one** physical resource, **or** one virtual resource from **one or more** physical resources.
> Source: [[11-LO02a-Virtualization-Fundamentals]]

> [!question]- 0688 — Full virtualization — guest awareness, request path, translator
> Guest is **unaware**; guest → **VMM** → host OS; the **VMM** translates to binary and forwards, and allocates resources to the guest.
> Source: [[11-LO02b-Virtualization-Approaches]]

> [!question]- 0689 — OS-assisted / para virtualization — who translates, and is the VMM involved?
> The **guest OS** translates its own commands to binary for the hardware; the **VMM is not involved** in the request and response operations.
> Source: [[11-LO02b-Virtualization-Approaches]]

> [!question]- 0690 — Hardware-assisted virtualization — what enables it?
> **Special instructions in modern microprocessor architectures** let the guest OS execute privileged instructions directly on the processor; the OS treats system calls as user programs.
> Source: [[11-LO02b-Virtualization-Approaches]]

> [!question]- 0691 — Hybrid virtualization — what does the guest use, and what does the VMM still do?
> The guest **adopts para-virtualization functionality**; the **VMM is still used for binary translation** to different types of hardware resources.
> Source: [[11-LO02b-Virtualization-Approaches]]

> [!question]- 0692 — Levels of virtualization — list the four
> **Storage Device** (striping/mirroring; RAID) · **File System** · **Server** (partition of the server OS environment / hard drive) · **Fabric** (virtual devices independent of physical hardware; SAN).
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0693 — Which technologies achieve fabric-level virtualization, and what do they create?
> **SAN** (storage area network); a **massive pool of storage areas** for the different VMs on the hardware, with virtual devices independent of the physical computer hardware.
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0694 — Types of virtualization — list the four
> **Operating System** · **Network** · **Server** · **Desktop**.
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0695 — Network virtualization — the two directions
> Multiple physical networks **combined into a single software-based virtual network**, **or** a single physical network **divided into multiple independent virtual networks**. Both are an abstraction of network resources.
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0696 — Desktop virtualization — where does the desktop and the data live?
> The desktop OS instance lives in a **central server on the cloud** (hosted on a remote central server, possibly a cluster) and is accessed from **any device**; the data and files are **not stored on the user's system** but in the cloud.
> Source: [[11-LO02c-Virtualization-Levels-and-Types]]

> [!question]- 0697 — Virtualization components — list the seven
> Hypervisor / VMM · Guest machine · Host / physical machine · Management Server · Management Console · Network Components · Virtual Storage.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0698 — Which two components decouple the control and forwarding planes?
> **Software Defined Network (SDN)** and **Network Function Virtualization (NFV)** — not NV.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0699 — What do SDN and NFV combine, and what does that produce?
> They **combine hardware and software** to create a **completely software-defined network** → simpler provisioning and management of network resources.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0700 — Enablers — how do the virtual networks relate to the physical network and to virtual environments?
> They are **decoupled from the underlying network hardware**, **integrate with virtual environments**, and can **run independently over a physical network in a hypervisor**.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0701 — What does virtual storage do, and what is an example network component?
> Virtual storage **abstracts physical storage into a single storage device** so the systems on the host can share it. Network components include **firewalls, load balancers, storage, switches, network interface cards**.
> Source: [[11-LO02d-Virtualization-Components-and-Enablers]]

> [!question]- 0702 — ``` / What single administrative unit is at the heart of the courseware NV definition?
> NV = combining all available network resources and sharing them among network users under a single administrative unit; hardware-allocated resources are abstracted into software. _(Mod 11 p17–p18)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0703 — ``` / How does NV handle the available bandwidth?
> It splits it into independent channels, assigned or reassigned to a particular server or device in real time. _(Mod 11 p18)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0704 — ``` / What does the "Benefits of Network Virtualization" side panel list?
> Efficient, flexible, scalable usage · logically segregates underlay administrative from overlay domain · automates network and security protocols · security by resource isolation · enhanced application delivery and reduced overall cost. _(Mod 11 p18)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0705 — ``` / What are the building blocks of a virtual network in an NVE?
> A collection of virtual nodes and virtual links — a subset of the underlying physical network resources. _(Mod 11 p19)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0706 — ``` / Name the five virtual-network examples listed by the courseware.
> VLAN · virtual service network (VSN) · virtual private network (VPN) · active and programmable networks · overlay networks. _(Mod 11 p19)_
> ```
> Source: [[11-LO03a-Network-Virtualization-Concepts]]

> [!question]- 0707 — ``` / What determines whether virtual network software goes inside or outside the virtual server?
> The size and type of the virtualization platform. Software placed inside = Internal Virtual Network; outside = External Virtual Network. _(Mod 11 p19, p20)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0708 — ``` / Which component acts as the virtual network software for an internal virtual network?
> The hypervisor — it provides the abstraction layer that lets internal virtual network types mimic physical networks, and implements virtualization at the server or cluster level. _(Mod 11 p21)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0709 — ``` / What hardware/software relationship makes external network virtualization possible?
> Managed/intelligent (layer 3) switches run virtualization software modules that abstract the physical switch ports and the surrounding network. _(Mod 11 p25)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0710 — ``` / Which virtualization type combines multiple physical LANs into one, or subdivides one physical LAN into isolated virtual networks?
> External network virtualization (e.g. VLAN + switch technology). _(Mod 11 p25)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0711 — ``` / Which hypervisor products does the courseware list, and what licence is VirtualBox under?
> VMware ESXi, Citrix Hypervisor 8.2 (formerly XenServer), Virtual Iron, Microsoft Hyper-V Server, VirtualBox — VirtualBox is free open source under GPL version 2. _(Mod 11 p22–p23)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0712 — ``` / How does VMware ESX Server 3 start up, and which component runs as the first VM?
> The vmkernel starts first and loads the virtualization components; the service console invokes the Linux kernel as the primary VM and runs as the first virtual machine. Type-I, bare metal. _(Mod 11 p24)_
> ```
> Source: [[11-LO03b-Virtual-Network-Types-and-Placements]]

> [!question]- 0713 — ``` / Name the three threat classes the courseware uses to classify hypervisor/VMM vulnerabilities.
> Disclosure, Deception, Disruption. _(Mod 11 p30)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0714 — ``` / Which hypervisor security features do its vulnerabilities attach to, and what else is affected besides the hypervisor itself?
> VM isolation and the internal software-based channels used to communicate with VMs; the weaknesses also affect VMMs and their management tools. _(Mod 11 p30)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0715 — ``` / Give the Xen example of improper input validation in the hypervisor and its impact.
> The intercept function in a software library uses an improper range → local HVM guests read data from the hypervisor or other guest machines; can also cause DoS or crash the host. _(Mod 11 p30)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0716 — ``` / What is an off-by-one error in the hypervisor's data handling, and what does it expose?
> An iterative loop iterates too many or too few times → local users obtain sensitive information from hypervisor memory; can also cause DoS or crash of the host. _(Mod 11 p30)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0717 — ``` / Define VM escape per the courseware and list its consequences.
> Attackers run code on a VM to directly communicate with the hypervisor, exploiting hypervisor coding or management errors → DoS, out-of-bounds writes, guest crash, and execution of arbitrary code. _(Mod 11 p31)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0718 — ``` / How does injection in hypervisor software libraries hurt, and what address type is named?
> Local guest users cause DoS and crash the host via a non-canonical guest address. _(Mod 11 p31)_
> ```
> Source: [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]]

> [!question]- 0719 — List the four threat classes the courseware uses to classify virtual network vulnerabilities.
> Disclosure, Deception, Disruption, Usurpation. _(Mod 11 p32)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0720 — Insufficient verification of data authenticity in a virtual network: what does it produce?
> Misbehaving virtual routers repeatedly resend old control messages (reply attacks), corrupting the data plane and causing DoS. _(Mod 11 p32–p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0721 — Why does rollback of networking activity logs stored in a VM matter (Deception)?
> It causes the loss of network entity activities and subsequently impacts the non-repudiation of actions. _(Mod 11 p32–p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0722 — Improper validation in a virtual network: how is the DoS produced?
> Incorrect throwing of exceptions when handling malformed, truncated, or maliciously crafted packets. _(Mod 11 p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0723 — Usurpation: give the three weakness and effect pairs.
> Injection -> privilege escalation; privileges and permissions -> controlling virtual network nodes like virtual routers; credentials management -> brute-force password guessing against the network management console. _(Mod 11 p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0724 — Which weakness sits under both Deception and Usurpation, and how do the effects differ?
> Injection. Deception: messages made to look as if from a legitimate entity -> identity fraud. Usurpation: messages from a fake source with high privileges -> privilege escalation. _(Mod 11 p32–p33)_
> Source: [[11-LO03d-Virtual-Network-Vulnerabilities-and-Attacks]]

> [!question]- 0725 — MAC flooding: mechanism and effect.
> The attacker sends a large number of fake MAC addresses to overflow the CAM table; once it is full, traffic without MAC entries floods out to all ports of the VLAN, making it easy to view and retrieve the traffic. _(Mod 11 p34–p35)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0726 — ARP attack: mechanism and the two stated effects.
> Fake ARP messages over the LAN bind the attacker's MAC to the IP of a legitimate host and poison the ARP table; it tricks the switch into forwarding packets with forged identities to a device in a different VLAN, and in the same VLAN it tricks end nodes such as routers and workstations. _(Mod 11 p34–p35)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0727 — Give the mechanism and effect of the DHCP starvation and multicast brute-force attacks.
> DHCP starvation: multiple DHCP requests with spoofed MAC addresses cause DoS at the DHCP server. Multicast brute-force: several multicast frames injected into a VLAN in quick succession leak frames from the original VLAN to other VLANs. _(Mod 11 p35–p36)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0728 — Double tagging: how are the two 802.1Q tags arranged and what follows?
> The inner tag is the VLAN the user wants to reach, the outer tag is the native VLAN; the switch removes the native VLAN and forwards the second frame to the trunk interface(s), so the attacker jumps from native VLAN to user VLAN and can conduct a DoS attack. _(Mod 11 p35)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0729 — Switch spoofing: what does the attacker exploit and what does it emulate?
> The default 'dynamic auto' or 'dynamic desirable' port mode plus an incorrectly configured trunk port to spoof itself as a switch; it then emulates 802.1Q and DTP messages. _(Mod 11 p35–p36)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0730 — Spanning-tree attack: the two variants and their outcomes.
> After obtaining the port ID information, send STP configuration/topology change acknowledgement BPDUs claiming to be the new root bridge with lower priority to gain access to network traffic; or install a new STP device and transmit junk data to flood packets and shut services down for a short period. _(Mod 11 p36)_
> Source: [[11-LO03e-VLAN-Attacks]]

> [!question]- 0731 — Front: Inconsistent time between Hyper-V guests and the host causes what failures?
> Authentication failures, and it affects security protocols such as Kerberos, certificate-dependent technologies that rely on time synchronization, and billing processes. Time sync also provides security and event correlation. _(Mod 11 p37, p39)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0732 — Front: How is time synchronization enabled in Hyper-V?
> Windows start menu → Hyper-V Manager → select the VM → right-click → Settings → Management section → Integration Services → check Time synchronization → Apply → OK. _(Mod 11 p39–p41)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0733 — Front: Besides controlling user access, what does setting Hyper-V access privileges achieve?
> It reduces the attack surface area, preventing damage from external and internal attacks. By default Hyper-V provides a group of admins with all administrative rights for the VMs. _(Mod 11 p41)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0734 — Front: Set-SmbServerConfiguration: which -MaxChannelPerSession value is paired with -Force?
> 32 with -Force; 16 is the variant that prompts for confirmation. _(Mod 11 p39)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0735 — Front: Name the three VMware hypervisor security measures.
> Time synchronization · Restrict user access · Encrypting guest virtual machines. _(Mod 11 p51–p52)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0736 — Front: Which two Windows services must be disabled on Windows Server 2016, and what else alongside them?
> Xbox Live Auth Manager and Xbox Live Game Save — plus their respective scheduled tasks. _(Mod 11 p46)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0737 — Front: Isolated User Mode: what is it and which two Windows virtualization-security siblings share its role?
> A virtualization-based security feature using secure kernels, separating business data/processes from the OS. Siblings: Credential Guard and Device Guard. Stops pass-the-hash attacks. _(Mod 11 p48)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0738 — Front: How is the VMware decryption password related to the VM password?
> They need not be the same. _(Mod 11 p52–p53)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0739 — Front: Which CVE IDs make disabling hyperthreading mandatory on affected hosts?
> CVE-2018-12126 and CVE-2018-12127. _(Mod 11 p56)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0740 — Front: What is the stated trade-off of disabling nested paging in VirtualBox?
> It makes AVX, XSVAE and POPCNT unavailable to guests, causing stability issues (especially during SMP configuration). _(Mod 11 p56)_
> Source: [[11-LO03f-Hypervisor-Security]]

> [!question]- 0741 — Front: List the four virtual-network recommendations that concern identity, standards, data and accountability.
> Assure a robust identity · Ensure security on open standards · Protect operational reference data · Provide accountability and traceability. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0742 — Front: Which recommendation covers data in transit between hosts and clients?
> Use cryptographic controls like SSL encryption on the network traffic between the hosts and the clients. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0743 — Front: How do the recommendations counter MAC spoofing?
> Enable MAC address filtering on the switches. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0744 — Front: What physical-layer recommendation prevents unauthorized device connections?
> Disconnect network interface controllers (NIC) to prevent outsiders from connecting to the network easily. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0745 — Front: Name the four network-architecture recommendations.
> Use segregation in networks · clearly define security dependencies and trust boundaries · make systems secure by default · provide manageable security controls. _(Mod 11 p59)_
> Source: [[11-LO03g-Virtual-Network-Security]]

> [!question]- 0746 — Front: Port security: two limitations/conditions the courseware states.
> It also protects against DHCP starvation attacks, and it works only for access ports - not for trunk ports. _(Mod 11 p60)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0747 — Front: How does 802.1X port-based authentication work once configured?
> The AAA server explicitly installs packet filtering rules based on dynamically learned information about users and MAC addresses. _(Mod 11 p60)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0748 — Front: What makes VLAN hopping possible, per the courseware?
> The ports of some switches automatically turn into trunks when they receive DTP frames. _(Mod 11 p61)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0749 — Front: Match the STP countermeasure to the problem: BPDU Filter vs Loop Guard and UDLD.
> BPDU Filter disables STP on selected ports by stopping BPDU send/receive; Loop Guard and UDLD prevent bridging loops caused by unidirectional links. _(Mod 11 p61)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0750 — Front: Two countermeasures against double tagging / native-VLAN abuse.
> Disable trunking on non-trunk ports and disable DTP on ports that may become trunks; never send user traffic on the native VLAN. _(Mod 11 p60–p61)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0751 — Front: ARPWatch: what does it do and what is the caveat on static ARP tables?
> It tracks IP/MAC pairing and checks forwarded ARP packets for identity correctness. Static entries only stop an adversary ARP response if the table holds correct MAC/IP pairs. _(Mod 11 p60–p61)_
> Source: [[11-LO03h-VLAN-Security]]

> [!question]- 0752 — SDN definition — control plane vs forwarding
> Network virtualization approach that centralizes the network controller by separating the network's control functions from its packet forwarding functions
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0753 — Three SDN architecture layers
> SDN Application layer · SDN Controller · SDN Networking Devices
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0754 — SDN conceptual components (6)
> Data Plane · Control Plane · Application Plane · Northbound API · Southbound API · OpenFlow
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0755 — Which SDN benefit delivers voice-over-IP / multimedia QoS?
> Implements quality of service (QoS) for voice over IP and multimedia transmissions, by controlling data traffic
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0756 — SDN vs traditional control architecture
> Traditional = distributed control architecture with only low-level awareness of network state. SDN = logically centralized network topologies enabling intelligent control and management of network resources
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0757 — SDN "Openness" benefit — which application classes do the open APIs support?
> OSS/BSS, SaaS, cloud orchestration, and business-related applications
> Source: [[11-LO04a-SDN-Concepts-and-Benefits]]

> [!question]- 0758 — SDN data plane — the three major attacks
> Device Attack (SDN switch software/hardware vulns: firmware, TCAM) · Protocol Attack (network protocol vulns of the forwarding device) · Side Channel Attack (deduce forwarding policy from performance metrics)
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0759 — SDN control plane — the three major attacks
> Manipulation Attack (controller's understanding of the data plane) · Availability Attack (e.g. numerous unauthenticated packet-in messages) · Software Hack (commodity server; e.g. altering a system variable like time)
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0760 — SDN southbound API — the three major attack types
> Interception Attacks (modify exchanged messages) · Eavesdropping Attacks (info between control and data plane) · Availability Attacks (numerous requests fail network policy implementation)
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0761 — Why is a compromised northbound API worse than a compromised southbound API?
> The data exchanged between application plane and control plane affects network policies, so impact is potentially higher; also OpenFlow standardises the southbound API whereas the northbound API has no standard
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0762 — SDN application plane — policy attacks
> Storage Attack · Control Message Attack · Resource Attack · Access Control Attacks
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0763 — SDN security limitation per layer (p67 figure)
> Data Plane: insecure implementation of the management application. Control Plane: potential for compromise of the control of network flow. Application Plane: no proper authentication mechanism for the application to access the control plane
> Source: [[11-LO04b-SDN-Vulnerabilities-and-Attacks]]

> [!question]- 0764 — Data plane — which protocol versions replace the insecure ones?
> SNMPv3 instead of SNMPv2c; secured shell (SSH) instead of telnet; TLS 1.2 (or UDP/DTLS) between network device agent and controller
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0765 — Data plane — anti-replay and tunnel options
> Use protocols within TLS sessions · use shared secret passwords or use nonce to avoid replay attacks · use passwords and shared-secrets to authenticate tunnel endpoints and secure tunneled traffic with the DCI protocol in use
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0766 — Controller layer — the five measures
> Secure + authenticated administrator access · RBAC policies · logging and audit trails · HA controller architecture if DoS risk exists · avoid SDN systems with redundant controllers
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0767 — Which two techniques protect the tunnel / control path?
> Authorize tunnel endpoints and protect tunneled traffic using data center interconnect (DCI) protocols; separate control protocol traffic from primary data flows through an out-of-band (OOB) network
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0768 — FlowChecker — what does it do?
> Validates flows in network device tables against controller policy, identifying malicious traffic and discrepancies caused by an attack
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0769 — Why avoid SDN systems with redundant controllers?
> It may enable an attacker to cause DoS in all the controllers in the SDN system, while leaving the attacker undetected
> Source: [[11-LO04c-SDN-Security-Measures]]

> [!question]- 0770 — Courseware definition of NFV
> A network virtualization approach that **decouples network functions from proprietary hardware appliances** so they run as software on standardized hardware / in virtual resources. Decoupled functions named: firewalls, traffic control, virtual routing. Benefit: minimizes OPEX and CAPEX, enables easy deployment of new services.
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0771 — Three principal elements of the NFV architecture
> **NFVI** (infrastructure) · **VNFs** (virtualized network functions) · **NFV MANO** (management and orchestration).
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0772 — Three subparts of NFVI
> **Hardware resources** (network devices, servers, storage) · **Virtualization layer** (contains the hypervisor) · **Virtual resources** (virtual networks, virtual storages, virtual servers).
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0773 — EMS: what does it manage and over what kind of interface?
> Accounting, configuration, performance and security management of a VNF, over a **proprietary interface**; a single EMS can manage **multiple VNFs**.
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0774 — MANO's three components and their jobs
> **VIM** — control/manage communication from the VNF to computing, storage and network resources plus virtualization · **VNF Manager** — life-cycle actions: updates, query, installation, termination, scale-up/down · **Orchestrator** — controls orchestration, manages software resources and NFV infrastructure.
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0775 — How is a VNF deployed onto VMs, and how does MANO reach the operator's OSS/BSS?
> A VNF can run on **multiple VMs** (one function per VM) or **entirely on a single VM**. MANO combines with the decoupled **OSS/BSS** using **standard interfaces**.
> Source: [[11-LO05a-NFV-Concepts-and-Components]]

> [!question]- 0776 — NFVI: list its vulnerabilities and its attack types
> Vulnerabilities: **shared resources · insecure interfaces · improper control and monitoring · design flaws · improper security enforcements**. Attacks: **conventional (DoS/DDoS) · manipulation of VM OS · data destruction · hypervisor-level attacks · hardware attacks**.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0777 — MANO: what does the adversary do, and what are the MANO vulnerabilities and attacks?
> Eavesdrops or modifies communications **inside MANO** and **between NFVI and MANO**. Vulnerabilities: inconsistent orchestration and management, insecure interfaces, data theft, compromised policies, isolation. Attacks: conventional, orchestration and control plane — targeting the **orchestrator or VNF manager**.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0778 — Why can a VNF be a source of attack, and what are its vulnerabilities?
> It is a **vendor-provided software component** — it can carry software vulnerabilities or **may even be malware designed to execute an attack**. Vulnerabilities: software crashes, software design flaws, software bugs. At-risk: shared resources, third party networks, other tenants on the server.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0779 — What can malicious NaaS providers do, and how is it mitigated?
> **DoS attacks and extraction of secret information** (RFA / resource consumption attacks). The **hypervisor** must detect **excessive resource consumption** and **malicious virtual networks**.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0780 — Side-channel example and mitigation
> An attacker VM **extracts a private ElGamal decryption key** from a **co-resident victim VM running GnuPG**. Mitigation: **hide access management from the VNFs**.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0781 — Mitigation for a compromised live migration
> Use a **virtual trusted platform module (vTPM)** that **uses the TLS protocol** to provide confidentiality and authentication.
> Source: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]]

> [!question]- 0782 — NFV infrastructure security by domain
> **Hypervisor** — authentication controlled/managed by the VMs (prevents unauthorized access, data leaks) · **Compute** — encrypt data, accessible only by the VNFs sharing the resources · **Network** — TLS, IPSec, SSH.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0783 — MANO: how should the security mechanisms be delivered, and where are they deployed?
> **Automated and agile** for all NFV MANO functions, enabling **quick deployment at different security policy enforcement points (PEPs)**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0784 — Why is controller availability a MANO priority?
> The controller is the **centralized decision point**; if compromised it causes a **wide network impact**, so its access must be **stringently monitored and controlled**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0785 — Orchestrator attack: what does the adversary do and what mitigates it?
> It **instantiates a modified VNF**, breaking **access privileges and VNF isolation**. Mitigations: **predefine user authentication, user privilege control, network configuration**; **security monitoring system to detect and separate the defective VNF**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0786 — What is sVirt, and which two tools harden the Linux kernel?
> **sVirt** = a **new form of SELinux** that **separates VM processes and data files** and safeguards **Linux-based hypervisors**. Tools: **`hidepid`** and **`GRSecurity`**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0787 — NFV best practice: TPM, launch control policy, security zoning
> Use a **TPM as a hardware basis of trust**; its **launch control policy (LCP)** requires **validation of platform measurements**. Zoning: **separate VM from management traffic**, group same-function VMs into **isolated zones**, protect each zone with **access control policies and firewalls such as a DMZ**.
> Source: [[11-LO05c-NFV-Security-Measures]]

> [!question]- 0788 — OS virtualization (Module 11 LO06) — what is replicated, and what are the instances called?
> The **host operating system's kernel is virtually replicated in multiple instances of isolated user space**, called **containers**, **software containers**, or **virtualization engines** — each instance gets (virtualized) OS functionality.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0789 — CaaS — what is it, and what can a subscriber build with it?
> Services that enable the **deployment of containers and container management through orchestrators**. Subscribers can develop **rich, scalable containerized applications through the cloud or on-site data centers**.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0790 — Container engine vs container orchestration — define each.
> **Container engine** = managed environment for deploying containerized applications; creates, adds, and removes containers. **Container orchestration** = **automated process of managing the lifecycles of software containers and their dynamic environment**.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0791 — Orchestrators named by the courseware — which are open source, which is commercial?
> **Open source:** Kubernetes, Docker Swarm. **Commercial:** **OpenShift by Red Hat**.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0792 — OS containers vs application containers — definition and examples.
> **OS containers** = virtual environments **sharing the kernel of the host**; run multiple services/processes; install libraries, databases. Examples: LXC, OpenVZ, Linux Vserver, BSD Jails, Solaris Zones. **Application containers** = run a **single application/service**, layered file system, built on OS container tech. Examples: Docker, Rocket.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0793 — Container technology architecture — the five tiers in order.
> **Developer** creates images → **testing/accreditation systems** validate, verify, sign → **registry** stores and distributes images on request from an orchestrator → **orchestrator** converts images to containers and deploys to hosts → **host** runs and stops containers on the orchestrator's direction.
> Source: [[11-LO06a-Container-Concepts-and-CaaS]]

> [!question]- 0794 — Container vs virtual machine — the four differentiators that are stated consistently.
> **Weight** lightweight vs heavyweight · **Virtualization** OS-level vs hardware-level · **Memory** less vs more · **Start-up** milliseconds vs minutes. Plus: container **shares the host OS**, VM **has its own OS**.
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0795 — Table 11.2 (p93) — what security/isolation does the *table* assign to a container and to a VM?
> Container = **process-level isolation (less secure)**. VM = **fully isolated (more secure)**. (Note: the figure on the same page states the reverse — the courseware is self-contradictory here.)
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0796 — Container vs virtual machine — start-up time and memory footprint.
> Container: start-up in **milliseconds**, **requires less memory space**. Virtual machine: start-up in **minutes**, **requires more memory space**.
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0797 — Which products does the courseware give as container and VM examples (p93)?
> Containers: **LXC, LXD, CGManager, Docker**. Virtual machines: **VMware, Hyper-V, vSphere, Virtual Box** (Table 11.2 lists the same four).
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0798 — Container stack, bottom to top (Fig. p93).
> **Infrastructure > Host Operating System > Container Engine (Docker) > Containers > Bins/Libs** — note there is no Guest OS layer; the VM stack inserts **Virtual Machines > Guest OS**.
> Source: [[11-LO06b-Containers-vs-Virtual-Machines]]

> [!question]- 0799 — Docker client ↔ daemon — how do they talk, and where can each run?
> The client interacts with the daemon using the **REST API through Unix sockets or a network interface**. Client and daemon can run on the same system, or the client can connect to a **remote** Docker daemon.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0800 — CNM — what are the three objects the courseware itemizes, and what is each for?
> **Sandbox** = the container's network stack (routing table, interfaces, DNS; multiple endpoints). **Endpoint** = joins a sandbox to a network and abstracts the actual connection from the application. **Network** = a collection of endpoints with connectivity between them.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0801 — Docker native network drivers — list them and the host-bridge one.
> **Host, Bridge, Overlay, MACVLAN, None**. The **bridge** driver creates a **Linux bridge on the host, managed by the Docker**.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0802 — What do the Host, Overlay, MACVLAN and None drivers do (p97)?
> **Host** = container uses the host networking stack · **Overlay** = container-to-container communication over the physical network infrastructure · **MACVLAN** = connection between container interfaces and the parent host interface (or sub-interfaces) · **None** = container implements its own networking stack, isolated from the host networking stack.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0803 — CNM drivers — the two types, and who writes each.
> **Native network drivers** are **provided by Docker** and used through **Docker network commands**; **remote network drivers** are **created by the community and vendors**. Multiple drivers can coexist on an engine/cluster, but each Docker network is represented by **a single driver**.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0804 — What do IPAM drivers do, and how can an IP be set manually (p97)?
> IPAM drivers provide **default subnets or IP addressing to the network and the endpoints**. A user can assign an IP address manually through the **network, container, and service create commands**.
> Source: [[11-LO06c-Docker-Network-Drivers]]

> [!question]- 0805 — Container security challenges — how much shorter is a container's lifespan than a VM's, and why does that matter?
> On average a container's lifespan is **four times less** than a virtual machine's — it is created instantly, runs briefly, is stopped and removed. This **ephemerality lets an attacker execute an attack and disappear quickly**.
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0806 — Name the three container challenges that create network exposure.
> **Network-based attacks** (a jeopardized container, especially on **outbound networks with unrestricted raw sockets**), **bypassing / lack of isolation** (compromising one container gives access to another on the same host), and **unbounded network access from containers** (in the default state containers reach other containers and the host OS over the network).
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0807 — Image threats — list the five.
> **Image vulnerabilities** (static archive, missing updates) · **configuration defects** (runs with more privilege than required → privilege escalation) · **embedded malware** (same privileges as the rest of the image) · **embedded clear text secrets** (image can be parsed to extract them) · **use of untrusted images** (malware, data leak, vulnerable components).
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0808 — Container risks — the two that involve the runtime itself.
> **Vulnerabilities within the runtime software** → attacker compromises the runtime and can then attack other containers and monitor container-to-container communication. **Insecure container runtime configurations** → too many configurable options; improper settings lower the security of the system.
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0809 — Orchestrator risks — why is mixing workload sensitivity levels dangerous?
> The orchestrator optimizes **workload density** and by default places **different-sensitivity workloads on the same host** — e.g. a public web server next to a container processing financial data. The sensitive container **can then be easily compromised**.
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0810 — Host OS risks — why is the shared kernel a risk if the container OS has a smaller attack surface?
> Because a container has **only software-level isolation of resources**, and **usage of a shared kernel increases the inter-object attack surface** — so a host OS component vulnerability or a shared-kernel flaw hits **every container on that host**.
> Source: [[11-LO06d-Container-Security-Challenges-and-Risks]]

> [!question]- 0811 — Docker — name the four security threats and what each is.
> **Escaping** = escape the container and gain **root on the host server**, then reach other machines on the local network. **Cross-container attacks** = use a compromised container to attack other containers on the same host or local network. **Inner-container attacks** = unauthorized access to a **single** container. **Docker registry attacks** = **image forgery** (tamper with the image) and **replay attack** (provide outdated content).
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0812 — List the five factors that may facilitate container breakouts (escaping).
> **Insecure defaults and weak configuration** · **information disclosure** · **weak network defaults** · **working with the root user (UID 0)** · **mounting host directories inside containers**.
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0813 — Kubernetes data exfiltration from a pod — which two techniques does the courseware name?
> **A reverse shell in a pod connecting to a command/control server**, and **network tunneling for hiding sensitive information**.
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0814 — Compromised container — which malicious processes may it run, and what enables it?
> **Cryptomining, network scanning, and port scanning** — a container normally runs a well-defined set of processes, so extra processes are the tell. Reached via **application misconfiguration** → access the container → hunt for weaknesses in the **network, process controls, or file system**.
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0815 — How is a Kubernetes worker node compromised, and what does it give the attacker (p110)?
> Through vulnerabilities such as the **dirty cow Linux kernel vulnerability**, which enables **user privilege escalation to root** — taking the whole host running the containers. Vulnerable components listed: management server, UI/API services, etcd, kubelets, compromised nodes/pods/accounts, exposed dashboard.
> Source: [[11-LO06e-Container-Attacks]]

> [!question]- 0816 — What is Kubernetes, and who developed it?
> An open-source, portable, extensible **orchestration platform developed by Google** for managing containerized applications and microservices. It provides a resilient framework to manage distributed containers, generate deployment patterns, and perform failover and redundancy.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0817 — Which component is the Kubernetes backing store, and what happens when a pod instance dies?
> **etcd.** It stores cluster data such as "run three instances of this pod"; that stored data determines how many instances are running, and if an instance is not working Kubernetes creates an additional instance of the same pod.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0818 — What does kube-scheduler do?
> Monitors newly created pods that have **no assigned node** and assigns each of them a node to run on.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0819 — Name the five control-plane components of a Kubernetes cluster.
> kube-apiserver · etcd · kube-scheduler · kube-controller-manager · cloud-controller-manager
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0820 — What are the three services on a Kubernetes node, and what does each do?
> **kubelet** — node agent ensuring the containers in a pod's PodSpec are running and healthy. **kube-proxy** — network proxy running and maintaining network rules on each node. **Container runtime** — software that downloads images and runs the containers (Docker, CRI-O, CRI).
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0821 — How do you stop cloud-controller-manager from running the cloud-provider controller loops?
> Set the `-cloud-provider` flag to `external`. The controllers with cloud-provider dependencies are the node, route, service and volume controllers.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0822 — Which Kubernetes storage backends does the courseware list under storage orchestration?
> Local storage, public cloud providers (**AWS or GCP**), or a network storage system.
> Source: [[11-LO06f-Kubernetes-Cluster-Architecture]]

> [!question]- 0823 — Container hardening: which two measures use segmentation and firewall technology, and what do they prevent?
> Limit container communications to defined segments - prevents unauthorized connections; prevent unauthorized network connections with network firewall technology - protects running containers. _(Mod 11 p112)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0824 — Container hardening: what does "alerts based on security baseline" mean per the courseware?
> Create a runtime security policy for the prompting of alerts and remedies when suspicious activity is observed. Audit container activity separately, from operational logs, configuration data and process documents. _(Mod 11 p112)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0825 — Two hardening items that reduce the attack surface directly.
> Disable unused OS capabilities - reduces vectors of attack to a significant extent; enforce fine-grained access control for granting and managing permissions. _(Mod 11 p112)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0826 — Container image security: what does Docker content trust (DCT) do?
> It lets image publishers (individuals or organizations) sign the image and assure consumers the image is authentic; sign the tagged version with default Docker options so Docker image integrity is implemented. _(Mod 11 p113)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0827 — Runtime security: why keep only a few running processes and mount read-only?
> Many processes complicate manage/troubleshoot. Read-only mount ensures writing prevention when only reading is required, makes the container filesystem immutable and reduces unauthorized change or tampering with critical files at runtime. _(Mod 11 p115–p116)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0828 — Runtime security: list the boot trust chain examples and the privilege-grant rule.
> Create a trust chain based on hardware: Intel TXT, Bootloader, Initrd, etc. Limit privileges to those required - provide fine-grained privileges by granting specific capabilities instead. _(Mod 11 p116)_
> Source: [[11-LO07a-Container-Security-Measures]]

> [!question]- 0829 — Which three container secrets does the courseware name as needing protection?
> Passwords, access tokens, and API keys - they must be secured to prevent them from being accessed by unauthorized users with malicious intent. _(Mod 11 p114)_
> Source: [[11-LO07b-Container-Secrets-Management]]

> [!question]- 0830 — Container secrets: give the full handling chain from transfer to revocation.
> Transfer through a secure channel, encrypt and decrypt with the container's private key, store in a secret store created and managed with third-party credential-management tools, rotate on a regular basis, revoke immediately if exposed - and log all secret operations. _(Mod 11 p114)_
> Source: [[11-LO07b-Container-Secrets-Management]]

> [!question]- 0831 — Two placement rules for secrets: where must they never live?
> Not in environment variables, and not inside the container image (nor in the container file / Dockerfile). _(Mod 11 p114)_
> Source: [[11-LO07b-Container-Secrets-Management]]

> [!question]- 0832 — One secrets-management responsibility the courseware assigns to the application itself.
> Each application must assume responsibility for authentication and authorization. _(Mod 11 p114)_
> Source: [[11-LO07b-Container-Secrets-Management]]

> [!question]- 0833 — NIST's six container recommendations, condensed.
> Tailor operational culture and technical processes; use container-specific host OSes instead of general-purpose; group only same-purpose, same-sensitivity, same-threat-posture containers per host kernel; adopt container-specific vulnerability management for images; consider hardware-based countermeasures for trusted computing; use container-aware runtime defense tools. _(Mod 11 p117)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0834 — The closing best-practice list: four items about the container's own environment and permissions.
> Control root access; check the container runtime; lock down the operating system; embrace isolation and least privilege - plus centrally managed access controls. _(Mod 11 p118)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0835 — Hardening bullet: list the six concrete configuration rules.
> Configure against benchmarks, adopt control features for host/daemon/kernel, avoid privileged mode execution, avoid noisy neighbors, limit resources such as CPU/memory, permit network traffic only on default bridge. _(Mod 11 p118)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0836 — Health-check and sprawl items in the best-practice prose.
> Ensure appropriate life cycle management, delete drifted containers, control container sprawl, adopt continuous monitoring of container traffic, ensure service log management. _(Mod 11 p118)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0837 — Two process/file/device restrictions named in the best-practice prose.
> Avoid using the AUFS driver, and enable user namespace - with privileges based on roles, RBAC, and authentication/authorization. _(Mod 11 p118)_
> Source: [[11-LO07c-Container-Security-Best-Practices]]

> [!question]- 0838 — Docker ships five security features - name them and say what capabilities gives you.
> Cgroups, LSMs (AppArmor/SELinux via runc), capabilities, seccomp, userns. Capabilities split root privileges on a thread basis; Docker allows only 14 of the 37 Linux capability groups by default, and more can be added or removed. _(Mod 11 p120)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0839 — Seccomp and userns: what does each control?
> Seccomp gives fine-grained per-syscall control - the default profile limits many syscalls and specific syscalls can be blocked from being used by container binaries. Userns remaps root to unprivileged IDs on the host, isolating the process and limiting access to system resources; Docker supports global uid/gid mapping. _(Mod 11 p120)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0840 — Docker content trust: what does it verify, what is its default state, and how is it enabled?
> It verifies the authenticity, integrity and publication date of images in the Docker Hub registry; it is disabled by default. Enable with sudo export DOCKER_CONTENT_TRUST=1, then only signed images are retrieved by docker pull. _(Mod 11 p121)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0841 — Resource limits: why does an uncapped container endanger the host, and what two limit types does Docker impose?
> A container can consume as much as the host scheduler provides; the kernel may throw an OOME and kill other processes, potentially collapsing the system. Docker imposes hard memory limits (only a set amount of system memory) or soft memory limits (unconstrained use under conditions such as overall low memory usage). _(Mod 11 p122)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0842 — Which container resource is limited with which stated option?
> CPU - add the --cpus=2 option to the run command to limit a container to 2 CPUs. The 1 GB memory limit is the other example, but its option string is not legible in the courseware figure. _(Mod 11 p122)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0843 — Third-party tool selection: what is the risk and how is an official image recognized?
> Containers pulled from public repositories may have been created insecurely and may contain malicious or corrupt files, so pull only from reliable sources such as the Docker Hub. In the search results the first entry is the official image - that flag distinguishes official from third-party sources and tools. _(Mod 11 p123)_
> Source: [[11-LO08a-Docker-Security-Measures]]

> [!question]- 0844 — Docker Bench Security: what is it and what does it check?
> A script that enables checking of host configuration, Docker daemon configuration, Docker daemon configuration files, container images and build files, and container runtime. Referred to on p.118 as the Docker bench audit tool for facilitating configuration best practices. _(Mod 11 p124, p118)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0845 — Name the two tools whose Kubernetes integrations are structural rather than just monitoring.
> Anchore integrates with Kubernetes using admission controllers, ensuring only images that meet the organization's policies are deployed. StackRox collects system-level events - process execution, network connections and flows, privilege escalation, files launched within each container in Kubernetes environments. _(Mod 11 p125, p126)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0846 — StackRox: what does it protect, and which threats do its pre-defined policies detect?
> Cloud-native apps across the full life cycle including build, deploy and runtime. Pre-defined policies detect cryptocurrency mining, privilege escalation and various exploits. _(Mod 11 p126)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0847 — Which tool's stated function is a true layer 7 container firewall, and what does it block?
> NeuVector - end-to-end Kubernetes platform with a true layer 7 container firewall; detects and blocks suspicious processes and file system activity to prevent exploits and breakouts, plus automated segmentation, DPI, and detection for DDoS, DNS, SQL injection and DLP breaches. _(Mod 11 p125)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0848 — Three tools and their one-line identity, from distinct layers of the pipeline.
> Anchore - image analysis in the build pipeline, creates software container bills of materials, Kubernetes admission controllers. CloudPassage Halo - cloud/container/serverless security posture and continuous CIS-benchmark compliance. Capsule8 - attack detection and response for Linux environments, containerized, virtualized or bare-metal, on-premises or cloud. _(Mod 11 p125)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0849 — Which tools work by blocking, whitelisting or real-time intervention, and what is each mechanism?
> Aqua - least-privilege whitelisting to detect and prevent anomalous behavior, privilege escalation or code injection. Twistlock - real-time intervention, blocking and prevention for in-process runtime attacks, plus granular access control. Tenable.io - vulnerability assessment, malware detection and policy enforcement across development to operation. _(Mod 11 p124–p125)_
> Source: [[11-LO08b-Docker-Security-Tools]]

> [!question]- 0850 — Why favor minimal and alpine base images?
> Choose images with fewer OS libraries and tools - this decreases risk and reduces the attack surface area of the container. Favor alpine-based images over full-blown system OS images. _(Mod 11 p127–p128)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0851 — COPY versus ADD: what does the courseware say, and how is it worded twice?
> ADD is vulnerable to MITM attacks because arbitrary URLs specified could be malicious data sources, and it implicitly unpacks local archives, which could result in path traversal or Zip Slip vulnerabilities. Use COPY instead of ADD - use COPY unless ADD is specifically required. _(Mod 11 p127–p128)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0852 — The three measures to stop secrets leaking into images during build, and the version constraint.
> Use multi-stage builds; use the Docker secrets feature to mount sensitive files without caching them - supported only from Docker 18.04; use a .dockerignore file to avoid a hazardous COPY instruction that may pull sensitive files from the build context. _(Mod 11 p128)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0853 — Fixed tags for immutability: what goes wrong, and what are the two fixes?
> Image owners can push new versions to the same tags, giving inconsistent images during builds and making it hard to track whether a vulnerability is fixed. Fix with a verbose tag carrying version and OS, for example node:8-alpine, plus an image hash to pin the exact content. _(Mod 11 p128)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0854 — Least privileged policy on an image, and the multi-stage build payoff.
> Create the dedicated user and group on the image with minimal permissions to run the application, and use the same user to run the process - the Node.js image has a built-in generic node user. Multi-stage builds create small, clean images with minimized attack surface and vulnerabilities. _(Mod 11 p127, p129)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0855 — Which two tools does the courseware name for image scanning and Dockerfile linting, and what is each for?
> Snyk - scan Docker images and open-source application libraries for vulnerabilities as part of CI, and monitor for newly disclosed ones. hadolint - a static code analyzer linter that detects and alerts on issues in a Dockerfile and enforces Dockerfile best practices. _(Mod 11 p127, p129)_
> Source: [[11-LO08c-Docker-Security-Best-Practices]]

> [!question]- 0856 — Kubernetes RBAC: why is privilege escalation blocked even when the RBAC authorizer is not in use?
> Because the RBAC API enforces it at the API level - editing roles or role bindings is blocked regardless of the active authorizer. _(Mod 11 p134)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0857 — Condition for creating or updating a role in Kubernetes RBAC.
> The user must already hold all the permissions contained in the role AND at the same scope - cluster-wide for a ClusterRole, within the same namespace for a Role. _(Mod 11 p134)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0858 — The three parts of Kubernetes RBAC permissions.
> Role or ClusterRole (rules = resources + verbs; Role = namespace, ClusterRole = cluster) · Subject (User, Group, ServiceAccount) · RoleBinding or ClusterRoleBinding joining them (namespace-scoped vs cluster-wide). _(Mod 11 p135)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0859 — How to disable ABAC on the API server.
> Kubernetes' ABAC is swapped with RBAC since release 1.6. Use --authorization-mode=RBAC, or in GKE --no-enable-legacy-authorization. _(Mod 11 p135)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0860 — PodSecurityPolicy fields that take a list of Linux capabilities, and the naming rule.
> AllowedCapabilities, RequiredDropCapabilities, DefaultAddCapabilities - capability name in ALL CAPS without the CAP_ prefix. _(Mod 11 p133)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0861 — Kubernetes container image guidelines for a small image, and the :latest tag.
> Minimal base image, few components restrict attack vectors, check for vulnerabilities regularly (BusyBox, Alpine given as examples); do not depend on :latest - use the specific version number as the tag and update it. _(Mod 11 p131)_
> Source: [[11-LO09a-Kubernetes-RBAC-and-API-Server]]

> [!question]- 0862 — Kubernetes audit logs: what do they record?
> A record of the activities of users, administrators, or system components that have affected the system. Audit logging customizes API logging at the metadata level and at the payload (request and response), set per organizational policy. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0863 — What is stored in the audit logs for read requests (get, list, watch) versus for Secret and ConfigMap requests?
> Read requests: the request object is exported. Secret and ConfigMap: only the metadata is saved. All remaining requests are exported. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0864 — List the seven questions Kubernetes audit logs must let cluster administrators answer.
> What happened · When did it happen · Who initiated it · What did it happen on · Where was it observed · Where was it initiated · Where was it going. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0865 — Minimal audit policy file: what are the apiVersion, kind and rule level?
> apiVersion audit.k8s.io/v1, kind Policy, rules with a single entry - level: Metadata (Figure 11.36) - logs all requests at the Metadata level. _(Mod 11 p140)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0866 — Which of these is NOT stated in the Kubernetes audit-policy guidance of Module 11?
> Audit-log rotation, retention and backends - the slice only gives the minimal Metadata-level policy file. See unresolved. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0867 — Audit logging in Kubernetes customizes API logging at which two levels?
> At the metadata level and at the payload (for example, request and response); the levels can be set as per the policy of the organization. _(Mod 11 p139)_
> Source: [[11-LO09b-Kubernetes-Audit-Policy]]

> [!question]- 0868 — Kubernetes NetworkPolicy: what is the default state, and what changes when a policy selects a pod?
> By default all pods can talk to all other pods - pods are non-isolated. If a NetworkPolicy in the namespace selects a pod, that pod rejects any communication not allowed by the policy. _(Mod 11 p141, p142)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0869 — Are Kubernetes NetworkPolicy resources additive or overriding?
> Additive - if multiple policies select a pod, the pod is isolated based on the union of the policies' rules. _(Mod 11 p141)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0870 — restrict-root.yaml: what does it block, and how is it activated?
> privileged: false plus runAsUser rule mustRunAsNonRoot, so containers cannot run privileged or as root. Saved as restrict-root.yaml and activated with kubectl create -f restrict-root.yaml. _(Mod 11 p146)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0871 — How do you restrict the volume/storage types a container may use?
> Specify the allowed volume types in the volumes key of a pod security policy (for example only nfs) and install the policy - this reduces costs or avoids accessing information. _(Mod 11 p146)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0872 — Which Kubernetes secret encryption provider is recommended for enhanced security, and why?
> kms - envelope encryption with DEKs (AES-CBC/PKCS#7) wrapped by KEKs per the KMS configuration, simplifying key rotation; EncryptionConfig alone only gives moderate security for stored keys, and the KMS provider must be configured. _(Mod 11 p150)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0873 — How do you verify that secrets are encrypted at rest in etcd, and what proves it?
> ETCDCTL_API=3 etcdctl get /registry/secrets/default/secret1 --hexdump -C, then check the stored secret is prefixed with k8s:enc:aescbc:v1:, and that kubectl describe secret secret1 -n default decrypts it correctly. Configuration is enabled with the kube-apiserver --encryption-provider-config argument. _(Mod 11 p149, p151)_
> Source: [[11-LO09c-Kubernetes-Pod-Security-Policy]]

> [!question]- 0874 — Istio: source and what it does for Kubernetes security.
> Source www.istio.io. It helps connect, secure, control and observe services, creating a service mesh for service-to-service communication including routing, authentication and encryption, and encrypting pod-to-pod communication with mutual TLS. _(Mod 11 p152)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

> [!question]- 0875 — Grafeas: source and scope.
> Source www.github.com. An open source initiative defining a best practice for auditing and governing the modern software supply chain, with an API spec for metadata about software resources - container images, virtual machine images, JAR files, scripts. _(Mod 11 p152)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

> [!question]- 0876 — What does the CIS Kubernetes benchmark give you, and what is the module's example check?
> Instructions to audit a configuration against the recommendation and to remediate setups that fail the audit test. Example: basic authentication uses plaintext credentials, so ensure --basic-auth-file is not set, checked with ps -ef | grep kube-apiserver on the master node. _(Mod 11 p153)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

> [!question]- 0877 — Which tools are named for updating a manually managed Kubernetes cluster, and what must also be updated?
> kubeadm and kops. Update both the control plane components (API server, scheduler) and the worker nodes, and check that plugins, add-ons and extensions are compatible with the new version. _(Mod 11 p154)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

> [!question]- 0878 — Before and after updating a Kubernetes cluster, what do the best practices require?
> Before: reliable backup of the entire cluster - configurations, applications, data. After: run container tests, thoroughly test all applications and services, and update the documentation with the changes. _(Mod 11 p154, p155)_
> Source: [[11-LO09d-Kubernetes-Security-Tools-and-Best-Practices]]

### Module 12 (293 items)

> [!question]- 0879 — Courseware definition of cloud computing — the three qualifiers
> On-demand delivery of IT capabilities where the IT infrastructure and applications are provided to subscribers as a metered service over a network
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0880 — The 12 characteristics of cloud computing, in courseware order
> On-demand self service · Distributed storage · Broad network access · Rapid elasticity · Automated management · Resource pooling · Measured service · Virtualization technology · Multi-tenancy · Resilient computing · Flexible pricing models · Sustainability
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0881 — Measured service — what exactly is metered?
> Pay-per-use — monthly subscription or per usage (storage levels, processing power, bandwidth); the CSP monitors, controls, reports and charges with complete transparency
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0882 — Limitations of cloud computing (courseware list)
> Limited control and flexibility · Prone to outage and other technical issues · Security, privacy and compliance issues · Contracts and lock-ins · Dependence on network connections
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0883 — Cloud computing benefits — the four groups and their item counts
> Economic 8 · Operational 7 · Staffing 7 · Security 8 = 30 items
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0884 — Which benefits group carries "Standardized open interface for managed security services (MSS)"?
> Security
> Source: [[12-LO01a-Cloud-Computing-Fundamentals]]

> [!question]- 0885 — IaaS — what does the subscriber get, and who runs the underlying infrastructure?
> VMs and other abstracted hardware and OSes controlled through a service API; the CSP manages the underlying cloud-computing infrastructure, so the subscriber avoids human capital and hardware costs
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0886 — IaaS — the two disadvantages the courseware lists
> Software security is at high risk (third-party providers are more prone to attacks) · Performance issues and slow connection speeds
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0887 — PaaS — three disadvantages
> Vendor lock-in · Data privacy · Integration with other system applications
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0888 — SaaS — three disadvantages
> Security and latency issues · Total dependency on the internet · Switching between SaaS vendors is difficult
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0889 — SaaS — how do providers charge for the service?
> Pay-per-use basis via subscription, advertising, or sharing among multiple users
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0890 — Why must subscriber and service-provider responsibilities be separated in cloud computing?
> Separation of duties prevents conflicts of interest, illegal acts, fraud, abuse and errors; helps identify security control failures (information theft, security breaches, invasion of security controls); restricts the influence held by an individual
> Source: [[12-LO01b-Cloud-Service-Delivery-Models]]

> [!question]- 0891 — Deployment-model selection is driven by which five factors?
> Where cloud computing services are hosted · Security requirements · Sharing cloud services · Ability to manage some or all cloud services · Customization capabilities
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0892 — Public cloud — disadvantages
> Security is not guaranteed · Lack of control (third-party providers are in charge) · Slow speed (relies on internet connections, data transfer rate is limited)
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0893 — Private cloud — advantages
> Enhance security (dedicated to a single organization) · More control over resources · Greater performance (inside the firewall) · Customizable hardware, network and storage · Sarbanes-Oxley, PCI DSS and HIPAA compliance data significantly easier to acquire
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0894 — Community cloud — what makes it different from a private cloud?
> Multi-tenant infrastructure shared among organizations from a specific community with common computing concerns; on-premise or off-premise; governed by the participating organizations or a third-party managed service provider
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0895 — Hybrid cloud — courseware definition and example
> Two or more clouds (private, public, community) that remain unique entities but are bound together; example — critical activities such as operational customer data on a private cloud, non-critical activities on a public cloud
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0896 — Does multi-cloud mix private and public clouds?
> No — multi-cloud is a combination of only two or more public cloud services; it does not mix public and private cloud services
> Source: [[12-LO01c-Cloud-Deployment-Models]]

> [!question]- 0897 — The five significant actors in the NIST cloud reference architecture
> Cloud consumer · Cloud provider · Cloud carrier · Cloud auditor · Cloud broker
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0898 — What does a cloud carrier do?
> Acts as an intermediary providing connectivity and transport services between the cloud service providers and cloud consumers; provides access to consumers via networks, telecommunication and other access devices
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0899 — What does a cloud auditor examine, and what does an audit verify?
> It independently examines the cloud service controls to express a corresponding opinion; audits verify adherence to standards by reviewing objective evidence
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0900 — The three service categories a cloud broker provides
> Service intermediation (improves a given function, value-added) · Service aggregation (combines multiple services into new services) · Service arbitrage (like aggregation but the services are not fixed)
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0901 — SLA in cloud computing — who specifies what?
> The consumer specifies the technical performance requirements — quality of service, security and remedies for performance failure; the CSP may also define limitations and obligations the consumer must accept
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0902 — Which actor steps out when the consumer buys directly from the CSP, and what stack does Figure 12.1 show?
> Cloud broker; Service Layer (SaaS/PaaS/IaaS) → Resource Abstraction and Control Layer → Physical Resource Layer → Hardware Facility, with Cloud Service Management, Business Support and Portability/Interoperability across it
> Source: [[12-LO01d-NIST-Cloud-Reference-Architecture]]

> [!question]- 0903 — Traditional security measures in the cloud — what changes and what does not
> The security protocols do not change; the security focus of the cloud consumers does
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0904 — Shared responsibility — the failure condition stated by the courseware
> If the consumers do not secure their functions, the entire cloud security model will fail
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0905 — Shared responsibility matrix — the four columns, left to right
> On-premises (for reference) · Infrastructure-as-a-service (IaaS) · Platform-as-a-service (PaaS) · Software-as-a-service (SaaS)
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0906 — Cloud service consumers are responsible for
> User security and monitoring (IAM) · information security—data (encryption and key management) · application-level security · data storage security · monitoring, logging and compliance
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0907 — Cloud service providers are responsible for
> Securing the shared infrastructure: routers · switches · load balancers · firewalls · hypervisors · storage networks · management consoles · DNS · directory services · cloud API
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0908 — IAM — why MFA is enabled and the preferred device types
> To control access to cloud service APIs; best option is a virtual MFA or a hardware device
> Source: [[12-LO02a-Cloud-Security-Shared-Responsibility]]

> [!question]- 0909 — Main challenge in cloud network security, per the courseware
> Lack of network visibility in monitoring and managing suspicious activities by the consumer
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0910 — Five data storage security techniques
> Local data encryption · Key management · Strong password management · Periodic security assessment of data security controls · Cloud data backup
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0911 — Why must organizations keep local backups of cloud data?
> Loss of data may imply financial loss as well as legal actions, so a local backup is essential to prevent possible data loss
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0912 — Two-step verification and updated patches — what do they defend against?
> They prevent hackers from attacking the systems easily
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0913 — Which network security control does each cloud use — AWS vs Azure?
> AWS: Network Access Control List (NACL) · Azure: Endpoint and NSG
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0914 — Cloud network security — what does the firewall usage guarantee?
> Isolation between multiple zones
> Source: [[12-LO02b-Cloud-Data-and-Network-Security]]

> [!question]- 0915 — Security logs — the three uses stated in the courseware
> Threat detection · Data analysis · Compliance audits
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0916 — Five questions that determine whether the right log data was captured
> Who is accessing the network? · What assets are they accessing? · From where are they accessing the asset? · When are they doing this? · Are there established permissions to allow their activity?
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0917 — Data monitoring — the two rule requirements
> Define thresholds and rules for normal activity, and alert the data owner if data activity exceeds the defined thresholds
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0918 — Where should aggregated logs be sent?
> To log analytics or a security information and event management (SIEM) system, giving a database of valuable information to access and analyze on demand
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0919 — Cloud monitoring plan — the seven essential aspects
> Identify metrics and events · Use one platform to report all data · Monitor cloud service usage and fees · Monitor user experience · Trigger rules with data · Separate and centralize data · Try failure
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0920 — Consequences of compliance failure
> Regulatory fines · Lawsuits · Cyber security incidents · Reputational damage
> Source: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

> [!question]- 0921 — Which three CSP market shares are printed on the Q2 2023 spend figure?
> AWS 30% · Microsoft Azure 26% · Others 35% (the Google Cloud slice label carries no legible percentage)
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0922 — What must be done before consuming a cloud service?
> Perform a gap analysis on the security capabilities and services provided by the cloud service providers
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0923 — Gap analysis — the three benchmark axes
> Maturity · Transparency · Compliance
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0924 — Enterprise security standard and regulatory standards named for the gap analysis
> ISO 27001 · PCI DSS · HIPAA · SOX
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0925 — CSP security maturity — the five evaluation points
> Disclosure of security policies, compliance and practices · Disclosure when mandated · Security architecture · Security automation · Governance and security responsibility
> Source: [[12-LO03a-CSP-Landscape-and-Evaluation]]

> [!question]- 0926 — The three closing questions for evaluating a CSP
> How many security tools are currently required in the organization? · What risks can the security tools reduce/address? · Rationalize the existing security vendors and tools
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0927 — When are third-party security tools required in cloud?
> For the security controls that are not provided by the CSP
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0928 — What must be checked about third-party products before choosing a provider?
> That they can be integrated with the cloud platform; then combine third-party controls with the CSP's own controls
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0929 — Approach used to review CSP tools before a technology decision
> A self-check or requirement-driven approach — review requirements and each CSP's existing tools
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0930 — Control categories the on-premise column is measured against
> Firewall and ACLS · IPS/IDS · WAF · SIEM · Log Analytics · Antimalware · PAM · DLP · Vulnerability Assessment · Email Protection · SSL Decryption · Reverse Proxy · Key Management · Encryption at rest · DDOS · MFA · Centralized logging/auditing · Load balancer · LAN/WAN · Endpoint protection · Certificate management · Container security · GRC · Monitoring · Backup and recovery
> Source: [[12-LO03b-CSP-Security-Feature-Comparison]]

> [!question]- 0931 — AWS shared responsibility — who secures what
> Customers decide the access levels they give from and to their resources; AWS secures the cloud. "In the cloud" = customer band · "of the cloud" = AWS band
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0932 — The two control types the AWS shared responsibility model uses
> Inherited Controls — inherited completely from AWS to customers (e.g. physical and environmental) · Shared Controls — applied to both the infrastructure and the customer layer with separate perspectives
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0933 — Shared Control: Patch Management split
> AWS patches and fixes flaws within the infrastructure; customers patch their guest OS and applications
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0934 — Shared Control: Configuration Management split
> AWS configures the infrastructure devices; the customer configures their guest OSes, databases, and applications
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0935 — Shared Control: Awareness and Training split
> AWS trains the AWS employees; customers train their employees
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0936 — Client-Side Data Encryption — which keys may the customer use
> Either an AWS-managed encryption key or a personal key not provided by AWS
> Source: [[12-LO04a-AWS-Shared-Responsibility-Models]]

> [!question]- 0937 — AWS IAM — the four attributes it ties together
> Who = workforce users and workloads with IAM · Can access = permissions with IAM policies · What = AWS services · Resources = within organization
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0938 — What AWS IAM Identity Center was formerly called
> AWS Single Sign-On
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0939 — IAM Identity Center — the five key features
> Workforce identities · application assignments for SAML applications (SAML 2.0) · Identity Center enabled applications · multi-account permissions · AWS access portal
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0940 — IAM Access Analyzer — the twelve resource types it generates findings for
> IAM roles · KMS keys · S3 buckets · Secrets Manager secrets · Lambda functions and layers · EBS volume snapshots · SQS queues · SNS topics · RDS DB snapshots · RDS DB cluster snapshots · ECR repositories · EFS file systems
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0941 — IAM Access Analyzer — what does policy validation produce
> Findings containing security errors, warnings, suggestions and general warnings, each with actionable recommendations; checked with more than 100 policy checks
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0942 — What Access Analyzer analyses to generate a policy
> AWS CloudTrail logs — the actions and services used by an IAM entity (user or role) within a specified date range; the generated policy can then be attached to a user or role
> Source: [[12-LO04b-AWS-IAM-Features]]

> [!question]- 0943 — Preventive guardrails — the three ways to cap what an IAM role can be granted
> Service control policies · permission boundaries · session policies
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0944 — Definition of an AWS IAM role
> An entity that you define and provide specific permissions to, allowing trusted identities such as workforce identities and applications to conduct actions in AWS — a security best practice because it gives temporary credentials that need not be rotated
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0945 — Which product gives temporary AWS access to applications running outside AWS
> IAM Roles Anywhere
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0946 — Name the five IAM role scenarios
> Federate workforce identities into AWS · access workloads within AWS · access workloads that run outside of AWS · enable cross-account access · grant access to AWS services
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0947 — Why root user access keys are not recommended
> They grant complete access to all resources for all AWS services including billing information, and the permissions associated with them cannot be reduced
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0948 — AWS password requirements
> Minimum 8 and maximum 128 characters · at least three of the four character types (uppercase, lowercase, numbers, symbols) · not identical to the AWS account name or email address
> Source: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

> [!question]- 0949 — The three stated objectives for creating individual IAM users
> 01 Do not allow a user to use the root user account — create individual user accounts instead · 02 give each IAM user a unique set of security credentials and appropriate permissions · 03 this lets you change or revoke their permissions as required
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0950 — Why create an IAM user for yourself instead of using root
> Create an IAM user, give it administrative permissions, and use it for all your work
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0951 — During user creation, which option is selected by default
> Add user to group — the new user is placed in a newly created group automatically (the example group is Training_Group)
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0952 — Which setting is optional on a new IAM user but recommended
> Require password reset — "The Require password reset is optional; however, enable this setting"
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0953 — Three stated advantages of using groups
> Create groups with similar job functions · assigning and reassigning rights to groups is easy and less time consuming · reduces accidental assignment of greater privileges to users
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0954 — Why do individual users still keep credentials when IAM groups exist
> The group policy governs access, but individual users still possess their own credentials
> Source: [[12-LO04d-AWS-IAM-Users-and-Groups]]

> [!question]- 0955 — The three phases IAM Access Analyzer drives toward least privilege
> Set fine-grained permissions · verify intended permissions · refine permissions by removing unused access
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0956 — Generating a policy from CloudTrail — what does Access Analyzer read
> AWS CloudTrail events for the chosen role, over a specified time period — choose the shortest, up to 90 days, to reduce generation time · status is reported on the role page; then View generated policy in the Permissions tab
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0957 — The five IAM access levels
> List · Read · Write · Permissions management · Tagging
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0958 — The five features of a managed policy
> Reusability · central change management · versioning and rolling back · delegating permission management · automatic updates (AWS-managed)
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0959 — Three AWS-managed policy classes with their named examples
> Full access — AmazonDynamoDBFullAccess, IAMFullAccess · Power user — AWSCodeCommitPowerUser, AWSKeyManagementServicePowerUser · Partial access — AmazonEC2ReadOnlyAccess, AmazonMobileAnalyticsWriteOnlyAccess
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0960 — The three policy summary tables
> Policy summary — services and permission summaries for the policy · Service summary — actions and permission summaries for one service · Action summary — resources and the conditions for one action
> Source: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]

> [!question]- 0961 — The elements a strong AWS password policy must contain
> Minimum length in the range 6 to 128 · at least one uppercase (A–Z) · at least one lowercase (a–z) · at least one numeric (0–9) · at least one non-alphanumeric · allow users to change their own password · enable password expiration · prevent password reuse · password expiration requires administrator reset
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0962 — The four IAM MFA methods as listed in the courseware
> FIDO security keys · Virtual authenticator apps · TOTP hardware tokens · TOTP hardware tokens for the AWS GovCloud (US) Regions
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0963 — The named TOTP hardware-token providers, by scope
> Thales — TOTP hardware tokens used exclusively with AWS accounts · Hypersecu — TOTP hardware tokens compatible with AWS GovCloud (US) Regions, used exclusively by IAM users with AWS GovCloud (US) accounts
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0964 — The two MFA response styles and how each finishes the sign-in
> Virtual/hardware MFA devices — generate a code that the user types on the sign-in screen · U2F security keys — generate a response when the device is tapped and the sign-in completes automatically
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0965 — How FIDO security keys are characterised
> FIDO-certified hardware keys from third-party providers such as Yubico; based on public key cryptography; strong, phishing-resistant authentication; a single key supports multiple root accounts and IAM users
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0966 — Assigning a virtual MFA device — the whole wizard in order
> Seed the app with Show QR code (scan it) or Show secret key (type it in) · type the OTP currently shown in MFA code 1 · wait 30 seconds for a new OTP · type the second OTP in MFA code 2 · select Assign MFA
> Source: [[12-LO04f-AWS-Password-Policy-and-MFA]]

> [!question]- 0967 — Why an IAM role is preferred over credentials on an EC2 instance
> A role is not a user or group and has no permanent credentials — IAM dynamically provides temporary credentials to the instance and they are automatically rotated; the role is set as a launch parameter and its permissions decide what the app may do
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0968 — The two policies attached to a delegation role, and the permission swap
> Permission policy — what the role's user may do on the resources (half the permissions) · Trust policy — which trusted-account members may assume the role (the other half) · assuming the role temporarily replaces the user's own permissions; they return when the user stops
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0969 — The permissions boundary, as the courseware defines it
> A more advanced feature that lets you use a managed policy to limit the maximum permissions that an identity-based policy can provide to an IAM role
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0970 — Zero-downtime key rotation — order of operations and the stale-key threshold
> Deactivate keys used more than 90 days ago, identified with Access Key Last Used · create the second access key (active by default) → update all applications and tools to use it → wait several days and check Last Used on the old key → Make inactive on the old key → confirm applications work → delete the old key
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0971 — Two trust-policy hardening options when creating a cross-account role
> Require external ID — adds a trust-policy condition that the request include the correct sts:ExternalId, any word or number agreed with the third-party administrator · Require MFA — adds a trust-policy condition that checks for an MFA sign-in
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0972 — How a service-linked role is named, and how it is marked
> The role name prefix is auto-populated and you type only the suffix; leave the suffix blank for services such as Amazon Lex that do not support custom suffixes; service-linked roles are marked with a cube-shaped icon in the IAM console
> Source: [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]]

> [!question]- 0973 — The ABAC rule and the condition keys it uses
> Define policies that use tag condition keys to grant permissions to principals based on their tags — session tags are passed when a principal assumes a role or federates a user · the access-assume-role policy string-equals iam:ResourceTag/access-project, iam:ResourceTag/access-team and iam:ResourceTag/cost-center against the same-named aws:PrincipalTag values
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0974 — The two policy variants in the ABAC walkthrough
> access-assume-role — wildcard on the role name (`access-*`) plus a tag-match Condition, so a user can assume only roles whose tags match their own · access-assume-specific-roles — no Condition; an explicit list of role ARNs the user may assume
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0975 — The ABAC secret-viewing decision rule
> Compare the role name to the secret name — if they share the same team name the access-team tags match and access is allowed; if they do not match, access is denied
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0976 — What the Condition element does in an IAM policy
> Specifies the conditions under which a policy statement is in force — allow access to resources and actions only if the request satisfies the criteria, expressed with condition operators (equal, less than, etc.) comparing condition keys and values in the policy against the request context
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0977 — The two console columns for finding stale credentials
> Console last sign-in — days since the user last signed into the console; Never = password never used, None = no password · password_last_used in the credentials report — N/A = no password, no_information = never used since tracking began
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0978 — The credential-to-purpose pruning rule
> Remove the console password for users who use the application but not the console · remove the access keys for users who only use the console
> Source: [[12-LO04h-AWS-ABAC-and-Policy-Conditions]]

> [!question]- 0979 — What the AWS log files display
> Time and date of actions · source IP for an action · actions that failed owing to inadequate permissions, among others
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0980 — The five logging services and what each is for
> Amazon CloudFront — user requests received, web and RTMP distributions · AWS CloudTrail — account activities and events, event history plus a trail for the ongoing record · AWS Config — detailed historical configuration of AWS resources · Amazon S3 — details of access requests to buckets, plus Audit Logs · Amazon CloudWatch logs — centralize logs from EC2, CloudTrail, and Route 53
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0981 — CloudTrail — data events, management events, Insights and log encryption
> Data events — resource ('data plane') operations on or within the resource itself · management events — management ('control plane') operations on resources in the account · CloudTrail Insights — identifies unusual activities · log file encryption — Amazon S3 server-side encryption (SSE) on log files delivered to S3 buckets
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0982 — The three IAM Identity Center identity sources
> Identity Center directory — the default when Identity Center is first enabled · Active Directory — AWS Managed Microsoft AD via AWS Directory Service, or a self-managed AD · External identity provider — e.g. Okta or Azure Active Directory
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0983 — The six steps to implement SSO with IAM Identity Center
> Step 1 enable IAM Identity Center (root user) · Step 2 select the identity source · Step 3 create an administrative permission set · Step 4 set up AWS account access for an administrative user · Step 5 sign in to the AWS access portal · Step 6 set up access to AWS applications
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0984 — How SSO to an EC2 Windows instance works
> AWS IAM Identity Center user portal → Management console → Fleet Manager → Instance actions → Connect with Remote Desktop → select IAM Identity Center and Connect; on first connect a new local user is created and AWS Fleet Manager uses the credentials it created to sign in — the All sessions tab then shows up to four concurrent sessions in a single view
> Source: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]

> [!question]- 0985 — The three AWS data-at-rest encryption models — who does what
> Model A — customer manages the encryption, key storage and key management · Model B — AWS provides the key storage layer, customer manages the encryption algorithm and key management · Model C — AWS provides the key storage layer, encryption algorithm and key management (transparent server-side encryption)
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0986 — In AWS data-at-rest Model B, where are the keys stored and who controls the algorithm?
> Keys are stored in the AWS environment (AWS CloudHSM) and are inaccessible to any AWS employee; the customer provides the KMI (on-premise or in Amazon EC2) and manages the encryption algorithm and key management, communicating with CloudHSM over SSL
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0987 — The three Amazon S3 server-side encryption key-management options
> SSE-S3 — Amazon S3-managed keys · SSE-KMS — AWS KMS-managed keys (CMKs in AWS Key Management Service) · SSE-C — customer-provided keys, never stored by S3
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0988 — Amazon S3 SSE-S3 as described by the courseware
> Each object is encrypted with a unique key, and that key is additionally encrypted with a master key; Amazon S3 SSE uses 256-bit AES (AES-256); a bucket policy can enforce SSE for all objects in the bucket
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0989 — Which Amazon S3 APIs support the `x-amz-server-side-encryption` request header
> PUT operations (uploading with the PUT API) · Initiate Multipart Upload (header in the initiate request for large objects) · COPY operations (source and target object)
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0990 — Amazon S3 SSE-KMS — the printed highlights
> Select a customer-managed CMK you create/manage or an AWS-managed CMK that Amazon S3 creates and manages for you · create, rotate and disable auditable customer-managed CMKs from the AWS KMS console · provides encryption of the data keys that encrypt customer data · provides encryption-related compliance requirements · the ETag in the response is not the MD5 of the object data
> Source: [[12-LO04j-AWS-Encryption-Data-at-Rest]]

> [!question]- 0991 — The two key components of the Bouncy Castle architecture, and what the rest build on
> Light-weight API and the Java Cryptography Extension (JCE) provider support cryptography; the remaining components built on the JCE provider add extra functionality (PGP support, S/MIME). Bouncy Castle supplies APIs for both Java and C#, from J2ME to JDK 1.11
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0992 — The two CloudHSM claims that give separation of duties
> AWS has administrative credentials to manage and maintain the appliance, but administrative credentials cannot access the HSM partitions; AWS monitors HSM health and network availability while users control the HSMs and the generation and use of their encryption keys
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0993 — The six AWS Certificate Manager best practices
> AWS CloudFormation · Certificate Pinning · Domain Validation · Adding or Deleting Domain Names · Opting Out of Certificate Transparency Logging · Turn on AWS CloudTrail
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0994 — Certificate pinning, as the courseware defines it
> Also called SSL pinning — validate a remote host by associating it directly with its X.509 certificate or public key, then use pinning to bypass the SSL/TLS certificate chain validation
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0995 — s2n — what it is and what it supports
> An open-source C99 implementation of the TLS/SSL protocols, designed to be simple, small, fast and security-first. Implements SSLv3, TLS1.0, TLS1.1, TLS1.2 · 128-bit and 256-bit AES, ChaCha20, 3DES and RC4 in CBC and GCM · DHE and ECDHE for forward secrecy · SNI, ALPN and OCSP TLS extensions
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0996 — What CloudFront does with the SSL/TLS connection in the ACM architecture
> Users communicate with CloudFront over HTTPS and CloudFront terminates the SSL/TLS connection at the edge location; CloudFront then communicates to the origin over HTTP or HTTPS as configured
> Source: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

> [!question]- 0997 — Security groups vs network ACLs — the two distinctions the courseware makes
> Security groups have no "Deny" rule, so a packet is dropped unless a rule explicitly permits it, and they apply at instance and subnet level · network ACLs do have an Allow/Deny list, are stateless traffic filters on subnets, are evaluated by rule number, and their changes apply automatically to the associated subnets
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 0998 — The five fields of a security group rule
> Type · Protocol · Port Range · Source · Description — the same five apply to both the Inbound and the Outbound table
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 0999 — Why customers must create their own VPC security groups
> Because Amazon EC2 security groups would not work inside Amazon VPC; VPC security groups add capabilities EC2 security groups lack — changing the security group after the instance is launched, and specifying any protocol with a standard protocol number
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 1000 — The four AWS VPC architecture templates, by level of public access
> VPC with only a single public subnet · VPC with public and private subnets · VPC with public and private subnets including hardware VPN access · VPC with only a private subnet along with hardware VPN access
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 1001 — Virtual Private Gateway (VPG) vs Internet Gateway
> VPG establishes private connections between an Amazon VPC and another network, with traffic isolation per VPG and each VPN connection secured by a pre-shared key plus the customer gateway device's IP address · an internet gateway is attached to a VPC to enable direct connectivity with the internet, Amazon S3 and other AWS services, and each instance needs an Elastic IP or to route traffic through a NAT instance
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 1002 — The five DMZ / isolation measures the courseware lists for AWS network security
> Use a demilitarized zone exposing external services to an untrusted network · isolate resources with subnets, firewalls and routing tables · secure DNS configurations · limit inbound/outbound traffic · secure accidental exposures
> Source: [[12-LO04l-AWS-VPC-and-Network-Security]]

> [!question]- 1003 — The two AWS DDoS detection inputs Shield Standard combines
> Traffic signatures and anomaly algorithms (plus analysis techniques) — it detects malicious traffic in real time, and automatically mitigates basic network layer attacks using deterministic packet filtering and priority-based traffic techniques
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1004 — AWS Shield Standard vs AWS Shield Advanced
> Shield Standard — threat protection for the first point of entry from outside the AWS network, automatic protection for all AWS customers at no additional charge, always on, pre-configured, static, no reporting or analytics, and the services CloudFront, Global Accelerator and Route 53 are part of it · Shield Advanced (optional) — available for CloudFront, Route 53 and Global Accelerator, and can be used with Elastic IP addresses to secure Network Load Balancers or Amazon EC2 instances
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1005 — What Amazon S3 Block Public Access does
> It ensures that the objects do not have public permissions — if a user writes an object in a bucket with S3 Block Public Access enabled and that object has public permissions through an ACL or any other policy, then that permission will be blocked
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1006 — How to restrict access to Amazon S3 resources
> Combine bucket policies, ACLs and IAM policies · enforce the VPC endpoint policy for private VPC-endpoint connections to S3 · use IAM policies to implement TLS encryption for S3 requests or S3 SSE with KMS keys · S3 Object Lock sets a specific retention date to prevent object deletion
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1007 — The two S3 metadata classes and the user-defined prefix
> System-defined metadata (add via Properties > Metadata > Add Metadata, picking a key and a value from the menus) and user-defined metadata, whose keys start with the `x-amz-meta-` prefix — e.g. custom name `alt-name` becomes `x-amz-meta-alt-name`
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1008 — Data classification by sensitivity, and Amazon Macie
> Public Data — not sensitive, available to everyone, unencrypted · Critical Data — not accessible directly on the internet, requires authentication and authorization, encrypted · Amazon Macie automatically discovers, classifies and protects sensitive data in AWS using machine learning, identifying PII and providing dashboards and alerts
> Source: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

> [!question]- 1009 — What Amazon GuardDuty is and how it works
> A threat detection service that monitors AWS accounts, instances, users, databases and workloads continuously for malicious activity; it delivers detailed security findings for visibility and remediation, using anomaly detection, ML, threat intelligence feeds and behavioral modeling to expose threats
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1010 — Amazon VPC Flow Logs vs Amazon CloudWatch Events
> VPC Flow Logs collect and store information about the incoming and outgoing IP traffic from Amazon VPC network interfaces, for debugging or where network flow data are required by legal or security policies · CloudWatch Events deliver system events describing changes in AWS resources, matched and routed to target functions or streams using simple rules
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1011 — Amazon Inspector — what it is
> An automated security assessment service that improves the security and compliance of applications deployed on AWS, working application-by-application; it automatically evaluates applications for vulnerabilities, exposures and deviations from best practices and lists security findings by severity level
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1012 — The four CloudTrail-related checklist items
> Permit CloudTrail logging across all Amazon Web Services · set (establish) CloudTrail log file validation · permit CloudTrail multi-region logging · combine CloudTrail with CloudWatch
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1013 — The credential and root-account hygiene items in the AWS security checklist
> Set MFA for the root account and for IAM users · avoid use of root user accounts · do not use access keys with root accounts · link IAM policies to groups or roles · rotate IAM access keys regularly and standardize the number of days · establish strict password policies and set password termination session to 90 days · reduce the number of IAM groups · disable unused or inactive IAM users · remove unused IAM access keys · terminate available access keys
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1014 — The encryption-at-rest and transport items in the AWS security checklist
> Encrypt the CloudTrail log files at rest · encrypt Amazon RDS · EBS must be encrypted · SSL secure ciphers and versions between client and ELB · use secure CloudFront SSL versions and HTTPS for CloudFront distributions · do not use expired SSL/TLS certificates · permit the required SSL parameters in all Redshift clusters · minimize the number of discrete security groups · use a standard naming (tagging) convention for EC2
> Source: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

> [!question]- 1015 — Which layers does the Azure service provider own completely under SaaS?
> Applications · network controls · operating system · physical hosts · physical network · physical data
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1016 — Which Azure service model has the customer completely retaining identity and directory infrastructure, applications and network controls?
> IaaS — plus information and data, devices, accounts and identities and the OS; the provider keeps only physical hosts, physical network and physical data center
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1017 — What is shared between the customer and Azure under SaaS?
> Identity and directory infrastructure — only; data, devices and identities stay with the customer, applications/network/OS/physical layers go to the provider
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1018 — Under PaaS, which layers are shared between customer and Azure?
> Identity and directory infrastructure · applications · network controls
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1019 — What is the responsibility split under the Azure on-premises data center model?
> All responsibilities are retained by the customer
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1020 — Shared responsibility items enumerated by the Azure courseware
> Data classification and accountability · client and endpoint protection · identity and access management · application-level controls · network controls · host infrastructure · physical security
> Source: [[12-LO05a-Azure-Shared-Responsibility-Model]]

> [!question]- 1021 — The two rules that govern Azure AD Conditional Access policies
> Implemented after first-factor authentication · configured on group, location and application sensitivity for SaaS apps and Azure AD-connected apps, and applied to on-premise and Azure cloud applications
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1022 — What does Azure AD Conditional Access do, as printed?
> It is the tool Azure AD uses for enforcing organizational policies to manage and control access to corporate resources, giving security and right access control
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1023 — The Azure single sign-on click path
> Azure AD Active Directory settings → Azure AD connect → under USER SIGN-IN enable Seamless single sign-on
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1024 — The 12 Azure IAM best practices listed on p159
> Enable SSO · turn on conditional access · enable password management · enforce MFA · enforce cloud-based MFA · enforce Azure AD identity protection · implement RBAC · restrict exposure of privileged accounts · centralize identity management · use Azure AD for storage authentication · treat identity as the primary security perimeter · plan for routine security improvements
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1025 — Why is the Azure AD Connect "staged rollout of cloud authentication" feature used?
> It allows you to test cloud authentication and migrate gradually from federated authentication
> Source: [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]

> [!question]- 1026 — The four advantages the courseware claims for Azure AD self-service password reset
> Reduced cost — support-assisted reset accounts for 20% of an organization's IT expenditure · improved user experience (no helpdesk call) · lower helpdesk volume · mobility — reset from any location
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1027 — What do Azure AD password protection agents add on-premise?
> They extend the banned password lists to the existing Windows Server AD infrastructure, so organizations can block common local words in addition to the global banned password list
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1028 — The SSPR areas the walkthrough configures
> Properties — enable SSPR and select Selected, then Save · Authentication methods — number of methods and available methods · Registration — who registers at sign-in and the re-confirmation days · Notifications — option, then Save
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1029 — What does Security Defaults enforce, and what is the printed effectiveness claim?
> It enforces MFA to block 99.9% of identity-related attacks, and users must register for and use Azure AD MFA with the Microsoft Authenticator app using notifications; it blocks attacks such as password spray, replay and phishing
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1030 — Steps to enable Security Defaults
> Azure portal → Azure Active Directory → Properties → Manage security defaults → set Enable security defaults to Yes → Save
> Source: [[12-LO05c-Azure-Password-Management-and-MFA]]

> [!question]- 1031 — The four RBAC best practices stated for Azure
> Use RBAC for least privilege and granular access control · assign permissions on a subscription, resource group or single resource scope · use built-in roles to segregate duties and grant only the access required for the job · grant the RBAC security reader role to security teams
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1032 — Azure RBAC scopes named by the courseware
> Rules: subscription · resource group · single resource — the walkthrough step 1 additionally searches Management groups, Subscriptions and Resource groups
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1033 — Azure RBAC security principal types
> User · group · service principal · managed identity, and managed identity splits into user-assigned and system-assigned
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1034 — When does Azure RBAC use a custom role instead of a built-in role?
> When the built-in roles do not meet the requirements of the organization — the customer then creates custom roles for the Azure resources
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1035 — The Add role assignment click path, in order
> Search the scope → open the resource → Access control (IAM) → Role assignments tab → Add > Add role assignment → pick the role on the Roles tab → Members tab: user, group or service principal, or managed identity → Select members → optional Description → Next → optional Add condition → Review + assign
> Source: [[12-LO05d-Azure-RBAC]]

> [!question]- 1036 — The six best practices the courseware gives for securing privileged Azure accounts
> Turn on Azure AD PIM (limits excessive, unnecessary or misused access) · define at least two emergency access accounts on the *.onmicrosoft.com domain · make all critical administrator accounts passwordless or require MFA · use Microsoft Authenticator for passwordless sign-in · give admins a separate workstation where production tasks are not allowed · use privileged access workstations
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1037 — What makes an Azure AD emergency access account, and when is it needed?
> Highly privileged, not assigned to an individual, cloud-only on the *.onmicrosoft.com domain, at least two of them — used when admins' devices or the MFA service are unavailable, when MFA cannot be completed to activate a role, when the Global Administrator has left, and in a natural disaster
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1038 — The four emergency access account settings configured at creation
> Username · Name · a long and complex password · Global Administrator role (under Roles) · usage location — then Create
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1039 — Azure AD PIM role settings touched in the Global Administrator walkthrough
> Activation: on activation require Azure MFA, duration 2 hours, plus require justification / ticket information / approval to activate — Assignment: expire eligible after 1 year, expire active after 6 months, require Azure MFA and justification on active assignment
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1040 — The Microsoft Authenticator authentication-mode options and the consequence of one of them
> Any or Passwordless — each added group or user defaults to "Any" (passwordless and push notification); choosing Push prevents the use of the passwordless phone sign-in credential
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1041 — What is a PAW and what protects it
> The highest security configuration for extremely sensitive roles — a hardened workstation on a dedicated OS where local administrators are restricted from access and only sensitive job tasks run, featuring application control, application guard, credential guard, app guard, device guard and exploit guard
> Source: [[12-LO05e-Azure-Privileged-Identity-Management]]

> [!question]- 1042 — The three advantages the courseware gives for Azure centralized identity management
> Provide a common identity for accessing both cloud and on-premise resources · enable administrators to manage accounts from one location · enhance security by preventing configuration errors
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1043 — Which tool does the courseware name to implement centralized identity management, and what must happen first?
> Azure AD Connect — it synchronizes the on-premise directory with the cloud directory. Prerequisite: users must synchronize the on-premise and cloud identity directories
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1044 — What the courseware prints as the benefits of using Azure AD Connect
> A common accessing identity to both cloud and on-premise resources (productivity) · a common hybrid identity leveraging Windows Server AD connected to Azure AD · conditional access by application resource, network location, device and user identity, and MFA · common identity reused for Office 365, SaaS and third-party apps
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1045 — Two reasons the courseware gives for using AD FS with the cloud directory
> AD FS overcome the authentication challenges created by the AD, and resolve the third-party authentication challenges — it also provides Web SSO to multiple web apps with a single account
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1046 — Password hash synchronization — what moves, in which direction, and why
> User password hashes move from an on-premise AD instance to a cloud-based Azure AD instance, to protect against leaked credentials; users keep one password for multiple Azure accounts, raising productivity and cutting helpdesk cost, and PHS can act as backup if on-premise servers fail
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1047 — Site-to-Site VPN in Azure — the three security benefits the courseware states
> Secure Connectivity (all traffic encrypted, protected against modification and eavesdropping) · Simplified Network Architecture (no internal-to-external IP conversion) · Access Control (admin defines rules simply because S2S VPN users are internal users)
> Source: [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]]

> [!question]- 1048 — The two data encryption models in Microsoft Azure and who performs the crypto
> 1. Server-side — the Azure resource provider performs encryption and decryption; 2. Client-side — encryption is performed outside the Azure service provider by the service or calling application, and the provider receives data it cannot decrypt
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1049 — The three sub-models under the server-side encryption model
> SSE with service-managed keys (Microsoft manages the keys) · SSE with customer-managed keys in Azure Key Vault · SSE with customer-managed keys on customer-controlled hardware
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1050 — What the courseware warns about when you manage your own keys in Azure Key Vault
> Loss of encryption keys leads to loss of data — do not delete the encryption keys, but keep a backup of the creation or rotation of keys
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1051 — What Azure Key Vault is used for, and the three concerns it addresses plus HSM backing
> A secure storage for the keys used to encrypt data at rest in Azure services — secrets management (tokens, passwords, API keys), key management, certificate management (SSL/TLS), and secrets/keys protected by software or FIPS 140-2 Level 2 validated HSMs
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1052 — Azure Storage Service Encryption — the algorithm and the encryption point
> 256-bit AES — data is encrypted before storing and decrypted upon retrieval; it is applied to the entire Azure storage system, users can enable or disable it, and data is encrypted only when SSE is enabled
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1053 — Transparent Data Encryption in Azure — what it is and what it covers
> An SQL Azure feature that encrypts data at both the database and server levels, covering the database, backups and transaction log files at rest without modifying the application; protects Azure SQL Database, SQL Managed Instance and Data Warehouse; it must be enabled per database
> Source: [[12-LO05g-Azure-Encryption-Data-at-Rest]]

> [!question]- 1054 — The five practices the courseware gives for encrypting data in transit in Azure
> Use HTTPS for Azure Storage objects and REST APIs · use Shared Access Signatures and enable Secure Transfer Required on storage accounts · use SMB 3.x for Azure File Storage · use client-side encryption before transfer into Azure Storage and decrypt on receipt · use Azure Site-to-Site (or point-to-site) VPN to encrypt between the corporate network and the Azure VNet
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1055 — What does "secure transfer required" actually do on an Azure storage account
> It enforces the HTTPS protocol — including when Shared Access Signatures and the REST APIs are used — so storage traffic cannot fall back to unencrypted HTTP
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1056 — What the courseware states about SMB 3.x in Azure File Storage
> SMB 3.0 uses encryption during transit, is available in Windows Server 2012 R2, Windows 8, Windows 8.1 and Windows 10, and allows cross-region access
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1057 — Site-to-Site VPN versus Point-to-Site VPN in Azure — the scope difference
> Site-to-Site connects the entire network (e.g., on-premise) to the Azure virtual network over a highly secure IPsec tunnel mode; Point-to-Site connects a single device to the Azure virtual network; both enable cross connectivity
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1058 — The values printed in the Azure Add-connection form for a Site-to-Site VPN
> Name VNet1toSite2 · connection type Site-to-site (IPsec) · virtual network gateway VNet1GW · local network gateway Site2 · shared key (PSK) — then click OK to create the connection
> Source: [[12-LO05h-Azure-Encryption-in-Transit]]

> [!question]- 1059 — What the courseware says you must do to secure inbound internet communications to an Azure VM, and the four application-level steps
> Implement SSL encryption to secure data transfer — get an SSL certificate, modify the service definition and configuration files, upload the certificate, then connect to the role instance via HTTPS
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1060 — What an endpoint ACL in Azure is used for, and what the two tool options are
> To restrict access on public endpoint IP addresses and restrict traffic to specific IP address sources — created and managed with PowerShell or through the Azure Management Portal (which can add, modify or remove an ACL on an endpoint)
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1061 — The two-step risk the courseware gives for exposing RDP/SSH to the internet
> An attacker using brute-force techniques over RDP/SSH over the internet can gain access to an Azure VM; once in, that VM becomes a launch point to compromise other VMs on the virtual network or attack network devices outside the Azure cloud
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1062 — The three alternatives the courseware offers instead of direct RDP/SSH over the internet
> Point-to-Site VPN, Site-to-Site VPN, and ExpressRoute — the protocols printed for Point-to-Site are SSTP, Open VPN and IKEv2
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1063 — The three security benefits the courseware states for Site-to-Site VPN
> Secure Connectivity — all traffic encrypted, protected against data modification and eavesdropping · Simplified Network Architecture — no internal-to-external IP address conversion · Access Control — rules defined simply because S2S VPN users are internal users
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1064 — ExpressRoute versus Site-to-Site VPN as the courseware describes it
> It works like Site-to-Site VPN but over a dedicated WAN link that does not go through the internet, so it is stable, faster, lower latency and more reliable, and it creates private connections between on-premises/co-located infrastructure and Azure data centers
> Source: [[12-LO05i-Azure-Inbound-Access-Control]]

> [!question]- 1065 — The three load-balancing options the courseware names and what each is for
> Azure Application Gateway — an HTTP web traffic load balancer doing end-to-end SSL encryption and SSL termination at the gateway · Azure Traffic Manager — load balances connections to services based on user locations (global, nearest data center) · external or internal Azure Load Balancer — distributes incoming requests across multiple VMs for higher availability
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1066 — What Azure Application Gateway offloads from the back-end web servers
> Encryption and decryption overhead — it terminates SSL at the gateway, implements end-to-end SSL encryption, and ensures unencrypted traffic flows to the back-end servers
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1067 — The Azure Application Gateway creation steps actually printed
> On the Azure homepage click Application Gateways, click create application gateway, fill in the details and click Review + create — no further create or Go to resource step is given
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1068 — The Azure Load Balancer creation steps actually printed
> On the Azure homepage click Load balancers, click Create load balancer, fill in the details and click Review + create, after validation click create, click Go to resource — then the load balancer is created
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1069 — How the courseware justifies Azure Traffic Manager performance
> Global Load Balancing routes to the nearest data center, and connectivity to the nearest data center is faster than to a distant one
> Source: [[12-LO05j-Azure-Load-Balancing]]

> [!question]- 1070 — What do Azure NSGs control, and how many subnets/VMs can one NSG cover?
> Inbound and outbound access to subnets, VMs, and network interfaces (NICs) — and an NSG can be applied to multiple subnets or VMs
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1071 — Can Azure's default NSG rules be deleted?
> No — they cannot be deleted, but they can be overruled by the customers
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1072 — What does Azure Firewall do inside the virtual network?
> It is an easily manageable cloud-based network security service that protects Azure virtual resources, implements network connectivity policies in virtual networks, and lets customers create allow or deny network filtering rules
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1073 — Which rule set is a WAF on an application gateway based on, and how is it kept current?
> The OWASP Core Rule Set (CRS) 3.1, 3.0 or 2.2.9 — WAFs are automatically updated to protect against new vulnerabilities
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1074 — The Azure Firewall creation steps actually printed
> Azure homepage > create a resource > type Firewall in the search box > Create > fill details and Review + create > after validation click Create > after deployment Go to resource — then the firewall is created
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1075 — The NSG creation steps actually printed
> Azure homepage > Network security group > Create network security group > details and Review + create > after validation Create > after deployment Go to resource > Inbound security rules > Add > enter details and Save
> Source: [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]]

> [!question]- 1076 — What does Microsoft Antimalware for Azure provide, and when does it alert?
> Real-time protection — it generates alerts on the installation and execution of malicious or unwanted software
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1077 — Name three Microsoft Antimalware features that are about updates
> Signature updates (automatic installation of protection signatures) · Antimalware Engine updates · Antimalware Platform updates
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1078 — What does the Azure Guest Agent (Fabric Agent) do in the antimalware chain?
> It runs the antimalware extension and configures its parameters, enabling the Antimalware service with default or custom configuration — default settings apply when no custom configuration is provided
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1079 — Where do Microsoft Antimalware events end up?
> The service writes them to the system OS event log under the "Microsoft Antimalware" event source; antimalware monitoring writes them as produced to the Azure Storage account, where the Azure Diagnostics extension collects and stores them in tables
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1080 — The four components of the Azure datacenter network topology
> Edge network · Wide area network · Regional gateways network · Datacenter network
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1081 — What is blocked by default when an Azure VM is created, and who adds the exceptions?
> All incoming and outgoing traffic is blocked by default; rules and exceptions to allow authorized traffic are added in the hypervisor packet filter by the FC agent
> Source: [[12-LO05l-Azure-Antimalware-and-Network-Architecture]]

> [!question]- 1082 — How does the courseware characterise a network security group?
> A simple, stateful packet inspection device that creates allow/deny rules for network traffic — used to protect Azure subnets against uninvited traffic
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1083 — Name the nine Azure network security best practices printed on the slide
> Strong network controls · logically segment subnets · adopt a Zero-Trust approach · control routing behaviour · deploy perimeter networks for security zones · avoid internet exposure with dedicated WAN links · disable RDP/SSH access to VMs · secure critical service resources to only virtual networks · use virtual network appliances
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1084 — Why does the courseware tell you to configure user-defined routes?
> Because VMs on different subnets can still connect to other VMs on a similar virtual network — user-defined routes plus a security appliance stop that
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1085 — What does the Zero-Trust best practice combine?
> Azure AD Conditional Access based on devices, identity and network location, plus just-in-time VM access in Microsoft Defender for Cloud to lock down inbound traffic to Azure VMs
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1086 — What is Azure ExpressRoute, per the courseware?
> A dedicated WAN link between the Microsoft Exchange hosting provider and the on-premises location, letting connectivity providers build a private connection of on-premises networks into the Microsoft cloud — reaching Azure, Microsoft 365 and Dynamics 365
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1087 — What happens on an active geo-replication failover?
> The application starts failover to a secondary database; after the failover the secondary becomes the primary, with different connection endpoints
> Source: [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]]

> [!question]- 1088 — What does the Azure Activity Log give you, and what is it scoped to?
> Insights into subscription-level events — it is used to collect, view and analyze the activity log
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1089 — Name the Activity Log filter fields printed on p239
> Timespan · Category · Subscription · Resource group · Resource (name) · Resource type · Operation name · Severity · Event initiated by · Open search
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1090 — The five VM statistics the Azure portal is said to track
> CPU percentage · Disk Read Bytes/s · Disk Write Bytes/s · Network in · Network out
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1091 — What is Microsoft Defender for Cloud, in the courseware's own framing?
> A cloud security posture management (CSPM) and cloud workload protection (CWP) solution that continuously assesses, secures and defends workloads across multi-cloud (AWS and GCP), Azure and on-premises
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1092 — Name the seven Network Watcher operational security features
> Audit Logs · IP Flow Verifies · Next Hop · Security Group View · NSG Flow Logging · Remote Network Monitoring · VPN Connectivity Issues
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1093 — What 5-tuple does IP Flow Verifies check, and what is it for?
> Source IP, Destination IP, Protocol, Source Port and Destination Port — to check if a packet is denied or allowed according to flow information
> Source: [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]

> [!question]- 1094 — How many Azure security checklist items does the courseware print in the body, and what do they cover?
> 19 items, all Azure AD identity, access, consent and guest-user settings — no network, data, encryption, antimalware or monitoring item is printed on pp243-244
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1095 — The first three checklist items
> Ensure MFA is enabled for all users · ensure there are no guest users · use RBAC to manage the access to resources
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1096 — Which checklist settings control password-reset behaviour, and to what values
> Memorize multi-factor authentication on devices they trust = disabled · number of processes required to reset = two · number of days before users are asked to re-confirm their authentication report = not zero · caution users on password resets = yes · notify all admins when other admins reset their password = yes
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1097 — The guest-user checklist items
> No guest users · guest user agreements are limited = yes · members can request = no · guests can invite = no
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1098 — The group and administration checklist items
> Entrance to the Azure AD administration portal is limited · users can create security associations = none · self-service group administration enabled = no · users who can handle security groups = none · users can create Office 365 groups = no
> Source: [[12-LO05o-Azure-Security-Checklist]]

> [!question]- 1099 — Features listed under LO#06
> GCP shared responsibility model · GCP IAM features and best practice to implement IAM securely · GCP encryption and key management (data at rest / data in transit) · GCP network security measures · GCP data storage security · GCP monitoring and logging
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1100 — In Google's shared responsibility model, which rows stay with the **user** at each layer
> IaaS: guest OS/data/content down to content (everything above network) · PaaS: deployment · usage · access policies · content · SaaS: access policies · content — content and access policies are the customer's at all three layers
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1101 — The three divisions of the GCP IAM model
> Principal (an identity — an email address) · Roles (a collection of permissions) · Policy (binds a set of members to a role, via one or more bindings)
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1102 — The seven GCP IAM members
> Google account · Service account · Google group · Google Workspace account · Cloud Identity domain · All authenticated users · All users
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1103 — GCP IAM stated purpose
> Granular access to specific Google Cloud resources, preventing unauthorized access, under POLP (principle of least privilege) — administrators control access by implementing IAM policies
> Source: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

> [!question]- 1104 — Definition of a GCP service account
> A special account that belongs to an application or VM instance, but not to end-user, to run the specified account code hosted in Google cloud — multiple service accounts can be created for different logical components of an application
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1105 — GCP permission format and the printed examples
> `<service>.<resource>.<verb>` — e.g. `pubsub.subscriptions.consume`; calling `topics.publish()` needs `pubsub.topics.publish`; permissions correlate one-to-one with REST API methods
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1106 — The 8 GCP IAM security best practices
> Grant least privileges to avoid primitive roles · Create separate service account · Check granted policy on each resource · Restrict who acts as service accounts · Rotate service account keys · Restrict access to create and manage service accounts · Grant predefined roles · Use logging roles for log auditing
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1107 — Project-level vs fine-grained grant
> Fine-grained — grant at the resource instead of the project (e.g. a single bucket → Storage Admin `roles/storage.admin`); Project level — the grant is inherited by all resources of that project, e.g. all buckets or all Compute Engine instances instead of individual ones
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1108 — Google group vs Cloud Identity domain
> Google group = collection of Google accounts and service accounts with one email address but no login credentials, so policies apply to the whole group without editing the IAM policy; Cloud Identity domain = virtual group of all Google accounts whose users cannot access the G Suite domain applications
> Source: [[12-LO06b-GCP-Service-Accounts]]

> [!question]- 1109 — When is a GCP **basic role** acceptable
> When a predefined role is not offered by the service · when you want to give a project broader permission · in test/development environments · for a small team that does not need granular permissions — otherwise assign the minimum predefined or custom role
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1110 — The four service-account-key rotation steps, in order
> Create a new key → switch apps to utilize the new key → disable the old key → delete the old key if certain it is no longer required
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1111 — Service account keys vs encryption keys
> Distinct — data is normally encrypted using encryption keys, and safe access to Google Cloud APIs is achieved via service account keys; never check the keys into source code or leave them in the Downloads directory
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1112 — Service Account User role: project-level vs single-account grant
> Project level → access to all service accounts in the project including any future ones; single account → access only to that account, and the principal can pretend to be it (roles/iam.serviceAccountUser)
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1113 — How does the courseware grant temporary access
> Conditional role binding for time-bounded access, so a user cannot reach the resource after the stated expiration date and time — add an IAM condition to an existing binding via the Condition Builder (condition type Expiring Access, by From, Time Date range) or the Condition Editor (CEL expression, Run Linter to validate)
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1114 — Which GCP roles let you change permissions without full administrative access
> Project IAM Admin and Folder IAM Admin — grant them only to those who must change permissions; grant owner (roles/owner) only when universal access is necessary
> Source: [[12-LO06c-GCP-IAM-Security-Best-Practices]]

> [!question]- 1115 — The three GCP primitive roles and what each grants
> Owner — all editor permissions plus project billing setup and management of all project resources · Editor — viewer permissions plus, for most GCP services, permission to modify resources · Viewer — read-only and viewing
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1116 — When may a primitive role be granted
> Only when the GCP service does not provide a predefined role · to grant broader permissions for a project (e.g. development or test environments) · for small teams that do not require granular permissions
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1117 — Separate-service-account rules
> One service account per service that needs a different permission set · treat every application component as a separate trust boundary · grant only the required permissions to each service account · minimum permission based on requirement · up to 100 service accounts per project
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1118 — Service account creation click path, in order
> IAM & admin → service accounts → CREATE SERVICE ACCOUNT → enter details → Create → select the role → CONTINUE → CREATE KEY and choose the JSON file with the private key → DONE (viewable in the IAM PERMISSIONS tab)
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1119 — Why caution is needed when granting a service account user role
> At project level it reaches all service accounts in the project, including future ones; at service account level it reaches that account — and the service account users indirectly have access to all resources of the service account
> Source: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]]

> [!question]- 1120 — The two categories of GCP service account key
> GCP-managed — cannot be downloaded or automatically rotated, used within two weeks, utilized by GCP services such as App Engine and Compute Engine; User-managed — the user creates, downloads and manages them, and they expire after ten years
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1121 — The courseware's definition of key rotation
> Generate a new key version of the key and mark that version as the primary version — done periodically; the user needs roles/cloudkms.admin, roles/owner or roles/editor
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1122 — Automatic vs manual key rotation
> Automatic — set a rotation schedule that determines when the key is rotated (gcloud kms keys update) · Manual — generate a new key version, disable automatic rotation, and set the new version as primary (gcloud kms keys versions create … primary)
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1123 — What happens to previous key versions after rotation
> They are neither disabled nor destroyed — this prevents data loss, so data encrypted under the old version is NOT automatically re-encrypted; the user must decrypt and re-encrypt with the new version, and may schedule the old version for destruction only once it protects no data
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1124 — Which service account API methods automate rotation
> serviceAccount.keys.create() and serviceAccount.keys.delete()
> Source: [[12-LO06e-GCP-Service-Account-Key-Rotation]]

> [!question]- 1125 — The four levels at which a GCP IAM policy can be set, and what each is inherited by
> Organization — policies are inherited by all resources · Folder — the highest folder level's roles are inherited by the projects and other folders in the parent folder · Project — the trust boundary; its roles are inherited by all resources · Resource — lowest-level roles, e.g. Genomics data, Compute Engine instances and Pub/Sub topics, apart from Cloud Storage
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1126 — The two constraint names printed for disabling service account creation
> Figure and both snippets: constraints/iam.disableServiceAccountCreation · body sentence: iam.disableServiceAccountKeyCreation (which "will not allow the creation of user-managed credentials") — the courseware prints both
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1127 — How to centralize the management of service accounts
> Disable the creation of new service accounts by enforcing the boolean constraint in an organization policy — console: IAM & Admin → Organization policies → select the organization → Disable Service Account Creation → Edit → Applies to Customize → Enforcement On → Save
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1128 — What does `Inherit parent's policy` do
> It lets the resource inherit the rules of the parent's policy, so a child no longer carries its own overridden policy — the policy summary then shows the Inherited policy / Google-managed default alongside the Current policy
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1129 — How is an effective IAM policy formed for a resource
> By combining the policy inherited from the parent with the policy set at the resource itself — so the hierarchy is organization (root) → projects (children) → other resources (descendants)
> Source: [[12-LO06f-GCP-Organization-Policies]]

> [!question]- 1130 — Why grant pre-defined roles instead of primitive roles
> To implement granular access to specific GCP resources and prevent unwanted access to other resources — predefined roles provide fine-grained access control, and a specific role is given to a resource type (multiple roles may be given to the same user); e.g. roles/pubsub.publisher only allows publishing messages for a Pub/Sub topic
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1131 — At which levels can a GCP custom role be created, and what is the drawback
> Organization and project level only — never at the folder level. Drawback: because Google does not maintain custom roles, they are not updated automatically by the GCP. Needed when predefined roles do not satisfy the organization's requirements
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1132 — `roles/logging.viewer` vs `roles/logging.privateLogViewer`
> viewer = read-only access to logging features, and does NOT give access to Access Transparency logs or Data Access audit logs · privateLogViewer = the log viewer role PLUS read access to Access Transparency logs and Data Access audit logs
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1133 — Which logging role is granted to service accounts for writing logs, and which for log metrics and export sinks
> `roles/logging.logWriter` — to service accounts, giving applications permission to write logs · `roles/logging.configWriter` — log metrics, log exclusion, and exporting log entries to a sink · `roles/logging.admin` — all logging permissions
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1134 — Which roles can read Data Access audit logs
> Only `roles/logging.privateLogViewer` and `roles/owner` (full access to logging, Access Transparency logs and Data Access audit logs) — `roles/viewer`, `roles/logging.viewer` and `roles/editor` are all excluded, and `roles/editor` also cannot create export sinks
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1135 — Where do you pick permissions from when building a custom role with logging permissions
> Select an API permission for the logging API role; select from console permissions for the role that grants Log Viewer; browse the `gcloud` tool for the role that grants `gcloud` logging
> Source: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]]

> [!question]- 1136 — At which layer does Google encrypt data at rest, and what protects what
> Several layers: Application → Platform → Infrastructure → Hardware. At the hardware device layer Google encrypts hard disks and solid-state drives with a device-level key; at the storage level data are broken into chunks of different sizes and each chunk is encrypted with a distinct encryption key, and those keys do not match each other even for the same customer on the same system
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1137 — KEK vs DEK in Google Cloud KMS — who stores what
> KMS stores the Key Encryption Keys (KEKs); the DEKs are generated locally, encrypt the data, and are then wrapped by the KEKs. The encrypted data chunk is stored with the wrapped DEK. Because one key envelops another this is called Envelope Encryption
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1138 — The Cloud KMS hierarchy, top to bottom
> Project (run KMS in a separate project, because primitive cloud IAM roles can otherwise reach all its resources) → Location (geographical region where requests are processed and keys are stored) → Key Ring (collection of keys for an organizational purpose, specific to a project; keys inherit the property from the key rings) → Key (the actual bits used for encryption) → Key version
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1139 — Customer-supplied vs customer-managed encryption keys
> Customer-supplied = the customer supplies their own keys as an extra layer over standard cloud storage encryption, and creates/manages them · Customer-managed = the customer uses keys generated by KMS as the additional layer, and generates/manages them
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1140 — `gcloud` commands to create a key ring and an encryption key (as printed on pp280-281)
> `gcloud kms keyrings create $KEYRING_NAME --location global` then `gcloud kms keys create $CRYPTOKEY_NAME --location global --keyring $KEYRING_NAME --purpose encryption` — the p281 body prints the key name as `democode` while p280's text prints `demolab`
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1141 — How is Cloud KMS enabled, in the console and on the command line
> CLI: `gcloud services enable cloudkms.googleapis.com`. Console: Google console dropdown menu, IAM & admin, Audit Logs; go to the Filter Table and select Title: Cloud Key Management Service (KMS) API; check the Cloud Key Management Service (KMS) API box, select the required service, and click Save
> Source: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]]

> [!question]- 1142 — The three defense-in-depth network security principles
> Secure internet-facing services · Secure VPC for private deployments · Micro-segment access to applications and services
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1143 — Which two GCP services together protect against Layer 3 and Layer 4 volumetric DDoS on publicly exposed data
> Place the services behind the Google Cloud HTTP(S) Load Balancer and deploy Google Cloud Armor — together they provide protection from Layer 3 and Layer 4 volumetric DDoS attacks
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1144 — What do WAF policies at the edge prevent, and what range of attributes do WAF custom rules filter
> Preconfigured WAF rules prevent cyberattacks such as SQL injection and cross-site scripting; WAF custom rules filter internet traffic across Layer 3 through Layer 7 attributes
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1145 — Host project vs service project in a shared VPC
> A shared-VPC organization consists of host projects connected to service projects; the host project network IS the shared VPC network, which is centrally managed across multiple projects over internal IPs. Run the setup from the host project — Shared VPC plus IAM separates network administration from project administration
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1146 — Firewall rules vs routes in GCP
> Firewall rules allow or deny traffic to and from VPC-attached resources (Compute Engine VMs, GKE clusters) and are targeted at specific VMs with network tags; incoming traffic from outside the network is blocked by default. Routes define the paths network traffic takes from a VM instance to another destination, inside or outside the VPC, resolved by the VM instance controller to a next hop in routing order
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1147 — How do you micro-segment in GCP
> VM-based applications — Google VPC firewall rules regulate communication between them; GKE-based applications — network policies set on the Google GKE clusters control container-to-container communication. Note VPC networks are global resources, not tied to a zone or region, and a project can hold several of them depending on the set organizational policy
> Source: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]

> [!question]- 1148 — How does GCP mitigate a DoS attack by default
> The data centers' fiber-optic Internet connection passes through several layers of software and hardware load balancers; the load balancers report incoming traffic to a central DoS service, which on detecting an attack configures the load balancers to drop or throttle the attack traffic. The central DoS service also gets application-layer information from the GFE instances (which the load balancers cannot see) and configures them to drop or throttle attack traffic
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1149 — What does the Google Front End (GFE) provide and do
> GFEs provide public IP address hosting of a public DNS name, DoS protection, and TLS termination; GFE applies DoS protections that terminate user traffic and automatically scale to absorb attacks before they reach the user's compute instances
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1150 — The ten GCP DDoS mitigation best practices
> Reduce the attack surface (Google Cloud Virtual Network, subnets/networks, firewall rules, tags, IAM, anti-spoofing, inter-VPC isolation) · isolate internal traffic (no public IPs, NAT gateway or SSH bastion, internal load balancing) · enable proxy-based load balancing (HTTP(S) or SSL proxy, multi-region) · scale to absorb (GFE, Anycast load balancing, autoscaling) · protect with CDN offloading (Google Cloud CDN, CDN Interconnect) · deploy third-party DDoS protection or Google Cloud Launcher solutions · deploy App Engine with a dos.yaml IP/IP-network blocklist · restrict Google Cloud Storage with signed URLs · API rate limits on the Compute Engine API · enforce Compute Engine resource quotas
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1151 — Which GCP best practice is stated as avoiding IP address conflicts
> Disable default networks — disable creation of default networks in new projects, delete them in existing projects, avoid IP address conflicts by first planning network and IP address allocation across connected deployments and projects, and limit multiple VPCs to one per project to enforce access control effectively
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1152 — The four network monitoring tools named as telemetry
> VPC Flow Logs and Firewall Rules Logging (real-time visibility into traffic) · Firewall Insights (reviewing firewall rules) · Network Intelligence Center (how network topology and architecture are performing) · Connectivity Tests (insight into the firewall rules and policies applied to the network path)
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1153 — Why use service accounts in firewall rules
> To enforce isolation without depending on an IP address as the sole identifier of a workload — combine with hierarchical firewall policies (rules applying to all networks regardless of network-level rules) and define folder-level rules to cover only portions of an organization
> Source: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]]

> [!question]- 1154 — Which three tools does the courseware name for monitoring logs
> GCP Logging from Console · Cloud Audit Logs · Google Cloud's operations suite — and Google Cloud services generate structured logs that can be easily queried
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1155 — The four GCP Logging console features
> Predefined or custom queries · create metrics from logs · a live stream of logs from multiple resources across the deployed cloud · export logs to other destinations (Google Cloud Storage, Google BigQuery, or Google Cloud Pub/Sub)
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1156 — The three Cloud Audit Logs types and the roles that read them
> Admin Activity Audit logs — Logging/Logs Viewer or Project/Viewer · Data Access Audit logs — Logging/Private Logs Viewer or Project/Owner · System Event Audit logs — Logging/Logs Viewer or Project/Viewer. Audit the access to service account keys regularly, and view them from the console by clicking Activity
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1157 — What is Google Cloud's Operation Suite and what does the log router do
> A collection of management tools that integrate monitoring, logging and trace managed services for applications and systems on Google Cloud and beyond, used to collect metrics, traces and logs and build dashboards, charts and alerts. All logs — audit, platform and user — are sent to the Cloud Logging API and pass through the log router, which checks each entry against existing rules to decide which to discard, which to ingest, and which to include in exports
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1158 — Which compliance standards are printed for GCP
> SSAE16/ISAE 3402 Type II (including SOC2 and 3) · ISO 27001, 27017, 27018 · FedRamp · PCI-DSS · HIPAA — with the note that GCP supports HIPAA compliance but it must be calculated by the customer
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1159 — The four administrative-hygiene items on the Google security checklist
> Enforce two-step verification for users · do not use a super admin account for daily activities · do not remain signed into an idle super admin account · do not automatically share the contact information
> Source: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

> [!question]- 1160 — The seven NIST recommendations for cloud security
> Assess risks posed to client data, software, and infrastructure · select appropriate deployment model according to the requirements · ensure audit procedures for data protection and software isolation · renew SLAs if security gaps are found between the security requirements of an organization and the standards of the cloud provider · establish appropriate incident detection and reporting mechanisms · analyze the security objectives of the organization · determine who is responsible for data privacy and security issues in the cloud
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1161 — The four organization/provider compliance checklists and their axes
> Table 12.5 Security Team (8 rows, p308) · Table 12.6 Operations (18 rows, pp309-310) · Table 12.7 Technology (8 rows, p310) · Table 12.8 Management (9 rows, pp310-311)
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1162 — Table 12.6 — the operational rows about forensics, multi-tenancy and exit
> Does the CSP have clear policies and procedures to handle digital evidence in the cloud infrastructure · does the CSP have defined procedures to support the organization in the case of incidents involving several clients in a multi-tenant environment · does the CSP provide flexibility of service relocation and switchovers · does the CSP provide 24/7 support for cloud operations and security-related issues
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1163 — Table 12.7 — the four failure modes of cloud network design
> Network congestion · misconnection · misconfiguration · lack of resource isolation. Plus: appropriate access controls such as federated SSO, data separation between the organization and customer information at runtime and during backup including data disposal, and authentication/authorization/key management mechanisms in a cloud environment
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1164 — Table 12.8 — the governance rows
> Is everyone aware of their cloud security responsibilities · is there a mechanism for assessing the security of a cloud service · does business governance mitigate the security risks from cloud-based "shadow IT" · does the organization know the jurisdictions within which its data can reside · is there a mechanism for managing cloud-related risks · does the organization understand the data architecture required to operate with appropriate security at all levels · can the organization be confident regarding end-to-end service continuity across several cloud service providers · does the provider comply with all relevant industry standards such as the UK Data Protection Act · does the compliance function understand the specific regulatory issues related to the adoption of cloud services
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1165 — Five best practices that target identity and access
> Prohibit user credential sharing among users, applications, and services · implement strong authentication, authorization, and auditing mechanisms · leverage strong two-factor authentication techniques where possible · enforce stringent registration and validation processes · use VPNs to secure the client data
> Source: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]]

> [!question]- 1166 — Scout Suite — the entire description the courseware gives
> An open source multi-cloud security-auditing tool that enables the security posture assessment of cloud environments. Using the APIs exposed by cloud providers it gathers configuration data for manual inspection and highlights risk areas. Source: https://github.com
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1167 — Qualys Cloud Platform — description, supported clouds, and readable features
> An end-to-end IT security solution providing a continuous, always-on assessment of the global security and compliance posture, with visibility across all IT assets irrespective of location. Supported/planned: Amazon Web Services · Microsoft Azure (beta) · Google Cloud Platform · Alibaba Cloud (early alpha) · Oracle Cloud Infrastructure (early alpha). Features: sensors provide continuous visibility · all data can be analyzed in real time · respond to threats immediately · visualize results in one place with AssetView
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1168 — CloudPassage Halo — the ten printed features
> Workload firewall management · multifactor network authentication · configuration security monitoring · software vulnerability assessment · file integrity monitoring · server account management · event logging and alerting · Halo REST API
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1169 — Core CloudInspect — what it is and what it enables
> Validates when a cloud deployment is secure and gives actionable remediation information when it is not, using proactive real-world security tests with the techniques attackers use to breach AWS systems. Enables users to verify AWS deployments against current attack techniques · pinpoint OS and service vulnerabilities with no false positives · measure susceptibility to SQL injection, cross-site scripting and other web-application attacks · validate controls required by industry and government regulations · get actionable information to apply patches and code fixes · certify systems before they go live
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1170 — The nine tools listed with no description
> Nessus Enterprise for AWS · Symantec Cloud Workload Protection · Alert Logic · Deep Security · SecludIT · Panda Cloud Office Protection · Data Security Cloud · Cloud Application Control · Intuit Data Protection Services — the courseware prints each with a vendor URL and nothing else
> Source: [[12-LO07b-Cloud-Security-Tools]]

> [!question]- 1171 — What the p316 module summary claims about AWS shared responsibility
> Three models — shared responsibility model for infrastructure services, for container services, and for abstract services. Note this conflicts with pp. 40-43, which teach one AWS model split into Inherited Controls and Shared Controls plus a six-item customer responsibility list
> Source: [[12-LO07b-Cloud-Security-Tools]]

## Verified external items

> Cards matched word-for-word against the module PDFs during the external-set audit. See [[External-Flashcards-Verification]].

> [!question]- V001 — Public key infrastructure
> is treated as the most effective method for providing verification during electronic transactions  _(Mod 03 p82)_
> Source: [[03-LO04-Cryptographic-Techniques]] · verified set 617277655

> [!question]- V002 — Secure Hashing Algorithm (SHA)
> generate a cryptographically one-way hash and is published by NIST as a Federal Information Standard  _(Mod 03 p94)_
> Source: [[03-LO05-Cryptographic-Algorithms]] · verified set 617277655

> [!question]- V003 — Digital Signature Algorithm
> It is a Federal Information Processing Standard (FIPS) for digital signatures.  _(Mod 03 p90)_
> Source: [[03-LO05-Cryptographic-Algorithms]] · verified set 617277655

> [!question]- V004 — Network Address Translation (NAT)
> firewall technology helps hide the internal network's configuration and thereby reduces the success of attacks on the network or system. It can act as a firewall filtering technique where it allows only those connections that originate inside a network and can block the connections that originate outside the network.  _(Mod 04 p23)_
> Source: [[04-LO02-Firewall-Technologies]] · verified set 617277655

> [!question]- V005 — Application proxy
> An application-level proxy works as a proxy server. It correlates with the gateway server and separates the enterprise network from the Internet.  _(Mod 04 p20)_
> Source: [[04-LO02-Firewall-Technologies]] · verified set 617277655

> [!question]- V006 — Stateful multi-layer inspection
> These firewalls filter packets at the network layer, determine whether session packets are legitimate, and evaluate the contents of packets at the application layer.  _(Mod 04 p19)_
> Source: [[04-LO02-Firewall-Technologies]] · verified set 617277655

> [!question]- V007 — Firewalk
> is used for reconnaissance purpose where it discovers firewall rules using an IP TTL expiration technique.  _(Mod 04 p62)_
> Source: [[04-LO06-Firewall-Implementation-Deployment]] · verified set 617277655

> [!question]- V008 — Security Reference Monitor (SRM)
> enforces an access control policy (ACL) over the ability of subjects to carry out operations on objects in a system. It is responsible for controlling access of a user to Windows resources.  _(Mod 05 p17)_
> Source: [[05-LO02-Windows-Security-Components]] · verified set 617277655

> [!question]- V009 — Local Security Authority Subsystem (LSASS)
> implements local security policies privileges granted to users and groups, system security auditing settings, user authentication, and sends security audit messages to the event log.  _(Mod 05 p19)_
> Source: [[05-LO02-Windows-Security-Components]] · verified set 617277655

> [!question]- V010 — Security Accounts Manager (SAM)
> is a database that stores the logon credentials of local users and groups. It is a user-mode component that saves the data that is used by LSASS.  _(Mod 05 p21)_
> Source: [[05-LO02-Windows-Security-Components]] · verified set 617277655

> [!question]- V011 — Network logon service (NetLogon)
> a service or a dynamic-link library file that runs continuously in the background. Therefore, it will not stop running unless it is forcibly stopped, or it incurs a runtime error. It can be stopped or restarted using the command-line terminal. It is used for AD logons.  _(Mod 05 p30)_
> Source: [[05-LO02-Windows-Security-Components]] · verified set 617277655

> [!question]- V012 — Windows logon application (WinLogon)
> used when a user wants to login to system locally. It is a user-mode running process and is responsible for managing user authorization sessions. It is activated when the system is turned on and runs in the background  _(Mod 05 p27)_
> Source: [[05-LO02-Windows-Security-Components]] · verified set 617277655

> [!question]- V013 — CPs
> a Windows security component. Credential providers (CPs) are in-process component object model (COM) objects. They run in the LogonUI process and are used to get username and password, smartcard PIN, or biometric data.  _(Mod 05 p29)_
> Source: [[05-LO02-Windows-Security-Components]] · verified set 617277655

> [!question]- V014 — Windows Integrity Control (WIC)
> is an access control mechanism for controlling the interactions between objects based on their integrity or level of trustworthiness.  _(Mod 05 p41)_
> Source: [[05-LO03-Windows-Security-Features]] · verified set 617277655

> [!question]- V015 — Microsoft Windows Defender Credential Guard (WDCG)
> protects login credentials by restricting their interaction with the components of the system. When Credential Guard is enabled, only privileged software can access the credentials.  _(Mod 05 p81)_
> Source: [[05-LO05-Windows-User-Accounts-Password-Management]] · verified set 617277655

> [!question]- V016 — User Account Control (UAC)
> is a key access control enforcement feature in Windows that improves the security of the OS by limiting application software to standard user privileges until an administrator authorizes an elevation  _(Mod 05 p98)_
> Source: [[05-LO07-User-Access-Management]] · verified set 617277655

> [!question]- V017 — Just Enough administration (JEA)
> a security technology used to limit the number of cmdlets or administration privileges of administrator, user, or service accounts.  _(Mod 05 p106)_
> Source: [[05-LO07-User-Access-Management]] · verified set 617277655

> [!question]- V018 — IoT User applications
> These applications help change the behavior of the application controls.  _(Mod 08 p13)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V019 — IoT Control applications
> Control applications send automatic commands and alerts to actuators and helps in investigating problematic cases and enhancing security by identifying security breaches.  _(Mod 08 p12)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V020 — IoT Gateways
> Gateways are devices through which data are transmitted from things to the cloud and vice versa.  _(Mod 08 p11)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V021 — IoT Streaming data processors
> These processors ensure that no data can be lost or corrupted  _(Mod 08 p11)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V022 — IoT Cloud layer
> his layer consists of servers hosted in the cloud that accept, store, and process the sensor data received from IoT gateways.  _(Mod 08 p15)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V023 — IoT Communication layer
> The communication layer includes the components of communication protocols and networks used for connectivity and edge computing.  _(Mod 08 p14)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V024 — IoT Process Layer
> The process layer gathers information and processes the received information. It includes decision making based on the information derived from policies and procedures of IoT computing.  _(Mod 08 p15)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V025 — Device-to-Device model
> In this type of communication, connected devices interact with each other through the Internet but primarily use protocols such as ZigBee, Z-Wave, or Bluetooth.  _(Mod 08 p16)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V026 — Device-to-Cloud model
> In this type of communication, devices communicate with the cloud, rather than directly communicating with the client, to send or receive data or commands.  _(Mod 08 p17)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V027 — Device-to-Gateway model
> In the device-to-gateway communication model, the IoT device communicates with an intermediate device called a gateway, which in turn communicates with a cloud service.  _(Mod 08 p17)_
> Source: [[08-LO02-IoT-Ecosystem-Architecture-and-Communication-Models]] · verified set 617277655

> [!question]- V028 — JTAG
> It is a standard interface to test and debug chips with debugging software to know how a chip respond to multiple commands.  _(Mod 08 p31)_
> Source: [[08-LO03-IoT-Security-Challenges-and-threat-Landscape]] · verified set 617277655

> [!question]- V029 — DigiCert IoT Security Solutions
> It protect private data and home networks while preventing unauthorized access using PKI-based security solutions for consumer IoT devices.  _(Mod 08 p116)_
> Source: [[08-LO06-IoT-Security-Tools-and-Best-Practices]] · verified set 617277655

> [!question]- V030 — AT&T
> AT&T developed The CEO's Guide to Securing the Internet of Things  _(Mod 08 p135)_
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]] · verified set 617277655

> [!question]- V031 — U.S Department of Homeland Security
> U.S DHS developed Strategic Principles for Securing the Internet of Things.  _(Mod 08 p128)_
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]] · verified set 617277655

> [!question]- V032 — ENISA
> ENISA developed 'Baseline Security Recommendations for Internet of Things  _(Mod 08 p135)_
> Source: [[08-LO07-IoT-Security-Standards-Initiatives-and-Efforts]] · verified set 617277655

> [!question]- V033 — Application Patch Management
> Application patch management is the process of ensuring the security of applications on hosts by regularly deploying new or missing patches.  _(Mod 09 p68)_
> Source: [[09-LO03-Application-Patch-Management]] · verified set 617277655

> [!question]- V034 — # setfacl -x u:guest test
> remove all access ACL rules of test file for the guest user.  _(Mod 10 p18)_
> Source: [[10-LO02-Data-Access-Controls]] · verified set 617277655

> [!question]- V035 — # setfacl -m u:user1:rwx test
> set read and write permission in the ACL of test file for the guest.  _(Mod 10 p18)_
> Source: [[10-LO02-Data-Access-Controls]] · verified set 617277655

> [!question]- V036 — # setfacl -m d:o:rx /Testdir
> This command is used to set default ACL for test directory.  _(Mod 10 p18)_
> Source: [[10-LO02-Data-Access-Controls]] · verified set 617277655

