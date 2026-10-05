---
type: note
module: "11"
lo: "06"
tags: [threat, mod/11]
topic: "Container security challenges and risks"
exam_weight: unknown
status: done
unresolved: ["'Compromise of secrets' is listed in the p101 'Container Security Challenges' figure, but the courseware gives it no accompanying prose anywhere in the slice, so its stated consequence is unknown and is not invented here."]
---

[[MOC-Module-11]]

# Container Security Challenges and Risks (§11.06)

## A. Container security challenges — the 12-item list _(Mod 11 pp101–102)_

> "While containerization provides fast and continuous delivery of applications to developers and DevOps teams, there are certain security challenges associated with it." _(Mod 11 p101)_

| # | Challenge | Courseware statement / stated consequence |
|---|---|---|
| 1 | **Inflow of vulnerable source code** | containers are **open source**; developer images are **frequently updated, stored and used** → an inflow of source code that **may potentially harbor vulnerabilities and unexpected behaviors** into an organization |
| 2 | **Large attack surface** | many containers run on multiple machines, in cloud or on-premises → large attack surface → **challenges in the tracking and detection of anomalies** |
| 3 | **Lack of visibility** | the **abstraction layer created by the container engine masks the activity of a particular container** |
| 4 | **Compromise of secrets** | *figure only — no prose given in the courseware* |
| 5 | **DevOps speed** | lifespan of a container is **four times less than virtual machines**; created instantly, run briefly, stopped, removed → because of this **ephemerality an attacker can execute an attack and disappear quickly** |
| 6 | **Lack of governance** | **software errors** and **IAM backdoor shortcuts** → **significant security gaps**; container security incidents now account for more security threats, **most of them major attacks** |
| 7 | **Noisy neighboring containers** | the behavior of one container can cause a **DoS for another** — e.g. **opening sockets frequently can freeze up the host machine** |
| 8 | **Container breakout to the host** | containers that run as the **root user can breakout and access the host's operating system** |
| 9 | **Network-based attacks** | a **jeopardized container** is vulnerable to them, **especially in outbound networks with unrestricted raw sockets** |
| 10 | **Bypassing isolation / lack of isolation** | any **inadequacy in the isolation** between containers → an attacker who compromises **one** container can **easily access another container on the same host** |
| 11 | **Ecosystem complexity** | the tools to build, deploy and manage containers come from **different sources** → the user must **keep the components secure and up-to-date** |
| 12 | **Lack of standardization** | hard to incorporate existing security standards (built on **alternative, out-of-date approaches**) into containers; **combining multiple standards** with growing container/tool/platform infrastructure **raises security concerns** |

**Loophole worth remembering:** 1, 5, 9, 10 all reduce to the same attacker advantage — *ephemeral, loosely isolated, network-reachable workloads that appear and vanish between scans*. → [[11-LO01b-Virtualization-Security-Risks]]

## B. Container security threats / risks _(Mod 11 pp103–106)_

> "Containers are among the most important technologies in DevOps … the increased use of containers is exposing companies to new security threats. Therefore, there is a need to **secure containers throughout the development pipelines**." _(Mod 11 p104)_

### B1. Image threats _(Mod 11 pp103–104)_

| Threat | Stated consequence |
|---|---|
| **Image vulnerabilities** | images are **static archive files**; **lack of updates in the image components** or **missing critical security updates** make the image vulnerable; a vulnerable image version **poses a risk to the containerized environment** |
| **Image configuration defects** | e.g. an image **fails to configure with a specific user account and instead runs with greater privileges than required** → **privilege escalation** |
| **Embedded malware** | image is a **collection of files packed together** → malicious files may be included **intentionally or inadvertently**; the malware has **the same privileges as other components of the image** and can **attack other containers or hosts** |
| **Embedded clear text secrets** | secrets needed to talk to other components (e.g. a web app's **username and password to the backend database**) get **embedded into the image** → a user with access to the image can **parse it to extract them** |
| **Use of untrusted images** | can **introduce malware, leak data, or introduce components with vulnerabilities** → avoid running **any** image from untrusted sources |

### B2. Registry threats _(Mod 11 pp103, 105)_

| Threat | Stated consequence |
|---|---|
| **Insecure connections to registries** | images may contain **sensitive components (proprietary software, embedded secrets)** → an insecure connection **enables a man-in-the-middle attack** |
| **Stale images in registries** | a registry holds **all images an organization deploys**; over time it may hold **vulnerable or out-of-date** images → no threat while stored, but they **increase the likelihood of accidental deployment** of the vulnerable image |
| **Insufficient authentication and authorization restrictions** | registries may run **sensitive or proprietary software** → insufficient authn/authz **exposes the technical details of the application to the attacker** |

### B3. Orchestrator risks _(Mod 11 pp104–105)_

| Risk | Stated consequence |
|---|---|
| **Unbounded administrative access** | orchestrators are designed **presuming all interacting users are administrators**; one orchestrator runs many applications managed by different teams; if access is **not scoped to requirements**, a malicious user **can affect the functionality of different containers** managed by it |
| **Unauthorized access** | the orchestrator has **its own authentication directory service**, possibly **separated from the rest of the organization** → **orphan accounts**, which are **highly privileged**; their compromise leads to **system-wide compromise** |
| **Poorly separated inter-container network traffic** | node-to-node traffic is routed through a **virtual overlay network managed by the orchestrator**, and is **obscure to network security and management tools**. (Related: the orchestrator tool manages the containers' **data storage volumes**; many organizations **encrypt the stored data** to prevent unauthorized access.) |
| **Mixing of workload sensitivity levels** | the orchestrator's primary focus is **workload density** — by default it places **different-sensitivity workloads on the same host** (e.g. a public-facing web server and a container processing **financial data**) → the financial container **can be easily compromised** |
| **Orchestrator node trust** | the orchestrator is the **foundational node**; if its **configuration is weak**, it exposes **the orchestrator and other components of the container technology** to increased risk |

### B4. Container risks _(Mod 11 pp103, 106)_

| Risk | Stated consequence |
|---|---|
| **Vulnerabilities within the runtime software** | attacker exploits the runtime to **compromise it**, then uses the compromised runtime to **attack other containers** and to **monitor container-to-container communication** |
| **Unbounded network access from containers** | **in the default state**, most containers during runtime **access other containers or the host OS through the network**; if a container is compromised, letting it reach network traffic **significantly increases the risk to other containers in the environment** |
| **Insecure container runtime configurations** | the administrator is exposed to **many configurable options** at runtime; **security is lowered if these options are improperly set** |
| **App vulnerabilities** | containers are compromised by **flaws in the application they run** — not a fault of the container, but the app's vulnerabilities **within the container environment** compromise it |
| **Rogue containers** | **unplanned or unsanctioned** containers, originating in **development** when a developer creates a container to test code; if **not properly configured** or **not passed through the rigors of vulnerability scanning**, they **can be exploited** |

### B5. Host OS risks _(Mod 11 pp103, 106)_

| Risk | Stated consequence |
|---|---|
| **Large attack surface** | the host OS attack surface = **all possible points through which an adversary can attempt to gain access to and exploit host OS vulnerabilities** → increases the potential to **compromise the host OS and the containers running on it** |
| **Shared kernel** | container-specific OSes have a **smaller attack surface area** than general-purpose OSes, but a container has **only software-level isolation of resources** and a **shared kernel increases the inter-object attack surface** |
| **Host OS component vulnerabilities** | impact **all the containers and applications running on the host** |
| **Improper user access rights** | risk when **users sign in directly on the host to manage containers**; improper rights affect **the host system and all other containers present in it** |
| **Host OS file system tampering** | an insecure container configuration **exposes the host volumes to significant risk of file tampering** → affects **the stability and security of the host and the containers running on it** |







