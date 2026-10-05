---
type: note
module: "19"
lo: "01"
tags: [concept, process, threat, mod/19]
topic: "attack surface analysis concept"
exam_weight: unknown
status: done
unresolved:
  - "p7 software surface says accessible to an authorized user but p6 says accessible to an unauthenticated user; kept both wordings as printed"
  - "p7 physical threat types truncated after Insider threats; second type not stated in slice, omitted"
---
[[MOC-Module-19]]

# Attack Surface Analysis Concept (§19.01)

> **LO#01: Understand attack surface analysis** _(Mod 19 p4)_
> Covers pp4–9.

## Attack surface definition _(Mod 19 p5)_

- Attack surface is the **sum of all possible exposures (known, unknown, and potential)** that exist in the information system through which an unauthorized user or attacker can access the organization's assets.
- Possible exposures include **protocols, interfaces, user input fields, and services**.
- Organization's surface includes **unpatched vulnerabilities, open ports, misconfigured networks, excess privileges granted to users, improper network segmentation, employees unaware of security controls**.
- Fewer vulnerabilities gives **smaller surface, less exploitable, reduced risk**; greater surface gives **more vulnerable, increased risk**.
- Standard practice: keep attack surface **as minimum as possible**.

## Five surface categories _(Mod 19 pp6–8)_

| Surface | What it covers | Printed example |
|---|---|---|
| Network | Vulnerabilities in hardware, software, firmware interfaces accessible to an unauthenticated user | Unnecessary open ports and services running on public IP |
| Software | Vulnerabilities in code, configuration, complete profile of application functions | Unvalidated input fields / entry points |
| Physical | Vulnerabilities in hardware system; direct attack surface by physical means | USB ports enabled on a laptop; endpoint devices (desktops, laptops, mobiles, USB ports, improperly discarded hard drives) |
| Human | Vulnerabilities related to human weaknesses; weakest point | Employees unaware of social engineering with access to sensitive information; fake calls giving up passwords |
| System | Attack surface of the OS; all entry points of services and applications running on the system; more services means greater surface | Unused roles from Windows systems; selecting features or components not needed |

## Network surface details _(Mod 19 p7)_

- **Unencrypted protocols** passing unencrypted data — **Telnet, FTP, HTTP, SMTP**.
- **Network file systems** passing unencrypted information — **NFS, SMB**.
- **Remote memory dump service (`netdump`)** passing unencrypted contents of memory.
- **Network printers**.

## Software surface details _(Mod 19 p7)_

- Covers code kinds — **applications, OSes, mobile apps, DLLs, databases, web pages, executables, email services, configurations**.
- **Unpatched software (Java, Adobe Reader, Adobe Flash)**.

## Physical surface details _(Mod 19 pp7–8)_

- Attacker with physical access can **scan network, ports, services to create a network map; access running databases; upload malware; crack credentials; copy data to removable devices or remote servers**.
- Exploited through **insider threats** plus a second type cut off in the slice (see unresolved).

## Human and system details _(Mod 19 p8)_

- Human targets are users who **want something for free, help anyone for goodwill, can be easily manipulated**.
- Human examples: **fake calls giving up passwords; losing removable devices with sensitive information; accessing legitimate websites with trojans or viruses**.
- System examples as in table above.

## Attack surface analysis _(Mod 19 p9)_

- Analysis is an **assessment of all possible exploitable vulnerabilities** in an organization's potential attack target.
- Helps with **identifying functions and parts that must be reviewed or tested; identifying high-risk code needing defense-in-depth; identifying when the surface changed and what threat assessment is needed; filtering issues speedily without financial disaster; continuous discovery of exposures before attackers exploit**.
- Steps in order:
  1. **Understand and Visualize the Attack Surface** — mapping all devices, paths, networks.
  2. **Identify the Indicators of Exposures (IoEs)** — potential risk exposures attackers can use to breach security.
  3. **Simulate the Attack** — recognizing how the identified IoE could turn to exploit.
  4. **Reduce the Attack Surface** — implementing controls and countermeasures.

See also [[MOC-Module-18]] for the vulnerabilities this analysis exposes.






