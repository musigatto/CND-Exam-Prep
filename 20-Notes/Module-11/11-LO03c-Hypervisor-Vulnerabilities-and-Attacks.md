---
type: note
module: "11"
lo: "03"
tags: [threat, mod/11, flashcard/11]
topic: "Hypervisor Vulnerabilities and Attacks"
exam_weight: unknown
status: done
unresolved:
  - "p30 printed table 'Vulnerabilities: Hypervisor/VMM' is flattened by OCR: its columns (Vulnerability | Threat: Disclosure/Deception/Disruption | Weakness | Consequence) could not be mapped cell-for-cell, so the page narrative text was used to build the table below."
  - "p30 table fragments 'Guest machines gain unauthorized privileges' and a second 'Bypassing security restrictions resulting in privilege escalation' cell have no recoverable threat-class column in the OCR; which of Disclosure/Deception/Disruption they belong to is not stated in recoverable text."
  - "The p30 cell 'Cross-site scripting attack on an administration console results in stealing victim's authentication cookies' was paired with the Deception row because p31 lists 'Cross site scripting' under Deception; the original cell adjacency was lost in OCR."
  - "Fig 11.4 (p28, VLAN topology) and Fig 11.5 (p39, 'Search for Hyper-V Manager') are image-only - no OCR text of their contents beyond stray labels; Fig 11.4 readable labels only: LAN / Physical LAN / VLAN / Switch / 802.1Q Trunk / VLAN 100."
---

[[MOC-Module-11]]
# Hypervisor Vulnerabilities and Attacks (§11.03)

## Why the hypervisor is the target _(Mod 11 p30)_

- **Fundamental component of virtualized systems** → *frequently targeted in attacks*.
- Vulnerabilities attach to its **security features**: **VM isolation** and **internal software-based channels** for communication with VMs.
- Common weaknesses/vulnerabilities affect **hypervisors, VMMs, and their management tools**.
- Classification axis: **potential threat** × **weakness** involved.
- Threat classes used in this table: **Disclosure · Deception · Disruption** _(p30 header; no Usurpation column, unlike the virtual-network table on p32)_

## Disclosure _(Mod 11 p30)_

| Weakness / vulnerability | What it does | Stated impact |
|---|---|---|
| **Improper input validation in hypervisor** — e.g. in the **Xen** hypervisor, when the **intercept function** in a software library uses an **improper range** | Local HVM guests read data from the hypervisor or other guest machines | Disclosure + **DoS / crash of the host** |
| **Data handling issues due to off-by-one error** (an iterative loop iterates too many or too few times) in a software function | Local users obtain **sensitive information from hypervisor memory** | Disclosure + **DoS / crash of the host** |
| **Data handling in memory** — stale data in a **segment register** | Local guests obtain **critical data from the hypervisor stack content**; guest OS users can change the address used in **memory mappings** and read from / write to **arbitrary memory** | Unauthorized read/write of hypervisor memory |

## Deception _(Mod 11 p31)_

Listed weaknesses: **improper input validation, configuration, and access control** · **cross site scripting** · **improper certificate validation, permission, and privilege management** · **race conditions**.

| Vector | Mechanism | Stated impact |
|---|---|---|
| **Race conditions** | Exploits the **time gap between the application of a security control and the execution of the service** | Bypassing security restrictions → **privilege escalation, disclosure, disruption, usurpation** |
| **Cross-site scripting** on an **administration console** | — | Attack on the admin console **steals the victim's authentication cookies** _(cell text on p30)_ |
| **Improper certificate validation, permission and privilege management** | — | **Privilege escalation** |

## Disruption / VM escape _(Mod 11 p31)_

| Vector | What it does | Stated impact |
|---|---|---|
| **Improper input validation, resource management errors** → **VM escape** | Attackers can **run code on a VM to directly communicate with the hypervisor**, by exploiting **hypervisor coding or management errors** | Exploiting a **guest OS** to cause **DoS**, **out-of-bounds writes**, **crash the guest**, and **execute arbitrary code** |
| **Injection** in hypervisor software libraries | Local guest users inject against the hypervisor's software libraries | **DoS and crash of the host** via a **non-canonical guest address** |

## Reading the VM escape chain _(Mod 11 p30, p31)_

```
guest code on a VM
   -> exploit hypervisor coding / management error  (improper input validation,
                                                      resource management errors)
   -> run code on the VM, talk DIRECTLY to the hypervisor
   -> escape the guest: DoS | out-of-bounds writes | guest crash | arbitrary code
```

Injection variant: `local guest` → `hypervisor software library` → **DoS / host crash** (`non-canonical guest address`).

## Figures in this page range _(Mod 11 p28, p39)_

- **Fig 11.4** (p28) — VLAN topology illustration; labels OCR'd: `LAN`, `Physical LAN`, `VLAN`, `Switch`, `802.1Q Trunk`, `VLAN 100`.
- **Fig 11.5** (p39) — "Search for Hyper-V Manager" screenshot (Hyper-V Manager start-menu path). Image-only.

## Cards

```
Name the three threat classes the courseware uses to classify hypervisor/VMM vulnerabilities.
?
Disclosure, Deception, Disruption. _(Mod 11 p30)_
```

```
Which hypervisor security features do its vulnerabilities attach to, and what else is affected besides the hypervisor itself?
?
VM isolation and the internal software-based channels used to communicate with VMs; the weaknesses also affect VMMs and their management tools. _(Mod 11 p30)_
```

```
Give the Xen example of improper input validation in the hypervisor and its impact.
?
The intercept function in a software library uses an improper range → local HVM guests read data from the hypervisor or other guest machines; can also cause DoS or crash the host. _(Mod 11 p30)_
```

```
What is an off-by-one error in the hypervisor's data handling, and what does it expose?
?
An iterative loop iterates too many or too few times → local users obtain sensitive information from hypervisor memory; can also cause DoS or crash of the host. _(Mod 11 p30)_
```

```
Define VM escape per the courseware and list its consequences.
?
Attackers run code on a VM to directly communicate with the hypervisor, exploiting hypervisor coding or management errors → DoS, out-of-bounds writes, guest crash, and execution of arbitrary code. _(Mod 11 p31)_
```

```
How does injection in hypervisor software libraries hurt, and what address type is named?
?
Local guest users cause DoS and crash the host via a non-canonical guest address. _(Mod 11 p31)_
```