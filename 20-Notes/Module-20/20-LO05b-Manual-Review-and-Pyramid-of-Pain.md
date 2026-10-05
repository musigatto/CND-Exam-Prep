---
type: note
module: "20"
lo: "05"
tags: [concept, process, mod/20]
topic: "Manual TI review and Pyramid of Pain"
exam_weight: unknown
status: done
unresolved:
  - "p60 'SHAI and MD5' quoted as printed; likely OCR for SHA1 — refused to normalise."
  - "p59 Fig 20.7 difficulty-to-indicator pairing read from figure label order; cross-checked against p60 ascending-order prose (TTPs apex label not captured as OCR text)."
---

[[MOC-Module-20]]

# Manual TI Review and Pyramid of Pain

> **LO#05** _(Mod 20 pp58–60)_
> Covers pp58–60: manual TI feed review + Pyramid of Pain.

## Manual Review of TI Feeds _(Mod 20 p58)_

- **Manual review = obtaining TI feeds and reviewing them manually** to investigate threats relevant to the organization's security posture.

## Pyramid of Pain — framework _(Mod 20 p59)_

- Framework to **prioritize detection/response effort**: categorizes IOCs and threat-actor tactics by **relative difficulty for defenders to detect and respond to**.
- Rule: **move up to higher levels → greater cybersecurity resilience**. Higher placement = **costlier for attackers**; the **more challenging an IOC is to utilize, the more effective it is** against threat actors.
- Focusing on **TTPs and strategic insights** → deeper understanding, **proactive defenses and incident response strategies**, resource allocation to the most challenging/valuable aspects.
- Arranges **six IOCs in ascending order**; bottom → top = **least painful → most painful** (Fig 20.7).

## Pyramid levels, Tough! → Trivial _(Mod 20 pp59–60)_

| Pain | Indicator | Printed effect on the attacker |
|---|---|---|
| Tough! | **TTPs** | Highest level; detect/respond = **countering behaviors, not tools**; substantial obstacles, diminishes attack prospects |
| Challenging | **Tools** | Must find/create new tools for the same purpose; research + learn how they work |
| Annoying | **Network/Host Artifacts** | C2 info, files/directories, registry objects, URL patterns; rejecting them **causes pain** |
| Simple | **Domain Names** | Harder to change than IPs; denied → Dynamic domain name system services and domain-generated algorithms to edit names |
| Easy | **IP Addresses** | Recover quickly and easily; VPNs + anonymous proxies alter as required |
| Trivial | **Hash Values** | `SHAI`/`MD5` refs to malware samples; metamorphic/polymorphic alteration; **least advantageous, little significance** |









![IMG-NEEDED: assets/20-pyramid-of-pain.png — Pyramid of Pain, bottom hash values to apex TTPs]

