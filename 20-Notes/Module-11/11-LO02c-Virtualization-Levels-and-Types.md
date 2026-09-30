---
type: note
module: "11"
lo: "02"
tags: [concept, mod/11, flashcard/11]
topic: "Virtualization levels and types"
exam_weight: unknown
status: done
unresolved: ["PDF p13 opens mid-sentence ('...accesses the desktop, but are instead stored in the cloud.'); that page carries only the tail of Desktop Virtualization, no figure and no further list content.", "The slice names exactly four levels and four types of virtualization; whether these lists are exhaustive is not stated."]
---

[[MOC-Module-11]]

# Virtualization Levels and Types (§11.02)

Two **separate** taxonomies. Do not merge them. "The design of a virtual environment may incorporate **several levels** of virtualization." _(Mod 11 p12)_

## A. Levels of virtualization — *where* in the stack _(Mod 11 p12)_

| Level | What is virtualized | Key mechanism / marker |
|---|---|---|
| **Storage Device** | storage devices | techniques: **data striping** and **data mirroring**. **RAID** is the example — multiple storage devices combined into a **single logical unit** |
| **File System** | data at the **file-system level** | eases **sharing and protection of data within the software**; **virtualized data pools manipulate files and data on user demand** |
| **Server** | the server's **operating system environment** | **logical partitioning of the server's hard drive** |
| **Fabric** | virtual devices made **independent of the physical computer hardware** | **massive pool of storage areas** for the VMs on the hardware; **SAN** achieves fabric-level virtualization |

→ [[10-LO06b-RAID-Technology]] · [[10-LO06c-SAN-and-NAS-Storage]] · [[MOC-Module-10]]

## B. Types of virtualization — *what is being virtualized* _(Mod 11 pp12–13)_

| Type | Mechanism | Stated benefit |
|---|---|---|
| **Operating System** | hardware executes **multiple OSes simultaneously**; done **directly in the kernel** | run apps needing different OSes on one system; **reduces hardware cost**; **saves time updating software on multiple machines** |
| **Network** | creates an **abstraction of network resources** (real hardware was directly visible/allocated in traditional networks) | multiple physical networks **combined into one** software-based virtual network, **or** one physical network **divided into multiple independent** virtual networks |
| **Server** | abstraction of server resources: **physical servers, processors, operating systems** | **multiple VMs on a single server**, each working **independently** and running **its own OS** |
| **Desktop** | the OS instance representing the user's desktop sits **in a central server on the cloud**; hosted on a **remote central server (could be a cluster)**, accessed through a server | user controls the cloud desktop and uses **any device** to access it; **data/files are not on the user's system but in the cloud**; **reduces cost of ownership and downtime**, enables **centralized management**, **may enhance security** |

## Trap: "Server Virtualization" is in both lists — different meanings

| | As a **level** _(p12)_ | As a **type** _(p12)_ |
|---|---|---|
| Server Virtualization | logical partitioning of the server's **OS environment / hard drive** | abstraction of **servers, processors, OSes** into multiple independent **VMs**, each with its own OS |

_(Mod 11 p12)_

## Cards

Levels of virtualization — list the four
?
**Storage Device** (striping/mirroring; RAID) · **File System** · **Server** (partition of the server OS environment / hard drive) · **Fabric** (virtual devices independent of physical hardware; SAN).

Which technologies achieve fabric-level virtualization, and what do they create?
?
**SAN** (storage area network); a **massive pool of storage areas** for the different VMs on the hardware, with virtual devices independent of the physical computer hardware.

Types of virtualization — list the four
?
**Operating System** · **Network** · **Server** · **Desktop**.

Network virtualization — the two directions
?
Multiple physical networks **combined into a single software-based virtual network**, **or** a single physical network **divided into multiple independent virtual networks**. Both are an abstraction of network resources.

Desktop virtualization — where does the desktop and the data live?
?
The desktop OS instance lives in a **central server on the cloud** (hosted on a remote central server, possibly a cluster) and is accessed from **any device**; the data and files are **not stored on the user's system** but in the cloud.

