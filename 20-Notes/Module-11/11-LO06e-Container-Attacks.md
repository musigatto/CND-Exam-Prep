---
type: note
module: "11"
lo: "06"
tags: [threat, mod/11]
topic: "Container and Kubernetes attacks"
exam_weight: unknown
status: done
unresolved: ["Fig. p108 lists five causes for inner-container attacks, the first OCR'd as 'Overage software'. The intended term cannot be resolved from the slice, so it is left as printed and not guessed.", "Fig. p109 'Kubernetes Security Challenges and Threats' lists eight challenges but the slice gives prose for only three (explosion of east-west traffic, increased attack surface, automating security to keep pace). 'Too many containers', 'Communication between containers', 'Default configuration settings', 'Runtime security challenges' and 'Compliance issues' appear in the figure with no accompanying statement, so none is invented here."]
---

[[MOC-Module-11]]

# Container and Kubernetes Attacks (§11.06)

## A. Docker security threats _(Mod 11 p107)_

"There are specific parts of the Docker infrastructure that are vulnerable to attacks."

### A1. Escaping _(Mod 11 p107)_

Adversary **escapes the container and gains root access on the host server**, then attempts to **compromise other machines within the local network**.

**Factors that may facilitate container breakouts:**

| # | Factor |
|---|---|
| 1 | **Insecure defaults and weak configuration** |
| 2 | **Information disclosure** |
| 3 | **Weak network defaults** |
| 4 | **Working with the root user (UID 0)** |
| 5 | **Mounting host directories inside containers** |

### A2. Cross-container attacks _(Mod 11 p107)_

Adversary **gains access to a container and utilizes it to attack other containers of the same host or within the local network**. Consequences named: **DoS attacks (e.g. XML bombs)**, **ARP spoofing and stealing of credentials**, **compromising of the sensitive container**.

| Listed outcome _(Fig. p107)_ | Detail |
|---|---|
| **DoS for other containers** | noisy neighbor using a significant % of resources — **CPU, memory, disk** |
| **Access other container's information** | gain access to **PIDs, files**, etc. of other containers |
| **Docker API access** | **full control over other containers** |

Causes: **weak network defaults** · **weak cgroup restrictions** · **working with the root user (UID 0)** _(Mod 11 p107)_

### A3. Inner-container attacks _(Mod 11 p108)_

Attacker **gains unauthorized access to a single container**. Causes as listed:

`Overage software` _(OCR-uncertain)_ · exposure to **insecure/untrusted networks** · use of **large base images** · **weak application security** · working with the **root user (UID 0)**

### A4. Docker registry attacks _(Mod 11 p108)_

| Attack | Technique |
|---|---|
| **Image forgery** | adversary gains access to the **registry server** and **tampers with the Docker image** |
| **Replay attack** | adversary gains access to the **registry server** and **provides outdated content** |

> UID 0 (root) appears in **escaping, cross-container and inner-container** — the single most-repeated facilitator in this section. → [[06-LO04b-Linux-File-Permissions-SUID]]

## B. Kubernetes security challenges _(Mod 11 p109)_

"Containerization in clouds can be targeted through attacks such as **ransomware attacks, cryptomining, data stealing, and service disruption**." The **hyperdynamic nature** of containers is responsible for the following challenges.

| Challenge | Stated consequence | Fig. only? |
|---|---|---|
| **Explosion of east-west traffic** | containers are **dynamically deployed in multiple hosts or clouds**; **east-west traffic** (traffic flow **within a data center**) and internal traffic **should be monitored for attacks** | |
| **Increased attack surface** | **every container has an attack surface and vulnerabilities**; additionally, **container orchestration tools like Docker and Kubernetes also increase the attack surface** of the container | |
| **Automating security to keep pace** | the **dynamic nature and constantly changing environment** mean **old models and security tools cannot provide complete protection** → security **must be automated** | |
| Too many containers | — | • |
| Communication between containers | — | • |
| Default configuration settings | — | • |
| Runtime security challenges | — | • |
| Compliance issues | — | • |

"Kubernetes containers are **vulnerable to attacks externally through the network or internally by an insider**." _(Mod 11 p109)_

## C. Kubernetes vulnerabilities and attacks _(Mod 11 p110)_

| Attack | Technique | Impact / next step |
|---|---|---|
| **Container compromise** | **misconfiguration of an application** | attacker gains access to the container and **searches for weaknesses in the network, process controls, or file system** |
| **Unauthorized connections between pods** | adversary **connects the compromised container to the pods in the same host or different hosts** | launches an attack across pods |
| **Data exfiltration from a pod** | **reverse shell in a pod connecting to a command/control server**; **network tunneling for hiding sensitive information** | data leaves the cluster without a visible transfer |
| **Compromised container running malicious process** | a compromised container may run **cryptomining, network scanning, and port scanning** (it "normally runs a well-defined set of processes") | covert compute abuse + internal recon |
| **Container file system compromised** | adversary **installs vulnerable libraries/packages** | then attempts **privilege escalation to root** or other breakouts |
| **Compromised worker node** | the **host running the containers** is compromised through vulnerabilities such as the **dirty cow Linux kernel vulnerability**, which enables **user privilege escalation to root** | whole node and its pods fall |

**Vulnerable Kubernetes components** _(Fig. p110)_: **Management server** · **UI/API services** · **etcd** · **kubelets** · **compromised nodes, pods and accounts** · **exposed dashboard and kubelets**

→ exfiltration playbook: [[10-LO08-Data-Loss-Prevention]] · kernel escalation: [[06-LO03b-Linux-Integrity-SecureBoot-Packages-Rootkits]]

## Attack-pattern index

| Attacker position | Move | Courseware label |
|---|---|---|
| Inside a container | escape to host, gain root | **Escaping** _(p107)_ |
| Inside one container | pivot to sibling/local-network containers | **Cross-container** _(p107)_ |
| Outside a single container | take over just that container | **Inner-container** _(p108)_ |
| On the registry | tamper / roll back content | **Image forgery / Replay** _(p108)_ |
| On a pod | exfiltrate via C2 reverse shell or tunneling | **Data exfiltration from a pod** _(p110)_ |
| On a worker node | dirty cow → root → node | **Compromised worker node** _(p110)_ |






