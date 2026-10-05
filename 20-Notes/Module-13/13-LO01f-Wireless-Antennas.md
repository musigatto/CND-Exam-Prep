---
type: note
module: "13"
lo: "01"
tags: [concept, tool, mod/13]
topic: "Wireless antennas"
exam_weight: unknown
status: done
unresolved:
  - "p25 states There are five types of wireless antennas but pp25-27 go on to describe eight - directional, omnidirectional, parabolic grid, Yagi and dipole on pp25-26, then reflector, semi-directional and aperture on p27. The count of five is reproduced as printed and the full set of eight is listed; no reconciliation is offered."
  - "p25 defines gain as the ratio of the power input to the antenna to the power output from the antenna, which is the reverse of the usual ratio. Reproduced verbatim as an exam-relevant wording; not corrected."
  - "p25: the sentence The gain is generally 3.0 dBi has no subject - it is not stated which antenna type it applies to. Not attributed to any antenna."
  - "p25 no advantages or disadvantages are listed for the directional antenna, unlike every other type described. Nothing supplied."
  - "p25: the parabolic grid antenna is credited with being able to transmit weak radio signals millions of miles back to Earth. This follows the satellite-dish sentence in the source and is reproduced verbatim; no measurement or unit is given."
  - "p25: the omnidirectional antenna is described as effective for radio signal transmission because the receiver may not be stationary, and the good example given is the one used by radio stations. The p21 figure instead gives wireless base stations as the use. Both preserved as printed."
---

[[MOC-Module-13]]

# Wireless Antennas (§13.01)

> **LO#01: Understand the fundamentals of wireless networks** _(Mod 13 p4)_
> Covers pp25–27.

## Antenna characteristics _(Mod 13 p25)_

| Characteristic | Courseware definition |
|----------------|-----------------------|
| **Typical gain** | *"Gain is the **ratio of the power input to the antenna to the power output from the antenna**. It is measured in **decibels relative to an isotropic antenna (dBi)**. The gain is generally **3.0 dBi**."_ |
| **Radiation pattern** | *"obtained in the form of a **3-dimensional plot** and is generally represented in terms of two parameters, namely **elevation and azimuth**."_ |
| **Directivity** | *"the **directivity gain** of an antenna is the calculation of **radiated power in a particular direction**. It is generally the **ratio of the radiation intensity in a given direction to the average radiation intensity**."_ |
| **Polarization** | *"the **orientation of electromagnetic waves** from the source."_ Types: **linear, vertical, horizontal, circular, LHCP** (left hand circular polarized), **RHCP** (right hand circular polarized)._ |

## Antenna types — full behaviour and trade-offs _(Mod 13 pp25–27)_

> *"There are **five types of wireless antennas**"* _(Mod 13 p25)_ — but eight are described; see
> `unresolved`.

| Type | Behaviour | Advantages | Disadvantages |
|------|-----------|------------|---------------|
| **Directional** _(p25)_ | *"can **broadcast and receive radio waves from a single direction**"*; designed to work effectively in a specified direction | *(none listed in the source)* | *(none listed in the source)* |
| **Omnidirectional** _(p25)_ | *"radiate electromagnetic radiation in **all directions**. They usually radiate strong waves **uniformly in two dimensions**, but **not as strongly in the third**."_ Effective where stations use **time-division multiple access**. *"the **receiver may not be stationary** … a radio can receive a signal regardless of where it is."* | Can deal with signals from **any direction** | *"coverage area … may be **limited owing to the interference of walls and other obstacles**"*; *"difficult … to work in an **internal environment**"* |
| **Parabolic grid** _(pp25–26)_ | *"relies on the principle of a **satellite dish**, however it does **not have a solid backing**. Instead … a **semi-dish formed by a grid made of aluminum wire**."* Achieves very long-distance Wi-Fi transmission via a highly focused beam | **Wind resistant** | *"**expensive**, since it requires a **feed system** for reflecting the radio signals"*; *"the antenna **requires a reflector**. Assembling of these components makes the **installation time consuming**"* |
| **Yagi (Yagi-Uda)** _(p26)_ | *"a **unidirectional** antenna"*; *"consists of a **reflector, dipole, and directors**"*; *"generates an **endfire radiation pattern**"*; *"concentrates the radiation and response"*; band **10 MHz → VHF and UHF** | *"**good range and ease of aiming** the antenna"*; *"**directional**, focusing the entire signal in a **cardinal direction** … results in **high throughput**"*; *"installation and assembly … **easy and less time consuming** as compared to other antennas"* | *"The antenna is **very large**, especially when built for **high gain** levels"* |
| **Dipole (doublet)** _(p26)_ | *"a **straight electrical conductor, measuring half a wavelength from end to end** and is connected to the **center of the RF feed line**."* *"**bilaterally symmetrical**, and thus is inherently a **balanced antenna**."* A **balanced parallel-wire RF transmission line** serves it | *"offers **balanced signals**. With the **two-pole design**, the device receives signals from a **variety of frequencies**"* | *"an **outdoor** dipole antenna can be **much larger**, making it **difficult to manage**"*; *"to achieve the perfect frequency, antennas are required to undergo **multiple combinations** … a hassle"* |
| **Reflector** _(p27)_ | *"used for **concentrating electromagnetic energy** that is radiated or received at a **focal point**. These reflectors are generally **parabolic**."_ | *"If the surface … is **within the tolerance limit**, it can be used as a **primary mirror for all the frequencies**. This can **prevent interference while communicating with other satellites**"*; *"The **larger the antenna reflector in terms of wavelengths, the higher is the gain**"* | *"**Reflector antennas reflect** radio signals"*; *"The **manufacturing cost** of the antenna is high"* |
| **Semi-directional** _(p27)_ | *"uses **radio frequency (RF) signals** to send and receive signals **from one place to another**."* Used for communication over **short to medium distances**, inside or outside | *(none listed in the source)* | *(none listed in the source)* |
| **Aperture** _(p27)_ | *"has an **opening** that allows electromagnetic waves to be **transmitted or received**."* *"typically used in **aeroplanes or spacecraft**"* | *(none listed in the source)* | *(none listed in the source)* |

## Per-type detail

### Directional _(Mod 13 p25)_
- *"can broadcast and receive radio waves from a **single direction**."*
- *"In order to **improve the transmission and reception**, a directional antenna is designed to
  work effectively in a **specified direction**."*
- *"This also helps in **reducing interference**."*

### Omnidirectional _(Mod 13 p25)_
- *"They usually radiate strong waves **uniformly in two dimensions, but not as strongly in the
  third**."*
- *"These antennas are **efficient in areas where wireless stations use the time-division multiple
  access technology**."*
- *"A good example of an omnidirectional antenna is the one used by **radio stations**."*
- Advantage: *"can deal with signals from **any direction**."*
- Disadvantages: coverage area limited by walls and obstacles; difficult to work indoors.

### Parabolic grid _(Mod 13 pp25–26)_
- *"relies on the principle of a **satellite dish**, however it **does not have a solid backing**."*
- *"a **semi-dish formed by a grid made of aluminum wire**."*
- *"can achieve **very long distance Wi-Fi transmissions** by making use of the principle of a
  **highly focused radio wave beam**."*
- *"This type of antenna can **transmit weak radio signals millions of miles back to Earth**."_
- Advantage: *"**wind resistant**."_
- Disadvantages: *"**expensive**, since it requires a **feed system** for reflecting the radio
  signals"*; *"In addition to the feed system, the antenna **requires a reflector**."_

### Yagi _(Mod 13 p26)_
- *"also called as the **Yagi-Uda** antenna, is a **unidirectional** antenna."*
- *"commonly used in communications using the frequency band from **10 MHz** to **very high
  frequency (VHF)** and **ultra high frequency (UHF)**."*
- Objectives: *"to **improve the gain** of the antenna and to **reduce the noise level** of the radio
  signal."*
- Elements: *"a **reflector, dipole, and directors**."* Pattern: *"**endfire** radiation pattern."_
- Advantage: *"**directional**, focusing the entire signal in a **cardinal direction** … results in
  **high throughput**."_
- Disadvantage: *"**very large**, especially when built for **high gain** levels."_

### Dipole _(Mod 13 p26)_
- *"a straight electrical conductor, **measuring half a wavelength from end to end** … connected
  to the **center of the RF feed line**. This antenna is also called as a **doublet** antenna."*
- *"**bilaterally symmetrical**, and thus is inherently a **balanced antenna**."*
- Advantage: *"**balanced signals** … **two-pole design** … receives signals from a **variety of
  frequencies**."_
- Disadvantage: *"Although an **indoor** dipole antenna might be small, an **outdoor** dipole
  antenna can be **much larger** … **multiple combinations** … a **hassle**."_

### Reflector, semi-directional, aperture _(Mod 13 p27)_
- Reflector advantage: *"**The larger the antenna reflector in terms of wavelengths, the higher is
  the gain**."_
- Semi-directional: *"used for communication over **short to medium distances**, whether it's
  inside or outside."_
- Aperture: *"It is typically used in **aeroplanes or spacecraft**."_

Component list context → [[13-LO01e-Components-of-a-Wireless-Network]] · architecture →
[[13-LO01d-Wireless-Network-Topologies]] · RF interference →
[[13-LO04h-RF-Interference-Protection]] · placement →
[[13-LO04b-AP-and-Antenna-Placement]]






