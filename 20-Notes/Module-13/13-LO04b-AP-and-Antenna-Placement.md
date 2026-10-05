---
type: note
module: "13"
lo: "04"
tags: [bestpractice, mod/13]
topic: "AP and antenna placement"
exam_weight: unknown
status: done
unresolved:
  - "p52 the guidance 'Use locks and a plastic sarel enclosure to secure the AP from theft' - 'sarel' is a garbled technical term. Quoted verbatim; NOT reconstructed as 'steel'."
  - "p54 the guidance 'Place the AP antenna in a perpendicular' is an incomplete sentence in the source; what follows 'perpendicular' is not recoverable. Quoted verbatim; nothing supplied."
  - "p52 '3600 coverage' and p54 'an angle of 450' carry no degree symbol in the OCR. Rendered as 360° and 45° on the reading that the trailing character is a lost degree sign; raw OCR forms recorded here. Not verified against the PDF artwork."
  - "p52 the guidance 'Avoid mounting an AP on a wall as it may restricts its 3600 coverage' keeps the source's grammatical error 'may restricts'."
  - "p54 the guidance 'The use of external antennas as integrated antennas has a limitation' states no limitation. Quoted verbatim; nothing supplied."
  - "p54 body says the antennas 'should be positioned vertically, especially in a spacious interior' while the p54 slide says to 'Tilt the antennas downwards when installed on the ceiling' and to 'Use omnidirectional antennas pointing downwards', and p53 says 'Antennas facing upward are not part of an optimal network setup'. Vertical, downwards and upward are three different orientations; the source does not reconcile them."
  - "p52 the slide says 'Install an AP on the ceiling' while the same slide also says 'Avoid placing APS too high on ceilings'. No reconciliation is given in the source."
  - "p54 names 'HeatMapper' and 'a WiFi Analyzer' as placement/channel tools. The slide on the same page shows a heat-map figure with the words 'Mirror', 'Filing', 'Spot', 'Good WiFi', 'Dead' which do not form a readable instruction. Figure text not transcribed."
---

[[MOC-Module-13]]

# AP and Antenna Placement (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers pp52–54.

Placement is security measure **2** on the LO#04 list — *"Proper mounting of a wireless AP is necessary to **avoid outside access** and improve performance"* _(Mod 13 p52)_. Antenna types are in
[[13-LO01f-Wireless-Antennas]].

## Placement of a Wireless AP — the 9 mounting guidelines _(Mod 13 p52)_

*"**NO AP is ideal for all locations** as AP vendors design their APS to be installed in specific
locations. An AP should be mounted in a **location recommended by the manufacturer**."*

| # | Guideline | Type |
|---|-----------|------|
| 1 | **Place APs in central locations** | do |
| 2 | **Install an AP on the ceiling** | do |
| 3 | **Avoid placing APs too high on ceilings** | don't |
| 4 | **Avoid mounting an AP on a wall** as it *"may restricts its 360° coverage"* | don't |
| 5 | **Avoid installing APs in corridors** | don't |
| 6 | **Avoid installing APs above suspended ceilings** | don't |
| 7 | **Use locks and a plastic sarel enclosure** to secure the AP from theft | do *(term garbled)* |
| 8 | **Avoid enclosing the AP in a metal cage** | don't |
| 9 | **Keep the AP away from metal objects** | don't |

## Why placement matters _(Mod 13 p52)_

- *"Every AP requires installation at a **specific location and angle** since their installation at
  **random locations will restrict the network performance**."*
- Coverage must be planned wisely: **"Overlap is good. Care must be taken to not create dead-zones."**
- *"APs with an antenna cover a **circular area** and can be **obstructed by walls, metal shutters,
  or furniture**."*
- Set up APs at **a location with no interference**.
- Place the AP **within the line of sight** so users optimize maximum network performance.

### Ceiling and desk traps _(Mod 13 p52)_

- **The ideal placement of an AP is the ceiling** — *"However, this location will not always be
  feasible in organizations having very high ceilings."*
- **Trap:** *"An AP that is **facing upwards will not provide good coverage** and will **drastically
  impact the network performance**. It is beneficial to **place the AP upside down** to get an
  optimal network performance."*
- **Trap:** *"**Placing APs on a desk is not part of a good network infrastructure implementation.**
  APS, if placed on a desk encounter large amounts of interference such as **phones, Bluetooth
  devices, furniture**, etc."*
- **Security angle:** *"if an AP is on a desk, **it is not secure and it is easier to tamper with
  and/or remove**."*

## Metal and multi-AP interference _(Mod 13 p53)_

- *"APs placed near **metal sources** will **reduce the range of travel**."*
- **Trap:** *"**Metal interference acts as a mirror for APS.** This also implies that **APs should not
  be kept in a closet or in a metal case**."*
- **Trap:** *"**Antennas of the external APs must not be pointed in the same direction.** The
  antennas should **always be tilted in opposite directions**."*
- *"**Antennas facing upward are not part of an optimal network setup.**"*

## Placement of a Wireless Antenna — the 11 guidelines _(Mod 13 p54)_

*"Placement of an antenna depends on the **type, angle, and location** of the AP, and the
**coverage required**."*

| # | Guideline | Type |
|---|-----------|------|
| 1 | **Use the trial and error method** to select an appropriate location and direction | do |
| 2 | **Place the AP antenna in a perpendicular** *(sentence incomplete in source)* | - |
| 3 | **Avoid keeping the antenna at an angle of 45°** | don't |
| 4 | **Point the antenna gain towards users** | do |
| 5 | **Know the antenna radiation patterns** | do |
| 6 | **Do not place obstructions** or objects that interfere with the function of the antenna | don't |
| 7 | **The use of external antennas as integrated antennas has a limitation** *(no limitation stated)* | - |
| 8 | **Tilt the antennas downwards** when installed on the ceiling | do |
| 9 | **Use omnidirectional antennas pointing downwards** for attenuating the signals traveling up to the AP | do |
| 10 | **Avoid using simple dipole antennas** as an optimal solution | don't |
| 11 | **Use single frequency antenna elements** rather than dual tuned elements | do |

## Antenna placement in practice _(Mod 13 p54)_

- *"A wireless device should be placed in the **center of a room** with proper positioning of the
  antennas. The antennas should be **positioned vertically**, especially in a spacious interior."*
- **Use third-party applications to find the best location** — *"Applications such as **HeatMapper**
  builds a map of the interior and on the basis of this map provides a guideline for placing the
  device in the best location**."*
- *"An **appropriate band and channel** must be chosen for the wireless antenna to work on."*
- **Frequency:** *"A reliable frequency starts from **2.4 GHz**."* Select *"a frequency that is
  **compatible with the wireless device and which can travel through walls**."*
- **Channel analysis:** *"applications such as a **WiFi Analyzer** should be used."*
- *"The wireless antenna should be **replaced** in order to achieve good networking results."*
- *"**Omnidirectional antennas** that will help in improving the **range** of the wireless
  environment should be setup."*
- **RF hygiene:** *"Wireless devices should be avoided from being mounted near objects that interfere
  with **electromagnetic radiation**. **Cathode-ray tube (CRT) televisions (TVs), monitors, and
  loudspeakers** are some of the devices that should not be placed near the wireless device."*
- *"The **trial and error** method should be used for determining the best location of the wireless
  device."*

## Related

- Finding a rogue AP on foot uses the same signal-strength idea — [[13-LO04g-Rogue-Access-Point-Detection]]
- RF interference is the hostile-channel version of the same problem — [[13-LO04h-RF-Interference-Protection]]






