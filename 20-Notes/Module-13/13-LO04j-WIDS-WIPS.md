---
type: note
module: "13"
lo: "04"
tags: [tool, bestpractice, mod/13]
topic: "WIDS/WIPS"
exam_weight: unknown
status: done
unresolved:
  - "p72 the body expands WIPS as 'wireless intrusion PREVENTION systems' in the heading and the first sentence, but as 'wireless intrusion PROTECTION systems' in the second sentence: 'Wireless intrusion detection systems (WIDS)/ wireless intrusion protection systems (WIPS) help in finding...'. Both printed on the same page; neither is declared correct."
  - "pp60 and 63 give a third definition of WIDS as 'wireless access points that detect and alert when a wireless device is detected... scans for rouge devices every few milliseconds'. Recorded in [[13-LO04g-Rogue-Access-Point-Detection]] unresolved; the three definitions are not reconciled here either."
  - "p75 uses a fourth form: 'wireless intruder detection-prevention system (WIDPS) sensors' - intruder, not intrusion. Recorded in [[13-LO04l-Additional-Guidelines-and-Module-Summary]]."
  - "p72 states that WIDS/WIPS 'help in finding any abnormalities' but gives no response, blocking or quarantine action for a detected abnormality. Nothing supplied."
  - "p72 the diagram carries the labels 'Internet Database Server', 'Wi-Fi Access Intrusion', 'Wi-Fi Users', 'Corporate Wi-Fi Network Access', 'Public Wi-Fi Network'. Their relationship to each other is not explained in text; reproduced as page furniture only."
  - "p72 the Cisco claim 'It is impenetrable by most wireless attacks' is a vendor claim reproduced verbatim. No qualification, test or reference is given."
  - "p72 'Wireless intrusion detection systems (WIDS)/ wireless intrusion protection systems (WIPS)' - the source never distinguishes what a WIDS does from what a WIPS does; both are described by one shared sentence."
---

[[MOC-Module-13]]

# WIDS / WIPS (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers p72 — security measure **12**, *"Implement a wireless intrusion detection system
> (WIDS)/wireless intrusion prevention system (WIPS"*.

## What they are for _(Mod 13 p72)_

> **"A wireless intrusion detection system (WIDS)/wireless intrusion prevention system (WIPS) helps in finding any abnormalities in the wireless network such as..."**

| Abnormality detected |
|----------------------|
| **Unauthorized network activity** |
| **Policy violations** |
| **Known patterns of wireless attacks** |
| **Rogue wireless AP** |
| **Unencrypted traffic** |

**Trap:** the source gives **one** description covering both WIDS and WIPS. It never states what a WIPS
does that a WIDS does not.

## The two products named _(Mod 13 p72)_

| # | Product | Source | What the courseware says |
|---|---------|--------|--------------------------|
| 1 | **Cisco Adaptive Wireless IPS** | `https://www.cisco.com` | *"provides **specific network threat detection and mitigation** against **malicious attacks, security vulnerabilities, and sources of performance disruption**. It provides the ability to **detect, analyze, and identify wireless threats**. It also delivers **proactive threat prevention capabilities for a hardened wireless network core**. It is **impenetrable by most wireless attacks**, allowing customers to maintain **constant awareness of their RF environment**."* |
| 2 | **Extreme AirDefense** | `https://www.extremenetworks.com` | *"helps a user to **manage, monitor, and protect their WLAN networks**."* |

## Terminology as printed _(Mod 13 p72, p75, pp60/63)_

| Form | Where |
|------|-------|
| **wireless intrusion prevention system(s)** | p72 heading and first sentence |
| **wireless intrusion protection systems** | p72 second sentence |
| **WIDS = wireless access points** | pp60, 63 |
| **wireless intruder detection-prevention system (WIDPS)** | p75 |

## Related

- WIDS is also listed as a rogue-AP detection technique, with its own contradictory definition — [[13-LO04g-Rogue-Access-Point-Detection]]
- Monitoring with WIDPS sensors and WLAN scanners is a general guideline — [[13-LO04l-Additional-Guidelines-and-Module-Summary]]
- RF environment awareness links to the interference measure — [[13-LO04h-RF-Interference-Protection]]





