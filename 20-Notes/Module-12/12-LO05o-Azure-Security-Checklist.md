---
type: note
module: "12"
lo: "05"
tags: [policy, bestpractice, exam, mod/12]
topic: "Azure security checklist"
exam_weight: unknown
status: done
unresolved:
  - "p243 SLIDE vs BODY: the slide blurb lists 18 items, the body text lists 19. The body contains one item the slide does not - 'Ensure that \"users can comply with apps obtaining company data on their account\" is set to none' - while the slide's ninth item is the garbled 'Ensure that \"users can disclose applications\" iS fixed to no'. Both are kept; the relationship between the two lines is not determinable from the slice."
  - "p243 item 11 the slide prints 'users can disclose applications' as 'iS fixed to no' where the body prints 'is set to no'. Body wording used."
  - "pp243-244 the checklist is ENTIRELY Azure AD identity/access and guest-user settings. No network, data-protection, logging/monitoring, perimeter, antimalware or encryption item is printed in this range. Do not assume a broader checklist exists in LO05."
  - "pp243-244 NO portal walkthrough, NO setting path, NO category and NO tenant property name is printed for any checklist item - the items are bare quoted setting names with a required value. Where each one is configured is not asserted."
  - "p243 items 13 ('members can request') and 18 ('users who can handle security groups') never state WHAT is requested or handled. The object of both verbs is not printed and is not inferred."
  - "p243 item 8 the setting name itself contains a question mark: 'notify all admins when other admins reset their password?'. Reproduced as printed."
---

[[MOC-Module-12]]

# Azure Security Checklist (§12.05)

> Covers pp. 243–244: the Azure security checklist, **all 19 body items transcribed verbatim and
> in printed order**. Related: `[[12-LO05c-Azure-Password-Management-and-MFA]]`,
> `[[12-LO05d-Azure-RBAC]]`, `[[12-LO05n-Azure-Monitoring-Logging-and-Compliance]]`.

## Scope note (read before the list)

The courseware prints **no sub-headings** for this checklist — it is one continuous run of
"Ensure that / Guarantee that …" sentences split across pp. 243–244. The courseware also prints
**no walkthrough, no setting path and no category** for any item. Nothing has been grouped or
re-worded below; the order is the printed order. Scope: **identity / access / guest-user
settings only**.

## The checklist — all 19 items, verbatim, in printed order _(Mod 12 pp243–244)_

| # | Checklist item (as printed) | p |
|---|---|---|
| 1 | Ensure that **MFA is enabled for all users**. | 243 |
| 2 | Ensure that **there are no guest users**. | 243 |
| 3 | Use **RBAC to manage the access to resources**. | 243 |
| 4 | Ensure that "**enable users to memorize multi-factor authentication on devices they trust**" is **disabled**. | 243 |
| 5 | Ensure that the "**number of processes required to reset**" is set to **two**. | 243 |
| 6 | Ensure that the "**number of days before users are asked to re-confirm their authentication report**" is **not set to zero**. | 243 |
| 7 | Ensure that "**caution users on password resets**" is set to **yes**. | 243 |
| 8 | Ensure that "**notify all admins when other admins reset their password?**" is set to **yes**. | 243 |
| 9 | Ensure that "**users can comply with apps obtaining company data on their account**" is set to **none**. | 243 |
| 10 | Guarantee that "**users can add gallery apps to their Entrance Panel**" is set to **no**. | 243 |
| 11 | Ensure that "**users can disclose applications**" is set to **no**. | 243 |
| 12 | Guarantee that "**guest user agreements are limited**" is set to **yes**. | 243 |
| 13 | Ensure that "**members can request**" is set to **no**. | 243 |
| 14 | Guarantee that "**guests can invite**" is set to **no**. | 243 |
| 15 | Ensure that the **entrance to the Azure AD administration portal is limited**. | 243 |
| 16 | Ensure that "**users can create security associations**" is set to **none**. | 243 |
| 17 | Ensure that "**self-service group administration enabled**" is set to **no**. | 243 |
| 18 | Ensure that "**users who can handle security groups**" is set to **none**. | 243 |
| 19 | Ensure that "**users can create Office 365 groups**" is set to **no**. | 244 |

### Required values, compressed _(pp243–244)_

| Value type | Items |
|---|---|
| **Enabled / on** | 1 (MFA for all users) |
| **Disabled / not set** | 4 (remember MFA on trusted devices = disabled) · 6 (re-confirm days ≠  zero) |
| **A number** | 5 (reset = **two**) |
| **Yes** | 7 (caution on password reset) · 8 (notify all admins on reset) · 12 (guest agreements limited) |
| **None** | 9 (apps obtaining company data on account) · 16 (security associations) · 18 (handle security groups) |
| **No** | 10 (gallery apps to Entrance Panel) · 11 (disclose applications) · 13 (members can request) · 14 (guests can invite) · 17 (self-service group administration) · 19 (create Office 365 groups) |
| **Limited (prose)** | 15 (Azure AD administration portal entrance) |
| **Rule, not a setting** | 2 (no guest users) · 3 (use RBAC) |

Mnemonic chain, in printed order: **MFA on → guests out → RBAC → no remembered MFA → reset = 2 →
re-confirm ≠  0 → caution on reset → notify admins → no data-grabbing apps → no gallery apps → no
disclosing apps → guest agreements limited → no member requests → no guest invites → lock the admin
portal → no security associations → no self-service group admin → nobody handles security groups →
no Office 365 groups.**

## Editorial clustering — NOT printed in the courseware

The courseware prints no headings; the grouping below is this note's reading of the item text
only, offered purely as a revision aid.

| Cluster | Items |
|---|---|
| Baseline identity hygiene | 1, 2, 3 |
| Authentication / password reset knobs | 4, 5, 6, 7, 8 |
| Consent & app install | 9, 10, 11 |
| Guest handling | 12, 13, 14 |
| Administrative surface | 15, 16, 17, 18, 19 |






