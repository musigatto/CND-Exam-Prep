---

type: note
module: "10"
lo: "04"
tags: [protocol, process, tool, crypto, mod/10, flashcard/10]
topic: "Email Encryption & S/MIME (Outlook, Office 365, Gmail)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Securing Email (§10.4.3)

## S/MIME — how it works
- Sign + encrypt messages; certs (X.509) + private keys handled via Email Security settings
- Outlook: **File → Options → Trust Center → Trust Center Settings → Email Security**
  - **Encrypt contents and attachments for outgoing messages** checkbox
  - Change Security Settings: choose **signing/encryption certificate**, **hash algorithm** (e.g., SHA-256), encryption algorithm, S/MIME format, "send these certificates with signed messages"
- Recipient needs your public cert to encrypt TO you / verify signed mail (Exchange integration simplifies this)

## Outlook S/MIME certificate on first use
- **Get a digital certificate/Digital ID**: File → Options → Trust Center → Trust Center Settings
- Under **Certificates and Algorithms** click **Choose**: select **signing certificate** (hash algorithm) + **encryption certificate** (encryption algorithm)
- Check **Send these certificates with signed messages**
- **Office 365 subscriber / Insider**: Options → **Encrypt** → **Encrypt with S/MIME** (requires installed S/MIME cert)
- **Outlook 2019/2016**: Options → **Permissions** (e.g., Do Not Forward)
- Send a digitally-signed message: Message → Sign; encrypt all outgoing: File → Options → **Trust Center → Email Security → Encrypt contents and attachments for outgoing messages**

## Office 365 Message Encryption (Information Rights Management)
- Requires **Office 365 Enterprise E3 license**
- Outlook 365: Options → **Encrypt**; Outlook 2019/2016: Options → Permissions (restrictions like Do Not Forward)
- Uses **SSL/TLS** to protect email transfer + IRM rights policies

## Gmail S/MIME (Workspace)
- Admin-enable S/MIME for domain; per-message: Encrypt (S/MIME) → view details / sign

## Cards
Where is the Outlook "Encrypt contents and attachments for outgoing messages" toggle?
?
File → Options → Trust Center → Trust Center Settings → Email Security.

What three cert/algorithm settings does Outlook S/MIME let you change?
?
Signing certificate, encryption certificate, hash/encryption algorithms (+ format, send-cert-with-sign).

What must S/MIME recipients have to read encrypted incoming mail?
?
Your public certificate (available to them) and their own private key; Exchange publishes certs to GAL.
