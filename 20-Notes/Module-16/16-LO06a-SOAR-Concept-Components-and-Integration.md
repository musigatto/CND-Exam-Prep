---
type: note
module: "16"
lo: "06"
tags: [concept, process, tool, mod/16]
topic: "SOAR concept, components and security-tool integration"
exam_weight: unknown
status: done
unresolved:
  - "p64 Figure 16.8 capabilities diagram is tile labels only - treated as non-evidence, omitted."
  - "p66 Figure 16.9 components diagram is tile labels only - treated as non-evidence, omitted."
  - "p67 Splunk SOAR playbook/action statistics dashboard is a GUI capture - treated as non-evidence, no numbers transcribed."
  - "p67 prints 'Source: https://www.splunk.corn/' - '.corn' is OCR garble, quoted verbatim here, URL omitted from body."
  - "p66 body prints 'case mangement' [sic] - preserved verbatim in body."
  - "p63 diagram-label OCR 'Security operatioty eutomation' is garbled layout text - non-evidence, omitted."
---

[[MOC-Module-16]]

# SOAR Concept, Components and Integration (§16.06)

> **LO#06: Understand incident response using SOAR** _(Mod 16 p3)_
> Covers pp62–67. Follows [[16-LO05b-AI-ML-Analysis-Response-and-Solutions]] (SOAR as an AI/ML solution); automation/playbooks continue in `16-LO06b`.

## What is SOAR _(Mod 16 pp62–63)_

- **Security Orchestration, Automation, and Response (SOAR)** — integrates **orchestration, automation and response** into one framework for **faster, more effective** response.
- Combines **people, processes, and technology**; collects and **aggregates huge amounts of security data and alerts** from various sources.
- Streamlines **alert triage**, keeps security tools working together; reduces **mean time to detect** and **mean time to respond**.

## Three core capabilities _(Mod 16 p63)_

| Capability | What the page says it does |
|---|---|
| Threat and vulnerability management | Supports vulnerability remediation via **formalized workflow, collaboration, reporting** |
| Security operations automation | Automates low-level ops — **event enrichment, alert prioritization**; AI-driven SOAR **recommends future security measures** |
| Security incident response | **Centralized console** — investigate and resolve **without switching tools**; SOAR data pinpoints **previously undetected ongoing threats** to focus threat hunting |

## Components of SOAR _(Mod 16 pp65–66)_

| Component | Prose function |
|---|---|
| Threat Intelligence | **Ingests and analyses data**; correlated to identify **attack patterns, threats, incidents**; feeds **prioritized by impact and severity** |
| Security Orchestration | **Connects and integrates disparate tools** via built-in/custom integrations and **application programming interfaces**; centralizes info, eliminates sharing inefficiency |
| Security Automation | Replaces manual processes — **log analysis, red-flag detection, anomaly detection**, centralized data-sharing; AI/ML on **previous trends and behavioral patterns**; protects **integrity and confidentiality** |
| Security Incident Response | **Single-view dashboard** to plan, manage, monitor, report mitigation; correlates warnings into the bigger picture; suggests **post-response activities** (`case mangement`, reporting) [sic] |

## Integration with security tools _(Mod 16 p67)_

- Integrates with **SIEMs, firewalls, IDS, endpoint security solutions, threat intelligence feeds, ticketing systems** for **data sharing and coordination**.
- Full prose list: **vulnerability scanners, SIEM, UEBA, IDS, IPS, endpoint security software, external threat intelligence feeds, firewalls, EDR, other third-party sources**.
- Channels efficiency into workflows to **detect, prioritize, eliminate** threats over secured communication channels; pick technology giving an overview of **data, playbooks, tool connections, ROI**.





