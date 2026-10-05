---
type: note
module: "20"
lo: "06"
tags: [concept, process, bestpractice, mod/20]
topic: "Threat hunting concept and maturity"
exam_weight: unknown
status: done
unresolved:
  - "p69 'out of data' quoted as printed in the internal/external scan bullet; likely OCR for 'out of date'."
  - "p70 SIEM examples printed as 'Security QRadar SIEM, Splunk, IBM QRadar SIEM' — first item looks duplicated/garbled, quoted as-is."
  - "p66 maturity-diagram bullet order is ambiguous in OCR; level traits below follow the p67–p68 prose."
---

[[MOC-Module-20]]

# Threat Hunting Concept and Maturity

> **LO#06: Understand Threat Hunting** _(Mod 20 pp61–70)_
> Covers pp61–70: definition, steps, building blocks, maturity model, best practices, tool types.

## Definition _(Mod 20 p62)_

- **Proactive approach that actively searches** for signs of malicious activities/threats within the network that **may go unnoticed through regular security measures**; continuous monitoring + response **mitigates incidents before significant damage**.
- Threat actors can remain **undetected for months** — quietly gathering data, seeking sensitive info, harvesting credentials, moving through the network; without detection capability, **advanced persistent threats persist unstopped**.
- Thorough investigations uncover actors that **evaded initial endpoint defenses**; **does not rely on signatures**.
- Findings feed **directly into the [[MOC-Module-16]] incident response process** on detection, or improve security monitoring / new detection methods.

## Steps (Fig 20.8) _(Mod 20 pp62–63)_

1. **Create Hypothesis** — attack models + strategies a threat might use; note what automated alerting already covers; devise the hunt.
2. **Investigate Via Tools and Techniques** — combine **raw + linked data analysis incl. machine learning to merge diverse cybersecurity datasets**.
3. **Uncover New Patterns and TTPs** — **definitive success criteria** of a hunt.
4. **Inform and Enrich Analytics** — automate each successful technique so the team moves to the next investigation; enhance existing detections.

## Threat hunter responsibilities _(Mod 20 p63)_

- Hunting **insider threats / outsider attackers**; proactively hunting **known adversaries**; searching **hidden threats to prevent the attack**; **executing the incident response plan**.

## Building blocks _(Mod 20 p64)_

- Hunting is **distinct from preventing breach and from addressing vulnerabilities**; requires security-infrastructure investment + proper tool use; focus = **searching for data availability and sorting through data**.
- Figure frame: **MATURITY, Search and Visualization, Enrichment, Data, Automation, Human Threat Hunter** — Objectives to Hypotheses to Expertise (Fig 20.10, p65 carries the diagram only).

| Block | Printed purpose |
|---|---|
| Automation | Avoid starting the hunt **from the beginning every time** |
| Enrichment | Data must be **enriched with contextual information** for effective analysis |
| Visualization | Identify **links between different datasets** |
| Threat Hunters | Natural curiosity, passion, skilled tool use, varied backgrounds |

## Maturity model — five levels _(Mod 20 pp66–68)_

- Framework of **five levels** of hunting capability; **HMMO least capable → HMM4 highest efficiency**. Criteria: **data collection, hypotheses creation, tools/techniques for hypothesis testing, analytics automation**.

| Level | Data collection | Key trait |
|---|---|---|
| **0 Initial (HMMO)** | None; relies on **open-source TI indicators/feeds** | Lower-Pyramid data (domains, hashes, URLs, IPs — easily changeable, less reusable, see [[20-LO05b-Manual-Review-and-Pyramid-of-Pain]]); **lacks substantial TI capability** |
| **1 Minimal** | Moderate/high; variety of logs, better visibility | **Automated alerting directs IR**; limited hunting; TIP **enriches individually generated IOCs** |
| **2 Procedural** | High/very high; large volumes | Uses **processes created by others**; least-frequency analysis; **most organizations prefer this** |
| **3 Innovative** | High/very high | **Creates new procedures**; a few hunters fluent from basic stats to linked analysis, visualization, ML |
| **4 Leading** | High/very high | **Automates majority of successful procedures**; methods become automatic detection; team refines methodology continuously |

## Best practices _(Mod 20 pp68–69)_

- **Understand all aspects of the environment** — flows, user rights, architecture; catch zero-days and cross-boundary attacks (e.g. account compromise + injection, network breaches).
- **Establish complete network visibility** — know the networks + attacker techniques; repel via monitoring and security solutions.
- **Keep updated on the latest techniques**; continuously improve.
- **Leverage existing tools and automation** — datasets, technologies, automated analytics; **ML processes more data speedily**, saving manual labor.
- **Use UEBA** — watch users, apps, entities; how they interact with info/systems; spot unusual activity.
- **Run internal and external scans** — hunt threats and weak spots; check OS `out of data` [as printed] / device patching.
- **Leverage external threat hunters** — pentests, unauthorized activity, backdoors/trojans, validate integrity + posture, monitor attack surface.
- **Check the dark web** — what tools hackers use to exploit data; what may be abused.
- **Follow OODA — Observe, Orient, Detect, Act**: observe context, detect threats/opportunities, act.

## Hunting tool types _(Mod 20 p70)_

- Tools **streamline hunting**, surfacing threats traditional measures miss.

| Type | Printed role | Examples as printed |
|---|---|---|
| Security Monitoring | Collect/analyze; flag unusual behavior, admin-setting changes | SolarWinds, Nagios, Wireshark (firewalls, antivirus, endpoint feed data) |
| SIEM Solutions | Real-time activity monitoring across the network | `Security QRadar SIEM`, Splunk, IBM QRadar SIEM |
| Analytics Tools | Stats/intel analysis; charts/graphs to correlate, find or adapt patterns | YARA |







