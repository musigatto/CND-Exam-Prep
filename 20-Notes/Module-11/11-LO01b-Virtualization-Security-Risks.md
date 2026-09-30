---
type: note
module: "11"
lo: "01"
tags: [threat, concept, mod/11, flashcard/11]
topic: "Virtualization Security Risks"
exam_weight: unknown
status: done
unresolved:
  - "Cloud service provider APIs risk: courseware states only that using the APIs 'for communication between environments can pose additional risk' - no mechanism, control or example is given in the slice."
  - "p1582 body-text run-on truncated mid-sentence before the 'Workloads of different trust levels located on the same server' entry; the entry text itself is intact on the same page's slide layer."
---

[[MOC-Module-11]]
# Virtualization Security Risks (Â§11.01b)

## Framing _(Mod 11 p7)_

- Premise: virtualization-enabled technologies deliver benefits â€” **secure, agile, dynamic** environments, **increased operational efficiency**, **reduced capital investment in hardware** _(Mod 11 p7)_.
- But security needs and challenges have **evolved along with** the evolution in network management _(Mod 11 p7)_.
- **Traditional security methods and strategies are NOT sufficient in virtualized environments** _(Mod 11 p7)_.
- Root cause of spread: multiple virtualized environments **may be physically collocated within a single host**, and the **isolation of each virtualized environment is software-based** â†’ a breach in security mechanisms can wreak havoc **not just within the virtualized environment, but potentially across the entire targeted host** _(Mod 11 p7)_.
  - Slide form: because virtualized environments are *isolated in nature*, there is a chance of **evading existing security mechanisms** and wreaking havoc across the targeted host â€” within the virtualized environment or **possibly outside** it _(Mod 11 p7)_.
- Virtualized environments are **considered secure**, but **negligence towards security** in them creates a **new set** of challenges and risks _(Mod 11 p7)_.
- Consequence: **careful planning and implementation of virtualization-specific security methods and strategies** is required to reap the flexibility of virtualized networked environments *securely* _(Mod 11 p7)_.
- Adjacent concept: [[11-LO03a-Network-Virtualization-Concepts]].

## Risks associated with virtual environments _(Mod 11 p7â€“p8)_

| # | Risk | What the courseware says it enables |
|---|---|---|
| 1 | **VM sprawling** | VMs are easily created, so their number can grow to the point the administrator can **no longer effectively manage** them; can potentially **increase the number of unpatched VMs** in the network environment _(Mod 11 p7)_ |
| 2 | **Sensitive data within a VM** | VMs move across the network easily â†’ **sensitive data in a VM can be at risk of being compromised** _(Mod 11 p8)_ |
| 3 | **Security of offline and dormant VMs** | May **lag behind the baseline security** of the environment; **if started**, can serve as **potential entry points for breaches** _(Mod 11 p8)_ |
| 4 | **Security of pre-configured/active VMs** | An attacker can **tweak security settings** by gaining unauthorized access to the **hosting platform**, *unless appropriate security is in place* _(Mod 11 p8)_ |
| 5 | **Lack of visibility and control over virtual networks** | **Traditional security protection devices lack visibility of and control over traffic in virtual networks** _(Mod 11 p8)_ |
| 6 | **Resource exhaustion** | **Over-allocation** of virtual environments â†’ **significant performance degradation** and **exhaustion of resources** _(Mod 11 p8)_ |
| 7 | **Hypervisor security** | Unauthorized access can **change the security of a device or server** on the hypervisor â†’ hypervisor is potentially a **single point of failure** for the VMs on the host _(Mod 11 p8)_ |
| 8 | **Account or service hijacking** | The virtual environment and hypervisor are often reached through a **self-service portal**; **compromise of an account** there has **significant consequences for security** _(Mod 11 p8)_ |
| 9 | **Workloads of different trust levels on the same server** | VMs or applications with **sensitive data in workloads are at risk** when workloads of **different trust levels** are **co-located** _(Mod 11 p8)_ |
| 10 | **Cloud service provider APIs** | Using the CSP APIs **for communication between environments** can pose **additional risk** _(Mod 11 p8)_ |

**Recall order** (courseware listing order): **S**prawl â†’ **D**ata-in-VM â†’ o**F**fline/**D**ormant â†’ **P**re-configured â†’ **V**isibility â†’ **R**esources â†’ **H**ypervisor â†’ **A**ccounts â†’ **T**rust levels â†’ cloud **APIs**.

## Cards

```
List the ten risks the courseware associates with virtual environments.
?
VM sprawling; sensitive data within a VM; security of offline and dormant VMs; security of pre-configured/active VMs; lack of visibility and control over virtual networks; resource exhaustion; hypervisor security; account or service hijacking; workloads of different trust levels on the same server; cloud service provider APIs. _(Mod 11 p7-p8)_
```

```
Why can one breach in a virtualized environment spread beyond the VM?
?
Multiple virtualized environments may be physically collocated in a single host and each environment's isolation is software-based - so a breach can wreak havoc across the entire targeted host, possibly outside the virtual environment. _(Mod 11 p7)_
```

```
VM sprawling - courseware definition and consequence?
?
VMs are easily created, so their number can rise to a point the administrator can no longer manage them effectively; it can increase the number of unpatched VMs in the network environment. _(Mod 11 p7)_
```

```
Why are offline and dormant VMs dangerous?
?
They may lag behind the baseline security of the environment and, if started, can serve as potential entry points for breaches. _(Mod 11 p8)_
```

```
Hypervisor security risk - what and why it matters?
?
Unauthorized access to the hypervisor can change the security of a device or server on it, so the hypervisor is potentially a single point of failure for the VMs on the host. _(Mod 11 p8)_
```

```
Account or service hijacking vector in a virtual environment?
?
The virtual environment and hypervisor are often accessed through a self-service portal; compromise of an account on that portal has significant security consequences. _(Mod 11 p8)_
```
