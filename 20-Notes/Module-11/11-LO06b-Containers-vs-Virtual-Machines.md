---
type: note
module: "11"
lo: "06"
tags: [concept, mod/11]
topic: "Containers vs virtual machines"
exam_weight: unknown
status: done
unresolved: ["Fig. p93 'Containers v/s Virtual Machine' and Table 11.2 (same page) contradict each other on Security: the figure gives Container 'Fully isolated (more secure)' and VM 'Process-level isolation (less secure)', while Table 11.2 gives the exact reverse. Both are reproduced as printed; the courseware does not state which is correct.", "Fig. p93 stack diagram is a jumbled OCR label dump; the two stacks below are reconstructed from the labels present (Infrastructure > Host Operating System > Virtual Machines > Guest OS > Bins/Libs, and Infrastructure > Host Operating System > Container Engine (Docker) > Containers > Bins/Libs). The printed left/right and top/bottom placement of each label could not be verified from the slice."]
---

[[MOC-Module-11]]

# Containers vs Virtual Machines (§11.06)

"Containers and virtual machines **decrease resource requirements and increase functionality**." _(Mod 11 p93)_

## Table 11.2 — Containers Vs Virtual Machines _(Mod 11 p93)_

| Attribute | **Container** | **Virtual Machine** |
|---|---|---|
| **Definition** | virtualization based on an operating system, in which the **kernel's operating system functionality is replicated on multiple instances of isolated user space** | an **operating system or application environment that runs on a physical machine** |
| **Type** | **Lightweight**. Provides **OS virtualization** | **Heavyweight**. Provides **virtualization, hardware-level** |
| **Memory space** | **Requires less memory space** | **Requires more memory space** |
| **Security** | **Process-level isolation (less secure)** | **Fully isolated (more secure)** |
| **Start-up time** | **milliseconds** | **minutes** |
| **Operating system** | **host OS is shared** | **each VM has its own OS** |
| **Examples** | **LXC, LXD, CGManager, Docker** | **VMware, vSphere, Virtual Box, Hyper-V** |

## Figure "Containers v/s Virtual Machine" — as printed _(Mod 11 p93)_

| **Container** | **Virtual Machine** |
|---|---|
| Provides **OS-level** virtualization | Provides **hardware-level** virtualization |
| **Lightweight** | **Heavyweight** |
| **All containers share the host OS** | **Each virtual machine runs in its own OS** |
| **Requires less memory space** | **Allocates required memory** |
| **Fully isolated (more secure)** | **Process-level isolation (less secure)** |
| Example: **LXC, LXD, CGManager, Docker** | Example: **VMWare, Hyper-V, vSphere, Virtual Box** |

⚠ **The Security row is swapped between the figure and Table 11.2 on the same page.** The figure credits the *container* with "fully isolated (more secure)"; Table 11.2 credits the *VM*. Both are reproduced as printed — the courseware never resolves it. Everything else agrees, except the memory wording: figure = VM "allocates required memory", table = VM "requires more memory space".

## Stack view _(Fig. p93)_

| VM stack | Container stack |
|---|---|
| Bins/Libs | Bins/Libs |
| Guest OS | Container Engine (Docker) |
| Virtual Machines | Containers |
| Host Operating System | Host Operating System |
| Infrastructure | Infrastructure |

The only OS in the container stack is the **host operating system**; in the VM stack each machine brings its own **Guest OS**. → [[11-LO03c-Hypervisor-Vulnerabilities-and-Attacks]] · [[11-LO03f-Hypervisor-Security]]

## Exam trap

- **"Lightweight / requires less memory / milliseconds / host OS shared" → container.** **"Heavyweight / more memory / minutes / own OS" → VM.** These four pairs are never contradicted.
- The **isolation** claim is the one the courseware prints inconsistently — do not "fix" it, quote the source you are given.






