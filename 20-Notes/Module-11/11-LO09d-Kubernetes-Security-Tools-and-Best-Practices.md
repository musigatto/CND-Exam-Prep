---
type: note
module: "11"
lo: "09"
tags: [tool, bestpractice, mod/11, flashcard/11]
topic: "Kubernetes Security Tools, CIS Benchmark and Patching"
exam_weight: unknown
status: done
unresolved:
  - "p.152 states Istio 'implements certifications and encryption for pod-to-pod communication using mutual transport layer security (TLS)'. 'certifications' is printed verbatim; the slice does not state what is being certified."
  - "p.152 names exactly two Kubernetes security tools (Istio, Grafeas) in this range; no vendor list, no versions and no install steps are given."
  - "p.154 names Amazon EKS as 'Elastic Kubernetes Services' in parentheses - printed as-is, not corrected."
  - "p.154 the only versioned command in the update guidance prints as 'sudo apt-get update && apt-get install -y kubeadm=1.26.3-00' (OCR: 'kubeadm=l .26.3-00'); the version token is read as 1.26.3-00. No other version numbers appear in the slice."
  - "p.156-157 are the closing module summary; the earlier LO09 guidance is not restated there, so only the summary statements carried in this range are recorded."
---

[[MOC-Module-11]]
# Kubernetes Security Tools, CIS Benchmark and Patching (§11.09)

Closing LO#09 material: **tools → compliance/auditing → keep the cluster up to date → module summary**. Policy content: [[11-LO09a-Kubernetes-RBAC-and-API-Server]], [[11-LO09b-Kubernetes-Audit-Policy]], [[11-LO09c-Kubernetes-Pod-Security-Policy]].

## Kubernetes security tools _(Mod 11 p152)_

| Tool | Source | Stated function |
|---|---|---|
| **Istio** | `www.istio.io` (slide shows `https://istio.io`) | Helps **connect, secure, control, and observe services**. Creates a **service mesh** for managing **service-to-service communication, including routing, authentication, and encryption**. Implements "certifications" and **encryption for pod-to-pod communication using mutual transport layer security (TLS)** |
| **Grafeas** | `www.github.com` | An **open source initiative to define a best practice for auditing and governing the modern software supply chain**. Provides auditing and governing of the software supply chain and **defines an API spec for managing metadata about software resources** such as **container images, virtual machine images, JAR files, and scripts** |

These are the only two tools named in this range — see `unresolved`.

## Compliance and auditing: CIS Benchmark _(Mod 11 p153)_

- Kubernetes is a **complex system with various components, each with numerous configuration parameters**. The **Center for Internet Security (CIS)** publishes a series of **benchmarks for secure configuration in Kubernetes**, as per security best practices. _(Mod 11 p153)_
- The benchmarks document consists of instructions on **how to audit** (check if a configuration matches the recommendation) and **how to remediate** a setup that does not pass an audit test. _(Mod 11 p153)_

**Worked example from the module** — *basic authentication uses plaintext credentials for authentication*, therefore ensure the **`--basic-auth-file` argument is not set**; run on the **master node**: _(Mod 11 p153)_

```bash
ps -ef | grep kube-apiserver
```

## Keep Kubernetes up-to-date _(Mod 11 p154–p155)_

To maintain **security, stability, and performance** of the container orchestration environment, keep Kubernetes up to date; new versions are released regularly **with important security patches and feature enhancements**. _(Mod 11 p154)_

| Practice | Detail |
|---|---|
| **Stay informed** | Regularly review the **Kubernetes release notes, security advisories, and the official Kubernetes blog** for new releases, features, and security updates |
| **Back up first** | Before updating, have a **reliable backup of the entire cluster** — configurations, applications, and data — usable to recover from any issue during the update |
| **Managed distributions** | Understand the update policies of **Google Kubernetes Engine (GKE), Amazon EKS (Elastic Kubernetes Services), Azure Kubernetes Service (AKS)** — they handle the update process |
| **Manually managed clusters** | Use tools such as **`kubeadm`** and **`kops`** to update Kubernetes containers without data loss |
| **Update everything** | Update both the **control plane components (e.g. API server, scheduler)** and the **worker nodes** |
| **Check compatibility** | Ensure **plugins, add-ons, and extensions** (networking solutions, storage drivers, monitoring tools) are **compatible with the updated Kubernetes version** |
| **Verify afterwards** | Updating components such as controllers, network plugins, and monitoring tools helps containers and clusters function safely; after updating it is crucial to **run container tests** to ensure efficiency and identify modifications made during the process, **thoroughly test all applications and services** for accuracy, and **update any relevant documentation** with the changes |
| **Ubuntu example** | `sudo apt-get update && apt-get install -y kubeadm=1.26.3-00` |

## Module summary tail _(Mod 11 p156–p157)_

- **Kubernetes (K8s)** is an **open-source, portable, extensible, orchestration platform** for managing **containerized applications and microservices**. _(Mod 11 p156, p157)_
- **Pod security policies provide central cluster-level configuration and security controls for Kubernetes.** _(Mod 11 p156, p157)_
- Container hardening and security practices must secure **container images, container runtime, container secrets, and registry**; these protect containers from being compromised. _(Mod 11 p156)_
- The module covered network virtualization (NV), SDN, NFV, OS virtualization, and provided **security guidelines, recommendations, and best practices to secure containers, Dockers, and Kubernetes**. _(Mod 11 p156)_

## Cards

Istio: source and what it does for Kubernetes security.
?
Source www.istio.io. It helps connect, secure, control and observe services, creating a service mesh for service-to-service communication including routing, authentication and encryption, and encrypting pod-to-pod communication with mutual TLS. _(Mod 11 p152)_

Grafeas: source and scope.
?
Source www.github.com. An open source initiative defining a best practice for auditing and governing the modern software supply chain, with an API spec for metadata about software resources - container images, virtual machine images, JAR files, scripts. _(Mod 11 p152)_

What does the CIS Kubernetes benchmark give you, and what is the module's example check?
?
Instructions to audit a configuration against the recommendation and to remediate setups that fail the audit test. Example: basic authentication uses plaintext credentials, so ensure --basic-auth-file is not set, checked with ps -ef | grep kube-apiserver on the master node. _(Mod 11 p153)_

Which tools are named for updating a manually managed Kubernetes cluster, and what must also be updated?
?
kubeadm and kops. Update both the control plane components (API server, scheduler) and the worker nodes, and check that plugins, add-ons and extensions are compatible with the new version. _(Mod 11 p154)_

Before and after updating a Kubernetes cluster, what do the best practices require?
?
Before: reliable backup of the entire cluster - configurations, applications, data. After: run container tests, thoroughly test all applications and services, and update the documentation with the changes. _(Mod 11 p154, p155)_
