---
type: note
module: "12"
lo: "04"
tags: [policy, concept, mod/12]
topic: "AWS ABAC with SAML session tags, IAM policy conditions, removing unnecessary credentials"
exam_weight: unknown
status: done
unresolved:
  - "p93 Figure 12.40 (policy access-assume-role): the first Condition key/value pair OCRs as '-project\": -project)\"' - both the resource tag key and the principal tag reference are partially lost. Read as `iam:ResourceTag/access-project` / `${aws:PrincipalTag/access-project}` by analogy with the two pairs that DO survive, and marked with ? in the table. Not asserted as certain."
  - "p93 Figure 12.40: 'Sid' OCRs as 'TutorialAssuneR01e' and 'Action' as 'Sts : AssumeR01e'; the 'Resource' value OCRs as ': 123456/89012:roIe/access-•'. Read as TutorialAssumeRole / sts:AssumeRole / `arn:aws:iam::123456789012:role/access-*`; the trailing wildcard is supported by the figure caption ('any role in your account with the access- name prefix'). Flagged with ? where uncertain."
  - "p94 Figure 12.42 (the ABAC policy access-same-project-team) is essentially unreadable - the OCR yields only 'StringL : - Effect • : \"Action : secret •POI i ey- \"Resource¯:'. The keys Effect / Action / Resource survive; NO statement values are transcribed. The only usable statement of this policy is its printed title: 'Access Secrets Manager Resources Only When the Principal and Resource Tags Match'."
  - "p94 Figure 12.43 'IAM roles': the role/tag table OCRs as 'peg \"Cess-ten • \"7654 • unl Propct A.svnce' - unusable. The four role names are taken instead from p95 Figure 12.45 and p96 Figure 12.46, where they are legible."
  - "p95 Figure 12.44 'ABAC tag combinations for role': column headers and the tag values are unreadable ('ABAC combinations / test- / cost-center / Denied / match / Of / Denied - tag value / is not / match the / to the / are the values / required tags / present'). Only the surrounding prose (the last tag set is allowed) is used."
  - "p96 Figure 12.46 'ABAC Secret Viewing Behavior for Each Role': the 4x4 role/secret matrix does not survive OCR - the secret-name rows repeat within each role block and the Expected-behavior cells cannot be aligned to them. The 16 behaviour values are reproduced in row-major order only; the per-cell mapping is NOT reconstructed."
  - "p98 Figure 12.48 'ABAC Secret Updating and Deleting Behavior for Each Role': same problem - the role column lists access-peg-quality-assurance twice (access-peg-engineering, access-peg-quality-assurance, access-uni-engineering, access-peg-quality-assurance) and 12 behaviour values do not divide evenly over the printed cells. No matrix is reconstructed."
  - "p95 Figure 12.45: the third Secret name prints as 'access -qas', truncated and inconsistent with the naming used elsewhere (test-access-<project>-<team>). Reproduced as printed; not completed."
  - "p95: the sentence 'In another browser window, test that the user Nikhil can create only Centaur engineering secrets, and that iew all engineering secrets' is broken in the OCR - the second clause's verb is lost. Only the first clause is quoted."
  - "p97 Figure 12.47: the 'Version' value OCRs as '2e12-1Ã¸-17' and is not readable; the 'Statement' is flattened without array brackets; 'Sid' OCRs as 'TutorialAssumeSpecificR01es••'. Marked with ? in the table."
  - "p97/p98: the role named in Step 7 for the fourth user prints as 'access-peg-quality-assurance' in the p98 list where p95/p96 give access-uni-quality-assurance for that position. The p98 list is reproduced as printed and the discrepancy is not repaired."
  - "p99: the Condition syntax schematic is printed across two lines with '{condition-key}' on the second line, so its exact inline layout cannot be recovered. Rendered here as the three placeholders it contains; no ordering beyond the print is claimed."
  - "p100 Figure 12.49 'Managing Unused Passwords' is a screenshot of the IAM console navigation; its column labels (Access management, User groups, Policies, Identity providers, Account, Access Analyzer, Archive, Credential report, Manage console access, Manage access keys) are legible but the user-table values are not. No user data is asserted."
---

[[MOC-Module-12]]

# AWS ABAC, Policy Conditions and Credential Pruning (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · use **SAML session tags for
> attribute-based access control** (pp92–98) · use **conditions in IAM policies to limit
> access** (pp99–100) · **remove unnecessary credentials** (pp100–102).
> Covers pp. 92–102.

## ABAC — the rule _(Mod 12 p92)_

- "The **attribute-based access control (ABAC)** authorization strategy **defines permissions
  based on attributes/tags**." _(Mod 12 p92)_
- "Organizations can attach these attributes to **IAM resources (including entities) as well
  as AWS resources**." _(Mod 12 p92)_
- "When an organization uses the entities to make requests to AWS, the entities become
  **principals** and those principals **include tags**." _(Mod 12 p92)_
- "Organizations can also **pass session tags** when they **assume a role/federate a user**."
  _(Mod 12 p92)_
- **The ABAC rule**: "Next, they can define policies that use **tag condition keys** to grant
  permissions to principals **based on their tags**." _(Mod 12 p92)_
- Payoff: "When organizations use tags to control access to AWS resources, they can **allow
  teams and resources to grow with fewer changes to AWS policies**." _(Mod 12 p92)_
- SAML route: "If organization uses a **SAML-based identity provider (IdP)** to manage corporate
  user identities, they can use **SAML attributes for fine-grained access control** in AWS. For
  example, these attributes can be **cost-center identifiers, user's email, classifications in
  each department, assignments of project**, etc." "When organizations **pass these SAML
  attributes as session tags**, they can then control access to AWS based on these session
  tags." _(Mod 12 p92)_

```
entity → makes a request → becomes a principal (carries tags)
   ↓ session tags on AssumeRole / federate
policy + tag condition keys → grant to principal by its tags
   ↓
access follows the tags, not the identity → policy edits stop scaling with the org
```

## ABAC walkthrough — rules vs the click path

**Step 1 — test users and the `access-assume-role` policy** _(Mod 12 p92–93)_

- "Create a customer managed policy named **`access-assume-role`**."
  Printed title: *"ABAC Policy: Assume any ABAC role only when the user and role tags match
  together."* _(Mod 12 p92)_
- "Attach the permissions policy `access-assume-role` and add the following tags."

**Figure 12.41 — IAM users** _(Mod 12 p93)_

| User name | `access-project` | `access-team` | `cost-center` |
|---|---|---|---|
| `access-Arnav-peg-eng` | `peg` | `eng` | `987654` |
| `access-Mary-peg-qas` | `peg` | `qas` | `987654` |
| `access-Saanvi-uni-eng` | `uni` | `eng` | `123456` |
| `access-Carlos-uni-qas` | `uni` | `qas` | `123456` |

**Figure 12.40 — the policy, as far as it is legible** _(Mod 12 p93)_

| Element | Value | Confidence |
|---|---|---|
| `Version` | `2012-10-17` | legible |
| `Sid` | `TutorialAssumeRole` | OCR `TutorialAssuneR01e` |
| `Effect` | `Allow` | legible |
| `Action` | `sts:AssumeRole` | OCR `Sts : AssumeR01e` |
| `Resource` | `arn:aws:iam::123456789012:role/access-*` | OCR partial; caption confirms the `access-` prefix |
| `Condition` operator | `StringEquals` | legible |
| Condition key → value | `iam:ResourceTag/access-project` → `${aws:PrincipalTag/access-project}` ? | **pair garbled**, see `unresolved:` |
| Condition key → value | `iam:ResourceTag/access-team` → `${aws:PrincipalTag/access-team}` | legible |
| Condition key → value | `iam:ResourceTag/cost-center` → `${aws:PrincipalTag/cost-center}` | legible |

Reading of the policy: a principal may assume **any** role whose name starts `access-` **only
when the role's `access-project`, `access-team` and `cost-center` resource tags are string-equal
to the same tags carried by the principal**.

**Step 2 — the ABAC policy** _(Mod 12 p93–94)_

- "Create the policy named **`access-same-project-team`**."
  Printed title: *"ABAC Policy: Access Secrets Manager Resources Only When the Principal and
  Resource Tags Match."* Its JSON (Figure 12.42) **did not OCR** — see `unresolved:`.

**Step 3 — the SAML role** _(Mod 12 p94)_

- "Create the below IAM roles and attach the `access-same-project-team` policy." The role table
  (Figure 12.43) **did not OCR**; the four role names are recoverable from pp95–96:
  `access-peg-engineering` · `access-peg-quality-assurance` · `access-uni-engineering` ·
  `access-uni-quality-assurance`.

**Step 4 — test creating secrets** _(Mod 12 pp94–95)_

- "**Remain signed in as the administrator user** to review users, roles, and policies in IAM.
  Use a **browser incognito window/separate browser for testing**." _(Mod 12 p94)_
- "Sign in as IAM user and open the **Secrets Manager** console at
  `https://console.aws.amazon.com/secretsmanager/`." _(Mod 12 p94)_
- "Try to switch to the `access-uni-engineering` role. This operation **fails** since the
  `access-project` and `cost-center` tag values **do not match** for the
  `access-Arnav-peg-eng` user and `access-uni-engineering` role." _(Mod 12 p95)_
- "Switch to the `access-peg-engineering` role. **Store a new secret**": _(Mod 12 p95)_
  1. Select **Other type of secrets** in the Select secret type section.
  2. In the two text boxes, enter `test-access-key` and `test-access-secret`.
  3. Enter `test-access-peg-eng` for the **Secret name** field.
  4. "Add **different tag combinations** from the below table and view the expected behavior."
     (Figure 12.44 did not OCR.)
  5. Select **Store** to create the secret. "If the storage **fails**, return to the previous
     Secrets Manager console pages. Then, use the **next tag set**… The **last tag set is
     allowed** and will successfully create the secret."
- "Sign out and repeat the first three steps for each of the below roles and tag values. In the
  fourth step in this procedure, test any set of **missing tags, optional tags, disallowed tags,
  and invalid tag values** that are chosen." _(Mod 12 p95)_

**Figure 12.45 — ABAC roles and tags** _(Mod 12 p95)_

| User name | Role name | Secret name | Secret tags |
|---|---|---|---|
| `access-Mary-peg-qas` | `access-peg-quality-assurance` | `test-access-peg-qas` | `access-project = peg` · `access-team = qas` · `cost-center = 987654` |
| `access-Saanvi-uni-eng` | `access-uni-engineering` | `test-access-uni-eng` | `access-project = uni` · `access-team = eng` · `cost-center = 123456` |
| `access-Carlos-uni-qas` | `access-uni-quality-assurance` | `access -qas` *(truncated)* | `access-project = uni` · `access-team = qas` · `cost-center = 123456` |

**Step 5 — test viewing secrets** _(Mod 12 pp95–96)_

- Sign in as one of `access-Arnav-peg-eng` · `access-Mary-peg-qas` · `access-Saanvi-uni-eng` ·
  `access-Carlos-uni-qas`, then switch to the **matching** role (`access-peg-engineering` ·
  `access-peg-quality-assurance` · `access-uni-engineering` · `access-uni-quality-assurance`).
- "In the navigation pane, expand the menu and then choose **Secrets**." _(Mod 12 p96)_
- "**Regardless of current role** see all four secrets in the table since it is assumed the
  policy named `access-same-project-team` allows the **`secretsmanager:ListSecrets`** action
  for **all** resources." _(Mod 12 p96)_
- "Select the name of one of the secrets. On the details page, **role's tags determine** where
  to view the page content." _(Mod 12 p96)_
- **The viewing rule**: "**Compare the name of role to the name of secret.** If they share the
  same **team name**, the `access-team` tags will match. **If they don't match, then access will
  be denied.**" _(Mod 12 p96)_
- Figure 12.46's expected-behaviour cells OCR in row-major order as
  `Allowed · Denied · Allowed · Denied` → `Denied · Allowed · Denied · Allowed` →
  `Denied · Allowed · Denied · Allowed` → `Allowed · Denied · Allowed · Denied` — the
  role↔secret alignment is **not** recovered, so the matrix is not reproduced. _(Mod 12 p96)_

**Step 6 — test scalability** _(Mod 12 pp96–97)_

- "Sign in as the **IAM administrator** user and open the IAM console at
  `https://console.aws.amazon.com/iam/`." _(Mod 12 p96)_
- "In the navigation pane, select **Roles** and add an IAM role named
  **`access-cen-engineering`**. Attach the `access-same-project-team` permissions policy to the
  role and add the following tags: `access-project = cen` · `access-team = eng` ·
  `cost-center = 101010`." _(Mod 12 p97)_
- "In the navigation pane, select **Users**. Add a new user named (say
  **`access-Nikhil-cen-eng`**), and attach the policy named (say **`access-assume-role`**).
  Follow the above Step 4 and Step 5. In another browser window, test that the user **Nikhil can
  create only Centaur engineering secrets**…" _(Mod 12 p97)_
- "In the main browser window in which you signed in as the administrator, select the user
  **`access-Saanvi-uni-eng`**. **Remove the `access-assume-role` permissions policy** on the
  Permissions tab. Add the below **inline policy** named `access-assume-specific-roles`."

**Figure 12.47 — ABAC Policy: Assume Only Specific Roles** _(Mod 12 p97)_

| Element | Value | Confidence |
|---|---|---|
| `Version` | `2012-10-17` ? | OCR `2e12-1Ã¸-17` — **not readable** |
| `Sid` | `TutorialAssumeSpecificRoles` | OCR `TutorialAssumeSpecificR01es••` |
| `Effect` | `Allow` | legible |
| `Action` | `sts:AssumeRole` | OCR `sts: AssumeR01e` |
| `Resource` | `arn:aws:iam::123456789012:role/access-peg-engineering` | legible |
| `Resource` | `arn:aws:iam::123456789012:role/access-cen-engineering` | legible |

No `Condition` block — this variant replaces tag matching with an **explicit role allow-list**.

- "Follow the above Step 4 and Step 5. In another browser window, confirm whether **Saanvi can
  assume both roles**. Check whether she can **create secrets depending on the role's tags**.
  Also, confirm whether she can **view details about any secrets owned by the engineering team**
  and the secrets she just created." _(Mod 12 p97)_

**Step 7 — test updating and deleting secrets** _(Mod 12 pp97–98)_

- Sign in as one of `access-Arnav-peg-eng` · `access-Mary-peg-qas` · `access-Saanvi-uni-eng` ·
  `access-Carlos-uni-qas` · `access-Nikhil-cen-eng`; switch to the matching role.
- "Try to **update the secret description** and try to **delete** the below secrets for each
  role." Figure 12.48's matrix did not survive OCR — see `unresolved:`. _(Mod 12 p98)_

## Conditions in IAM policies to limit access _(Mod 12 p99–100)_

- "The **conditions under which a policy statement is in force** can be specified. This will
  enable users to allow access to resources and actions, **but only if the access request
  satisfies certain criteria**." _(Mod 12 p99)_
- Use case 1 printed: "To **mandate that all requests be sent using SSL**, for instance, users
  can establish a policy condition." _(Mod 12 p99)_
- Use case 2 printed: "If a particular AWS service, such as **AWS CloudFormation**, is used to
  access the service action, users can also use conditions to **enable access to that
  action**." _(Mod 12 p99)_
- Mechanism: "Users can provide conditions for **when a policy is in effect** using the
  **`Condition` element** (or **Condition block**)." _(Mod 12 p99)_
- "Users can create **expressions** in the `Condition` element using **condition operators**
  (**equal, less than**, etc.) to **compare condition keys and values in the policy** to keys
  and values in the **request context**." _(Mod 12 p99)_

Syntax as printed on p99 — three placeholders, wrapped across two lines in the figure:

```
Condition {condition-operator}: {condition-value}
{condition-key}
```

_(Mod 12 p99; layout per the figure, see `unresolved:`)_

## Remove unnecessary credentials _(Mod 12 pp100–102)_

- "Remove the IAM user credentials (**passwords and access keys**) that are not required." _(Mod 12 p100)_
- "Remove unused passwords and access keys using the **console, CLI, API**, or by
  **downloading the credentials report**." _(Mod 12 p100)_
- "Remove **passwords for users who use the application but not the console**." _(Mod 12 p100)_
- "Remove **access keys for users who only use the console**." _(Mod 12 p100)_
- "The AWS IAM Console **displays when the access keys were last used**." _(Mod 12 p100)_

### Find unused passwords — the `Console last sign-in` column _(Mod 12 p101)_

1. Select **Users** in the navigation pane of the IAM console.
2. Above the table on the far right, choose the **settings icon**.
3. Select **Console last sign-in** in **Manage Columns**.
4. Select **Close** to return to the list of users.

> "The **Console last sign-in** column displays the **number of days since the user last signed
> into AWS through the console**. The column displays **`Never`** for users with passwords that
> have never signed in and **`None`** for users with **no passwords**." _(Mod 12 p101)_

`Never` = password exists, never used → candidate for removal. `None` = no password at all.

### Find unused passwords — the credentials report _(Mod 12 p101)_

1. Select **Credential report** in the navigation pane.
2. Select **Download Report** to download a **comma-separated value (CSV)** file.

> "The **`password_last_used`** column shows the following:" _(Mod 12 p101)_
> - **`N/A`** — "Users that **do not have a password**."
> - **`no_information`** — "Users that have **not used their passwords since IAM began tracking
>   the password age** (date)."

### Remove the console password _(Mod 12 p101)_

1. Select **Users** in the navigation pane.
2. Select the **name** of the user whose password you want to delete.
3. Select the **Security credentials** tab, then under **Sign-in credentials** select
   **Manage password** next to **Console password**.
4. For Console access, select **Disable (delete)**, followed by **Apply**.

### Remove access keys — own IAM user _(Mod 12 pp101–102)_

1. Select your **username** in the navigation bar on the upper right → **My Security
   Credentials**.
2. In the **AWS IAM Credentials** tab, in the **Access keys for CLI, SDK, and API access**
   section, select the **X** button. Then select **Delete** to confirm.

### Remove access keys — another IAM user _(Mod 12 p102)_

1. Select the **name** of the user whose access keys you want to delete → **Security
   credentials** tab.
2. In the **Access keys** section, select the **X** button to delete the access key, then select
   **Delete** to confirm.

Upstream: [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]] · least-privilege removal of unused
access: [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]] · SAML background:
[[03-LO03-IAM-Authentication-Authorization]]







