---
type: note
module: "12"
lo: "05"
tags: [concept, policy, mod/12, flashcard/12]
topic: "Azure AD single sign-on and Conditional Access"
exam_weight: unknown
status: done
unresolved:
  - "p159 prints 'It enables network defender to track user account activities and their access permissions'. The subject of 'enables' is garbled (reads as 'network defender'); quoted as printed, not corrected. What is certain is only the second half: tracking of user account activities and access permissions."
  - "CONTRADICTION (p159 vs the module summary): p159 defines Azure IAM as managing/controlling user identities and tracking account activities and access permissions. The module summary (p316, outside this page range) frames Azure IAM as enabling single sign-on, turning on conditional access and enforcing MFA. Both readings are kept; on p159 SSO / Conditional Access / MFA appear as *best practices*, not as IAM's definition."
  - "p160 Seamless SSO sentence is garbled: 'Azure AD Seamless SSO automatically sign-in corporate desktops users connected to a corporate network.' Reproduced as printed; the intended subject (corporate desktop users connected to a corporate network) is inferred from the surrounding readable clauses, not asserted as a corrected sentence."
  - "p161 Azure AD Connect screenshot: only the left-rail tooltips read cleanly (Federation, Password Hash Sync, Pass-through authentication, STAGED ROLLOUT OF CLOUD AUTHENTICATION, PROVISION FROM ACTIVE DIRECTORY). The sync status values ('Not Installed', 'Last Sync: Sync has never run', '0 domains', '0 agents', 'Disabled') and the right-rail navigation ('Users', 'Organizational relationships', 'Roles and administrators', 'Enterprise applications', 'Devices', 'Application Proxy', 'Licenses', 'Groups', 'Troubleshoot', 'Refresh') are OCR fragments; no status value or nav item is asserted beyond the two tooltips quoted."
  - "p163: 'All Baseline Protection policies will be removed on February 2m. 2020.' The day token OCRs as '2m' and cannot be resolved (2nd? 2 st?). Only the month/year are asserted; the day is left unresolved."
  - "p162 Security blade: the left navigation OCR's as 'Getting started / Diagnose and solve problems / Protect / Identity Protection Center / Verifiable credentials (Preview) / Identity Secure Score / Authentication methods / Certificate authorities'. The middle nav label is partly garbled ('Centi…') and is not asserted."
---

[[MOC-Module-12]]

# Azure AD SSO and Conditional Access (§12.05)

> **LO#05: Security in Microsoft Azure Cloud** — area 2 of 7: **Azure IAM features and best
> practices to securely implement IAM** _(Mod 12 p156)_
> Covers pp. 159–163: Azure IAM overview (p159) · enable single sign-on (pp160–161) · turn on
> Conditional Access (pp162–163).

## Azure IAM — what p159 actually says _(Mod 12 p159)_

- "Azure Identity and Access Management (IAM) **enables users to manage and control the user
  identities**. It enables network defender to **track user account activities and their access
  permissions**." (second sentence garbled — see `unresolved:`)
- **Framing check:** p159 does *not* define IAM as "SSO + conditional access + MFA". Those three
  appear in p159 only as entries in the best-practices list. The identity management + activity
  tracking definition is the one stated on this page.

## Azure IAM best practices — the 12 items as printed _(Mod 12 p159)_

| # | Best practice | Note in this note set |
|---|---|---|
| 1 | Enable single-sign-on (SSO) | → p160 |
| 2 | Turn on conditional access | → p162 |
| 3 | Enable password management | `[[12-LO05c-Azure-Password-Management-and-MFA]]` |
| 4 | Enforce MFA | `[[12-LO05c-Azure-Password-Management-and-MFA]]` |
| 5 | Enforce cloud-based MFA | not expanded in pp159–163 |
| 6 | Enforce Azure AD identity protection | not expanded in pp159–163 |
| 7 | Implement role-based access control (RBAC) | `[[12-LO05d-Azure-RBAC]]` |
| 8 | Restrict exposure of privileged accounts | `[[12-LO05e-Azure-Privileged-Identity-Management]]` |
| 9 | Centralize identity management | not expanded in pp159–163 |
| 10 | Use Azure AD for storage authentication | not expanded in pp159–163 |
| 11 | Treat identity as the **primary security perimeter** | not expanded in pp159–163 |
| 12 | Plan for routine security improvements | not expanded in pp159–163 |

_(Mod 12 p159)_

## Enable single sign-on — the rules _(Mod 12 p160)_

- "Azure AD Connect SSO refers to **accessing multiple applications and resources by signing in
  once with a single user account**."
- **Azure AD Seamless SSO** — printed: "automatically sign-in corporate desktops users connected to
  a corporate network. It allows users to easily access cloud-based applications."
  _(p160, see `unresolved:`)_
- Implement SSO to:
  - provide **security and convenience** to users;
  - let users "utilize the same credentials to sign-in and access the resources located
    **on-premise or in the Azure cloud**";
  - let users access **SaaS applications based on the organization account in Azure AD**.
- Slide rule _(p160)_: "Azure AD does **not** issue a token to sign-in unless they have been
  granted access through Azure AD."

**Walkthrough** _(pp160–161)_:
1. Go to **Azure AD Active Directory settings**.
2. Click on **Azure AD connect**. _(p160)_
3. Under **USER SIGN-IN**, enable **Seamless single sign-on**. _(p161)_

Two Azure AD Connect tooltips read cleanly in the p161 figure _(p161)_:

| Pane | Printed tooltip |
|---|---|
| PROVISION FROM ACTIVE DIRECTORY | "This feature allows you to **manage provisioning from the cloud**." |
| STAGED ROLLOUT OF CLOUD AUTHENTICATION | "This feature allows you to **test cloud authentication and migrate gradually from federated authentication**." |

Other USER SIGN-IN options visible in the same figure, by name only: **Federation** ·
**Password Hash Sync** · **Pass-through authentication**. _(p161)_

## Turn on Conditional Access — the rules _(Mod 12 p162)_

- "Azure AD uses a tool called **Conditional Access** for enforcing organizational policies to
  manage and control the access to corporate resources."
- "The organizations use conditional access policies for **security and right access control**.
  These policies are implemented **after first-factor authentication**." ← exam hook
- Configuration inputs: "the **group**, **location**, and **application sensitivity** for **SaaS
  apps**, and **Azure AD connected apps**."
- Scope: policies "are prepared and implemented for **on-premise and Azure cloud applications**."

Azure AD security features listed on the p162 Security blade _(p162)_: Azure AD Conditional Access
· Azure AD Identity Protection · Azure Security Center · Identity Secure Score · Authentication
methods · Security guidance · Azure AD Password Guidance · Azure AD Data Security Whitepaper ·
How Password Hash (PHS) works.

**Walkthrough** _(pp162–163)_:
1. Go to **Azure AD Active Directory settings** and click on **Security**.
2. Under the **Protect** section, click on **Conditional Access**. _(p162, Fig 12.76)_
3. Click on **Policies** and set the policy. _(p163, Fig 12.77)_

p163 **Policies** blade _(Fig 12.77)_ — printed notice: "Baseline Protection policies are legacy
experience which is being deprecated. All Baseline Protection policies will be removed on
**February 2… 2020**. If you're looking to enable Baseline policies we recommend enabling
**Security defaults** or **configuring Conditional Access policies**."
Policy entries visible: *Policy* (Baseline) · *Policy* (Preview): Require MFA · *Policy* (Preview):
End user protection · *Policy*: Block · *Policy* (Preview): Require MFA for Service.

Cross-module: IAM basics `[[03-LO03-IAM-Authentication-Authorization]]` · identity as perimeter
`[[03-LO02-Zero-Trust-and-Distributed-Access]]` · AWS SSO comparison
`[[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]]`

## Cards

The two rules that govern Azure AD Conditional Access policies
?
Implemented after first-factor authentication · configured on group, location and application sensitivity for SaaS apps and Azure AD-connected apps, and applied to on-premise and Azure cloud applications

What does Azure AD Conditional Access do, as printed?
?
It is the tool Azure AD uses for enforcing organizational policies to manage and control access to corporate resources, giving security and right access control

The Azure single sign-on click path
?
Azure AD Active Directory settings → Azure AD connect → under USER SIGN-IN enable Seamless single sign-on

The 12 Azure IAM best practices listed on p159
?
Enable SSO · turn on conditional access · enable password management · enforce MFA · enforce cloud-based MFA · enforce Azure AD identity protection · implement RBAC · restrict exposure of privileged accounts · centralize identity management · use Azure AD for storage authentication · treat identity as the primary security perimeter · plan for routine security improvements

Why is the Azure AD Connect "staged rollout of cloud authentication" feature used?
?
It allows you to test cloud authentication and migrate gradually from federated authentication
