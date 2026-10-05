---
type: note
module: "14"
lo: "01"
tags: [concept, process, mod/14]
topic: "Network traffic monitoring and its need"
exam_weight: unknown
status: done
unresolved:
  - "p6 the body prose twice says 'Networking monitoring' ('Networking monitoring helps network defenders identify possible issues', 'Networking monitoring not only prevents outages') while the heading, the callout and the rest of the module say 'network monitoring'. Printed as printed; treated as the same term, not two terms."
  - "p5 'Continuous' network traffic monitoring is stated with no threshold, interval or numeric value; the term is used qualitatively only."
---

[[MOC-Module-14]]

# Network Traffic Monitoring and Its Need (§14.01a)

> **LO#01: Understand the Need for and Advantages of Network Traffic Monitoring** _(Mod 14 p4)_
> Covers pp4–6. *"The objective of this section is to explain in detail the need for and advantages of
> network traffic monitoring."* _(Mod 14 p4)_

## The one-word qualifier _(Mod 14 p5)_

> **"Network monitoring is a retrospective security approach"** that involves monitoring a network for
> abnormal activities, performance issues, bandwidth issues, etc. _(Mod 14 p5)_

Two consequences printed on the same page:

- It is **an integral part of network security**, and a **demanding task** within the network security
  operations of organizations. _(Mod 14 p5)_
- **Continuous** network traffic monitoring **and analysis** are required for **effective threat
  detection**. _(Mod 14 p5)_

## Definition and the job it does _(Mod 14 p5)_

**Network traffic monitoring** = *"the process of **capturing network traffic** and **inspecting it
closely** to determine what is happening on the network."* _(Mod 14 p5)_

- Network defender must *"constantly strive to maintain smooth network operation"* — *"If a network
  goes down even for a small period, **productivity within a company may decline**."* _(Mod 14 p5)_
- Goal: *"To be **proactive rather than reactive**"* — traffic movement and performance must be
  monitored to ensure **no security breach** occurs within the network. _(Mod 14 p5)_

### The monitoring chain _(Mod 14 p5)_

```
sniff the traffic flowing through the network
  -> capture network packets
    -> signature analysis
      -> identify any malicious activity
```

- Network operators use **network traffic analysis tools** to identify **malicious or suspicious
  packets hiding within traffic**. _(Mod 14 p5)_
- What they watch: **download/upload speeds · throughput · content · traffic behaviors** — *"to
  understand the status of the network operations."* _(Mod 14 p5)_

## Why existing security tools are not enough _(Mod 14 p6)_

Three gaps, printed as the "Need for Network Monitoring" callout _(Mod 14 p6)_:

| Gap | Printed statement |
|---|---|
| **Bypass** | *"**Even when security tools are in place**, attackers can find ways to **bypass such security mechanisms** to enter the network"* |
| **Signature dependence** | *"Security tools generally use **signature-based detection** techniques. Hence, they are often unable to identify **continuously changing attack signatures/patterns**"* |
| **No behaviour view** | *"Security tools are generally **not designed to identify behavioral anomalies** and are unable to detect activities of attackers that are **initiated before and during an attack**"* |

**The gap in one line:** security tools match *known, static* signatures; monitoring finds
*anomalous conditions* and sees the activity that is **initiated before and during** an attack.

## What monitoring buys the defender _(Mod 14 p6)_

- Identifies **possible issues before they affect business continuity**. _(Mod 14 p6)_
- **Root cause** of a network issue *"can be determined easily"*; with **network automation tools**
  the problem **can be fixed automatically**. _(Mod 14 p6)_
- *"not only **prevents outages** but also gives **visibility to potential issues**."* _(Mod 14 p6)_
- *"**Continuous network monitoring minimizes downtime** and **increases the performance** of the
  network."* _(Mod 14 p6)_
- **"Network monitoring tools provide the first level of security"** and help identify **anomalous
  conditions** in the network, **which indicate attacker activity**. _(Mod 14 p6)_

## Exam angle

- The distinguishing word is **retrospective** — it is the qualifier the exam can test. The same page
  also demands monitoring be *proactive rather than reactive*, so the two words **co-exist** and are
  **not** interchangeable. _(Mod 14 p5)_
- The **first level of security** phrase is the second exam hook: monitoring is the *baseline layer*
  that signature-based tools sit on top of. _(Mod 14 p6)_

## Related

- Advantages list: [[14-LO01b-Advantages-of-Network-Monitoring]]
- The sniffers that do the capture: [[14-LO02a-Network-Sniffers-for-Network-Monitoring]]
- Sniffer mechanics (promiscuous mode, packet capture): [[14-LO02b-How-Network-Sniffers-Work-and-Placement]]
- Security-tool weaknesses in context: [[MOC-Module-03]] · perimeter tooling: [[MOC-Module-04]]






