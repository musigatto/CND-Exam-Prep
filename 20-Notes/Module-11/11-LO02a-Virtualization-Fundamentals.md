---
type: note
module: "11"
lo: "02"
tags: [concept, mod/11, flashcard/11]
topic: "Virtualization fundamentals"
exam_weight: unknown
status: done
unresolved: ["Figure 11.1 / Figure 11.2 diagram text is scrambled in the OCR (layer labels come through as word salad); the layer order used in the comparison table is taken from the surrounding body prose, not from the figures.", "Courseware states a single OS 'completely utilizes the available 32-bit hardware infrastructure' (p11) but never explains why 32-bit; significance is not given anywhere in this slice."]
---

[[MOC-Module-11]]

# Virtualization Fundamentals (§11.02)

## LO scope
Explain **virtualization concepts** · the **types** of virtualization · the **components** · the **enablers** of virtualization technology. _(Mod 11 p9)_

## Definitions
| | Courseware wording |
|---|---|
| Core | software-based **virtual representation** of an IT infrastructure — network, devices, applications, storage, etc. _(Mod 11 p10)_ |
| Mechanism | creation of **virtual**, as opposed to actual/physical, versions of computer resources in which **software simulates the functionality of hardware** _(Mod 11 p10)_ |
| Framework effect | **divides** physical resources (traditionally bound to hardware) into **multiple individual simulated environments** _(Mod 11 p10)_ |

**Cardinality works both ways** _(Mod 11 p10)_:
- N virtual resources ← **one** physical resource
- **one** virtual resource ← one or more physical resources

**Payoff** — operate **multiple operating systems** and execute **numerous applications on a single server** → enhances efficiency and the scale of the economy of the organization. _(Mod 11 p10)_

## Traditional vs virtualization architecture

| | Traditional (Fig 11.1) | Virtualization (Fig 11.2) |
|---|---|---|
| OS instances | a **single** operating system | **multiple sets** of virtual OSes (guest OSes) + their applications |
| Stack shape | Apps → OS → hardware | Apps → guest OSes → **virtualization layer** → hardware |
| Hardware utilisation | that one OS + its apps **completely utilizes the available 32-bit hardware infrastructure** | hardware platform (host machine) runs all guest OS sets |
| Resource request path | **host OS directly** interacts with the hardware to request system resources | **host OS directly**; **guest OSes interact through the virtualization layer** |
| Partitioning | — | virtualization layer **logically partitions** hardware resources based on requests from the **host and guest** OSes |

_(Mod 11 pp10–11)_

- Virtualization layer = **middleware between the operating systems and the computer hardware**. _(Mod 11 p11)_

## Lock in
1. **Only the host OS touches hardware directly.** Guest OSes reach hardware only via the virtualization layer. _(Mod 11 p11)_
2. The virtualization layer's job is **logical partitioning on request** — it is driven by resource requests from *both* host and guest OSes. _(Mod 11 p11)_

## Cards

Courseware definition of virtualization
?
Software-based **virtual representation** of an IT infrastructure (network, devices, applications, storage, etc.); the framework divides physical resources into multiple individual simulated environments.

Who converts commands to binary instructions in full virtualization?
?
The **VMM** — it translates the guest's commands to binary instructions and forwards them to the host OS; resources reach the guest through the VMM.

In the virtualization architecture, who interacts with the hardware directly?
?
The **host OS**. The **guest OSes interact through the virtualization layer**, which acts as middleware and logically partitions hardware resources.

Cardinality rule for virtual vs physical resources
?
N virtual resources may be created from **one** physical resource, **or** one virtual resource from **one or more** physical resources.

