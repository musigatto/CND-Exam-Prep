---

type: note
module: "05"
lo: "10"
tags: [concept, process, tool, command, protocol, crypto, mod/05, flashcard/05]
topic: "Network Services and Protocol Security (RDP, DNS, SMB)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# Network Services and Protocol Security — RDP / DNS / SMB (§5.10)

Configure Windows network services + protocols against attacks.

## Secure Remote Desktop Protocol (RDP)
- **RDP**: encrypted remote connection over **TCP port 3389**; tunneling encrypts data **between client and server only** — **not** terminal-server authentication → credential guess enables **MITM** sniffing
- Best practices: **limit allowed users · firewall scoping · strong passwords · RDP gateways · Network Level Authentication (NLA) · account lockout policy**

### Limit RDP Users
- Default: **all administrative-rights users** may log on remotely (unused accounts = risk)
- **Local Security Policy → Local Policies → User Rights Assignment** → "Allow logon through Remote Desktop Services" → **remove Administrators**, keep **Remote Desktop Users**; add users via System Control Panel

### Scoping the RDP Firewall Rule
- Restrict the RDP port to **specific source IPs**; rejection happens **at the firewall**, freeing server resources (attacker never reaches RDP)
- **Windows Defender Firewall → Advanced Security → Inbound Rules** → RDP rule → **Scope** tab → Remote IP address → **"These IP addresses"** → add IPs/range
- Optional: change default RDP port (3389) — but scoping only protects against unlisted IPs

### RDP Gateways
- **RDP over HTTPS (port 443)** + SSL certificates through an RD Gateway server between client and terminal server
- Plain 3389 = **password-protected only, not encrypted** → brute-forceable; gateway layout: internal hops use **3389**, external leg uses **443 (encrypted)**
- Client: Remote Desktop Connection → **Show Options → Advanced → Connect from anywhere → Settings** (RD Gateway server settings; bypass for local addresses; logon method)

### Network Level Authentication (NLA)
- Decides access **before the session is established**; sends credentials securely via the client's **security service provider**
- GPO per host:
  1. Group Policy Management → new GPO → Edit → **Computer Configuration → Policies → Windows Settings → Public Key Policies → Automatic Certificate Request Settings** → new auto-enrollment for **Computer Certificate Template**
  2. Enable **Certificate Services Client – Auto-Enrollment** (renew automatically)
  3. **Computer Configuration → Templates → Windows Components → Remote Desktop Services → Remote Desktop Session Host → Security → "Require user authentication for remote connections by using NLA"** → Enabled
  4. Client: **Remote Desktop Connection Client → "Configure Authentication for Client"** → Warn me if authentication fails
- Grant permission on the **Domain Computers** group; link GPO to domain/OU; hosts without RDP see NLA as the only option

### Protect Credentials over RDP (Restricted Admin / Remote Credential Guard)
- **Remote Credential Guard**: protects user credentials over an RDP connection — **no passwords in memory, no hashes** → defeats **pass-the-hash / brute-force**; redirects **Kerberos** requests to the client device (which supplies credentials); SSO active only when the host supports it
- **Restricted Admin**: limits access to resources on other servers/networks from the remote host because credentials are **not delegated**
- GPO: **Computer Configuration → Administrative Templates → System → Credentials Delegation → "Restrict delegation of credentials to remote servers"** (participating app: Remote Desktop Client) → `Require Remote Credential Guard` / `Require Restricted Admin` / `Restrict Credential Delegation`

## DNSSEC
- **DNS**: distributed hierarchical database mapping URLs ↔ IPs; vulnerable to **cache poisoning + DNS spoofing**
- **DNSSEC** adds **digital signatures** to DNS info; **DS (delegation signing) data** = digital signature info per domain
- **Guarantees**: **authenticity · integrity · non-existence** (of a name/type)
- **Does NOT guarantee**: **confidentiality · protection against DoS**
- Flow: resolver requests → server adds **key** to response → validator checks public/private key vs **TLD + root** data → keys match ⇒ data not tampered in transit
- DS-record-manageable TLDs: `.com .net .biz .us .org .eu .co.uk .me.uk .org.uk .co .com.co .net.co .nom.co`
- Setup demo (Google Domains): select domain → **DNS** → **DNSSEC** → Enable
- Non-aware vs aware lookups: non-aware accepts the **first response** (MITM injects bogus IP → user lands on fake site); aware lookup gets the registry **signature duplicate** and refuses to display unless the response carries a **matching digital signature**
- Key features: **data-origin authentication** (resolver cryptographically authenticates zone data) + **data-integrity protection** (data signed by zone owner's private key)

## Monitor DNS Logs for Security Threats
- Nearly every connection attempt starts as a **DNS query** → log = request visibility (external + internal lookups); malicious-site requests record the site name
- Malicious domains often look **unusual / random-character**; flagged for restriction
- Enable: **DNS Management Console → right-click → Properties → Debug Logging** → check **"Log packets for debugging"** (disabled by default) → Save/OK
- Config: packet direction / transport (UDP/TCP) / packet type (Queries/Transfers, Request, Response, Updates, Notifications) / packet contents; **filter by IP**; log file max size **500000000 bytes**

## Disable SMB 1.0
- **SMB** shares files/printers/serial ports; clients request, servers respond; predates AD-era Windows
- **Disable SMB 1.0**; use later versions (2.0/3.0 have enhanced security); disable 2.0/3.0 **only as a temporary troubleshooting measure**

| SMB security feature | Version | Protects |
|---|---|---|
| Pre-authentication integrity | **3.1.1+** | Security-downgrade attacks |
| Secure dialect negotiation | **3.0, 3.02** | Security-downgrade attacks |
| Encryption | **3.0+** | Wire inspection, MITM |
| Insecure guest auth blocking | 3.0+ on Win10+ | MITM |
| Better message signing | **2.02+** | Enhanced performance/signing |

### Disable SMB 1.0 — methods
| Method | Command / steps |
|---|---|
| PowerShell (Win8+) | `Disable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol`; status: `Get-WindowsOptionalFeature -Online -FeatureName SMB1Protocol` / `Get-SmbServerConfiguration` |
| PowerShell (Win7) | `Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" -Name SMB1 -Type DWORD -Value 0 -Force` + restart |
| Set-SmbServerConfiguration | `Set-SmbServerConfiguration -EnableSMB1Protocol $false` |
| Windows Features | Control Panel → Programs and Features → **Turn Windows features on or off** → uncheck **"SMB 1.0/CIFS File Sharing Support"** → restart |
| Registry | `HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters` → **SMB1** `REG_DWORD` **0=disabled**, 1=enabled (default 1; key may not exist) → restart |
| Group Policy (server) | Forced registry pref `SMB1 = 0` (**Action: Create**, HKLM) |
| Group Policy (client) | `Services\mrxsmb10` → **Start** `REG_DWORD = 4` (Disabled), then `Services\LanmanWorkstation` → **DependOnService** `REG_MULTI_SZ` = `Bowser, MRxSmb20, NSI` (drops MRxSMB10 dependency) → restart |

## Enable SMB Encryption
- End-to-end SMB data encryption; **AES-CCM** algorithm; no **IPsec / WAN accelerators** needed; per-share or server-wide
- PowerShell (check first: `Get-SmbServerConfiguration` → EncryptData=False):
  - Per share: `Set-SmbShare -Name <sharename> -EncryptData $true`
  - Whole server: `Set-SmbServerConfiguration -EncryptData $true`
  - New share: `New-SmbShare -Name <sharename> -Path <pathname> -EncryptData $true`
- Server Manager: **File and Storage Services → Shares → right-click share → Properties → Settings → check "Encrypt data access"** (grayed-out + ticked ⇐ admin forced encryption server-wide)

## Module Summary
Weak spots attackers exploit on Windows: **unpatched OS · improper configurations · weak passwords · missing anti-malware · unnecessary services/processes left enabled**. Baseline = Microsoft-recommended config set.

## Cards
RDP default port and encryption scope?
?
TCP 3389; tunneling encrypts data between client and server only — terminal-server authentication is unencrypted (guessable → MITM).

Scoping the RDP firewall rule?
?
Restrict the RDP rule's Scope to specific remote IP addresses; rejections happen at the firewall, freeing server resources.

RDP gateway encryption path?
?
Internal hops use 3389; from the gateway to the client the data is encrypted over HTTPS port 443 with SSL certs.

Why is plain 3389 insecure?
?
Password-protected only (not encrypted) → susceptible to brute-force.

What does NLA do?
?
Requires authentication before the RDP session is established, sending credentials securely via the client's security service provider.

Remote Credential Guard protection?
?
No passwords in memory / no hashes → defeats pass-the-hash and brute-force; redirects Kerberos requests to the client device. Restricted Admin = credentials not delegated.

DNSSEC guarantees vs non-guarantees?
?
Guarantees authenticity, integrity, non-existence of name/type; does NOT guarantee confidentiality or DoS protection.

Threat mitigated by DNSSEC?
?
DNS cache poisoning and DNS spoofing (validates the key attached to the DNS server response against TLD/root data).

How to spot a malicious domain in DNS logs?
?
Unusual random-character names; log via DNS Management Console → Debug Logging → "Log packets for debugging".

SMB version to disable and why?
?
SMB 1.0 — legacy, weak; keep SMB 2.0/3.0+ (2.02+ signing, 3.0+ encryption, 3.1.1+ pre-auth integrity). Registry: SMB1 = 0.

SMB encryption details?
?
AES-CCM; end-to-end; no IPsec/WAN accelerators; per-share (Set-SmbShare) or server-wide (Set-SmbServerConfiguration).
