---
type: note
module: "11"
lo: "05"
tags: [threat, mod/11]
topic: "NFV vulnerabilities and attacks"
exam_weight: unknown
status: done
unresolved:
  - "p81 'NFV Vulnerabilities and Weaknesses' figure: label groups are partly garbled ('Conventional attacks Outside Control plane attacks Third party networks Noisy neighbor Shared resources Multi tenancy issues Attacks Conventional attacks Orchestration and control plane attacks Inside'). The inside/outside attack split printed in the figure for NFVI and VNF could not be read reliably, and no box-to-row mapping was inferred from the image; figure-only terms are kept in a separate table."
  - "p81 figure lists 'Third party networks', 'Noisy neighbor' and 'Multi tenancy issues' under VNF, and 'Inconsistent orchestration and nt' (truncated 'management') plus 'Compromised policies and isolation' under MANO; the body prose repeats most but not all of these — the figure-only extras are flagged as such."
  - "p84 figure: the four callout headings and the four attack/mitigation rows are the same rotated callout box; pairing them by order (third-party outsourcing → malware injection, live migration → control of the migrated service, noisy neighbor → resource exhaustion, side-channel → GnuPG key extraction) matches the body prose but the OCR does not preserve the visual mapping."
  - "p82 figure callout 'Mitigation: Ensure hypervisor detects excessive resource consumption' is truncated relative to the p83 prose, which also requires the hypervisor to detect malicious virtual networks."
  - "The slice uses the terms 'NFVIaaS' and 'VNFaaS' for the two layers without defining them; no expansion was guessed."
---

[[MOC-Module-11]]
# NFV Vulnerabilities and Attacks (§11.05)

**Each component of an NFV is vulnerable to various attacks.** Attack surface is stated per component: **NFVI · VNF · MANO**. _(Mod 11 p81)_

## Per-component vulnerability / attack matrix _(Mod 11 p81)_

### NFVI
| | Items |
|---|---|
| **Entry point** | NFVI resources used by VNFs are **managed by a VIM**, which can itself be a target of attacks |
| **Vulnerabilities** | **shared resources · insecure interfaces · improper control and monitoring · design flaws · improper security enforcements** |
| **Attacks** | **conventional attacks (DoS/DDoS) · manipulation of VM OS · data destruction · hypervisor level attacks · hardware attacks** |
| **Impact** | adversary targets **hypervisor** vulnerabilities → compromises **confidentiality, integrity, and availability** of the VNFs' resources |

### VNF
| | Items |
|---|---|
| **Dual role** | a VNF can be the **source** of an attack **or** the **target** |
| **Why** | a VNF is a **vendor-provided software component** → can carry **software vulnerabilities**, or **may even be malware designed to execute an attack** |
| **Vulnerabilities** | **software crashes · software design flaws · software bugs** |
| **At-risk resources** | **shared resources · third party networks · other tenants in the server** |

### MANO
| | Items |
|---|---|
| **Entry point** | adversary **eavesdrops or modifies** communications **within an NFV MANO** and the **traffic between the NFVI and the NFV MANO** |
| **Vulnerabilities** | **inconsistent orchestration and management · insecure interfaces · data theft · compromised policies · isolation** |
| **Attacks** | **conventional attacks · orchestration and control plane attacks** |
| **Target** | the adversary targets the **orchestrator** or the **VNF manager** to affect **network services or individual VNFs** |

## Figure-only labels (p81) — not repeated in the body prose
| Block | Labels recovered from the figure |
|---|---|
| VNF | conventional attacks · control plane attacks · third party networks · **noisy neighbor** · shared resources · **multi tenancy issues** |
| MANO | inconsistent orchestration and management · insecure interfaces · data theft · compromised policies and isolation |

The figure also prints **Inside / Outside** groupings next to the attack lists for NFVI and VNF; the mapping could not be read reliably — see `unresolved`. _(Mod 11 p81)_

## Named attacks and their stated mitigations
| Attack / vector | What the attacker does | Stated mitigation |
|---|---|---|
| **Operational interface** — NIC with **programmable cards** + **virtual switch implemented partially in the hypervisor** _(p82)_ | **Traps the packets of the host** or **generates malicious packets** that lead to **network congestion or packet retransmission** _(p82–p83)_ | Implement a **secure packet processing system** to monitor the **instruction level operations of the packet processor** _(p82–p83)_ |
| **Resource Freeing Attacks (RFA)** and **Resource Consumption Attacks** _(p82)_ | **Malicious Network-as-a-Service (NaaS) providers** conduct **DoS attacks** and **extract secret information** _(p83)_ | Hypervisor must detect **excessive resource consumption** *and* **malicious virtual networks** _(p83; figure p82 gives the truncated "excessive resource consumption" form)_ |
| **Outsourced workload to a third party** _(p84)_ | Gains control of services and **compromises confidentiality by injecting malware** | **Control the entry of third parties**; prevent malicious entities from spreading malware or gaining unauthorized access _(p84)_ |
| **Live migration** — relocating VNFs without service interruption _(p84)_ | Gains control of the **migrated service** between hypervisors | **vTPM (virtual trusted platform module)** that **uses the TLS protocol** for confidentiality and authentication _(p84)_ |
| **Noisy neighbour** _(p84)_ | A VNF instance **attempts to exhaust all the resources** of the shared system | **Logical isolation** — improves control and manageability of the shared infrastructure system _(p84)_ |
| **Side-channel attack** _(pp84–85)_ | Attacker VM **extracts a private ElGamal decryption key** from a **co-resident victim VM running Gnu Privacy Guard (GnuPG)** | **Hide access management from the VNFs** — if access management is visible to the VNF the adversary may gain control of the service _(p85)_ |

## Reading notes
- **VNF egress attacks** named in prose: **eavesdropping, spoofing, man-in-the-middle** against VNF applications. _(Mod 11 p84)_
- **VNF network attacks in the figure** add **control plane attacks**, **noisy neighbor**, **multi-tenancy**. _(p81)_
- Mitigation-side measures are collected in [[11-LO05c-NFV-Security-Measures]]; component definitions in [[11-LO05a-NFV-Concepts-and-Components]].







