---
type: note
module: "20"
lo: "04"
tags: [concept, process, mod/20]
topic: "TI layers, providers and sources"
exam_weight: unknown
status: done
unresolved:
  - "p26 figure vs prose: p25 says four layers; Figure 20.3 tiles read Providers / TI Sources / TI Feeds / TI Platforms / TI Professional Services — prose defines the four as sources, feeds, platforms, professional services with provider as deliverer"
  - "p27 truncated: Internal Intelligence definition cuts off at well aware..."
  - "p28 truncated: defensive counterintelligence definition cuts off at use of the intelli..."
  - "p29 garbled: Exploit Database URL printed as https://www.exp/oit-db.com — quoted verbatim"
  - "p29 duplicate/variant: OxOOsec vs 0x00sec both printed with https://OxOOsec.org/ — quoted verbatim"
  - "p30 truncated: Finance factor cuts off at Finance: Wh... — omitted"
---
[[MOC-Module-20]]

# TI Layers, Providers and Sources (§20.04)

> **LO#04: Understand the different layers of threat intelligence** _(Mod 20 pp25–31)_
> Covers pp25–31.

## Layers of TI

- **TI comprises four layers** — allow orgs to **use threat data to identify malicious activity** in a network. _(Mod 20 p25)_
- Four layers as **sources, feeds, platforms, and professional services**. _(Mod 20 p26)_
- **Provider** = open-source community, movement, private body, or commercial body that **provides TI as sources, feeds, platforms, and professional services**. _(Mod 20 p26)_
- Providers **categorized by way they deliver/organize threat content**; a provider supplies **few or all four layers**. _(Mod 20 p26)_
- TI provided by **commercial providers, government institutes, independent research bodies**. _(Mod 20 p26)_

## TI sources

- **Source = raw data** from **openly available, internal, or commercial** sources; **parsed, analyzed, packaged** to create an intelligence feed. _(Mod 20 p27)_
- Efficient strategy = **relevant, minimal sources**; keep a source only if it (1) **helps long-term intelligence strategy**, (2) is **relevant to the plan** — avoid the rest. _(Mod 20 p27)_
- Typical sources: **vendors and the public sector**; types: **Internal, OSINT, Counterintelligence, HUMINT**. _(Mod 20 p27)_

| Source | What the page says |
|---|---|
| Internal | Employees **well aware** of handling/responding to incidents → good source on **internal threats and incidents**; also **SIEM tools, IOCs, honeypots**. _(Mod 20 pp27–28)_ |
| OSINT | **Easiest** way; gathering from **open/publicly available sources** (newspapers, TV, SNSs, blogs; even day-to-day activities); **in-depth understanding at low cost**. OSINT sources: **daily newspapers, magazines, TV, radio**; **search engines, blogs, forums, social networks**. _(Mod 20 p28)_ |
| Counterintelligence | Gathering for **protection against espionage**; designed to **mislead attacker** and **acquire info about attacker**; **offensive** = attack the attacker on receiving compromise intelligence; **defensive** = use of the intelli... [truncated]. _(Mod 20 p28)_ |
| HUMINT | Listed as typical source; **no prose definition in slice** — refused. _(Mod 20 p27)_ |

## OSINT via hacking forums (example)

- Forums reveal **methods to launch an attack**, **techniques/tools**, **procedures for covering tracks**; plus **tools, hacking procedures, stolen data, new vulns, patches, cyberattack/exploit news**. _(Mod 20 p29)_
- Defenders browse them to **identify emerging threats** and **implement protection techniques**. _(Mod 20 p29)_
- Printed forums: **Hack Forums** (`https://hackforums.net`), **Hackaday** (`https://hackaday.com`), **The Ethical Hacker Network** (`https://www.ethicalhacker.net`), **Hack This Site** (`https://www.hackthissite.org`), **Hak5 Forums** (`https://forums.hak5.org`), **OxOOsec / 0x00sec** (`https://OxOOsec.org/`), **Hack In The Box** (`http://www.hitb.org`), **The Hacker News** (`https://thehackernews.com`), **Exploit Database** (`https://www.exp/oit-db.com` [garbled, verbatim]), **Packet Storm** (`https://packetstormsecurity.com`). _(Mod 20 p29)_

## TI feeds — definition and uses

- **TI feeds = continuous streams / packaged collection** from different sources re **potential or current threats**; mostly **domains, malicious IPs, botnet activity**; **actionable**, implemented **with technical controls**. _(Mod 20 p30)_
- Uses: **couple feeds to security tools** (e.g. **blocking bad IPs after feeds accepted by some firewalls**); **generate alerts** (**SIEM + UEBA correlate feed data with internal events**); **manual review** if relevant to posture. _(Mod 20 p30)_
- Know **feed requirements first**; assess **network infrastructure** (how it looks), **current security posture** (unique risks), **Finance** [truncated]. _(Mod 20 p30)_

## Feed sources: public vs commercial

- **Publicly available**: on the Internet (**open source, social listing, OSINT**). Free list: **SHODAN, Threat Connect, Virus Total, AlienVaults Open Threat Exchange (OTX), Zeus Tracker, The dark web**. _(Mod 20 pp30–31)_
- **Commercial**: org **must purchase** (**government, commercial vendors**). Printed vendors: **Microsoft Cyber Trust Blog, SecureWorks Blog, Kaspersky Blog**. _(Mod 20 pp30–31)_






