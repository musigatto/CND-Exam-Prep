---
type: note
module: "14"
lo: "04"
tags: [tool, command, process, mod/14]
topic: "Wireshark: the tool, its components, menus and capture/display filters"
exam_weight: unknown
status: done
unresolved:
  - "p25 the page prints the step numbers '1. 2. 3. 4. 5.' but only four step sentences are readable; which step each number maps to is not recoverable."
  - "p25 the command is printed as '$ wireshark -i eth0 —k'; the dash before k is an OCR form and has not been corrected."
  - "p29 'select Capture -5 Capture Filters' — the '5' is a mangled character, not a menu letter."
  - "p30 the capture filter syntax is printed as '[not] primitive [and lor [not] primitive ...l' — the bracketed tail is garbled; reproduced verbatim."
  - "p24 names the 'Packet byte panel' while p28 names the 'Packet bytes panel' — the source uses both."
---

[[MOC-Module-14]]

# Wireshark: the Tool and Its Interface (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp23–30. Objective of the section: **how to use Wireshark to perform network monitoring and analysis**. _(Mod 14 p23)_

The full LO#04 section works through, in order: FTP traffic, Telnet traffic, HTTP traffic, passive OS fingerprinting attempts, ping sweep attempts, ARP sweep/ARP scan attempts, TCP half open/stealth scan attempts, SYN/FIN Distributed DoS (DDoS) attempts, UDP scan attempts, password cracking attempts, sniffing attempts, MAC flooding attempts, ARP poisoning attempts, Structured Query Language (SQL) injection attempts, etc. _(Mod 14 p23)_

## What Wireshark is

- **A widely used network sniffer for network monitoring and analysis.** It "captures and intelligently browses the traffic on a network". _(Mod 14 p24)_
- A packet sniffer for **network troubleshooting**, to **investigate security issues**, and to **analyze and understand network protocols**. It "can exploit information passed in plain text". _(Mod 14 p24)_

### Feature set _(Mod 14 p24)_

| # | Feature |
|---|---|
| 1 | Identify poor network performance due to high path latency |
| 2 | Locate internetwork devices that drop packets |
| 3 | Validate the optimal configuration of network hosts |
| 4 | Analyze application functionality and dependencies |
| 5 | Optimize application behavior for best performance |
| 6 | Analyze network capacity before application launch |
| 7 | Verify application security during launch, login, and data transfer |
| 8 | **Identify unusual network traffic indicating potentially compromised hosts** |

## Components of Wireshark _(Mod 14 p24)_

| Component | Function (as printed) |
|---|---|
| Menu bar | Hosts the features of Wireshark |
| Toolbar | Hosts the most frequently used tools and icons |
| Filter toolbar | Filters the traffic based on filter options |
| Packet list panel | Displays the captured packets |
| Packet details panel | Displays detailed information about the captured packets at a granular level |
| Packet byte panel | Displays the captured packet's bytes in a hex dump format |

## Prerequisites for network packet capture _(Mod 14 pp24–25)_

"Setting up Wireshark to capture packets for the first time can be tricky." Three common problems:

- **Special privileges are required to start a live capture.** _(Mod 14 p24)_
- **The correct network interface must be chosen** to capture packet data from. _(Mod 14 p25)_
- **Packets should be captured at the correct location in the network** to view the desired traffic. _(Mod 14 p25)_

## Network analysis activities _(Mod 14 p25)_

The capture engine enables the defender to:

- Capture from different types of network hardware such as **Ethernet and 802.11**
- Stop the capture on different triggers — **amount of captured data, elapsed time, or number of packets**
- Simultaneously show decoded packets while capturing is in progress
- Filter packets to reduce the amount of data to be captured
- Save packets in multiple files during a long capture
- Simultaneously capture from **multiple network interfaces**

## First packet capture _(Mod 14 p25)_

Install and launch the tool on the target network, then select the appropriate network interface. Readable steps:

1. Double-click on an interface in the main window.
2. An overview of the available interfaces can be obtained using the **Capture Interface** dialog box.
3. Start a capture from this dialog box using the **Start** button.
4. A capture can be immediately started using the current settings by selecting **Capture Start** or by clicking the first toolbar button.

Command line, when the capture interface name is known:

```
$ wireshark -i eth0 —k
```

## Main menu — enumerates the features of Wireshark _(Mod 14 pp26–28)_

| Menu | What the page says it contains |
|---|---|
| **File** | Open and merge capture files, save, print, import and export capture files in whole or in part, and quit the application |
| **Edit** | Find a packet, time reference, and mark one or more packets; handles configuration profiles and sets preferences |
| **View** | Controls the display of captured data — colorization of packets, font zoom, display of a packet in a separate window, expanding/collapsing packet tree details |
| **Go** | Navigate to a specific packet: **previous, next, corresponding, first, last** |
| **Capture** | Start, stop and restart capture; edit capture filters |
| **Analyze** | Manipulate, display and apply filters; enable/disable dissection of protocols; configure user-specified decodes; **follow a different stream — TCP, UDP, SSL** |
| **Statistics** | Summary of captured packets, protocol hierarchy statistics, IO graphs, flow graphs |
| **Telephony** | Telephony statistic windows: media analysis, flow diagrams, protocol hierarchy statistics |
| **Wireless** | **Bluetooth and IEEE 802.11** wireless statistics |
| **Tools** | Creation of firewall access control list (ACL) rules; use of the **Lua** interpreter |
| **Help** | Help manual pages for the command-line tools, online access to some webpages, the **About Wireshark** dialog |

### View sub-items _(Mod 14 p27)_

| Sub-item | Effect |
|---|---|
| **Colorize packet list** | Controls whether the packet list is colorized. **Enabling colorization slows down** the display of new packets while capturing and loading capture files |
| **Coloring rules** | Color packets in the packet list pane **according to the filter expressions of your choice** — useful for spotting certain types of packets |
| **Colorize conversation** | Submenu that recolors packets based on the addresses of the currently selected packet — distinguishes packets belonging to different conversations |

### Analyze sub-items — follow a stream _(Mod 14 p27)_

| Sub-item | Displays |
|---|---|
| **Follow TCP stream** | All captured TCP segments on the same TCP connection as a selected packet |
| **Follow UDP stream** | All captured UDP segments on the same UDP connection as a selected packet |
| **Follow SSL stream** | All captured SSL segments on the same SSL connection as a selected packet |

### Tools sub-items _(Mod 14 p28)_

| Sub-item | Detail |
|---|---|
| **Firewall ACL rules** | Creates command-line ACL rules for **Cisco IOS, Linux Netfilter, OpenBSD, Windows Firewall**. Rules for **MAC addresses, IPv4 addresses, TCP and UDP ports, and IPv4+port combinations** are supported. **It is assumed the rules will be applied to an outside interface** |
| **Lua** | Works with the built-in Lua interpreter. Wireshark uses Lua to **write protocol dissectors** |

## Toolbars, panels, status bar _(Mod 14 p28)_

- **Main toolbar** — quick access to frequently used menu items. **Cannot be customized by the user.** Can be hidden via the **View** menu to free screen space for packet data. Items unusable in the current program state are **greyed out**.
- **Filter toolbar** — quickly edit and apply **display** filters.
- **Packet list panel** — lists packets in the current capture file, **colored by protocol**. **Each line = one packet.** Selecting a line drives the Packet Details and Packet Bytes panes.
- **Packet details panel** — details of the selected packet: the protocols making up the layers of data, shown as an expandable/collapsible **tree**. Layers named: **frame, Ethernet, IP, TCP, UDP, ICMP**, and application protocols such as **HTTP**.
- **Packet bytes panel** — packet bytes in **hex dump and ASCII**. Left side = offset in the packet data; middle = **hexadecimal**; right = corresponding **ASCII** characters.
- **Status bar** — left: context-related information · middle: current number of packets · right: selected configuration profile. Drag the handles between text areas to resize.

### Packet list default columns _(Mod 14 p28)_

| Column | Shows |
|---|---|
| **No** | Number of the packet in the capture file. **This number does not change, even if a display filter is used** |
| **Time** | Timestamp of the packet; presentation format can be changed |
| **Source** | Source address of the packet |
| **Destination** | Destination address of the packet |
| **Protocol** | Protocol name in abbreviated form |
| **Info** | Additional information about the packet content |

## Capture and display filters _(Mod 14 pp29–30)_

Purpose: to sort network traffic, **confine the search and show only the desired traffic**. Both types can be defined and **given labels for later use**, saving time recreating and retyping complex filters.

| | Display filter | Capture filter |
|---|---|---|
| Applied | On **captured** packets, while displaying | **Before** starting the capture |
| Purpose | Concentrate on interesting packets, hide uninteresting ones | Only capture what is already known to be wanted |
| Limitation | — | **Cannot be applied directly on captured traffic**; apply only when you know what you are looking for |

### Display filter selection options _(Mod 14 p29)_

Protocol · Presence of a field · Value of a field · Comparison between fields

Define or edit: the page prints "select **Capture -5 Capture Filters** or **Analyze Display Filters**" (see `unresolved`) — the mechanisms for defining and saving the two are almost identical. `+` adds a new filter, `−` removes an unwanted one, the copy button copies a selected filter, **double-clicking edits** an existing filter, **OK saves** the changes.

### Capture filter syntax — libpcap filter language _(Mod 14 p30)_

"A capture filter takes the form of a series of primitive expressions connected by conjunctions (and/or) and is optionally preceded by 'not.'"

```
[not] primitive [and lor [not] primitive ...l
```

Example — a capture filter for Telnet to and from a particular host:

```
tcp port 23 and host 10.0.0.5
```

## Related

- Protocol analysis: [[14-LO04b-Plaintext-Protocol-Traffic-FTP-TFTP-UFTP-Telnet-HTTP]] · [[14-LO04c-OS-Fingerprinting-Passive-ICMP-and-TCP-Based]]
- Attack traffic: [[14-LO04d-Nmap-Scan-Traffic-Ping-Sweep-ARP-Sweep-and-TCP-Scans]] · [[14-LO04e-SYN-FIN-DDoS-UDP-Scan-and-Password-Cracking-Traffic]]
- Name service / handshake traffic: [[14-LO04j-Name-Service-Encrypted-and-Handshake-Traffic]]
- 802.11 / Bluetooth statistics: [[MOC-Module-13]]







