---
type: note
module: "11"
lo: "06"
tags: [concept, mod/11, flashcard/11]
topic: "Container concepts, CaaS and orchestration"
exam_weight: unknown
status: done
unresolved: ["Fig. p92 labels the first container type 'System Containers' while the p92 prose calls the same type 'OS Containers'; both labels are reproduced as printed."]
---

[[MOC-Module-11]]

# Container Concepts, CaaS and Orchestration (§11.06)

## Definition — OS virtualization _(Mod 11 p89)_

> In OS virtualization, the **host operating system's kernel is virtually replicated in multiple instances of isolated user space**, called **containers**, **software containers**, or **virtualization engines**, thereby lending (virtualized) operating system functionality to each container.

| Term | Role |
|---|---|
| **Container** | encapsulates **an application and its dependencies** in its own environment; runs **in isolation** from other containers and applications **while utilizing the same resources and operating system** |

**Scope of the section:** vulnerabilities, attacks and security challenges of containers, and of **Docker** and **Kubernetes** — "widely used for developing, packaging, running, and managing applications and all their dependencies in the form of containers". _(Mod 11 p89)_

## Why containerization _(Mod 11 p90)_

- Use case: **virtual hosting** requiring **segmentation of the physical resources among multiple users** → each user gets their own virtual space; containers manage the users and their respective resources **while keeping them isolated**.
- Containers are monitored and managed by the **administrator having full admin rights to all the containers**.
- "Many virtualization problems are effectively resolved with containerization." Resources are **not wasted** since the **actual OS runs independently of the containers**.
- vs VMs: each container image is **more easily migrated and shared** because of **smaller sizes**; only **one** OS is involved → a container is **easily maintained**.
- **Minimizes hardware costs** — multiple applications run on the same hardware, **increasing the utilization of the hardware**.

→ related: [[11-LO02c-Virtualization-Levels-and-Types]] · [[11-LO01b-Virtualization-Security-Risks]]

## Containers as a Service (CaaS) _(Mod 11 p90)_

| Item | Statement |
|---|---|
| **CaaS** | services that enable the **deployment of containers and container management through orchestrators** |
| **Payoff** | subscribers can develop **rich, scalable containerized applications** through the **cloud or on-site data centers** |

## Container Engine vs Container Orchestration _(Mod 11 pp90–91)_

| | **Container Engine** | **Container Orchestration** |
|---|---|---|
| What it is | **managed environment for deploying containerized applications** | **automated process of managing the lifecycles of software containers and their dynamic environment** |
| Action | used to **create, add, and remove containers** as per requirements; manages the environment for deploying containerized applications | manages the **lifecycles** of software containers and their **dynamic environment** |

**Orchestrators named:** **Docker Swarm** · **OpenShift** · **Kubernetes**
_(Mod 11 p90)_

- **Open source:** Kubernetes, Docker Swarm
- **Commercial:** **OpenShift by Red Hat**
_(Mod 11 p91)_

## Container technology architecture — five tiers _(Mod 11 p92)_

| # | Tier | Action |
|---|---|---|
| 1 | **Developer** | creates the **images** and sends them for **testing and accreditation** |
| 2 | **Testing and accreditation systems** | **validate, verify, and sign** the images, then send them to the **registry** |
| 3 | **Registry** | **stores and distributes** images **upon request from an orchestrator** |
| 4 | **Orchestrator** | converts the images into **containers** and **deploys them to the hosts** |
| 5 | **Host** | **runs and stops** the containers **on the direction of the orchestrator** |

## Two container types _(Mod 11 p92)_

| | **OS Containers** (figure: *System Containers*) | **Application Containers** |
|---|---|---|
| What | **virtual environments sharing the kernel of the host environment** that provides them isolated user space | containers used to run a **single application / single service** |
| Capability | user can **install, configure, and run different applications, libraries, etc.**; run **multiple services and processes** | **layered file systems**; **built on top of OS container technologies** |
| Fits | users that require an **operating system** to install various libraries, databases, etc. | users that need to **package an application and its components together for distribution** |
| Content | — | the **application, its dependencies, and hardware requirements file** |
| Examples | **LXC, OpenVZ, Linux Vserver, BSD Jails, Solaris Zones** | **Docker, Rocket** |

## Cards

OS virtualization (Module 11 LO06) — what is replicated, and what are the instances called?
?
The **host operating system's kernel is virtually replicated in multiple instances of isolated user space**, called **containers**, **software containers**, or **virtualization engines** — each instance gets (virtualized) OS functionality.

CaaS — what is it, and what can a subscriber build with it?
?
Services that enable the **deployment of containers and container management through orchestrators**. Subscribers can develop **rich, scalable containerized applications through the cloud or on-site data centers**.

Container engine vs container orchestration — define each.
?
**Container engine** = managed environment for deploying containerized applications; creates, adds, and removes containers. **Container orchestration** = **automated process of managing the lifecycles of software containers and their dynamic environment**.

Orchestrators named by the courseware — which are open source, which is commercial?
?
**Open source:** Kubernetes, Docker Swarm. **Commercial:** **OpenShift by Red Hat**.

OS containers vs application containers — definition and examples.
?
**OS containers** = virtual environments **sharing the kernel of the host**; run multiple services/processes; install libraries, databases. Examples: LXC, OpenVZ, Linux Vserver, BSD Jails, Solaris Zones. **Application containers** = run a **single application/service**, layered file system, built on OS container tech. Examples: Docker, Rocket.

Container technology architecture — the five tiers in order.
?
**Developer** creates images → **testing/accreditation systems** validate, verify, sign → **registry** stores and distributes images on request from an orchestrator → **orchestrator** converts images to containers and deploys to hosts → **host** runs and stops containers on the orchestrator's direction.
