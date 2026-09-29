---
type: note
module: "10"
lo: "04"
tags: [protocol, process, tool, crypto, mod/10]
topic: "Securing Communication − Database Server to Web Server"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Secure Communication: Database ↔ Web Server (§10.4.2)

## Problem
- Web servers → DB servers; DB creds + data cross the network → encrypt the channel (SSL/TLS)

## MS SQL Server — Force Encryption (SQL Server Configuration Manager)
1. **SQL Server Configuration Manager** → SQL Server Network Configuration → **Protocols for MSSQLSERVER**
2. **Flags** tab → **Force Encryption = Yes**
3. **Apply** → restart SQL Server service
4. Cert must be **FQDN-provisioned** for SQL instance

## Oracle Advanced Security SSL
- Configure **certificate authority**, wallet, cipher suites
- Server- and client-side config; enables encrypted client→DB channel
- (Same class as SQL: transport-level crypto between app/web layer and Oracle)

## NAS / SAN caveat
- Encrypt DB-to-storage as well: DB servers write plaintext to SAN/NAS unless encryption configured (see LO06 storage notes)

## Cards
Q:: Which two DB platforms get transport encryption in this subsection?
A:: MS SQL Server (Force Encryption) and Oracle (Advanced Security SSL).
#flashcard
Q:: SQL Server: where is Force Encryption enabled?
A:: SQL Server Configuration Manager → Protocols for MSSQLSERVER → Flags → Force Encryption = Yes → Apply → restart SQL Server service.
#flashcard