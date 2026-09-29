---

type: note
module: "08"
lo: "05"
tags: [process, tool, command, bestpractice, mod/08, flashcard/08]
topic: "IoT Security Measures — Access, Vuln Mgmt, Firmware (M06–M10)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Security Measures — Access Control, Vulnerabilities, Firmware (§8.5, M06–M10)

## M06 — Network Access Control (Limit Access)
- Limit each device's access to only required apps/services
- On routers: user ACLs, **PACL** (Policy-based), **VACL** (VLAN Access Control Lists); **Cisco ASA ACL** / **Cisco IOS ACL**
- Once IoT device approves, dynamically allow only authorized flows
- Command family (Cisco IOS/ASA):
  `access-list 100 permit/deny ip-address host host` · `acl` on switch · `policy-map` · `vlan access-map` (VACL)

## M07 — Monitor Malware & Ransomware
- Continuously watch for **Mirai, Echobot, Torii, Dark Nexus, WannaCry (EternalBlue)** variants
- Use EDR/malware-analysis sandboxes; block known C2 domains; keep threat intel

## M08 — Scan for Vulnerabilities & Threats (Be Aware of Threat Landscape)
- Continuous vuln scanning of IoT network, OS, apps (CVEs)
- Tools: **Nexpose**, **Qualys (VM/CS)**, **Tenable**, **Cloudpassage Halo**, **AlienVault USM**, **Fortify**
- IoT-specific: **RloT Scanner**, **beSTORM** (~thousands of crash scenarios)

## M09 — Deploy Firmware Updates (Keep Devices Updated)
- Plan updates (patch firmware/OS as released); vet updates in sandbox; **OTA (over-the-air)** where supported; sign updates; rollback plan

## M10 — Close Insecure Network Services
- Disable unused services (Telnet, SNMP, TFTP, UPnP) on IoT devices
- Command style:
  `sudo nmap -sS -sU -O 10.10.10.10` · `netstat -tulpn` · `nmap --top-ports 1000 10.10.10.10`
- Result: reduce attack surface

## Cards
Security measures M06–M10?
?
Limit access (ACL/PACL/VACL) → monitor malware/ransomware → vulnerability scan → firmware updates → close insecure network services.

PACL vs VACL?
?
PACL = Policy-based access control list; VACL = VLAN access control lists.

IoT malware to monitor (M07)?
?
Mirai, Echobot, Torii, Dark Nexus, WannaCry (EternalBlue).

IoT vuln scanners (M08)?
?
RloT Scanner, beSTORM; also Nexpose, Qualys, Tenable, Cloudpassage Halo, AlienVault USM.

Firmware update best practice (M09)?
?
Vet in sandbox, OTA where supported, sign updates, rollback plan.

Port/service closure command (M10)?
?
sudo nmap -sS -sU -O <target> · netstat -tulpn · nmap --top-ports 1000 <target>.
