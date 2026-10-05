---
type: note
module: "12"
lo: "06"
tags: [bestpractice, process, mod/12]
topic: "GCP defense-in-depth network security, VPC, Shared VPC, firewall rules, routes"
exam_weight: unknown
status: done
unresolved:
  - "p282: the p282 body sentence says Cloud IAP 'is built on the BeyondCrop security strategy developed by Google'. 'BeyondCrop' is printed in the body; the same page's companion figure and p294 print the product as 'BeyondCorp Enterprise'. The body spelling is reproduced as printed and is recorded here rather than silently corrected."
  - "p282: Fig 12.192 'Overview of Network Security Controls' is a dense three-column diagram. The legible column headers are 'Secure your internet-facing', 'Secure your VPC', 'Micro-segmentation'; almost all control labels inside the columns are OCR mash (e.g. 'Global LB / TLS', 'Cloud Armor', 'VPC Service Controls', 'VPC level firewalls', 'Outbound NAT', 'Private Google Access', 'Istio security based', 'Application based controls', 'Identity based controls', 'API based access', 'Access based on HTTPS', 'IoT'/'IIO', 'per GKE cluster'). The 15 legible labels are listed in the note but the mapping of each label to a column is NOT asserted, because the column assignment cannot be read."
  - "p283: 'Apply granular security policies' prints 'uniform L 7 filtering' - the layer number OCR's as the digit '1'/'7'; rendered here as L7 per the surrounding Layer 3-through-Layer 7 wording, which is itself printed on the same page."
  - "p284 Fig 12.196 'Enable VPC on Google Cloud Platform User Interface': the screenshot carries no numbered steps. Its legible fragments are three option labels ('Bring your own VPC network', 'Shared VPC', 'Serverless VPC access') plus a 'DEFAULT CONFIGURATION' panel reading 'Disabled logs configuration' and 'Data Read: Disabled' / 'Cloud Key Management Service (KMS) Apt'. Only the three option labels are recorded; the KMS/api panel is a screenshot artefact and no service name is asserted from it."
  - "p287: the figure bullet 'Firewall rules incornirq or taffr to an' is unreadable - the object of 'include or restrict' is garbled. The claim that firewall rules 'allow or deny connections' is taken from the legible p287 body sentence instead; the garbled figure bullet is not transcribed."
  - "p287: the figure bullet 'By default tramc from Outsde network iS mae' does not state the object. The p288 body sentence 'By default, incoming traffic from outside your network is blocked.' is used instead; the figure bullet is not treated as an independent source."
  - "p288 Fig 12.201: legible field values are Name 'learn-custom-firewall-rule1', Network 'learn-custom', Priority range '0 - 65535' (default 1000), Direction of traffic Ingress/Egress, Action on match 'Allow', and the Logs warning 'Turning on firewall logs can generate a large number of logs which can increase costs'. The 'Source' and 'Destination' field values are NOT legible and are not asserted. The project is 'My First Project'."
  - "p289/p290: the console menu OCR's as 'R0Jtes' in one place and 'FireÃ†l X R0Jtes' in another - both are 'Firewall rules' and 'Routes' menu entries. The route entry itself is unambiguous; the garbled token is the menu label, not the concept."
  - "p290 Fig 12.203 'Route details': the route name OCR's as 'default-route-QÃŸiiju•ueeeeeedf' and is NOT reconstructed. The legible rows are 'Default route to the Internet', 'Route type', 'IP version', 'Destination IP address range', 'Instance route applies to all instances within the specified network', and 'Next hop'. The Next hop value OCR's as 'Oef.uit tn.ernet gateway' - read here as 'Default internet gateway' with the caveat that the first letters are garbled; no IP or gateway id is printed legibly."
---

[[MOC-Module-12]]

# GCP Defense-in-Depth and VPC (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)**
> Covers pp. 282–290: defense-in-depth network security principles (pp282–284) ·
> centralize network control with Shared VPC (pp285–286) · firewall rules (pp287–288) ·
> routes (pp289–290).
> Downstream: [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]] ·
> [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]] (Operations Suite for the real-time
> monitoring pillar). IAM boundary: [[12-LO06f-GCP-Organization-Policies]].

## The three defense-in-depth principles _(Mod 12 p282)_

- "The Google Cloud Platform (GCP) has **strong network security controls** to reduce the
  potential risks, safeguard the resources, and effectively run the operations. It **enables
  customers to implement a defense-in-depth (DiD) security strategy**."
- **Figure rule** — "Implement the following **three principles for defense-in-depth network
  security** to reduce risk and protect the resources and environment:"

| # | Principle (verbatim) |
|---|---|
| 1 | **Secure internet-facing services** |
| 2 | **Secure VPC for private deployments** |
| 3 | **Micro-segment access to applications and services** |

_(Mod 12 p282)_

### Principle 1 — Securing internet-facing services _(Mod 12 pp282–283)_

"Internet-facing services can be secured by **limiting the access and defending against
cyberattacks**."

| Control | Printed as |
|---|---|
| **Defend against DDoS attacks** | "place the services **behind the Google Cloud HTTP(S) Load Balancer** and deploy the **Google Cloud Armor**. Together, they will provide protection from **Layer 3 and Layer 4 volumetric DDoS attacks** to the data exposed publicly in cloud services." |
| **Control access to applications and VMs** | "Implement **Cloud Identity-Aware Proxy (IAP)**, a GCP service, that is built on the **BeyondCrop** security strategy developed by Google to control the access to applications and VMs in a **zero-trust environment**. Cloud IAP allows access to authorized users so that they can **work securely from any location without connecting to a VPN**." |
| **Enforce WAF policies at the edge** | "Employ **preconfigured WAF rules** to prevent cyberattacks such as **SQL injection and cross-site scripting**. **WAF custom rules** help customers to **filter the internet traffic across Layer 3 through Layer 7 attributes**." |
| **Apply granular security policies** | "Apply granular security policies such as **uniform L7 filtering** or **customized access controls** depending on the complexity of deployments. **REST API, CLI, and UI** help in updating the rules and policies." |
| **Turn on real-time monitoring, logging, and alerting** | "Implement the **Google Cloud's Operations Suite** to monitor, diagnose, and fix applications across the GCP. Operations Suite **monitoring** collects **metrics, events, and metadata** from the **GCP, AWS**, and a variety of common application components. Operations Suite **logging** allows users to **filter, search and view logs**. Operations Suite **error reporting** alerts users regarding **new issues**." |

_(Mod 12 pp282–283)_

### Principle 2 — Securing VPC for private deployments _(Mod 12 p283)_

"The GCP provides **numerous solutions for deploying the customer workload securely and
privately**."

| Control | Printed as |
|---|---|
| **Deploy VMs with only private IPs** | "The exposure to internet can be minimized by **disabling external IPs in VMs** or by **implementing the Org Policy**." |
| **Deploy GKE private clusters** | "For the **Google Kubernetes Engine (GKE)** enterprise users, deploy **private clusters**." |
| **Serve applications privately** | "Use the **Google Internal Load Balancer** for scaling and serving the applications privately for users that access the application through **Google cloud VPC or on-premise private connection such as cloud VPN**." |
| **Access Google managed services privately** | "GCP provides various **private access options** for users to host their applications in the GCP or on-premise data centers to privately utilize services such as **cloud storage, BigQuery, or cloud SQL**." |
| **Provide secure outbound internet connections with Cloud NAT** | "**Google Cloud NAT** allows **private VMs or private GKE clusters to connect to the internet**. It **minimizes the access paths and public IPs**." |
| **Mitigate exfiltration risks** | "Implement **VPC service controls** to build a **trusted network perimeter** to mitigate the **exfiltration risks** — preventing data from moving outside the boundaries of a trusted perimeter." |

_(Mod 12 p283)_

### Principle 3 — Micro-segment access to applications and services _(Mod 12 p283)_

"The GCP provides **multiple tools for the micro-segment workloads** and secures them at the
**granular level**."

| Type | Printed as |
|---|---|
| **Micro-segmentation for VM-based applications** | "**Google VPS** helps in regulating the communication of VM-based applications by **setting firewall rules**." |
| **Micro-segmentation for GKE-based applications** | "**Google GKE clusters** control the communication in container-based applications by **setting network policies**." |

_(Mod 12 p283)_

**Legible control labels inside Fig 12.192** _(p282, see `unresolved:` for the column mapping)_:
Global LB · TLS · Cloud Armor · VPC Service Controls · VPC level firewalls · Outbound NAT ·
Private Google Access · Istio security based · Application based controls · Identity based
controls · API based access · Access based on HTTPS · micro-segmentation for VM based ·
micro-segmentation within a GKE cluster.

## Utilize VPC to define the network IP addresses — the stated rules _(Mod 12 p284)_

- "A **VPC network is a virtual representation of physical network**, which connects **VM
  instances, GKE clusters, App Engine, and other resources of a project**."
- "A project could have **multiple VPC networks** depending on the **set organizational
  policy**."
- "**VPC networks are not associated with a particular zone or region and are global
  resources.**"
- "**Each VPC network contains subnets that define a set of IP addresses.**"
- "In a VPC, **network firewall rules control traffic** that moves in and out of instances."
- "Resources inside a VPC network use **IPv4 addresses** to communicate with one another, **as
  per the applicable firewall rules**."
- "In a **hybrid environment**, the administrator can use **Cloud Interconnect or Cloud VPN** to
  securely connect VPC networks."
- "To connect VPC networks **from different projects**, use **VPC network peering**."
- "**Use IAM roles to secure network administration** in VPC networks."

**Security benefits offered by VPC networks** _(Mod 12 p284)_

| # | Printed benefit |
|---|---|
| 1 | "Use GCP **VPC and subnets** to map the network, and to **group and isolate related resources**." |
| 2 | "VPC networks provide **scalable and flexible networking** for the **Compute Engine VM instances**." |
| 3 | "A VPC network provides **internal TCP/UDP Load Balancing**." |
| 4 | "It establishes **secure connection with on-premises networks** via **cloud interconnect attachments and cloud VPN tunnels**." |
| 5 | "It helps in **distributing traffic from Google Cloud external load balancers to backend**." |

_(Mod 12 p284)_

## Centralize network control — Shared VPC _(Mod 12 p285)_

- "The Google cloud **shared VPC** can configure and **centrally manage one or more virtual
  networks across multiple projects in an organization** for secured and efficient
  communication **by utilizing internal IPs**."
- **Terminology** — "The project of an organization using a shared VPC consists of **host
  projects**, which are connected to **service projects**. The **host project network is the
  shared VPC network**."
- **Figure rules**
  - "Use **shared VPC** to connect to a **common VPC network**."
  - "**Shared VPC and IAM controls enable the separation of network administration from
    project administration.**"

### Walkthrough — set up Shared VPC _(Mod 12 pp285–286)_

1. From the Google console dropdown menu, navigate to **VPC network** and select **VPC
   networks** on the Menu tab. _(p285, Fig 12.197)_
2. Navigate to **Shared VPC**.
3. "Select **Set up Shared VPC**." _(p286, Fig 12.198)_
4. "Click on **Save & continue**." _(p286, Fig 12.199)_

> "**While establishing the shared VPC, run the process from the host project.**" _(Mod 12 p286)_

## Manage traffic with firewall rules _(Mod 12 p287)_

- "Configure firewall rules that **allow or deny traffic to and from the resources attached
  to the VPC**, including **Compute Engine VM instances and GKE clusters**."
- "**Use network tags** to make firewall rules and routes **applicable to specific VM
  instances**."
- "Configure Virtual Private Cloud (VPC) firewall rules **for project and network**."
- "**Firewall rules control incoming or outgoing traffic to an instance. By default, incoming
  traffic from outside your network is blocked.**" _(Mod 12 p288)_
- "**Logs can generate a large number of logs which can increase costs.**" _(Mod 12 p287)_

**Legible fields of the Create Firewall Rule form** _(p288, Fig 12.201 — see `unresolved:`)_
`Name` = `learn-custom-firewall-rule1` · `Network` = `learn-custom` · `Priority` range
**0 – 65535**, displayed value **1000** · `Direction of traffic` = **Ingress / Egress** ·
`Action on match` = **Allow** · `Logs` = On/Off with the Stackdriver cost warning.

### Walkthrough — create a firewall rule _(Mod 12 pp287–288)_

1. From the Google console dropdown menu, navigate to **VPC network** and select **VPC
   networks** on the Menu tab. _(Mod 12 p287)_
2. Navigate to **Firewall rules**. _(p287, Fig 12.200)_
3. "Click on **Create firewall rule**, **set the required rules**, then click on **Create**."
   _(p288, Fig 12.201)_

## Use routes _(Mod 12 p289)_

- "Define the **paths taken by the network traffic (routes)** from a **VM instance to another
  destination**."
- "Google cloud routes are the paths taken by the network traffic from a VM instance to reach
  another destination. The **destination could be either be inside or outside** the Google
  cloud VPC network." *(printed with the "either be" error)*
- "The **VM instance controller knows the applicable routes**. The packet leaving the VM is
  carried to the **next hop based on the routing order**."

### Walkthrough — view routes _(Mod 12 p289)_

1. From the Google console dropdown menu, navigate to **VPC network** and select **VPC
   networks** on the Menu tab.
2. Navigate to **Routes**. _(p289, Fig 12.202)_

**Legible rows of Route details** _(p290, Fig 12.203)_ — `Default route to the Internet` ·
`Route type` · `IP version` · `Destination IP address range` · "**Instance route applies to all
instances within the specified network**" · `Next hop` = *Default internet gateway* (label
partially garbled).

## Firewall rules vs routes — the exam delta

| | Firewall rules | Routes |
|---|---|---|
| **Controls** | traffic **in and out of instances**, allow/deny | the **path** traffic takes from a VM to its destination |
| **Scoped by** | project + network, **network tags** to target specific VMs | the **network**, applied by the **VM instance controller**; next hop chosen by **routing order** |
| **Default** | **incoming traffic from outside the network is blocked** | a **default route to the Internet** exists |

_(Mod 12 pp287–290)_

Upstream: [[12-LO06h-GCP-Encryption-and-Cloud-KMS]] (KMS) ·
[[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]] (roles for network administration) ·
[[quiz.html]]







