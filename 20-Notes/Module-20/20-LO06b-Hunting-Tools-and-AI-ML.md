---
type: note
module: "20"
lo: "06"
tags: [process, tool, mod/20]
topic: "Hunting tools and AI/ML enhancement"
exam_weight: unknown
status: done
unresolved:
  - "p71 header prints 'CrowdStrike Falcono' and 'Trend Micro Managed )(DR'; prose forms used, tile forms quoted verbatim"
  - "p72 prints both 'Cynet 369' and 'Cynet 360'; kept as printed, not reconciled"
  - "p72 YARA prose Source prints garbled 'www.www.ka/i.org'; quoted verbatim"
  - "p73 Log360 prints both 'https://www.manageengine.com' and garbled 'www.managengine.com' / 'MangeEngine'; quoted verbatim"
  - "p71 OCR prints 'Mantix4'; kept as printed"
---
[[MOC-Module-20]]

# Hunting Tools and AI/ML Enhancement (§20.06)

> **LO#06: Understand threat hunting** _(Mod 20 pp71–74)_
> Covers pp71–74. Dashboards on pp71–73 treated as non-evidence; prose below only.

## Hunting platforms and tools _(Mod 20 pp71–72)_

| Tool (as printed) | What the page says it does | Prose Source (as printed) |
|---|---|---|
| CrowdStrike Falcon OverWatch | Leverages **real-time indicators of attack, threat intelligence on evolving adversary tradecraft and enriched telemetry** to deliver detections, **automated protection and remediation, elite threat hunting and prioritized observability of vulnerabilities** — all through a **single, lightweight agent** | Source: `www.crowdstrike.com` |
| Trend Micro Managed XDR | Offers **24/7 analysis and monitoring**; correlates **email, endpoint, server, cloud, workload, and network sources** for stronger detection and insight into **attack source and spread**; **cross-layered detection and response service** | Source: `www.trendmicro.com` |
| Mantix4 | Cyber Threat Hunting Platform, originally developed by a team of **defense intelligence, cybersecurity, and military experts**; meshes **critical human intuition and analysis with advanced machine learning** to proactively and persistently **hunt, disrupt and neutralize** dangerous threats | Source: `www.mantix4.com` |
| VMware Carbon Black EDR | **Incident response and threat hunting solution** for SOC teams with **offline environments or on-premises requirements**; **continuously records and stores endpoint activity data**; hunt threats in **real-time and visualize the complete attack kill chain**, using the **VMware Carbon Black Cloud's aggregated threat intelligence** | Source: `www.vmware.com` |
| Exabeam Fusion | **Cloud-native SIEM and New-Scale SIEM**; unites cloud-native data storage, **rapid data ingestion, hyper-quick query performance, powerful behavioral analytics, and automation** | Source: `www.exabeam.com` |
| Cynet 369 | **Scan endpoints on demand, according to known IOCs**; discovers **files saved on the host even if not opened** — as opposed to continuous scanning of **running processes** that Cynet 360 performs | Source: `www.cynet.com` |
| YARA | Helps **malware researchers identify and classify malware samples**; create **descriptions of malware families based on textual or binary patterns** in samples | Source: `www.www.ka/i.org` (garbled as printed) |
| Maltego | **Fight fraud, abuse and insider threat**; no in-house maintenance, development and deprecation risk | Source: `www.maltego.com` |

Header tile URLs on p71–72 (`crowdstrike.com`, `trendmicro.com`, `mantix4.com`, `vmware.com`, `exabeam.com`, `cynet.com`, `kali.org`, `maltego.com`) not read as evidence beyond the prose Sources above. See also [[20-LO07a-AI-ML-for-Threat-Intel]] for AI/ML uses in TI.

## Threat hunting with ManageEngine Log360 _(Mod 20 p73)_

- Log360 is a **SIEM solution** with a **robust correlation engine** for **real-time aggregation of diverse network events**, enabling identification and validation of potential threats. _(Mod 20 p73)_
- Finds **malicious actors and hidden attacks that slipped through initial defenses** via **advanced threat analytics**; **high-speed, flexible SQL search over the entire log bucket in seconds**; **notifies when threat patterns repeat**. _(Mod 20 p73)_
- Prose Sources as printed: Source: `https://www.manageengine.com` and Source: `www.managengine.com` (with `MangeEngine Log360` spelling as printed). _(Mod 20 p73)_
- Figure 20.12 capture treated as non-evidence; no values read out. _(Mod 20 p73)_

## Enhance threat hunting using AI/ML _(Mod 20 p74)_

1. **Analyze immense amounts of information; identify patterns and anomalies** that may indicate threats. _(Mod 20 p74)_
2. **ML-powered hunting** analyzes **system logs, user behavior, and network traffic**. _(Mod 20 p74)_
3. **Prioritize and triage by impact, urgency, or severity**; generate **recommendations for response and actionable insights**. _(Mod 20 p74)_
- Techniques named: **anomaly detection, pattern recognition, natural language processing, and behavioral analysis**; find and categorize **malicious activities, events, or IOCs that differ from usual behavior**; **extract and correlate data** from feeds, logs, behaviors, traffic, alerts. _(Mod 20 p74)_






