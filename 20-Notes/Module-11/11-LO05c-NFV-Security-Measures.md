---
type: note
module: "11"
lo: "05"
tags: [bestpractice, mod/11]
topic: "NFV security measures"
exam_weight: unknown
status: done
unresolved:
  - "The p87-p88 'NFV Security Best Practices' block (hypervisor & virtual network security, Linux kernel security / SELinux / sVirt / hidepid / GRSecurity, hypervisor introspection) is hypervisor-security material that the courseware also covers under LO03. It sits at the end of this LO's page range and is labelled 'NFV Security Best Practices', so it is recorded here; the slice states no reason for the placement."
  - "p86 NFV MANO Security figure names two further measures, 'Implement storage protection' and 'Protect the Scaling and Elasticity of VNF', with no accompanying body text in the slice — no detail, threat or mechanism is given for either."
  - "p82 figure callout 'Mitigation: Ensure hypervisor detects excessive resource consumption' omits the p83 prose requirement to also detect malicious virtual networks; the prose form was used."
  - "The slice uses 'NFVIaaS' and 'VNFaaS' as layer names without defining them; no expansion was guessed."
  - "p87-p88 figure boxes ('Boot Integrity Measurement Leveraging TPM', 'Security Zoning', 'Hypervisor Introspection', 'Hypervisor and Virtual Network Security', 'Linux Kernel Security') are slide callouts; only their body-prose counterparts were used, and the figure's box-to-prose mapping was not inferred."
---

[[MOC-Module-11]]
# NFV Security Measures (§11.05)

## 1 · NFV Infrastructure security _(Mod 11 p82)_

**Domain-level model** — three domains, three different controls:

| Domain | Required measure |
|---|---|
| **Hypervisor** | authentication is **controlled and managed by the virtual machines** → prevents **unauthorized access and data leaks** |
| **Compute** | **encrypt data**; access it **only by the VNFs** sharing the computing resources |
| **Network** | adopt **secure networking techniques — TLS, IPSec, SSH** |

### Specific NFVI strategies _(Mod 11 pp82–83)_
| Strategy | Requirement |
|---|---|
| **Defense-in-depth + well-defined policy enforcement** | required for operating and maintaining **NFVIaaS layer** security |
| **Network isolation and segmentation** | via **VLANs and VXLAN**; safeguards **external VMs from sniffing or monitoring internal traffic** |
| **Security monitoring and intrusion detection** | key countermeasure: **detect threats, identify suspicious events**, minimize attacks on the NFVIaaS layer |
| **Security services on demand** | **firewalls, IDS/IPS, DPI** — minimize malicious-attack risk and enhance security at the **hypervisor and NFVIaaS layer** |
| **Regular VM updates and patches** | maintains a **stable host environment**; safeguards against virtualized attacks such as **hyper jacking and VM DoS** |
| **Protection of the operational interface** | mitigates the **programmable-NIC / partially-hypervisor virtual switch** packet trap & injection issue → **secure packet processing system** monitoring **instruction level operations of the packet processor** |
| **Protection against RFA and resource consumption attacks** | hypervisor detects **excessive resource consumption** and **malicious virtual networks** (malicious **NaaS** providers run DoS and extract secrets) |

Attack side of the last two rows: [[11-LO05b-NFV-Vulnerabilities-and-Attacks]].

## 2 · NFV VNF security measures _(Mod 11 pp84–85)_
| Measure | Why / effect |
|---|---|
| **Trust relationship** across **intra-VNF, inter-VNF and extra-VNF** domains | trust between all VNF instances is evaluated by **policy rules, contracts, guidelines**; it is **not workable if one instance is not faithful** |
| **Secure the network + end-to-end security + authentication** | counters **eavesdropping, spoofing, man-in-the-middle**; use **encryption, policy enforcement, access control, security zoning, segmentation** |
| **Control access when outsourcing workload to a third party** | stop malicious entities spreading malware or gaining unauthorized access |
| **Use TLS protocol (via vTPM)** | secures **live migration** — relocating VNFs without service interruption |
| **Logical isolation** | a VNF instance may try to **exhaust all resources**; isolation improves control and manageability of the **shared infrastructure** |
| **Hide access management from VNFs** | blocks **side-channel attacks** |
| **Monitoring** | lack of control/monitoring leaves the **NFVIaaS and VNFaaS** layers prone to attack; non-transparent monitoring lets an adversary exploit **network services, VNF instances, virtual assets and sensitive data** |

## 3 · NFV MANO security _(Mod 11 p86)_
| Measure | Detail |
|---|---|
| **Secure management, orchestration, automation** | security mechanisms for **all NFV MANO functions** should be **automated and agile** for **quick deployment at different security policy enforcement points (PEPs)** |
| **Ensuring controller availability** | the controller is the **centralized decision point**; if compromised → **wide network impact** → its access must be **stringently monitored and controlled** |
| **Attack on the orchestrator** | adversary **instantiates a modified VNF**, which might **break access privileges and VNF isolation** |
| → mitigations | **predefine user authentication, user privilege control, and network configuration** · implement a **security monitoring system to detect and separate the defective VNF** |
| *Implement storage protection* | figure callout only — no detail in the slice |
| *Protect the scaling and elasticity of VNF* | figure callout only — no detail in the slice |

## 4 · NFV security best practices _(Mod 11 pp87–88)_

**Boot integrity measurement leveraging TPM** _(p87)_ — use a **TPM as a hardware basis of trust**; the **launch control policy (LCP)** requires **validation of the platform measurements**.

### Hypervisor and virtual network security _(p88)_
- **Keep the hypervisor up to date.**
- **Disable all services** and enable only **necessary** ones based on requirements.
- **Strong password policy on the cloud administrator account.**

### Security zoning _(p88)_
- **Separate VM traffic and management traffic** → a compromised VM cannot affect another VM or the host.
- **Group VMs with the same functionalities into specific zones** and **isolate their traffic**.
- **Protect each zone with access control policies and firewalls such as a DMZ** (demilitarized zone).

### Linux kernel security _(p88)_
| Item | Role |
|---|---|
| **SELinux module** in the kernel | **separate the users** in the host virtual environment |
| **sVirt** | a **new form of SELinux**; **separates the VM processes and data files**, safeguarding **Linux-based hypervisors** |
| **`hidepid`, `GRSecurity`** | tools used to **secure the Linux kernel** |

### Hypervisor introspection _(p88)_
- **Identifying abnormal activities in the VMs** is invaluable for enhancing VM security.

### Traditional practices also required for NFV security _(p88)_
| Practice | Detail |
|---|---|
| **Defense in depth** | |
| **Log management** | with **accurate date/time stamps** |
| **Monitor software bugs** | |
| **Layer 2 security** | **isolate VLANs** for secure zones |
| **Layer 3 security** | |
| **Access control** | via **access lists and firewall rules** |
| **IPS/IDS tools** | to secure the network |

VLAN-level detail: [[11-LO03h-VLAN-Security]] · host hardening: [[11-LO03f-Hypervisor-Security]].

## Lock in
1. **VNF = attacker *or* target**; **MANO = centralized control**; the **controller is the single point of wide impact**. _(Mod 11 pp81, 86)_
2. **Three domains → three controls**: hypervisor = VM-controlled authentication · compute = encrypt + VNF-only access · network = `TLS` / `IPSec` / `SSH`. _(p82)_
3. **RFA / NaaS defence sits in the hypervisor**, not in the VNF: detect excessive consumption + malicious virtual networks. _(p83)_
4. **Live migration is protected by `vTPM` over `TLS`.** _(p84)_







