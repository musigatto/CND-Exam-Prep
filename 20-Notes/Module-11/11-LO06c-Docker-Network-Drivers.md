---
type: note
module: "11"
lo: "06"
tags: [tool, concept, mod/11]
topic: "Docker networking and drivers"
exam_weight: unknown
status: done
unresolved: ["p96 states that the CNM 'consists of the following five objects' but the slice itemizes only three (Sandbox, Endpoint, Network); the other two are not described in the text. The p96 figure does show a separate 'Network IPAM Driver' object alongside the 'Network Driver' object."]
---

[[MOC-Module-11]]

# Docker Networking and Drivers (§11.06)

## Docker control plane — why the network matters _(Mod 11 p94)_

Docker: **open source technology** for developing, packaging and running applications and all their dependencies **in the form of containers**, "to ensure that the application works in a seamless environment". Provides **platform-as-a-service (PaaS) through OS-level virtualization** and delivers **containerized software packages**. Client-server architecture. _(Mod 11 pp94–95)_

| Component | Function _(Mod 11 p94)_ |
|---|---|
| **Docker Daemon** | manages **images, containers, networks, and storage volume**; processes requests of the Docker API; performs container-related actions; **communicates with other daemons** to manage its services |
| **Docker Engine REST API** | used by an application to **communicate with the Docker daemon** |
| **Docker CLI** | command line interface to interact with the daemon; executes **build, run, and stop** commands |

**Transport:** the client interacts with the daemon using the **REST API through Unix sockets or a network interface**. Client and daemon can run on the **same system**, or a client can be pointed at a **remote Docker daemon**. _(Mod 11 p94)_

## Docker host objects _(Mod 11 p95)_

| Object | Definition |
|---|---|
| **Docker Client** | enables users to communicate with the Docker environment; key function = **retrieve images from the registry and run them on the Docker host**. Commands: `docker build`, `docker pull`, `docker run` |
| **Docker Host** | the environment to run an application = **daemon, images, containers, networks, storage** |
| **Images** | **read-only binary template** for building a container; container capabilities/requirements rely on the image **metadata**; hosted by **registries** |
| **Containers** | encapsulated environment to run an application; a container's **access to resources is defined by the image**; a new image can be created from the container's state |
| **Networking** | Docker has **networking drivers** to support networking containers; **application-driven** manner |
| **Registries** | services providing locations for **storing and downloading images**. Commands: `docker push`, `docker pull`, `docker run` |

## Container Network Model (CNM) _(Mod 11 p96)_

Docker allows **connecting multiple containers and services, or other non-Docker workloads, together**. The networking architecture is built on a set of interfaces known as the **CNM** — "**provides application portability across heterogeneous infrastructures**".

| CNM object | Definition |
|---|---|
| **Sandbox** | configuration of a **container's network stack** — routing table, management of container's interfaces, DNS settings; may have **multiple endpoints from various networks**. Implementable as **Windows HNS**, **Linux network namespace**, or a **FreeBSD jail** |
| **Endpoint** | connects a **sandbox to a network**; **abstracts the actual connection to the network from the application**; aids portability so the service can use various types of network driver |
| **Network** | a **collection of endpoints that have connectivity between them**; the corresponding driver is notified when a network is created or updated; a CNM network can implement a **Linux bridge, VLAN**, etc. |

**CNM has two pluggable, open driver interfaces** — for users, vendors, community — to "drive additional functionality, visibility, and control in the network". _(Mod 11 p96)_

## Network drivers _(Mod 11 pp96–97)_

**Network drivers** are pluggable and provide the **actual implementation for the functioning of the network**. **Multiple network drivers can be used simultaneously on a Docker engine or cluster**, but **each Docker network is represented by a single driver**.

| Type | Who provides them |
|---|---|
| **Native Network Driver** | **provided by Docker**; used through **Docker network commands** |
| **Remote Network Driver** | created by the **community and vendors** based on their requirements |

### Docker native drivers — **H-B-O-MAC-N** _(Mod 11 p97)_

| Driver | Stated behaviour |
|---|---|
| **Host** | container **uses the host networking stack** |
| **Bridge** | a **Linux bridge is created on the host**, which is **managed by the Docker** |
| **Overlay** | an **overlay network is created**; enables **container-to-container communication over the physical network infrastructure** |
| **MACVLAN** | a network connection is created between **container interfaces and its parent host interface (or sub-interfaces)** |
| **None** | container **implements its own networking stack** and is **isolated from the host networking stack** |

### IPAM drivers _(Mod 11 p97)_

- **IP address management drivers** in Docker provide **default subnets or IP addressing to the network and the endpoints**.
- A user can also **assign an IP address manually through the network, container, and service create commands**.

## Exam map

| Question cue | Answer |
|---|---|
| "container talks to the daemon" | **REST API over Unix sockets or a network interface** _(p94)_ |
| "which driver uses the host's stack" | **Host** _(p97)_ |
| "Linux bridge on the host, managed by Docker" | **Bridge** _(p97)_ |
| "container-to-container over the physical network" | **Overlay** _(p97)_ |
| "container interfaces ↔ parent host interface" | **MACVLAN** _(p97)_ |
| "own networking stack, no host connectivity" | **None** _(p97)_ |
| "default subnets / IP addressing" | **IPAM drivers** _(p97)_ |

→ [[11-LO03h-VLAN-Security]] (a CNM network can implement a Linux bridge or VLAN)







