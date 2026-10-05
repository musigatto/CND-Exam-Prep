---
type: note
module: "13"
lo: "01"
tags: [protocol, mod/13]
topic: "Wireless network standards"
exam_weight: unknown
status: done
unresolved:
  - "p10 first numeric table: header and row alignment is NOT recoverable from the OCR. The Frequency column carries four values (2.4 | 5 | 3.7 | 2.4) against three row labels, Bandwidth only three (22 | 20 | 22), Outdoor four (100 | 120 | 5000 | 140), and a bare 802.11g row sits at the foot of the page with an unaligned value string. Values are reproduced as column sequences only; no row was reconstructed."
  - "p10: 3.7 GHz appears in the Frequency column of the first numeric table but no standard described anywhere in pp11-13 uses 3.7 GHz. Not reconciled."
  - "p10 second numeric table: the Range (m) column holds up to 2294m, UP to 4803LF1, Up to 10530 and 30 Gbps - 46 Gbps (3750-5750). UP to 4803LF1 is garbled and the 30 Gbps entry is not a distance. Reproduced verbatim; not interpreted."
  - "p10 second numeric table: Bandwidth has ten values for five row labels, Indoor has seven, and Modulation has only three entries (MIMO-OFDM, MIMO-OFDM, MIMO-OFDM) for five rows."
  - "p10: the 802.11d table cell reads ...allowing variation in 802.11d frequencies, power levels, and bandwidth - the standard number sits mid-sentence. It is treated as an inline row-label artefact and is kept in the verbatim block; the p12 prose for 802.11d (regulatory domains, MAC layer) does not mention global portability, power levels or bandwidth variation."
  - "p11 third numeric table: only 4 of the 7 row labels carry description text (802.12, 802.15, 802.15.5, 802.16); 802.11ad, 802.15.1 and 802.15.4 have none in the OCR. The numeric columns carry 4, 2, 2, 3, 1 and 1 values for 7 rows."
  - "p10-p12: standard numbers are OCR-corrupted with letter l for digit 1 (802.Ila, 802. 1 lax, 802.1 In, 802.1 lg). Normalised to 802.11a / 802.11ax / 802.11n / 802.11g in prose; left exactly as printed inside the verbatim blocks."
  - "p10: 802.11i is given a Frequency value of 5 GHz in the numeric table even though p12 describes it only as a WLAN encryption standard and no band."
---

[[MOC-Module-13]]

# Wireless Network Standards (§13.01)

> **LO#01: Understand the fundamentals of wireless networks** _(Mod 13 p4)_
> Covers pp10–13: three numeric tables (pp10–11) plus the per-standard descriptions (pp11–13).

> [!warning] The numeric tables on pp10–11 are not transcribed as tables
> The OCR reads each table **column by column** and the row/column alignment is lost, so any piped
> reconstruction would be invention. The numeric blocks are therefore reproduced **verbatim, column
> sequence only**. Use the prose descriptions (pp11–13) for exam answers — those are clean.

## Table block 1 — p10, rows 802.11 (Wi-Fi) / 802.11a / 802.11b

```text
[ p10 table 1 — verbatim OCR column sequences; row alignment NOT recoverable ]

Column labels printed : Protocol | Frequency (GHz) | Bandwidth (MHz) |
                       Stream data rate (Mbits/s) | Modulation | Indoor | Outdoor | Range (m)
Row labels printed   : 802.11 (Wi-Fi) | 802.11a | 802.11b

Frequency (GHz)            : 2.4 | 5 | 3.7 | 2.4
Bandwidth (MHz)            : 22 | 20 | 22
Stream data rate (Mbits/s) : 6, 9, 12, 18, 24, 36, 48 | 54 | 1, 2, 5.5, 11
Modulation                 : DSSS, FHSS | OFDM | DSSS
Indoor                     : 20 | 35 | 35
Outdoor                    : 100 | 120 | 5000 | 140

[ stray row printed at the foot of p10, labelled 802.11g ]
802.11g                    : 2.4 | 6, 9, 12, 18, 24, 36, 48, 20 | 54 | OFDM | 125 | 450
```

## Table block 2 — p10, rows 802.11i / 802.11n / 802.11ac / 802.11ax / 802.11be

```text
[ p10 table 2 — verbatim OCR column sequences; row alignment NOT recoverable ]

Column labels printed : Protocol | Frequency (GHz) | Bandwidth (MHz) |
                       Stream data rate (Mbits/s) | Modulation | Indoor | Outdoor | Range (m)
Row labels printed   : 802.11i | 802.11n | 802.11ac | 802.11ax | 802.11be

Cell text captured for 802.11i:
  This is a standard for WLANs that provides improved encryption for networks that use the
  802.Ila, 802.11b, and 802.11g standards

Frequency (GHz)    : 5 | 2.4 | 5 | 2.4/5/6 | 2.4/5/6
Bandwidth (MHz)    : 20 | 40 | 20 | 40 80 160 | 40 80 80+80 320
Stream data rate (Mbits/s):
   7.2, 14.4, 21.7, 28.9, 43.3, 57.8, 65, 72.2
   15, 30, 45, 60, 90, 120, 135, 150
   7.2, 14.4, 21.7, 28.9, 43.3, 57.8, 65, 72.2, 86.7, 96.3
   15, 30, 45, 60, 90, 120, 135, 150, 180, 200
   32.5, 65, 97.5, 130, 195, 260, 292.5, 325, 390, 433.3
   65, 130, 195, 260, 390, 520, 585, 650, 780, 866.7
Range (m)          : up to 2294m | UP to 4803LF1 | Up to 10530 | 30 Gbps - 46 Gbps (3750-5750)
Modulation         : MIMO- OFDM MIMO- OFDM MIMO-OFDM
Indoor             : 70 | 70 | 35 | 35 | 35 | 35 | 30
Outdoor            : 150 | 120
```

Also on p10, as table cells:
- **802.11d** — *"It is an enhanced version of 802.11a and 802.11b that enables global portability by
  allowing variation in 802.11d frequencies, power levels, and bandwidth."*
- **802.11e** — *"It provides guidance for prioritization of data, voice, and video transmissions by
  enabling quality of service (QOS)."*

## Table block 3 — p11, rows 802.11ad / 802.12 / 802.15 / 802.15.1 / 802.15.4 / 802.15.5 / 802.16

```text
[ p11 table — verbatim OCR column sequences; row alignment NOT recoverable ]

Row labels printed : 802.11ad | 802.12 | 802.15 | 802.15.1 (Bluetooth) |
                     802.15.4 (Zigbee) | 802.15.5 | 802.16

Frequency (GHz)            : 60 | 2.4 | 2.4 | 868, 900
Bandwidth (MHz)            : 2160 | 10
Stream data rate (Mbits/s) : 6.75 Gbit/s | 1-3 Mbps
Modulation                 : OFDM, single carrier, low-power single carrier
Indoor                     : 60
Outdoor                    : 100

Description cells captured:
  802.12   : This standard defines the demand priority and media access control protocol for
             increasing the Ethernet data rate to 100 Mbps.
  802.15   : This standard defines the communication specifications for wireless personal area
             networks (WPANs)
  802.15.5 : A standard for mesh networks with enhanced reliability via route redundancy
  802.16   : A group of broadband wireless communication standards for metropolitan area
             networks (MANs)
[ no description text captured for 802.11ad, 802.15.1 or 802.15.4 ]
```

## 802.11 family — the descriptions (exam source) _(Mod 13 pp11–12)_

*"The IEEE standards correspond to the various wireless networking transmission methods."* _(Mod 13 p11)_

| Standard | Courseware description |
|----------|------------------------|
| **802.11 (Wi-Fi)** | *"corresponds to **WLANs** and uses **FHSS or DSSS** as the frequency hopping spectrum. It allows an electronic device to connect to the internet using a wireless connection that is established in any network."* |
| **802.11a** | *"the **second extension** to the original 802.11 standard. It operates in the **5 GHz** frequency band and supports a bandwidth of **up to 54 Mbps by using OFDM**. It has a fast maximum speed, but is **more sensitive to walls and other obstacles**."* |
| **802.11b** | *"IEEE expanded the 802.11 standard by creating the 802.11b specifications in **1999**. This standard operates in the **2.4 GHz industrial, scientific and medical (ISM) radio band** and supports a bandwidth of **up to 11 Mbps by using DSSS modulation**."* |
| **802.11d** | *"an **enhanced version of the 802.11a and 802.11b** standards. It **supports the regulatory domains**. The particulars of this standard can be set at the **media access control (MAC) layer**."* |
| **802.11e** | *"defines the **quality of service (QoS)** for wireless applications. The enhanced service is modified using the **MAC layer**. This standard maintains the quality of **video and audio streaming, real-time online applications, voice over internet protocol (VoIP)**, etc."* |
| **802.11g** | *"an extension of the 802.11 standard. It supports a maximum bandwidth of **54 Mbps using the OFDM** technology and uses the **same 2.4 GHz band as 802.11b**. It is **compatible with the 802.11b standard**, which implies that **802.11b devices can work directly with a 802.11g access point**."* |
| **802.11i** | *"used as a standard for **WLANs** and provides **improved encryption** for networks. 802.11i requires new protocols such as **TKIP** and **advanced encryption standard (AES)**."* |
| **802.11n** | *"developed in **2009**. It aims to **improve the 802.11g standard in terms of the bandwidth**. It operates on both the **2.4 and 5 GHz** bands and supports a maximum data rate **up to 300 Mbps**. It uses **multiple transmitters and receiver antennas (MIMO)** to allow a maximum data rate along with security improvements."* |
| **802.11ac** | *"provides a **high throughput** network at the frequency of **5 GHz**. It is **faster and more reliable than the 802.11n** standard. It involves **gigabit networking** which provides an instantaneous data transfer experience."* |
| **802.11ax** | *"also known as **Wi-Fi 6**. It is the **sixth generation** of the Wi-Fi standard. It is designed to operate in **all ISM bands between 1 and 6 GHz**."* |
| **802.11be** | *"Formally known as **Extremely High throughput (EHT)**, it will be **based on 802.11ax**, with the primary focus on **indoor and outdoor Wide Area Network (WAN) operation with fixed and walking speeds** in the frequency bands **2.4 GHz, 5 GHz, and 6 GHz**."* |
| **802.11mc** | *"enables computing devices to accurately **measure the distance to the nearest Wi-Fi access point (AP) and determine the indoor location of the AP** with a round-trip delay of **1-2 metres**."* |
| **802.11ad** | *"involves the inclusion of a **new physical layer** for 802.11 networks. This standard works on the **60 GHz spectrum**. The data propagation speed in this standard is significantly different from the bands operating at 2.4 GHz and 5 GHz. With a very high frequency spectrum, the transfer speed is **much higher than that of 802.11n**."* |

## 802.12 — demand priority _(Mod 13 p12)_

- *"dominates media utilization by working on the **demand priority protocol**. Based on this
  standard, the **ethernet speed increases to 100 Mbps**."*
- *"It is **compatible with the 802.3 and 802.5** standards. Users currently on these standards can
  **directly upgrade** to the 802.12 standard."*

## 802.15 family — WPAN _(Mod 13 p12)_

| Standard | Courseware description |
|----------|------------------------|
| **802.15** | *"defines the standards for a **wireless personal area network (WPAN)**. It describes the specification for wireless connectivity with **fixed or portable devices**."* |
| **802.15.1 (Bluetooth)** | *"Bluetooth is mainly used for **exchanging data between fixed and mobile devices over short distances**."* |
| **802.15.4 (Zigbee)** | *"The 802.15.4 standard has a **low data rate and complexity**. **Zigbee is the specification used in the 802.15.4 standard**. It transmits long distance data through a **mesh network**. This specification handles applications operating at a low data rate, but **longer battery life**. Its data rate is **250 kbits/s**."* |
| **802.15.5** | *"deploys itself on a **full mesh or a half mesh topology**. It includes **network initialization, addressing, and unicasting**."* |

## 802.16 — WiMax _(Mod 13 p13)_

> *"This standard is also known as **WiMax** and is a specification for **fixed broadband wireless
> metropolitan access networks (MANs) that use a point-to-multipoint architecture**."* _(Mod 13 p13)_

Modulation families referenced across the tables → [[13-LO01a-Wireless-Fundamentals-and-Terminologies]] ·
technology-level figures → [[13-LO01b-Types-of-Wireless-Technologies]]






