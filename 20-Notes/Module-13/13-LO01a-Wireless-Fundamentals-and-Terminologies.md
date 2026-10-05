---
type: note
module: "13"
lo: "01"
tags: [concept, protocol, mod/13]
topic: "Wireless fundamentals and terminologies"
exam_weight: unknown
status: done
unresolved:
  - "p7 the Advantages/Limitations callout is a two-column box and the OCR interleaved both columns, splitting two bullet lines mid-sentence (...within the range / Of an access point (AP) and ...a constant internet / connection using WLAN). The two lists were separated on that reading; the reading is not stated in the source."
  - "p5 vs p6: TKIP is expanded as Temporal Key Integrity Protocol in the p5 callout but as a temporary key integrity protocol in the p6 body text. Both forms are preserved, neither is treated as the correction."
  - "p5: the DSSS callout gloss is cut off mid-phrase - Original data signal is multiplied with a pseudorandom noise spreading. Not completed."
  - "p5 vs p6: LEAP is a proprietary WLAN authentication protocol developed by Cisco Systems Inc. in the p5 callout but a proprietary Cisco authentication version protocol in the p6 body text."
  - "p5: LAWN (local area wireless network) is used once here and once on p17 (WLAN is also known as a LAWN); the module never expands it beyond that."
---

[[MOC-Module-13]]

# Wireless Fundamentals and Terminologies (§13.01)

> **LO#01: Understand the fundamentals of wireless networks**
> Section scope: *"the wireless network terminologies, components used in wireless networks, the
> uses of wireless networks, and their advantages and limitations"* — covers *"the different types
> of wireless technologies, wireless network standards, and topologies"* _(Mod 13 p4)_

## Wireless networks — the mechanism _(Mod 13 p7)_

- Data transmission by **electromagnetic waves** carrying signals over the communication path.
- Wireless networks use **radio frequency (RF) signals** to connect wireless-enabled devices.
- **Wi-Fi** = the **IEEE 802.11** standard, using radio waves for communication.
- The most important aspect in wireless networking is the **access point**, through which a user
  communicates with another mobile or fixed host.
- An AP *"is a device that contains a radio transceiver (that sends and receives signals) along with
  a **registered jack 45 (RJ-45)** wired network interface, which allows a user to connect to a
  standard wired network using a cable."* _(Mod 13 p7)_

## Terminology quick table _(Mod 13 p5)_

| Term | Courseware gloss |
|------|------------------|
| **OFDM** — Orthogonal Frequency-division Multiplexing | Method of encoding digital data on multiple carrier frequencies |
| **DSSS** — Direct-sequence Spread Spectrum | Original data signal is multiplied with a pseudorandom noise spreading _(gloss truncated in source)_ |
| **FHSS** — Frequency-hopping Spread Spectrum | Method of transmitting radio signals by rapidly switching a carrier among many frequency channels |
| **SSID** — Service Set Identifier | A 32 alphanumeric unique identifier given to a wireless local area network (WLAN) |
| **MIMO-OFDM** — Multiple-input multiple-output OFDM | Air interface for fourth generation (4G) and fifth generation (5G) broadband wireless communications |
| **TKIP** — Temporal Key Integrity Protocol | A security protocol used in wireless protected access (WPA) as a replacement for wired equivalent privacy (WEP) |
| **LEAP** — Lightweight Extensible Authentication Protocol | A proprietary WLAN authentication protocol developed by Cisco Systems Inc. |
| **EAP** — Extensible Authentication Protocol | Supports multiple authentication methods, such as token cards, Kerberos, certificates, etc. |

## Modulation / spreading

**OFDM** _(Mod 13 p5)_
- *"a system modulation format that encodes digital data to multiple channels distributed across
  the frequency band."*
- *"OFDM **minimizes the attenuation in transmission**, resulting in a high throughput."*
- Used by the **802.11a, 802.11g, 802.11n and 802.11ac** wireless standards.

**DSSS** _(Mod 13 p5)_
- *"a modulation technique that transmits digital signals over airwaves"*; requires spread spectrum
  modulation.
- *"The **802.11b** network works on the DSSS technique."*
- *"DSSS requires a **large amount of bandwidth** since it allows channel sharing."*

**FHSS** _(Mod 13 p5)_
- *"A **local area wireless network (LAWN)** uses the frequency-hopping spread spectrum (FHSS)
  modulation technique."*
- *"The transmission hop in FHSS occurs **several times per second**…"; large systems using the same
  frequency do not affect the working of small devices.*

**MIMO-OFDM** _(Mod 13 p5)_
- *"influences the spectral efficiency of the **4G** and **5G** wireless communication services."*
- *"Adopting the MIMO-OFDM technique **reduces the interference** and **increases the robustness of
  the channel**."*

## Security terminology

**SSID** _(Mod 13 p6)_
- *"a **32 alphanumeric sequence character** that acts as an identifier of a wireless network."*
- *"The SSID permits connections to the required network from an available independent network."*
- *"Devices connecting to the same WLAN **must use the same SSID** to establish a connection."*

**TKIP** _(Mod 13 p6)_
- *"an **encryption protocol** that is a part of a WLAN. It **encrypts each data packet with a
  unique encryption key**."*
- *"A TKIP is a **set of algorithms** and is **more secure than WEP**."*
- Introduced as a WPA replacement for WEP _(Mod 13 p5)_; the p12 table row for 802.11i gives it as
  *"improved encryption for networks that use the 802.11a, 802.11b, and 802.11g standards"* —
  see [[13-LO01c-Wireless-Network-Standards]].

**LEAP** _(Mod 13 p6)_
- *"used in wireless networks and point-to-point connections."*
- *"The authentication protocol depends on **WEP keys** which change with the frequent
  authentication process between a client and a server."*

**EAP** _(Mod 13 p6)_
- *"used by the **point-to-point protocol (PPP)**."*
- Supports multiple authentication types: **smart cards, token cards, public key encryption, etc.**
- Named methods: **EAP-TLS** · **EAP-SIM** · **EAP-AKA** · **EAP-TTLS**

## Advantages _(Mod 13 p7)_

- **Installation is easy and eliminates wiring.**
- **Access to the network can be from anywhere within the range of an access point (AP).**
- **Public places such as airports, schools, etc., can offer a constant internet connection using
  WLAN.**
- Removing the cable makes data **portable, mobile, and accessible**; useful in libraries, coffee
  shops, hotels, airports _(Mod 13 p7)_

## Limitations _(Mod 13 p7)_

- **Wi-Fi security may not meet the expectations.**
- **The bandwidth suffers as the number of users on the network increase.**
- **Wi-Fi standard changes may require replacing wireless components.**
- **Some electronic equipment can interfere with the Wi-Fi network.**

Types of technology → [[13-LO01b-Types-of-Wireless-Technologies]] · antenna types →
[[13-LO01f-Wireless-Antennas]]






