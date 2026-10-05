---
type: note
module: "14"
lo: "04"
tags: [threat, protocol, command, mod/14]
topic: "DHCP spoofing and VLAN hopping"
exam_weight: unknown
status: done
unresolved: []
---

[[MOC-Module-14]]

# DHCP Spoofing and VLAN Hopping (§14.04)

> **LO#04: Perform network monitoring and analysis for suspicious traffic using Wireshark** _(Mod 14 p23)_
> Covers pp59–60.

Tooling: [[14-LO04a-Wireshark-the-Tool-and-Its-Interface]]. Switch-level active sniffing that overlaps this material: [[14-LO04f-MiTM-Sniffing-and-Malformed-Packets]].

## DHCP spoofing (p59)

- "Dynamic Host Configuration Protocol (**DHCP**) spoofing is a technique attackers use to compromise network security."
- Mechanism: "By employing DHCP spoofing, they **distribute rogue IP addresses to clients**."
- Outcomes: "**eavesdropping**, **network disruption**, and **man-in-the-middle attacks**."
- Transport: "**DHCP employs the client/server protocol `BOOTP` as its transport protocol.**"
- Filter: "To filter out DHCP spoofing attacks, **use the filter `dhcp`**." _(Mod 14 p59)_

Objective: **analyze DHCP traffic to detect and mitigate attacks that involve an attacker falsely claiming to be a legitimate DHCP server**. _(Mod 14 p59)_

## VLAN hopping (p60)

- "**VLAN hopping** is an attack where the attacker **sends traffic from one VLAN to another, bypassing Network Access Controls (NAC) to access different VLANs**."
- "This attack **exploits misconfigurations in switches** to **steal protected information**."
- **Tell in the capture:** "The presence of **DTP packets** or **packets tagged with multiple VLAN tags** indicates a VLAN hopping attack."
- Filter: "To detect VLAN hopping on a network, **use the Wireshark filter `vlan`**." _(Mod 14 p60)_

Objective: monitor and analyze network traffic for VLAN hopping attempts to detect and mitigate threats where an attacker tries to **gain unauthorized access to different VLANs in a switched network**. _(Mod 14 p60)_

## Side-by-side

| | DHCP spoofing | VLAN hopping |
|---|---|---|
| L2 target | DHCP server role (client/server over `BOOTP`) | switch configuration / VLAN boundaries |
| What the attacker does | falsely claims to be a legitimate DHCP server; distributes **rogue IP addresses** to clients | sends traffic **from one VLAN to another**, **bypassing NAC** |
| Root cause abused | a legitimate-looking server on the segment | **switch misconfigurations** |
| Capture tell | *(none printed)* | **DTP packets** or **packets tagged with multiple VLAN tags** |
| Filter printed | `dhcp` | `vlan` |
| Stakes | eavesdropping · network disruption · man-in-the-middle | stealing protected information |

_(Mod 14 pp59–60)_





