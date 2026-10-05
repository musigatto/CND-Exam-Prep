---
type: note
module: "13"
lo: "04"
tags: [tool, bestpractice, mod/13]
topic: "Wireless security assessment tools"
exam_weight: unknown
status: done
unresolved:
  - "p69 the AirMagnet Wi-Fi analyzer coverage is printed as '802.11a\\b\\g\\n and 5 GHz channels'. The separators are literal REVERSE SOLIDUS characters (char 92) in the OCR, not forward slashes, and the source does not confirm which characters are on the page. Quoted verbatim as printed; NOT normalised to 802.11a/b/g/n."
  - "pp68-69 the same product is called 'AirMagnet WiFi Analyzer' in the p68 callout and 'AirMagnet Wi-Fi analyzer' as item 1. Both spellings occur in the source."
  - "p70 the vulnerability-scanning list heads item 8 with 'Nmap' but the description is entirely of Zenmap: 'Zenmap is a multi-platform GUI for the Nmap Security Scanner...'. The heading/description mismatch is in the source; not reassigned to a separate entry."
  - "p70 the source gives no description of Nmap itself in this list, although Nmap is already described on pp62-63 as a wired network scanner. Not cross-filled."
  - "p70 the nexus tool is headed 'Nexpose Community Edition' and the body calls it 'Nexpose'. Quoted as printed."
  - "p70-71 the WiFish Finder description is split across the page break: 'Most Wi-Fi clients keep a memory of' ends p70 and 'networks (SSIDs) that they have connected to in the past' opens p71."
  - "p70 'the attacker's mindset' in the Nexpose entry is a marketing phrase reproduced verbatim; no risk-scoring method, scale or formula is given anywhere in the section."
  - "p68-71 the twelve tools are split across two headings with no stated selection criteria: items 1-7 'can assist a user in assessing wireless security' and items 8-12 are 'Wi-Fi vulnerability scanning tools'. The split does not follow any stated distinction."
---

[[MOC-Module-13]]

# Assessing the Security of a Wireless Network (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers pp68–71 — security measure **11**, *"Assess wireless network security"*.

## Purpose _(Mod 13 p68)_

> **"A wireless security assessment is used for detecting, locating, and mitigating the risks posed by the current configuration of a wireless network."**

- *"A security assessment/testing should be performed to **detect potential vulnerabilities** in the
  wireless network and **mitigate them before attackers can exploit them**."*
- *"A wireless network should be **regularly checked** for possible vulnerabilities. Parameters such
  as **security, performance, and speed** should be considered while performing the assessment."*
- *"**Different security assessment and vulnerability scanning tools** should be used for finding the
  potential vulnerabilities."*

## The assessment checklist _(Mod 13 p68)_

*"The following should be considered in a typical wireless network security assessment:"*

1. Check if a **proper and up-to-date inventory** is being maintained for all wireless network devices
2. Check the **location of APs** to make sure that they are **properly placed**
3. Check if the **wireless antennas are pointing in the right direction**
4. **Discover new wireless devices**
5. **Document all the findings** for new wireless devices
6. If the wireless device found is using a Wi-Fi network, check if it is using **weak encryption**
7. **Create a rogue AP and check if it can be detected**
8. Check if the **SSID is visible or hidden**
9. Check if **MAC filtering has been enabled or not**

## Tools that assist in assessing wireless security (items 1–7) _(Mod 13 pp68–70)_

### 1. AirMagnet Wi-Fi analyzer — `https://www.netally.com`

*"Offers **continuous evaluation** of the wireless channels, devices, speeds, interference issues,
and RF spectrum. It helps to **automatically detect the security threats and wireless network
vulnerabilities**, common wireless performance issues including **throughput issues, connectivity
issues, device conflicts, and signal multipath problems**."*

- *"This tool can detect **Wi-Fi attacks such as DoS attacks, authentication/encryptions attacks,
  network penetration attacks**."*
- *"It can easily **locate unauthorized (rogue) devices or any policy violator**."*
- *"The tool examines `802.11a\b\g\n` and **5 GHz** channels for interference and can be installed in
  **PCs, laptops, tablets**, etc."* _(see `unresolved` for the separator characters)_

### 2. Elcomsoft Wireless Security Auditor — `https://www.elcomsoft.com`

*"Helps in verifying **how secure and busy** a company's wireless network is. The tool **attempts to
break into a secured Wi-Fi network** by **analyzing the wireless environment, sniffing Wi-Fi
traffic**, and **running an attack on the network's WPA/WPA2-PSK password**."*

### 3. WepAttack — `http://wepattack.sourceforge.net`

*"A **WLAN open source Linux tool** for breaking **802.11 WEP keys**. This tool is based on an
**active dictionary attack** that **tests millions of words** to find the right key."*

### 4. Aircrack-ng — `http://www.aircrack-ng.org`

*"A **complete suite of tools** used for assessing Wi-Fi network security. It focuses on different
areas of Wi-Fi security:"*

| Area | What it does _(Mod 13 p69)_ |
|------|-----------------------------|
| **Monitoring** | *"It **captures packets** and **exports data to text files** for further processing by third party tools."* |
| **Attacking** | *"It **replays attacks, de-authentication, fake APs**, and others via **packet injection**."* |
| **Testing** | *"It **checks Wi-Fi cards and driver capabilities** (**capture and injection**)."* |
| **Cracking** | *"**WEP and WPA PSK (WPA 1 and 2)**"* |

### 5. WEPCrack — `http://wepcrack.sourceforge.net`

*"An **open source tool for breaking 802.11 WEP secret keys**. It cracks 802.11 WEP encryption keys
using the **latest discovered weakness of RC4 key scheduling**."*

### 6. WepDecrypt — `http://wepdecrypt.sourceforge.net`

*"**Guesses the WEP keys** based on an **active dictionary attack, key generator, distributed network
attack**, and some other methods."*

### 7. CommView for WiFi — `http://www.tamos.com`

*"**Captures every packet on the air** to display important information such as the **list of APs and
stations, per-node and per-channel statistics, signal strength, a list of packets and network
connections, and the protocol distribution charts**."*

## Wi-Fi vulnerability scanning tools (items 8–12) _(Mod 13 p70)_

*"Wi-Fi vulnerability scanning tools can help a user in **finding weaknesses in the wireless networks
and secures them before attackers actually attack**."*

### 8. Nmap — `http://nmap.org`

*"**Zenmap** is a **multi-platform GUI** for the Nmap Security Scanner, which is useful for **scanning
vulnerabilities on wireless networks**. This tool **saves the vulnerability scans as profiles** to
make them **run repeatedly**. The **results of recent scans are stored in a searchable database**."*

### 9. Nessus — `http://www.tenable.com`

*"A **vulnerability, configuration, and compliance scanner**. It features **high-speed discovery,
configuration auditing, asset profiling, malware detection, sensitive data discovery, patch
management integration**, and vulnerability analysis of a wireless network."*

### 10. Network Security Toolkit — `http://networksecuritytoolkit.org`

*"**Network Security Toolkit (NST)** is a **Fedora-based application** that provides **easy access
to the open source network security applications**. The toolkit includes an **advanced user
interface** for system/network administration, navigation, automation, network monitoring, **host
geolocation**, network analysis and configuration of many network and security applications found
within the NST distribution."*

### 11. Nexpose Community Edition — `http://www.rapid7.com`

*"A **vulnerability management application** that analyzes vulnerabilities, controls, and
configurations in order to find the security risks. It uses **RealContext and RealRisk** features and,
in addition, **the attacker's mindset**, to **prioritize and drive risk reduction**. This tool helps
a user to understand the network and to **prioritize and manage risks effectively**."*

### 12. WiFish Finder — `https://sourceforge.net`

*"A **vulnerability assessment tool** that determines if active Wi-Fi devices are vulnerable to
**'Wi-Fishing' attacks**. A user can perform this assessment via a combination of **passive traffic
sniffing and active probing** techniques."*

- *"Most Wi-Fi clients **keep a memory of networks (SSIDs) that they have connected to in the
  past**."*
- *"**Wi-Fish Finder builds a list of the probed networks** and **determines the security setting of
  each probed network**."*
- **The fishing-target rule:** *"A client is a **fishing target** if it is **actively seeking to
  connect to an OPEN or a WEP network**."* _(Mod 13 p71)_

## Related

- Detecting a planted rogue AP is checklist item 7 — [[13-LO04g-Rogue-Access-Point-Detection]]
- Nmap and Kismet also appear as rogue-AP collection tools — [[13-LO04g-Rogue-Access-Point-Detection]]
- The passphrase rules the crackers go after: [[13-LO04f-Wireless-Monitoring-and-WPA-Cracking]]
- WEP key weaknesses: [[13-LO02a-WEP-Encryption]] · [[13-LO02f-Issues-in-WEP-WPA-and-WPA2]]






