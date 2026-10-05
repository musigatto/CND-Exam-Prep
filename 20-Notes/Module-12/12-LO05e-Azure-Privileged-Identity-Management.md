---
type: note
module: "12"
lo: "05"
tags: [policy, bestpractice, mod/12]
topic: "Azure AD PIM, emergency access accounts, passwordless admin sign-in and PAW"
exam_weight: unknown
status: done
unresolved:
  - "p184 Figure 12.113 CONTRADICTION: the caption says 'Enable Microsoft Authentication by navigating to Settings -> Usage Data', but the screenshot's own text is about App Lock ('Settings to be enabled. To turn off App Lock, you will need to remove those accounts from the app') plus a USAGE DATA disclosure. The App Lock toggle is never named in the printed steps. The same figure block also appears on p177. No App Lock requirement is asserted; only the caption's path is quoted."
  - "p187 CONTRADICTION: the preamble says 'Configure device setting in Active Directory to allow the administrative security group to join devices to your domain', but the step that follows selects the 'Secure Workstation Users' group under 'Users may join devices to Azure AD'. Both printed; not reconciled."
  - "p186/p187 CONTRADICTION: four groups are announced — 'Secure Workstation users, Secure Workstation Admins, Emergency BreakGlass, and Secure Workstation Devices' — but only three are created (Secure Workstation Users, Emergency BreakGlass, Secure Workstations). No 'Secure Workstation Admins' group is ever created, and the Admins paragraph actually configures the group named 'Emergency BreakGlass'. Not repaired."
  - "p187 dynamic membership rule prints as '(device.devicePhisicallds -any contains [OrderlD]:PAW)'. The attribute OCR's as 'device.devicePhisicallds' (likely devicePhysicalIds but not certain) and the bracketed token as '[OrderlD]' (unresolvable). The rule is quoted as printed; the attribute name and the bracketed token are NOT asserted."
  - "p186: the device USER block and the device ADMINISTRATOR block both print 'Name — Secure Workstation Administrator' with usernames secure-ws-user@contoso.com and secure-ws-admin@contoso.com respectively. The identical Name for two different accounts is a print/OCR anomaly; the two blocks are kept separate and no name is invented for the user account."
  - "p185 Figure 12.114 'Account Security Controls': the column headers OCR as a jumble ('access to resources', 'profile Summary', 'Security Benefit', 'ttacker costs increase hen you remove lower st attacks', 'Implementation Efforts', 'Steps to implement PAW') and the 'Security Benefit' cells mix short phrases with sentence fragments. The three security tiers and their summary/step cells are transcribed, but which cell belongs to which column is NOT asserted beyond the clearly adjacent ones."
  - "p185 Figure 12.114 security-benefit cells are truncated at 'Insider Coercion/Extortion' and 'Insider Coercion/Extortion with sophisticated execution'; the rest of each cell is lost."
  - "pp178-183: the PIM walkthrough never states which Azure AD licence tier is required for PIM, and no eligibility-duration, notification-recipient or approval settings beyond those listed are given. Nothing is supplied for these."
  - "p183: the emergency-access-account walkthrough creates ONE account and never shows how the 'cloud-only *.onmicrosoft.com' property is set. The 'at least two' and the *.onmicrosoft.com rule come from the prose (pp177, 182), not from the click path."
---

[[MOC-Module-12]]

# Azure AD Privileged Identity Management (§12.05)

> **LO#05: Security in Microsoft Azure Cloud** — area 2 of 7: **Azure IAM best practices**
> _(Mod 12 p156)_
> Covers pp. 177–187: lower exposure of privileged accounts (p177) · turn on Azure AD PIM
> (pp178–182) · define at least two emergency access accounts (pp183) · Microsoft Authenticator
> passwordless phone sign-in (pp184–185) · privileged access workstation (pp185–187).

## Why privileged accounts _(Mod 12 p177)_

- "Accounts that manage and administer IT systems are called **privileged accounts**. To gain access
  to an organization's data and system, **cyber attackers target these accounts**."

**Best practices — rules, not clicks** _(p177, six bullets as printed)_:

| # | Rule | Detail printed |
|---|---|---|
| 1 | Turn on **Azure AD Privileged Identity Management (PIM)** to manage, control and monitor access to privileged accounts | "PIM mitigates the risks of **excessive, unnecessary, or misused access permissions** on resources" |
| 2 | **Define at least two emergency access accounts**, cloud-only, using the **`*.onmicrosoft.com`** domain | "not assigned to specific individuals and are highly privileged and used for emergency scenarios" |
| 3 | All **critical administrator accounts** should be **passwordless or require MFA** | — |
| 4 | Use the **Microsoft Authenticator app** to sign into your Azure AD account **without using a password** | "key-based authentication to enable a user credential that is **tied to a device**, in which the device uses **biometric or PIN**" |
| 5 | For administrator accounts, have a **separate administrator workstation where production tasks are not allowed** | — |
| 6 | Use **Privileged Access Workstations (PAW)** | slide: "provides a **hardened workstation** that has clear **application control** and **application guard**"; body: "provides a dedicated OS that is **protected from Internet attacks and threat vectors**" |

## Turn on Azure AD PIM — the walkthrough _(Mod 12 pp178–182)_

1. Go to the **Azure portal**, search for **Privileged Identity Management**, go to **Azure AD
   Roles**. _(p178, Fig 12.98 — left rail also lists *Quick start, What's new, Get started, My
   roles, My requests, Approve requests, Review access, Privileged access groups (Preview)*)_
2. **Navigate to Assign Eligibility** to assign a role and **click Add assignments**. Click
   **Next** when done. **Assign the role of Global administrator**. _(p178, Fig 12.100)_
3. "Choose the assignment and the **start and end date for eligibility**." _(p179, Fig 12.102:
   assignment type **Eligible** / **Active**, "Maximum eligible duration is permanent", dates shown
   `02/28/2022` → `02/28/2023` — screenshot values, not stated defaults)_
4. "Go to **Roles**, search for the **Global Administrator** role and **click on it**."
   _(p179, Fig 12.103)_
5. **Click on Role Settings**, then **click on Edit** to change the default settings.
   _(p180, Figs 12.104–12.105)_
6. "Select **Azure MFA** and change the **duration to 2 hours** for the **Global admin** role."
   _(p180, Fig 12.106)_
7. "Choose **Assignment** and enter the required details." _(p181, Fig 12.107)_
8. "If needed change the **notification template**. And click **Update**." _(p181, Fig 12.108)_
9. "From the Privileged Identity Management portal **activate the Global Administrator role**."
   _(p181, Fig 12.109)_
10. "Enter the **Reason** and click on **Activate**." _(p182, Fig 12.110)_

### Role settings — the controls the figures name

**Activation** tab _(p180, Fig 12.106)_ — "On activation, require": **None** · **Azure MFA** ·
**Require justification** · **Require ticket information** · **Require approval to activate**
(no approver selected in the figure). Plus **Activation maximum duration (hours)** — set to
**2 hours** for Global admin in step 6. _(pp180–181)_

**Assignment** tab _(p181, Fig 12.107)_:

| Control | Printed value in the walkthrough |
|---|---|
| Allow permanent eligible assignment | Expire eligible assignments after **1 Year** |
| Allow permanent active assignment | Expire active assignments after **6 Months** |
| Require Azure Multi-Factor Authentication on active assignment | *(enabled)* |
| Require justification on active assignment | *(enabled)* |

**Activation request** _(p182, Fig 12.110)_: **Custom activation start time** · **Duration
(hours)** · **Reason (max 500 characters)**.

**Activation status** _(p182, Fig 12.111)_ — three printed stages: **Stage 1** "Processing your
request and activating your role" · **Stage 2** "Validating that your activation is successful" ·
**Stage 3** "Activation completed successfully". "When the [activation] completes **refresh your
browser**; you do not have to sign out and sign in again."

## Emergency access accounts _(Mod 12 pp182–183)_

- "Emergency access accounts are **highly privileged** and are used **under emergency scenarios
  where normal administrative accounts cannot be used**." _(Mod 12 p182)_
- "Define **at least two** … and these accounts should be **cloud-only accounts** that use the
  **`*.onmicrosoft.com`** domain." _(Mod 12 p182)_

**When they are used** _(pp182–183)_:

1. "The administrators are registered through Azure AD MFA, and **all their devices are
   unavailable or the service is unavailable**."
2. "Users might be **unable to complete MFA to activate a role**."
3. "The employee with **Global Administrator access has left the company**. Azure AD **prevents the
   deletion of the last Global Administrator account**, but it does not prevent the deletion of the
   account. These situations make the organization **unable to recover the account**."
4. "**Natural disaster** emergency, during which a mobile phone or other networks might be
   unavailable."

**Create walkthrough** _(p183, Fig 12.112)_:
1. Sign in to the **Azure portal as an existing Global Administrator**.
2. Select **Azure Active Directory** and navigate to **Users**.
3. Select **New user** → **Create user**.
4. Give the account a **Username** and a **Name**.
5. **Create a long and complex password** for the account.
6. Assign the **Global Administrator** role, under **Roles**.
7. Select the appropriate **location**, under **Usage location**.
8. Select **Create**.

## Microsoft Authenticator — passwordless phone sign-in _(Mod 12 p184)_

- "All **critical administrator accounts** should be passwordless."
- "Microsoft Authenticator uses **key-based authentication** to enable a user credential that is
  **tied to a device**, in which the device uses **biometrics or PIN**." *(p184; p177 prints
  "biometric or PIN")*
- "Users with **multiple accounts in Azure AD** can add every account to Microsoft Authenticator and
  use passwordless phone sign-in **for all of them from the same iOS device**."

**Steps to enable passwordless phone sign-in** _(Mod 12 p184)_:
1. Sign in to the **Azure portal with an Authentication Policy Administrator account**.
2. "Search for and select **Azure Active Directory** and navigate to **Security > Authentication
   methods > Policies**."
3. "Under **Microsoft Authenticator**, choose: **Enable** — Yes or No; **Target** — All users or
   Select users."
4. "Each added group or user is **enabled by default** to use Microsoft Authenticator in **both
   passwordless and push notification** modes (**"Any" mode**). To change the mode, for each row for
   **Authentication mode** — choose **Any** or **Passwordless**. **Choosing Push prevents the use of
   the passwordless phone sign-in credential.**"
5. "To apply the new policy, click **Save**."

**First-time phone sign-in, user side** _(pp184–185)_: enter their name on the sign-in page →
**Next** → "Select **Approve a request** on my Authenticator app" → "The app prompts the user to
authenticate by **typing the required number instead of a password**."

## Privileged Access Workstation (PAW) _(Mod 12 p185)_

- "A privileged access workstation (PAW) is the **highest security configuration designed for
  extremely sensitive roles**. If this account is compromised, there will be a **significant
  impact** on the organization."
- "The configuration is set with **security controls and policies where local administrators are
  restricted from access**. It is designed to perform **necessary and only sensitive job tasks**."
- "This makes the PAW **difficult to compromise as it blocks the common vector of phishing
  attacks**."
- "A PAW is a **hardened workstation** that features **clear application control** and an
  **application guard**. To protect the host from malicious behaviour it also leverages a
  **credential guard, app guard, device guard, and exploit guard**." *(also printed on p185)*

**Three security tiers** _(p185, Fig 12.114)_

| Tier | Summary (printed) | Steps to implement (printed) |
|---|---|---|
| **Enterprise Account** — *Enterprise Security* | "Baseline security for assets + starting point for higher security" | Enforce strong MFA · enforce account/session risk |
| **Specialized Account** — *Specialized Security* | "Enhanced security profile for higher value assets" | Configure strong MFA & educate users · require account/session risk in conditional access policy · integrate alerts into security operations/SOC · share accounts as sensitive · prioritize security response for accounts · update security operations processes · educate security operations personnel (analysts, threat hunters, incident managers, etc.) |
| **Privileged Account** — *Privileged Security* | "Strongest security for highest impact assets and accounts" | Explicitly restrict account usage to specific devices · explicitly monitor for anomalous usage within the enterprise · determine authorized devices and patterns for role · design restrictions and monitoring for each role · update security operations processes and educate personnel |

Threats printed against the tiers: *Insider Coercion/Extortion* and *Targeted workstation
compromise*; the privileged tier adds *Insider Coercion/Extortion with sophisticated execution*,
and the benefit cell reads (partly garbled) "Attacker costs increase when you remove lower …
attacks". _(p185, see `unresolved:`)_

### Steps to implement PAW _(Mod 12 pp185–187)_

1. "From the Azure portal, navigate to **Azure Active Directory → Users → New user**."
2. **Create a device user** _(pp185–186, Figs 12.115)_: in **Microsoft Endpoint Manager** select
   **Users → All users → New user**; enter a **Name**; enter a **Username**
   (`secure-ws-user@contoso.com`); "Select **Show password** and **remember the automatically
   generated password** so that you can sign in to a test device"; **Directory role** — Limited
   administrator and Administrator role; **Usage Location** — desired location; **Create**.
3. **Create a device administrator user** _(Mod 12 p186)_: **Name** — `Secure Workstation Administrator`;
   **Username** — `secure-ws-admin@contoso.com`; **Directory role** — Limited administrator and
   Administrator role; **Usage Location** — desired location; **Create**.
4. "**Create four groups**: Secure Workstation users, Secure Workstation Admins,
   **Emergency BreakGlass**, and Secure Workstation Devices" — `Azure Active Directory → Groups →
   New group`. *(four announced, three created — see `unresolved:`)*
5. **Workstation users group** _(Mod 12 p187)_: Group type **Security** · Name `Secure Workstation Users`
   · Membership type **Assigned** · add `secure-ws-user@contoso.com` · **Create**. "For the
   workstation users group configure **group-based licensing** to automate the provisioning of
   licenses to users." _(p186)
6. **Privileged workstation Admins group** _(Mod 12 p187)_: Group type **Security** · Name
   **`Emergency BreakGlass`** · Membership type **Assigned** · **Create** · "**Add Emergency Access
   accounts to this group**."
7. **Workstation devices group** _(Mod 12 p187)_: Group type **Security** · Name `Secure Workstations` ·
   Membership type **Dynamic Device** · dynamic membership rule as printed →
   `'[device.devicePhisicallds -any contains "[OrderlD]:PAW"]'` (attribute unresolvable) · **Create**.
8. **Device join setting** _(Mod 12 p187)_: `Azure Active Directory → Devices → Device settings` → "Choose
   **Selected** under **Users may join devices to Azure AD**" and select the `Secure Workstation
   Users` group.

Upstream: `[[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]` · access control:
`[[03-LO01-Access-Control-Models]]`







