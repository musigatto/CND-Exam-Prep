---
type: note
module: "12"
lo: "04"
tags: [policy, bestpractice, mod/12, flashcard/12]
topic: "AWS least privilege, managed vs inline policies, access levels"
exam_weight: unknown
status: done
unresolved:
  - "p65 Figure 12.17 'CloudTrail Access': the service role name OCR's as 'AccessAnalyzerMomWServiceRole_9ArytZw5C'. The middle segment and the trailing account-derived suffix are not resolvable from the slice; the ARN/name is NOT completed from outside knowledge. Only the printed fact - 'IAM uses the service role on your behalf to access the specified trail' - is asserted."
  - "p66: the sentence 'IAM Access Analyzer analyzes all access channels and offers a thorough examination of external access to your resources using verifiable security' has a garbled trailing phrase. Only the leading clause is used."
  - "p66 Figure 12.19 'Review and Create Policy': the generated-policy table body is unreadable ('Of 276 9Y?w 271 List. List. Write. List, Write Read, Write rmrc?'). Only the heading 'Generated policy' is transcribed; no per-service action list is asserted. The five access levels come from the p75 prose instead."
  - "p68 Figure 12.21: the finding text is truncated in the OCR ('An AWS account has read and'). Not completed."
  - "p69 Figure 12.22 'Display of Information About the Role': role names OCR as 'Create EC.2Fu??mess TestRo??e Tusted Accomt' and the Last activity column is ambiguous ('12 47 t%y-s 12 / 128 days days 23 'hys'). No role name or day-count is asserted."
  - "p69 Figure 12.23 'Display of Information on Access Advisor': contents OCR as 'Summary CLVAPI EC2 EC2 2: Advigy'. Not transcribed; the Access Advisor description used here is the p69 prose only."
  - "p70: the partial-access sentence is broken across the page turn - 'Partial-access AWS managed policies provide specific levels of access to the AWS services. example, For AmazonEC2ReadOnlyAccess. [p1802] AmazonMobileAnalyticsWriteOnlyAccess'. The two policy names are legible; the sentence connecting them is not, so the names are listed without a reconstructed sentence."
  - "p71: the body sentence 'Here, a single AWS managed policy is attached to the principal entities in different AWS accounts and different principal entities in a single AWS account' is self-contradictory and sits under 'The above diagram illustrates three AWS managed policies'. Only the three legible policy names are asserted."
  - "p72 Figure 12.25: the group name OCR's as 'LtdAhins' on p72 and 'LtdAdmins'/'LltAdmins' on p73. Reproduced as printed; not resolved to a group name. Role names 'EC2 - access' and 'books-app' are legible."
  - "p73: 'The above diagram shows that each policy is an inherent part of the principal entity. Here, two roles have the same policy (Policy EmpDB-app) even though they do not share any policies. Each role comprises its own copy of the policy.' The second sentence contradicts itself ('same policy' vs 'do not share any policies'); both halves are quoted, neither is repaired."
  - "p73 Figure 12.26 inline-policy labels are partly garbled ('Role EQ- App', 'EC2--access', 'Policy EnwDB-app', 'Policy RestrictedAdmins-admins'). Only the body-prose name 'Policy EmpDB-app' is used."
  - "p74: the justification sentence reads '...they are separate the IAM resources that can be attached to several identities' - the 'separate' clause is garbled. Quoted as printed."
  - "p64: the generator flow prints the sign-in step as 'Sign up for AWS Management Console' (not 'sign in'). Reproduced as printed, not corrected."
---

[[MOC-Module-12]]

# AWS Least Privilege and Policy Types (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · area 2 of 6: **AWS IAM features and best
> practice to implement IAM securely** _(Mod 12 p40)_
> Covers pp. 64–76: implement least privilege with IAM Access Analyzer (pp64–69) · AWS-managed
> policies (pp70–71) · customer-managed policies instead of inline policies (pp72–74) · use
> access levels to review IAM (pp75–76).

## Implement least privilege using IAM Access Analyzer _(Mod 12 pp64–69)_

- "IAM Access Analyzer is used to achieve the least privilege by **setting fine-grained
  permissions, verifying intended permissions, and refining permissions**." _(p64)_
- "IAM Access Analyzer offers **over 100 policy checks** and actionable recommendations." _(p64)_

### Step 1 — Set / grant fine-grained permissions (generate from CloudTrail) _(Mod 12 pp64–65)_

| # | Step |
|---|---|
| 1 | Open the IAM console at `https://console.aws.amazon.com/iam/` |
| 2 | Sign up for AWS Management Console |
| 3 | Select **Roles** |
| 4 | Choose the name of a **role to analyze** |
| 5 | Under **Generate policy based on CloudTrail events**, choose **Generate policy** |
| 6 | On the **Generate policy** page, specify the **time period** IAM Access Analyzer uses to analyse CloudTrail events. "**Choose the shortest time, up to 90 days, to reduce policy generation time.**" |
| 7 | In **CloudTrail access**, choose an **existing role** or **create a new role** — "IAM uses the service role on your behalf to access the specified trail" |

_(Mod 12 pp64–65)_

### Step 2 — Review, create and attach the generated policy _(Mod 12 p66)_

- "A **successful notification** will appear on the role page if policy generation is ready."
  In the **Permissions** tab, choose **View generated policy**. _(p66)_
- Status fields shown: **Policy last requested** · **Requested on** · **Time period of
  activity** · **Status** (example values: requested on `2021/4/6 21 (PDT)`; activity
  `2021/3/20 0:00 (PDT) – 2021/4/5 0:00 (PDT)`; status **Success**). _(p66)_
- On the *Review and create managed policy* page, enter a **Name** and **Description**, choose
  **Attach policy to application role**, then **Create and attach policy**. _(p66)_
- "Policies can be attached to an entity in your account, or you can remove any other policies
  attached to the entity." _(p66)_

### Step 3 — Verify intended permissions _(Mod 12 pp66–68)_

- "IAM Access Analyzer's **public and cross-account** can be used to confirm whether the access
  already in place corresponds to your intentions." _(p66)_
- "When you **enable** IAM Access Analyzer, it starts **watching for new or updated resource
  permissions** so that you can see which ones allow cross-account and public access." _(p66)_

**Preview access to an S3 bucket** _(Mod 12 p67)_:

1. Open the **Edit bucket policy** page.
2. Draft a policy in the S3 console.
3. Under **Preview external access**, select an existing **account analyzer**.
4. Click **Preview** — Access Analyzer generates findings for access to the bucket.
5. It considers conclusions for **both the proposed bucket policy and the current bucket
   rights**, including the bucket or account's **S3 Block Public Access** settings, **bucket
   ACLs**, and the bucket's associated **S3 access points**.

**Finding badges** next to each finding _(Mod 12 p64, p68)_:
`New` · `Resolved` · `Archived` · `Existing` · `Public` — "Understand how a policy would change
access using the badge".

**Validate policies** _(Mod 12 pp67–68)_:

1. Open the IAM console / `https://console.aws.amazon.com/iam/`.
2. Then one of: go to the **Policies** page and create a new policy (**new managed policy**);
   or choose a policy by name and select **Edit policy** (**existing managed policy**); or go to
   the **Users** or **Roles** page, select a user or role, and click **Edit policy** on the
   **Permissions** tab (**inline policy** checks).
3. Choose the **JSON** tab and select the policy editor.
4. **Update policy to resolve findings.**
5. Choose **Review policy**; enter the **Name** and **Description**.
6. Review the policy **Summary** to examine the permissions the policy grants.
7. Select **Create policy** to save.

### Step 4 — Refine by removing unused access _(Mod 12 pp68–69)_

- "As the application gets to final review, the team and applications **may not rely on all
  roles that were created**." Roles not used in the account "can then be **deleted**." _(p68)_
- "The security team removes these **unused roles** to enhance the **security posture** of AWS
  environments. By removing the unused roles, it becomes **easier to monitor and audit** the
  roles that are in use." _(p69)_
- "**IAM reports the last-used timestamp** to identify the unused roles." The **last-accessed
  data** tells you when AWS services were last used → opportunities to secure permissions. _(p69)_
- "Navigate to the **Access Advisor** tab, which displays the list of **timestamps and services**
  that specify when the selected IAM principal last accessed each of the services that it has
  permission to." _(p69)_

Steps _(Mod 12 p69)_: select **Roles** in the IAM navigation pane → look for **Last activity**,
which displays the **number of days that have passed since each role made an AWS service
request** → navigate to **Access Advisor** from the role detail page and verify what the role was
used for → **Delete role**.

## The three policy types _(Mod 12 pp70–74)_

| | **AWS-managed** _(pp70–71)_ | **Customer-managed** _(pp72–73)_ | **Inline** _(pp73–74)_ |
|---|---|---|---|
| **Who creates it** | AWS — "standalone policies that are **created and administered by AWS**" | The **administrator** | The administrator |
| **How many principals** | Attached to principal entities **in different AWS accounts and in a single account** (Figure 12.24) | Attached to **multiple principal entities in an AWS account** | **Exists only on one IAM identity** (user, group, or role) |
| **Storage** | Standalone | Standalone — "an entity in IAM with its own **Amazon Resource Name (ARN)** that includes the policy name" (p73) | **Embedded in** the principal entity; "an **inherent part** of the principal entities" |
| **When created** | Pre-existing | Pre-existing | "during its creation **or later on**" |
| **Policy↔principal relationship** | Reusable across principals (Fig 12.24) | Reusable across principals | "help in maintaining a **strict one-on-one relationship** between a policy and the principal entity that it is applied to" |
| **Updates** | "AWS manages AWS managed policies by **updating them automatically**" | Change creates a **new version**; versions allow **rolling back** | Tied to the entity's own copy |
| **Rule stated** | Use during "the **creation and designing of access policies**"; useful for **common use cases** | "**It is recommended to use customer managed policies instead of inline policies**" | "**can be converted to managed policies**" |

_(Mod 12 pp70–74)_

### AWS-managed policy classes _(Mod 12 p70)_

| Class | What it grants | Examples named in the courseware |
|---|---|---|
| **Full access** | "define permissions for **service administrators** by granting **full access to a service**" | `AmazonDynamoDBFullAccess` · `IAMFullAccess` |
| **Power user** | "**multiple levels of access** to AWS services **without allowing permission management**" | `AWSCodeCommitPowerUser` · `AWSKeyManagementServicePowerUser` |
| **Partial access** | "**specific levels of access** to the AWS services" | `AmazonEC2ReadOnlyAccess` · `AmazonMobileAnalyticsWriteOnlyAccess` |

_(Mod 12 p70)_

- Rationale printed: admins need time to understand policies before giving them to employees;
  "**AWS managed policies … helpful until designing and creating access policies**"; they let
  users "familiarize them with the tasks that they must perform with the granted permissions". _(p70)_
- Figure 12.24 names three policies: **`AdministratorAccess` · `PowerUserAccess` ·
  `AWSCloudTrailReadOnlyAccess`**. _(p71)_

### Features of managed policies _(Mod 12 p73)_

| # | Feature | Printed statement |
|---|---|---|
| 1 | **Reusability** | "A single managed policy can be attached to **multiple principal entities**" |
| 2 | **Central change management** | "A change in a managed policy is implemented to **all principal entities** attached to the policy" |
| 3 | **Versioning and rolling back** | "A change … **does not overwrite** the existing policy. Instead, IAM **creates a new version**… help in **reverting** a policy to an earlier version" |
| 4 | **Delegating permission management** | Users "can be allowed to **attach and detach policies** while maintaining **control over the permissions defined in those policies**" |
| 5 | **Automatic updates** (AWS-managed only) | "AWS manages AWS managed policies by **updating them automatically** when needed… applied to the principal entities attached" |

_(Mod 12 p73)_

- "A customer managed policy can be better utilized by **copying the existing AWS managed policy
  and customizing it**, if needed." _(p72)_
- Inline-policy anti-pattern printed: "Here, **two roles have the same policy** (Policy
  `EmpDB-app`) even though they do not share any policies. **Each role comprises its own copy of
  the policy.**" _(p74)_

### Convert inline → managed _(Mod 12 p74)_

1. In the IAM console navigation pane, select **User groups**, **Users**, or **Roles**.
2. Select the name of the Group/User/Role with the policy to remove.
3. Select the **Permissions** tab. (For user groups, select the inline policy name directly; for
   users and roles, select **Show n more** *(OCR)* if necessary and the arrow next to the inline
   policy.)
4. **Copy the JSON policy document** for the policy.
5. Select **Policies** in the navigation pane → **Create policy** → **JSON** tab → replace the
   existing text with your JSON policy text → **Review policy**.
6. Enter a **name** and click **Create policy**.
7. Select Groups/Users/Roles in the navigation pane, open the entity that has the policy to
   remove (user groups: **Permissions** tab; users and roles: **Add permissions**).

_(Mod 12 p74)_

## Use access levels to review IAM _(Mod 12 pp75–76)_

- "IAM policies must be **constantly reviewed and monitored** to maintain AWS account security
  and ensure that the **least privileges** are granted to individual accounts." _(p75)_
- Policy summary is on the **Policies** page for **managed policies** and on the **Users** page
  for policies **attached to users**. _(p75)_

> **AWS classifies service actions into five access levels:**
> **List · Read · Write · Permissions management · Tagging** _(Mod 12 p75)_

| Summary table | Contains |
|---|---|
| **Policy summary** | The list of **services** and summaries of the permissions defined by the selected policy |
| **Service summary** | The list of **actions** and summaries of the permissions defined by the policy for the selected service |
| **Action summary** | The list of **resources** and the associated **conditions** implemented for the selected action |

_(Mod 12 p75)_

Where to read them _(Mod 12 pp75–76)_:

| Source | Path |
|---|---|
| **Policies page** | Policies → select the policy name → **Permissions** tab → policy summary on the **Summary** page |
| **Attached to a user** | Users → select the user name → **Permissions** tab → list of policies attached **directly or from a group** → expand the policy row |
| **Attached to a role** | Roles → select the role name → **Permissions** tab → list of attached policies on the **Summary** page → expand the policy row |

_(Mod 12 pp75–76)_

Upstream: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]] ·
[[12-LO04b-AWS-IAM-Features]] · concept background: [[03-LO03-IAM-Authentication-Authorization]]

## Cards

The three phases IAM Access Analyzer drives toward least privilege
?
Set fine-grained permissions · verify intended permissions · refine permissions by removing unused access

Generating a policy from CloudTrail — what does Access Analyzer read
?
AWS CloudTrail events for the chosen role, over a specified time period — choose the shortest, up to 90 days, to reduce generation time · status is reported on the role page; then View generated policy in the Permissions tab

The five IAM access levels
?
List · Read · Write · Permissions management · Tagging

The five features of a managed policy
?
Reusability · central change management · versioning and rolling back · delegating permission management · automatic updates (AWS-managed)

Three AWS-managed policy classes with their named examples
?
Full access — AmazonDynamoDBFullAccess, IAMFullAccess · Power user — AWSCodeCommitPowerUser, AWSKeyManagementServicePowerUser · Partial access — AmazonEC2ReadOnlyAccess, AmazonMobileAnalyticsWriteOnlyAccess

The three policy summary tables
?
Policy summary — services and permission summaries for the policy · Service summary — actions and permission summaries for one service · Action summary — resources and the conditions for one action