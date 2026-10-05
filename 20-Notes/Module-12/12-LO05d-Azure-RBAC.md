---
type: note
module: "12"
lo: "05"
tags: [concept, policy, mod/12]
topic: "Azure IAM role-based access control (RBAC)"
exam_weight: unknown
status: done
unresolved:
  - "p171: the section's first sentence prints 'ASC uses RBAC to assign various built-in roles to users, groups, and services to access the Azure resources.' 'ASC' is never expanded in the body; the section heading prints 'Azure IAM App Security Configuration: Implement Role-based Access Control'. The token is left as printed rather than expanded to Azure Security Center."
  - "p171 principal list differs between the rules and the prose: the best-practice bullet says permissions are assigned to 'users, groups, and applications', while the opening sentence says 'users, groups, and services'. The walkthrough then uses 'User, group, or service principal' plus 'Managed identity'. All four phrasings are kept as printed; the courseware does not reconcile them."
  - "p175 CONTRADICTION: the step text says 'Click Review + assign to assign the role', while the caption of Figure 12.96 for the very same step reads 'Click Review+Create'. Both are reproduced as printed; neither is treated as the correct button name."
  - "p175: the 'Add condition' step is scoped as refining assignments 'based on the storage blob attributes' and the figure is a Storage Blob Data Reader assignment. The courseware never states that conditions are available for any other role."
  - "pp171-176: NO role definition IDs, GUIDs, cmdlets or PowerShell/CLI equivalents are printed anywhere in this walkthrough. None are supplied here."
  - "p172 Figure 12.89 'Add role assignment' page: the command bar OCR's as 'Add role / Edit columns / Refresh / Add custom roles / Deny assignments / Classic administrators' over a garbled 'the subscription type' line. Only 'Deny assignments' and 'Classic administrators' read cleanly enough to name; 'Add custom roles' is a fragment and is not asserted as a control."
  - "p173 Figures 12.90/12.91: the Roles tab role names do not OCR ('Blob Data' is the only readable fragment in the Details view). The only role name printed cleanly in the whole walkthrough is 'Storage Blob Data Reader' (p175, Fig 12.95)."
  - "p176 Figure 12.97: the Role assignments grid values OCR as '32', '16' and '1 items (0 users)' with a role reading 'Blob Data Reader / Storage' and scope 'this resource'. The counts are screenshot values, are not reproducible, and are not asserted."
---

[[MOC-Module-12]]

# Azure RBAC (§12.05)

> **LO#05: Security in Microsoft Azure Cloud** — area 2 of 7: **Azure IAM features and best
> practices** _(Mod 12 p156)_
> Covers pp. 171–176: implement role-based access control.

## The concept — rules, not clicks _(Mod 12 p171)_

- "**[ASC]** uses RBAC to **assign various built-in roles** to users, groups, and services to access
  the Azure resources." (token as printed — see `unresolved:`)
- "The **assignment of roles** helps in **controlling access to resources**."
- "If the **built-in roles do not meet the requirements** of an organization, then the customer can
  **create custom roles** for the Azure resources."

**Best practices** _(p171, as printed)_:

| # | Rule |
|---|---|
| 1 | Use RBAC to implement the **least-privilege security principles** and **granular access control** |
| 2 | Assign permissions to users, groups, and applications on a **subscription, resource group, or single resource scope** |
| 3 | Use **built-in roles to segregate duties within the team** and only grant users the required access **for their job** |
| 4 | **Grant the RBAC security reader role to security teams** |

## The two objects you must be able to name

**Role** = a bundle of permissions, chosen from built-ins or custom. **Assignment** = role + security
principal + scope. _(Mod 12 p171)_

**Scope** — the level the assignment applies to, from broad to narrow _(Mod 12 p171)_:

| Scope | Printed as |
|---|---|
| Subscription | rule 2; also listed in the walkthrough search |
| Resource group | rule 2; also the scope used in Figures 12.87–12.88 |
| Single resource | rule 2 |
| Management groups | appears **only** in walkthrough step 1, not in rule 2 |

**Security principal** — who receives the role _(pp173–174)_:

| Principal | Where the courseware names it |
|---|---|
| **User** | Members tab, "assign the selected role to Azure AD users" _(Mod 12 p173)_ |
| **Group** | Members tab _(pp173–174)_ |
| **Service principal** | Members tab, "or applications" _(Mod 12 p173)_ |
| **Managed identity** — *user-assigned* or *system-assigned* | Members tab; "In the Select managed identities pane, select whether the type is user-assigned managed identity or system-assigned managed identity" _(p174, Fig 12.94)_ |

Result of the walkthrough: "The **security principal is assigned the role at the selected
scope**." _(p176, Fig 12.97)_

## Walkthrough — click path only _(Mod 12 pp171–176)_

1. **Sign on to the Azure portal** and in the **Search box** search for the scope to grant access
   to (Management groups, Subscriptions, Resource groups). _(Mod 12 p171)_
2. **Click on the specific resource** for that scope. _(p172, Fig 12.87)_
3. **Click on Access control (IAM).** _(p172, Fig 12.88)_
4. **Click on the Role assignments tab** to view the role assignments at this scope. _(Mod 12 p172)_
5. **Click Add > Add role assignment.** _(p172, Fig 12.89)_
6. **Select the role** that is needed from the **Roles tab**; "Click on **View** to get details
   about a role in the **Details** column." _(p173, Figs 12.90–12.91)_
7. On the **Members** tab select **User, group, or service principal** to assign the selected role
   to Azure AD users, groups, or applications. _(p173, Fig 12.92)_
8. **Click on Select members** to select the users, groups or applications. _(p174, Fig 12.93)_
9. **Click on Select** to add more users, groups or applications to the Members list. _(Mod 12 p174)_
10. **Select Managed identity** to assign the selected role to one or more managed identities;
    **Click Select members**; in the pane select **user-assigned managed identity** or
    **system-assigned managed identity**. _(p174, Fig 12.94 — also shows *All system-assigned
    managed identities* and a *Virtual machine* entry)_
11. **Click Select** to add the managed identities to the Members list. _(Mod 12 p175)_
12. In the **Description** box enter an **optional** description for this role assignment. _(Mod 12 p175)_
13. **Click Next.** _(Mod 12 p175)_
14. **Click Add condition** if you want to refine the role assignments **based on the storage
    blob attributes** — the figure's role is **Storage Blob Data Reader**, and the pane reads "Add
    an optional check to your role assignment for more fine-grained control". _(p175, Fig 12.95)_
15. **Click Review + assign** to assign the role — the figure caption for this step prints
    "Click Review+Create". _(p175, Fig 12.96 — see `unresolved:`)_
16. **Result:** the security principal holds the role at the selected scope; verify on the
    **Role assignments** tab (grid columns: **Role**, **Scope**; *Group by: Role*). _(p176, Fig 12.97)_

Cross-module: least privilege `[[03-LO01-Access-Control-Models]]` ·
AWS role comparison `[[12-LO04e-AWS-Least-Privilege-and-Policy-Types]] ·
upstream `[[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]`






