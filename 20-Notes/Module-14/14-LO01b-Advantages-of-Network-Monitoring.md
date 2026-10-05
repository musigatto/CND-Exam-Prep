---
type: note
module: "14"
lo: "01"
tags: [process, bestpractice, mod/14]
topic: "Advantages of network monitoring"
exam_weight: unknown
status: done
unresolved:
  - "p7 the advantage labelled 'Proactive' says network monitoring 'proactively detects applications that consume the maximum bandwidth and reduces the bandwidth'. The mechanism by which bandwidth is reduced is not stated; reproduced verbatim."
  - "p7 the four advantages are printed as a headed run-in list, not a numbered table, and the last one ('Minimizing risk') carries over onto p8. The grouping into four is the page's own; no ordering priority is claimed."
  - "p7 the callout list ('Monitoring network traffic helps in ...') and the body list ('The traffic statistics from network traffic analysis helps in ...') overlap only partially; neither is stated to be a subset of the other."
---

[[MOC-Module-14]]

# Advantages of Network Monitoring (§14.01b)

> **LO#01: Understand the Need for and Advantages of Network Traffic Monitoring** _(Mod 14 p4)_
> Covers pp7–8 — the advantage list.

## What the analysis is for _(Mod 14 p7)_

- **Network traffic analysis** = *"performed to gain **in-depth insight** into the **types of network
  packets or data** flowing through a network."* _(Mod 14 p7)_
- Done *"Typically … through **network monitoring** or **network bandwidth monitoring** utilities."_
  _(Mod 14 p7)_

### What the traffic statistics yield _(Mod 14 p7)_

- **Understanding and evaluating network utilization**
- **Determining download/upload speeds**
- **Determining the type, size, origin, destination, and content/data of packets**

### What monitoring network traffic helps in _(Mod 14 p7 callout)_

- **Understanding how data flows** in a network
- **Optimizing network performance**
- **Avoiding bandwidth bottlenecks**
- **Detecting signs of malicious activity**
- **Finding unnecessary and vulnerable applications**
- **Investigating security breaches**

## The four advantages _(Mod 14 pp7–8)_

| # | Advantage | What the courseware claims it delivers |
|---|---|---|
| 1 | **Proactive** | *"proactively detects applications that consume the **maximum bandwidth** and **reduces the bandwidth**"*; **manages server bottleneck** situations and other systems connected to the network; delivers an **efficient quality of service** to users; *"creates a **record of all the irregularities** occurring in the network that network defender can handle later"* |
| 2 | **Utilization** | Gives **complete details on the infrastructure**; *"an idea about the **amount of load a network can handle** during periods of **heavy traffic**"* → **efficient utilization of the space** in the network. Motivation printed: *"important to understand the need … especially with all the **new and evolving technology**"* |
| 3 | **Optimization** | Gathers **network infrastructure information in a timely manner** and **saves it** for the network defenders, who *"can then take the required actions **before the situation worsens**"*; **identifies applications that prove vulnerable** to the network |
| 4 | **Minimizing risk** | Necessary for establishing **service-level agreements (SLAs)** and **compliance** applicable to users or consumers. *"**Complete infrastructure information** is required when drafting SLAs"*; **real-time monitoring of network topologies and channels** helps in creating the SLAs |

Mnemonic: **P-U-O-M** — Proactive · Utilization · Optimization · Minimizing risk.

## The closing claim _(Mod 14 p8)_

- Network monitoring techniques are **beneficial for network defenders**.
- *"They are **very easy to setup and implement**, considering the **complexity of networks**."*
  _(Mod 14 p8)_

> Note the tension, printed on the same page: monitoring is easy to deploy, yet the four advantages
> above (load limits, bottleneck handling, SLA drafting) assume the defender first *knows* the
> infrastructure in detail. No reconciliation is given.

## Exam angle

- The **only** advantage that mentions a formal artifact is **Minimizing risk** → **SLAs** and
  **compliance**. That is the discriminable answer candidate. _(Mod 14 p8)_
- **Proactive** is the only advantage whose text names an **irregularity record** kept for later
  handling. _(Mod 14 p7)_
- The two six-item lists on p7 are **different lists** — memorise them separately; neither is
  presented as a subset of the other.

## Related

- Why it is needed at all: [[14-LO01a-Network-Traffic-Monitoring-and-Its-Need]]
- Utilities that produce these statistics: [[14-LO02a-Network-Sniffers-for-Network-Monitoring]]
- Bandwidth/performance monitoring detail: performance is the module's LO#05 topic, not these pages.






