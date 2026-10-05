---
type: note
module: "20"
lo: "05"
tags: [process, tool, mod/20]
topic: "Consume TI and SIEM Integration"
exam_weight: unknown
status: done
unresolved:
  - "p51 TI-classification sentence truncated ('classified into Internet (web reputation, IP reputation, anti-phishing), file (file reputation), and mobile (app reputatio...'); remainder not recoverable"
  - "p53 TIDirector benefits truncated ('single integration point for all STIX/Trusted Automated Exchange ...'); remainder not recoverable"
  - "p54 SIEM-benefit sentence truncated ('complete understanding of the threats and their TT...'); remainder omitted"
  - "p57 Fig 20.6 AlienVault OSSIM screenshot treated as non-evidence; no values read"
---

[[MOC-Module-20]]

# Consume TI and SIEM Integration (§20.05)

> **LO#05: Learn to leverage/consume threat intelligence for proactive defense** _(Mod 20 pp50–57)_
> Covers pp50–57.

## Why consume TI _(Mod 20 p50)_

- With relevant actionable TI, defenders make **quick security decisions** and shift to **proactive** defense — defend **before an actual attack occurs**.
- This section = how to **integrate TI feeds into SIEMs** and similar tools.

## Before consuming: goals and feed evaluation _(Mod 20 pp51–52)_

- **Define goals, need, purpose** around proactive defense: know the **specific actor/group targeting or relevant to** the org, plus location and people the org does business with.
- Assess capabilities/goals: **what does network infrastructure look like; current posture + budget/resources** to produce and apply TI _(Mod 20 p51)_
- Evaluate feed sources before selecting — printed criteria:
  1. **How and from where data are sourced**
  2. **Whether data cover the global threat landscape**
  3. **When sourced (age)** — when sourced + how long processing took
  4. **Data efficacy** — false positives/negatives, correlation against other data
  5. **Relevance to specific needs** (organization or geographic level) _(Mod 20 pp51–52)_

## Cisco Firepower + Threat Intelligence Director _(Mod 20 p53)_

- `Source: https://www.cisco.com`
- **Threat Intelligence Director runs on Firepower Management Center**; ingests TI via **open standards** from third-party sources (TI feeds, TI platforms) into **Firepower NGFW / NGIPS** appliances.
- **Firepower sensors** (NGFW/NGIPS) supply host + user info, traffic flows with **source/destination IPs, port, protocol**; combining this with TIDirector surfaces **actionable IOCs** from feeds.
- Printed benefits: **detect/block indicators and observables via automated actions**; accurate detection/incident reporting; **improved detection and response time**; single integration point for STIX-based exchange (remainder truncated).

## TI feeds into SIEM _(Mod 20 pp54–55)_

- Purpose: **take control of chaos, gain in-depth threat knowledge, eliminate false positives**, implement **proactive intelligence-driven defense** _(Mod 20 p54)_
- Benefits:
  - Quickly **prevent high-impact evolving threats** to IT assets
  - **Real-time support** to act on indications of compromise
  - More effective detection with **fewer false-positive alarms**
  - **Context** expediting alert triage + investigation; real-time alerts with full threat understanding
  - Better tracking by **combining internal logs with external/internal TI**; verify historical data against current TI to **uncover unknown threats** _(Mod 20 pp54–55)_
- Scope an incident by **relating local observations to feeds** (all compromised resources + attack traces); mitigate advanced threats **without analyzing huge log volumes**; **pivot outside known IOCs** to add context _(Mod 20 p55)_
- CTI + SIEM adds **context and relationship to indicators** → nature of threat + level of risk → effective response _(Mod 20 p55)_

## OSSIM integration _(Mod 20 p56)_

- **AlienVault Labs TI drives USM threat assessment** → broadest view of threat vectors, attacker techniques, effective defenses.
- **Open Threat Exchange (OTX)** = collaborate, research, receive alerts on emerging/evolving threats; latest feeds updated into **OSSIM** for enhanced monitoring.
- Updated OSSIM rules: **correlation directives** (pre-defined rules linking cross-network events); **network IDS signatures** (malicious traffic); **host IDS signatures** (threats to critical systems); **asset discovery signatures** (OS/app/device info); **vulnerability assessment signatures**; **reporting modules**; **dynamic IR templates** (per-alert response guidance); **data source plugins** (legacy device/app integration).
- p57 Fig 20.6 OSSIM screenshot = non-evidence.

See also: [[MOC-Module-16]] (incident response — SIEM/TI consumer).






