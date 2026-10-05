---
type: note
module: "11"
lo: "03"
tags: [concept, mod/11]
topic: "Network Virtualization Concepts"
exam_weight: unknown
status: done
unresolved: []
---

[[MOC-Module-11]]
# Network Virtualization Concepts (§11.03)

## Definition _(Mod 11 p17, p18)_

- **NV** = process of combining all available network resources, enabling network defenders to share them among network users under a **single administrative unit**.
- **Abstraction**: resources traditionally allocated as *actual hardware* are abstracted into *software*.
- Two directions: **many physical → one** virtual software-based network · **one physical → many** separate independent virtual networks.
- **Bandwidth**: available bandwidth split into **independent channels**, assigned or reassigned to a server/device **in real time**.
- **Location independence**: a VLAN can unite network devices into one unit **irrespective of physical location** — creating a subsection of the LAN _(p18 example)_.
- Access: files, folders, computers, printers, hard drives — from any user's system.

## Advantages / benefits _(Mod 11 p18)_

Side panel — *Benefits of Network Virtualization*:

| # | Benefit |
|---|---|
| 1 | Efficient, flexible, scalable network usage |
| 2 | Logically segregates the **underlay administrative** domain from the **overlay** domain |
| 3 | Automates network and security protocols |
| 4 | Security by **resource isolation** |
| 5 | Enhanced application delivery, reduced overall cost |

Body text — *key advantages*:

| # | Advantage |
|---|---|
| 1 | Efficient, flexible, scalable usage of the network |
| 2 | Logically segregates the underlay administrative domain with the overlay domain |
| 3 | **Accommodates the dynamic nature of server virtualization** |
| 4 | Security and **isolation of traffic and network details** from one user to another |

## Virtual network = end product of NV _(Mod 11 p19)_

- **Software-based** network; consolidates virtualized network resources into **one administrative unit**.
- Lets **domains** reach a physical network over a **single network interface**; eases interaction with remote systems.
- Usually configured through a **virtual switch**; several virtual network devices connect to it.
- Anatomy: each virtual network in an **NVE** = collection of **virtual nodes** + **virtual links**; a **subset** of the underlying physical network resources.
- Purpose: well-organized networking structure for applications hosted by the data center / service provider network + controlled, secure sharing of networking resources between systems and users.

**Stack** (Fig 11.3) _(Mod 11 p19–p20)_

```
Virtual Network          <- software-based, end product
•••••••••••••••••
Virtualization Layer
•••••••••••••••••
Physical Layer
```

## Virtual network examples (courseware list) _(Mod 11 p19)_

`VLAN` · `VSN` (virtual service network) · `VPN` (virtual private network) · `Active and programmable networks` · `Overlay networks`





