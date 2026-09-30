---
type: note
module: "11"
lo: "03"
tags: [concept, mod/11, flashcard/11]
topic: "Virtual Network Types and Placements"
exam_weight: unknown
status: done
unresolved:
  - "p25 final sentence is truncated in the OCR to the fragment '...e manufacturers work on embedding their technology into hypervisor network topologies.' The full claim about hardware manufacturers and hypervisor network topologies is not recoverable and was omitted."
---

[[MOC-Module-11]]
# Virtual Network Types and Placements (§11.03)

## Where the software sits — the placement decision _(Mod 11 p19, p20)_

Virtual network software is used for virtual networking. It is placed **either inside (internal) or outside (external) the virtual server**, chosen *based on the **size and type of the virtualization platform*** _(Mod 11 p19, p20)_.

```
Virtual Networks are categorized into:
  Outside a virtual server  ->  External Virtual Networks
  Inside  a virtual server   ->  Internal  Virtual Networks          _(Mod 11 p20)_
```

## Side-by-side _(Mod 11 p21, p25)_

| | **Internal virtual network** | **External virtual network** |
|---|---|---|
| Placement | **Inside** the virtual server _(p20)_ | **Outside** the virtual server _(p20)_ |
| Scope | Communication **between VMs on the same system** _(p21)_ | **Multiple physical LANs** ↔ virtual network; or one physical LAN split into **isolated** virtual networks _(p25)_ |
| Software | The **hypervisor** acts as the virtual network software _(p21)_ | Virtualization **software modules on managed/intelligent (layer 3) switches** abstracting physical switch ports and the surrounding network _(p25)_ |
| Granularity | Server **or cluster** level _(p21)_ | **Routers and switches** must support virtualization while connecting multiple systems _(p25)_ |
| Build | Single system configured with **containers** (e.g. domains) clubbed with hypervisor control programs or **pseudo-interfaces** (e.g. virtual network interface cards / vNICs) → *network in a box* _(p21)_ | VLAN + switch technology: systems physically on the same LAN can be configured into different virtual networks; systems on **separate** LANs can be combined into one VLAN spanning the corporate network _(p25)_ |
| Role | Provides the **abstraction layer** enabling different internal virtual network types to **mimic physical networks** _(p21)_ | Increases efficiency of a corporate network or **data center** _(p25)_ |

## Internal virtual network — detail _(Mod 11 p21)_

- Networking functionality for **VM↔VM communication on the same system**; creates a **purely software-based logical network** between the VMs.
- Emulates network connectivity **within** the server, enabling hosted VMs to **exchange data**.
- Can be created on a **single system**; enhances single-system efficiency by **isolating applications to separate containers or pseudo-interfaces**.
- Offered by various software vendors.

### Hypervisor = the internal virtual network software _(Mod 11 p21)_

A hypervisor is **software that runs and manages virtual machines** _(Mod 11 p22)_.

**Vendor products named** _(Mod 11 p22–p23)_

| Product | Slice-stated highlight |
|---|---|
| **VMware ESXi** | Partitions hardware to consolidate applications, cuts cost; installs **directly onto a physical server**; direct access to/control of underlying resources; centralized management cuts CapEx/OpEx; minimized hardware footprint |
| **Citrix Hypervisor 8.2** (formerly **XenServer**) | Virtualization management platform optimized for application, desktop and server virtualization infrastructure |
| **Virtual Iron** (`oracle.com` / `virtualiron.fr`) | Enterprise-class server virtualization + virtual infrastructure management; unmodified Windows/Linux workloads; policy-based automation |
| **Microsoft Hyper-V Server** | Creates/manages VMs; multiple OSes on one physical computer, isolated from each other |
| **VirtualBox** | x86 and AMD64/Intel64 product; enterprise + home; free **Open Source**, **GPL version 2** |

### Internal virtual network worked example — VMware ESX Server 3 _(Mod 11 p24)_

- **Production-proven, enterprise-class *type-I* hypervisor**; runs on **bare metal** (directly on a physical machine).
- Key component of the VMware Infrastructure suite; replaces Service Console with a rudimentary OS; integrates a **Linux kernel (`vmkernel` / virtualization layer)**.
- Abstracts **processor, memory, storage, networking** resources → provisioned to multiple VMs.
- Boot/runtime: `vmkernel` starts first → loads virtualization components incl. ESX; service console invokes the Linux kernel as the **primary VM**; normally `vmkernel` runs on the bare computer and the **service console runs as the first virtual machine**.
- Diagram topology: physical network cards → **ESX Server 3 layer** hosting the virtual networking split; **virtual switches** connect VMs and the service console to each other and to external networks.
- `vmkernel` manages **resource allocation** *and* **secure isolation of traffic** meant for different VMs.

## External virtual network — detail _(Mod 11 p25)_

- Combines multiple physical LANs into one virtual network, **or** subdivides a physical LAN into multiple virtual networks **isolated from each other**.
- Requires **external virtual network software + network resources**; **routers and switches must support virtualization** while connecting multiple systems.
- **Layer 3 intelligent/managed switches** run the virtualization software modules that abstract the physical switch ports and surrounding network — the hardware↔software relationship is what makes external NV possible.
- Standard example: **VLAN + switch technology**.

### Layer 3 intelligent/managed switch vendors cited _(Mod 11 p26–p27)_

| Vendor | Slice-stated highlight |
|---|---|
| CISCO | Affordable, easy install/use, ideal for SMBs |
| MOXA | Industrial-grade reliability; **security enhancements based on the IEC 62443 standard**; EN 50155 (rail), IEC 61850-3 (power automation), NEMA TS2 (transportation) |
| NETGEAR | Fully managed switches across core/distribution/access; NMS300 single-pane-of-glass management |
| LINKSYS | Advanced network management, traffic-handling intelligence, network security features, fiber-optic expansion |
| tp-link | L3 routing, physical stacking, optional redundant external power unit |
| Buffalo | Gigabit smart switches, plug-and-play, auto-sensing ports |
| HP | Enterprise-edge resiliency/security; IRF stacking, static RIP, **OSPF, BGP, IS-IS**, PoE+, **ACLs**, IPv6; optional HP IMC management |
| D-Link | Large IP routed networks / network core; dynamic routing, advanced QoS, stackable, 10 Gb uplinks |

## Cards

```
What determines whether virtual network software goes inside or outside the virtual server?
?
The size and type of the virtualization platform. Software placed inside = Internal Virtual Network; outside = External Virtual Network. _(Mod 11 p19, p20)_
```

```
Which component acts as the virtual network software for an internal virtual network?
?
The hypervisor — it provides the abstraction layer that lets internal virtual network types mimic physical networks, and implements virtualization at the server or cluster level. _(Mod 11 p21)_
```

```
What hardware/software relationship makes external network virtualization possible?
?
Managed/intelligent (layer 3) switches run virtualization software modules that abstract the physical switch ports and the surrounding network. _(Mod 11 p25)_
```

```
Which virtualization type combines multiple physical LANs into one, or subdivides one physical LAN into isolated virtual networks?
?
External network virtualization (e.g. VLAN + switch technology). _(Mod 11 p25)_
```

```
Which hypervisor products does the courseware list, and what licence is VirtualBox under?
?
VMware ESXi, Citrix Hypervisor 8.2 (formerly XenServer), Virtual Iron, Microsoft Hyper-V Server, VirtualBox — VirtualBox is free open source under GPL version 2. _(Mod 11 p22–p23)_
```

```
How does VMware ESX Server 3 start up, and which component runs as the first VM?
?
The vmkernel starts first and loads the virtualization components; the service console invokes the Linux kernel as the primary VM and runs as the first virtual machine. Type-I, bare metal. _(Mod 11 p24)_
```