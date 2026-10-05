---
type: note
module: "14"
lo: "06"
tags: [tool, threat, concept, mod/14]
topic: "DDoS detection, NetFlow Analyzer, and additional NBAD tools"
exam_weight: unknown
status: done
unresolved:
  - "p88 is a single screenshot page (figure 14.30, 'Example DDoS Attack Detection', NetFlow Analyzer LocalDemo). Its OCR is unintelligible console/dashboard garbage ('WTC NCM rcp IOS TCPRst inva4d TOS F Iow Excess East Alarms Maps Reguts') — treated as screenshot non-evidence, nothing transcribed."
  - "p87 the NetFlow Analyzer figure band prints 'Source: www.manageengine.com' (no scheme) while p89 prints 'Source: https://www.manageengine.com/'. p89 form used."
  - "p89-p90 the additional-tools list is printed as name + URL pairs; the URLs are reproduced exactly as printed, including 'https://cybersecurity.att.com' for AlienVault OSSIM."
---

[[MOC-Module-14]]

# DDoS Detection, NetFlow Analyzer, and Additional NBA Tools (§14.06)

> **LO#06: Understand Network Anomaly Detection with Behavior Analysis** _(Mod 14 p78)_
> Covers pp87–90.

Attack-shaped companion to [[14-LO06b-Behaviour-Detection-Tools-Awake-Cisco-Ransomware-Compromised]].
General NBA (as opposed to NBAD) and its tool list: [[14-LO06d-Network-Behaviour-Analysis-and-Its-Tools]].

## DDoS attack detection using NADBA _(Mod 14 p87)_

- "A DDoS attack can be detected by **monitoring the network traffic of an environment**."
- Tell: "a **sudden spike in the flow of incoming requests, exceeding what is normally expected**. Such a spike is considered **abnormal or unconventional**."
- Effect: "A **rapid influx of connection requests can overwhelm the server, leading to reduced response times**."
- Side effect: "**Security systems and devices may lose their internet connection** under such circumstances."
- Detection window: "Detecting them **at early stages might mitigate the attack**."
- Countermeasures the page names: "frequently execute **traffic filtering and redirection** methods. **Subnetting on a large scale can channel the requests to different network devices**."
- Outcome chain: "Devices might **lose critical resources** due to such unconventional behaviors and drastic spikes in statistics. This also **reduces the system's performance**, which might eventually lead to the **successful execution of a DDoS attack**."

Also monitor "**user login activity, device access to critical resources, and system performance metrics**" for DDoS-indicative patterns _(Mod 14 p87)_.

## Example tool for detecting DDoS attacks — NetFlow Analyzer _(Mod 14 p87)_

- "**Security module** is designed to **detect and analyze network security threats and anomalies**."
- Engine: "**Continuous Stream Mining Engine™** technology for **pattern matching and event correlation across multiple events**, thereby **sensing attacks before they can compromise the entire network**."
- "Capable of detecting **junk or anomalous traffic** and classifies it into **four problem classes** based on predefined algorithms":

| # | Problem class |
|---|---|
| 1 | **Suspect flows** |
| 2 | **Bad source or destination** |
| 3 | **DDoS attacks** |
| 4 | **Scans/probes** |

> p88 is the worked capture (figure 14.30) — screenshot only, no readable body text; nothing taken from it.

## Additional Network Behavioral Anomaly Detection Tools _(Mod 14 pp89–90)_

| Tool | Source as printed | What the page says it does |
|---|---|---|
| **InsightlDR** | `https://www.rapid7.com/` | Equipped with a **network sensor**, giving "visibility and network detection for **critical assets and data at rest**"; includes **lightweight tools that aid in detecting suspicious activities and policy modifications**; enhances security through an **IDS** that monitors malicious traffic, and the IDS data is **accessible on the details page** |
| **Progress Flowmon** | `https://www.flowmon.com/` | "Detection engine leverages **behavioral algorithms** to identify potential **anomalies embedded in the network**, exposing threats and enabling their mitigation"; helps the network "**recognize indicators of compromise and vulnerabilities**"; "adds a **network-centric layer** to the environment" |
| **ManageEngine NetFlow Analyzer** | `https://www.manageengine.com/` | "**Traffic analysis tool**"; enhances visibility of critical assets and offers "a **detection mechanism for the network's bandwidth utilization**"; can "**optimize various traffic patterns**"; "collects records of activities in the network, monitors them, and then **analyzes and reports on who is controlling and using the network bandwidth**" |
| **NETWITNESS** | `https://www.netwitness.com/` | "Designed to **enhance threat detection and response**"; "**monitors, collects, and analyzes data across all access points**"; lets analysts "**select and prioritize, respond to, and reconstruct plans for investigating threats**" |
| **AlienVault OSSIM** | `https://cybersecurity.att.com` | "**Open-source security information and event management (SIEM)** tool" offering features for "**gathering, normalizing, and correlating events**"; "developed in response to the **scarcity of open-source products** in the market and to address a **common challenge faced by many security professionals**"; enhances security visibility |
| **GURUCUL ML XDR** | `https://gurucul.com/` | "**Traffic analyzer tool** that provides **visibility into unknown and undetected network traffic threats based on the network's anomalous behavior**"; uses "**machine learning-based network traffic analyzer entities** to create **behavior baselines for every device and machine**"; baselines are based on **network flow data such as source and destination IPs/machines, protocol, bytes in/out** |
| **IBM QRadar Network Insights** | `https://www.ibm.com/` | "Aids in identifying **suspicious activity that coincides with regular traffic**" and "**extracts content** to enhance visibility into network threat activity"; conducts "comprehensive analyses of both **network metadata and application content**"; "integrates seamlessly with **conventional data sources and threat intelligence**" |
| **ZABBIX** | `https://www.zabbix.com/` | "Monitors **network hardware**, collects, analyzes, and responds to **network traffic metrics**"; "includes **numerous parameters to monitor the health of devices**" |






