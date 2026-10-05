---
type: moc
module: "11"
tags: [concept, mod/11]
topic: "Module 11 — Enterprise Virtual Network Security"
exam_weight: unknown
status: done
unresolved:
  - "PDF p3 (book p1577) objective list omits the LO#06 number entirely: the line reads 'Discuss OS virtualization security' with no 'LO#06:' prefix, while LO#01–05 and LO#07–09 are numbered. Confirmed as LO#06 by the p89 (book p1663) section header. The same p3 prose list has 8 items and omits NFV security entirely, so NFV appears in the numbered list but not the prose list."
  - "PDF p156 (book p1730) expands the acronym as 'Network Defined Functions (NFV)'. Every other occurrence in the module is 'Network Function Virtualization'. Recorded as the PDF's own wording; not corrected in notes that quote it."
  - "Per-module exam blueprint weights are not stated in the courseware. Domain weights are sourced separately in [[quiz.html]]; the bank uses a flat 5 items per module."
  - "Placement of the p88 block (hypervisor/virtual-network security, security zoning, SELinux/sVirt, hidepid/GRSecurity, hypervisor introspection) is ambiguous: it sits at the end of LO05's page range but is thematically hypervisor security, which the courseware also covers under LO03. Carried in [[11-LO05c-NFV-Security-Measures]] by page position, not by theme."
---

[[MOC-Module-10]]

# Module 11 — Enterprise Virtual Network Security

> [!abstract] Scope
> 9 LOs · PDF pp. 4–157 (book pp. 1578–1731) · 36 notes · 207 cards.
> Evolution of network/security management in virtualized environments → essential virtualization
> concepts (definitions, 4 approaches, 4 levels, 4 types, components, enablers) → **network
> virtualization (NV)** security → **SDN** security → **NFV** security → **OS virtualization =
> containers** security → container hardening → Docker hardening → Kubernetes hardening.
> The module's spine is *concept → vulnerability/attack → security measure*, repeated for
> NV, SDN, NFV, containers, Docker, and Kubernetes.

## Sections
| LO   | §    | Section                                                  | PDF pp. | Book pp.   |
| ---- | ---- | -------------------------------------------------------- | ------- | ---------- |
| LO01 | 11.1 | Security Management in Virtualization-Enabled IT Environments | 4–8     | 1578–1582  |
| LO02 | 11.2 | Essential Virtualization Concepts                       | 9–16    | 1583–1590  |
| LO03 | 11.3 | Network Virtualization (NV) Security                     | 17–62   | 1591–1636  |
| LO04 | 11.4 | Software-Defined Network (SDN) Security                 | 63–77   | 1637–1651  |
| LO05 | 11.5 | Network Function Virtualization (NFV) Security           | 78–88   | 1652–1662  |
| LO06 | 11.6 | OS Virtualization Security *(= containers)*              | 89–110  | 1663–1684  |
| LO07 | 11.7 | Security Guidelines, Recommendations, and Best Practices for Containers | 111–118 | 1685–1692 |
| LO08 | 11.8 | Security Guidelines, Recommendations, and Best Practices for Dockers    | 119–129 | 1693–1703 |
| LO09 | 11.9 | Security Guidelines, Recommendations, and Best Practices for Kubernetes | 130–157 | 1704–1731 |

## Technical focus

- **LO01 management evolution → risks:** traditional model = evaluation → selection → procurement → installation → configuration → maintaining security; it fails on **geographic expansion · dynamic throughput** (commerce/media/voice/mobile/IoT) · **protracted procurement cycles** (remote install) · control of resources + policy enforcement · **increasingly disaggregated** networks; limited dynamic provisioning/de-provisioning and policy modification → shift to **SDN + NFV**, claimed benefits: flexibility, **centralized control**, fine-grained policy, protection of data and applications, improved management of processing demand via **network automation**, enhanced efficiency. → **10 risks**: VM sprawling · sensitive data in a VM · security of **offline and dormant** VMs · security of pre-configured/active VMs · lack of visibility/control over virtual networks · resource exhaustion · hypervisor security · account or service hijacking · **workloads of different trust levels on one server** · **cloud service provider APIs**. Framing: traditional methods insufficient; isolation is **software-based** so a breach can spread across the whole physical host.

- **LO02 concepts:** def = software-based virtual representation; software simulates hardware; many virtual resources from one physical resource **or vice versa**. Architecture: traditional = single OS on 32-bit hardware directly; virtualized = **virtualization layer as middleware** between guest OSes and hardware, logically partitioning resources. **4 approaches — discriminator is *who translates to binary*:** **Full** (guest unaware; guest → **VMM** → host OS; VMM translates and allocates) · **OS-assisted / Para** (guest aware; **guest OS** translates; **VMM not involved** in request/response) · **Hardware-assisted** (**special CPU instructions**; guest executes privileged instructions directly; OS treats system calls as user programs) · **Hybrid** (guest adopts para-functionality **and** VMM still does binary translation). **4 levels (*where*):** Storage Device (striping/mirroring; RAID) · File System (virtualized data pools) · Server (logical partitioning of the server OS environment / hard drive) · Fabric (devices independent of physical hardware; massive storage pool; **SAN**). **4 types (*what*):** Operating System (multiple OSes simultaneously, **in the kernel**) · Network (abstraction of network resources; combine N physical → 1 virtual **or** split 1 physical → N independent) · Server (servers/processors/OSes → independent VMs, each its own OS) · Desktop (OS instance in a **central cloud server**, any device, data in the cloud). **Trap: "Server Virtualization" is in both lists with different meanings.** Components: **Hypervisor/VMM · guest machine · host · management server · management console · network components · virtual storage**. Enablers: **NV · SDN · NFV** — decouple control and forwarding planes, hardware + software → completely software-defined network.

- **LO03 NV security (largest LO, 46 pp, 30 figures):** NV = combine all available network resources, share among users under **one administrative unit**; abstract traditionally-allocated hardware into software; **split bandwidth into independent channels assigned/reassigned in real time**; VLAN unites devices into one unit irrespective of physical location. Virtual network = end product; examples VLAN, virtual service network, virtual private network, active and programmable networks, **overlay networks**. Placement: **external** virtual networks (software **outside** a virtual server) vs **internal** (software **inside**) — decided by the size/type of the virtualization platform; internal "network in a box" = containers + hypervisor control programs + **pseudo-interfaces (vNICs)**; products VMware **ESX Server 3**, VirtualBox (`x86 and AMD64/Intel64`); external via **Layer 3 intelligent/managed switches**. **Attacks** use the same 4 threat classes throughout: **Disclosure · Deception · Disruption · Usurpation**. **VLAN attacks:** MAC flooding (CAM table overflow → flood out all VLAN ports) · ARP attack (fake ARP → poison table) · DHCP starvation · multicast brute-force (leak frames across VLANs) · **two VLAN-hopping paths** = incorrectly configured **trunk port** spoofing a switch to emulate **802.1Q** and **DTP**, and **spanning-tree attack** (grab port ID → send STP topology-change-ack BPDUs as new root with lower priority → install/transmit junk data). Security: **Hyper-V** — time synchronization, set access privileges, **disable unnecessary services**, **Isolated User Mode (IUM)**, **SMB 3.0**, `Hyper-V Administrators` group; **VMware**; **VirtualBox**; then guidelines. Plus **security zoning** (separate VM traffic from management traffic; group same-functionality VMs into zones; protect each with ACLs and firewalls such as a **DMZ**), **SELinux** module, **sVirt** (new form of SELinux separating VM processes and data files), **hidepid** / **GRSecurity**, **hypervisor introspection** (identify abnormal VM activity).

- **LO04 SDN security:** SDN = network management approach differing from traditional; **consistent management across the entire network**; **logically centralized** intelligence and control vs the traditional **distributed** control architecture; **central view**; manage physical + virtual switches from a central controller; **SDN APIs** for programmability; **whitelist** security model; QoS for VoIP/multimedia; abstract cloud resources; cut operational cost. **Attacks by component impacted** — **Data Plane** has exactly 3: **Device Attack** (software/hardware vulns of the SDN switch — firmware, **TCAM**) · **Protocol Attack** (network-protocol vulns of the forwarding device) · **Side Channel Attack** (deduce forwarding policy by packet-processing timing analysis). Also **Southbound API**, **Control Plane**, **Northbound**, **Application Plane**. **Measures:** authenticate + encrypt app→controller, secure coding for northbound, secure internet-facing web apps; data plane **TLS** device↔agent↔controller, shared secret or **nonces** to stop replay, **SNMPv3 not SNMPv2c**, **SSH not telnet**, password/shared-secret auth of tunnel endpoints + DCI protocol; controller kept updated, RBAC, logging/audit trails; **out-of-band (OOB) network** to separate control traffic from primary data flows.

- **LO05 NFV security:** 3 principal elements — **NFVI** (infrastructure), **VNF** (virtualized network functions), **MANO** (management and orchestration). Attacks: programmable NIC cards, virtual switch partly **in the hypervisor** → trap or generate malicious packets; **Resource Freeing Attacks (RFA)** and **Resource Consumption Attacks**; malicious **NaaS** providers doing DoS and extracting secrets; **side-channel** — attacker VM extracts a private **ElGamal** decryption key from a **co-resident victim VM running GnuPG** → mitigation **hide access management from the VNFs**. Measures per domain: **hypervisor** domain (authentication controlled/managed by the VMs) · **compute** domain (encrypt data, access only by VNFs sharing compute) · **network** domain (secure networking techniques). **MANO**: automate security for all MANO functions for quick deployment at different **policy enforcement points (PEPs)**; ensure **controller availability** (centralized decision point — compromise has wide impact); attack on the **orchestrator** → predefined user authentication + privilege control + network config + security monitoring to detect and separate defective VNFs; storage protection; protect scaling/elasticity. Module summary adds: implement a **secure packet processing system** monitoring **instruction-level operations of the packet processor**.

- **LO06 containers (= OS virtualization):** def — host OS kernel "virtually replicated in multiple instances of isolated user space, called **containers, software containers, or virtualization engines**". **CaaS**; orchestration = automated lifecycle + dynamic environment management; orchestrators **Docker Swarm, OpenShift, Kubernetes**; five-tier architecture; two container types. **Container vs VM (Table 11.2):** container = **OS-level**, lightweight, share the host OS, less memory, process-level isolation, "fully isolated (more secure)", LXC/LXD/CGManager/Docker · VM = **hardware-level**, heavyweight, each runs its own OS, VMware/Hyper-V/vSphere/VirtualBox. **Docker networking:** control plane (client/daemon/REST API over Unix sockets or a network interface); **CNM**; **native drivers H·B·O·MAC·N** = **Host** (uses the host networking stack) · **Bridge** (a Linux bridge is created on the host, managed by Docker) · **Overlay** (container-to-container over the physical network infrastructure) · **MACVLAN** (container interfaces ↔ parent host interface or sub-interfaces) · **None** (container implements its own stack, isolated from the host's); **remote drivers** (community/vendors); **IPAM drivers** (default subnets/IP addressing; manual assignment via the network, container and service create commands); **CNM** objects **Sandbox / Endpoint / Network**. **Kubernetes architecture:** control plane = **kube-apiserver · etcd · kube-scheduler · kube-controller-manager · cloud-controller-manager** (`-cloud-provider external` disables cloud loops); node = **kubelet · kube-proxy · container runtime** (Docker, CRI-O, CRI); 7 features (service discovery, load balancing, storage orchestration, automated rollouts/rollbacks, automatic bin packing, self-healing, secret and configuration management). **12 container security challenges** + risks by image / registry / orchestrator / container / host OS. Attacks: escaping, cross-container, inner-container, registry; **data exfiltration** (reverse shell to C2, network tunneling), cryptomining, network/port scanning, file-system compromise.

- **LO07 container hardening:** image security · **runtime** security · **secrets** (never environment variables, never baked into images, log all secret operations, secure channel transfer, encrypt and decrypt with the container private key, third-party secret stores, **rotate periodically, revoke immediately if exposed**); closing best-practice list incl. do not trust a container's software, control root access, lock down the OS, trusted registry, reduce attack surface, vulnerability assessment process, **isolation and least privilege**, centrally managed access controls, real-time threat detection/IR, hardening against benchmarks and **avoid privileged mode**. Cites **NIST** recommendations.

- **LO08 Docker hardening:** security features — **Cgroups · LSMs · Capabilities · Seccomp · Userns**; **Docker content trust (DCT)** via `DOCKER_CONTENT_TRUST=1`; **resource limits** (default = no limit; `--cpus=2` for 2 CPUs; memory option) because unlimited consumption → **OOM**; select third-party tools carefully. Tools: **Docker Bench Security** (CIS-derived checks) and named commercial tools incl. **StackRox** (`www.stackrox.com`) covering build/deploy/runtime, process + network + privilege-escalation + file events in Kubernetes, policies detecting crypto mining, privilege escalation, exploits. Best practices: multi-stage builds to cut image-dependency attack surface, **hadolint** linter for Dockerfiles (`hadolint` is printed on pp127 and 129).

- **LO09 Kubernetes hardening:** **RBAC with least privilege, disable ABAC** — RBAC API prevents privilege escalation by editing roles/role bindings, enforced **at the API level** even when the RBAC authorizer is not in use; a user may create/update a role only if they hold **all** its permissions **at the same scope** (cluster-wide = **ClusterRole**, same namespace = **Role**). `apiGroup: rbac.authorization.k8s.io`. **Audit policy** — log all requests at the **Metadata** level (`apiVersion: audit.k8s.io/v1`, `kind: Policy`). **Network policies** — pods are **non-isolated by default**; `networking.k8s.io/v1` `NetworkPolicy`; policies are **additive** (union of rules); requires server **> v1.8** and a provider with policy support (**Calico, Cilium, Kube-router, Romana**); playground **Minikube, Katacoda, Play with Kubernetes**. **PodSecurityPolicy** (`extensions/v1beta1`) — `privileged: false`, `runAsUser: RunAsNonRoot`, restrict **Linux capabilities**, restrict **volumes** to block **NFS**, block **host ports**. **Secrets** — never a config file; providers **identity · aescbc · secretbox · aesgcm · kms**; **aesgcm = AES-GCM with random nonce using envelope encryption (DEK encrypted by KEK)**; `head -c 32 /dev/urandom | base 64`; verify via `etcdctl` and the `k8s:enc:aescbc` prefix. Tools **Istio** (`istio.io`, service mesh, mTLS pod-to-pod) and **Grafeas** (software supply chain auditing); **CIS Benchmark**; keep up to date.

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware → `exam_weight: unknown`; domain weights are sourced in [[quiz.html]] and the bank uses a **flat 5 per module**.
- Strong question sources, in rough order of yield: **4 virtualization approaches** (the discriminator is *who translates*, and para's VMM is *not* involved) · **4 levels vs 4 types** and the "Server Virtualization appears in both" trap · **4 threat classes** (Disclosure/Deception/Disruption/Usurpation) reused for both hypervisor and virtual network · **5 named VLAN attacks** and the two VLAN-hopping paths (802.1Q/DTP trunk spoofing vs STP root election) · **SDN Data Plane = exactly 3 attacks** (Device/Protocol/Side Channel) with **TCAM** as the Device Attack target · **SNMPv3 not SNMPv2c**, **SSH not telnet**, **nonces**, **OOB network** · **NFVI / VNF / MANO** plus the **ElGamal + co-resident GnuPG** side channel · **ELGamal** · Kubernetes **5 control-plane + 3 node components**, `-cloud-provider external` · **RBAC scope rule** (ClusterRole = cluster-wide, Role = namespace) · **pods non-isolated by default** and **NetworkPolicy is additive** · **server > v1.8** · **aesgcm envelope encryption**, `k8s:enc:aescbc` prefix · **PodSecurityPolicy** `privileged: false` + `RunAsNonRoot` · **NFS** volume block · **StackRox** / **Istio** / **Grafeas** / **hadolint** / **Docker Bench Security** · **Cgroups/LSMs/Capabilities/Seccomp/Userns** · **DOCKER_CONTENT_TRUST=1** and `--cpus=2`.
- Deliberate distractors to expect: Hyper-V is **not** LO06 (LO06 is containers) · **VPC/VPN confusion** in NV examples · confusing **NFV with SDN** · putting **ABAC** where the courseware says RBAC · **"Server Virtualization"** as level vs type.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-11")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/11-enterprise-virtual-network-security-map.canvas|Enterprise Virtual Network Security Map]]
- Flow to visualize: traditional management breaks → virtualization risks → virtualization concepts (approaches / levels / types) → **NV** (concepts → placement → hypervisor attacks → virtual-network attacks → VLAN attacks → hypervisor/virtual-network/VLAN security) → **SDN** (concepts → attacks by plane → measures by layer) → **NFV** (NFVI/VNF/MANO → attacks → measures) → **containers** (concepts/CaaS → vs VM → Docker drivers → K8s architecture → challenges/risks → attacks) → **container hardening** → **Docker hardening** → **Kubernetes hardening**.

## Cross-links
- [[00-Home]]
- [[quiz.html]] (unified bank, offline: 100 module + 56 external items) · [[Answer-Key]]
- Related modules: [[MOC-Module-04]] (network perimeter, secure comms) · [[MOC-Module-05]] (Windows — Hyper-V host, SMB, BitLocker) · [[MOC-Module-06]] (Linux — kernel hardening, SELinux/sVirt lineage) · [[MOC-Module-03]] (technical network security — VLANs, switching) · [[MOC-Module-09]] (application security, secure API/app design) · [[MOC-Module-10]] (data security — encryption at rest, DLP, integrity) · [[MOC-Module-12]] (IoT).

## Unresolved
- **p3 objective list** drops the `LO#06:` number and omits NFV from its prose list (see frontmatter).
- **p156** expands NFV as "Network Defined Functions" (see frontmatter).
- **p88 placement** — hypervisor/zoning/SELinux/sVirt/hidepid/GRSecurity/introspection block sits inside LO05's range but is LO03 material (see frontmatter).
- Per-module blueprint weights not in courseware.
- **OCR gaps, all recorded in the individual notes:** many screenshots did not OCR — the LO01 evolution figure, the LO03 Hyper-V/VMware/VirtualBox walkthrough steps, the LO05 NFV architecture figure labels, and most Kubernetes `kubectl` output tables. YAML and command blocks in LO09 were repaired to canonical spelling only where unambiguous (`vlbetal`→`v1beta1`, `rbac . k8s.i0`→`rbac.authorization.k8s.io`, `metadta`→`metadata`, `keyl`→`key1`, `ipB10ck`→`ipBlock`, `EIGamal`→`ElGamal`, `VNlCs`→`vNICs`, `kube-pubhc`→`kube-public`).
- **p34 figure MAC address** — System A's MAC OCRs as `ABCD.EFoom01`; the 8-character reading `ABCD.EF00.0001` is unconfirmed. System B's `ABCD.EF00.0002` is sound.
- p41 Fig 11.9 shows a **Windows Server 2019** build while the LO03f prose refers to 2016/2012-R2; not reconciled.
- The courseware does not state whether its 4 virtualization levels and 4 types are exhaustive.

## Quick review

Which four virtualization approaches are given, and what is the single discriminator between them?
?
**Who performs the binary translation.** Full → the **VMM** (guest unaware). OS-assisted/Para → the **guest OS** (VMM not involved in request/response). Hardware-assisted → the **processor**, via special instructions (no translation step). Hybrid → the guest adopts para-functionality **and** the VMM still does binary translation.

Levels of virtualization vs types of virtualization — list both sets of four.
?
**Levels (where):** Storage Device · File System · Server · Fabric. **Types (what):** Operating System · Network · Server · Desktop. "Server Virtualization" appears in both with different meanings — as a level it is logical partitioning of the server's OS environment/hard drive; as a type it is abstraction of servers/processors/OSes into independent VMs each running its own OS.

Which three attacks does the courseware place in the SDN **Data Plane**, and what does each target?
?
**Device Attack** — software/hardware vulnerabilities of the SDN switch, such as firmware attacks or the switch's **TCAM**. **Protocol Attack** — network protocol vulnerabilities of the forwarding device. **Side Channel Attack** — deduces forwarding policy (e.g. by packet-processing timing analysis).

Name the three principal NFV elements.
?
**NFVI** — NFV Infrastructure. **VNF** — Virtualized Network Functions. **MANO** — NFV Management and Orchestration.

Which protocol versions does the courseware require for SDN, and what defeats replay?
?
**SNMPv3 instead of SNMPv2c**, and **SSH instead of telnet**. Replay is defeated with **shared secret passwords or nonces** inside the TLS sessions, plus shared-secret authentication of tunnel endpoints under the data center interconnect protocol.

Kubernetes control-plane components and node components — name them.
?
Control plane: **kube-apiserver · etcd · kube-scheduler · kube-controller-manager · cloud-controller-manager**. Node: **kubelet · kube-proxy · container runtime** (Docker, CRI-O, CRI).

Under Kubernetes RBAC, who may create or update a role, and what is the scope rule?
?
Only a user who already holds **all the permissions contained in the role**, and **at the same scope** as the role — **cluster-wide for a ClusterRole**, **within the same namespace for a Role**. The RBAC API prevents privilege escalation by editing roles or role bindings and is enforced at the API level.

Are Kubernetes pods isolated from each other by default, and how do multiple NetworkPolicies combine?
?
**No** — the default network policy lets every pod talk to every other pod, so pods are non-isolated by default. NetworkPolicy resources are **additive**: if several policies select a pod, it is isolated by the **union** of their rules.

Which secret-encryption provider is strongest, and how is it built?
?
**aesgcm** — AES-GCM with a random nonce, using an **envelope encryption scheme** where the data is encrypted by **data encryption keys (DEKs)** using AES-CBC with PKCS#7 padding, and the DEKs are themselves encrypted by a **key encryption key (KEK)**. `kms` is recommended for enhanced security because EncryptionConfiguration gives only moderate security for the stored keys.

What does the courseware call OS virtualization, and which orchestrators does it name?
?
OS virtualization is the host operating system's kernel being "virtually replicated in multiple instances of isolated user space, called **containers, software containers, or virtualization engines**". Orchestrators named: **Docker Swarm, OpenShift, Kubernetes**.

Which five measures does the courseware give for securing the hypervisor?
?
**Time synchronization · setting access privileges for users · disabling unnecessary services · Isolated User Mode (IUM) · enabling SMB 3.0** for file shares.

Which four security mechanisms does the courseware list as Docker's own security features?
?
**Cgroups · LSMs · Capabilities · Seccomp · Userns** — with Docker Trusted Content implementing 14 of the 37 Linux security mechanisms.
