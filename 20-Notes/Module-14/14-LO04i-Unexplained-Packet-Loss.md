---
type: note
module: "14"
lo: "04"
tags: [threat, process, tool, mod/14]
topic: "Unexplained packet loss"
exam_weight: unknown
status: done
unresolved:
  - "p62/p63 packet-list OCR of the Capture File Properties Interfaces table is garbled ('Pa&ets: 141 141 (100.0%)', '694 64.31.2 10.4 7185 666 (100.0%)'); no column values read out of the screenshot."
---

[[MOC-Module-14]]

# Unexplained Packet Loss (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp61–63.

Tooling: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]. The DDoS traffic itself: [[14-LO04e-SYN-FIN-DDoS-UDP-Scan-and-Password-Cracking-Traffic]].

## Why it matters (p61)

- "**Unexpected packet loss indicates an attack.**"
- "Monitoring and analyzing **unexplained packets** is crucial for identifying network attacks, such as **distributed denial of service (DDoS) attacks** or **packet injection attempts**."
- "Observing **patterns of packet loss** and scrutinizing the associated network traffic assists in **detecting security incidents**."
- "This acts as an **early warning system** for potential attacks, enabling prompt responses to **limit the damage to the organization**." _(Mod 14 p61)_

| Angle | Effect |
|---|---|
| Performance | "Unexplained packet loss adversely affects network performance, leading to **poor user experience, increased latency, and reduced throughput**." |
| Diagnostics | "By monitoring this unexplained packet loss, you can **determine the nature of the attack** and **its impact on specific network segments or devices**." |
| Action | "This information is essential for taking necessary actions to **enhance network performance**." |

_(Mod 14 p61)_

## The Wireshark route to dropped packets

Objective steps _(Mod 14 p61)_:

1. Go to **"statistics"** on the menu bar to find missing packets.
2. Click on **"Capture File Properties"**; a window pops up on the screen.
3. **Dropped packets** are displayed under **"Interfaces"**; the number denotes the number of lost packets.

Body restates the same route _(Mod 14 p62–63)_:

1. "To determine if there are **dropped packets** using Wireshark, **click Statistics in the menu bar**." → **a new window will open** (the **Capture File Properties** window).
2. "**Under Interfaces, see the Dropped packets** and the number underneath it will tell **how many packets were not captured**." _(Mod 14 p63)_

Route in one line: **Statistics → Capture File Properties → Interfaces → Dropped packets**. _(Mod 14 pp61–63)_

> The p63 body says the number "tells how many packets were **not captured**", while the p61 objective says it "denotes the number of **lost packets**". Same figure, two labels. _(Mod 14 pp61, 63)_




