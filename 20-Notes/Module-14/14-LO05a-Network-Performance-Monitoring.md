---
type: note
module: "14"
lo: "05"
tags: [concept, tool, mod/14]
topic: "Network performance monitoring (NPM)"
exam_weight: unknown
status: done
unresolved:
  - "p73 The abbreviation given for Windows Management Instrumentation is garbled by OCR as (WM!); the expansion is readable, the acronym is not. Quoted as printed."
  - "p72 The side-bar bullet reads '...helps u measure, maintain, and optimize the network health...' while the body prose on the same page reads '...helps measure, maintain, and optimize network health' (no subject, no leading 'the'). The body prose is used for the quote below."
---

[[MOC-Module-14]]

# Network Performance Monitoring (§14.05)

> **LO#05: Discuss network performance and bandwidth monitoring concepts** _(Mod 14 p71)_
> Covers pp71–73. Bandwidth side of the same LO: [[14-LO05b-Bandwidth-Monitoring-and-Best-Practices]].

Section objective, p71: explain **how to monitor network performance and bandwidth**. It "describes
various network performance and bandwidth monitoring tools as well as **best practices for bandwidth
monitoring**." _(Mod 14 p71)_

## What NPM is

> "Network performance monitoring is one of the primary responsibilities of those involved in
> **day-to-day network operations**. Continuous network performance monitoring helps **measure,
> maintain, and optimize network health; diagnose and detect potential outages; and address other
> network problems** in the organization's network infrastructure." _(Mod 14 p72)_

NPM tools are used to monitor a network's **performance, availability, quality of service, and other
important metrics** _(Mod 14 p72)_. See [[14-LO01a-Network-Traffic-Monitoring-and-Its-Need]] for the
wider monitoring rationale.

Four NPM tools are named in the courseware _(Mod 14 p72)_:
**PRTG Network Monitor** · **SolarWinds Network Performance Monitor** · **ManageEngine OpManager** ·
**Capsa**.

## PRTG Network Monitor

- Network monitoring software. Supports **remote management using any web browser or smartphone**,
  **various notification methods**, and **monitoring of multiple locations** _(Mod 14 p72)_.
- Scope of use: **availability, usage, and activity monitoring** — "covers the entire range from
  **website monitoring to database performance monitoring**" _(Mod 14 p72)_.
- Captioned as providing features for **monitoring, managing, and analyzing network traffic**
  _(Mod 14 p72, figure caption)_

**"It helps in the following"** _(Mod 14 p72)_:

1. **Avoid** bandwidth and performance bottlenecks.
2. **Identify** applications or servers **using up the available bandwidth**.
3. **Instantly identify sudden spikes** caused by malicious code.
4. **Reduce the costs** of purchasing additional hardware and bandwidth.

### Data-collection protocols supported by PRTG

"PRTG can collect data for almost anything of interest on the network. It supports multiple
protocols for collecting data:" _(Mod 14 p73)_

| Group | Protocols, exactly as printed |
|---|---|
| Management | Simple Network Management Protocol (**SNMP**); Windows Management Instrumentation (**WM!** — as printed, see `unresolved:`) |
| Capture | **Packet sniffing** |
| Flow export | **NetFlow**; IP Flow Information Export (**IPFIX**); **jFlow**; **sFlow** |

The flow-export family is also a detection input in
[[14-LO06c-DDoS-Detection-NetFlow-Analyzer-and-Additional-NBA-Tools]].

## The other NPM tools named

| Tool | What the courseware says it does |
|---|---|
| **SolarWinds Network Performance Monitor (NPM)** | "a network monitoring software that can be used to quickly **detect, diagnose, and resolve** network performance problems and outages" _(Mod 14 p73)_ |
| **ManageEngine OpManager** | "an **integrated network management** software that provides **real-time network monitoring** and offers **detailed insights** into various problematic areas of a network" _(Mod 14 p73)_ |
| **Capsa Free Network Analyzer** | "a network performance **analysis and diagnostics** tool that can be used to perform **comprehensive packet capture and analysis**" _(Mod 14 p73)_ |

Capture context for the packet-analysis path: [[14-LO02a-Network-Sniffers-for-Network-Monitoring]],
[[14-LO02c-Connecting-the-Capture-Device-to-a-Managed-Switch]].

> **Non-evidence:** pp.72–73 carry product screenshots captioned "Source: https://…". No window
> titles, menu paths, counters, gauge values or graph axes were read from them. Only the readable
> running prose and figure captions are used above.







