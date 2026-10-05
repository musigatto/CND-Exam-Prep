---
type: note
module: "16"
lo: "07"
tags: [process, threat, tool, mod/16]
topic: "EDR threat detection, investigation, hunting, response and remediation"
exam_weight: unknown
status: done
unresolved:
  - "p93 Figure 16.24 Wazuh dashboard capture treated as non-evidence; no tile labels or values transcribed."
  - "p95 dashboard tile text (e.g. 15710 counts) and Figure 16.25/16.26 captions treated as non-evidence; Source https://learn.microsoft.com is a figure caption, not body prose."
  - "p97 Source printed as https://www.solarwinds.corn/ (sic); kept verbatim, presumed OCR/rendering error for .com."
  - "p98 tool printed as ECR tool (sic); kept verbatim, not normalised to EDR/XDR."
  - "p99 Source printed as https://www.cynet.com with garbled scheme (https with middle-dot); kept as https://www.cynet.com."
  - "p100 Figures 16.27 and 16.28 Cynet dashboard captures treated as non-evidence; no alert values or tile labels transcribed."
---

[[MOC-Module-16]]

# EDR Detection, Investigation, Hunting, Response (§16.07)

> **LO#07: Understand incident response using Endpoint Detection and Response (EDR)** _(Mod 16 p93)_
> Covers pp93–100.

## Threat detection using EDR _(Mod 16 pp93–94)_

- EDR solutions provide **real-time visibility into endpoint activities**, help **identify potential threats early**, and enable a **rapid and targeted response**. _(Mod 16 p93)_
- Help detect **Advanced Persistent Threats (APTs)** and other sophisticated attacks that may **bypass traditional antivirus and firewall defenses**. _(Mod 16 p93)_
- Threat detection = process of **examining and assessing a network or computer system for malicious applications and data**. _(Mod 16 p93)_
- EDR **continuously analyzes user behavior and activities of other devices**; detects **ransomware and malware by identifying abnormal activities**, ensuring **accurate anomaly detection**. _(Mod 16 p93)_
- **Wazuh file integrity monitoring (FIM)** module can be used to **locate malicious files on inspected endpoints**. _(Mod 16 p93)_
- Log gathering: EDR technologies collect logs from **various external malware detection programs**; leveraging **Wazuh robust log-gathering** gives a **comprehensive view of security infrastructure**; Wazuh **systematically collects and verifies logs from multiple malware detection technologies** for analysis. _(Mod 16 p94)_
- Source: `https://www.wazuh.com` _(Mod 16 p93)_

## Incident investigation using EDR _(Mod 16 pp95–96)_

- EDR collects **additional data from the affected endpoint** and identifies the **source and scope of the threat**. _(Mod 16 p95)_
- Incident investigation = meticulous technique/process of investigating an incident to determine its **cause, effects, and other relevant variables**. _(Mod 16 p95)_
- EDR capabilities: **incident data analysis, investigation alert triage, verification of suspicious activities, threat hunting, detection and containment of malicious activities**. _(Mod 16 p95)_
- Investigation process, in printed order: _(Mod 16 p95)_
  1. **Data collection** — gather data from logs of endpoint devices (network connections, user activities).
  2. **Threat detection** — analyze data to uncover anomalies and potential threat indicators.
  3. **Alert generation** — notify the organization's hierarchy about unexpected attacks from unchecked vulnerabilities.
  4. **Incident prioritization** — prioritize threats by **severity and impact**; higher-risk threats first.
  5. **Incident investigation** — analysts use EDR console to identify and examine compromised endpoints.
  6. **Threat hunting** — proactive step to detect hidden threats.
  7. **Threat containment and eradication** — isolate identified threats, prevent further movement.
  8. **Remediation** — **preventive measures applied before potential threats are identified and discovered**; remediate early to prevent high impact. _(Mod 16 p96)_

## Threat hunting using EDR _(Mod 16 pp97–98)_

- EDR performs **proactive threat hunting by searching for IOCs and behavioral anomalies** indicating advanced or hidden threats. _(Mod 16 p97)_
- Threat Hunter **thoroughly examines network activities** down to minute details; persists **until the incident is confirmed harmless**; **real-time monitoring and advanced algorithms** drive effectiveness. _(Mod 16 p97)_
- Source: `https://www.solarwinds.corn/` (sic). _(Mod 16 p97)_
- ECR tool prose (verbatim): provides **graphical representations of spikes in network behavior**, **categorizes events by type**, presents **device connectivity** and **node health status**; improves monitoring, **quick decisions**, resolution of connection issues, network stability. _(Mod 16 p98)_

## Incident response and remediation using EDR _(Mod 16 pp99–100)_

- Assign **severity scores** based on **potential impact and relevance**; prioritize response efforts. _(Mod 16 p99)_
- Generate **alerts and reports** with **affected endpoint, nature of incident, potential impact** for further investigation. _(Mod 16 p99)_
- **Automated response**: **isolating affected endpoint, blocking malicious network traffic, initiating remediation processes**. _(Mod 16 p99)_
- Behavior engines **monitor every phase of an attack in real time**; modern EDR **automatically detects/flags abnormalities** and **provides recommendations**; rogue processes → **promptly shut down affected devices to prevent pivot attacks**; limits impact of successful attack. _(Mod 16 p99)_
- Source: `https://www.cynet.com` _(Mod 16 p99)_
- Cynet prose: **automated end-to-end detection system**, automated cybersecurity platform; alerts **categorized by date, description, scope of attack**; **in-depth investigations for root cause**; **recommendations for further security measures**. _(Mod 16 p100)_

## Links

- [[MOC-Module-16]]
- [[MOC-Module-14]]
- [[MOC-Module-15]]







