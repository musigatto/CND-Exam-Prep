---
type: note
module: "13"
lo: "04"
tags: [threat, bestpractice, tool, mod/13]
topic: "RF interference protection"
exam_weight: unknown
status: done
unresolved:
  - "p66 the source says 'DoS attacks may occur in the various levels of the open system interconnection (OSI) network layer.' 'The various levels of the ... network layer' is internally odd - a layer does not have levels. Quoted verbatim; no correction attempted."
  - "p66 names the tool 'Wi-Fi Surveyor' in the body but 'WiFi Surveyor' in the three-item slide list. The source URL given for it is http://rfexplorer.com. Both spellings recorded; not harmonised."
  - "p66 lists only the physical layer for the DoS method: 'The DoS attack in the physical layer is carried out by signal jamming or intentional interference.' The three named attacks (RF jamming, signal bombing, war spamming) appear only in the callout and are not mapped to any layer. Not mapped here either."
  - "p67 the AirMagnet Spectrum XT entry on p66 carries no functional description; the body line 'AirMagnet Spectrum identifies the RF interference that impacts the performance of a wireless network' drops the 'XT'. Both forms kept as printed."
  - "p66 the slide describes RF spectrum analyzing tools as providing 'notification about excessive RF interference on a wireless network'. No alert threshold, notification format or interval is given."
---

[[MOC-Module-13]]

# Protecting from RF Interference (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers pp66–67 — security measure **10**: *"Protect from denial-of-service (DOS) attacks: interference"* _(Mod 13 p49)_.

## Why wireless is exposed to DoS _(Mod 13 p66)_

> **"Wireless networks are often susceptible to DoS attacks, since wireless networks have a shared medium of transmission."**

- *"DoS attacks may occur in the various levels of the **open system interconnection (OSI) network
  layer**."*
- *"The DoS attack in the **physical layer** is carried out by **signal jamming or intentional
  interference**."*
- *"Wireless networks use **radio frequencies** for communication and **RF spectrum analyzing tools**
  can be helpful in detecting the RF interference."*

## The measure _(Mod 13 p66)_

> **"Excessive RF interference should be detected and monitored in order to avoid DoS attacks such as RF jamming, signal bombing and war spamming."**

| Named DoS form _(Mod 13 p66)_ |
|-------------------------------|
| **RF jamming** |
| **Signal bombing** |
| **War spamming** |

*"**RF spectrum analyzing tools** should be used for detecting RF interference. Such tools provide
**notification about excessive RF interference** on a wireless network."*

## The three RF spectrum analyzers _(Mod 13 pp66–67)_

| # | Tool | Source | What the source says it does |
|---|------|--------|------------------------------|
| 1 | **AirMagnet Spectrum XT** | `https://www.netally.com` | *"AirMagnet Spectrum **identifies the RF interference** that impacts the performance of a wireless network."* _(Mod 13 p66)_ |
| 2 | **Wi-Fi Surveyor** | `http://rfexplorer.com` | **Displays** the RF environment · **Monitors** the RF signals · **Troubleshoots** the RF issues · **Detects sources** of RF interference. *"This tool helps in detecting **wireless devices and RF interference** in the network that may affect the network's performance."* _(Mod 13 p66)_ |
| 3 | **Ekahau Spectrum Analyzer** | `http://www.ekahau.com` | *"a **device** that assists in **determining the devices causing the interference** in a wireless network."* _(Mod 13 p67)_ |

## Related

- RF awareness is a stated WIDS/WIPS capability — *"constant awareness of their RF environment"* — [[13-LO04j-WIDS-WIPS]]
- Co-channel and interference analysis sit in the Wi-Fi discovery tools — [[13-LO04g-Rogue-Access-Point-Detection]]
- The band/channel choice that interference analysis feeds: [[13-LO04b-AP-and-Antenna-Placement]]






