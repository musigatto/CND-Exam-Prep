---
type: note
module: "11"
lo: "03"
tags: [bestpractice, mod/11]
topic: "VLAN Security"
exam_weight: unknown
status: done
unresolved:
  - "pp.60-62 describe the ATTACK classes only as the stated target of a countermeasure; the courseware in this range gives no attack step-by-step or impact statement, so none is asserted here."
  - "BPDU Guard is worded two ways: slide (p60) 'ports that should never receive a BPDU message from its connected device'; prose (p61) 'prevents the accidental connection of switch ports with those that are PortFast-enabled'. Both kept, not reconciled."
  - "Root Guard: slide (p60) 'disable ports that can become root bridges'; prose (p61) 'prevents the switches that are configured as access ports from becoming the root switch'. Both kept."
  - "p62 'telnet/SHH' read as telnet/SSH - high confidence, not literal."
  - "No figures on pp.60-62; VLAN attack diagrams (if any) fall outside this slice."
---

[[MOC-Module-11]]
# VLAN Security (§11.03)

Closes the LO. Countermeasures grouped by the attack class each one targets. _(Mod 11 p60–p62)_

## MAC flooding _(Mod 11 p60)_

**Port security** — aim: safeguard the switch interface from an attacker who may send multiple Ethernet frames with **fake MAC addresses**. The admin can **statically define MAC addresses for the port** or let the switch **dynamically determine a limited number** of them. Also blocks **DHCP starvation** attacks. **Works only on access ports, never on trunk ports.** _(Mod 11 p60)_

| Control | Statement | Ref |
|---|---|---|
| Port security | Enable the switch feature; specify the **maximum number of MAC addresses** allowed on the interface; **define the MAC addresses of known devices**; **block invalid MACs and shut the port down** on receiving one | _(p60)_ |
| AAA server-based auth | Validate + filter detected MAC addresses through an **Authentication, Authorization and Accounting** server. AAA = validate identity, grant access, track user actions; gives **central management**. Configure by specifying a list of authentication methods, then implementing that list across interfaces | _(p60)_ |
| 802.1X port-based auth | **Identity-based access control, visibility and security at the network edge**. The AAA server **explicitly installs packet filtering rules** based on dynamically learned information about users and MAC addresses | _(p60)_ |

## VLAN hopping _(Mod 11 p61)_

Root cause stated: **the ports of some switches automatically turn into trunks when they receive DTP frames** → significant security threat. _(Mod 11 p61)_

| Attack class | Countermeasure | Ref |
|---|---|---|
| **Switch spoofing** | Disable trunking on all ports **not** going to be trunks; disable **DTP** on ports that are or might become trunks | _(p60–p61)_ |
| **Double tagging** | The **native VLAN should not be used to send user traffic** | _(p60–p61)_ |

## STP attacks _(Mod 11 p61)_

Implement **BPDU guard, BPDU Filter, root guard, loop guard and UDLD**. _(Mod 11 p61)_

| Feature | What it does | Ref |
|---|---|---|
| **BPDU Guard** | Prevents the accidental connection of switch ports with **PortFast-enabled** ports; prevents **L2 loops or topology changes**. Slide wording: enable on ports that should never receive a BPDU from their connected device | _(p60–p61)_ |
| **BPDU Filter** | **Disables STP on selected ports** by stopping the port from sending and receiving BPDUs | _(p61)_ |
| **Root Guard** | Prevents switches configured as **access ports** from becoming the **root switch**. Slide wording: disable ports that can become root bridges | _(p60–p61)_ |
| **Loop Guard + UDLD** | Prevent **bridging loops caused by unidirectional links** | _(p61)_ |

## ARP attacks _(Mod 11 p60–p61)_

- **Static ARP entries**: created in the ARP cache to **minimize the risk of ARP spoofing**; a static ARP entry is a **constant** entry in the cache. Prevents an adversary from sending an ARP response from their MAC address — **provided the static table holds correct MAC/IP pairs**. _(Mod 11 p60–p61)_
- **ARPWatch**: track **IP/MAC address pairing** and check forwarded ARP packets for identity correctness. _(Mod 11 p60)_

## VLAN security best practices _(Mod 11 p62)_

1. Treat VLANs as part of a **broader security implementation**.
2. Ensure that VLANs are **properly configured**.
3. **Do not configure user traffic on VLAN1.**
4. Create a **separate VLAN or virtual switch** for communication between management tools and the service console.
5. **Remove console-port cables**; use **password-protected console or virtual terminal access** with specified timeouts and restricted access policies.
6. Create an **access-list to restrict telnet/SSH access** from specific networks and hosts.
7. **Move all ports from VLAN1** and assign them to a **not-in-use VLAN**.
8. **Disable high-risk protocols** on any port that does not require them — e.g. **CDP, DTP, PAgP, UDLD**.
9. Deploy **VTP domain, VTP pruning, and password protections**.
10. **Control inter-VLAN routing** through the use of **IP access lists**.

VLAN as an NV construct: [[11-LO03a-Network-Virtualization-Concepts]].







