---
type: note
module: "12"
lo: "06"
tags: [policy, bestpractice, mod/12, flashcard/12]
topic: "GCP organization policies and policy inheritance"
exam_weight: unknown
status: done
unresolved:
  - "p264 CONTRADICTION: the figure bullet and BOTH code snippets use the constraint 'constraints/iam.disableServiceAccountCreation', but the body sentence says 'Establishing the Boolean constraint iam.disableServiceAccountKeyCreation for the service account of a project will not allow the creation of user-managed credentials.' The two names differ (Creation vs KeyCreation) and both are reproduced; neither is treated as the correct one."
  - "p264: the figure snippet's closing braces OCR as '\\321' and the body snippet has no 'resource:' line but does carry an 'etag:' field. Both renderings are shown as printed rather than merged into one clean snippet."
  - "p264: the organization id reads 'organizations/842463781240' in the figure snippet and 'organizations/ 8424 63781240' in the body snippet. The digits are the same number with different OCR spacing; treated as one value."
  - "p265: the resource-hierarchy diagram did not OCR at all - no node labels, no edges. The four policy levels recorded here come entirely from the body text, not from the figure."
  - "pp265-267: the App Engine Admin example member address OCR's as 'userid@gmail.com' (identity spelled 'identify'); reproduced as printed and it is a generic placeholder, not a real account."
  - "pp266-267: the constraint shown in Figures 12.181-12.183 is 'Define allowed APIs and services' with policy-name fragments OCR-ing as '...vmExternalAccess' and '...googleGuestAttributesAccess'. These are screenshot names of an unrelated constraint and are not asserted as valid policy names here."
  - "p267: the courseware prints 'which allows the resource to inherent the rules of the parent's policy' - 'inherent', not 'inherit'. Reproduced as printed."
---

[[MOC-Module-12]]

# GCP Organization Policies and Policy Inheritance (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)** _(Mod 12 p245)_
> Covers pp. 264–267: restrict access for creating and managing service accounts (p264) ·
> check the granted policy on each resource, i.e. hierarchical inheritance (pp265–267).
> Source list: [[12-LO06b-GCP-Service-Accounts]] (best practices 3 and 6).

## Centralizing service account creation — the stated rules _(Mod 12 p264)_

- "To centralize the management of service accounts, the **creation of new service accounts
  should be disabled**."
- **Figure rule** — "**Use the `iam.disableServiceAccountCreation` boolean constraint to
  disable the creation of new service accounts**."
- **Body sentence, different constraint name** — "Establishing the Boolean constraint
  **`iam.disableServiceAccountKeyCreation`** for the service account of a project will not
  allow the creation of **user-managed credentials**." (see `unresolved:`)

**Snippet as printed in the figure** _(p264)_ — closing braces OCR garbled:

```
resource: "organizations/842463781240"
policy {
    constraint: "constraints/iam.disableServiceAccountCreation"
    boolean_policy {
        enforced: true
```

**Snippet as printed in the body** _(p264)_ — no `resource:` line, adds `etag:`:

```
organizations/ 8424 63781240
policy {
    constraint: constraints/iam.disableServiceAccountCreation
    etag:
    boolean_policy {
        enforced: true
```

### Walkthrough — restricting access to service accounts _(Mod 12 p264)_

1. From the Google Cloud Console, navigate to **IAM & Admin** and click on **Organization
   policies**.
2. **Select the organization** from the drop-down list.
3. Select **Disable Service Account Creation**.
4. Click on the **Edit** button.
5. Under **Applies to**, click on **Customize**.
6. Go to **Enforcement** and select **On**.
7. Select **Save**.

## Check the granted policy on each resource — the stated rules _(Mod 12 p265)_

- "A policy **describes the member roles** on the cloud resource. The creation of a policy
  linked to a resource **binds the member(s) to a role** in the Google cloud resources."
- **Printed example** — a member whose identity is an email address (`userid@gmail.com`) is
  granted **App Engine Admin** (`roles/appengine.appAdmin`). "If a policy is created for a
  **project**, then the end-user would take the App Engine Admin role **within the purview of
  the project**… This allows the user to **view, create, and update all app functionalities
  and behaviors at the project level**."
- **Figure rule** — "**Understand the hierarchical inheritance of the policy to know whether a
  policy is set on a child resource or its parent.**"
- "The Google cloud resources are arranged **hierarchically**, in which the **organization is
  the root node**, the **projects** are depicted as the **children of an organization**, and
  other resources are the **descendants of the projects**."
- "An **effective** cloud IAM policy can be formed for a resource by **combining the policy
  inherited from the parent and that set at the resource**."

| Level | Printed as |
|---|---|
| **Organization** | "Cloud IAM policies granted at the organization level are **inherited by all resources**." |
| **Folder** | "Folders may contain **projects, other folders, or a combination** of projects and folders. The roles granted to the **highest folder level are inherited by the projects and other folders present in the parent folder**." |
| **Project** | "In an organization, the **projects depict the trust boundary**. The roles allowed in the cloud IAM **project level are inherited by all resources**." |
| **Resource** | "**Apart from Cloud Storage**, resources like **Genomics data, Compute Engine instances, and Pub/Sub topics** support the **lowest-level roles**." |

_(Mod 12 p265)_

## Walkthrough — enable organization policy inheritance _(Mod 12 pp266–267)_

1. "**Open the Google Cloud Console, navigate to `IAM & Admin`, click on `Organization
   policies`.**" _(p266)_
2. "**Click on `Select`**, and then **select the project/folder/organization as per
   requirement to change the policy**." _(p266, Fig 12.181)_
3. "A **policy details page containing the constraints** will open; **select a constraint from
   the list**." _(p266, Fig 12.182 — the constraint displayed is *Define allowed APIs and
   services*)_
4. "**Click on `Edit`** and select **`Inherit parent's policy`**, which allows the resource
   to **inherent** the rules of the parent's policy." _(p267, Fig 12.183)_
   - Policy summary rows legible in Fig 12.183: `Inherited policy` · `Recommended` ·
     `Google-managed default` · `Recommended` · `Current policy` · `Recommended`; `Applies to` =
     `Organization`, with `Customize` and `SAVE`.

_(Mod 12 pp266–267)_

Upstream: [[12-LO06c-GCP-IAM-Security-Best-Practices]] ·
[[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]] · cross-module hierarchy and
trust boundary: `[[03-LO01-Access-Control-Models]]`

## Cards

The four levels at which a GCP IAM policy can be set, and what each is inherited by
?
Organization — policies are inherited by all resources · Folder — the highest folder level's roles are inherited by the projects and other folders in the parent folder · Project — the trust boundary; its roles are inherited by all resources · Resource — lowest-level roles, e.g. Genomics data, Compute Engine instances and Pub/Sub topics, apart from Cloud Storage

The two constraint names printed for disabling service account creation
?
Figure and both snippets: constraints/iam.disableServiceAccountCreation · body sentence: iam.disableServiceAccountKeyCreation (which "will not allow the creation of user-managed credentials") — the courseware prints both

How to centralize the management of service accounts
?
Disable the creation of new service accounts by enforcing the boolean constraint in an organization policy — console: IAM & Admin → Organization policies → select the organization → Disable Service Account Creation → Edit → Applies to Customize → Enforcement On → Save

What does `Inherit parent's policy` do
?
It lets the resource inherit the rules of the parent's policy, so a child no longer carries its own overridden policy — the policy summary then shows the Inherited policy / Google-managed default alongside the Current policy

How is an effective IAM policy formed for a resource
?
By combining the policy inherited from the parent with the policy set at the resource itself — so the hierarchy is organization (root) → projects (children) → other resources (descendants)
