---
type: note
module: "14"
lo: "04"
tags: [threat, process, tool, mod/14]
topic: "MiTM sniffing and malformed packets"
exam_weight: unknown
status: done
unresolved:
  - "p55 prevention bullet reads 'The implementation of IEEE suites allows packet filtering rules to be installed by an AAA server' — the suite name is not legible; quoted verbatim, not guessed."
  - "p55 self-contradiction: 'the source address is also the same, which implies that the packets were sent from a legitimate source' is immediately followed by 'If every source has the same TTL values and all the packets are directed towards the same machine, then there may be a MAC flooding attempt'. Same-source traffic is called legitimate, then called a possible MAC flood."
  - "p54 hex dump `52 43 20 aa 54 50 77 73` and the p54/p55 Wireshark window captures are not transcribed — the pages' prose never walks through the bytes."
---

[[MOC-Module-14]]

# MiTM Sniffing and Malformed Packets (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp53–55.

Sniffing tooling: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]. ARP poisoning leg: [[14-LO04g-ARP-Poisoning-and-SQL-Injection-Traffic]].

## Section objective (p53)

- Attackers sniff network traffic to obtain sensitive information; they use **different approaches depending on the type of network**.
- **Passive sniffing** → **hub-based** network. **Active sniffing** → **switch-based** network.
- An attacker uses **MAC flooding** and **ARP poisoning** to sniff traffic.
- Identify sniffing attempts by detecting the signs of a **MAC flood** and/or an **ARP poisoning** using Wireshark. _(Mod 14 p53)_

## Active vs passive sniffing

**Sniffing (man-in-the-middle / MITM)** — "a form of eavesdropping in which an attacker captures packets by **placing themselves between a client and server**." _(Mod 14 p53)_

| | Active sniffing | Passive sniffing |
|---|---|---|
| Where | over a **switched** network | on the **hub** |
| How | attacker **injects packets** into the network traffic to gain information from the switch | hub **broadcasts all packets**; attacker only has to **initiate a session and wait** for someone else to send packets on the same collision domain |
| Target of interest | the switch, which maintains its own ARP cache known as **content addressable memory (CAM)** | the collision domain |

_(Mod 14 p53)_

Methods used in sniffing: **MAC flooding**, **ARP poisoning**. _(Mod 14 p53)_

## MAC flooding = CAM flooding

- Active sniffing method. Attacker **connects to a port on a switch** and sends a **flurry of Ethernet frames with various fake MAC addresses**.
- Goal: gain access to the **CAM table** maintained by the switch. Also known as **CAM flooding**. _(Mod 14 p54)_

### Where it shows up in Wireshark

Section objective steps _(Mod 14 p54)_:

1. **MAC-flooding packets can be detected using the Expert Information window of Wireshark** — Wireshark considers these as **malformed packets**.
2. To view these malformed packets, go to the **Analyze** menu and select **Expert Information**.
3. Signs of a MAC flooding are detected by analysing the **source IP, destination IP, and TTL values**.
4. Check whether traffic **originates from various IP addresses** and is **directed to the same destination IP address with the same TTL values**.
5. → **indication of a MAC flooding attempt on the network.**

Body text: detection is "by carefully analyzing a packet's source and destination addresses along with its **time to live (TTL)**"; after capture, go to the **Analyze tab** and click **Expert Information** from the drop-down context menu (Figure 14.6), then "look for **malformed packets** in the Expert Information tab" (Figure 14.7). _(Mod 14 pp54–55)_

### Malformed ≠  MAC flooding

> "There are various reasons for malformed packets, and they are **not necessarily** due to MAC flooding attempts." _(Mod 14 p55)_

To detect accurately, the defender must check whether **several packets are destined towards the same machine but originate from different sources**. _(Mod 14 p55)_

Figure 14.8 walkthrough: "Although the **destination address is the same**, it should be noted that the **source address is also the same**, which implies that the packets were sent from a **legitimate source**." The defender can "also verify the **TTL values** for each packet." _(Mod 14 p55)_

> ⚠ Source inconsistency: p55 then states "If **every source has the same TTL values** and all the packets are directed towards the same machine, then there **may be a MAC flooding attempt**" — i.e. same-source traffic it just called legitimate. Both sentences are in the note unreconciled; see `unresolved:`.

## Prevention (p55)

- **Port security** — the built-in port security feature of **Cisco switches**. "Port security limits the number of MAC addresses and creates a **small MAC address table instead of the larger ones created conventionally**."
- **AAA** — "The implementation of **authentication, authorization, and accounting (AAA)** by vendors **minimizes the risk of MAC flooding**."
- "The implementation of **IEEE suites** allows packet filtering rules to be installed by an AAA server." _(garbled — quoted, not guessed)_






