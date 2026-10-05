---
type: note
module: "14"
lo: "06"
tags: [concept, tool, process, mod/14]
topic: "Network behaviour analysis (NBA) and its tools"
exam_weight: unknown
status: done
unresolved:
  - "p92 the McAfee feature list is cut off mid-item: 'External host visibility with detailed host threat' — the text ends there (figure follows). Quoted as printed; no completion supplied."
  - "p98 the Splunk detection-framework list prints 'CIS 20'. Printed verbatim; not identified or corrected."
  - "p96 figure band prints URLs without a scheme ('https://www.broadcom.corn/', 'https://www.cisco.corn/', 'https://www.netscout.com') — OCR garbles of .com; the p96/p97 body sources are used instead."
  - "p96-p98 the Splunk source is printed twice and differently: 'Source: www.splunk.com' in the band and 'splunkbase.splunk.com' in the list. Both recorded, neither chosen."
  - "p93, p95, p97, p98 figures 14.31-14.32 are dashboards — panel labels/values not transcribed (screenshot non-evidence)."
  - "p98 the tool heading prints 'NetWitness Detect Al' (OCR of AI); the body spells out 'artificial intelligence (AI)' on the same page, so AI is used."
---

[[MOC-Module-14]]

# Network Behaviour Analysis and Its Tools (§14.06)

> **LO#06: Understand Network Anomaly Detection with Behavior Analysis** _(Mod 14 p78)_
> Covers pp91–98.

**NBA** (the behaviour-analysis family, as opposed to the *anomaly-detection* framing used earlier in the
LO) — see [[14-LO06a-Network-Anomaly-Detection-and-Baseline-Establishment]]. The NBAD tool list is
[[14-LO06c-DDoS-Detection-NetFlow-Analyzer-and-Additional-NBA-Tools]].

## Network behavior analysis (NBA) _(Mod 14 p91)_

> "Network behavior analysis (NBA) is a **process that collects and analyses the network data of an
> enterprise to identify unusual or malicious activity**."

- Utilises "**advanced analytics, rule-based techniques, and machine learning** to detect suspicious activities."
- Traffic characteristics it studies: **packet size, packet signature, flow duration, response time**.
- Alerts on "potential cyber threats such as **malware infecting the network, DDoS attacks, and other security breaches**."

Four things NBA allows _(Mod 14 p91)_:

| # | Capability |
|---|---|
| 1 | "Tracking and recording **bandwidth and protocol usage patterns**" |
| 2 | "Gathering data about network operations from various sources, employing **machine learning to recognize data patterns**, so **any sudden change suggests the presence of malicious activity**" |
| 3 | "Detecting **new malware and zero-day vulnerabilities** by considering characteristics like **packet size, packet signature, flow duration, and response time**" |
| 4 | "Enhancing **network visibility, network behavior detection, network troubleshooting, threat identification, and mitigation**" |

Notification targets: "**malware taking hold of part of the network and spreading its presence**, unfolding **DoS attacks**, or a **hacker attempting to infiltrate the enterprise network**."

## McAfee Network Threat Behavior Analysis _(Mod 14 p92)_

- An "**integrated component of McAfee Network Security Platform**"; provides "**real-time visibility and threat protection** of the network infrastructure."
- "By **analyzing traffic from switches and routers**, it **pinpoints risky behavior** in the network and effectively **prevents stealthy attacks**."
- Parent platform: helps businesses "identify and block **vulnerability threats across virtual environments, data centers, and both private and public clouds**"; "enables IT teams to **analyze business risks and monitor unusual network behavior through a unified platform**."

| Feature | Detail |
|---|---|
| Malware stop | "Using **real-time emulation of malicious files**, it **stops malware**" |
| Anomaly detection | "includes **zero-day, spam, botnet, and reconnaissance attacks**" |
| Monitoring | "**Monitors and reports unusual network behavior** through network traffic analysis" |
| Integration | "Enhanced security through **integration with McAfee**" |
| Analysis | "**Sorting and analysis of network traffic**" |
| Host visibility | "**External host visibility with detailed host threat**" — list truncated on the page (see `unresolved:`) |

## Flowmon ADS _(Mod 14 p94)_

"Leverages **behavior analysis algorithms** to detect **anomalies concealed within network traffic**, to
expose malicious behaviors, **attacks against mission-critical applications**, **data breaches**, and
**indicators of compromise**."

| Feature | Detail |
|---|---|
| Coverage | "detects the **slightest network anomalies** that indicate the activity of **unknown and insider threats undetectable by perimeter and endpoint security**" |
| Behavior patterns | "Detect **misuse and suspicious behavior of users, devices, and servers**." "Understanding protocols such as **DNS, DHCP, ICMP, and SMTP** can reveal **data exfiltration, reconnaissance, lateral movement**, and other unwanted activities" |
| Attack evidence & analysis | "Understand **every suspicious event in its complexity**. **Context-rich evidence, visualization, network data, or full packet traces for forensics** allow for prompt decisive actions" |
| Prioritization & reporting | "Out-of-the-box **prioritization and severity rules at a global, group, or user level**"; custom dashboards for security, networking, IT helpdesk or managers |
| Advanced action triggering | "Respond to attacks **automatically through script-based integration** with network or authentication tools" — e.g. "**Flowmon can connect to Cisco ISE through pxGrid and quarantine the malicious IP address**" |
| Configuration wizard | Predefined configurations for a variety of network types; **automatically adjusts settings after the initial setup**, then manages false positives |

Integration and false positives _(Mod 14 pp94–95)_: "The ADS can be integrated with **network access
control, authentication, firewall, and other tools for immediate incident response**", and it
"**minimize[s] false positives**."

## Additional Network Behavior Analysis Tools _(Mod 14 pp96–98)_

| Tool | Source as printed | What the page says it does |
|---|---|---|
| **AppNeta Performance Manager** | `https://www.broadcom.com` | "**Network performance monitoring** tool that delivers **visibility into the end-user experience of any application, from any location, at any time**"; identifies the cause of network problems and determines critical traffic "by identifying the **apps running on it**". Features: **active and passive monitoring** ("AppNeta's **4-dimensional monitoring**"), **critical network data collection** "without impacting overhead", **flexible deployment** of **Monitoring Points** |
| **Cisco StealthWatch** | `https://www.cisco.com` | "Outsmart emerging threats in the digital business with industry-leading **machine learning and behavioral modeling provided by Secure Network Analytics (formerly StealthWatch)**". Features: **comprehensive visibility and analytics** — "high-fidelity alerts enriched with context, including **user, device, location, timestamp, and application**"; **speed up incident response** — "unknown malware, insider threats like **data exfiltration, policy violations**"; **simplify network segmentation** — "define smarter segmentation policies without disrupting the business", custom alerts for unauthorized access and compliance |
| **ManageEngine OpManager** | `https://www.manageengine.com` | "**Network monitoring** software offering **deep visibility into the performance of routers, switches, firewalls, load balancers, wireless LAN controllers, servers, VMs, printers, and storage devices**". Features: **network monitoring**; **physical & virtual server monitoring** — "servers up and running at their optimum performance level, **24x7**"; **wireless network monitoring** — "in-depth wireless network stats for access points, wireless routers, switches, Wi-Fi systems" |
| **NetScout Arbor Sightline** | `https://www.netscout.com` | "**DDoS attack detection solution**" offering "powerful features ranging from **network-wide capacity planning** to the identification and management of the mitigation and detection of **DDoS and other threats**". Features: **network peering analysis** — "determine which traffic can transfer off **expensive transit links** to either **free peering** or even become **revenue-generating**"; **network capacity management** — "avoidance of **saturation**" and "**re-engineering** of network traffic"; **threat detection** — "**proactive detection of network or service availability threats**", "quickly diagnose and detect DDoS attacks" |
| **NetWitness Detect AI** | `https://www.netwitness.com` | "**Artificial intelligence (AI) and machine learning (ML)** technologies to enhance threat detection and response"; "collects and analyzes data across **all capture points (logs, packets, NetFlow, endpoint, and IoT)** and computing platforms (**physical, virtual, and cloud**), **enriching the data with threat intelligence and business context**". Features: "innovative, **dynamic statistical risk scoring model** produces **high-fidelity alerts** with meaningful insights"; "**intelligent peer grouping of anomalies** provides additional context"; "**patented unsupervised machine learning and behavioral analytics**" |
| **Splunk** | `splunk.com` / `splunkbase.splunk.com` | "**Data analytics and visualization platform** used for **monitoring, searching, and analyzing machine-generated data, such as logs, events, and metrics**"; collects from "**servers, applications, and devices**", providing "**real-time insights and actionable intelligence**". Features: **advanced threat detection** — "machine learning and **1400+ out-of-the-box detections** for frameworks such as **MITRE ATT&CK, NIST, CIS 20, and Kill Chain**"; **risk-based alerting** — "attribute risk to users and systems, **map alerts to cybersecurity frameworks**, trigger alerts when **risk exceeds thresholds**"; **rapid response security content** — automatic updates from the **Splunk Threat Research Team** |

> Packet-level counterpart to all of this statistical/ML analysis: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]].






