---

type: note
module: "08"
lo: "05"
tags: [process, tool, bestpractice, mod/08]
topic: "IoT Security Measures — Gateways, Control, Remote Admin (M16–M19)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-08]]

# IoT Security Measures — Gateway, Control Server, Remote Admin (§8.5, M16–M19)

## M16 — Secure the IoT Gateways
- Patch + harden field gateways; edge firewall / IDPS on gateway
- Mutual auth to cloud, secure boot, least-privilege services (see M10)
- Encrypt gateway↔device and gateway↔cloud hops (E2EE)

## M17 — Secure the IoT Control Server (Master Control)
- **Control server / plant controller** = brain that sends commands to devices
- Protect: MFA, role-based admin, audited commands, SIEM alerts on anomalies, HSM for signing commands

## M18 — Secure Remote Administration
- Use **SSH** (config port 22) not Telnet; disable Telnet/weak services
- **"Unplug n' Pray"** — physically disconnect when physically compromised
- HW inventory of remote-admin ports (console, USB)

## M19 — Router Security for IoT
- WPA2/WPA3 for Wi-Fi; strong pre-shared keys; **disable WPS**, UPnP, SNMP if unused
- Admin: change defaults; **Zenmap** & **ShieldsUP (GRC)** to scan exposed ports; PAT/NAT; menu: secure settings
- Sample harden steps: update firmware, disable remote mgmt, standard DHCP





