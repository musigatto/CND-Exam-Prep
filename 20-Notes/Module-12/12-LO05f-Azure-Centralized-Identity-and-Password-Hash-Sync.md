---
type: note
module: "12"
lo: "05"
tags: [concept, bestpractice, mod/12]
topic: "Centralized identity management, AD FS and password hash synchronization"
exam_weight: unknown
status: done
unresolved:
  - "p190 the paragraph beginning 'Azure Active Directory, a separate online service, can provide' is largely OCR-destroyed: 'stmphfed identity and access management secunty report•ny sar•.gle sign-on to clCRJd and on-premises web apps.' Only the topic (Azure AD = separate online service providing identity/access management and SSO to cloud and on-premises web apps) is legible; the full sentence is NOT asserted."
  - "p190 'Things to note' #2 is garbled and reads 'The Web Application Proxy role service in the Remote Access server role functions as the federation service proxy cannot be installed on the same computer as the federation service.' Two clauses are fused and the subject of the second half is lost. The 'must be joined to a domain' note (#1) is clean; the WAP clause is quoted as printed only."
  - "p189 Figure 12.116 ('Navigate to Identity users') is unreadable apart from a jumble: 'Required us• Sign-ln', 'Cont•ct to Azure AD', 'Conr.ct Oeecto.ories', 'Azure AD Fittenna users Feat•.zes', 'Let margge source anchor'. The AD Portal identity-matching settings (Mail attribute / attribute SamAccountName / MsDS-ManagedPassword...) are NOT transcribed — only the clearly adjacent terms 'Mail attribute', 'SAMAccountt•ome and M&dNickNarne attributes' and 'Let merge source anchor' could be read, and even those are unreliable."
  - "pp188-189 CONTRADICTION/tension: the slide lists TWO ways to synchronize — 'Synchronizing on-premise and cloud directories using Active Directory Federation Services (AD FS)' and 'Synchronizing on-premise and cloud directories using Azure AD Connect' — and a figure titled 'Synchronizing on-premise and cloud directories using AD FS' whose OCR is fragmentary ('AD FS need by to •nd Connect your directories for on-pr«nises forests: ... DIRECTORY ... Active FOREST'). The body text however says only 'Use Azure AD Connect to synchronize...' while p189 says 'Use Active Directory Federation Services (AD FS) to integrate the on-premise identity with the cloud directory'. Sync (AD Connect) vs federation/integration (AD FS) is left as printed."
  - "p191 NO numbered implementation steps are printed for password hash synchronization — the page carries only the concept bullets plus Fig 12.121. The figure's readable labels are 'Azure AD Connect to Azure IAM Authentication Process', 'Source: httos://www.microso .com', 'USER SION-IN', '3 STAGED ROLLOUT OF CLOUD AUTHENTICATION ON-PREMISES APPLICATIONS'. No wizard path, cmdlet, licence or prerequisite list is supplied."
  - "p188 'Users must synchronize the on-premise and cloud identity directories for centralized identity management' is printed on the concept slide; no further prerequisite (agent, licensing, forest trust, account permissions) is given anywhere in pp188-191."
---

[[MOC-Module-12]]

# Azure Centralized Identity and Password Hash Sync (§12.05)

> Covers pp. 188–191: centralized identity management (pp188–189) · Active Directory
> Federation Services (pp189–190) · password hash synchronization with Azure AD Connect (p191).
> Upstream: `[[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]`,
> `[[12-LO05c-Azure-Password-Management-and-MFA]]`.

## Centralized Identity Management — rules, not clicks _(Mod 12 pp188–189)_

Azure identity management **integrates the on-premise and cloud directories**. The three stated
advantages, verbatim: _(pp188, 189)_

1. "Provide a **common identity** for accessing both cloud and on-premise resources."
2. "Enable administrators to **manage accounts from one location**."
3. "Enhance security by **preventing configuration errors**."

Prerequisite printed on the slide: "**Users must synchronize the on-premise and cloud identity
directories** for centralized identity management." _(Mod 12 p188)_

Implementation rule: "**Use Azure AD Connect to synchronize the on-premise directory with the
cloud directory**." _(Mod 12 p188)_

### Benefits of Azure AD Connect _(Mod 12 pp188–189)_

| Benefit | As printed |
|---|---|
| Common identity | Integrating on-premise directories with Azure AD "will provide a common accessing identity, which will allow users to access both the cloud and on-premise resources, thereby **enhancing the productivity** of an organization" |
| Hybrid identity | "a common **hybrid identity** is provided by the organization to leverage **Windows Server AD**, which is **connected to Azure AD**" — for on-premise or cloud-based services |
| Conditional access | "provided by the administrators depending on the **application resource, network location, device and user identity, and MFA**" |
| Reuse across apps | common identity "can be leveraged with the accounts in Azure AD for **Office 365, SaaS, and third-party applications**" |
| App development | "The applications should be **developed by leveraging a common identity model**." |

## Active Directory Federation Services (AD FS) _(Mod 12 pp189–190)_

**Why AD FS** — "Use Active Directory Federation Services (AD FS) to integrate the on-premise
identity with the cloud directory because" _(Mod 12 p189)_

- "AD FS overcome the **authentication challenges created by the AD**"
- "and **resolve the third-party authentication challenges**."

**What AD FS allows** _(Mod 12 p190)_

- "AD FS allow users to **work remotely** and provide **access to the AD-integrated applications**."
- "User can perform authentication using the **organizational AD credentials via a web interface**."
- "AD FS allow the users of an organization to access the **applications of different organizations outside the AD domain**."

**Federation model** _(Mod 12 p190)_

- AD FS "provides **Web single sign-on (SSO) capabilities** to authenticate a user to **multiple
  Web applications using a single user account**."
- "AD FS helps organizations **bypass the need for secondary accounts** by allowing you to
  **protect a user's digital identity and access rights to trusted partners**."
- "In this **federated environment, each organization continues to manage its own identities**."

**Things to note** _(Mod 12 p190)_

| # | Printed |
|---|---|
| 1 | "This computer **must be joined to a domain** before you can successfully install the Federation Service." |
| 2 | "The **Web Application Proxy role service** in the **Remote Access** server role … *functions as the federation service proxy cannot be installed on the same computer as the federation service.*" _(fused/garbled — see `unresolved:`)_ |

## Password Hash Synchronization _(Mod 12 p191)_

Slide title: **"Azure IAM App Security Configuration: Implement Password Hash Synchronization
with Azure AD Connect Sync"** _(Mod 12 p191)_

- Purpose: "To protect against **leaked credentials** from previous attacks, **sync user password
  hashes from an on-premise Active Directory instance to a cloud-based Azure AD instance**."
- Direction: on-premise AD instance → cloud-based Azure AD instance. **Hashes only**, not passwords.
- Benefit: "minimizes the **number of passwords** and the users can **maintain only one password for
  multiple accounts** in Microsoft Azure. Thus, it not only improves the **productivity** of users
  but also reduces the **helpdesk cost**."
- Failure case: users can **optionally set up password hash synchronization as a backup** "in case
  when **on-premise servers become temporarily unavailable or fail**."

No numbered steps are printed for PHS on p191 — the page is concept text plus a figure whose
readable labels are listed in `unresolved:`.






