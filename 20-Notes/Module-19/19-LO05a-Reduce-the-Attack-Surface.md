---
type: note
module: "19"
lo: "05"
tags: [process, bestpractice, mod/19]
topic: "reduce the attack surface"
exam_weight: unknown
status: done
unresolved:
  - "p43 OCR prints SurfaceBrowserto without space; rendered as SurfaceBrowser per p47 clean form"
  - "p44 prints severs for servers; quoted list keeps the printed scope (data, network, systems) without the garbled token"
  - "pp46-47 attack-methodology and attack-category tables are heavily garbled and truncated; omitted per assignment scope"
---

[[MOC-Module-19]]

# Reduce the Attack Surface (§19.05)

> **LO#05: Learn to reduce the attack surface** _(Mod 19 pp42–48)_
> Covers pp42–48.

## General

- Reducing the attack surface **reduces the likelihood of compromising the organization's assets**; it minimizes the number of vulnerabilities in a system _(Mod 19 p44)_
- This activity is called **Attack Surface Reduction (ASR)**; it closes all but the needed doors that lead to system assets and restricts others with access rights _(Mod 19 p44)_
- Section scope: best practices to reduce the **system, application, network, human, and physical** attack surfaces _(Mod 19 p42)_
- This note records the **application, human, code-simplicity, browser-hardening, and port-audit** measures; system, SSL, segmentation, DNS, and physical rows are out of assignment scope _(Mod 19 pp42–48)_

Related: [[19-LO04a-Attack-Simulation-and-Tools]]

## Application ASR

- **Eliminate redundant and unnecessary functionalities, entry points, Application Program Interfaces (APIs), code, and unnecessary complexity** within an application's architecture _(Mod 19 p43)_
- Application ASR involves **eliminating code redundancies and unnecessary complexity** within an application's architecture _(Mod 19 p45)_
- The **simplest code with least assumptions can avoid bigger attack surfaces** _(Mod 19 p45)_
- Audit and eliminate **unnecessary functionality, entry points, and Application Program Interfaces (APIs)** _(Mod 19 p45)_

## Browser hardening list (as printed, web-browser ASR example)

- Disable Firewall Traversal; Disable Network Prediction; Disable Sharing with Cloud Peripherals; Disable Google Data Synchronization; Disable Pop-ups; Disable 3D Graphic APIs _(Mod 19 p45)_
- Disable JavaScript in all Available Locations; Disable Autocomplete on Forms; Update Browser and Plugins Regularly; Disable Session Only Cookies; Disable Background Processing _(Mod 19 p45)_
- Disable Search Suggestions; Disable Metrics Reporting; Disable Incognito Mode; Disable Cleartext Passwords; Disable Password Manager; Disable Import of Saved Passwords _(Mod 19 p45)_
- Disable Outdated Plugins; User Permission to Run Plugins; Disable Automatic Plugin Search; Disable Automatic Plugin Installation; Disable Automatic Plugin Execution _(Mod 19 p45)_
- Enable Revocation Checks for Certificates; Enable Safe Browsing; Block Desktop Notifications; Block Third-Party Cookies _(Mod 19 p45)_
- Set the Default Search Provider Name; Set Home Page; Set Highest HTTP Authentication Scheme; Blacklist/Whitelist Plugins and Extensions; Limit Plugins to a Specific URL; Use Encrypted Searching; Disallow Location Tracking; Save Browser History _(Mod 19 pp45–46)_

## Port audit

- Keeping all ports open increases the network attack surface; **close all unnecessary and unused ports** on the public IP addresses _(Mod 19 p43)_
- Run an **audit of network ports before the attacker scans** network ports by using the tool **Nmap** _(Mod 19 pp47–48)_
- Other port scanners include **Unicornscan, Angry IP Scanner, and Netcat** _(Mod 19 p48)_

## Human ASR

- Conduct **periodic awareness and training programs** to train employees on **security policies, social engineering, physical security, and other security best practices** _(Mod 19 p44)_
- Security awareness training plays a **crucial role in reducing the human attack surface**; employee training helps employees **comply with the organization's security policies** _(Mod 19 p48)_
- Social engineering awareness enhances **data confidentiality, data integrity, and data availability** by preventing various **phishing attacks and other social engineering attacks** _(Mod 19 p48)_
- Awareness programs should cover _(Mod 19 p48)_
  - What is information security?
  - Why is information security necessary?
  - Where can the organization's security policies be found?
  - How can the security of sensitive information assets be ensured?
  - What are the regulations that apply to the business of the organization?
  - What are the potential effects of a security incident on the organization?






