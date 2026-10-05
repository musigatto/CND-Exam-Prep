---
type: note
module: "14"
lo: "02"
tags: [tool, concept, mod/14]
topic: "Network sniffers for network monitoring"
exam_weight: unknown
status: done
unresolved:
  - "p10 the URL for WinDump in the figure is OCR-garbled as 'https://www.\"npcap.org'. The p11 caption prints the same host cleanly as 'https://www.winpcap.org'; that value is used."
  - "p10 the SolarWinds URL in the figure is OCR-garbled as 'https://www.sohrwinds.com'. The p11 caption prints it cleanly as 'https://www.solarwinds.com'; that value is used."
  - "p10 the NetworkMiner URL in the figure is OCR-garbled as 'https://www.netresec.com'. The p11 caption prints it cleanly as 'https://www.netresec.com'; that value is used."
  - "p10 describes a network sniffer as 'a software' while the body text and the module elsewhere use 'a tool'. Both printed forms reproduced; no distinction drawn."
  - "p11 the NetworkMiner sentence reads 'its displays extracted artifacts in an intuitive user interface' - 'its' is printed where the sentence needs a subject. Quoted structure preserved; no subject inferred."
  - "p11 the SolarWinds entry carries no 'Source:' caption of its own; the https://www.solarwinds.com URL is printed as a standalone line above it in the figure."
---

[[MOC-Module-14]]

# Network Sniffers for Network Monitoring (§14.02a)

> **LO#02: Setting up the Environment for Network Monitoring** _(Mod 14 p9)_
> Covers pp9–11. *"The objective of this section is to explain how to setup the environment for network
> monitoring and **describe the use of various network sniffing tools** for network monitoring."_
> _(Mod 14 p9)_

## What a sniffer is _(Mod 14 p10)_

- **Callout**: *"A network sniffer is **a software** that analyzes and tracks **inbound and outbound
  packets**, monitors the network traffic, intercepts packets, **records the path taken by packets**,
  and so on."* _(Mod 14 p10)_
- **Body**: *"A network sniffer or **packet sniffer** is **a tool** that can **intercept and log
  traffic passing through** a network."* _(Mod 14 p10)_

### Why sniffers exist _(Mod 14 p10)_

- Used in **network management** for their **monitoring and analyzing** features, which help:
  **detect intrusions · supervise network contents · troubleshoot network · control traffic**. _(Mod 14 p10)_
- Used to **analyze the behavior of an application or device causing network issues**. _(Mod 14 p10)_
- Driver: *"The information flowing through a network is a **valuable source of evidence** to counter
  intrusions or anomalous connections. **The need to capture this information has led to the
  development of packet sniffers.**"* _(Mod 14 p10)_

## The six named products _(Mod 14 pp10–11)_

| Tool | Form | Source URL | What the courseware says it does |
|---|---|---|---|
| **Wireshark** | Open-source, cross-platform packet capture and analysis; **Windows and Linux** | `https://www.wireshark.org` | **GUI** gives *"a detailed breakdown of the **network protocol stack** for each packet"*; can **save packet data to a file for offline analysis**; can **export and import** captures **to and from other tools**; **statistics** can be generated for capture files |
| **tcpdump** | **Command-line** network analyzer — *"or, more technically, a packet sniffer"* | `http://www.tcpdump.org` | *"Network defenders can use this utility for network analysis."* |
| **WinDump** | *"the **Windows version of tcpdump**"* | `https://www.winpcap.org` | **watch, diagnose, and save** network traffic *"according to **various complex rules**"* |
| **ManageEngine NetFlow Analyzer** | *"complete traffic analytics tool that leverages **flow technologies**"* | `https://www.manageengine.com` | Network traffic analysis by providing **real-time visibility to traffic patterns** |
| **SolarWinds Deep Packet Inspection and Analysis Tool** | DPI; tracks **network and application traffic on a packet level** | `https://www.solarwinds.com` | Uses **response time metrics** to measure the time for packets to travel **between clients and servers** → lets administrators **manage traffic flows** and **distinguish between network and application problems** |
| **NetworkMiner** | **Passive** network sniffer / packet capturing tool | `https://www.netresec.com` | **Advanced network traffic analysis (NTA)**; displays **extracted artifacts** in an intuitive user interface |

**Discriminators worth memorising** _(Mod 14 p10–11)_

| Question | Answer as printed |
|---|---|
| Which one has a **GUI** with a protocol-stack breakdown? | Wireshark |
| Which one is **command-line**? | tcpdump |
| Which one is the **Windows** counterpart of a Linux-style CLI tool? | WinDump |
| Which one is **passive**? | NetworkMiner |
| Which one works on **flow technologies**? | ManageEngine NetFlow Analyzer |
| Which one separates **network** problems from **application** problems? | SolarWinds DPI |

## Exam angle

- All six are on pp10–11 as a **figure list plus descriptions** — recognise the vendor name and the
  one-line role; no version numbers, licences, or platform lists beyond *Windows and Linux* for
  Wireshark are given. _(Mod 14 p10)_
- The **pairing that matters**: `tcpdump` (CLI, cross-platform root) ↔ `WinDump` (its **Windows
  version**). _(Mod 14 p11)_

## Related

- Capture tooling in action: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]
- How the capture actually happens: [[14-LO02b-How-Network-Sniffers-Work-and-Placement]]
- Why capture at all: [[14-LO01a-Network-Traffic-Monitoring-and-Its-Need]]






