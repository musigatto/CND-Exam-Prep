---

type: note
module: "09"
lo: "04"
tags: [concept, tool, threat, mod/09, flashcard/09]
topic: "Web Application Firewalls — Types, Deployment, Benefits, Limitations"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-09]]

# Web Application Firewall (WAF) (§9.4)

## Concept
- **WAF** = security layer protecting web servers from **malicious traffic**; conventional firewalls can't (attack at **layer 7**)
- Rule-based filter that **monitors + analyzes traffic before it reaches the web application**
- Appliance-based or cloud-based, deployed as **proxy ahead of the web app**
- **Scope of protection:** WAF covers web-app vulnerability + DoS attacks; IDS/IPS cover DoS + network-vulnerability attacks; standard firewall covers network attacks; **web-app attacks can't be fully prevented by existing firewall + IDS/IPS alone**

## Types of WAF
| Type | Placement | Pros | Cons |
|---|---|---|---|
| **Network/hardware-based** | edge of network perimeter; protects all web apps on network; blocks traffic per network security policies | protects all apps; wide threat range (incl. network-based); blocks by IP/port | needs dedicated hardware + significant investment; less granular than host-based |
| **Host/software-based** | on a single web server; secures the app on that server; inspects incoming traffic per rules | more user control; any web server; no special hardware | protects only that server's app; may need extra resources |
| **Cloud-hosted** | hosted/operated by third-party provider; blocks non-compliant traffic | no hardware/software purchase; easy scaling; variety of server types | third-party subscription; provider-dependent protection level |

## WAF Deployment Options
| Option | Notes |
|---|---|
| **Reverse proxy** | WAF is proxy to app server; encrypted connections terminated at **layer 7** → full control + content rewriting |
| **Layer-2 bridge** | in-line, acts as layer-2 switch; passive SSL decryption; blocks by dropping packets; high performance; architecturally like reverse proxy |
| **Out of band** | not in-line; least impact; monitoring port sends traffic copy; passive SSL decrypt + malware detection (avoids false-positive outages) |
| **Server resident** | embedded software on host executing web server; app or server plugin; extra server load; **check server utilization first**; less functional than network appliance |
| **Internet hosted/cloud** | works like reverse proxy; DNS points into cloud (CDN-like); **not under org control** → review cloud provider compliance |

## Benefits of WAF
- Secures existing/productive web apps
- Design-stage functionalities minimize workload
- **Cookie protection** with encryption + signature methodology
- Secures against **CSRF**; negates **parameter tampering by URL encryption**
- Detects **data-validation issues** (characters, character length, value range)
- Demonstrates compliance (PCI, HIPAA, GDPR)

## Limitations of WAF
- Not a replacement for proper app security (user authentication, input filtering)
- Not "set-and-forget" — needs ongoing admin
- Different from NGFW (WAF inspects per specific protocol)
- **Cannot read database commands** → not complete web-attack protection
- Session fixation / anti-automation protection only partial — **if it manages the session itself**
- No protection from **false positives**

## Cards
WAF working + layer?
?
Rule-based filter before the web app; protects at layer 7 where standard firewalls/IDS-IPS fall short.

Three WAF types?
?
Network/hardware-based · Host/software-based · Cloud-hosted.

Host vs network WAF granularity?
?
Host gives more control (single server, any server, no hardware); network covers all apps/network via IP/port but less granular + pricey hardware.

WAF deployment options (5)?
?
Reverse proxy · Layer-2 bridge · Out of band · Server resident · Internet hosted/cloud.

Out-of-band WAF advantage?
?
Least impact (not in-line); copies traffic via monitoring port; avoids false-positive outages.

WAF benefits list?
?
Cookie encryption/signature · CSRF protection + URL encryption (parameter tampering) · data-validation depth-testing · compliance (PCI, HIPAA, GDPR).

WAF limits?
?
Not replacement for auth/input filtering · can't read DB commands · partial session-fixation/anti-automation · no false-positive protection · needs ongoing management.
