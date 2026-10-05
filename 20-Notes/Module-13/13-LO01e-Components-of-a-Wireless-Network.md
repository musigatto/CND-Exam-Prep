---
type: note
module: "13"
lo: "01"
tags: [tool, concept, mod/13]
topic: "Components of a wireless network"
exam_weight: unknown
status: done
unresolved:
  - "p20 the two component figures give nine labels (Access Point (AP), Wireless Cards (NIC), Wireless Modem, Wireless Bridge, Wireless Repeater, Wireless Router, Wireless Gateways, Wireless USB Adapter, Wireless Controller) but the OCR captures only five description cells and does not bind them to labels. The figure descriptions are therefore NOT reproduced as a table; the component descriptions below come from the body text on pp21-24, which names each component explicitly."
  - "p20 the five captured figure descriptions (in OCR order, unattributed): It is a hardware device that allows wireless communication devices to connect to a wireless network via wireless standards such as Bluetooth, Wi-Fi, etc. / Systems connected to the wireless network require a network interface cards (NIC) to establish a standard Ethernet connection. / It is a device that receives and transmits network signals to other units without requiring physical cabling. / It connects multiple LANs at the medium access control (MAC) layer and is separated either logically or physically. / It is used for increasing the coverage area of the wireless network."
  - "p21 the antenna figure's name/description pairing was read from the OCR column order. Seven of the eight pairings are corroborated verbatim by pp25-27 (directional, semi-directional, parabolic grid, omnidirectional, Yagi, reflector, aperture); the dipole pairing (Bidirectional antenna, used for supporting client connections rather than site-to-site applications) has no exact match on p26, which describes the dipole as bilaterally symmetrical. Not re-assigned."
  - "p24 the antenna characteristics conflict with the rest of the module: Operating frequency band: Antennas operate at a frequency band between 960 MHz and 1215 MHz and Transmission power: Antennas transmit power at 1200 W peak and 140 W on an average. Neither figure matches the 2.4 GHz and 5 GHz Wi-Fi bands given on pp7-8, nor typical AP power. Reproduced verbatim; not corrected."
  - "p24: A radiator is always the size of half the wavelength is stated without units or context in the courseware."
  - "p22 the wireless-modem protocol list ends in CPCD and the frequency band list reads 900 MHz, 2.4 GHz, 23 GHz, 5 Hz. Both are reproduced verbatim and are likely garbled; not normalised."
  - "p22 the NIC feature list has four bullets but the last one merges two statements - It informs when to send the packets to the destination. It delivers the packet. Kept as printed."
---

[[MOC-Module-13]]

# Components of a Wireless Network (§13.01)

> **LO#01: Understand the fundamentals of wireless networks** _(Mod 13 p4)_
> Covers pp20–24.

## The nine components the courseware figures list _(Mod 13 p20)_

Access Point (AP) · Wireless Cards (NIC) · Wireless Modem · Wireless Bridge · Wireless Repeater ·
Wireless Router · Wireless Gateways · Wireless USB Adapter · Wireless Controller

> See `unresolved` — the p20 figure descriptions could not be bound to labels, so everything below
> is taken from the **body text on pp21–24**, which names each component.

## At a glance _(Mod 13 pp21–24)_

| Component | Function, per the courseware body text |
|-----------|----------------------------------------|
| **Access point** | Switch/hub between a wired LAN and a wireless network; built-in transmitter, receiver and antenna |
| **Wireless NIC** | Card that locates and communicates to an AP; **built-in antenna** instead of a port |
| **Wireless modem** | Connects a PC to a wireless network and the internet directly via an **ISP** |
| **Wireless bridge** | Connects multiple LANs **at the MAC layer**, separated logically or physically; longer range than APs |
| **Wireless repeater** | Retransmits the signal from a router or AP to create a new network; **requires an omnidirectional antenna** |
| **Wireless router** | Functions as a router **and** a wireless AP; filters traffic by IP, filters MACs, controls SSID authentication |
| **Wireless gateway** | Combines AP + router functions; provides **NAT** (public IP → private IP) and DHCP |
| **Wireless USB adapter** | Internet access via a USB port; varieties: **Cellular, Bluetooth, Wi-Fi** |
| **Wireless controller** | Central point that monitors and manages a large number of APs |

## Access point _(Mod 13 p21)_

- *"a hardware device that uses the **wireless infrastructure network mode** to connect wireless
  components to a wired network for transmitting data."*
- *"It serves as a **switch or hub** between a wired LAN and a wireless network."*
- *"It has a **built-in transmitter, receiver, and an antenna**."*
- *"The additional ports in the **WAP** help in **expanding the network range** and provide access to
  additional clients."*
- *"**The number of APs depends on the network size.** However, multiple APs provide access to a
  larger number of wireless clients."*
- *"The transmission range and distance that a client has to be from a wireless AP is a **maximum
  default value**; APs transmit usable signals **well beyond the default range**."*
- What sets the real distance: *"the **wireless standards**, **obstructions**, and **environmental
  conditions** between the clients and the APS."*
- *"The transmission range and number of devices that a WAP can connect depends on the **wireless
  standard used** and the **signal interference** between the devices."*

## Wireless network cards / NICs _(Mod 13 pp21–22)_

- *"cards that **locate and communicate to an AP** with a powerful signal, giving network access to
  the users."*
- *"**required on each device** to connect to the wireless network."*
- *"Laptops or desktop computers generally have **built-in wireless NICs** or have **slots** to
  attach them."*
- Two plug-in card types: **PCMCIA** — *"personal computer memory card international association"*,
  inserted into laptop slots; **PCI** — *"peripheral component interconnect"*, added to
  *"internal slots"* in desktops.
- *"The functionality of a wired and a wireless network card is **similar**. The difference … a
  wired network card has a **port** to connect over a network, whereas a wireless network card has
  a **built-in antenna**."*
- *"computers having a **PCI bus or USB ports** can connect to the wireless NIC."*

Data transmitted using a NIC provides: _(Mod 13 p22)_
- *"Customization of the computer's internal data from **parallel to series** before transmission."*
- *"Division of data into small blocks which incorporates **sending and receiving addresses**."*
- *"It informs when to send the packets to the destination. It delivers the packet."*

## Wireless modem _(Mod 13 p22)_

- *"allows PCs to connect to a wireless network and **access the internet connection directly with
  the help of an ISP**."*
- Contrast: *"**Wi-Fi routers** have the capacity to transmit an internet service within a **confined
  range**, whereas **wireless modems** can be used in **almost any location where a mobile phone is
  present**."*
- *"Portable devices such as laptops, mobile phones, PDAs, etc., use wireless modems to receive
  signals over the air, **similar to a cellular network**."*

Three common types _(Mod 13 p22)_

| Type | Courseware |
|------|------------|
| **Cards** | *"the **oldest** form of wireless connection"*; two types — **data cards** and **connect cards**; from mobile providers; used by laptops, PCs and routers; small, easy to use |
| **USB sticks** | *"resemble a **universal serial bus (USB) flash drive**"*; fit into a laptop USB port; require **special drivers and software**; portable |
| **Mobile hotspots** | listed as the third common type |

Selection factors _(Mod 13 pp22–23)_
- Speed of the modem
- Protocols it can support — *"ethernet, GPRS, **integrated services digital network (ISDN)**,
  **Evolution-data optimized (EVDO)**, Wi-Fi, CPCD"*
- Frequency band — *"900 MHz, 2.4 GHz, 23 GHz, 5 Hz"*
- Radio technique — *"such as a **DSSS or frequency hopping**"*
- Total number of channels for transmitting and receiving data
- Maximum signal strength
- Full duplex or half duplex capability

## Wireless bridge _(Mod 13 p23)_

- *"connects multiple LANs at the **medium access control (MAC) layer**."*
- *"These bridges **separate networks either logically or physically**. They **cover longer
  distances than APS**."*
- *"Few wireless bridges support **point-to-point** connections to an AP, while some support
  **point-to-multipoint** connections to several other APS."*
- *"Two segments reside on the **same subnet** and look like two ethernet switches connected with a
  cable."*
- *"**Broadcasts reach all the machines on that subnet** allowing **DHCP clients in one segment** to
  obtain the respective addresses from a **DHCP server from a different segment**."*
- Use case: *"connecting computers in one room to computers in another room without a cable."*

## Wireless repeater (range expander) _(Mod 13 p23)_

- *"**retransmits the existing signal** captured from the wireless router or an AP to **create a new
  network**."*
- *"It works as an **AP and a station simultaneously**."*
- *"These repeaters **require an omnidirectional antenna**. They **capture, boost, and retransmit**
  the signals."*

## Wireless router _(Mod 13 p23)_

- *"interconnects two types of networks using radio waves to the wireless enabled devices such as
  computers, laptops, and tablets."*
- *"It **functions as a router in the LAN**, but also provides **mobility** to users."*
- Security functions: *"filter the network traffic based on the **sender's and receiver's IP
  address**"*, *"provides **strong encryption, filters MAC addresses and controls SSID
  authentication**."* → see [[13-LO04e-MAC-Address-Filtering]]

## Wireless gateway _(Mod 13 p23)_

- *"allows internet-enabled devices to access the network."*
- *"It **combines the functions of wireless APs and routers**."*
- *"Wireless gateways have the feature of **network address translation (NAT)**, which translates
  the **public IP into a private IP** and **DHCP**."*

## Wireless USB adapter _(Mod 13 pp23–24)_

- *"enables internet access via a **USB port** on a computer."*
- *"It also supports **communication links and syncs between two or more devices**."*
- Three varieties: **Cellular** · **Bluetooth** · **Wi-Fi** _(Mod 13 p24)_

## Wireless controller _(Mod 13 p24)_

- *"**monitors and manages a large number of wireless access points** and enables wireless devices
  to access a wireless network architecture, known as **WLAN**."*
- *"It is typically a **central point** in the network, to which **all wireless access points** on
  the network are connected **directly or indirectly**."*

## Antenna — role _(Mod 13 p24)_

- *"designed to **transmit and receive electromagnetic waves** at radio frequencies."*
- *"a collection of **metal rods and wires** that captures radio waves and **translates them into an
  electrical current**."*
- *"The **size and shape** of an antenna is designed depending on the **frequency** of the signal
  they are designed to receive."*
- *"An antenna that receives **high frequency** signals is **highly focused**, whereas a
  **low-gain** antenna receives or transmits over a **large angle**."*
- *"A **transducer** translates the RF fields into an **alternating current (AC)** and vice-versa."*

### Antenna types (p21 figure) _(Mod 13 p21)_

| Type | Figure description |
|------|--------------------|
| **Directional Antenna** | Used for broadcasting and obtaining radio waves from a **single direction** |
| **Semi-directional antenna** | Provides **point-to-point** communication for short-to-medium distance |
| **Dipole Antenna** | **Bidirectional**; used for supporting **client connections** rather than site-to-site applications |
| **Parabolic Grid Antenna** | Based on the principle of a **satellite dish**; can pick up Wi-Fi signals from a distance of **16 km or more** |
| **Omnidirectional Antenna** | Provides a **360° horizontal radiation pattern**; used in **wireless base stations** |
| **Yagi Antenna** | **Unidirectional**; used in communications in the frequency band from **10 MHz** to **VHF** and **UHF** |
| **Reflector Antennas** | Used for **concentrating electromagnetic energy** that is radiated or received at a **focal point** |
| **Aperture Antenna** | Used for **space applications** because they are more practical for space applications |

Full characteristics and advantages/disadvantages → [[13-LO01f-Wireless-Antennas]]

### Functions of antennas _(Mod 13 p24)_

| Function | Courseware |
|----------|------------|
| **Transmission line** | *"Antennas transmit or receive radio waves from one point to another. This power transmission takes place in **free space through the natural media such as air, water, and earth**."* *"Antennas avoid power that is transmitted through other means."* |
| **Radiator** | *"A radiator **radiates energy powerfully**. This radiated energy is transmitted through the medium. A radiator is always the size of **half the wavelength**."* |
| **Resonator** | *"The use of a resonator is necessary in **broadband applications**. Resonances that occur must be **attenuated**."* |

### Characteristics of antennas _(Mod 13 p24)_

- **Operating frequency band** — *"Antennas operate at a frequency band between **960 MHz and 1215
  MHz**."*
- **Transmission power** — *"Antennas transmit power at **1200 W peak** and **140 W on an
  average**."*

> Both figures are reproduced verbatim from p24 and conflict with the 2.4 GHz / 5 GHz bands given
> elsewhere in the module — see `unresolved`.

Architecture context → [[13-LO01d-Wireless-Network-Topologies]] · future notes in this module:
[[13-LO04g-Rogue-Access-Point-Detection]] · [[13-LO04k-Router-Administrative-Security]]






