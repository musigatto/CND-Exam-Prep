---
type: note
module: "19"
lo: "04"
tags: [process, tool, mod/19]
topic: "attack simulation and tools"
exam_weight: unknown
status: done
unresolved:
  - "p36 figure caption prints Source: https://www.akamai.com while body prose prints Source: www.guardicore.com; note records the prose form"
  - "p38 BAS Vendors tile lists AttackIQ, CyCognito and XM Cyber with prose; omitted per assignment scope (note covers Infection Monkey, Cymulate, Picus, SafeBreach, FireMon, WhiteHaX, PhishThreat only)"
---

[[MOC-Module-19]]

# Attack Simulation and Tools (§19.04)

> **LO#04: Learn to conduct attack simulation** _(Mod 19 pp34–41)_
> Covers pp34–41.

## Purpose

- Conducting an attack simulation helps a network defender **validate and manage the security controls** across the organization _(Mod 19 p34)_
- It enables a network defender to **assess the security flaws before any attack takes place** _(Mod 19 p34)_
- An attack simulation helps a network defender recognize **how identified Indicators of Exposure (IoEs) could become an exploit** or **how the organization looks from the attacker's perspective** _(Mod 19 p35)_
- It involves running **virtual penetration testing to uncover cyberattack scenarios**; done by simulating an attack that aims to **exploit vulnerable areas** _(Mod 19 p35)_
- **BAS tools** help run a virtual penetration test on the target organization _(Mod 19 p35)_

## How a simulation runs

- The attack simulation looks at an organization as a **single unit** but focuses on a **specific application/system** while performing penetration testing _(Mod 19 p35)_
- The target (**Network, Software, Application, or Human**) is attacked to meet the assessment goals _(Mod 19 p35)_
- The simulation starts with **goal setting, reconnaissance, and attacking servers and services** to find the spots in the network _(Mod 19 p35)_
- Through **social engineering, phishing simulation, and data exfiltration testing**, the network is attacked to identify the breaches _(Mod 19 p35)_
- The organization obtains a **broad overview of the attack surface and security posture** _(Mod 19 p35)_
- Simulate the attack by taking a **small input or change** to the network to know the following _(Mod 19 p35)_
  - How can any of the vulnerable exposures become exploits?
  - What happens if the asset is moved?
  - What happens if the topology and routing rules are changed?
  - What happens if a policy is added or removed?
  - What would be the result if an attack came in a particular way?

Related: [[19-LO05a-Reduce-the-Attack-Surface]]

## Tools — prose capabilities only

| Tool | What the page says it does | Source as printed |
|---|---|---|
| Infection Monkey | Open-source BAS tool that **tests and evaluates the strength of a network security configuration**; simulates a breach by **infecting any random server within Cloud or on-premises infrastructure**, then runs around the network through different methods to enter the propagation paths and to **attack every identified vulnerability point** _(Mod 19 p36)_ | Source: www.guardicore.com |
| Cymulate | Enables organizations to handle cybersecurity threats by **simulating the different strategies that hackers use to attack network and endpoint security infrastructures**; identifies security gaps automatically in **one click** and describes **how to fix them exactly** _(Mod 19 p37)_ | Source: https://cymulate.com |
| Sophos PhishThreat | **Educates and tests the end users through automated attack simulations and quality security training awareness**; combines training and testing to make easy-to-use campaigns with **automated on-the-spot training**; gives numerous realistic and challenging phishing attacks in less processes and helps users understand the health of an organization _(Mod 19 pp38–39)_ | Source: https://www.sophos.com/en-us |
| Picus Security | Helps to **measure and strengthen cyber solutions and resilience by automatically testing the effectiveness of cyber detection tools**; finds and fixes unwanted exposures that put critical assets at risk; complete **security control validation** platform that helps identify logging and alert gaps needing additional action to **optimize the SIEM** _(Mod 19 p40)_ | Source: https://www.picussecurity.com/ |
| SafeBreach | Continuously **monitors and validates all layers of security by simulating real-world attacks**; unlocks visibility into security controls so administrators can take immediate action against potential vulnerabilities; increases security control effectiveness and real threat emulation and helps improve cloud security; visualize reports for better understanding of the environment status _(Mod 19 p40)_ | Source: https://www.safebreach.com |
| FireMon | Addresses **change detection and reporting, compliance, and behavioral analysis**; vulnerability management technology under **Security Manager and Cloud Defense**, offering real-time risk assessment, mitigation and validation; attack path graphics and analysis enable administrators greater visibility _(Mod 19 p41)_ | Source: https://www.firemon.com/ |
| WhiteHaX | **Cloud-hosted automated, cyber security readiness verification pen-testing platform**; provides a cyber insurance version of business readiness by enabling numerous attack simulations against deployed security architecture, perimeter firewalls and security and controls; protects from **phishing, ransomware attacks and malware** _(Mod 19 p41)_ | Source: https://www.ironsdn.com/ |

### Printed key features (quoted)

- Cymulate — Exercise defenses against a wide range of attack vectors; provide an **Advanced Persistent Threat (APT) simulation** of security posture at all times; test ability to cope with **pre-exploitation-stage threats in email, web-gateway, and web applications**; analyze ability to respond with post-exploitation modules such as **Lateral movement, Endpoint, and Data Exfiltration**; assess and improve employee awareness of phishing, ransomware, and other attacks _(Mod 19 p37)_
- PhishThreat — Reduces larger attack surfaces; Comprehensive reports; Quality security awareness training; Monitoring data points; Available in 9 languages _(Mod 19 p39)_
- Picus — Security control validation; Mitigation Library; Attack path validation; Continuous assessment; Compliance enablement; Detection Rule validation _(Mod 19 p40)_
- SafeBreach — Threat assessment; Security control validation; Cloud security assessment; Risk-based vulnerability management; Flexible to IT/OT Environments _(Mod 19 p40)_
- WhiteHaX — Deep analysis of security and data privacy; Wi-fi security scan; AES-256 secured; Cloud-based VPN; Cross-platform password vault _(Mod 19 p41)_






