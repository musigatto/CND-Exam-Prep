---
type: note
module: "19"
lo: "03"
tags: [concept, process, tool, mod/19]
topic: "IoE system and application surfaces"
exam_weight: unknown
status: done
unresolved:
  - "p19 IOE vs IoE casing varies on same page; body uses both"
  - "p21 Source prints as www.microsoft.com in body vs https://www.microsoft.com in figure caption; body form used"
  - "p22 CLI transcript and Figure 19.4 dashboard garbled in OCR; treated as non-evidence, not read"
  - "p23 Figure 19.3 tile text Attack Suface Analyze garbled; not read"
  - "p23 NT syste line truncated at 2000 chars in slice; omitted"
  - "p25 Source variants https://mwv.owasp.org vs https://www.owasp.org vs https://owasp.org; body form https://owasp.org used"
  - "p25 ASD capability sentence cut off at The Attack Surface Detector (ASD) tool can do the following; continuation is on p26 in sibling note"
---
[[MOC-Module-19]]

# IoE System and Application Surfaces (§19.03)

> **LO#03: Learn to identify Indicators of Exposures (IoEs)** _(Mod 19 p18)_
> Covers pp18–25.

## IoE definition _(Mod 19 p19)_

- **Indicators of Exposure (IoE)** refers to **potential risk exposures that attackers can use to breach the security of an organization**. _(Mod 19 p19)_
- Shows **potentially exploitable vectors before an incident actually occurs**; helps understand security posture and make more informed decisions to prevent breaches in advance. _(Mod 19 p19)_
- An IoE can represent: **existence of vulnerabilities** in the information system · **absence of security controls** · **insecure configuration** of security controls. _(Mod 19 p19)_
- IoEs include **software vulnerabilities, misconfigurations, missing security controls, overly permissive rules, and policy violations**. _(Mod 19 p19)_
- Collected from **vulnerability scanners, network and security device logs, and threat intelligence sources**; can be **visualized with attack surface visualization tools**. _(Mod 19 p19)_

See also [[19-LO03b-IoE-Network-and-Human-Surfaces]] for ASD continuation (p26) and network/human surfaces.

## Identification of IoEs _(Mod 19 p20)_

- Helps identify **potential vulnerable areas in identified network assets, topologies, and policies**; involves understanding the **nature and location** of possible IoEs and **collecting them**. _(Mod 19 p20)_
- By viewing exploitable attack vectors, teams **focus on critical exposures** and find measures to prevent data breaches. _(Mod 19 p20)_
- Working with identified IoEs instead of raw vulnerabilities uses **contextual analysis** to formulate actions that **minimize the attack surface with less effort**. _(Mod 19 p20)_
- Determining IoEs involves analyzing factors **including events** — e.g. an **unexpected firewall rule change (event) that opens up an access path to a critical asset** is an IoE. _(Mod 19 p20)_

## System surface — Attack Surface Analyzer _(Mod 19 pp21–22)_

- **Attack Surface Analyzer (ASA)** helps identify **security weaknesses introduced while installing software on Windows, Linux, or macOS**. Source: www.microsoft.com _(Mod 19 p21)_
- Shows changes to key elements of the system attack surface by **taking a snapshot before and after installation** of other software. _(Mod 19 p21)_
- Figure 19.3 Analyze Results and Figure 19.4 CLI transcript are dashboard captures — **non-evidence, not read**. _(Mod 19 pp21–22)_
- Allows developers to see **changes from adding their code** to assess the **aggregation of the attack surface**; displays particular **configuration changes which may result in potential threats**. _(Mod 19 p22)_
- **Determines threat severity and shows severity by category**. _(Mod 19 p22)_
- Comprises an **Electron-based GUI and CLI**; CLI results can be written to a **local HTML or JSON file**; snapshots stored in a **local SQLite database** used to generate reports on system changes. _(Mod 19 p22)_

| OS component ASA reports on | _(Mod 19 p22)_ |
|---|---|
| File system | Network ports |
| Certificates | Event logs |
| Registry | Services |
| Component Object Model (COM) objects | User accounts |
| Firewall settings | |

## System surface — Windows Sandbox Attack Surface Analysis Tool _(Mod 19 pp23–24)_

- Suite of tools that **analyzes the attack surface of the Windows OS for security vulnerabilities**; performs analysis of potential attack surface of **applications and services**, extracting accessible resources and services with **low-level inspection of the OS**. Source: https://github.com/googleprojectzero _(Mod 19 p23)_
- Researchers and developers find it useful to **verify the security of products on Windows OS**. _(Mod 19 p23)_

| Tool | What the page says it does _(Mod 19 pp23–24)_ |
|---|---|
| CheckDeviceAccess | Checks access to device objects |
| CheckExeManifest | Checks for specific executable manifest flags |
| CheckFileAccess | Checks access to files |
| CheckObjectManagerAccess | Checks access to object manager objects |
| CheckProcessAccess | Checks access to processes |
| CheckRegistryAccess | Checks access to registry |
| CheckNetworkAccess | Checks access to the network stack |
| DumpTypeInfo | Dumps simple kernel object type information |
| DumpProcessMitigations | Dumps basic process mitigation details on Windows8+ |
| NewProcessFromToken | Creates a new process based on an existing token |
| ObjectList | Dumps object manager namespace information |
| TokenView | Views and manipulates various process token values |
| NtApiDotNet | Basic managed library to access NT system calls and objects |
| NtObjectManager | PowerShell module that uses NtApiDotNet to expose the NT object manager |

## Application surface — OWASP Attack Surface Detector _(Mod 19 p25)_

- **Attack Surface Detector (ASD)** uncovers the **endpoints of a web application, the parameters endpoints accept, and the data type of parameters**. Source: https://owasp.org _(Mod 19 p25)_
- Includes **unlinked endpoints a spider will not find in client-side code** and **optional parameters completely unused in client-side code**. _(Mod 19 p25)_
- Can **calculate the changes in attack surface between two versions** of an application. _(Mod 19 p25)_
- Available as a **plugin to both ZAP and Burp Suite and as a CLI tool**. _(Mod 19 p25)_
- Burp/ZAP plugin screenshots on p25 are captures — **non-evidence, not read**; capability list headed by The Attack Surface Detector (ASD) tool can do the following continues on p26, covered in [[19-LO03b-IoE-Network-and-Human-Surfaces]]. _(Mod 19 p25)_







