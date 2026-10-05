---
type: note
module: "16"
lo: "08"
tags: [concept, tool, mod/16]
topic: "XDR tools and EDR vs MDR vs XDR comparison"
exam_weight: unknown
status: done
unresolved:
  - "p113-116 Figs 16.34-16.37 Cynet and Log360 dashboards are captures treated as non-evidence, tile numbers and sidebar labels not transcribed"
  - "p117 tool-tile URL OCR garbled (trendrricro, pabaltonetworks, cyberseason, Extra Hop spacing) refused to normalize, URLs omitted except prose Source lines"
  - "p121 figure OCR prints behavior-based anomalies vs body prose behavior-based analytics, body prose form used"
  - "p121 MDR nature row prints packages the assistance of EDR and MDR quoted verbatim, not reconstructed"
---

[[MOC-Module-16]]

# XDR Tools and EDR vs MDR vs XDR (§16.08)

> **LO#08: Understanding incident response using Extended Detection and Response (XDR)** _(Mod 16 p113)_
> Covers pp113–121.

## Cynet auto XDR _(Mod 16 p113)_

- **Autonomous breach protection platform** unifying/automating **monitoring and control, attack prevention and detection, response orchestration** across the environment. `Source: https://www.cynet.com`
- **Cynet 360 leverages AI and ML** to **automatically detect and respond in real time without constant human intervention**.
- Key features: **autonomous threat detection and response**; **unparalleled accuracy and complete attack-surface coverage**; **24/7 expert responders**; **endpoint protection**.

## ManageEngine Log360 _(Mod 16 p115)_

- **Unified SIEM with integrated DLP and CASB**; **detects, prioritizes, investigates, responds**. `Source: https://www.manageengine.com`
- Combines **threat intelligence + ML-based anomaly detection + rule-based attack detection**; **incident management console** for remediation; visibility across **on-premises, cloud, hybrid**.
- Key features: **collect and analyse logs from various sources incl. end-user devices**; **monitor/audit critical Active Directory changes in real time**; **detect security incidents or data breaches**; **incident response**.

## Other XDR tools _(Mod 16 pp117–120)_

| Tool | What the page says it does |
|---|---|
| Trend Micro Vision One (XDR) | Collects/correlates **deep activity data across email, endpoints, servers, cloud workloads, networks** — detection/investigation **difficult or impossible with SIEM, EDR, point solutions** |
| CrowdStrike Falcon (Falcon Insight XDR) | **Unifies third-party data sources across all key attack surfaces** from **one unified XDR command console** |
| SentinelOne Singularity | Brings together **native endpoint, cloud, identity telemetry** + third-party data in a **large data lake**; ingests security data **from any source**, cost-effectively |
| ExtraHop | Integrated best-in-class strategy, **no vendor lock-in**; integrated workflows **natively in ExtraHop Reveal(x) 360**; end-to-end visibility |
| Cortex XDR (Palo Alto) | **Industry-first extended solution**; combines **endpoint, network, cloud** insights to **reduce manual work** |
| Cybereason Cyber Defense Platform | **Unites all endpoints, extends visibility across network infrastructure**; **automated controls, remediation, actionable threat intelligence** |
| Mandiant Advantage (now part of Google) | Platform for **automating security response teams**; **Automated Defense** via data science + ML **triages alerts, scales SOC, investigates 24/7**; known for **IOC research** |
| Sophos Intercept X | Combines **Intercept X Endpoint** with server, firewall, **cloud security posture management**, email data security bundles |
| Microsoft XDR | **Microsoft Defender Advanced Threat Protection**: preventive protection, **post-breach detection, automated investigation and response**; **agentless, cloud-powered, no additional deployment/infrastructure** |
| Bitdefender GravityZone Business Security Enterprise | **Extends EDR analytics and event correlation beyond a single endpoint** for multi-endpoint attacks |

Key features per tool, as printed:

- Trend Micro: **automated IOC searching**; **dynamic risk assessments + automated remediation**; **attack-surface discovery** (internet domains, containers, private business networks); **threat correlation from multiple sources**.
- CrowdStrike: **third-party integrations** via technology alliance partners; **graph explorer showing cross-domain attack patterns**; **behavioral analytics**; **CI/CD pipeline integrations**.
- SentinelOne: **customizable role-based access control**; **MFA integration**; **Skylight data analytics integration** for XDR data visibility.
- ExtraHop: **faster mean time to respond**; **stronger security across entire attack surface**; **less manual data gathering** so analysts focus on priorities.
- Cortex XDR: **insider-threat and credential-attack detection**; **incident scoring and alert categorization**; **automated root-cause analysis**; **identity threat detection and response module**; threat hunting/intel via **PAN Unit 42**, **ML-based behavioral analysis**, streamlined deployment.
- Cybereason: **integrations incl. Okta, Fortinet, Palo Alto, Check Point**; **charts ranking MalOps by severity and status**; **full attack story per MalOp**.
- Mandiant: **dark web monitoring**; **dynamic host and malware views**; **threat-actor data**; **OSINT indicators** for publicized threats.
- Sophos: **highly-reviewed ransomware protection**; **24/7 threat hunting by Sophos analysts**; **command-line option for scripts/config**; **easy-to-understand UI**.
- Microsoft: **email security insights**; **single dashboard for incident management and alert categories**; **automatic self-healing**; **threat hunting with customizable queries**.
- Bitdefender: **visibility beyond managed endpoints** (broad/deep observability); **root-cause analysis**; **single-click response across endpoints**.

Related: [[16-LO08a-XDR-Concept-and-Features]] · [[16-LO07c-EDR-Tools]]

## EDR vs MDR vs XDR — Table 16.1 _(Mod 16 p121)_

| Row | EDR | XDR | MDR |
|---|---|---|---|
| Scope | **Monitors/secures endpoints** on a network | **Monitors/secures endpoints, cloud services, networks** | **Threat hunting, network monitoring, threat detection and response**, ingest analysis and workflows across the network |
| Nature | **A technology** | **A technology, extension of EDR** | **A managed security service**, packages the assistance of EDR and MDR (as printed) |
| Data | **From endpoints** | **From multiple sources** | **From networks, applications, endpoints, cloud services** |
| Detection | **Signature and behavior-based analytics** | **ML and AI associating data from various sources** | **Analytics and human expertise** |
| Response | Automates e.g. **isolating endpoints** | Automates e.g. **blocking (malicious) network connections** | **Usually more automated than EDR/XDR** — third-party vendors manage, greater resources/expertise |

- The three are the **main detection-and-response approaches**; similar but **different security approach**. _(Mod 16 p121)_







