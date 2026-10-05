---
type: note
module: "16"
lo: "07"
tags: [tool, concept, mod/16]
topic: "EDR tools: Cybereason, NetWitness, Falcon, Huntress, Bitdefender"
exam_weight: unknown
status: done
unresolved:
  - "p101 dashboard tile numbers (e.g. 51/66, 194, 29/43) treated as non-evidence; not transcribed."
  - "p102 Figures 16.29 and 16.30 Cybereason dashboard captures treated as non-evidence; garbled tile OCR not transcribed."
  - "p104 Figures 16.31 and 16.32 RSA NetWitness dashboard captures treated as non-evidence."
  - "p105 tool-list URLs kept verbatim as printed: https://go.crowdstrike.com, https://www.matwarebytes.com (sic), https://www.paloanonetworks.com (sic), https://www.huntress.com, www.broadcom.com, https://www.coro.net, https://www.bitdefender.com (bullet prints middle-dot in scheme)."
  - "p106 CrowdStrike key feature printed as Managed selection and response (sic); kept verbatim."
  - "p107 Coro key features print Al-driven and Al automation (sic, Al with lowercase L); kept as AI only in prose quotation where unambiguous, original form noted here."
---

[[MOC-Module-16]]

# EDR Tools (§16.07)

> **LO#07: Understand incident response using Endpoint Detection and Response (EDR)** _(Mod 16 p101)_
> Covers pp101–108. Prose names and `Source:` URLs only; all dashboard captures are non-evidence.

## Cybereason _(Mod 16 pp101–102)_

- Source: `https://www.cybereason.com` _(Mod 16 p101)_
- Integrated endpoint security tool to **detect, contain, investigate, and eliminate** hostile threats **higher in the cyber kill chain**. _(Mod 16 p101)_
- Operates as a **proactive cyber investigator and resolver**, auditing incidents on endpoints **across all operating systems**. _(Mod 16 p101)_
- Key features (prose): **threat intelligence, instant remediation, rapid detection with high accuracy, ML-powered correlation of malicious behaviors**. _(Mod 16 p101)_
- p102 is Figures 16.29–16.30 dashboard captures = non-evidence. _(Mod 16 p102)_

## RSA NetWitness Endpoint _(Mod 16 pp103–104)_

- Source: `https://www.netwitness.com` _(Mod 16 p103)_
- Continuous monitoring of endpoints **on and off the network**; deep visibility into security state; **prioritizes alerts when there is an issue**. _(Mod 16 p103)_
- Gives teams data for **attack scope understanding and forensic investigations**; **minimizes dwell time** via swift **root cause analysis** and threat prioritization. _(Mod 16 p103)_
- Detects endpoint threats **even those missed by other solutions** via **unmatched real-time visibility** across connected and disconnected endpoints. _(Mod 16 p103)_
- Simplifies collection via **endpoint inventory scans** with **Microsoft Windows log forwarding and filtering**. _(Mod 16 p103)_
- p104 is Figures 16.31–16.32 dashboard captures = non-evidence. _(Mod 16 p104)_

## Tool list and Sophos _(Mod 16 p105)_

| Tool (as printed) | Source (as printed) |
|---|---|
| Sophos Intercept X Endpoint | `https://www.sophos.com` |
| CrowdStrike Falcon | `https://go.crowdstrike.com` |
| Malwarebytes | `https://www.matwarebytes.com` (sic) |
| Cortex XDR | `https://www.paloanonetworks.com` (sic) |
| Huntress | `https://www.huntress.com` |
| Symantec Endpoint Protection | `www.broadcom.com` |
| Coro Endpoint Security | `https://www.coro.net` |
| Bitdefender | `https://www.bitdefender.com` |

- Sophos Intercept X Endpoint: protection against **advanced attacks**; provides **EDR and XDR** to **search, investigate, respond** to suspicious activity and indicators. _(Mod 16 p105)_
- Sophos key features: **web protection** (blocks phishing/malicious sites), **anti-exploitation**, **threat exposure reduction**, **account health check**, **adaptive attack protection** (heightened defenses when attacked), **critical attack warning** (adversary activity across multiple endpoints/servers). _(Mod 16 p105)_

## CrowdStrike, Malwarebytes, Cortex XDR _(Mod 16 p106)_

- CrowdStrike Falcon Insight — Source: `https://www.crowdstrike.com/` — comprehensive EDR for **continuous monitoring of all endpoint activities**; **real-time analysis** to automatically identify and respond. _(Mod 16 p106)_
- Key features: **real-time monitoring, forensic capabilities, risk-based vulnerability management, endpoint security and XDR, threat intelligence, managed selection and response** (sic). _(Mod 16 p106)_
- Malwarebytes — Source: `https://www.malwarebytes.com` — all-in-one portfolio against **ransomware, malware, viruses**; layers of protection, threat intelligence, human expertise without extensive IT staff. _(Mod 16 p106)_
- Key features: **attack isolation, automated remediation, ransomware rollback**. _(Mod 16 p106)_
- Cortex XDR — Source: `https://www.paloaltonetworks.com` — offers **detection, response, automation, attack surface management**. _(Mod 16 p106)_
- Key features: **proven endpoint protection, laser-accurate detection using ML, lightning fast investigation and response, automated root-cause analysis**. _(Mod 16 p106)_

## Huntress, Symantec, Coro _(Mod 16 p107)_

- Huntress — Source: `https://www.huntress.com/` — managed EDR supported by a **24/7 team of threat hunters** against persistent cybercriminals. _(Mod 16 p107)_
- Key features: **managed EDR and antiviruses, adds threat operations, reviews all suspicious activity, quick and accurate response**. _(Mod 16 p107)_
- Symantec Endpoint Protection — Source: `www.broadcom.com` — protects **laptops, desktops, mobile devices, servers, applications, cloud workloads, containers, storage devices**. _(Mod 16 p107)_
- Key features: **strongest protection against stealthy malware and ransomware; threat detection and remediation with attack analytics and automated response; intelligent automation, AI-guided policy management**. _(Mod 16 p107)_
- Coro Endpoint Security — Source: `https://www.coro.net` — **AI automation and machine learning** across the threat landscape. _(Mod 16 p107)_
- Key features: **AI-driven automation, advanced threat detection and remediation; real-time protection from malware, ransomware, zero-day exploits, phishing attacks; behavioral-based machine learning of devices and users; tiered, layered defenses behind the email security tool**. _(Mod 16 p107)_

## Bitdefender _(Mod 16 p108)_

- Source: `https://www.bitdefender.com/` _(Mod 16 p108)_
- **Cloud-based** solution on the **Bitdefender Gravity Zone XDR platform**; each agent includes an **event recorder** with **continuous monitoring**; transmits insights to the **centralized Gravity Zone Control Center**. _(Mod 16 p108)_
- Key features: **endpoint data collection, threat detection and analysis, automated response through sandboxing of suspicious files, threat investigation, integration with security infrastructure**. _(Mod 16 p108)_

## Links

- [[MOC-Module-16]]
- [[16-LO07a-EDR-Concept-Workflow-and-Features]]
- [[16-LO07b-EDR-Detection-Investigation-Hunting-Response]]





