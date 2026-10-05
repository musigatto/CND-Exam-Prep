---
type: note
module: "12"
lo: "04"
tags: [concept, bestpractice, mod/12]
topic: "AWS EC2 instance roles, credential rotation, delegation and service-linked roles"
exam_weight: unknown
status: done
unresolved:
  - "p88: the permissions-boundary sentence is printed twice - once on the p87 slide ('A permissions boundary is a more advanced feature that allows you to use a managed policy to limit the maximum permissions that an identity-based policy can provide to an IAM role') and again as body prose on p88, where it carries the attribution 'Source: https://aws.amazon.com'. Reproduced once; the source line is recorded here as printed."
  - "p90 Figure 12.38 'Description for Role': the notification text OCRs as 'ARO you creato this you can moOfy through AWS srvic, Leam L to arri en Dots on behatt The rOW&nazonLexB0tPdicy 01 his rolo by the AWS sgvice. cannot De moated.' The role name is only partly legible and the sentence is unreadable. Only the reliably readable fragment - the role's policy is managed by the AWS service and cannot be deleted - is used; the role name is NOT reconstructed."
  - "p90 Figure 12.39 'Role Created with Cube-Shaped Icon': the role list OCRs as 'Create role Rob 1 Cr-Oon TEN 2017-04-13 1787 POT 2017-04-13 liss POT croe-eant to Courant 2*Suxuxu Ah.- EC2 AWS to AWS on yar'. The two service-linked role names are not resolvable. Only the body statement 'service-linked roles are marked with a cube-shaped icon in the IAM console' is asserted."
  - "p89 Figure 12.37 'Choose Role Type for AWS Service' is a screenshot of the Select role type page; the service list OCRs as 'MS - ervie-4Ned role Lex - Sots Mazon Lex create runa# Lex - Channels Lex td Chmnes o cross-accoun access n identity provider access'. Only the AWS Service-Linked role section is used, from the body text."
  - "p86 Figure 12.34 'Review the Last Used for Oldest Access Key': the screenshot's example values OCR as 'Created 08 por / Last Used 20150422 0828 / Last Used Region us-easV1'. The column NAMES are used; the concrete created/last-used timestamps and the region string are not asserted as example data."
  - "p84 Figure 12.33 'Instance Profile': the console field labels are legible (Default Availability Zone, Default SSH key, Stack color, IAM Role, Default IAM Instance Profile, New IAM Role, New IAM Instance Profile) but the Availability Zone value OCRs as 'us-east-la' and is not asserted."
  - "p91: the email-template bullet list is cut off at the page break - only 'Username and URL to the account sign-in page' is legible. The remaining template fields are not reconstructed."
  - "p87: the three bullet markers for the trusted/trusting account combinations are corrupted in the OCR (they render as mojibake). The three combinations themselves are legible ('Same account', 'Separate accounts under the control of an organization', 'Two accounts owned by different organizations') and are listed; only the bullet glyphs are missing."
---

[[MOC-Module-12]]

# AWS EC2 Roles, Credential Rotation and Delegation (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · areas 4–6 of 6: **use IAM roles for Amazon
> EC2 instances · rotate security credentials regularly · use IAM roles to delegate permissions
> and do not share access keys** _(Mod 12 p40)_
> Covers pp. 83–91: EC2 roles + instance profile (pp83–84) · credential rotation (pp85–86) ·
> delegation, permissions boundary, service-linked roles, personal access keys (pp87–91).

## Roles for Amazon EC2 instances — the rules _(Mod 12 p83)_

- "To access other AWS services, applications that run on an Amazon EC2 instance **require
  credentials**. The IAM roles securely provide credentials (username and password or access
  keys) for these applications." _(Mod 12 p83)_
- "An IAM role is **not a user or group** and it **does not have its own permanent set of
  credentials** like IAM users. However, it is an entity that **has its own set of
  permissions**." _(Mod 12 p83)_
- "IAM **dynamically provides temporary credentials** to EC2 instances and these credentials
  are **automatically rotated**." _(Mod 12 p83)_
- "A role can be specified as a **launch parameter** for an instance when launching it, and the
  specified role permission determines the tasks that an application is allowed to do." _(Mod 12 p83)_
- Slide payoff: "Using IAM roles **prevents credentials from being passed via a user
  application**." _(Mod 12 p83)_

```
IAM Role  ••Action A / Action B••–  AWS Service (Permissions: Action A, Action B)
```

### Worked example — the `Get-pics` service role _(Mod 12 p84)_

- Scenario printed: a developer runs an app on an EC2 instance that needs access to the S3
  bucket (**photos**).
- "A **Get-pics service role** is created and **attached to the EC2 instance by the
  administrator**." _(Mod 12 p84)_
- "This service role comprises a **permission policy** that allows **read-only access** to the
  S3 bucket and a **trust policy** that allows the instance to **assume the role** and retrieve
  temporary credentials." _(Mod 12 p84)_
- "The application uses the **temporary credentials of the role** to access the photo bucket
  when it runs on the instance." _(Mod 12 p84)_
- Payoff: "the developer does **not** need to share or manage his credentials and the
  administrator is **not** required to grant permission to the developer** to access the photo
  bucket." _(Mod 12 p84)_

**Figure 12.32 — the 4-step flow** _(Mod 12 p84)_ (objects: `AWS Account` · `EC2 Instance` ·
`Application` · `Role: Get-pics` · `Amazon S3 Bucket 'Photos'`):

| # | Step |
|---|---|
| 1 | Role created by admin to get access to the **Photos** bucket |
| 2 | Instance with the role **launched** |
| 3 | App **retrieves role credentials** from the instance by developer |
| 4 | App **gets photos using the role credentials** |

### Instance profiles _(Mod 12 p84)_

- "If applications running on a particular EC2 Instance's stack want to access other AWS
  resources, they should have appropriate permissions to do so. An **EC2 instance profile** can
  be used to grant those permissions." _(Mod 12 p84)_
- "While creating an **AWS OpsWorks Stacks** stack, an instance profile for **every instance**
  can be specified. The profile specifies an **IAM role that can be assumed by the apps running
  on the instance** to access AWS resources **as per the permissions the role's policy
  grants**." _(Mod 12 p84)_

**Figure 12.33 console fields** _(Mod 12 p84)_: `Default Availability Zone` · `Default SSH key` ·
`Stack color` · `IAM Role` · `Default IAM Instance Profile` · `Do not use a default SSH key` ·
`New IAM Role` · `New IAM Instance Profile`.

## Rotate security credentials regularly — the rules _(Mod 12 p85)_

Slide objectives _(Mod 12 p85)_: "Change passwords and access keys regularly" · "Ensure that
data cannot be accessed via **old keys/credentials**" · "Use the **Access Key Last Used**
attribute to identify and deactivate the keys/credentials that have been used for **more than
90 days**" · "Enable credential rotation for IAM users" · "Use **credential report** to audit
credential rotation".

- "Change passwords and IAM user access keys **regularly** and ensure that all IAM users in
  your account follow this practice." _(Mod 12 p85)_
- "Identify and **deactivate** the keys/credentials used **more than 90 days ago** using
  **Access Key Last Used**." _(Mod 12 p85)_ â† the operative threshold
- "If a password or access key is **compromised unknowingly**, limit how long the credentials
  can be used to access the resources." _(Mod 12 p85)_
- "Apply a **password policy** to your account that requires all IAM users associated with your
  account to rotate their passwords regularly and **decide how often they must do so**." _(Mod 12 p85)_
- "Use **Credential Report** to audit credential rotation." _(Mod 12 p85)_

### Rotate access keys without interrupting applications _(Mod 12 pp85–86)_

The rule printed: **create the second key first, cut over, then retire the first** — never
delete the old key while it is still in use. _(pp85–86)_

| # | Action |
|---|---|
| 1 | "Create a **second access key** while the first set of credentials is still active." |
| 2 | Select **Users** in the navigation pane of the IAM console. |
| 3 | Select the **Security credentials** tab after selecting the name of the intended user. |
| 4 | Select **Create access key**, followed by **Download .csv file** to save the access key ID and secret access key to a `.csv` file on your computer in a secure location. |
| 5 | After downloading the `.csv` file, select **Close**. — "The new access key is **active by default** and the user now has **two active access keys**." |
| 6 | **Update all applications and tools** to use the new access key. |
| 7 | "Check whether the first access key is still in use by reviewing the **Last used** column for the oldest access key. This can be done by **waiting for several days** and then checking the old access key for any use before proceeding." |
| 8 | "If the **Last used** column value shows that the old key has **never been used**, then do **not immediately delete** the first access key. Instead, select **Make inactive** to deactivate the first access key." |
| 9 | "Using the new credentials, **confirm that the applications are working normally**." |
| 10 | Select **Users** → select the name of the intended user → **Security credentials** tab → locate the access key to delete by selecting its **X** button and **Delete** to confirm. |

_(Mod 12 pp85–86)_

Access-keys table columns shown on the Security credentials page _(Mod 12 p86)_: **Access Keys:
Created** · **Last Used** · **Last Used Region**.

### Determine rotation of access keys _(Mod 12 p86)_

1. Select **Users** in the navigation pane of the IAM Console.
2. Add the **Access key age** column to the user table, if needed: the **settings icon above the
   table on the far right** → **Access key age** in **Manage columns** → **Close**.
3. "The **Access key age** column shows the **number of days since the oldest active access key
   was created**, which is useful for finding users with access keys that must be rotated. The
   column displays **None** for users with **no access key**."

### Download credential reports _(Mod 12 p86)_

- Select **Credential report** in the navigation pane of the IAM console.
- Select **Download Report**.

## Delegate permissions — the rules _(Mod 12 p87)_

- "**Instead of sharing the security credentials between accounts** to prevent the users of one
  AWS account to access the resources of another AWS account, IAM roles can be used." _(Mod 12 p87)_
- "An IAM role specifies the **permissions (delegation) allowed to IAM users to access another
  account** or **designates which AWS accounts have the IAM users that are allowed to assume the
  role**." _(Mod 12 p87)_
- "**Delegation sets up a trust between two accounts.**" The **Trusting Account** owns the
  resource; the **Trusted Account** comprises the users that need to access the resource. _(Mod 12 p87)_

| Trusted / trusting accounts can be | _(Mod 12 p87)_ |
|---|---|
| Same account | |
| Separate accounts **under the control of an organization** | |
| Two accounts **owned by different organizations** | |

**The role carries two attached policies** _(Mod 12 p87)_ — created in the **trusting** account:

| Policy | Printed role |
|---|---|
| **Permission policy** | "allows the user of the role to perform their tasks on the resources with the required permissions and consists of **half of the permissions**" |
| **Trust policy** | "specifies the **trusted account members that are allowed to assume the role** and comprises the **second half** of the permissions" |

- **Permissions swap, they do not add**: "The users who assume the role **temporarily give up
  their own permissions** and take the permissions of the role. **Once a user stops using the
  role, their original permissions are restored.**" _(Mod 12 p87)_
- Delegating *management*: "In some circumstances, you might want to give someone else control
  over a user account's permissions. For example, **developers can be allowed to create and
  manage roles for their workloads**." _(Mod 12 p87)_

### Permissions boundary _(Mod 12 pp87–88)_

- "When delegating permissions to others, use **permissions boundaries** to **limit the maximum
  number of permissions that can be delegated**." _(Mod 12 p87)_
- Definition printed (verbatim, on the slide and repeated on p88): "A permissions boundary is a
  more advanced feature that allows you to use a **managed policy** to limit the **maximum
  permissions that an identity-based policy can provide to an IAM role**." _(pp87–88)_

### Steps — create a role to delegate permissions to IAM users _(Mod 12 p88)_

1. Select **Roles**, followed by **Create role** in the navigation pane of the IAM console.
2. Select **Another AWS account** role type.
3. Type the **AWS Account ID** to which you want to grant access to your resources.
4. "To grant permission to assume this role to any IAM user in the specified account, the
   administrator attaches a policy to the **user or a group** that grants permission for the
   **`sts:AssumeRole`** action. That policy should specify the **ARN of the role** as the
   `Resource`. When granting permissions to users from an account that you do not control, the
   users will assume this role **programmatically**."
5. "Then, select the additional parameter **Require external ID** that ensures the secure use of
   roles between accounts that are not controlled by the same organization by **adding a
   condition to the trust policy** that allows the user to assume the role when the request only
   includes the correct **`sts:ExternalId`**. This can be **any word or number agreed upon by
   you and the administrator of the third-party account**."
6. "In the case of restricting the role to users who sign in with MFA, select **Require MFA**,
   which adds a **condition to the trust policy** of the role that checks for an MFA sign-in."
7. Select **Next: Permissions**. Select the policy (**AWS managed/Customer managed policies**)
   to use for the permissions policy, or select **Create policy** to create a new policy.
8. **Set a permissions boundary**: open the **Set permissions boundary** section and select
   **Use a permissions boundary to control the maximum role permissions**; select the policy to
   use for the permissions boundary.
9. Select **Next: Tags** — "Add metadata to the role by attaching tags as **key-value pairs**."
10. Select **Next: Review** → type a **Role name** → type a **Role description** → **Create
    role**.

### Steps — delegate permissions to AWS services: service-linked roles _(Mod 12 pp89–90)_

1. Select **Roles** in the navigation pane of the IAM console → **Create new role** (Figure 12.35
   / 12.36).
2. "In the **AWS service-linked role** section of the **Select role type** page, select the AWS
   service for which you want to create the role."
3. "Observe that the **role name prefix is automatically populated**. Type the **role name
   suffix** for the service-linked role. If AWS services such as **Amazon Lex** do not support
   custom suffixes, **leave the role name suffix box blank**."
4. "Provide a **description** for the new role. **IAM suggests a description** for roles, which
   can be edited."
5. Select **Create role**.
6. "The **service-linked roles are marked with a cube-shaped icon** in the IAM console."

Wizard steps printed in Figure 12.38 _(Mod 12 p90)_: `1: Select type` · `2: Establish trust` ·
`3: Attach policy` · `4: Set role name` · `5: Set role name and review`.

## Do not share access keys _(Mod 12 pp87, 90)_

Four prohibitions printed _(Mod 12 p87 slide)_:

1. "Do not share security credentials **between users in an AWS account**."
2. "Do not **embed access keys within unencrypted code**."
3. "Configure programs to **retrieve temporary security credentials** for applications that
   require AWS access."
4. "**Create an IAM user with personal access keys** to allow individual programmatic access to
   IAM users."

Body printed on p90 _(Mod 12 p90)_: "Access keys give **programmatic access** to AWS. It is
recommended to avoid sharing the security credentials between the users in an AWS account and
not embed the access keys within the unencrypted code. Configure the program to retrieve the
temporary security credentials for applications that need AWS access. Create an IAM user with
personal access keys to allow individual programmatic access to IAM users."

### Steps — create IAM users with personal access keys _(Mod 12 pp90–91)_

1. Select **Users**, followed by **Add user** in the navigation pane of the IAM console.
2. Type the **username**. "To add more users, select **Add another user** and type their
   usernames."
3. Select the type of access: **programmatic access**, **access to the AWS Management Console**,
   or **both**. "Select **Programmatic access** when the users need access to the **API, AWS
   CLI, or Tools for Windows PowerShell**, which will create an **access key for each new
   user**."
4. **Next: Permissions** — three ways to assign permissions _(Mod 12 p91)_:
   - **Add user to group** — "assign the users to one or more groups that already have
     permission policies."
   - **Copy permissions from existing user** — "copy **all group memberships, attached managed
     policies, embedded inline policies, and any existing permission boundaries** from an
     existing user to the new users."
   - **Attach existing policies to user directly** — "a list of the **AWS and customer managed
     policies** in your account."
5. **Next: Tags** → **Next: Review** "to see all decisions made by you" → **Create user**.
6. "Provide user credentials, and then select **Send email** next to each user. Then, a local
   mail client opens with a draft to allow customization before sending it."

Upstream: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]] · policy mechanics:
[[12-LO04e-AWS-Least-Privilege-and-Policy-Types]] · users and groups:
[[12-LO04d-AWS-IAM-Users-and-Groups]]







