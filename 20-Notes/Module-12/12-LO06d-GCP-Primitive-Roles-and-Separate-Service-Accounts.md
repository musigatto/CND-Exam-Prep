---
type: note
module: "12"
lo: "06"
tags: [bestpractice, policy, mod/12]
topic: "GCP primitive roles and separate service accounts"
exam_weight: unknown
status: done
unresolved:
  - "p255 CONTRADICTION/GAP: the body says 'Cloud IAM roles are of three types:' and then defines ONLY the Primitive role. The names of the other two role types are never printed in pp.255-261, so they are not supplied here. The two remaining types are visible only as a blurred figure banner that did not OCR ('...IAM ... Polky ... ')."
  - "p255: the three primitive roles are printed as 'Roles/Owner', 'Roles/Editor', 'Roles/Viewer' in the body and as 'roles/owner, roles/editor, and roles/viewer' in the figure. Both capitalisations are kept as printed; the body spelling is also confirmed by the p251 text 'the owner (roles/owner) role'."
  - "pp256-257: the console screenshots do not yield a single legible role name, role id or permission string. The only readable member value is a '@gmail.com' address. The walkthrough below is the numbered body text only; nothing about the IAM grid is asserted."
  - "p259 Figure 12.173: five sample service-account addresses of the form `<name>`@`<project-id>`.iam.gserviceaccount.com are visible in the screenshot. They are lab sample data with an OCR-garbled project id, are not reproducible, and are not asserted."
  - "p260 Figure 12.176: the 'Create key (optional)' sub-panel yields two button labels - 'Download' and 'Why you need a key' - plus a warning that the key cannot be recovered if lost. A third button label was previously drafted here as 'Skip now'; that string does NOT occur anywhere in the module OCR (verified against all 316 pages) and has been REMOVED as a fabrication. Only the two surviving labels and the recovery warning are transcribed; the rest of the panel is garbled."
  - "p258: 'It is possible to create up to 100 service accounts per project' is printed verbatim. The courseware gives no mechanism, reference or error behaviour for this limit."
  - "p258 vs p252: the role is written 'Service account user role' on p258 and 'Service Account User role' on p252, and p258 also spells the IAM concept 'cloud IAM permission' where p250 writes 'IAM service account API'. Kept as printed per page; not treated as different objects."
---

[[MOC-Module-12]]

# GCP Primitive Roles and Separate Service Accounts (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)** _(Mod 12 p245)_
> Covers pp. 255–261: grant least privileges to avoid primitive roles (pp255–257) · create a
> separate service account (pp258–261). Source list: [[12-LO06b-GCP-Service-Accounts]] (best
> practices 1 and 2).

## Primitive roles — what they are _(Mod 12 p255)_

"Cloud IAM roles are of three types:" — only the **Primitive** role is defined on the page (see
`unresolved:`).

> "**Primitive role: It consists of Owner, Editor, and Viewer roles.**"

| Role | Printed definition |
|---|---|
| **Owner** (`roles/owner`) | "It has **all editor permissions, project billing setup permissions, and permissions for managing all resources in a project**." |
| **Editor** (`roles/editor`) | "It has **viewer permissions**. For most of the Google cloud services, this role provides permissions to **modify resources**." |
| **Viewer** (`roles/viewer`) | "**Permissions for read-only and viewing**." |

_(Mod 12 p255)_

- "**Owing to security concerns, it is better to avoid the use of primitive roles.**"
- Figure rule: "**Avoid using primitive roles such as (`roles/owner`, `roles/editor`, and
  `roles/viewer`) for security-critical resources.**" _(Mod 12 p255)_

**The only three cases in which a primitive role is granted** — figure and body agree _(Mod 12 p255)_:

| # | Figure wording | Body wording |
|---|---|---|
| 1 | "When a GCP service **does not provide a predefined role**" | identical |
| 2 | "**To grant broader permissions for a project**" | "Requiring broader permissions for a project such as in **development or test environments**" |
| 3 | "**For small teams that do not require granular permissions**" | "When the **team size is small and team members do not require granular permissions**" |

### Walkthrough — assign a role in IAM _(Mod 12 pp256–257)_

1. "**Open the Google Cloud Console, navigate to `IAM & admin`, and click on `IAM` on the Menu
   tab.**" _(p256, Fig 12.169)_
2. "**Select `Add`** to assign a role, **enter one or more members in the `New members` field**,
   **select the role from the `Role` dropdown menu**, and **click on `Save`**." _(p256, Fig 12.170)_
3. Result: "The selected role will be **granted and can be viewed in `PERMISSIONS`** in the
   horizontal menu." _(p257, Fig 12.171)_

## Separate service account per service — the stated rules _(Mod 12 p258)_

**Figure, three bullets, verbatim** _(Mod 12 p258)_:

- "When working with **multiple services that require different permissions**, **create a
  separate service account for each service**."
- "**Treat each application component as a separate trust boundary.**"
- "**Grant only the required permissions to each service account.**"

**Body rules** _(Mod 12 p258)_:

- "Service accounts are **accounts created to access the cloud platform APIs using
  applications**. They **perform tasks according to the role assigned** to specific service
  accounts."
- "It is possible to create **up to 100 service accounts per project**."
- **Service account user role scope** — "can be granted at the **project level** or
  **service account level**. If a service account user role is granted at the project level,
  then the user **can access all service accounts in the project**. If … at the service
  account level, the user **can only access that service account**."
- "It is important to **practice caution** while granting service account user roles because
  the service account users **indirectly have access to all resources of the service
  account**."
- "**Minimum permission should be granted to service accounts based on the requirement.**"
- "**Every component of the application should be treated as a discrete trust boundary.** If
  there are many services and each service requires different permissions, then **create a
  separate service account for each service and give permission to the required service
  account**."
- "**Restrict the actions of users to modify the service accounts of a project.**"

### Walkthrough — create a service account _(Mod 12 pp259–261)_

1. "**From the Google Cloud Console, navigate to `IAM & admin` and select `service accounts`
   from the menu.**" _(p259, Fig 12.172)_
2. "To create a service account, **click on `CREATE SERVICE ACCOUNT`** on the horizontal
   menu." _(p259, Fig 12.173)_
3. "**Enter the service account details and click on `Create`.**" _(p259, Fig 12.174)_
4. "**Select the role for service account permissions and click on `CONTINUE`.**" _(p260, Fig 12.175)_
5. "**Click on `CREATE KEY` and select the JSON file that contains the private key.**"
   _(p260, Figs 12.176–12.177 — the **JSON download** step)_
6. "**After the private key is saved, click on `DONE`.**" _(p261, Fig 12.178)_
7. Result: "Thus, **service account with the assigned role is created and can be viewed in the
   IAM menu `PERMISSIONS` tab**." _(p261, Fig 12.180)_

**Optional panels legible in the figures** (screenshot text only, pp259–261):
`Grant this service account access to the project (optional)` ·
`Grant users access to this service account (optional)` · key panel: `Download` ·
`Why you need a key` · confirmation banner: "**Private key saved to your
computer**". _(a third button label beside `Download` / `Why you need a key` does not
survive the OCR and is not asserted — see `unresolved:`)_

**Definition banner, p259 Fig 12.173:** "A service account represents a **Google Cloud service
identity such as code running on Compute Engine VMs, App Engine apps, or systems running
outside Google**."

Downstream: [[12-LO06e-GCP-Service-Account-Key-Rotation]] ·
[[12-LO06f-GCP-Organization-Policies]] · least privilege:
[[12-LO06c-GCP-IAM-Security-Best-Practices]]






