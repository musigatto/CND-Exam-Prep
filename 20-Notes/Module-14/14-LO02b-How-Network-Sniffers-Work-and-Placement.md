---
type: note
module: "14"
lo: "02"
tags: [tool, process, concept, mod/14]
topic: "How network sniffers work and capture-machine placement"
exam_weight: unknown
status: done
unresolved:
  - "p12 the callout reads 'the system's network interface card (NIC) must be set to the promiscuous mode' and separately 'stored on the network interface controller (NIC) of a device'. Both expansions of NIC appear on the same page; reproduced as printed."
  - "p12 the source states promiscuous mode 'will help in listening to all the data transmitted in the network'. No statement is made about switched vs hubbed networks, and no exception for secure ports is given."
  - "p13 Figure 14.1 is a diagram whose labels OCR as 'user', 'Malkbus Traffic', 'Intemet', 'Attacker'. Normalised to User, Malicious Traffic, Internet, Attacker. The label 'Running Network Administrator' appears in the figure body but its position relative to the other nodes is not recoverable from the text layer; no topology beyond the prose statement is asserted."
  - "p13 the prose says the machine 'should connect to a switch in front of a firewall'. Whether 'in front of' means the switch sits between the sniffer and the firewall, or the sniffer sits between the switch and the firewall, is not disambiguated by the text; reproduced verbatim, not interpreted."
  - "p13 the callout says the machine must be placed so it 'can view all the traffic on the network'. No method (SPAN/port mirroring, inline tap) is named on this page; p14 supplies port monitoring separately."
---

[[MOC-Module-14]]

# How Network Sniffers Work and Capture-Machine Placement (§14.02b)

> **LO#02: Setting up the Environment for Network Monitoring** _(Mod 14 p9)_
> Covers pp12–13 — sniffer mechanics and where to put the capture machine.

## Working of network sniffers _(Mod 14 p12)_

> **"When a sniffer is installed on a system, the system's network interface card (NIC) must be set to
> the promiscuous mode. This will help in listening to all the data transmitted in the network."**
> _(Mod 14 p12)_

- Then the sniffer *"intercepts packets flowing in and out the of the wired or **wireless** network and
  copies it to a file. **This process is called packet capture.**"* _(Mod 14 p12)_

```
NIC set to promiscuous mode   -> hear all data on the network
        |
sniffer intercepts packets in/out (wired or wireless)
        |
copies them to a file          == packet capture
```

> Exam-critical pair: **promiscuous mode** = the *enabling condition*; **packet capture** = the *file
> copy* action. Both are named on the same page. _(Mod 14 p12)_

## The Ethernet addressing context the page sets up _(Mod 14 p12)_

Prerequisites before a capture makes sense:

- *"The most common way of networking computers is through **Ethernet**."* _(Mod 14 p12)_
- A LAN-connected computer has **two addresses**: **MAC** and **IP**. _(Mod 14 p12)_
- A **MAC address** *"uniquely identifies each node in a network and is stored on the network interface
  controller (NIC) of a device."* _(Mod 14 p12)_
- Ethernet uses the **MAC address** to transfer data to and from a system *"while building **data
  frames**."* _(Mod 14 p12)_
- The **data-link layer** of the OSI model uses an **Ethernet header** carrying *"the MAC address of
  the destination machine **instead of the IP address**."* _(Mod 14 p12)_
- The **network layer** *"is responsible for **mapping network IP addresses to MAC addresses**, as
  required by the data-link protocol."* _(Mod 14 p12)_

### ARP cache resolution _(Mod 14 p12)_

```
network layer needs the destination machine's MAC for its IP
  -> looks in a table, "usually called the Address Resolution Protocol (ARP) cache"
     -> entry present?      -> use that MAC
     -> entry absent?       -> ARP broadcast of a request packet
                               goes out to ALL machines on the local sub-network
                                  -> the machine holding that address responds
                                     to the source machine with its MAC address
                                       -> source machine's ARP cache adds this MAC to the table
                                          -> source uses this MAC in all later
                                             communication with that destination
```

**ARP cache** = the local sub-network's **IP → MAC** table. Broadcast scope is stated as the
**local sub-network**, not the routed internet. _(Mod 14 p12)_

## Positioning the machine at the appropriate location _(Mod 14 p13)_

> **"To run network sniffers, the machine must be placed at an appropriate location so that it can view
> all the traffic on the network."** _(Mod 14 p13)_

Placement rules as printed _(Mod 14 p13)_:

1. Systems *"should be **placed and connected in such a manner that all the inbound and outbound
   traffic** flowing through the network **can be viewed**."*
2. *"**Each packet must be inspected against policy violations**."*
3. A machine *"must be placed as shown in **Figure 14.1**."*
4. It *"should **connect to a switch in front of a firewall**."*
5. It *"must be **installed with the required packet sniffing and network monitoring tools**."*

### Figure 14.1 — *Deployment of machines at appropriate locations* _(Mod 14 p13)_

Readable node/edge labels: **Internet · Attacker · User · Internal Network/LAN · Switch · Firewall ·
Wireshark · Network Defender · Running Network Administrator**, with edge labels **Normal Traffic**
and **Malicious Traffic**.

Two flows are distinguished, which is the point of the figure _(Mod 14 p13)_:

| Flow | Printed label |
|---|---|
| Legitimate path | **Normal Traffic** |
| Hostile path | **Malicious Traffic** |

> The placement requirement in one line: a single vantage point that sees **all inbound and outbound**
> traffic, so a **normal** and a **malicious** flow are both visible to the same analysis tool. The
> figure is a diagram, so no node-to-edge wiring is asserted beyond the labels and the prose above.

## Related

- The tools themselves: [[14-LO02a-Network-Sniffers-for-Network-Monitoring]]
- How the wire is actually fed to the capture machine: [[14-LO02c-Connecting-the-Capture-Device-to-a-Managed-Switch]]
- Why all this capture matters: [[14-LO01a-Network-Traffic-Monitoring-and-Its-Need]]






