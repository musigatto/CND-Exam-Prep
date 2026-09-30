---
type: note
module: "11"
lo: "03"
tags: [bestpractice, concept, mod/11, flashcard/11]
topic: "Hypervisor Security"
exam_weight: unknown
status: done
unresolved:
  - "The Hyper-V 'Restrict user access' prose that introduces Figures 11.14-11.19 lies on p43, outside this slice (slice starts p44); p44 opens mid-walkthrough, so only figure captions/instruction lines are available for pp.44-45."
  - "Note on the entry above: the range is now extended to p37, and p43 was re-read - it still ends at Figure 11.13. The 'Restrict user access' prose for Figures 11.14-11.19 is genuinely absent from pp.37-45; only figure captions exist. The original entry is kept as written."
  - "p50: a parameter value '32' is OCR'd after '-MaxChannelPerSession', conflicting with the '16' visible in the Figure 11.28 PowerShell screenshot; intended value unresolved."
  - "p56: VirtualBox flush-level-1-cache command is OCR'd as '-- -- I try' / '--11'; the actual switch name is unreadable and was not guessed."
  - "p56: CPU feature printed as 'AVX, XSVAE, and POPCNT'; 'XSVAE' is an OCR error of unknown target and is kept as printed."
  - "Figure 11.29 (VM settings > VMware Tools) and Figure 11.30 (Encrypt Virtual Machine dialog) are screenshots whose body text did not OCR; only captions and the surrounding prose were used."
  - "p47: Administrative Tools screenshot list is garbled ('Sem ces', 'cs)', '3•'); only the entries referenced by the procedure were used."
  - "p37: the 'Hyper-V Administrators Properties' screenshot (Local Users and Groups > Users list) is image-only; group names and descriptions are garbled ('itsearh es-V Administrators'), so nothing was read from it."
  - "p38: the uncaptioned Windows Features screenshot showing the IUM checkbox is image-only and garbled; the Services screenshot's description column is partially garbled ('Xbox Lwe Game Save ... This service syncs data for Xbox Live sav...', 'This service supports the Xbox Live')."
  - "p39: the PowerShell screenshot of both Set-SmbServerConfiguration variants is garbled ('Set-SmbServerConfiguration PS 32', 'PS C ?\"Mamehannelper Session'); the commands were taken from the p39 prose instead."
  - "p39 resolves the p50 16/32 conflict recorded above: p39 states 16 for the variant that prompts for confirmation and 32 for the -Force variant. The earlier p50 entry is retained rather than deleted - confirm against the PDF before retiring it."
  - "pp.40-41: Figures 11.6 (Hyper-V Manager context menu), 11.7 and 11.8 (Integration Services panels) are screenshots whose body text did not OCR; only captions and surrounding prose were used."
  - "p41 Figure 11.9: only 'Windows Server 2019 Standard Evaluation' and 'Windows License valid for 119 days' were legible; the build string OCR's as '17763.rs5_re1ease1O14-1434 ENG' and was not normalized."
  - "p43: Figure 11.12 (Administrative Tools list) and the adjacent uncaptioned Task Scheduler screenshot (date column OCR'd as '30-10-20' repeated) are image-only; only the caption actions were used."
---

[[MOC-Module-11]]
# Hypervisor Security (§11.03)

Courseware structure: **vendor-specific measures** (Hyper-V → VMware → VirtualBox) then a **general guidelines / best-practices** list. _(Mod 11 p37–p58)_

Hyper-V's five measures, in the order the courseware presents them: **Time synchronization → Set access privileges for users → Disable unnecessary services → Isolated User Mode (IUM) → Enable SMB 3.0**. _(Mod 11 p37–p39)_

## Hyper-V (Windows) hardening _(Mod 11 p37–p50)_

### Time synchronization _(Mod 11 p37, p39–p41)_

- **What it buys**: time synchronization provides **security and event correlation**. _(p37, p39)_
- VMs lose track of time if date and time are **not synchronized between the host machine and the VM**; **saved VMs have incorrect/wrong time when restored** if time is not synchronized. _(p37, p39)_
- When multiple interconnected VMs use time to track transactions, time must be **consistent across all the VMs**. _(p39)_
- Consequence of inconsistency: **authentication failures**; affects security protocols such as **Kerberos**, **certificate-dependent technologies that rely on time synchronization**, and **billing processes**. _(p39)_

| Step | Action | Fig |
|---|---|---|
| 1 | From the Windows **start menu**, open **Hyper-V Manager** on the host machine | 11.5 _(p39)_ |
| 2 | Select the virtual machine, right-click it → **Settings** | 11.6 _(p40)_ |
| 3 | In the **Management** section, select **Integration Services** | 11.7 _(p40)_ |
| 4 | Check **Time synchronization** → **Apply** → **OK** | 11.8 _(p41)_ |
| 5 | Open the VM — its time is now synchronized with the host system | 11.9 _(p41)_ |

### Set access privileges for users _(Mod 11 p37, p41–p43)_

- **Why**: setting access privileges does not only **control access** — it also **reduces the attack surface area, preventing damage from external and internal attacks**. _(p41)_
- **By default Hyper-V comes with a group of admins having all administrative rights for the virtual machines**. _(p37, p41)_
- **Non-admin users who need access**, and **admins who do not need access** to the hypervisor, can be **added or removed as per requirement**. _(p37)_

Reach the management console — Figures 11.10 → 11.13:

| Step | Action | Fig |
|---|---|---|
| 1 | Windows **Control Panel** → **System and Security** | 11.10 _(p42)_ |
| 2 | Under System and Security → **Administrative Tools** | 11.11 _(p42)_ |
| 3 | In Administrative Tools → **Computer Management** | 11.12 _(p43)_ |
| 4 | Under Computer Management → **System Tools** → **Local Users and Groups** | 11.13 _(p43)_ |

### Restrict user access — `Hyper-V Administrators` local group _(Mod 11 p44–p45)_

Walkthrough, Figures 11.14 → 11.19:

| Step | Action | Fig |
|---|---|---|
| 1 | `Computer Management` → `System Tools` → **Local Users and Groups** | 11.14 _(p44)_ |
| 2 | Under Local Users and Groups, click **Groups** | 11.15 _(p44)_ |
| 3 | Navigate to **Hyper-V Administrators**, double-click it, click **Add** | 11.16 _(p44)_ |
| 4 | **Add Members to Hyper-V Administrators** → select object type `Users` | 11.17 _(p45)_ |
| 5 | In `Select Users`, under "Enter the object names to select", enter the user for setting privilege access → **Check Names** | 11.18 _(p45)_ |
| 6 | Select the user → **OK** to set access privilege | 11.19 _(p45)_ |

### Disable unnecessary services _(Mod 11 p46–p48)_

- **Why**: disable unnecessary Windows services so computer resources are not wasted and the system runs smoothly. By default Windows runs unnecessary services, which can affect performance. _(Mod 11 p46)_
- **Microsoft recommendation** — disable these services **and their respective scheduled tasks** on **Windows Server 2016**: _(Mod 11 p46)_
  - `Xbox Live Auth Manager`
  - `Xbox Live Game Save`
- Procedure: Control Panel → `System and Security` _(Fig 11.20, p46)_ → `Administrative Tools` _(11.21, p46)_ → `Services` _(11.22, p47)_ → select the service, double-click _(11.23, p47)_ → `General` tab → **Startup type → Disabled** → `Apply` → `OK` _(Fig 11.24, p48)_

### Isolated User Mode (IUM) _(Mod 11 p48–p49)_

| Property | Statement | Ref |
|---|---|---|
| Introduced for | **Windows 10 Enterprise** and **Windows Server 2016** | _(p48)_ |
| Type | **virtualization-based security** feature that uses **secure kernels** | _(p48)_ |
| Effect | separates **business data and processes** from the operating system | _(p48)_ |
| Siblings | alongside **Credential Guard** and **Device Guard** | _(p48)_ |
| Stops | **pass-the-hash** attacks; lets defenders change **application control policy** | _(p48)_ |
| Protects against | cyber criminals who infiltrate and download malicious applications | _(p48)_ |

Enable: Control Panel → `Programs` _(Fig 11.25, p48)_ → `Programs and Features` → **Turn Windows features on or off** _(11.26, p49)_ → scroll to **Isolated User Mode** → check → `OK` → **reboot** _(Fig 11.27, p49)_

### SMB 3.0 file shares _(Mod 11 p49–p50)_

- SMB 3.0 file shares = shared storage for **Hyper-V (Windows Server 2012 and 2012 R2)**. _(p49)_
- Storeable on it: **configuration files**, **virtual hard disk (VHD) files**, **snapshots**; accessed over the **SMB 3.0 protocol**. _(p49)_
- Works with **standalone and clustered** file servers that use Hyper-V and shared file storage. _(p49)_
- Enable: `Set-SmbServerConfiguration -MaxChannelPerSession 16` in PowerShell; confirm with `Y` (Yes) or `A` (Yes to All) + `Enter`. Add **`-Force`** to run without the confirmation message. _(Mod 11 p49–p50, Fig 11.28)_
- The **no-confirmation** variant is stated as `-MaxChannelPerSession 32 -Force` — i.e. **16** belongs to the variant that prompts, **32** to the `-Force` variant. _(Mod 11 p39)_

## VMware hypervisor security _(Mod 11 p51–p54)_

| Measure | Detail | Ref |
|---|---|---|
| **Time synchronization** | VMs may show **time drift / time lag** vs the **hosting machine** clock → forensic investigation may not find the needed data. VMware supplies a sync option. | _(p51–p52)_ |
| **Restrict user access** | A **group** = users sharing a common set of rules and permissions; the same permissions apply to all members. **Only groups with permissions can access a virtual machine.** | _(p51, p53)_ |
| **Encrypting guest VMs** | Encryption restricts access by users **without privileges** / unprivileged actions. Decryption uses the password given at encryption time. **The decryption password and the VM password need not be the same.** | _(p52–p53)_ |

**Time sync** _(Mod 11 p52–p53, Fig 11.29)_: open the VM → right-click `Virtual Machine` tab → `Virtual Machine Settings` → `Options` tab → `VMware Tools` → in the VMware Tools Features pane check **"Synchronize guest time with host"** → `OK`.

**Add users individually to a group (ESXi)** _(Mod 11 p53)_:
1. Log in to **ESXi** using the **vSphere client**
2. `Local Users & Groups` tab → `Users`
3. Right-click the user → `Edit` (opens **Edit User** dialog)
4. Enter the **Username**; in **Change password** section add a new password
5. To add the user to a group: pick the group in the **Group** drop-down → `Add`
6. Enter the **Group** name, select a user to add to that group → `OK`

**Encrypt a guest VM** _(Mod 11 p54, Fig 11.30)_: open the VM → right-click `Virtual Machine` tab → `Virtual Machine Settings` → `Options` → **Access Control** → in the **Encryption** section click `Encrypt…` → in **Encrypt Virtual Machine** enter **Password** + **Confirm the password** → `Encrypt` → `OK`. Dialog also shows a **"Require user to change encryption password when this virtual machine is moved or copied"** option.

## VirtualBox hypervisor security _(Mod 11 p55–p56)_

| Measure | Reason | Cost / effect | Ref |
|---|---|---|---|
| **Disable nested paging** | VMM then validates each entry before shadowing → guest cannot insert **inappropriate entries into the page tables** → secures the VirtualBox environment | Makes CPU features **AVX, XSVAE, POPCNT** unavailable to guests → stability issues, especially during **SMP** configuration | _(p55–p56)_ |
| **Disable hyperthreading** | Removes potentially sensitive data from affected buffers that **leak information between the threads**. Required for hosts affected by **CVE-2018-12126** and **CVE-2018-12127** | `VBoxManage modifyvm --mds-clear-on-vm-entry` clears the affected buffer on every VM entry; may reduce performance — impact depends on the workload | _(p55–p56)_ |
| **Flush level 1 cache data** | While executing guest code, sensitive data must be removed from the **L1 cache**. **Prerequisite: CPU microcode must be up to date** (traditionally done by system firmware; some OSes install it automatically) | `VBoxManage modifyvm <switch unreadable>` flushes the L1 data cache on every VM entry; may reduce performance | _(p55–p56)_ |

Nested paging background: it implements memory management in hardware, removing the overheads of VM exits and page table accesses, so the guest handles paging **without hypervisor intervention** — a task that is not meant to be performed by virtualization software. _(Mod 11 p55–p56)_

## Additional hypervisor security guidelines / recommendations / best practices _(Mod 11 p57–p58)_

1. Install all updates to the hypervisor when the vendor releases them.
2. Restrict administrative privileges to the **hypervisor management console**.
3. Synchronize the virtualized infrastructure to a **trusted authoritative time server**.
4. Protect the hardware hosting the VMs by **disconnecting unused physical hardware** from the host machine.
5. Disable all unnecessary hypervisor services such as **clipboard or file-sharing** between the guest OS and the host OS.
6. Monitor the security of **each guest OS** using tools.
7. Monitor the security of **activities between guest OSes** using tools.
8. Monitor the hypervisor for **signs of compromise**.
9. Improve **visibility and controls over virtual networks**.
10. Use **SMB** for transferring data — provides **end-to-end encryption** and protects data from **eavesdropping** attacks. _(slide text names SMB 3.0)_
11. Configure the **built-in hypervisor firewall** to allow **only necessary ports and protocols**.
12. To protect the hypervisor and enforce traffic control, use a **dedicated virtual network segment**.
13. Establish **multiple communication paths** within the host to communicate from VMs to the physical network.
14. Set **traffic rate limit** specifications in the hypervisor to **prevent DoS attacks**.

Concept background for hypervisor-driven exposure lives in [[11-LO03a-Network-Virtualization-Concepts]].

## Cards

Front: Inconsistent time between Hyper-V guests and the host causes what failures?
?
Authentication failures, and it affects security protocols such as Kerberos, certificate-dependent technologies that rely on time synchronization, and billing processes. Time sync also provides security and event correlation. _(Mod 11 p37, p39)_

Front: How is time synchronization enabled in Hyper-V?
?
Windows start menu → Hyper-V Manager → select the VM → right-click → Settings → Management section → Integration Services → check Time synchronization → Apply → OK. _(Mod 11 p39–p41)_

Front: Besides controlling user access, what does setting Hyper-V access privileges achieve?
?
It reduces the attack surface area, preventing damage from external and internal attacks. By default Hyper-V provides a group of admins with all administrative rights for the VMs. _(Mod 11 p41)_

Front: Set-SmbServerConfiguration: which -MaxChannelPerSession value is paired with -Force?
?
32 with -Force; 16 is the variant that prompts for confirmation. _(Mod 11 p39)_

Front: Name the three VMware hypervisor security measures.
?
Time synchronization · Restrict user access · Encrypting guest virtual machines. _(Mod 11 p51–p52)_

Front: Which two Windows services must be disabled on Windows Server 2016, and what else alongside them?
?
Xbox Live Auth Manager and Xbox Live Game Save — plus their respective scheduled tasks. _(Mod 11 p46)_

Front: Isolated User Mode: what is it and which two Windows virtualization-security siblings share its role?
?
A virtualization-based security feature using secure kernels, separating business data/processes from the OS. Siblings: Credential Guard and Device Guard. Stops pass-the-hash attacks. _(Mod 11 p48)_

Front: How is the VMware decryption password related to the VM password?
?
They need not be the same. _(Mod 11 p52–p53)_

Front: Which CVE IDs make disabling hyperthreading mandatory on affected hosts?
?
CVE-2018-12126 and CVE-2018-12127. _(Mod 11 p56)_

Front: What is the stated trade-off of disabling nested paging in VirtualBox?
?
It makes AVX, XSVAE and POPCNT unavailable to guests, causing stability issues (especially during SMP configuration). _(Mod 11 p56)_
