---
type: note
module: "11"
lo: "07"
tags: [bestpractice, mod/11, flashcard/11]
topic: "Container Security Best Practices"
exam_weight: unknown
status: done
unresolved:
  - "p.118 'Ensure compliance with situation specific laws, frameworks, and Compliance - benchmarks (FISMA, NIST, etc.)' - the dash is an OCR-rendered break; no compliance scheme is named beyond FISMA and NIST, and the NIST page (p.117) is the only NIST item in the slice."
  - "p.118 lists 'avoid noisy neighbors' and 'permit network traffic only on default bridge' inside the Hardening bullet with no elaboration; the meaning is left as printed, not interpreted."
  - "p.117 cites NIST only as 'Source: https://nvlpubs.nist.gov' - no document number, title, SP number or section is given in the slice, so the recommendation set cannot be pinned to a specific NIST publication."
---

[[MOC-Module-11]]
# Container Security Best Practices (§11.07)

Closes LO#07: NIST recommendations (p.117) + the courseware's own best-practice list (p.118).

## NIST recommendations to secure containers _(Mod 11 p117)_

Source given: `https://nvlpubs.nist.gov`. _(Mod 11 p117)_

1. **Tailor the operational culture and technical processes** to support the new ways of developing, running and supporting applications made possible by containers.
2. **Container-specific host OSes** instead of general-purpose ones → reduce attack surface.
3. **Group only same-purpose / same-sensitivity / same-threat-posture containers** on a single host OS kernel → additional defense in depth.
4. **Container-specific vulnerability management tools and processes** for images → prevent compromise.
5. **Hardware-based countermeasures** → basis for trusted computing.
6. **Container-aware runtime defense tools**.

Mnemonic: **culture → distro → co-location → vuln mgmt → hardware → runtime defense**. _(Mod 11 p117)_

## Container security best practices — the closing list _(Mod 11 p118)_

Slide list: do not trust a container's software · know what is happening within each container · control root access · check the container runtime · lock down the operating system · secure containers that support the microservices-based architecture · verify that the images originate from a **trusted registry** · reduce containers' potential attack surface · define an effective **vulnerability assessment process** · embrace **isolation and least privilege** · apply **centrally managed access controls** · implement **real-time threat detection and incident response**. _(Mod 11 p118)_

## Prose expansion _(Mod 11 p118)_

| Theme | Content |
|---|---|
| **Hardening** | Configure containers against **benchmarks**; adopt control features for **host / daemon / kernel**; **avoid privileged mode execution**; avoid noisy neighbors; limit resources such as CPU/memory; permit network traffic **only on default bridge** |
| **Adopt minimal OS** | Minimize surface area of attack — e.g. **Canonical Light OS, Redhat Atomic** |
| **Image security** | **Multistage build** of an image + **image scanning (from registry)**; code-level security; ensure authenticity; enable **Docker content trust** |
| **Secret management** | **Separate until runtime, encrypt at rest** |
| **Health check** | Appropriate life-cycle management; **delete drifted containers**; control **container sprawl**; continuous monitoring of container traffic; service log management |
| **Process, file and device restrictions** | Privileges based on roles, **RBAC**; ensure authentication/authorization; **avoid the AUFS driver**; enable **user namespace** |
| **Trusted containers based on hardware** | Secure the trust chain |
| **Third-party tools** | For threat control; tools like the **Docker bench audit tool** facilitate configuration best practices |
| **Compliance** | Situation-specific laws, frameworks and compliance benchmarks (**FISMA, NIST**, etc.) |
| **Holistic approach** | Adopt a holistic approach and perform **security benchmarking** |

"Lock down the operating system" ← OS hardening layer: [[05-LO08-Windows-OS-Security-Hardening]]. Isolation + least privilege: [[03-LO02-Zero-Trust-and-Distributed-Access]]. Docker mechanics behind DCT / bench: [[11-LO08a-Docker-Security-Measures]], [[11-LO08b-Docker-Security-Tools]].

## Cards

NIST's six container recommendations, condensed.
?
Tailor operational culture and technical processes; use container-specific host OSes instead of general-purpose; group only same-purpose, same-sensitivity, same-threat-posture containers per host kernel; adopt container-specific vulnerability management for images; consider hardware-based countermeasures for trusted computing; use container-aware runtime defense tools. _(Mod 11 p117)_

The closing best-practice list: four items about the container's own environment and permissions.
?
Control root access; check the container runtime; lock down the operating system; embrace isolation and least privilege - plus centrally managed access controls. _(Mod 11 p118)_

Hardening bullet: list the six concrete configuration rules.
?
Configure against benchmarks, adopt control features for host/daemon/kernel, avoid privileged mode execution, avoid noisy neighbors, limit resources such as CPU/memory, permit network traffic only on default bridge. _(Mod 11 p118)_

Health-check and sprawl items in the best-practice prose.
?
Ensure appropriate life cycle management, delete drifted containers, control container sprawl, adopt continuous monitoring of container traffic, ensure service log management. _(Mod 11 p118)_

Two process/file/device restrictions named in the best-practice prose.
?
Avoid using the AUFS driver, and enable user namespace - with privileges based on roles, RBAC, and authentication/authorization. _(Mod 11 p118)_
