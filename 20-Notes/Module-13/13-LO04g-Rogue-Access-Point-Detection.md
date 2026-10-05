---
type: note
module: "13"
lo: "04"
tags: [threat, tool, bestpractice, mod/13]
topic: "Rogue access point detection"
exam_weight: unknown
status: done
unresolved:
  - "pp60 and 63 CONTRADICT each other on what a WIDS is. p60: 'WIDS are dedicated systems or software that continuously monitor wireless network traffic to detect and report anomalies, including rogue access points.' p63: 'WIDS are wireless access points that detect and alert when a wireless device is detected. It scans for rouge devices every few milliseconds.' Both reproduced as printed; not reconciled."
  - "p63 spells the product 'WiFi Pineapple' in the scanning-tools list. Quoted as printed; no further description of it is given anywhere in the section."
  - "p63 'Scanning tools ... identify rogue access points broadcasting. These tools scan wireless controllers and devices.' The sentence 'identify rogue access points broadcasting' is incomplete as printed - no adjective or noun follows 'broadcasting'."
  - "p63 and p64 misspell 'rogue' as 'rouge' in the body text ('a rouge access point', 'rouge devices', 'the rouge device'). The p60 slide correctly reads 'rogue'. Source spellings noted, not corrected in quotations."
  - "p65 names the same handheld product three ways across the page: 'AirCheck G2 Wi-Fi Tester' (slide), 'AirCheck Wi-Fi G2 Tester' (body) and 'AirCheck Wi-Fi Tester' (figure caption). The canonical name is not determinable from the slice."
  - "p60 'Tools such as NetSpot, Ekahau, or professional site survey map network's coverage can help look for unexpected devices' - the list mixes a tool name with a phrase. Quoted as printed."
  - "p63 the Nmap result instruction is 'search for WAP characteristics in the result'. 'WAP' is printed, not 'Wi-Fi' or '802.11'. Quoted verbatim."
  - "p62 Vistumbler feature 'Speaks, signal strength using sound files' is OCR-garbled; the surrounding AirCheck material on p65 confirms sound output is a real capability but the exact wording of this line is not recoverable. Not reconstructed."
  - "p61 'Provides six graphical diagnostic views' is the first NetSurveyor feature; the remaining features continue on p62. The list is split across the page break."
  - "p61 the inSSIDer result sort order lists 'MAC address' and then 'MAC' again in the same enumeration ('MAC address, SSID, channel, received signal strength indicator (RSSI), MAC, vendor, data rate, signal strength and time last seen'). Reproduced verbatim; the duplicate is in the source."
---

[[MOC-Module-13]]

# Rogue Access Point Detection (§13.04)

> **LO#04: Discuss the various security measures that must be implemented for wireless networks** _(Mod 13 p3, p48)_
> Covers pp60–65 — security measures **8** (detect rogue APs) and **9** (locate rogue APs).

## Definition and risk _(Mod 13 p60)_

> **"A wireless AP is termed as a rogue AP when it is installed on a trusted network without authorization."**

- *"An **inside or outside attacker** can install rogue APs on a trusted network for their malicious
  intent."*
- *"To maintain the security and integrity of the network, it is **essential to detect rogue access
  points**."*
- *(p63)* *"A rouge access point **can be plugged into a firewall or switch, or a wireless card into a
  server**. They can be **lethal to security**."*

## Types of rogue APs _(Mod 13 pp60–61)_

1. Wireless router connected via a **"trusted"** interface
2. Wireless router connected via an **"untrusted"** interface
3. **Installing a wireless card** into a device that is already on a **trusted LAN**
4. **Enabling wireless** on a device that is already on a **trusted LAN**

## The core detection rule _(Mod 13 p61)_

> **"The detected wireless APs should be compared with the wireless device inventory for the environment. If an AP that is not listed in the inventory is found, it can generally be considered as a rogue AP."**

→ The inventory is the reference set. See [[13-LO04a-Security-Measures-and-Wireless-Inventory]].

## Three collection methods _(Mod 13 p60)_

| Method | What it does | Tools named |
|--------|--------------|-------------|
| **Wireless Scanning** | *"Performs a **wireless network scanning** to detect the presence of wireless APs in the vicinity"*; *"Discovery of an **AP not listed in the wireless device inventory** indicates the presence of a rogue AP"* | inSSIDer, NetSurveyor, NetStumbler, Vistumbler, Kismet |
| **Wired Network Scanning** | *"Use network scanners such as **Nmap** to identify APs on the network. This will help in locating rogue devices on the wired network."* | Nmap |
| **SNMP Polling** | *"Use the SNMP to identify the IP devices attached to the wired network."* | SolarWinds SNMP scanner, Lansweeper SNMP scanner |

> **Note _(Mod 13 p60)_:** *"To use SNMP polling, the **SNMP service on all IP devices** in the network should be enabled."*

## Technique 1 — Wireless scanning _(Mod 13 pp61–62)_

*"It performs an **active** wireless network scanning to detect the presence of wireless APs in the
vicinity. It helps in detecting **unauthorized or hidden wireless APs** that can be malicious."*

### i) inSSIDer — `https://www.metageek.com` _(Mod 13 p61)_

*"An **open source, multi-platform Wi-Fi scanner** software. It provides the user information on the
**proper channeling** of a wireless network, while offering the ability to **check co-channel effects
and overlapping networks**."*

- Uses *"a native Wi-Fi application program interface (API) and the user's NIC"*.
- **Sorts results on the basis of:** MAC address · SSID · channel · **received signal strength indicator (RSSI)** · MAC · vendor · data rate · signal strength · time last seen.

| Feature _(Mod 13 p61)_ |
|------------------------|
| Inspects WLAN and the surrounding networks to **troubleshoot competing APs** |
| **Tracks the strength of the received signal in dBm over time** |
| **Filters APs** |
| **Highlights APs** for areas having a **high Wi-Fi concentration** |
| Exports Wi-Fi and **global positioning system (GPS)** data to a **keyhole markup language (KML)** file for viewing in the **Google Earth** software |
| Shows which Wi-Fi network channels overlap and are compatible with **GPS devices** |

### ii) NetSurveyor — `http://nutsaboutnets.com` _(Mod 13 pp61–62)_

*"An **802.11 (Wi-Fi) network discovery tool** that **gathers information on the nearby wireless APs
in real-time** and displays it in useful ways. It displays the data using a variety of **diagnostic
views and charts**. It **records and provides data playback**."*

- **Provides six graphical diagnostic views**
- **Generates reports in the Adobe PDF format** that includes a list of APs and their properties along with images
- *"Supports most wireless adapters installed with a **network driver interface specification (NDIS) 5.x driver or later**"*

### iii) Vistumbler — `http://www.vistumbler.net` _(Mod 13 p62)_

| Feature |
|---------|
| **Finds wireless APs** |
| Provides **GPS support** |
| **Exports/imports APs** from Vistumbler TXT/VSI/VSZ or Netstumbler TXT/Text NSI |
| **Exports AP GPS locations** to a **Google Earth KML file** or **GPS exchange format (GPX)** |
| **Enables live Google Earth tracking:** auto KML automatically shows APs in Google Earth |
| Speaks signal strength using sound files, **Windows sound API**, or **musical instrument digital interface (MIDI)** *(line garbled in OCR)* |

### iv) NetStumbler — `http://www.netstumbler.com` _(Mod 13 p62)_

*"Uses of NetStumbler:"*

1. **Wardriving**
2. **Verifying network configurations**
3. **Finding locations with poor coverage** in a WLAN
4. **Detects the causes of wireless interference**
5. **Detects unauthorized (rogue) APs**
6. **Aiming directional antennas** for long-haul WLAN links

### v) Kismet — `https://www.kismetwireless.net` _(Mod 13 p62)_

*"A **wireless network and device detector, sniffer, wardriving tool, and has a WIDS framework**."*

## Technique 2 — Wired network scanning (Nmap) _(Mod 13 pp62–63)_

*"Wired network scanners such as Nmap are used for **identifying a large number of devices** on a
network by **sending specially crafted TCP packets** to the device (**Nmap-TCP fingerprinting**). It
helps **locate rogue APs attached to a wired network**."* — `https://nmap.org`

> **"A user can scan their entire address space using the `-A` option to identify rogue AP. When the scan is completed, the user should search for `WAP` characteristics in the result."** _(Mod 13 p63)_

## Technique 3 — SNMP polling _(Mod 13 p63)_

*"SNMP polling is used for **identifying the IP devices attached to a wired network**."*

| Utility | Source | What it does |
|---------|--------|--------------|
| **SolarWinds SNMP scanner** | `https://www.solarwinds.com` | *"a user can **regularly discover and monitor SNMP-enabled devices**"* |
| **Lansweeper SNMP scanner** | `https://www.lansweeper.com` | *"scans **all available SNMP-enabled devices** to retrieve **detailed information** through the SNMP tool"* |

## Technique 4 — WIDS _(Mod 13 pp60, 63)_

- _(p60)_ *"WIDS are **dedicated systems or software** that **continuously monitor wireless network
  traffic to detect and report anomalies**, including rogue access points."*
- _(p63)_ *"WIDS are **wireless access points** that detect and alert when a wireless device is
  detected. It scans for **rouge devices every few milliseconds**."*

→ **Contradiction.** See `unresolved`. Detail in [[13-LO04j-WIDS-WIPS]].

## Technique 5 — Wireless site surveys _(Mod 13 pp60, 63)_

*"**Regular wireless site surveys** can help identify **unauthorized access points**. Tools such as
**NetSpot, Ekahau**, or professional site survey map network's coverage can help **look for unexpected
devices**."*

## Technique 6 — Scanning tools _(Mod 13 p63)_

*"Scanning tools such as **Kismet, Aircrack-ng, or WiFi Pineapple** identify nearby wireless networks
and devices and identify rogue access points broadcasting. These tools **scan wireless controllers and
devices**. These tools provide details of **all the endpoints connected** to it, **when the rogue
access point was connected**, and **for how long it has been active**."*

## Technique 7 — Signal strength analysis _(Mod 13 pp60, 63)_

*"Rogue access points **might have a different signal strength** from that of authorized access
points. **Multiple sniffers** are used to collect the signal strength. Tools like **inSSIDer** can
help analyze signal strength and interference."*

## Technique 8 — MAC address monitoring _(Mod 13 pp60, 64)_

*"Maintain a **list of MAC addresses for authorized access points** and **check regularly for
unfamiliar MAC addresses** in the network. When a device tries to connect to the network, the
**router** checks the MAC address of the device against the list. If the MAC address is on the list
the **access is granted or else denied**."*

## Response plan once a rogue AP is found _(Mod 13 pp60, 64)_

> **"Once a rogue access point is detected, a response plan should be in place to investigate and mitigate the risk."** _(Mod 13 p60)_

| Step | Detail |
|------|--------|
| **Investigate** | *"It must **address the rogue access point, secure the physical location, or reconfigure the network settings** to prevent similar incidents."* _(Mod 13 p64)_ |
| **Disable or remove immediately** | *"Disabling can be done using a **network access control system to deactivate the switch or port** to which the rogue device is connected."* _(Mod 13 p64)_ |
| **Secure the network** | *"Secure the network to **prevent further unauthorized access**."* _(pp60, 64)_ |
| **Keep detecting** | *"Implement **intrusion detection systems that continuously scan** for rogue access points."* _(Mod 13 p64)_ |
| **Policy** | *"Create **network access policies and controls** to prevent unauthorized access."* _(Mod 13 p64)_ |

## Locating rogue access points _(Mod 13 p65)_

> **AirCheck G2 Wi-Fi Tester** — *"a **handheld tool** that identifies and locates **authorized or rogue** wireless APs in the network."* — `https://www.netally.com`

- *"It helps to **find the exact location** of any wireless AP."*
- *"must be **carried to track** the rogue AP. It detects the access point **based on the signal
  strength**."*
- *"This device **tracks down rogue and other APs by graphing the signal strength over time or by
  using an audible indication, which can be muted**."*

## Related

- MAC monitoring as a filter control: [[13-LO04e-MAC-Address-Filtering]]
- Dedicated WIDS/WIPS products: [[13-LO04j-WIDS-WIPS]]
- Full assessment tools list: [[13-LO04i-Wireless-Security-Assessment-Tools]]
- Detecting laptops used as APs is the last guideline in [[13-LO04l-Additional-Guidelines-and-Module-Summary]]






