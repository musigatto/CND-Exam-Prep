---
type: note
module: "14"
lo: "04"
tags: [threat, protocol, command, tool, mod/14]
topic: "ARP poisoning and SQL injection traffic"
exam_weight: unknown
status: done
unresolved:
  - "p57 the printed SQL-indicator list is truncated by the source/OCR to 'characters specific to SQL injection such as OR, , , and z.' — the tokens between the commas are missing. Quoted verbatim; no characters supplied."
  - "p58 figure 14.13 detail pane OCR is garbled ('csrf-toEen•SecurityIsOasaleuLog •hello'') — not transcribed."
  - "p56/p58 packet-list and hex bytes are not transcribed; the pages' prose never walks through the bytes."
---

[[MOC-Module-14]]

# ARP Poisoning and SQL Injection Traffic (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp56–58.

Tooling: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]. ARP poisoning as a sniffing method: [[14-LO04f-MiTM-Sniffing-and-Malformed-Packets]]. HTTP-level inspection sits alongside [[14-LO04b-Plaintext-Protocol-Traffic-FTP-TFTP-UFTP-Telnet-HTTP]].

## ARP poisoning (p56)

**ARP** — "The address resolution protocol (ARP) **maps a MAC address to an IP address**." _(Mod 14 p56)_

Attack:
- "In an ARP poisoning attack, an attacker **changes the MAC address of the target system to their MAC address**."
- "Consequently, **all packets destined to the target system are transmitted to the attacker's machine**."
- Gain: **monitor the data flow** in a network, **forge more than one device** on the network, and have all their packets directed towards the attacker. _(Mod 14 p56)_

Objective framing _(Mod 14 p56)_: the attacker's MAC address is associated with the IP address of the target host **or a number of hosts** in the target network.

### Detection in Wireshark

| Step | Detail |
|---|---|
| Look for | warning message reading **"duplicate IP address configured"** |
| Where | the **Warnings** tab in Wireshark |
| Filter | `arp.duplicate-address-detected` |

"These messages are an **indication of an ARP poisoning attempt** on the network." _(Mod 14 p56)_

> The courseware prints the filter as `arp.duplicate- address-detected` (stray space) in the body and `arp . duplicate—address—detected` in the objective band — rendered here in normal form as `arp.duplicate-address-detected`. _(Mod 14 p56)_

## SQL injection (pp57–58)

- Wireshark detects "various **application-level attacks** such as **SQL injection** and **cross-site scripting (XSS)**."
- Method: inspect traffic and "look for **patterns specific to these types of attacks**."
- Verbatim indicator list: "look for traffic that contains **characters specific to SQL injection such as OR, , , and z**." _(Mod 14 p57 — the source text itself is incomplete between the commas; see `unresolved:`)_

Progressive analysis:

| Stage | Action | Figure |
|---|---|---|
| 1 | spot the SQL-injection pattern in the packet list — "Figure 14.10 shows an indication of an SQL injection attempt" | 14.10 |
| 2 | "These SQL injection attack patterns can be detected by **following the stream**" | 14.11 |
| 3 | "By **analyzing the traffic details**, one can even **determine whether the attack was successful**" | 14.12 |

_(Mod 14 pp57–58)_

## XSS (p58)

"Similarly, **XSS exploits can be recognized by finding malicious data (XSS injection string patterns) in the web-page `POST`**." _(Mod 14 p58)_






