---

type: note
module: "05"
lo: "05"
tags: [concept, policy, command, mod/05, flashcard/05]
topic: "Windows User Account and Password Management"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-05]]

# Windows User Account & Password Management (§5.5)

## User Account Management
- Set up **different user accounts** when a system is accessed by multiple users; a user can hold multiple accounts (own files/themes/data per account)
- User management: identify/control logged-in users · manage login/logout times · monitor authentication + authorization **before granting permission** · analyze logging details (filter by **IP address or user**)

| Account type | Rights |
|---|---|
| **Administrator** | Full control + access to all files/folders in the system |
| **Standard** | Limited; only own files/folders; cannot install new apps or modify existing ones |
| **Guest** | Read + write only; cannot install new apps or change existing ones |

## Disable Guest Account
- Guest can access the system **without a password**; guest users can make **unauthenticated Internet access**; even though temporary → **disable** to prevent long-term misuse
- Ways:
  - Local Security Policy → **Local Policies → Security Options → `Accounts: Guest account status`** → Disabled
  - `gpedit.msc` → **Computer Configuration → Windows Settings → Security Settings → Local Policies → Security Options** → same policy
  - `net user guest` / check status; `net user guest /active:No` (CMD + PowerShell)
- Related hardening policies seen alongside: `Accounts: Administrator account status`, `Accounts: Limit local account use of blank passwords to console logon only` (Enabled), `Accounts: Rename administrator account`, `Accounts: Rename guest account`

## Disable Unnecessary Accounts
- Disable **inactive** accounts (unused long period) and accounts of **resigned employees** — attackers pivot through compromised unused/inactive accounts
- **Disabling ≠ deleting**: disabled accounts are **restorable**; deleted are **not**
- GUI: **Computer Management → System Tools → Local Users and Groups → Users** → double-click → check **Account is disabled**

## Disable Unnecessary Local Administrator Accounts
- Often configured on multiple computers with a **common password**; if attackers learn the **SID** of an admin account, they can compromise the system **even if the account name is changed**
- `net user Administrator` / check; `net user Administrator /active:No` (CMD + PowerShell)

## Enforce Password Policy
- Well-defined password policy minimizes compromise risk during authentication; controls must preserve **availability, confidentiality, integrity** of passwords (confidentiality = hardest)
- Best practices: password **history** · **minimum + maximum age** · **minimum length** · **complexity** · periodic reset · strong **passphrases** · password **audit** policy · email notification on password change · reversible-encryption storage policy
- **Complexity requirements** (enforced when passwords **changed or created**; helps defeat brute-force):
  - Not contain the user's account name or parts of full name exceeding **two consecutive** characters
  - At least **six characters**
  - Characters from **3 of 4** categories: English uppercase (A–Z) · English lowercase (a–z) · base-10 digits (0–9) · non-alphabetic (`!, $, #, %`)
- Domain policy via PowerShell: `Set-ADDefaultDomainPasswordPolicy -Identity cnd.com -ComplexityEnabled $True` / `Get-ADDefaultDomainPasswordPolicy`

## Password Age
- Too-high age → credential stays valid long → attacker gets time for unauthorized access → **set as low as possible**
- Default **maximum password age = 42 days** (`Windows Settings → Security Settings → Account Policies → Password Policy`); set via PowerShell `Set-ADDefaultDomainPasswordPolicy -MaxPasswordAge …`

## Password Length
- Too-low length → **easy to guess/brute-force** → set as high as possible
- Default minimum = 0 characters; `Set-ADDefaultDomainPasswordPolicy -Identity cnd.com -MinPasswordLength 11` (domain example)

## Password Protection Using Credential Guard
- Restricts credentials' interaction with system components; only **privileged software** can access them; strong encryption → even **extracted password hashes cannot be decrypted**
- Protects **LANMAN password hashes** + **Kerberos TGT**; blocks **pass-the-hash**
- GPO: Computer Configuration → Admin Templates → **System → Device Guard → Turn On Virtualization Based Security** → Enabled; Platform Security Level: **Secure Boot** or **Secure Boot + DMA Protection** (requires Win10 / Server 2016+)

## Cards
Three Windows account types?
?
Administrator (full access), Standard (own files only), Guest (read/write only).

Disable guest account (command)?
?
`net user guest /active:No`; policy: Local Policies → Security Options → 'Accounts: Guest account status'.

Disable vs delete an account?
?
Disabled = restorable; deleted = cannot be restored.

Password complexity requirements?
?
Not contain account name/2+ consecutive name chars; ≥6 chars; 3 of 4 categories (upper, lower, digits, non-alphabetic).

Default maximum password age?
?
42 days.

Credential Guard protects what?
?
LANMAN password hashes + Kerberos TGT; thwarts pass-the-hash; hashes can't be decrypted even if extracted.

Why worry about local administrator SID?
?
If attackers know the admin account's SID they can compromise the system even when the account name is changed.


## Cards (verified set 617277655)

> Matched word-for-word to the module PDF. See [[External-Flashcards-Verification]].

Microsoft Windows Defender Credential Guard (WDCG)
?
protects login credentials by restricting their interaction with the components of the system. When Credential Guard is enabled, only privileged software can access the credentials.  _(Mod 05 p81)_
