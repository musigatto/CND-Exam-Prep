---
type: note
module: "11"
lo: "02"
tags: [concept, tool, mod/11]
topic: "Virtualization components and enablers"
exam_weight: unknown
status: done
unresolved: ["In the p14 components figure the 'Management Server' and 'Management Console' labels and their captions are interleaved out of order by the OCR; the table here follows the unambiguous body list.", "PDF p15 carries only a MITRE-sourced pull quote and no other body text or figure content."]
---

[[MOC-Module-11]]

# Virtualization Components and Enablers (§11.02)

## Components _(Mod 11 p14)_

| Component | Definition |
|---|---|
| **Hypervisor / Virtual Machine Monitor (VMM)** | application **or firmware** that enables **multiple guest OSes to share a host's hardware resources** |
| **Guest machine** | independent instance of an OS created by the VMM; with the resources provided it **works as if it were an actual physical machine** |
| **Host / physical machine** | real physical machine providing computing resources to support guest machines; **the server component of the virtual machine** |
| **Management Server** | virtualization platform components that **directly manage the VMs** and **simplify the administration of resources** |
| **Management Console** | component used to **access, configure and use the management interface** of the virtualization product |
| **Network Components** | components for **creating a virtual network to support VMs** — firewalls, load balancers, storage, switches, network interface cards, etc. |
| **Virtual Storage** | components that **abstract physical storage into a single storage device**, letting the multiple systems on the host machine **share the available storage among themselves** |

Layer view in the figure: Apps → guest OS → **VMM / Hypervisor** → **physical machine (host)** → virtual network. _(Mod 11 p14)_

**Bridge** — virtualization "has moved beyond just server and storage capacities and now encompasses the **network** as well." _(Mod 11 p15)_

## Enablers _(Mod 11 p16)_

**Network Virtualization (NV)** · **Software Defined Network (SDN)** · **Network Function Virtualization (NFV)** — "technologies by which virtualization can be realized" and the **key enablers responsible for creating virtual environments**.

| Claim | Detail |
|---|---|
| What they produce | **logical and virtual networks decoupled from the underlying network hardware** |
| How they compose | those virtual networks **integrate with virtual environments** |
| How they run | **independently over a physical network in a hypervisor** |
| Plane split | **SDN and NFV are responsible for decoupling the control and forwarding planes** |
| End state | SDN + NFV **combine hardware and software to create a completely software-defined network** |
| Payoff | **simpler provisioning and management** of network resources; **key role in virtualization** |

_(Mod 11 p16)_

## Trap
Only **SDN and NFV** are credited with decoupling the control and forwarding planes — **NV is not** named for that. All three are enablers of creating virtual environments. _(Mod 11 p16)_







