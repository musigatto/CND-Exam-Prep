---
type: note
module: "12"
lo: "06"
tags: [policy, concept, mod/12]
topic: "GCP predefined roles, custom roles, and logging roles"
exam_weight: unknown
status: done
unresolved:
  - "p268: the role id is printed two ways. The body says 'The role of roles/action.Admin is given to the Action Admin to edit and deploy an action' (singular 'action'), while the p269 search instruction uses the term '(actions.Admin)' and the Fig 12.184 header OCR's to 'roles/ actions. Adn in roles/ act Ions'. Both spellings are kept; neither is asserted as the canonical id."
  - "p268 Fig 12.184: the List of Actions roles table has a Permissions column, but its cells OCR as an unreadable mash ('actions.• firebase projects.get firebase. projects. update resourcemanager.projects get resourcemanager.pr*txlist actions.agent.get actiors.agentversions.list'). Only the four permissions printed legibly in the BODY paragraph are transcribed. 'actions.*' appears in the body list but its exact token is not certain from the garbled figure."
  - "p270: the courseware prints the grammar error 'custom roles are created to according to the permissions' and 'Custom roles: When predefined roles do not satisfy the requirements of the organization'. Reproduced as printed."
  - "p271 Fig 12.190: the ADD PERMISSIONS permission picker did not OCR. The legible window chrome is 'accessapproval.requests.* / accessapproval.settings.* / accesscontextmanager.accessLevels.*' but these are unrelated to the custom role being created and are not asserted as the role's permissions."
  - "p271: the Create Role figure's Title field is legible as 'Custom App Engine Admin' and the 'Based on:' line as 'App Admin' / 'Custom App Engine Admin'; the Created date OCR's as both '2020-01-16' and a garbled '10'."
  - "p273: the Fig 12.195 role-id list OCR's as 'roles/Iogging.IogWriter' for the third entry. Resolved to roles/logging.logWriter because the body paragraph two lines later names 'Roles/logging.logWriter' with the same description. The other seven ids in that figure are legible."
  - "p274: the page contains ONLY the three body sentences transcribed above - the console walkthrough for creating a custom role with logging permissions was not printed in the text, only a section heading. No click path is asserted here."
---

[[MOC-Module-12]]

# GCP Predefined Roles and Logging Roles (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)**
> Covers pp. 268–274: grant pre-defined roles for granular access (pp268–272) ·
> use logging roles for log auditing (pp273–274).
> Contrast: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]] (predefined is
> granted *instead of* primitive). Downstream log-audit roles: [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]].

## Grant pre-defined roles — the stated rules _(Mod 12 p268)_

- **Figure rule** — "To implement **granular access** to specific Google Cloud Platform
  resources and **prevent unwanted access** to other resources, **grant pre-defined roles
  instead of primitive roles**."
- "**Predefined roles provide fine-grained access control.**"
- "A **specific role is given to a resource type**. **Multiple roles can also be given to the
  same user.**"
- **Printed example** — the predefined role **Pub/Sub Publisher (`roles/pubsub.publisher`)**
  "will allow permission to **only publish messages** related to Pub/Sub topic."
- **Printed example** — the role of **`roles/action.Admin`** "is given to the **Action Admin**
  to edit and deploy an action; It contains the following permissions:"

| Permission, as printed on p268 |
|---|
| `actions.*` |
| `firebase.projects.get` |
| `firebase.projects.update` |
| `resourcemanager.projects.get` |
| `resourcemanager.projects.list` |

### Walkthrough — grant a predefined role _(Mod 12 p269)_

1. From the Google console dropdown menu, navigate to **IAM & admin** and select **Roles**.
2. "Select the **filter from filter table (Name)** and search the role (**`actions.Admin`**)."
3. "Click on the **context menu** to see the assigned permissions."
4. "Click **IAM** on the Menu tab, select **Add** to assign role, **enter the email id of the
   user**, select **Actions Admin** from the **Role** dropdown menu, and click on **Save**."
5. Result: "a predefined role is **granted** in the GCP." _(p270, Fig 12.187)_

## Custom roles — the stated rules _(Mod 12 p270)_

- "**When predefined roles do not satisfy the requirements of the organization**, then custom
  roles are created to according to the permissions."
- "A **custom role is a user-defined role** that allows the **collection of supported
  permissions** to satisfy the requirements of an organization."
- "**Because Google does not maintain custom roles**, these roles are **not updated
  automatically** by the GCP."
- **Where they can be created** — "Custom roles can be created at the **organization and
  project** level; **however, they cannot be created at the folder level.**"
- Console wording, Fig 12.188 / Fig 12.189 _(p270–271)_: "Custom roles let you **group
  permissions** and **assign them to members** of your project or organization. You can
  **manually select permissions or import permissions from another role**."

### Walkthrough — create a custom role and grant it _(Mod 12 pp270–272)_

1. From the Google console dropdown menu, navigate to **IAM & Admin** and select **Roles**.
2. "Select a **role from the filter table**, click on the **context menu**, and select
   **Create role from this role**."
3. "Create custom role and click on **ADD PERMISSIONS**."
4. "**Select the required permissions** and click on **ADD**." → "the custom **App Engine
   Admin** roles are created." _(p271, Fig 12.191)_
5. "Click on **IAM** in the Menu tab, select **Add** to assign role, **enter the email id of
   the user**, select **Custom App Engine Admin** from the **Role** dropdown menu, and click
   on **Save**." _(p272, Fig 12.192)_
6. Result: "custom roles are **granted** to the user." _(p272, Fig 12.193)_

| Predefined vs custom — the exam delta | Predefined | Custom |
|---|---|---|
| Maintained by Google | yes | **no** — not updated automatically |
| Granularity | fine-grained, per resource type | user-built collection of supported permissions |
| Creatable at | (service-defined) | **organization and project** only — **not folder** |

_(Mod 12 pp268, 270)_

## Use logging roles for log auditing — the stated rules _(Mod 12 p273)_

- **Figure rules** — "Use **logging roles** to restrict access to logs" · "**Create custom
  roles with logging permissions**."
- "Cloud IAM permissions and roles guide the user on the **Logging API, Logs Viewer, and
  `gcloud` command-line tool**."
- "**Each Google cloud resource has its own group of members** with Google Cloud's operations
  suite logging roles and permissions. **A member with a cloud IAM role can only use logging as
  follows:**"

| Role id | Printed capability |
|---|---|
| `roles/logging.viewer` | "**read-only access** to the logging features. This role **does not provide access to the Access Transparency logs and Data Access audit logs**." |
| `roles/logging.privateLogViewer` | "consists of the **log viewer role with read** Access Transparency logs and Data Access audit logs" |
| `roles/logging.logWriter` | "is **provided to service accounts** for giving permissions to **applications for writing logs**" |
| `roles/logging.configWriter` | "permission for **log metrics, log exclusion, and exporting log entries to sink**" |
| `roles/logging.admin` | "provides **all permissions related to logging**" |
| `roles/viewer` | "The **project viewer** role is **the same as that of log viewer**" |
| `roles/editor` | "consists of log viewer permissions to **write and delete logs and create logs metrics**. This role **does not allow the creation of export sinks** or read the Access Transparency and Data Access audit logs" |
| `roles/owner` | "provides **full access** to logging, Access Transparency logs, and Data Access audit logs" |

_(Mod 12 p273)_

**The two log families that gate on `privateLogViewer` / `owner`** — Access Transparency
logs and Data Access audit logs. Both are excluded by `roles/logging.viewer` and by
`roles/editor`; only `privateLogViewer` and `owner` read them.

## Creating a custom role with logging permissions — the stated rules _(Mod 12 p274)_

- "To create a custom role that grants **logging API permissions**, **select an API
  permission**."
- "For the role that grants permissions to **use the log viewer**, select from **console
  permissions**."
- "For the role that grants permissions to **use `gcloud` logging**, **browse the `gcloud`
  tool**."

> Permission source follows the interface: **API permission** for the logging API itself ·
> **console permissions** for Logs Viewer · **`gcloud` tool** for the command line. No
> console click path is printed on p274.

Upstream: [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]] ·
[[12-LO06f-GCP-Organization-Policies]] · [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]







