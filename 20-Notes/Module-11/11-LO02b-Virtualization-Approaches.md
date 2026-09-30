---
type: note
module: "11"
lo: "02"
tags: [concept, mod/11, flashcard/11]
topic: "Virtualization approaches"
exam_weight: unknown
status: done
unresolved: ["For hardware-assisted virtualization the courseware states only that special microprocessor instructions enable the guest OS to execute privileged instructions directly; it does not state whether the guest OS is virtualization-aware, nor what role (if any) the VMM plays."]
---

[[MOC-Module-11]]

# Virtualization Approaches (§11.02)

Four approaches "can be adopted to achieve virtualization". _(Mod 11 p11)_

| | **Full** | **OS-assisted / Para** | **Hardware-assisted** | **Hybrid** |
|---|---|---|---|---|
| Guest OS knows it is virtualized? | **No** | **Yes** | not stated | **Yes** — adopts para-virtualization functionality |
| Resource request goes to | **VMM** | the **host machine** | — | guest *and* VMM |
| Who translates to binary | the **VMM** → forwards to host OS | the **guest OS** itself, for the computer hardware | **no translation step** — special microprocessor instructions | **VMM**, for binary translation to different types of hardware resources |
| VMM in request/response | in the path | **not involved** in the request and response operations | not stated | in the path for binary translation |
| How privileged work runs | — | — | special CPU instructions let the guest OS **execute privileged instructions directly on the processor**; the OS **treats system calls as user programs** | — |

_(Mod 11 pp11–12)_

## Discriminator — who does the translation

| Approach | Translator |
|---|---|
| Full | **V**irtual machine **M**anager |
| Para / OS-assisted | the **G**uest OS |
| Hardware-assisted | the **P**rocessor (no translation) |
| Hybrid | **G**uest (para) *and* **V**MM |

- **Full** — guest OS is not aware it is running in a virtualized environment; it sends commands to the VMM to interact with the computer hardware, the VMM translates those commands to binary instructions and forwards them to the host OS; **resources are allocated to the guest OS through the VMM**. _(Mod 11 p11)_
- **Para** — guest OS is aware of the virtual environment and communicates with the host machine to request resources; the commands are translated into binary code by the **guest OS** for the computer hardware; **the VMM is not involved in the request and response operations**. _(Mod 11 p11)_
- **Hardware-assisted** — modern microprocessor architectures have **special instructions to aid the virtualization of hardware**. _(Mod 11 p11)_
- **Hybrid** — the guest OS **adopts the functionality of para virtualization** *and* **uses the VMM for binary translation** to different types of hardware resources. _(Mod 11 p12)_

## Exam traps
- "Para" ≠ "the VMM translates". Para moves translation **into the guest**; full keeps it **in the VMM**. _(Mod 11 p11)_
- Hardware-assisted is about **CPU instructions**, not about who issues the request. _(Mod 11 pp11–12)_

## Cards

Full virtualization — guest awareness, request path, translator
?
Guest is **unaware**; guest → **VMM** → host OS; the **VMM** translates to binary and forwards, and allocates resources to the guest.

OS-assisted / para virtualization — who translates, and is the VMM involved?
?
The **guest OS** translates its own commands to binary for the hardware; the **VMM is not involved** in the request and response operations.

Hardware-assisted virtualization — what enables it?
?
**Special instructions in modern microprocessor architectures** let the guest OS execute privileged instructions directly on the processor; the OS treats system calls as user programs.

Hybrid virtualization — what does the guest use, and what does the VMM still do?
?
The guest **adopts para-virtualization functionality**; the **VMM is still used for binary translation** to different types of hardware resources.

