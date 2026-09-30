---
type: note
module: "11"
lo: "04"
tags: [concept, mod/11, flashcard/11]
topic: "SDN Concepts and Benefits"
exam_weight: unknown
status: done
unresolved: []
---

[[MOC-Module-11]]
# SDN Concepts and Benefits (§11.04)

## What SDN is

| Framing | Statement |
|---|---|
| Network virtualization | Centralizes the **network controller** by **separating the network's control functions from its packet forwarding functions** |
| Network framework | Centralizes control of a network by separating control functions from **data-packet forwarding** functions; centralizes **intelligence** and **reduces complexity** of the traditional architecture for apps/services |
| Network management | An **approach to network management that differs from traditional network management** |

_(Mod 11 p63, p64)_

Adoption driver: rapid growth in **multimedia content, cloud computing, mobile technology** → enterprises, carriers and service providers switching to SDN for **consistency in managing the network and devices across the entire network**. _(Mod 11 p63, p64)_

## Three layers

| Layer | Content |
|---|---|
| **SDN Application** | Programs that communicate with the SDN controller through **SDN APIs**; all the applications and services that run on the network |
| **SDN Controller** | Centralized seat of control — the "**brain** of the network"; a *logical* entity that transfers information from SDN apps to networking components, and extracts/transfers information from hardware devices to SDN apps |
| **SDN Networking Devices** | Switches, routers + supporting hardware; regulate the **forwarding and data processing** capabilities |

_(Mod 11 p64)_

## Conceptual components

| Component | Function |
|---|---|
| **Data Plane** | Packet forwarding according to instructions stored in **flow tables** |
| **Control Plane** | Abstract view of the network — **the network model** |
| **Application Plane** | Supports different applications such as **routing, load balancers, monitoring, security**; communicates with the applications and business logic "**above**" |
| **Northbound API** | Connects the SDN application layer ↔ SDN controller; enables communication between network services and business applications; communicates with the applications and business logic "above" |
| **Southbound API** | Connects the SDN controller ↔ SDN networking devices; relays information from network services to devices such as switches and routers "**below**" |
| **OpenFlow** | Protocol used to manage the **southbound interface** of the SDN |

_(Mod 11 p64, p65)_

Wiring: `Applications —Northbound API→ Controller —Southbound API→ Network Elements` _(Mod 11 p64)_

## Benefits (as listed)

| # | Benefit |
|---|---|
| 1 | Provides **central view** of the network |
| 2 | Enables management of network devices — **physical and virtual switches** — from a **central controller** |
| 3 | Enhances network **scalability and reliability** |
| 4 | Provides **central security control** across the organization |
| 5 | Enables **abstraction of cloud resources** |
| 6 | Implements **quality of service (QoS) for voice over IP and multimedia transmissions**, by **controlling data traffic** |
| 7 | Implements **whitelist security model** |
| 8 | Optimizes organization's **applications, services, and infrastructure** |
| 9 | Reduces **operation costs** |

_(Mod 11 p66)_

## Benefits (named + rationale)

**Network Programmability** — operator can introduce new services and write programs by utilizing **SDN APIs to control network behavior**. _(Mod 11 p66)_

**Logically centralize intelligence and control** —

| | Traditional | SDN |
|---|---|---|
| Control architecture | **Distributed** control architecture | **Logically centralized** network topologies |
| Awareness of network state | Only a **low level** of awareness | Enables **intelligent control and management** of network resources |

_(Mod 11 p66)_

**Abstraction of the network** — services and applications are **abstracted from the underlying technologies** and communicate with the network via **APIs**. _(Mod 11 p66)_

**Openness** — a **common software environment** to run network services and applications. Open APIs support **OSS/BSS, SaaS, cloud orchestration, and business-related applications**. _(Mod 11 p66)_

## Cards

SDN definition — control plane vs forwarding
?
Network virtualization approach that centralizes the network controller by separating the network's control functions from its packet forwarding functions

Three SDN architecture layers
?
SDN Application layer · SDN Controller · SDN Networking Devices

SDN conceptual components (6)
?
Data Plane · Control Plane · Application Plane · Northbound API · Southbound API · OpenFlow

Which SDN benefit delivers voice-over-IP / multimedia QoS?
?
Implements quality of service (QoS) for voice over IP and multimedia transmissions, by controlling data traffic

SDN vs traditional control architecture
?
Traditional = distributed control architecture with only low-level awareness of network state. SDN = logically centralized network topologies enabling intelligent control and management of network resources

SDN "Openness" benefit — which application classes do the open APIs support?
?
OSS/BSS, SaaS, cloud orchestration, and business-related applications
