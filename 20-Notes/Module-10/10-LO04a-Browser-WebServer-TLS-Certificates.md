---

type: note
module: "10"
lo: "04"
tags: [protocol, process, crypto, mod/10, flashcard/10]
topic: "Secure Communication − Browser to Web Server (SSL/TLS certificates)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Secure Communication on the Web (§10.4.1)

## How a browser ↔ web server secure a connection
**6-step handshake**: browser confirms server cert; each side completes the logic to derive shared session key; TLS handshake steps — client hello → server hello + cert → client verifies CA → exchange key material → session encryption

## Digital certificates
- Verify the server = who it claims → prevents man-in-the-middle
- Fields you inspect in **Details** tab (Chrome):
  | Field | Example (google.com) |
  |---|---|
  | Issued To | www.google.com |
  | Issued By | GTS CA 1C3 |
  | Validity | from → to |
  | Public Key / Key Use | 2048-bit RSA (ECHARGE) |
  | Fingerprints | SHA-256 ... |
- **Standard SSL** (domain validated, cheap) vs **Extended Validation / EV** (green-bar address bar, org verified)

## Viewing certificates per browser
| Browser | Steps |
|---|---|
| Chrome/Edge | Padlock/Lock → "Certificate is valid" → Details → Certificate Viewer |
| Firefox | Padlock → Connection secure → More information / View Certificate |
| Safari | Padlock → Show Certificate |

## Cert lifecycle
- Renewal prior to expiry; **revocation list** (CRL) checked by browser
- Avoid expired-cert warnings (looks suspicious to users)

## Mnemonic
- HTTPS = HTTP + TLS/SSL wrapper in browser examples (this is the exact use case)

## Cards
What does the browser verify during the SSL handshake before showing the green padlock?
?
Server certificate authenticity — Issued To/By, validity, CA signature — preventing MITM.

In Chrome Details tab, which fingerprint types appear on a cert?
?
SHA-256 (and MD5/SHA-1 for legacy) fingerprints; public key size (e.g., 2048-bit RSA).

EV vs standard SSL difference in what the user sees?
?
EV → green-bar address bar + organization verified; standard → HTTPS padlock only.
