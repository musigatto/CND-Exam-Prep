---
type: note
module: "11"
lo: "06"
tags: [concept, tool, mod/11, flashcard/11]
topic: "Kubernetes Cluster Architecture and Features"
exam_weight: unknown
status: done
unresolved:
  - "p98 lists 7 Kubernetes features (service discovery, load balancing, storage orchestration, automated rollouts and rollbacks, automatic bin packing, self-healing, secret and configuration management) but the p99 prose only expands the first four. 'Self-healing' and 'Secret and configuration management' have no supporting prose anywhere in pp.98-99; their meaning is not asserted here."
  - "p98 control-plane component list continues onto p99; etcd's description is split across the page break ('...used to determine number' / 'of instances that are running'). Rejoined, not inferred."
---

[[MOC-Module-11]]

# Kubernetes Cluster Architecture (§11.6)

Placed by the courseware inside the **containers** section, immediately after the Docker
material — not in the Kubernetes-security section. See [[11-LO09a-Kubernetes-RBAC-and-API-Server]]
for the security side.

## What Kubernetes is _(Mod 11 p98)_
- **K8s** — open-source, portable, extensible **orchestration platform developed by Google**
  for managing containerized applications and microservices
- Resilient framework to: manage distributed containers · generate deployment patterns ·
  perform **failover and redundancy**
- **Pod** = group of containers deployed together on the same host

## Cluster topology _(Mod 11 p98)_
- **Nodes** = worker machines running the containerized applications
- At least **one** worker node per cluster · nodes host the pods

## Control plane components _(Mod 11 p98–p99)_
Perform decisions for the cluster — **scheduling**, starting a new pod.

| Component | Role |
|---|---|
| **kube-apiserver** | Front-end API server, implementation of the Kubernetes API. Multiple instances may run to facilitate maintenance of traffic between instances |
| **etcd** | Backing store for cluster data. Specifying "three instances of a specific pod" is stored here; the stored data determines how many instances are running, and if one is not working K8s creates an additional instance of the same pod |
| **kube-scheduler** | Monitors newly created pods that have **no assigned node** and assigns each a node |
| **kube-controller-manager** | Runs the controller processes: **node, replication, endpoints, service account, token** controllers. All compiled and run as a **single process** to minimize complexity |
| **cloud-controller-manager** | Runs the controller that communicates with **cloud providers**; executes the cloud-provider-specific controller loops. Disable those loops by setting the `-cloud-provider` flag to `external`. Controllers with cloud-provider dependencies: **node, route, service, volume** |

## Node components _(Mod 11 p99)_
A node is a worker machine containing the services required to run pods, managed by master
components.

| Component | Role |
|---|---|
| **kubelet** | Node agent that ensures the containers are running in a pod. A pod contains a **PodSpec** (a YAML or JSON object); the kubelet ensures the containers named in the PodSpecs are **running and healthy** |
| **kube-proxy** | Network proxy that runs and **maintains network rules on each node** |
| **Container runtime** | Software that **downloads the images** and runs the containers. Supported runtimes: **Docker, CRI-O**, and the **container runtime interface (CRI)** |

## Features _(Mod 11 p98 list, p99 prose)_
| Feature | Courseware prose |
|---|---|
| **Service discovery** | A container is represented using **DNS** or its **own IP address** |
| **Load balancing** | When traffic to the container is high, traffic is **distributed** |
| **Storage orchestration** | Choose between **local storage**, **public cloud providers (AWS or GCP)**, or a **network storage system** |
| **Automated rollouts and rollbacks** | Change the **actual state** of the container to the **desired state** at a **controlled rate** |
| **Automatic bin packing** | Fit containers into nodes depending on the **specifications provided by the user** |
| Self-healing | listed on p98; no prose in the slice — see `unresolved` |
| Secret and configuration management | listed on p98; no prose in the slice — see `unresolved` |

## Cards

What is Kubernetes, and who developed it?
?
An open-source, portable, extensible **orchestration platform developed by Google** for managing containerized applications and microservices. It provides a resilient framework to manage distributed containers, generate deployment patterns, and perform failover and redundancy.

Which component is the Kubernetes backing store, and what happens when a pod instance dies?
?
**etcd.** It stores cluster data such as "run three instances of this pod"; that stored data determines how many instances are running, and if an instance is not working Kubernetes creates an additional instance of the same pod.

What does kube-scheduler do?
?
Monitors newly created pods that have **no assigned node** and assigns each of them a node to run on.

Name the five control-plane components of a Kubernetes cluster.
?
kube-apiserver · etcd · kube-scheduler · kube-controller-manager · cloud-controller-manager

What are the three services on a Kubernetes node, and what does each do?
?
**kubelet** — node agent ensuring the containers in a pod's PodSpec are running and healthy. **kube-proxy** — network proxy running and maintaining network rules on each node. **Container runtime** — software that downloads images and runs the containers (Docker, CRI-O, CRI).

How do you stop cloud-controller-manager from running the cloud-provider controller loops?
?
Set the `-cloud-provider` flag to `external`. The controllers with cloud-provider dependencies are the node, route, service and volume controllers.

Which Kubernetes storage backends does the courseware list under storage orchestration?
?
Local storage, public cloud providers (**AWS or GCP**), or a network storage system.
