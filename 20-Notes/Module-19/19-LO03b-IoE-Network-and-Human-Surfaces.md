---
type: note
module: "19"
lo: "03"
tags: [process, tool, threat, mod/19]
topic: "IoE network and human surfaces"
exam_weight: unknown
status: done
unresolved:
  - "p26 Burp Suite plugin screenshot text garbled in OCR; treated as non-evidence, prose only"
  - "p27 Source prints https://threatmodeler.com in body vs https://threatmodeler.corn/ in figure caption; body form used"
  - "p27 ThreatModeler console and lower dashboard text garbled; not read"
  - "p28 AttackSurfaceMapper CLI help and author lines garbled in OCR; not read; Source line spaced as A ttackSurfoceMapper so URL omitted"
  - "p29 Table 19.1 column mapping flattened by OCR; technique-to-source assignment uncertain, lists reproduced without column claims"
  - "p29 IPv41nfo prints with numeral 1, Sublist3rAPl casing, Archivelt spelling kept as printed"
  - "p30 is Figure 19.7 Automated Attack Surface Mapping only; no body prose, treated as non-evidence"
  - "p31 OhPhish dashboard numbers non-evidence; figure URL https://www_shieldalllance.corn/ garbled, body form www.shieldalliance.com used"
  - "p32 SPF Source prints as bare https://github.com with no repo path; kept as printed"
  - "p33 Phishing Frenzy Source prints as bare www.github.com; kept as printed"
  - "p33 prints hosing websites kept verbatim, likely hosting"
---
[[MOC-Module-19]]

# IoE Network and Human Surfaces (§19.03)

> **LO#03: Learn to identify Indicators of Exposures (IoEs)** _(Mod 19 p18)_
> Covers pp26–33. Application tail (p26 ASD cont'd, p27 ThreatModeler) included here because the source places it on these pages.

See also [[19-LO03a-IoE-System-and-Application-Surfaces]] for IoE definition and system surfaces.

## Application surface cont'd — OWASP ASD capabilities _(Mod 19 p26)_

- **Find the endpoints** of a web application. _(Mod 19 p26)_
- **Perform static code analyses to identify web application endpoints by parsing routes and identifying parameters**; data made available in **OWASP ZAP and Burp Suite to help improve testing coverage**. _(Mod 19 p26)_
- **Find the allowed parameters by the endpoints and the data type of parameters**, including unlinked endpoints and unused optional parameters. _(Mod 19 p26)_
- **Calculate the changes in attack surface between two versions** of an application. _(Mod 19 p26)_
- Available as a **ZAP plugin and PortSwigger BApp Store**, installable directly from within those tools; Burp plugin shows **list of endpoints, endpoint details, and corresponding requests**. Figure 19.5 is a capture — **non-evidence**. _(Mod 19 p26)_

## Application surface — ThreatModeler _(Mod 19 p27)_

- **ThreatModeler is an automated threat modeling software** that assists organizations in **managing their attack surface and avoiding threats**. Source: https://threatmodeler.com _(Mod 19 p27)_
- Allows defining a **communication channel (protocols) between components** and allocates **data elements and widgets (Cookie, Session, Form, or URL)** to these components. _(Mod 19 p27)_
- When the user finishes the component diagram, the **intelligent threat engine automatically recognizes threats and automatically prioritizes them according to risk level**. _(Mod 19 p27)_
- Figure 19.6 console screenshot is a capture — **non-evidence, not read**. _(Mod 19 p27)_

## Network surface — AttackSurfaceMapper _(Mod 19 p28)_

- **AttackSurfaceMapper is a reconnaissance tool using a mixture of open source intelligence and active techniques** that help understand the attack surface. _(Mod 19 p28)_
- Enumerates **subdomains with brute forcing and passive lookups, other IPs of the same network block owner, IPs with multiple domain names pointing to them, and so on**. _(Mod 19 p28)_
- Terminal help output and module list (HostHunter, DNSdumpster, URLScan, LinkedIn, Hunter, Shodan) on p28 are capture text — **non-evidence, not read**. _(Mod 19 p28)_

## Network surface — amass Automated Attack Surface Mapping _(Mod 19 p29)_

- **The OWASP Amass Project is a cybersecurity tool for gathering information on the attack surface of targets in multiple dimensions**. Source: https://github.com/OWASP/Amass _(Mod 19 p29)_
- Allows **network mapping of the attack surface** and **external asset discovery by collecting open-source information and using reconnaissance techniques (OSINT Reconnaissance)**. _(Mod 19 p29)_
- Information gathering techniques listed include **Domain Name System (DNS), Scraping Certificates, Application Program Interfaces (APIs), Web Archives** (Table 19.1 headings as linearized). _(Mod 19 p29)_
- Listed techniques and sources, kept as printed: **Basic enumeration, Brute forcing (optional), Reverse DNS sweeping, Subdomain name alterations or permutations, Zone transfers (optional)**; **Ask, Baidu, Bing, DNSDumpster, DNSTable, Dogpile, Exalead, Google, HackerOne, IPv41nfo, Netcraft, PTRArchive, Riddler, SiteDossier, ViewDNS, Yahoo**; **Active pulls (optional), Censys, CertSpotter, Crtsh, Entrust, GoogleCT**; **AlienVault, BinaryEdge, BufferOver, CIRCL, CommonCrawl, DNSDB, GitHub, HackerTarget, Mnemonic, NetworksDB, PassiveTotal, Pastebin, RADb, Robtex, SecurityTrails, ShadowServer, Shodan, Spyse (CertDB and FindSubdomains), Sublist3rAPl, TeamCymru, ThreatCrowd, Twitter, Umbrella, URLScan, VirusTotal, WhoisXML**; **Archivelt, ArchiveToday, Arquivo, LoCArchive, OpenUKArchive, UKGovArchive, Wayback**. _(Mod 19 p29)_
- Figure 19.7 on p30 is a mapping capture — **non-evidence**. _(Mod 19 p30)_

## Human surface — phishing frameworks _(Mod 19 pp31–33)_

- To identify and evaluate the **human attack surface, use phishing frameworks to identify IoEs related to human behavior**. Run a phishing campaign using frameworks such as **OhPhish** to evaluate it. _(Mod 19 p31)_
- Phishing frameworks help fight phishing and social-engineering attacks by enabling users to do: **continuous simulation and training on latest attack techniques · recognizing subtle clues · stopping email fraud · stopping data loss and brand damage**. _(Mod 19 p31)_
- **OhPhish** is a phishing simulation framework that **mitigates risks involving human error**; combines **simulated phishing attacks with set-and-go training modules**, enhances awareness, changes user behavior, mitigates social engineering risk. Key features: **simple user-friendly solution, extensive reports, predefined templates, theme-based campaigns, trend monitoring, analytics**. Source: www.shieldalliance.com _(Mod 19 p31)_

| Framework | What the page says it does. Source as printed _(Mod 19 pp32–33)_ |
|---|---|
| SpeedPhish Framework (SPF) | Python tool for quick reconnaissance and deployment of simple social engineering phishing exercises. Source: https://github.com _(Mod 19 p32)_ |
| SoSafe | Training and simulation platform; employees identify and report phishing attempts; builds security culture and mitigates phishing risk. https://sosafe-awareness.com/ _(Mod 19 p32)_ |
| Social-Engineer Toolkit (SET) | Open-source Python tool targeting penetration testing around social engineering; custom attack vectors to make a legitimate attack quickly; built-in attacks targetable against a person or organization during pentesting. Source: www.trustedsec.com _(Mod 19 pp32–33)_ |
| PhishGrid | Simulations helping workforce understand, detect and neutralize threats; lower response time; active defenders with safer behaviors; smart reporting tools. Source: https://one.phishgrid.com/ _(Mod 19 p32)_ |
| Phishing Frenzy | Open-Source Ruby on Rails email phishing framework; manage multiple complex campaigns; campaign management, template reuse, statistical generation; works by sending emails, hosing websites, and tracking analytics. Source: www.github.com _(Mod 19 p33)_ |
| GoPhish | Open-source phishing framework to test exposure to phishing; set templates and targets, launch campaigns, track results. Source: www.getgophish.com _(Mod 19 p33)_ |

- OhPhish dashboard (p31) and OhPhish build screen Figure 19.8 (p32) are captures — **non-evidence, not read**. _(Mod 19 pp31–32)_







