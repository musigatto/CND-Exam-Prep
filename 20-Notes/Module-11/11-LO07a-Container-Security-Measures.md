---
type: note
module: "11"
lo: "07"
tags: [bestpractice, mod/11]
topic: "Container Security Measures"
exam_weight: unknown
status: done
unresolved:
  - "p.112 three measures exist on the slide only, with no prose elaboration anywhere in the slice: 'Automate security', 'Integrate security testing and secure the container deployment environment and infrastructure', 'Integrate enterprise security tools to enhance security policies'."
  - "p.116 prose reads 'Create a trust chain (Intel TXT, Bootloader, Initrd, etc.): This automates container security.' The stated rationale looks garbled/wrong; quoted as printed, not interpreted."
  - "The slice contains no vendor-neutral method, no CVE data and no concrete command for the container blocks on pp.112-116; none is asserted."
---

[[MOC-Module-11]]
# Container Security Measures (§11.07)

LO#07 target: the security **measures, best practices and recommendations for the security of containers**. _(Mod 11 p111)_
Four blocks in order: **hardening → image → secrets → runtime**. Secrets have their own note ([[11-LO07b-Container-Secrets-Management]]); NIST + closing list in [[11-LO07c-Container-Security-Best-Practices]]; the Docker-specific equivalents in [[11-LO08a-Docker-Security-Measures]]. _(Mod 11 p112–p118)_

## Container hardening — measures to implement against vulnerabilities _(Mod 11 p112)_

| Measure | Stated rationale |
|---|---|
| **Limit container communications to defined segments** | Prevents unauthorized connections |
| **Prevent unauthorized network connections** | Use **network firewall technology**; protects running containers |
| **Alerts based on security baselines** | Create a **runtime security policy** that prompts alerts and remedies when suspicious activity is observed |
| **Audit container activity** | Resolve issues pertaining to the org's containers from **operational logs, configuration data, process documents** |
| **Automate security** | Container adoption is rising → automation finds vulnerabilities promptly and makes container management less challenging |
| **Authenticate and authorize container actions** | Safeguard the container, prevent unauthorized access |
| **Disable unused OS capabilities** | Reduces vectors of attack to a significant extent |
| **Image signing and verification** | Validates images + enforces policies **while retrieving them into the system** |
| **Enforce fine-grained access control** | As needed for granting and managing permissions |

Slide also lists, without prose: automate security; integrate security testing and secure the container deployment **environment and infrastructure**; integrate **enterprise security tools** to enhance security policies. _(Mod 11 p112)_

## Container image security _(Mod 11 p113)_

"The security of container images is crucial when a user migrates to Docker." Exposure prevented by:

| Measure | Detail |
|---|---|
| **Verify the image source** | Download from a reliable source |
| **Sign + verify (DCT)** | **Docker content trust (DCT)** lets image publishers (individuals or organizations) sign the image and assure consumers it is authentic; sign the **tagged version** with default Docker options → **Docker image integrity** |
| **Image scanning** | Scanning services from **third-party vendors** |
| **Strong access control for images** | Apply **task-centric access control or RBAC** to limit the damage if one container is compromised |
| **Non-root** | By default **all users have root privilege** → change to non-root |
| **Lightweight** | Too many packages reduce performance and cause security issues; lightweight increases performance and **decreases attack surface area** |
| **Runtime health monitoring** | Threat detection tools to monitor image health during runtime |
| **Patch currency** | Keep images up to date with latest versions and security patches |
| **No secrets in files** | Do not store confidential tokens etc. in the **container file or Dockerfile** |

## Container runtime security — key aspects _(Mod 11 p115–p116)_

- **Few processes** — a container should have only a few running processes; many processes make it complicated to manage and troubleshoot. _(Mod 11 p115)_
- **Be task-specific** — paths, ports, daemon configuration, mount points. _(Mod 11 p115)_
- **Runtime + OS layers up to date** — outdated containers pose **compatibility, performance, security** risks; current ones offer portability, isolation, scalability. _(Mod 11 p115)_
- **Monitor in-house applications** — performance and health visibility into the application; monitoring finds **vulnerabilities lurking in the image**. _(Mod 11 p115)_
- **Generous logs, searchable format** — log analysis identifies **unused containers** → remove them from the host. _(Mod 11 p115)_
- **Policies specific to container behavior** — a policy on a **monitored image** imposes specific behavior constraints. _(Mod 11 p115)_
- **Mount as read-only** + restrict copy/write permissions → writing prevented when only reading is required, container filesystem **immutable**, risk of unauthorized change/tampering with critical files reduced. _(Mod 11 p115–p116)_
- **Boot trust chain** — trusted containers based on hardware: **Intel TXT, Bootloader, Initrd**, etc. _(Mod 11 p115–p116)_
- **Limit container privileges** — grant only what is required to run; safe to give **fine-grained privileges by granting specific capabilities** instead. _(Mod 11 p116)_
- **Container orchestration tools** — threats uncovered directly within the container code and the running environment. _(Mod 11 p116)_
- **Security patches** — apply them, keep runtimes up to date → latest security improvements and bug fixes. _(Mod 11 p116)_
- **Secrets management at runtime** — identify which authn/authz secrets are required to control and where they are needed; know how secrets are configured, stored, managed. _(Mod 11 p116)_
- **Security at the application level** — techniques that protect application code, find vulnerabilities, give insight into application security. _(Mod 11 p115)_

OS-level lockdown: [[05-LO08-Windows-OS-Security-Hardening]]. Least privilege / fine-grained access control: [[03-LO02-Zero-Trust-and-Distributed-Access]].







