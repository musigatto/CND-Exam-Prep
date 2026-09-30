---
type: note
module: "11"
lo: "05"
tags: [concept, mod/11, flashcard/11]
topic: "NFV concepts and components"
exam_weight: unknown
status: done
unresolved:
  - "p79 NFV architecture figure: box labels are OCR-unreliable ('Virtual Com ute' for Virtual Compute, 'Virtual Stora' for Virtual Storage, 'NFV Infrastructure (NFVI' unterminated). Only the labels recorded in this note were used; no layer order, box nesting or box-to-component mapping was inferred from the image."
  - "p79 figure lists 'Virtual Compute / Virtual Storage / Virtual Network' inside NFVI, while the p79 body prose lists virtual resources as 'virtual networks, virtual storages, and virtual servers'; how the two lists correspond is not stated."
  - "p79 figure shows no Orchestrator box although the p80 prose names the Orchestrator as one of MANO's three components; the figure's EMS box is drawn as a peer of NFVI / VNFs / MANO while the prose introduces EMS inside the VNF element — whether EMS is a fourth principal element alongside the three named in the prose is not stated."
  - "p79 figure wording differs from the prose: 'run in software on standardized hardware' (figure) vs 'runs them as software in virtual resources' (prose), and 'MANO is the management system for NFVI' (figure slide)."
---

[[MOC-Module-11]]
# NFV Concepts and Components (§11.05)

## LO scope
Explain **NFV** and its **components**; the same objective also covers **vulnerabilities and attacks** ([[11-LO05b-NFV-Vulnerabilities-and-Attacks]]) and **security measures per component** ([[11-LO05c-NFV-Security-Measures]]). _(Mod 11 p78)_

## What NFV is
| Aspect | Courseware |
|---|---|
| Definition | **network virtualization approach** that **decouples network functions from proprietary hardware appliances** |
| What it runs on | network functions run as **software on standardized hardware**, in **virtual resources** |
| Decoupled NFs | **firewalls · traffic control · virtual routing** — previously bound to physical devices |
| Payoff | **minimizes OPEX and CAPEX** · **easy deployment of new services** |
| Interoperability | **NFVI standards enhance the interoperability of VNF components** |

_(Mod 11 p79)_

## Three principal elements
`NFVI` → `VNF` → `MANO` — EMS is introduced alongside the VNF element. _(Mod 11 pp79–p80)_

### 1 · NFVI — NFV Infrastructure
- **Main component** of the NFV architecture: all the **hardware and software** components on which VNFs are deployed. _(Mod 11 p79)_

| NFVI subpart | Content |
|---|---|
| **Hardware resources** | hardware of **network devices, servers, storage**, etc. — used by VNFs |
| **Virtualization layer** | the layer **containing the hypervisor** in which virtualization is implemented |
| **Virtual resources** | **virtual networks · virtual storages · virtual servers** |

_(Mod 11 p79)_

### 2 · VNF — Virtualized Network Functions
- **Implementation of software** for the virtualization of network functions **on virtual resources**; VNFs handle the specific network functions running in VMs. _(Mod 11 p79)_
- **VNF (Virtual Network Function)** = the virtualized network function. Example: virtualize a router → a **VNF router**. VNFs are **deployed on VMs**. _(Mod 11 p79)_
- **Deployment shape** _(Mod 11 pp79–p80)_:
  - a VNF can be deployed on **multiple VMs**, each VM hosting a **single function** of the VNF, **or**
  - the **entire VNF** can be deployed on a **single VM**.
- **EMS — Element Management System** _(Mod 11 p80)_:
  - handles VNF management functions: **accounting · configuration · performance · security management**
  - uses a **proprietary interface** to manage the VNF
  - **multiple VNFs can be managed by a single EMS**

### 3 · MANO — NFV Management and Orchestration
- **Communicates with the NFVI and VNF layers**; manages the **resources of NFVI** and the **allocation of VNFs**. _(Mod 11 p80)_
- Combines with the operator's **decoupled OSS (operation support subsystem) or BSS (business support system)** using **standard interfaces**. _(Mod 11 p80)_

| MANO component | Job |
|---|---|
| **VIM** — Virtualized Infrastructure Manager | control and manage the communication **from the VNF to computing, storage, and network resources**, along with virtualization |
| **VNF Manager (VNFM)** | VNF **life-cycle actions**: **updates · query · installation · termination · scale-up/down** |
| **Orchestrator** | controls **orchestration**; manages **software resources** and the **NFV infrastructure** |

_(Mod 11 p80)_

## Labels recovered from the p79 architecture figure
- **NFV OSS/BSS Layer** (top band in the figure)
- **NFV Infrastructure (NFVI)** → `Hardware Resources`, `Virtualization Layer`, `Virtual Compute`, `Virtual Storage`, `Virtual Network`
- **Virtualized Network Functions (VNFs)**, **Element Management System (EMS)**
- **NFV Management Orchestration** → `VNF Manager (VNFM)`, `Virtualized Infrastructure Manager (VIM)`

Figure slide captions: NFV *"is a network virtualization approach that decouples the network functions from proprietary hardware appliances so that they can run in software on standardized hardware"*; MANO *"is the management system for NFVI"*. OCR of the diagram is garbled — see `unresolved`. _(Mod 11 p79)_

## Lock in
1. **Decoupling** from proprietary appliances is what produces the **OPEX/CAPEX** and fast-deployment benefits. _(p79)_
2. **VNF ≠ VM** — a VNF may span many VMs (one function each) or sit wholly on one VM. _(pp79–p80)_
3. **EMS = proprietary interface; MANO↔OSS/BSS = standard interfaces.** _(p80)_
4. **Only the Orchestrator manages software resources**; **VNF Manager owns life-cycle actions**; **VIM owns compute/storage/network resource communication**. _(p80)_

## Cards

Courseware definition of NFV
?
A network virtualization approach that **decouples network functions from proprietary hardware appliances** so they run as software on standardized hardware / in virtual resources. Decoupled functions named: firewalls, traffic control, virtual routing. Benefit: minimizes OPEX and CAPEX, enables easy deployment of new services.

Three principal elements of the NFV architecture
?
**NFVI** (infrastructure) · **VNFs** (virtualized network functions) · **NFV MANO** (management and orchestration).

Three subparts of NFVI
?
**Hardware resources** (network devices, servers, storage) · **Virtualization layer** (contains the hypervisor) · **Virtual resources** (virtual networks, virtual storages, virtual servers).

EMS: what does it manage and over what kind of interface?
?
Accounting, configuration, performance and security management of a VNF, over a **proprietary interface**; a single EMS can manage **multiple VNFs**.

MANO's three components and their jobs
?
**VIM** — control/manage communication from the VNF to computing, storage and network resources plus virtualization · **VNF Manager** — life-cycle actions: updates, query, installation, termination, scale-up/down · **Orchestrator** — controls orchestration, manages software resources and NFV infrastructure.

How is a VNF deployed onto VMs, and how does MANO reach the operator's OSS/BSS?
?
A VNF can run on **multiple VMs** (one function per VM) or **entirely on a single VM**. MANO combines with the decoupled **OSS/BSS** using **standard interfaces**.
