---
type: note
module: "14"
lo: "03"
tags: [concept, process, threat, protocol, bestpractice, mod/14]
topic: "Network traffic signatures and baselining normal traffic"
exam_weight: unknown
status: done
unresolved:
  - "p15 the LO objective sentence prints 'the various types network traffic signatures' - the word 'of' is absent in the source. Not completed."
  - "p16 the figure gives the two signature types in the abbreviated form (Normal Traffic Signature / Attack Signatures) while the body headings print 'Normal traffic signatures' / 'Attack Signatures'; both forms kept."
---

[[MOC-Module-14]]

# Network Traffic Signatures and Baselining Normal Traffic (§14.03)

> **LO#03: Determine baseline traffic signatures for normal and suspicious network traffic** _(Mod 14 p15)_
> Covers pp15–17. Stated objective: explain the various types of network traffic signatures and the
> concept of **baselining normal traffic signatures**; the section also describes the categories of
> suspicious network traffic signatures and attack signature analysis techniques _(Mod 14 p15)_.

## What a signature is _(Mod 14 p16)_

- **"A signature is a set of traffic characteristics such as a source/destination IP address, ports,
  Transmission Control Protocol (TCP) flags, packet length, time to live (TTL), and protocols."**
- Second printed form: **"a set of characters that define network activity, including IP addresses,
  Transmission Control Protocol (TCP) flags, and port numbers"** — **"It includes a set of rules used
  to detect malicious traffic entering a network."**
- *"Signatures are used to define the type of activity on a network."* _(Mod 14 p16)_

Characteristic set = **IP addresses · ports · TCP flags · packet length · TTL · protocols**.

### What signatures are used for _(Mod 14 p16)_

| Use |
|-----|
| **Raise alerts** in the case of unusual traffic on the network |
| **Identify suspicious header characteristics** in a packet |
| **Configure an intrusion detection system** to identify attacks or probes |
| **Acquire knowledge** on a specific attack that occurred or a vulnerability that can be exploited |
| **Match patterns** in a packet analysis |

### The two signature types _(Mod 14 pp16)_

| Type | Definition | Disposition |
|------|------------|-------------|
| **Normal traffic signature** | The normal network traffic in the network, **defined based on a normal traffic baseline** for the organization; contains **no malicious patterns** | **Acceptable traffic patterns allowed to enter the network** |
| **Attack signature** | Traffic patterns that appear suspicious; **deviate from the normal signature behavior** and should be analyzed | **Suspicious traffic patterns not allowed to enter the network**; if allowed, they often cause a network security breach |

## Baselining normal traffic signatures _(Mod 14 p17)_

- **"A network baseline is the accepted behavior for normal network traffic. It is a benchmark to
  differentiate between normal and suspicious traffic."**
- Baselines **differ between organizations** and **change over time** according to the operating
  environment and prevailing threat scenario.
- Purpose chain:
  - baseline → **understand the behavioral patterns of a network**;
  - baselining **allows a set of metrics to monitor network performance**; those metrics *"define the
    normal working condition of an enterprise's network traffic"*;
  - traffic is **compared with the metrics to detect any changes** that could indicate a security issue;
  - it **establishes the accepted packets that are safe for the organization**;
  - it **facilitates the detection of suspicious activities**;
  - **"Any deviation from the normal traffic baseline can be considered a suspicious traffic signature."**
- The defender should **define a baseline and validate traffic against it**; *"Baselining is more
  effective if it works in parallel with the organization's policy."*
- **No industry standard** exists to measure network traffic performance baselines — *"there are
  network monitoring tools that provide estimates of what type of traffic is normal."*
- Scope: **all incoming and outgoing Internet traffic and WAN links**, plus the traffic for
  **critical business data and backup systems**.

### Considerations to create a baseline for normal traffic _(Mod 14 p17)_

| # | Consideration |
|---|---------------|
| 1 | TCP/IP communication involves a **three-way handshake** for normal traffic |
| 2 | **A SYN flag appears at the beginning and a FIN flag at the end** of a connection |
| 3 | **All conversations originating inside the demilitarized zone (DMZ) are trusted traffic items** |
| 4 | Any traffic violating the network policies is malicious traffic — *"e.g., the existence of File Transfer Protocol (FTP) traffic when this type is restricted indicates a potential issue"* |
| 5 | **DHCP traffic from unknown DHCP servers indicates a rogue DHCP server** |
| 6 | **Mail traffic originating in the network but not sent to a mail server is suspect** |
| 7 | **Any DNS traffic not sent to the DNS server is suspect** |
| 8 | **Any outgoing traffic with internal addresses not matching the organization's address space may be malicious** |

### Normal TCP signatures _(Mod 14 p17)_

*"According to a network traffic baseline, normal traffic signatures for TCP packets should have the
following characteristics:"*

- **"To establish a three-way handshake, TCP uses SYN, SYN ACK, and ACK bits in every session."**
- **"The ACK bit should be set in every packet, except for the initial packet, in which the SYN bit
  is set."**

→ The flag-pair list that continues this section, and the illegal-packet tests, are in
[[14-LO03b-Suspicious-Traffic-Signature-Categories]] · the four suspicious-signature categories are
there too.






