---
type: note
module: "11"
lo: "08"
tags: [tool, mod/11]
topic: "Docker Security Tools"
exam_weight: unknown
status: done
unresolved:
  - "p.124 figure 'Additional Container Security Tools' is a names-only list in scrambled column order: CoreOS Clair, Aqua Security, Anchore, NeuVector, CloudPassage, Halo, Aporeto, Tenable, Flawcheck, Black Duck, capsule8, StackRox, Sysdig, Falco, Hashicorp Vault. Only Aqua, Anchore, NeuVector, CloudPassage, Tenable, capsule8 and StackRox get prose elsewhere; the rest carry no stated function in the slice."
  - "'Flawcheck' in that figure list is OCR-garbled and cannot be resolved confidently - possibly a misread of another product; listed verbatim, no function asserted."
  - "p.124 the Docker Bench Security screenshot is heavily garbled; the legible check texts are listed below but the numbering (5.19-6.3) is NOT reliable, so no check number is attached to any item."
  - "'Docker bench audit tool' (p.118) and 'Docker Bench Security' (p.124) are two spellings of the bench script across the slice; treated as the same tool, both spellings kept."
---

[[MOC-Module-11]]
# Docker Security Tools (§11.08)

" A number of third-party tools can assist in the maintenance of Docker security." The catalogue starts with a **bench script**, then **eight described vendors** with their stated source URLs. Measures behind them: [[11-LO08a-Docker-Security-Measures]]; image-side rules: [[11-LO08c-Docker-Security-Best-Practices]]. _(Mod 11 p124–p126)_

## Docker Bench Security _(Mod 11 p124)_

A **script that enables checking**. The slice's own list of what it checks:

- **Host Configuration**
- **Docker Daemon Configuration**
- **Docker Daemon Configuration Files**
- **Container Images and Build Files**
- **Container Runtime**

Referenced on p.118 as the "**Docker bench audit tool**" for facilitating configuration best practices, and as a source of **security benchmarking**. _(Mod 11 p118)_

Legible check texts from the screenshot (numbering unreliable): do not set mount propagation mode to shared · do not share the host's UTS namespace · do not disable default seccomp profile · do not `docker exec` commands with privileged option · do not `docker exec` commands with user option · confirm cgroup usage · restrict container from additional privileges · check container health at runtime · ensure docker commands always get the latest version of image · use PIDs cgroup limit · do not use Docker's default bridge network (`docker0`) · do not share the host's user namespaces · security operations: perform regular security audits of your host system, Docker containers usage/performance, backup container data. _(Mod 11 p124)_

## Described tools _(Mod 11 p124–p126)_

| Tool | Source | Stated function |
|---|---|---|
| **Twistlock** | `www.twistlock.com` | Secures **VMs, containers, serverless functions and service meshes**, or combinations. Holistic platform protecting hosts, networks, applications. **Real-time intervention, blocking and prevention** for in-process runtime attacks; insights into attempted attacks via detailed forensics, auditing, real-time log analytics; granular access control across all pivots and segments. _(p124)_ |
| **Aqua** | `www.aquasec.com` | **Dev-to-prod** security across the entire **CI/CD pipeline and runtime**; end-to-end visibility; controls consistently enforced across orchestrators, on-premises or cloud. Adopts **least-privilege whitelisting** to detect/prevent anomalous behavior, privilege escalation, code injection. _(p124)_ |
| **Anchore** | `https://anchore.com` | In the **build pipeline**: analyzes images and creates **software container bills of materials**. Triggered when new code is committed and pushed. Integrates with Kubernetes via **admission controllers**, so only images meeting the organization's policies are deployed. _(p125)_ |
| **NeuVector** | `https://neuvector.com` | Cloud-native **Kubernetes** security platform, end-to-end: DevOps vulnerability protection → automated runtime security, with a true **layer 7 container firewall**. Blocks suspicious processes and file-system activity to prevent exploits/breakouts; automated segmentation, **DPI**, and attack detection for **DDoS, DNS, SQL injection, DLP** breaches. _(p125)_ |
| **CloudPassage** | `www.cloudpassage.com` | **CloudPassage Halo** — security automation: visibility, protection, continuous compliance monitoring. Assesses **cloud compute, storage and other infrastructure services such as containers, server instances, serverless functions**; maintains **CIS benchmark** and other best-practice/regulatory compliance via built-in customizable policies. _(p125)_ |
| **Tenable** | `www.tenable.com` | **Tenable.io** container security: end-to-end visibility of Docker images — vulnerability assessment, malware detection, policy enforcement across the SDLC, development → operation. Integrates with developer build systems (visibility at the pace of DevOps), monitors a wide range of **external vulnerability databases**, and addresses new risks emerging **after deployment**. _(p125)_ |
| **Capsule8** | `https://capsule8.com` | Attack detection and response for **Linux** environments — containerized, virtualized or bare-metal, on-premises and in the cloud. **Distributed, streaming analytics** + high-fidelity data detection; automatic response the instant an attack is attempted; continuous expert updates against the latest **zero-day** attacks. _(p125)_ |
| **StackRox** | `www.stackrox.com` | Protects cloud-native apps across the **full life cycle — build, deploy, runtime**. Monitors, collects and evaluates **system-level events**: process execution, network connections and flows, privilege escalation, files launched within each container in Kubernetes → suspicious activity detected faster. Applies **pre-defined policies** to detect threats: **cryptocurrency mining, privilege escalation, various exploits**. _(p126)_ |

## Names-only figure _(Mod 11 p124)_

"Additional Container Security Tools": **CoreOS Clair · Aqua Security · Anchore · NeuVector · CloudPassage · Halo · Aporeto · Tenable · Flawcheck (garbled) · Black Duck · capsule8 · StackRox · Sysdig · Falco · Hashicorp Vault**. The slice gives no function for these beyond the entries above. Snyk is used separately for image scanning: [[11-LO08c-Docker-Security-Best-Practices]] _(p127)_







