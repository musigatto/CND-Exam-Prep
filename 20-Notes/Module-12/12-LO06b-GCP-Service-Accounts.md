---
type: note
module: "12"
lo: "06"
tags: [concept, policy, mod/12]
topic: "GCP service accounts, roles and permissions"
exam_weight: unknown
status: done
unresolved:
  - "p249: the brief's framing 'a service account grants access to all resources of that project' is NOT printed anywhere in pp.248-249. p249 says something different: permissions granted AT THE PROJECT LEVEL are inherited by all resources of that project. The only place in this LO where a service account confers blanket resource access is p258 - 'the service account users indirectly have access to all resources of the service account' - which is scoped to THAT service account's resources, not to the project. Both statements are kept as printed and neither is reworded into the other."
  - "p249: the master list prints EIGHT best practices, not 'some of the ...' in the count sense. Only the first six are expanded anywhere in the LO#06 pp.245-267 range; 'Grant predefined roles' and 'Use logging roles for log auditing' are never explained in that range."
  - "p248: only two role ids are legible - roles/storage.admin (Storage Admin) and roles/compute.instanceAdmin (Compute Instance Admin). No other role id is printed in this slice and none is supplied."
  - "p248: the Google group section says the group 'has a unique email address' and in the next sentence 'It is not possible to establish an identity for a Google group to access resources because it does not have login credentials.' Both are printed; the courseware does not reconcile the tension."
  - "p248: 'G Suite Domain' and 'Cloud Identity Domain' are both defined here, but the p247 member list names the same two members 'Google Workspace account' and 'Cloud Identity domain'. The courseware uses 'G Suite' and 'Google Workspace' interchangeably; both spellings are kept as printed on their own page."
  - "pp248-249: the project-level inheritance sentence straddles the page break - it starts on p248 ('...which is inherited by') and completes on p249 ('all resources of that project')."
---

[[MOC-Module-12]]

# GCP Service Accounts, Roles and Permissions (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)** _(Mod 12 p245)_
> Covers pp. 248–249: service account (p248) · Google group / G Suite domain / Cloud Identity
> domain / role / permission (p248) · scope of a grant and the GCP IAM best-practice list
> (p249). Upstream: [[12-LO06a-GCP-Shared-Responsibility-and-IAM]].

## Service account — the definition to quote _(Mod 12 p248)_

> "A service account is a **special account that belongs to an application or VM instance, but
> not to end-user, to run the specified account code hosted in Google cloud**."
> "**Multiple service accounts can be created for different logical components of an
> application**."

That is the entirety of the p248 service-account material — the page then moves to Google
groups, domains, and roles/permissions.

## Scope of a grant: project level vs resource level _(Mod 12 pp248–249)_

- **Fine-grained (resource) level** — "For some service support, there is the need to grant
  cloud IAM permission at **fine-grained levels instead of the project level**."
- **Project level** — "in other scenarios, the permissions should be granted at the **project
  level, which is inherited by all resources of that project**."

| Level | Printed example |
|---|---|
| Resource / fine-grained | the user of a **specific Cloud Storage bucket** is given **Storage Admin** (`roles/storage.admin`); the user of a **particular Compute Engine instance** is given **Compute Instance Admin** (`roles/compute.instanceAdmin`) |
| Project | "access to **all cloud storage buckets** of a project will be granted at the project level instead of individual bucket level"; "access to **all Compute Engine instances** of a project will be given at the project level instead of an individual instance" |

_(Mod 12 pp248–249)_

> **Neither example is about a service account** — both are about *where a grant is placed*.
> The only service-account-scoped blanket access claim in this LO is p258: "the service
> account users **indirectly have access to all resources of the service account**" —
> see [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]].

## Role and permission _(Mod 12 p248)_

- **Role** = "a **set of permissions**." "Note that **permissions cannot be directly assigned
  to a user**; instead, they are **granted by assigning roles** to the user, group, or service
  account."
- **Permission** = determines "the **accessibility of resource operations**", written
  `<service>.<resource>.<verb>` — printed example: `pubsub.subscriptions.consume`.
- "Permissions are generally **correlated one-to-one with the REST API method**", and "each
  Google cloud service is associated with the collection of permissions for each **exposed
  REST API method**", so "the users **need permission to call that method**."
- **Printed worked example** — Google Cloud Pub/Sub "exchanges messages between independent
  applications"; calling `topics.publish()` requires the **`pubsub.topics.publish`**
  permission on that topic.

## The other p248 members, one line each _(Mod 12 p248)_

| Member | Printed statement |
|---|---|
| **Google group** | "consists of **Google accounts and service accounts**"; "has a **unique email address**, which can be viewed by clicking on **About** on the Google group homepage"; "**not possible to establish an identity** for a Google group to access resources because it **does not have login credentials**"; "easy to apply a policy to the **whole group**", and members can be added/removed "**without updating the GCP IAM policy**" |
| **G Suite domain** | "a **virtual group comprising all Google accounts** of an organization"; "an **internet domain** of an organization such as `example.com`"; adding a user creates `username@example.com` |
| **Cloud Identity domain** | "a **virtual group of all Google accounts**"; its users "**cannot access the G suite domain applications**" |

## The 8 GCP IAM security best practices — master list _(Mod 12 p249)_

> "Following are some of the GCP IAM security best practices:" — eight items, verbatim.

| # | Best practice | Expanded in this LO at |
|---|---|---|
| 1 | Grant least privileges to avoid primitive roles | [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]] |
| 2 | Create separate service account | [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]] |
| 3 | Check granted policy on each resource | [[12-LO06f-GCP-Organization-Policies]] |
| 4 | Restrict who acts as service accounts | [[12-LO06c-GCP-IAM-Security-Best-Practices]] |
| 5 | Rotate service account keys | [[12-LO06e-GCP-Service-Account-Key-Rotation]] |
| 6 | Restrict access to create and manage service accounts | [[12-LO06f-GCP-Organization-Policies]] |
| 7 | Grant predefined roles | — not expanded in pp. 245–267 |
| 8 | Use logging roles for log auditing | — not expanded in pp. 245–267 |

_(Mod 12 p249)_






