---
type: note
module: "16"
lo: "05"
tags: [concept, process, mod/16]
topic: "role of AI/ML in incident response, detection, triage"
exam_weight: unknown
status: done
unresolved:
  - "p52 OCR prints AI as Al (lowercase L) and I/ML — rendered as AI/ML where surrounding prose makes it unambiguous"
  - "p53 figure-tile OCR spacing noise (algorithmscan, compromiseddevices, maliciouslP) — clean body-prose forms used"
  - "p55 Source URL printed as www.dynatrace.corn — quoted verbatim, likely OCR noise for .com"
  - "p56 Dynatrace business-impact dashboard is fully garbled GUI capture — no numbers, tiles, or graph values transcribed; only Figure 16.5 caption recorded"
  - "p57 BigPanda algorithmic-correlation panel is a product screenshot — non-evidence; only the prose triage claims and the printed Source line recorded"
---

[[MOC-Module-16]]

# AI/ML Role in IR: Detection and Triage (§16.05)

> **LO#05: Enhance incident response using AI/ML** _(Mod 16 p52)_
> Covers pp52–57. Triage baseline precedes this: [[16-LO04b-Triage-Classification-and-Notification]].

## Role of AI/ML in incident response

- AI/ML lets organizations **detect, respond to, and recover more effectively and efficiently**; vs manual methods: **faster, less susceptible to human error**. Resilience via **automated analysis, predictive insights, continuous learning**. _(Mod 16 pp52–53)_
- Four roles, in printed order: _(Mod 16 pp53–54)_
  | Role | What the page says it does |
  |---|---|
  | **Proactive defense** | Analyze **historical security and threat-intelligence data** to identify attack patterns; proactive steps: **software upgrades, vulnerability patching, access-control rule updates** |
  | **Incident triage** | Consider **severity, potential impact, relevance**; categorize via incident attributes, historical and contextual data; **prioritize alerts by risk and urgency**, cut **false-positive noise**, critical alerts first, optimize resource allocation |
  | **Automated analysis** | Streamline investigations over **log data, system events, network traffic**; process **threat-intelligence from various sources**; correlate TI with internal activity to spot **known threats, vulnerabilities, IOCs**; understand attack vectors, set preventive measures |
  | **Autonomous response** | Automate: **isolate compromised devices, block malicious IP addresses, implement security patches, disable compromised user accounts, initiate remediation** — less manual effort, shorter response times, **reduced response mean time** |

## Enhancing detection with AI/ML

- ML algorithms **analyze large volumes of data in real time**, detecting **patterns and anomalies** indicative of threats; systems **adapt by continuously updating models and detection methods**, learning from new data to catch **emerging-threat patterns and behaviors**. Anomaly detection **through root cause analysis** strengthens this further. _(Mod 16 p55)_
- Automated root-cause analysis figure carries `Source: www.dynatrace.corn` (spelling as printed); the p56 business-impact dashboard (affected service calls, baselines, failure rates) is GUI non-evidence — only the caption recorded: **Figure 16.5: Automated Root Cause Analysis using Dynatrace**. _(Mod 16 pp55–56)_

## Enhancing triage with AI/ML

- Implement **AI/ML-driven automated processes** (data analysis + ML models) to **determine severity and criticality**; **prioritize by risk and urgency** so the most critical incidents go first while cutting **false positives and alert fatigue**. _(Mod 16 p57)_
- Structured, standardized evaluation: identify **vulnerabilities and threats to critical security infrastructure**; **severe vulnerabilities first**; fewer false alarms and operational disruptions; better **real-world detection decision-making**; **cost-effective — manual operations only when necessary**. _(Mod 16 p57)_
- Triage-technology panel printed as `Source: www.bigpanda.io` (BigPanda Algorithmic Correlation) — screenshot non-evidence, source line only. _(Mod 16 p57)_





