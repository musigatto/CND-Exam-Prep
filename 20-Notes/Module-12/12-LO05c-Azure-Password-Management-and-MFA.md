---
type: note
module: "12"
lo: "05"
tags: [policy, bestpractice, mod/12, flashcard/12]
topic: "Azure AD password management (SSPR, password protection) and MFA enforcement"
exam_weight: unknown
status: done
unresolved:
  - "p165: the sign-in step reads 'Sign in to the Microsoft Entra Administrator Center as at least an Authentication Policy ...' — the role word is split around Figure 12.78 and only reads 'e AD C—ct'. 'Authentication Policy Administrator' is the confident reading of the surrounding fragments, but the full role title does not print cleanly; the step is quoted with the gap marked."
  - "p167: the opening sentence 'Microsoft Azure feature authentication methods can block the use of common local words as passwords' is garbled — the product name and feature name are merged/illegible. The second, clean sentence ('It allows organizations to block common local words in addition to the global banned password list') is the one used as the claim."
  - "p166 Figure 12.80 'Authentication methods' for password reset: only 'No. of methods to users' and 'Mobile app' read cleanly; the other method rows OCR as fragments ('Authx*on', 'T*thods & as•ts'). The number of authentication methods a user must register, and the full method list, are NOT asserted."
  - "p166 Figure 12.81 'Registration': the field label OCR's only as 'of days are to re-confirm th[ir] ... pos[ed]' — the 'No. of days' setting is described in the printed step text but its exact field name and any default value are not readable. No number of days is asserted."
  - "p167 Figure 12.82 'Notifications': only 'Notify on password resets?' reads cleanly; the radio options below it OCR as 'Notify ... when Othe tho pzsword?'. The selectable options are not asserted."
  - "p165/p166 mix two portal surfaces: the step text says 'Microsoft Entra Administrator Center' while p169-170 use 'the Azure portal'. Both are reproduced as printed; the courseware does not state they are the same portal."
  - "p164 prints 'extend banned password lists to your existing infrastructure' while p165 prints 'extend the banned password lists to the existing infrastructure'. Same rule, wording differs; neither is treated as the canonical form."
---

[[MOC-Module-12]]

# Azure Password Management and MFA (§12.05)

> **LO#05: Security in Microsoft Azure Cloud** — areas 3 and 4 of 7: **enable password
> management** and **enforce MFA** _(Mod 12 p156)_
> Covers pp. 164–170: enable password management (pp164–168) · enforce Azure MFA (pp169–170).

## Enable password management — the two rules _(Mod 12 pp164, 167)_

1. Use the **Azure AD self-service password reset (SSPR)** feature to set up an SSPR for users, and
   the **Azure AD Password Reset Registration Activity report** to monitor registered users.
   _(p164)_
2. Use **Azure AD password protection for the Windows Server Active Directory agents on-premise**
   to **extend banned password lists to your existing infrastructure**. _(pp164, 167)_

- "SSPR … allows the employees of an organization to **reset their passwords without contacting
  the helpdesk**." _(p164)_

**Advantages of SSPR** _(p164, as printed)_:

| Advantage | Printed detail |
|---|---|
| Reduced cost | "Support-assisted password reset accounts for **20%** of an organization's IT expenditure" |
| Improve user experiences | "There is no need for users to contact the helpdesk if they forget their passwords" |
| Lower helpdesk volume | "Password management reduces the helpdesk volume of an organization" |
| Enable mobility | "Users can reset their passwords from **any location**" |

## Azure AD password protection _(Mod 12 p167)_

- "It allows organizations to **block common local words in addition to the global banned password
  list**." _(p167)_
- Reach: "Azure AD password protection can be used for **Windows Server Active Directory agents
  on-premise** to extend the banned password lists to the existing infrastructure." _(p167)_

**Walkthrough** _(pp167–168)_:
1. Go to **Azure AD Active Directory settings** and click on **Security**. _(p167, Fig 12.83)_
2. Under the **Manage** section, click on **Authentication methods**. _(p168, Fig 12.84)_
3. "Navigate to **Password protection** and click **Yes** on **Enforce custom list**. Enter the
   list of common passwords in the **Custom banned password list** box and **Save**."
   _(p168, Fig 12.85)_

Password protection panel, fields as printed _(p168, Fig 12.85)_:

| Field | Printed control |
|---|---|
| Password protection → Custom banned passwords | **Enforce custom list**: Yes / No |
| Password protection → Custom banned password | *(text box for the list)* |
| Password protection for Windows Server Active Directory | **Enable password protection on Windows Server Active Directory**: Yes / No |
| Password protection for Windows Server Active Directory | **Mode**: Enforced |
| — | **Custom smart lockout** (heading present; its settings did not OCR) |

## SSPR settings — the walkthrough _(Mod 12 pp165–167)_

1. "Sign in to the **Microsoft Entra Administrator Center** as at least an Authentication Policy
   [Administrator]." _(p165, Fig 12.78)_
2. "Click on **Properties** under the **Manage** section to enable SSPR and select **Selected**
   and **Save**." → *Default password reset policy*. _(p166, Fig 12.79)_
3. "Click on **Authentication methods** and select the required **number of authentication
   method(s)** and the **available methods** for a user." _(p166, Fig 12.80)_
4. "Click on **Registration**, select the required users **to register when signing in** and the
   **number of days** before users are asked to **re-confirm the authentication information**
   during password reset, and **Save**." _(p166, Fig 12.81)_
5. "Click on **Notifications**, select the required option, and **Save**." _(p167, Fig 12.82)_

SSPR blade = five areas the courseware names: **Properties** (enable, *Selected*) · **Authentication
methods** (count + methods) · **Registration** (who registers at sign-in + re-confirm days) ·
**Notifications**. _(pp166–167)_

## Enforce Azure MFA — Security Defaults _(Mod 12 p169)_

- "Managing security for identity-related attacks can be difficult. Microsoft is using **security
  defaults** to protect against attacks such as **password spray, replay, and phishing**."
- "**Security defaults enforce MFA to block 99.9% of identity-related attacks**" — printed claim.
- "The users who are using security defaults are **required to register for and use Azure AD MFA
  using the Microsoft Authenticator app using notifications**."

**Walkthrough** _(pp169–170)_:
1. Sign in to the **Azure portal**.
2. Browse to **Azure Active Directory → Properties**.
3. Select **Manage security defaults**.
4. Set the **Enable security defaults** toggle to **Yes**.
5. Select **Save**. _(p170, Fig 12.86)_

Related: [[12-LO04f-AWS-Password-Policy-and-MFA]] ·
`[[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]` ·
`[[12-LO05e-Azure-Privileged-Identity-Management]]`

## Cards

The four advantages the courseware claims for Azure AD self-service password reset
?
Reduced cost — support-assisted reset accounts for 20% of an organization's IT expenditure · improved user experience (no helpdesk call) · lower helpdesk volume · mobility — reset from any location

What do Azure AD password protection agents add on-premise?
?
They extend the banned password lists to the existing Windows Server AD infrastructure, so organizations can block common local words in addition to the global banned password list

The SSPR areas the walkthrough configures
?
Properties — enable SSPR and select Selected, then Save · Authentication methods — number of methods and available methods · Registration — who registers at sign-in and the re-confirmation days · Notifications — option, then Save

What does Security Defaults enforce, and what is the printed effectiveness claim?
?
It enforces MFA to block 99.9% of identity-related attacks, and users must register for and use Azure AD MFA with the Microsoft Authenticator app using notifications; it blocks attacks such as password spray, replay and phishing

Steps to enable Security Defaults
?
Azure portal → Azure Active Directory → Properties → Manage security defaults → set Enable security defaults to Yes → Save
