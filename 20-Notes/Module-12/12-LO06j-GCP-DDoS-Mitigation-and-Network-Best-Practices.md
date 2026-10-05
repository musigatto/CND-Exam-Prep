---
type: note
module: "12"
lo: "06"
tags: [threat, bestpractice, mod/12]
topic: "GCP DDoS mitigation and network security best practices"
exam_weight: unknown
status: done
unresolved:
  - "p291 Fig 12.204 lists 10 'Best Practices to Mitigate DDoS Attacks for GCP Deployments' bullets. The p292-293 body text expands those same 10 into named sections; only 9 named sections are printed in the body (Deploy Third-party, Deploy App Engine, Google Cloud Storage, Use API Rate-Limiting, Enforce Resource Quotas, Protect Infrastructure with CDN Offloading, plus the four headed groups on p292). The mapping is 1:1 by wording and is asserted on that basis, not from the figure's own structure."
  - "p291: the figure bullet 1 prints 'provisioning isolated and secure piece of the Google Cloud' (singular 'piece') while the p292 body prints 'Provision isolated and secure pieces'. Both are kept as printed."
  - "p293: the body sentence for Deploy App Engine runs the mitigation and the dos.yaml mechanism together in one item ('...which ensures an evil application will not impact the performance of other applications and specify a set of IPs/IP networks via a dos.yaml file...'). The 'evil application will not impact the performance of other applications' claim is NOT made anywhere else in the module and is reproduced verbatim without interpretation."
  - "p292: the Cloud CDN bullet prints 'Use the Google Cloud CDN's proxy capability where CND caches content from points-of presence closer to users' - 'CND' for 'CDN' is an OCR/substitution artefact; the p291 figure prints 'CDN' in the same bullet, so it is rendered CDN here."
  - "p294 Fig 12.206 (the 'Include the Following' summary) prints 8 bullets that compress the pp294-296 body. Bullet 3 ends mid-word at 'limiting multiple VPC' and bullet 4's list duplicates 'Cloud IDS' twice ('using Cloud IDS and packet mirroring, using Cloud Intrusion Detection System (IDS), configuring Packet Mirroring and then using Cloud IDS/any third-party tool'). Both are reproduced as printed and the body wording is given alongside."
  - "p295: the first Secure Perimeter bullet prints the broken sentence 'Use different methods and secure cloud perimeter, to segment including firewalls and VPC service controls.' Reproduced as printed; the intended meaning is not reconstructed."
  - "p295/p301 spelling: the Network Intelligence product is printed 'Network Intelligence Centre' on p295 and 'Network Intelligence Center' in the p294 figure. Both are kept as printed; neither spelling is asserted as official."
  - "p296: 'Automate Infrastructure Provisioning' is a HEADING on its own page with no bullets under it - the automation sentence follows the heading. There is no per-item automation checklist on p296."
  - "NO numbered console walkthrough is printed anywhere in pp.291-296 - this range is entirely rules/figures, unlike the IAM and VPC ranges."
---

[[MOC-Module-12]]

# GCP DDoS Mitigation and Network Security Best Practices (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)**
> Covers pp. 291–296: DDoS mitigation (pp291–293) · GCP network security best practices
> (pp294–296).
> Upstream: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]] (the Load Balancer + Cloud Armor pair and
> the firewall-rule surface these practices build on) ·
> [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]] (Operations Suite monitoring/logging).

## GCP infrastructure mitigates DoS by default — the stated rules _(Mod 12 p291)_

- "Google protects its **shared infrastructure** and its **production services** by placing
  **different mechanisms** to **prevent overwhelming of shared infrastructure** by services
  and to **maintain isolation among customers** using the shared infrastructure."
- "**GCP infrastructure enables it to mitigate DoS attacks by default** and also provides
  **multi-tier and multi-layer protections** to further mitigate DoS impact."
- "**Mitigation requires disabling access** to the services or applications, **implementing
  barriers**, and **deploying detection systems**."

**The path from the Internet to the customer's compute instance** _(p291, as printed)_

| Step | Printed as |
|---|---|
| 1 | "The data centers obtain an external Internet connection through **fiber-optic** where the connection passes through **several layers of software and hardware load balancers**." |
| 2 | "The information about the **incoming traffic** is reported by the **load balancer to the central DoS service** running on the infrastructure." |
| 3 | "When there is a DoS attack **detected by the central DoS service**, the service mitigates the attack by **configuring the load balancers to drop or throttle traffic** associated with the attack." |
| 4 | "Services that want to make themselves available on the Internet get **registered** with an infrastructure service called **Google Front End Service (GFE)**." |
| 5 | "**GFEs** provide **public IP address hosting of its public DNS name, DoS protection, and TLS termination**." |
| 6 | "**GFE applies protections against DoS attacks that terminate user traffic and automatically scale to absorb attacks before they reach the user's compute instances.**" |

**Figure bullets (p291)**

- "GCP infrastructure **mitigate DoS attacks by default** and provides **multi-tier and
  multi-layer protections** to reduce DoS impact on services."
- "**Various layers of hardware and software load balancers** provide incoming traffic
  information to a **central DoS service** that can detect a DoS attack and **configure the
  load balancers to reduce or improve traffic** associated with the attack." *(figure wording;
  the body on the same page says "drop or throttle" — both printed)*
- "The central DoS service **also receives application-layer information from the Google Front
  End (GFE) instances, which the load balancers do not have access to**, and it configures the
  GFE instances to **drop or throttle attack traffic**."

### Best practices to mitigate DDoS attacks for GCP deployments _(Mod 12 pp291–293)_

| # | Practice | Printed detail |
|---|---|---|
| 1 | **Reduce the attack surface for GCE deployment** | "**Provision isolated and secure pieces of the Google Cloud** using **Google Cloud Virtual Network**" _(p292; the p291 figure bullet reads "piece")_. Isolate and secure deployment using **subnetworks and networks, firewall rules, tags, and Identity and Access Management (IAM)**. "**Open access to ports and protocols that are needed using firewall rules and/or protocol forwarding.**" "**Use the default anti-spoofing protection** offered by GCP for the private network (IP addresses)." "**Utilize the automatic isolation** provided by GCP **between virtual networks**." |
| 2 | **Isolate internal traffic from the external world** | "**Deploy instances without public IPs unless necessary.**" "**Set up a NAT gateway or SSH bastion** to limit the number of instances that are **exposed to the Internet**." "Deploy **Internal load balancing** for the internal client instances accessing internally deployed services, thereby **avoiding exposure to the external world**." |
| 3 | **Enable proxy-based load balancing** | "Enable **HTTP(S) load balancing or SSL proxy load balancing** so that **Google Infrastructure mitigates and absorbs many attacks**." "Have HTTP(S) load balancing **with instances in multiple regions** so that the attack gets **disseminated across instances**." |
| 4 | **Scale to absorb the attack** | "**GFE infrastructure, which terminates user traffic before they reach compute devices**; it **automatically scales to absorb attacks**." "**Anycast-based load balancing**, which moves the traffic to instances with **available capacity** in the event of a DDoS attack." "**Autoscaling** — the load-balancing proxy layer **distributes traffic across all backends with available capacity** in the event of a sudden traffic spike." |
| 5 | **Protect infrastructure with CDN offloading** | "**Google Cloud CDN's proxy capability**, where CDN **caches content from points-of-presence closer to users**." "**CDN Interconnect partners** for additional DDoS protection." |
| 6 | **Deploy third-party DDoS protection solutions** | "**Purchase specialized third-party DDoS protection solutions** to meet certain needs of protection for DDoS attacks." "In addition, deploy **DDoS solutions available via Google Cloud Launcher**." |
| 7 | **Deploy App Engine** | "Deploy **App Engine's capabilities** to mitigate DDoS attacks, which **ensures an evil application will not impact the performance of other applications**, and **specify a set of IPs/IP networks via a `dos.yaml` file** to block requests from accessing application(s)." |
| 8 | **Restrict access to Google Cloud Storage** | "**Control users' access to Google Cloud Storage resources using signed URLs.**" |
| 9 | **Use API rate-limiting** | "**Use API rate limits** to define the **number of requests** that can be made to the **Google Compute Engine API**." |
| 10 | **Enforce resource quotas** | "**Enforce quotas using Compute Engine on resource usage**, which **prevents unforeseen spikes in usage**." |

_(Mod 12 pp291–293 — items 1–5 expanded on p292, items 6–10 on p293)_

## GCP network security best practices _(Mod 12 pp294–296)_

- "To **secure an organization's data and workloads on Google Cloud**, follow the below security
  best practices." _(Mod 12 p294)_

### 1 · Deploy zero-trust networks _(Mod 12 p294)_

- "**Check both the user's identity and context**, whether they are **inside or outside** the
  organization's network."
- "**Unlike a VPN**, shift access controls **from the network perimeter to the users and
  devices**."
- "**Use Google Cloud's BeyondCorp Enterprise as a zero-trust solution** and obtain threat and
  data security while having **additional access controls**."
- "In addition, use **Google Cloud's Identity-Aware Proxy (IAP) to authenticate and authorize
  users** who access applications and resources."

### 2 · Secure connections to on-premises or multi-cloud environments _(Mod 12 pp294)_

- "Use **Google Cloud's private access methods for VMs** that the **Cloud VPN or Cloud
  Interconnect** support."
- "These private access methods for VMs include **IPSec VPNs, private service connect for
  services, Anthos, and dedicated interconnect and partner interconnect**."

### 3 · Disable default networks _(Mod 12 pp294–295)_

- "**Disable the creation of default networks in new projects.**"
- "**Delete the default networks in existing projects.**"
- "**Avoid IP address conflicts by first planning network and IP address allocation** across
  connected deployments and projects."
- "**Limit multiple VPCs to one per project** to enforce access control effectively."

### 4 · Inspect network traffic _(Mod 12 p295)_

- "Use **cloud IDS and packet mirroring** to ensure the security of workloads that are running
  in **Compute Engine and Google Kubernetes Engine (GKE)**."
- "Use **cloud IDS** to see the **traffic movement from and to VPC networks**."
- "**Configure packet mirroring** and then use **Cloud IDS/any third-party tool** to **collect
  and inspect network traffic at scale**."

### 5 · Monitor network _(Mod 12 p295)_

- "**Monitor network and traffic using telemetry.**"

| Tool | Printed as |
|---|---|
| **VPC Flow Logs and Firewall Rules Logging** | "provide **real-time visibility into the traffic**" |
| **Firewall Insights** | "helps in **reviewing the firewall rules**" |
| **Network Intelligence Centre** *(p294 figure prints "Center")* | "to see how **network topology and architecture are performing**" |
| **Connectivity Tests** | "provide insights into the **firewall rules and policies that are applied to the network path**" |

_(Mod 12 p295)_

### 6 · Secure perimeter _(Mod 12 p295)_

- "Use different methods and secure cloud perimeter, to segment including **firewalls and VPC
  service controls**." *(printed as shown — see `unresolved:`)*
- "Use **Shared VPC** to build a production deployment that **isolates workloads into
  individual projects**."
- "**Define firewall rules and policies at the organization, folder, and VPC network level.**"
- "**Use service accounts in firewall rules to enforce isolation** to **avoid depending on an
  IP address as the sole identifier of a workload**."
- "Use **hierarchical firewall policies** to define rules that **apply to all networks
  regardless of what the network-level firewall rules permit**. Also, **define rules at the
  folder level to cover only portions of an organization**."
- "**Set up context-based perimeter security** by considering **VPC service controls**."
- "**Use Google Cloud Armor security policies** to manage requests to an **external HTTP(S)
  load balancer at the Google Cloud edge**."

### 7 · Use a web application firewall _(Mod 12 p295)_

- "**Enable Google Cloud Armor** to get **DDoS protection and WAF capabilities** for external
  web applications and services."

### 8 · Automate infrastructure provisioning _(Mod 12 pp294, 296)_

- "**Automate infrastructure provisioning** by using tools such as **Terraform, Jenkins,
  Cloud Build**, etc" _(p294 figure)_.
- "To help build an environment that uses **automation**, Google Cloud provides **security
  blueprints**, which in turn provide a **secure application environment** and describe
  **step-by-step** on how to **configure and deploy the Google Cloud estate**." _(Mod 12 p296)_

## The eight best-practice headlines, as printed on p294

| # | Headline (Fig 12.206, compressed) |
|---|---|
| 1 | **Deploy zero trust networks** — check identity **and** context, shift access control from the perimeter to users and devices, BeyondCorp Enterprise as the zero-trust solution, IAP to authenticate and authorize |
| 2 | **Secure connections to on-premises or multi-cloud environments** using Google's private access methods |
| 3 | **Disable default networks** — disable creation in new projects, delete in existing, avoid IP conflicts, limit multiple VPC *(bullet truncates here)* |
| 4 | **Inspect network traffic** using Cloud IDS and packet mirroring |
| 5 | **Monitor network** using telemetry — VPC Flow Logs, Firewall Rules Logging, Firewall Insights, Network Intelligence Center, Connectivity Tests |
| 6 | **Secure perimeter** — firewalls and VPC Service Controls, Shared VPC, firewall rules and policies, service accounts in firewall rules, hierarchical firewall policies, context-based perimeter security, Google Cloud Armor security policies |
| 7 | **Use a web application firewall** by enabling Google Cloud Armor |
| 8 | **Automate infrastructure provisioning** — Terraform, Jenkins, Cloud Build, etc |

_(Mod 12 p294)_

Upstream: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]] · [[12-LO06c-GCP-IAM-Security-Best-Practices]]
(IAM inside the attack-surface control) · [[quiz.html]]







