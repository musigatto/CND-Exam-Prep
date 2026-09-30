---
type: note
module: "12"
lo: "04"
tags: [bestpractice, process, mod/12, flashcard/12]
topic: "Creating IAM users and groups"
exam_weight: unknown
status: done
unresolved:
  - "p58 Figure 12.8 'Creating Individual Users in AWS IAM': the panel text is unreadable ('Identity and Access ( IAM) Q Au Access Users (Selected 1\") ANS'). Only the three numbered objectives printed above the figure are transcribed."
  - "p59: the Set permissions step offers three options; the first OCR's as 'No access', the second as 'Add user to group' (the default, selected in the walkthrough), and the third as 'Set permssons bourxlary' - a garble whose leading verb cannot be resolved. Reproduced as printed; the permissions-boundary reading of the tail is not asserted as the button label."
  - "p59: the step 'Click Next Permission.' is printed with a truncated button label; rendered here as Next/Next step without reconstructing the console label."
  - "p60: the tag instruction is printed as 'Specify Department as Tag Key and Key-Value as Training.' The sentence is malformed; it is quoted as printed rather than rewritten as key/value pairs."
  - "p60 Figure 12.12 'Review Page': the screenshot labels are largely unreadable ('AWS tym Permssions surnmary The Ake Ecess nd AWS Cons& The uw'). Not transcribed."
  - "p63 Figures 12.14 / 12.15: the list-area screenshot is heavily garbled ('Filter User groups by groverty w group name and press enter'). Only the two clean labels - 'User groups (1)' and 'A user group is a collection of IAM users. Use groups to specify permissions for a collection of users' - are transcribed."
  - "p62 heading prints 'Croups' for 'Groups' and the intro line as 'Create groups and define them specific rights and permissions'; rendered with the obvious spelling normalisation, wording otherwise kept."
  - "No policy names are attached to the example group in pp.58-63 - the walkthrough creates users and groups but never names an AWS-managed or customer-managed policy. Nothing is supplied from outside knowledge."
---

[[MOC-Module-12]]

# AWS IAM Users and Groups (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · area 2 of 6: **AWS IAM features and best
> practice to implement IAM securely** _(Mod 12 p40)_
> Covers pp. 58–63: create individual IAM users (pp58–61) · use groups to assign permissions
> (pp62–63). **These pages are console walkthroughs** — the security-relevant *rules* are
> separated from the *click path* below.

## Rules stated by the courseware — create individual IAM users _(Mod 12 p58)_

| # | Objective (as printed) |
|---|---|
| 01 | "Do not allow a user to use the **root user account**; instead, **create individual user accounts** for accessing AWS services" |
| 02 | "Provide a **unique set of security credentials** and appropriate permissions to IAM users" |
| 03 | "This will help in **changing or revoking** the permissions of IAM users as required" |

_(Mod 12 p58)_

Body _(Mod 12 p58)_:

- "It is recommended to **avoid using the AWS root user account** to access AWS. Instead,
  create individual user accounts for accessing AWS."
- "**Create an IAM user for yourself as well, give that user administrative permissions, and
  use that IAM user for all your work.**"
- "Give the IAM user a **unique set of security credentials** and **different permissions to
  each IAM user**."
- "**Change or revoke** an IAM user's permissions if needed."

## Walkthrough — create an IAM user (click path, p58–61) _(Mod 12 pp58–61)_

1. Select **Users** from the Identity and Access Management (IAM) section; click **Add user**. _(p58)_
2. **Username:** provide any name — the courseware example is **`Alice`**. _(p58)_
3. **Access type:** give Alice **AWS Management Console access** under *Select AWS access type*.
   Choose the **Custom password** radio button and provide the password in the **Password**
   field. **"Require password reset" is optional; however, enable this setting.** _(p59)_
4. **Set permissions:** **Add user to group** is **selected by default**. Check the **newly
   created group** — the courseware example is **`Training_Group`**. Other options in this step
   are `No access` and a third option whose label did not OCR (see `unresolved:`). _(p59)_
5. **Tags:** optional, "however, tagging allows searching for **tag keys** later on easily."
   Printed instruction: "Specify `Department` as Tag Key and Key-Value as `Training`." _(p60)_
6. **Review** the settings on the Review page, then click **Create user**. _(p60)_
7. A **success message** is displayed. _(p61)_

### Security-relevant points from the walkthrough

- **Console access is a separate access type from programmatic access** — the example grants
  `Alice` **AWS Management Console access** with a **custom password**. _(p59)_
- **A group is created during user creation** and the new user is placed in it automatically by
  default — "**Add user to group** option is selected by default". _(p59)_
- **Force a password reset** on first sign-in (the recommended setting). _(p59)_
- **One user, one credential set** — the same p58 rule drives the walkthrough. _(p58–59)_

## Rules stated by the courseware — use groups to assign permissions _(Mod 12 p62)_

- "Granting permissions for each individual IAM user **can be a hard task**. Instead, create
  groups and define them specific rights and permissions, and **add IAM user accounts to those
  groups based on their job functions**." _(p62)_
- "Through this, **modification to the IAM users of a specific group can be done at one
  place**." _(p62)_
- Reduces **access management complexity** for organizations with a large number of users. _(p62)_

| # | Advantage (as printed) |
|---|---|
| 1 | **Create groups with similar job functions** |
| 2 | **Assigning and reassigning rights to groups is easy and less time consuming** |
| 3 | **Reduces accidental assignment of greater privileges to users** |

_(Mod 12 p62)_

- "If the user is changed from one role to the other role, then the IAM user account in one
  group can be **changed to that specified group**." _(p62)_
- IAM feature restated: "Use IAM groups for easier permissions management and to follow IAM
  best practices… **Individual users still possess their credentials.**" _(p51, p62)_

## Walkthrough — create an IAM group and attach policies (click path, p62–63) _(Mod 12 pp62–63)_

1. Sign into the AWS Management Console by visiting `https://console.aws.amazon.com/iam/`. _(p62)_
2. In the navigation pane, select **User groups** followed by **Create group**. _(p62)_
3. Type the name of the group for **User group name**. _(p62)_
4. Select the check box for **each user** you want to add to the group, in the list of users. _(p62)_
5. Select the check box for **each policy** you want to apply to **all members of the group**,
   in the list of policies. _(p63)_
6. Click **Create group**. _(p63)_

Console definition shown _(Mod 12 p63)_: "A user group is a collection of IAM users. **Use groups
to specify permissions for a collection of users.**" The list is titled **User groups (1)**.

Upstream: [[12-LO04b-AWS-IAM-Features]] · practice:
[[12-LO04e-AWS-Least-Privilege-and-Policy-Types]] · least privilege concept: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]]

## Cards

The three stated objectives for creating individual IAM users
?
01 Do not allow a user to use the root user account — create individual user accounts instead · 02 give each IAM user a unique set of security credentials and appropriate permissions · 03 this lets you change or revoke their permissions as required

Why create an IAM user for yourself instead of using root
?
Create an IAM user, give it administrative permissions, and use it for all your work

During user creation, which option is selected by default
?
Add user to group — the new user is placed in a newly created group automatically (the example group is Training_Group)

Which setting is optional on a new IAM user but recommended
?
Require password reset — "The Require password reset is optional; however, enable this setting"

Three stated advantages of using groups
?
Create groups with similar job functions · assigning and reassigning rights to groups is easy and less time consuming · reduces accidental assignment of greater privileges to users

Why do individual users still keep credentials when IAM groups exist
?
The group policy governs access, but individual users still possess their own credentials
