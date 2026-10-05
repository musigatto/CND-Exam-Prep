---
type: note
module: "20"
lo: "02"
tags: [concept, mod/20]
topic: "Types of threat intelligence"
exam_weight: unknown
status: done
unresolved:
  - "p9 intro and p10 body state three types (strategic, tactical, operational) but p14 prints a fourth, Technical; source contradicts itself, all four recorded as printed"
  - "p10 prints `ISAO/lSAC's`; p11 prose prints ISAOs/ISACs in full; expanded prose form used"
  - "p11 prints `lnformation` (lowercase-L n); read as Information"
  - "p14 running prose OCR prints `single loc`; slide caption on same page prints `single IoC`; IoC used"
---

[[MOC-Module-20]]

# Types of Threat Intelligence (§20.02)

> **LO#02: Understand the different types of threat intelligence** _(Mod 20 p9)_
> Covers pp9–14.

## Basis

- Categorized by **initial intelligence requirements, sources of information, intended audience** _(Mod 20 p9)_
- By consumption: **strategic, tactical, operational** — differ in **data collection, data analysis, intelligence consumption** _(Mod 20 p10)_
- A fourth type, **Technical**, is printed on p14 though the p9/p10 framing says three _(Mod 20 pp9–14)_

| Type | Consumed by | Core content |
|---|---|---|
| Strategic | High-level executives, management (IT management, CISO) | Posture, financial impact, trends, business-decision impact |
| Tactical | IT service managers, security operations managers, NOC staff, administrators, architects | Attacker TTPs, capabilities, goals, vectors |
| Operational | Security managers/IR heads, network defenders, forensics, fraud detection | Specific threats, actor intent/capability/opportunity, courses of action |
| Technical | Security teams | Tools, channels, resources; stealer logs, IOC feeds, CVE data |

## Strategic

- **High-level information**: posture, threats, business impact; **financial impact of cyber activities, attack trends, impact of high-level business decisions** _(Mod 20 p10)_
- **Report** form, **pre-emptive**; high-level sources, **highly skilled professionals** _(Mod 20 pp10–11)_
- Sources: **OSINT, CTI vendors, ISAOs/ISACs** _(Mod 20 p11)_
- Use: strategic business decisions + effect analysis; **budget/staff allocation**; risk-based view of risks + probability; long-term issues + real-time alerts on **IT infrastructure, employees, customers, applications** _(Mod 20 p10)_
- Identifies past similar incidents, **intentions/attribution**, why the org is in scope, major trends, risk reduction _(Mod 20 p11)_
- Typically includes _(Mod 20 p11)_: financial impact; attribution for intrusions/breaches; threat actors and attack trends; per-sector threat landscape; breach/theft/malware statistics; **geopolitical conflicts** of cyber-attacks; how adversary TTPs change over time; sectors impacted by high-level business decisions

## Tactical

- **TTPs used by threat actors (attackers)** to perform attacks _(Mod 20 p12)_
- Highly technical: **malware, campaigns, techniques, tools** as **forensic reports** _(Mod 20 p12)_
- Sources: **campaign reports, malware, incident reports, attack group reports, human intelligence**; via white/technical papers, peer orgs, purchased intelligence _(Mod 20 p12)_
- Use: expected attack methods, **information leakage**, capabilities/goals/vectors; **advance detection/mitigation** (update products with indicators, patch); day-to-day analyst support (events, investigations); also guides executive strategy _(Mod 20 p12)_

## Operational

- **Specific threats against the organization**; context on events/incidents: risks, attacker methodologies, past malicious activity, efficient investigation _(Mod 20 p13)_
- Consumed by **security managers/heads of IR, network defenders, security forensics, fraud detection teams** — see [[MOC-Module-16]] _(Mod 20 p13)_
- Covers: possible actors + **intention, capability, opportunity**; vulnerable IT assets; **impact if successful** _(Mod 20 p13)_
- Often **only government organizations** can collect it; lets IR/forensics deploy assets to **stop upcoming attacks**, detect early, cut damage; predicts future attacks, sharpens IR plans _(Mod 20 p13)_
- Sources: **humans, social media, chat rooms**, real-world activities/events; analyzing **human behavior, threat groups** _(Mod 20 p13)_
- **Report** form: identified malicious activities, **recommended courses of action**, warnings of emerging attacks _(Mod 20 p13)_

## Technical

- Security teams use it to **track new threats / investigate incidents from open-source feeds** _(Mod 20 p14)_
- **Tools, channels, resources** of the attacker: software tools, exploit methods, vectors (**phishing to advanced techniques**), channels (**compromised websites, command servers**) _(Mod 20 p14)_
- Receives: **stealer logs, IOC feeds (high-risk IPs/domains), CVE data**, other technical data _(Mod 20 p14)_
- **Quick dissemination and response**; **more transient**, concentrates on a **single IoC**; narrow-scope immediate threats _(Mod 20 p14)_






