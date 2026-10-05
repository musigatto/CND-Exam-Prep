---
type: note
module: "20"
lo: "03"
tags: [concept, process, mod/20]
topic: "IOAs and IOC-vs-IOA"
exam_weight: unknown
status: done
unresolved:
  - "p24 Table 20.1 IOA cells garbled, quoted verbatim: 'Monitoring what (whom) recognize yet' (words missing) and 'Used in real time we do not' (truncated); not reconstructed"
  - "p23 'Advance persistence threats' kept verbatim (printed identically in figure and prose lists)"
  - "p23 prose prints 'Connection using uncommon ports' (singular) vs figure 'Connections using uncommon ports'; prose followed"
  - "OCR variants 'loAs' and 'IoAs' normalised to IOAs throughout"
---

[[MOC-Module-20]]

# IOAs and IOC-vs-IOA (§20.03)

> **LO#03: Understand IoCs and IOAs** _(Mod 20 p15)_
> Covers pp21–24. Sibling: [[20-LO03a-IoCs-STIX-and-MAEC]].

## IOA definition

- **IOAs = strategic indicators** from the **attacker's intent + end goal/purpose + series of pre-attack actions**; reveal an **active attack before IOCs become visible** _(Mod 20 p21)_
- **IOAs focus on the "why"**, IOCs on the **"what"** _(Mod 20 p21)_
- Detect **new/modified threats** when the attacker reconnoitres exploits or holes at the **planning stage** → defender learns intent + likely actions _(Mod 20 p21)_
- By **monitoring attack execution points** defenders infer **how the actor attempts network access → intent**; **IOCs (tool/malware knowledge) not required** _(Mod 20 p21)_

## IOA data types (p21)

- Real-time behavior incl **endpoint behavioral analytics (EBA)**; persistent + stealth components; actions taken; sequence of events _(Mod 20 p21)_
- Use behavior re the digital threat; calling of **dynamic-link libraries (DLLS)** [sic]; **TTPs linked to hostile data (malware)**; **code-execution metadata** _(Mod 20 p21)_

## IOA advantages (p22)

- **Strategic view of threat-actor/group TTPs**; proactively ID **new unknown threats + defensive strategies** _(Mod 20 p22)_
- IOA-based system suits **pre-entry prevention** — attacker **needs no malware** to compromise; system **requires no tools** to identify attacks (both verbatim) _(Mod 20 p22)_
- Indicators of **actions at each attack stage**; strong defensive **game plan**; understand **internal environment + probable targets** _(Mod 20 p22)_

## Printed IOA examples (p23)

- Advance persistence threats [sic]; remote command execution; DNS tunneling; fast flux DNS; beaconing attempt _(Mod 20 p23)_
- Unauthorized communication between public servers and internal host; multiple honeytoken notifications from a same host _(Mod 20 p23)_
- Port scanning; communication with C&C; remote code execution; C&C heartbeat detection; data exfiltration; high SMTP traffic; connection using uncommon ports _(Mod 20 p23)_

## Table 20.1 — IOCs vs IOAs (p24, cells verbatim)

| IOCs | IOAs |
|---|---|
| Monitoring "what (who) we know" | Monitoring "what (whom) recognize yet" [sic — garbled] |
| Reactive indicators of compromise | Proactive indicators of attack |
| Can be used only after a point in time | Used in real time we do not [sic — truncated] |
| Focus on malware, signatures, exploits, vulnerabilities, an IP addresses [sic] | Focus on code execution, persistence, stealth, command and control, and lateral movement |
| May not necessarily help detect new or modified threats | Identify new unknown threats and defensive strategies proactively |
| Known, universal bad news | Become bad news only based on what they mean to the organization and the situation |
| Examples: Malware, Signatures, Exploits, IP addresses, Vulnerabilities | Examples: Code executions, User behavior, Malware behavior, Persistence, Stealth |






