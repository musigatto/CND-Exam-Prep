---
type: note
module: "09"
lo: "04"
tags: [tool, command, threat, bestpractice, mod/09]
topic: "WAF Implementation — URLScan and WAF Solutions"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-09]]

# WAF Implementation — URLScan & Solutions (§9.4b)

## URLScan (IIS WAF tool)
- Analyzes + filters all **HTTP requests** received by IIS; protects against **SQL injection + XSS**; requests logged; risky request → **HTTP 404**
- Features: new deny rules, global AlwaysAllowedUrls (safe query strings), escape sequences, multiple URLScan instances, config-change notifications to IIS worker processes, enhanced **W3C logging**
- Reject conditions (filter rules):
  - HTTP request method/verb
  - File extension of requested resource
  - **Suspicious URL encoding**
  - Non-ASCII characters in URL
  - Specified character sequences in URL
  - Specified headers in request

## Additional WAF Solutions
| WAF | Vendor / Key trait |
|---|---|
| **F5 NGINX App Protect WAF** | lightweight high-performance L7 protection across distributed/hybrid architectures |
| **NAXSI** | open-source **positive-model** WAF for Nginx; high performance, low rule maintenance; signatures need no updates |
| **WebKnight** | ISAPI filter for IIS; blocks bad requests; SQL injection protection (AQTRONIX) |
| **Cloudflare WAF** | dashboard rule engine; block/challenge/log suspicious requests |
| **Shadow Daemon** | open-source; filters malicious params; detect/record/prevent web attacks |
| **Wallarm** | API/microservices/web app; OWASP API Top 10, API abuse, automated threats; real-time analysis |
| **NetScaler / Citrix Web App Firewall** | known + unknown/zero-day app-layer protection; cloud or ADC-integrated |
| **AppWall (Radware)** | web attacks incl. behind-CDN, API manipulation, **Slowloris**, dynamic floods, brute-force login |
| **Barracuda WAF** | OWASP Top 10, zero-day, data leakage, app-layer DoS |
| **Qualys WAF** | Qualys Cloud Platform; blocks attacks + patches web-app vulnerabilities; multiple instances |
| **FortiWeb (Fortinet)** | ML-enabled protection for known + unknown vulnerabilities |

## Cards
Q:: URLScan purpose?
A:: IIS WAF tool filtering HTTP requests; SQL injection + XSS protection; rejects risky requests with HTTP 404.
#flashcard
Q:: URLScan reject criteria list?
A:: Request verb · file extension · suspicious URL encoding · non-ASCII chars · specified char sequences · specified headers.
#flashcard
Q:: NAXSI model?
A:: Open-source positive-model WAF for Nginx; no signature updates needed, low rule maintenance.
#flashcard
Q:: WebKnight placement?
A:: ISAPI filter for Microsoft IIS; blocks bad requests.
#flashcard
Q:: AppWall special coverage?
A:: Behind-CDN attacks, API manipulation, Slowloris, dynamic floods, brute-force on login pages.
#flashcard
Q:: Wallarm scope?
A:: APIs, microservices, web apps; OWASP API Top 10, API abuse, automated threats, real-time.
#flashcard