---
type: note
module: "20"
lo: "04"
tags: [process, tool, mod/20]
topic: "TI feed focus areas and providers"
exam_weight: unknown
status: done
unresolved:
  - "p35 truncated: US-CERT entry cuts off at National Protection and Programs Directo... — omitted remainder"
  - "p35 AIS Source line: tile/prose prints Source: www.dhs.gov while body describes DHS AIS — quoted verbatim, no reconciliation"
  - "pp37–39 no Source: lines printed in prose for Recorded Future, Broadcom, Team Cymru, Trellix, Anomali — URLs omitted"
  - "pp37–39 prose names only the five assigned providers; AlienVault, CrowdStrike, Infragard, ISC, Proofpoint, ThreatStop, Talos prose deliberately omitted per assignment"
---
[[MOC-Module-20]]

# TI Feed Focus Areas and Providers (§20.04)

> **LO#04: Understand the different layers of threat intelligence** _(Mod 20 pp32–39)_
> Covers pp32–39. Tile grids and dashboard captures treated as non-evidence; only running prose recorded.

## Focus areas of TI feeds

| Area | What the page says |
|---|---|
| Compromised devices | **External notifications** to a device in **botnet-like activity** or communicating with **known malicious sites and C&Cs**. Ex: **botted nodes, botnet C2 servers**. _(Mod 20 p32)_ |
| Malware indicators | Malware analysis → **intention of malicious code**; technical/behavioral indicators: **memory corruption, stopping current protections, registry changes**. Ex: **IOCs and IOAs of known malicious and blacklisted files**. _(Mod 20 p32)_ |
| IP reputation | **Indicator of maliciousness of an IP**; list of **known bad/suspicious IPs**; spam/virus-origin IPs get bad reputation. _(Mod 20 p32)_ |
| Web reputation | **Security risk of visiting a website**; lets defenders **finely tune security settings**. _(Mod 20 p32)_ |
| C&C networks | **Track global C&C traffic** to identify **malware originators, botnet controllers**, other IPs/sites for monitoring. _(Mod 20 p33)_ |
| Phishing messages | **Isolation and analysis of phishing email** → attackers and tactics. Ex: **email attack campaigns, business email compromise**. _(Mod 20 p33)_ |
| Mobile app reputation | Groups **score apps using multi-stage analysis and advanced algorithms** for **safe and compliant** apps. Ex: **app reputation**. _(Mod 20 p33)_ |

## Free and open-source feed providers

- **Threatfeeds.io** — free, open-source provider of popular free feeds/sources; **lists links for direct downloads and live summaries**. `Source: https://threatfeeds.io`. _(Mod 20 p34)_
- Printed feeds: **IPSpamList** by NoVirusThanks; **Darklist** by Darklist; **SSL BL** by abuse.ch; **C&C Domains** by Bambenek Consulting; **Botvrij.eu – ips / urls** by Botvrij.eu; **Malicious EXE URLs** by NoVirusThanks; **Monero Miner** by Minerchk; **AlienVault IP Reputation** by AlienVault. _(Mod 20 p34)_

## Government feed providers

| Provider | What the page says | Source |
|---|---|---|
| AIS | Free; provided by **US Department of Homeland Security (DHS)**; **exchange of cyber threat indicators between federal government and private sector at machine speed**; indicators = **malicious IP addresses, sender addresses of phishing emails**. _(Mod 20 p35)_ | `www.dhs.gov` |
| DC3 | **Department of Defense Cyber Crime Center**; DoD **center of excellence for digital and multimedia forensics**, under executive agency of **Secretary of the Air Force**; delivers for cybersecurity, infrastructure protection, law enforcement, critical services counterintelligence; **daily context via newsletters and twitter feed**. _(Mod 20 p35)_ | `http://dc3.mil` |
| US-CERT | Organization **within DHS's National Protection and Programs Directo...** [truncated]. _(Mod 20 p35)_ | `https://www.us-cert.gov/` |
| ENISA | **European Union Agency for Network and Information Security**; contributes to **European cybersecurity policy**, supports **member states and EU stakeholders**, aids **responses to cyber incidents** and **Digital Single Market** functioning. _(Mod 20 p36)_ | `https://www.enisa.europa.eu/` |
| FBI Cyber Crime | **Lead US federal agency for investigating cyber-attacks**; enhances **Cyber Division investigative capacity** re **intrusions into government and private networks**; provides **news on latest cases to Congress**. _(Mod 20 p36)_ | `https://www.fbi.gov/` |
| StopThinkConnect | **Global online safety awareness campaign** under **NCSA + APWG**; strives to **make cybersecurity understandable**. _(Mod 20 p36)_ | `www.stopthinkconnect.org` |

## Commercial providers (prose only)

- **RecordedFuture.com** — **Security Control Feeds** give **quality indicators and context needed to automate action**; **operationalizing trusted intelligence**, **automatic detection and blocking of threats**. _(Mod 20 p39)_
- **Broadcom.com** — prominent provider of **comprehensive cybersecurity solutions**; features: **Comprehensive Threat Detection, Endpoint Security, Network Security, IAM Management, Security Analytics**. _(Mod 20 p38)_
- **Team-Cymru.com** — **threat intelligence and insight for security vendors, network defenders, IR teams, analysts**; **query tool for direct access to more than 50 different threat categories**. _(Mod 20 p39)_
- **Trellix.com** — **advanced threat intelligence services for proactive defense**; features: **threat actor/group attribution and TTP analysis**, **TI-driven risk assessments**, **analyst augmentation using multiple sources and tools**, **malware analysis — static or dynamic limited reversing**, **malicious infrastructure analysis**. _(Mod 20 p38)_
- **Anomali.com** — leading provider of **threat intelligence and detection solutions**; features: **Threat Intelligence Feeds, Threat Detection Analysis, Integration with Security Tools, Customizable alerts**. _(Mod 20 p39)_






