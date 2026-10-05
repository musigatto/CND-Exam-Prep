---
type: note
module: "12"
lo: "06"
tags: [bestpractice, policy, mod/12]
topic: "GCP IAM security best practices and temporary access"
exam_weight: unknown
status: done
unresolved:
  - "p254: the Condition Editor CEL expression OCR's as 'request. time < timestamp TOO: 00:00. OOOZ\")'. The left operand, the comparison operator and the timestamp() call are readable, but the DATE portion of the timestamp literal did not OCR. The full expression is not reconstructed here - only the legible shape is shown."
  - "p250: the 'basic roles might be suitable to assign' list prints THREE bullet markers but FOUR conditions. All four are transcribed; the marker count does not match the item count."
  - "p250: the body sentence 'It also adherence to the security principle of least-privilege' is printed with the grammatical error; reproduced as printed, not corrected."
  - "p252: the step after 'Enter your principal's email address' is a screenshot OCR mash ('Grant access to \"My First Project\" to this ro*S to can tee Optional... ccr...'). It is unreadable and is not transcribed; only the numbered step text survives."
  - "pp250-252: the Service Account User role is named on p251 and in the p250 figure, but its id `roles/iam.serviceAccountUser` is printed only on p252. The name-only and name+id forms are both kept as printed."
  - "pp253-254: the courseware states the benefit of time-bounded access only qualitatively ('a user cannot access a resource after the stated expiration date and time'). NO duration option is printed - no hour, day or month figure - so none is asserted here."
---

[[MOC-Module-12]]

# GCP IAM Security Best Practices and Temporary Access (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)** _(Mod 12 p245)_
> Covers pp. 250–254: GCP IAM security best practices (pp250–252) · the Service Account User
> role (p252) · granting temporary access via conditional role binding (pp253–254).
> Source list: [[12-LO06b-GCP-Service-Accounts]] (best practice 4, "Restrict who acts as
> service accounts").

## The principle _(Mod 12 p250)_

- "IAM enables you to **restrict access to other resources while granting fine-grained
  access to specific Google Cloud services**."
- "It also **[a]dherence to the security principle of least-privilege**, which states that
  **no one should be granted more permissions than they require**."

## Least-privilege — the stated rules _(Mod 12 p250–252)_

- "**Thousands of permissions** are included in **basic roles** for all Google Cloud services."
- "**Do not assign basic roles in production environments** unless there is no other option.
  Instead, assign the **minimum predefined roles or custom roles** that are appropriate for
  your purposes."
- "**Role recommendations** might help in choosing which roles to award in place of a basic
  role if needed to do so."
- "To make sure that **changing the role won't affect the principal's access**, the
  **Policy Simulator** may be used."

**The only four cases where a basic role is acceptable** _(p250, as printed)_:

1. "When a **predefined role is not offered** by the Google Cloud service."
2. "If you want to give a project **broader permission**."
3. "When granting rights in **test or development environments**, this occurs frequently."
4. "When you are **part of a small team with few individuals** that want granular
   permissions."

**The rest of the least-privilege rules** _(p251, verbatim in substance)_:

- "**Consider every element of your application as a distinct trust boundary.** Create
  **separate service accounts for each of your services** if they each need a different set of
  permissions, and then only give those accounts access to the necessary permissions."
- "It is important to keep in mind that **the allowed policies for child resources are derived
  from the allowed policies for their parent resources**."
- "**Provide roles with the minimal scope possible.**"
- "**Specify which principals are permitted to serve as service accounts.**"
- "**All resources that a service account has access to are accessible to users who have been
  given the role of Service Account User.** As a result, **take caution** when providing a
  user with the Service Account User role."
- "**Specify who in your project has permission to create and manage service accounts.**"
- "Giving the predefined roles of **Project IAM Admin** and **Folder IAM Admin** access will
  let users **change permissions without giving them full read, write, and administrative
  access to all resources**."
- **Owner** — "A principal will be able to **access and edit almost all resources, including
  updating allowed policies** if they are given the **owner (`roles/owner`)** role. This level
  of privilege **carries some risk**. **Only grant the owner role when universal access is
  necessary.**"
- **Just-in-time** — "**Consider only allowing privileged access on a just-in-time basis** and
  use **conditional role bindings to make access expire automatically**."

_(Mod 12 p251)_

## Service accounts — the stated rules _(Mod 12 p251)_

- "To prevent potential security issues, **make sure service accounts have only limited
  permissions**."
- "**Do not remove service accounts that are being used by instances that are running.** If
  you have not switched over to using a different service account beforehand, this could
  **cause all or parts of your application to fail**."
- "**Use the service account's display name** to remember what it is used for and what
  permissions it requires."

## Service account keys — the stated rules _(Mod 12 pp251–252)_

- "**Service account keys should not be used if an alternative is available.** If service
  account keys are not managed properly, they **pose a security concern**. If at all feasible,
  **authenticate using an alternative method**."
- "**Utilize the IAM service account API to rotate** the service account keys." Rotation order,
  exactly as printed: "**first create a new key, then switch apps to utilize the new key,
  disable the old key, and then delete the old key** if you are certain it is no longer
  required."
- "**Implement processes for managing user-managed service account keys.**"
- "**Keep in mind that service account keys and encryption keys are distinct.** Data is
  normally encrypted using **encryption keys**, and **safe access to Google Cloud APIs is
  achieved via service account keys**."
- "The service account keys **should not be checked into the source code or left in the
  Downloads directory**."

## The Service Account User role _(Mod 12 p252)_

- "For all service accounts included in the project, the **Service Account User role
  (`roles/iam.serviceAccountUser`)** can be granted at the **project level or the service
  account level**."

| Grant level | Effect as printed |
|---|---|
| **Project** | "they gain access to **all service accounts in the project, including any potential future service accounts**" |
| **Single service account** | "has access to **only that service account**"; "**Granting a role on a single service account will enable a principal to pretend to be that account**" |

### Walkthrough — grant a principal access to a service account _(Mod 12 pp252–253)_

1. Navigate to the **Service Accounts** page in the Google Cloud dashboard.
2. **Select a project.**
3. To allow the principal to act as another user's service account, **click the account's
   email address**.
4. Click the **Permissions** tab.
5. Under **"Principals with access to this service account"**, click on **Grant Access**.
6. **Enter your principal's email address.**
7. **Choose a role that permits the principal to impersonate service accounts.**
8. **Click Save** to apply the role to the principal.

_(p252 for steps 1–7 and the step-7 lead-in, p253 for step 8)_

## Grant Temporary Access — the stated rule _(Mod 12 p253)_

- "To ensure that a user **cannot access a resource after the stated expiration date and
  time**, **conditional role binding** can be used to grant **time-bounded access** to a
  resource."
- Two interfaces for the expression _(Mod 12 p253)_:

| Interface | Printed as |
|---|---|
| **Condition Builder** | "an **interactive interface** where you may choose the **operator, condition type**, and other relevant expression-related information" |
| **Condition Editor** | "a **text-based interface for manually entering an expression utilizing CEL syntax**" |

> **No duration option is printed** anywhere in pp. 253–254 — no hour/day/month figure. The
> only time control named is the *Date range* button. See `unresolved:`.

### Walkthrough — grant expirable access to a project resource _(Mod 12 pp253–254)_

1. In the Google Cloud console, **go to the IAM page**.
2. **Locate the appropriate principal** from the list of principals, then **click the edit
   button**.
3. **Locate the relevant role to specify a condition** from the **Edit permissions** panel.
4. **Select `Add IAM condition`** under **IAM condition (optional)**.
5. **Specify the condition's title and optional description** in the **Edit condition** panel.
6. **Add a condition expression** using the Condition Editor or the Condition Builder.
7. **Click Save** to apply the condition.
8. **Click Save once more** from the **Edit permissions** panel, after the Edit condition panel
   has been closed, to update the **allow policy**.

**Condition Builder** _(p253, Fig 12.168)_:

1. From the **Condition type** drop-down, select **Expiring Access**.
2. Select **by = From** from the **Operator** drop-down.
3. From the **Time** drop-down, click the **Date range** button to select a date and time
   range.
4. **Click Save**; then **Save** again from Edit permissions.

**Condition Editor** _(pp253–254)_:

1. Select the **Condition Editor** tab, then type the following expression (replace the
   timestamp with your own) — legible shape only:
   ```
   request.time < timestamp("...<date did not OCR>...00:00.000Z")
   ```
2. "You have the option to **validate the CEL syntax** after inputting your expression by
   selecting **Run Linter** at the top-right of the text box."
3. **Click Save**; then **Save** again from **Edit permissions** to update the allow policy.

_(Mod 12 p254)_

Upstream: [[12-LO06b-GCP-Service-Accounts]] · downstream:
[[12-LO06e-GCP-Service-Account-Key-Rotation]]







