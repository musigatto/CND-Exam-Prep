---
type: note
module: "13"
lo: "01"
tags: [concept, mod/13]
topic: "Wireless network topologies"
exam_weight: unknown
status: done
unresolved:
  - "p15: the block headed key characteristics of an ad-hoc wireless network lists three items that all refer to an AP - The AP encrypts and decrypts text messages / Each AP operates independently and has its own respective configuration files / The network configuration remains constant with changes in the network conditions. That contradicts the p14 definition of ad-hoc mode, which states it does not implement a WAP/AP. Reproduced verbatim, not reconciled."
  - "p16: the figure caption text is not legible - the OCR yields use 46 HotAt 'G Connection Cen 4G Hotspot. Treated as non-evidence; nothing from the figure is used."
  - "pp14-21 the module uses AP, WAP, APS, HAPS and HAPs for the same device without defining the variants. p16 does define Hardware APs (HAPS); the other forms are left as printed."
  - "p17: the source says All HAPs have the capability of directly connecting to other HAPs in the LAN-to-LAN section. Reproduced as printed."
  - "p19: A WMAN links between the WLANs is stated immediately after A WMAN uses a wireless infrastructure or optical fiber connections to link the sites. The two sentences are not expanded by the source."
---

[[MOC-Module-13]]

# Wireless Network Topologies (§13.01)

> **LO#01: Understand the fundamentals of wireless networks** _(Mod 13 p4)_
> Covers pp14–19.

> *"In order to plan and install a wireless network, it is necessary to determine the type of
> architecture that would be suitable for the network environment. There are **two types of wireless
> topologies**."* _(Mod 13 p14)_

## 1. The two architectures _(Mod 13 pp14–15)_

| | **Ad-hoc / Standalone** _(Independent Basic Service Set, IBSS)_ | **Infrastructure** _(Centrally Coordinated / Basic Service Set, BSS)_ |
|---|---|---|
| Alias | Standalone Architecture (Ad-hoc Mode) | Centrally Coordinated Architecture (Infrastructure Mode) |
| Path | *"Devices connected over a wireless network communicate with each other directly, similar to that in the **peer-to-peer** communication mode."* | *"all wireless devices connect to each other **through an AP**."* |
| AP | *"does **not** implement a wireless access point (WAP)/access point (AP)"* | *"This AP (**router or switch**) receives internet access by connecting to a **broadband modem**."* |
| Adapter config | *"configured on the **ad-hoc mode** rather than on the infrastructure mode"* | AP wired to the broadband/internet side |
| Shared settings | *"Adaptors for all the devices must use the same **channel name and SSID**"* | — |
| Best fit | *"works effectively for a **small group of devices**"* and *"works better in a **small area**"* | *"will work effectively when deployed in **large organizations**"* / *"Installed in large organizations"* |

### Ad-hoc — strengths and limits _(Mod 13 p14)_

- *"the ad-hoc mode … is necessary to connect all the devices with each other **in close
  proximity**."*
- *"**Network performance degrades as the number of devices increases**."*
- *"It becomes **cumbersome for a network administrator to manage** the network in this mode,
  because devices connect and disconnect regularly."*
- *"It is **not possible to bridge this mode with a traditional wired network** and it does **not
  allow internet access until a special gateway is present**."*
- *"does not require any access points (such as a router or a switch), thus **minimizing the
  cost**."*
- *"This mode acts as a **backup option** and appears when there is a problem or a malfunction in the
  APs or a centrally coordinated network (infrastructure mode)."*

Key characteristics as printed _(Mod 13 p15)_ — see `unresolved`, these describe an AP:
- The AP encrypts and decrypts text messages.
- Each AP operates independently and has its own respective configuration files.
- The network configuration remains constant with changes in the network conditions.

### Infrastructure — value and key characteristics _(Mod 13 p15)_

*"It simplifies the network management and helps address the operational issues. It **assures
resiliency** while allowing a number of systems to connect across the network. This mode provides
**enhanced security options, scalability, stability, and easy management**. The downside is that it
is **expensive**, since an AP (router or switch) is required."*

- *"It **increases or decreases the range** of the wireless network by **adding and removing the
  APS**."*
- *"The **controller reconfigures the network** according to the changes in the **RF footprint**."*
- *"The controller regularly **monitors and controls the activities** on the wireless network by
  reconfiguring the AP elements to **maintain and protect** the network."*
- *"The **wireless centralized controller manages all the AP tasks**."*
- Controller tasks: *"**user authentication, policy creation and enforcement, fault tolerances,
  network expansion, configuration control**, etc."*
- *"It maintains **backups of other APs in a different location** and these are used when a
  particular AP **malfunctions**."*

## 2. Classification by the connection used _(Mod 13 p16)_

*"Wireless networks are classified on the basis of the connection used and the geographical area."*

| Type | What it is _(pp16–17)_ |
|------|------------------------|
| **Extension to a wired network** | APs placed between a wired network and wireless devices. The AP *"acts as a **hub**"*. Connects a **wireless LAN to a wired LAN**, giving wireless computers access to LAN resources such as **file servers** or existing internet connectivity. Wired-LAN clients and wireless-LAN clients can *"share files and printers … and vice versa."* Extensible per location size and interference from other devices. |
| **Multiple APs** | Used *"If a single large area is not covered by a single AP."* *"**Extension points** are **not defined in the wireless standard**."* *"When using multiple APS, **each AP must cover its neighbors**"*, which *"allows the users to move around seamlessly using a feature called **roaming**."* Some manufacturers make extension points that *"act as **wireless relays**, and thus **extend the range of a single AP**"*; *"**Multiple extension points can be strung together**."* |
| **LAN-to-LAN** | *"APs provide wireless connectivity to **local computers and computers on a different network**."* *"All **HAPs** have the capability of **directly connecting to other HAPs**."* *"Building interconnecting LANs by using wireless connections is **large and complex**."* |
| **4G hotspot** | *"provides internet access over a **WLAN** with the help of a **router connected to the internet service provider (ISP)**."* *"**Multiple devices can be connected at the same time** using a Wi-Fi network adapter."* *"Hotspots use the service from **cellular providers for 4G** internet access."* *"Computers generally **scan for hotspots** thereby identifying the **SSID (network name)**."* |

### The two AP flavours in "extension to a wired network" _(Mod 13 p16)_

1. **Software APs** — *"can be connected to a wired network and which **run on a computer with a
   wireless network interface card**."*
2. **Hardware APs (HAPS)** — *"provide a **comprehensive support of most of the wireless
   features**."*

## 3. Classification by geographic area coverage _(Mod 13 p17)_

*"Wireless networks are classified into **WLAN, wireless wide-area network (WWAN), wireless
personal area network (WPAN), and wireless metropolitan-area network (WMAN)** based on the area they
cover geographically."*

| Class | Coverage / mechanism | Courseware notes |
|-------|-----------------------|------------------|
| **WLAN** _(p17–18)_ | *"A WLAN connects users in a **local area** with a network. The area may range from a **single room to an entire campus**."* | Connects wireless users **and** the wired network; uses **high-frequency radio waves**; *"WLAN is also known as a **LAWN**."* *"In **1990**, IEEE created a group to develop a standard for wireless equipment."* AP *"functions as a **mediator** between the wired and wireless networks."* |
| **WWAN** _(p18)_ | *"covers an area **larger than the WLAN**"*; *"can cover a particular **region, nation, or even the entire globe**."* | Handles **CDMA, GSM, GPRS and CDPD**; *"has a built-in **cellular radio (GSM/CDMA)**."* Wireless data listed: fixed microwave links, digital dispatch networks, wireless LANs, data over cellular networks, wireless WANs, satellite links, one-way and two-way paging networks, laser-based communications, diffuse infrared, keyless car entry, GPS, *"and more."* |
| **WPAN** _(p18)_ | *"interconnects devices positioned **around an individual**"*; *"a **very short range** … can communicate within a range of **10 m**."* | *"The main concept in WPAN technology is **plugging in**."* *"the ability to **lock out other devices and prevent interference**."* Every device can connect to any other in the same WPAN **within physical range**. *"**Bluetooth is the best example of WPAN.**"* |
| **WMAN** _(pp18–19)_ | *"covers a **metropolitan area** such as an **entire city or a suburb**"*; *"accesses broadband area networks by using an **exterior antenna**."* | *"a good **alternative for a fixed-line network**"; "simple to build and is inexpensive."* *"the **subscriber stations communicate with the base station** that is connected to a **central network or hub**."* *"A WMAN links between the WLANs."* |

### WLAN advantages / disadvantage _(Mod 13 pp17–18)_

- Flexible to install; easy to set up and use.
- **Robust** — *"If one base station is down, users can **physically move their PCs in the range of
  another base station**."*
- *"It has a **better chance of surviving in case of a disaster**."*
- Disadvantage: *"Data transfer speeds are **normally slower than wired network**."*

### WMAN link technology _(Mod 13 p19)_

- *"A WMAN uses a **wireless infrastructure or optical fiber** connections to link the sites."*
- *"**Distributed queue dual bus (DQDB)** is the MAN standard for data communications, specified by
  the **IEEE 802.6** standard."*
- *"the network can be established over **30 mi** with a speed of **34 to 154 Mbits/s**."*

Technology types → [[13-LO01b-Types-of-Wireless-Technologies]] · AP hardware →
[[13-LO01e-Components-of-a-Wireless-Network]] · antenna placement →
[[13-LO04b-AP-and-Antenna-Placement]]






