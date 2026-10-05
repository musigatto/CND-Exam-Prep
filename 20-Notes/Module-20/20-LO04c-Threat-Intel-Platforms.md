---
type: note
module: "20"
lo: "04"
tags: [process, tool, mod/20]
topic: "Threat Intel Platforms"
exam_weight: unknown
status: done
unresolved:
  - "p40 data-collection bullet truncated in OCR (collecti...); full wording not recoverable from slice"
  - "p44 IBM key feature prints 'Integrated solution to help suddenly stop threats'; kept verbatim, likely OCR garble"
  - "p45 USM Anywhere sentence truncated ('Because it does not require th...'); omitted remainder"
  - "p46 LookingGlass Source prints 'www.zerofox.com'; kept verbatim, not corrected"
  - "p46-47 DeepSight block truncated ('The data are enriched, verified, ...') and p47 monitor/prioritize/investigate bullets lack a printed platform name in slice; attribution left generic"
  - "p47 Darkweb TIP and p49 Frontline CTM entries truncated; only printed fragment recorded"
  - "pp42-43, p43 Fig 20.4 treated as dashboard non-evidence; no tile/sidebar values read"
---

[[MOC-Module-20]]

# Threat Intel Platforms (§20.04)

> **LO#04: Understand the different layers of threat intelligence** _(Mod 20 pp40–49)_
> Covers pp40–49.

## TIP definition _(Mod 20 p40)_

- **TIPs automate storing, analyzing, organizing, comparing multiple feeds from multiple sources in real time.**
- **TIP + SIEM** = combine all feeds into one, correlate with security events, create **prioritized alerts**.
- Driver: large data volumes, shortage of skilled analysts, growing adversarial attacks; existing tools cannot store information in **centralized format**.
- Installed as **SaaS or on-premises**; gathers/manages evolving threats + entities: **threat actors, IOCs, bulletins, TTPs**.
- Automates **aggregating, correlating, analyzing** threat data from multiple sources in real time.
- Basic capabilities: **data collection, data correlation, data enrichment, contextualization, data analysis, data integration**.

## Processing necessity _(Mod 20 p41)_

- After collection, **must process effectively to identify numerous indicators**.
- Three main aspects:
  1. **Normalization** — determining connected data across multiple inputs/sources
  2. **De-duplication** — deleting duplicate data
  3. **Improvement** — eliminating false positives, fake indicators, etc.
- Once normalized → **correlated and pivoted** to identify actionable intelligence.
- **Enrichment/contextualization** — build enriched context; automatic or via third-party analysis apps (threat actor, capabilities, infrastructure).
- **Analysis** — analyze indicator content, investigate threats, suggest investigation process, determine implication for the organization.
- **Integration** — disseminate/integrate cleaned data to **SIEM, firewalls, IDS/IPS, ticketing systems**.

## TC Complete _(Mod 20 pp42–43)_

- `Source: https://www.threatconnect.com` _(Mod 20 p42)_
- **Security operations and analytics platform built on the ThreatConnect platform**; orchestrates security functions with confidence tasks/decisions rest on **vetted, relevant TI**.
- Includes all ThreatConnect features: **indicator analytics, TI analysis, orchestration, tasking**; orchestrate processes, analyze data, **proactively hunt threats in one central place**.
- User actions:
  - **Analyzing, hunting, creating, acting** on TI
  - **Studying what worked / did not** to keep improving defenses
  - **Configuring instance** with custom apps, playbooks, indicators, attributes, import rules
- Benefits:
  - **Improves visibility:** aggregate + normalize from multiple sources; view observation frequency + relevance; identify **platform ratings, team votes, false-positive counts** per indicator/incident _(Mod 20 pp42–43)_
  - **Maximizes efficiency:** one-click automated configurable playbooks **without coding**; automate sending alerts, enriching data, assigning tasks _(Mod 20 p43)_
  - **Takes control:** proactively hunt in own network; custom dashboards; customize indicators/attributes/import rules; **private communities for secure role-based collaboration** _(Mod 20 p43)_
- p43 Fig 20.4 ThreatConnect screenshot = non-evidence; nothing read from it.

## IBM X-Force Exchange _(Mod 20 p44)_

- `Source: https://www.ibm.com`
- **Cloud-based TIP** to **consume, share, act** on TI; rapidly research latest global threats, aggregate actionable intel, consult experts, collaborate with peers.
- Supported by **human- and machine-generated intelligence**; leverages scale of IBM X-Force.
- Key features: wealth of TI data; collaborative sharing platform; integrated solution (printed wording kept verbatim); easy-to-use organize/annotate interface; **watch lists** for indicators; add **third-party TI licenses**; latest actionable threat research.

## IntelMQ _(Mod 20 p45)_

- `Source: https://intelmq.readthedocs.io/`
- For **CERTs, CSIRTs, abuse departments**; collects/processes security feeds via **message queue protocol**.
- Community-driven **Incident Handling Automation Project**, conceptually designed by **European CERTs/CSIRTs**; goal: easy collect/process method improving CERT incident handling.
- Design influenced by **AbuseHelper**, rewritten from scratch; aims to:
  - Reduce sysadmin complexity; reduce new-bot-writing complexity; reduce lost events via **persistence (even crashes)**
  - Use/improve existing **data harmonization ontology**; **JSON for all messages**
  - Integrate with AbuseHelper, **CIF**, etc.; store into **ElasticSearch, Splunk, PostgreSQL**; easy custom blacklists; communicate via **HTTP RESTFUL API**.

## USM Anywhere _(Mod 20 pp45–46)_

- `Source: https://cybersecurity.att.com/`
- **Centralized monitoring for cloud, on-premises, hybrid** incl. endpoints + cloud apps such as **Office 365 and G Suite**; one unified platform for threat detection, IR, compliance for resource-constrained teams; deploys rapidly, detecting within minutes.
- Continuous TI updates from **AlienVault Labs Security Research Team**; Labs leverages **Open Threat Exchange — world's largest open threat community** _(Mod 20 p46)_

## Other prose TIPs in slice

| Platform | What prose says it does _(Mod 20 pp46–48)_ |
|---|---|
| Pulsedive `Source: https://pulsedive.com` | Leverages **OSINT + user submissions**; submit/search/correlate/update IOCs; lists risk factors for high-risk IOCs; high-level view of threats/activity |
| LookingGlass `Source: www.zerofox.com` | Analyzes **billions of raw intel pieces daily** (social media, app stores, code shares, forums); most comprehensive view of the threat |
| FireEye iSIGHT `Source: https://www.fireeye.com` | **Proactive, forward-looking**; qualifies threats by attacker **intents, tools, tactics**; visibility before/during/after attack; predict attack, refocus on what matters |
| DeepSight (p46) `Source: https://www.symantec.com` | **Cloud-hosted CTI platform**; Symantec endpoint/product intel aggregated via big-data warehouse; enriched, verified (remainder truncated) |
| threatnote.io `Source: https://threatnote.io` | Web app by **defense point security**; add/retrieve **IPs, domains, threat actors**; new indicator needs only the object itself; fixes difficult install, paid features, excessive info |
| AbuseHelper `Source: https://github.com` | **Open-source framework** for receiving/redistributing abuse feeds + TI |
| NetWitness Orchestrator `Source: https://www.netwitness.com` | Threat data aggregation, **real-time detection**, TI feeds; advanced TI + analysis capabilities |
| Anomali ThreatStream `Source: https://www.anomali.com` | Specializes in **information sharing + TI**; aggregation, customizable feeds, IR support |
| IntSights `Source: https://intsights.com/` | Comprehensive data, **real-time monitoring, automated analysis**, customizable dashboards, risk management |
| DeepSight (p48) `Source: https://www.broadcom.com` | TI service by Broadcom: sharing, IR support, attack analysis, vulnerability intel, customizable alerts |
| Recorded Future `Source: https://www.recordedfuture.com` | Collects/analyzes huge data volumes for **real-time insights**; web interface, browser extension, expert analysis, third-party risk assessment, security control feeds, TIP _(Mod 20 p49)_ |
| Webroot BrightCloud `Source: https://www.webroot.com` | Proactive protection; **IP reputation, web classification/reputation, real-time anti-phishing, streaming malware detection, file reputation** _(Mod 20 p49)_ |
| TI Professional Services | Providers also sell **TI expert services** to help obtain TI data _(Mod 20 p49)_ |

See also: [[MOC-Module-16]] (IR — where TIP output and ticketing land).






