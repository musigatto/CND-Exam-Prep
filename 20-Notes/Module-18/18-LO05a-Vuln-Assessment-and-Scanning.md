---
type: note
module: "18"
lo: "05"
tags: [process, tool, mod/18]
topic: "external vs internal assessment, scanning stages and tools"
exam_weight: unknown
status: done
unresolved:
  - "p60 'Four Stages of Vulnerability Assessment' prints only three bullets in OCR (plan/configure, resolve, maintain baseline) — one stage label missing, not reconstructed."
  - "p59 nmap scan-report block heavily garbled in OCR (hostnames, port table) — command kept, output values omitted."
  - "p61 tool-list header OCRs as 'Not Scans 0' and body lead-in has stray 'u' — tool names taken from clean p62 prose instead."
  - "p63 the page prints 'Weblnspect' (lowercase L for capital I) in the scanner list and 'HP Weblnspect' with Source https://www.microfocus.com; rendered here as WebInspect. Substitution recorded."
---
[[MOC-Module-18]]

# Vuln Assessment and Scanning (§18.05)

> **LO#05: Learn vulnerability scanning and assessment** _(Mod 18 p58)_
> Covers pp58–64.

## External assessment _(Mod 18 p59)_

- Evaluates **security profile from network perimeter / from the outside**; identifies vulnerabilities in **OSes, devices, applications on Internet-facing hosts**.
- Actions/steps: **find all live hosts** → **fingerprint OSes** → **detect open ports** → **map open ports and running services** → **find version of all running services** → **map service version to associated security vulnerabilities** → **check vulnerable vs patched**.
- Printed example command: `nmap -sv -T4 -f www.certifiedhacker.com` — output values garbled in OCR, not reproduced.

## Four stages + guidelines _(Mod 18 p60)_

- Printed as **Four Stages of Vulnerability Assessment**; OCR captures three bullets:
  - **Plan and configure** — set up tasks to run and generate reports.
  - **Resolve the vulnerabilities**.
  - **Maintain a security baseline for a network**.
- Guidelines for effective external assessment:
  - **Regularly assess all devices including new ones**; a vuln in one device does **not mean entire network corrupt**, but need to optimize security increases.
  - **Assess hardware manufacture, procurement, storage, installation**; find **non-functional / non-compatible** devices.
  - **Detect all open ports and interfaces, act accordingly**; assessment must cover **all devices, never just one device/system**.
  - **Determine status of running services**; **patch unpatched apps/services**; **map network infrastructure** to boost network/application performance.
- Typical tasks: **collect/document all network info including public-facing** (shows attacker entry paths) · **application probing and scanning** · **OS fingerprinting and vulnerability detection** · **evaluate findings/reports, take action** · **identify weak user authentication systems**.

## Internal assessment _(Mod 18 p61)_

- Finds weaknesses **within the network**, e.g. **password complexity, antivirus protection, and other potential weaknesses**; scan with tools such as **Nessus**.
- Assess **every critical device**; report based on detected vulnerabilities.
- Includes:
  - **Host and Service Discovery** — all accessible systems/services: **live host detection, service enumeration, application fingerprinting**.
  - **Vulnerability Identification and Verification** — scans on discovered hosts/services.
- Examples of internal vulnerabilities: **ineffective procedures (security configuration)** · **old passwords (older than one month)** · **old patch levels** · **unnecessary services (multiple open ports)**.

## Network scanner tools _(Mod 18 pp61–62)_

| Tool | What the page says | Source as printed |
|---|---|---|
| GFI LanGuard | Compatible with **Microsoft, Mac OS, Linux and many third-party applications**; **automatic or on-demand** scans; identifies **more than 60,000 vulnerabilities**; scans, identifies, categorizes, **recommends course of action and provides tools to solve**; **graphic threat level indicator** gives intuitive weighted assessment | Source: https://www.gfi.com |
| OpenVAS | **Full-featured scanner**: unauthenticated + authenticated testing, high- and low-level Internet and industrial protocols, **performance tuning for large-scale scans**, powerful internal programming language for any test | Source: http://www.openvas.org |
| Nsauditor | Suite of **more than 45 network tools** (auditing, scanning, monitoring); **Network Security Auditor** scans networks/hosts and provides security alerts | Source: http://www.nsauditor.com |

- p61 also names **Nessus** for internal scanning and lists GFI LanGuard / OpenVAS / Nsauditor as additional tools _(Mod 18 p61)_.

## Web assessment _(Mod 18 pp63–64)_

- **Crawl the website to discover potential vulnerabilities, then report**; aim to **make websites vulnerability free**; run scanners such as **OWASP ZAP, WebInspect, IBM Security AppScan, Qualys, Vega**.
- Crucial scanner-selection functions: **user-friendly interface** · **automated assessment processes** · **easily assign priorities and grouping** · **accurate reports**.

| Scanner | What the page says | Source as printed |
|---|---|---|
| OWASP ZAP | **Open source, easy to use, integrated tool for finding vulnerabilities in web applications** | Source: https://www.owasp.org |
| WebInspect | **Web application security assessment** for **complex web applications and services**; broadest **dynamic application security testing coverage**, detects new vuln types often missed by black-box testing | Source: https://www.microfocus.com |
| IBM Security AppScan Standard | **Security vulnerability testing tool for web applications and services**; most advanced testing methods; **full range of application data output options** | Source: https://www.ibm.com |
| Qualys Web Application Scanner | **Robust cloud solution for continuous web app discovery and detection of vulnerabilities and misconfigurations** | Source: https://www.qualys.com |
| Vega | **Open source**; finds/validates **SQL injection, XSS, inadvertently disclosed sensitive information, and other vulnerabilities** | Source: https://subgraph.com |






