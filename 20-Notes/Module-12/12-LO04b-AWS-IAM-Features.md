---
type: note
module: "12"
lo: "04"
tags: [tool, concept, mod/12]
topic: "AWS IAM core, features, Identity Center, Access Analyzer"
exam_weight: unknown
status: done
unresolved:
  - "p46 Figure 12.4 'Working of AWS IAM Identity Center': the three banner labels are only partly legible - 'One place to manage AWS account access' and 'Application assignments - One place to manage access to AWS and cloud applications' read cleanly, but the third OCR's as 'l&ntities Che place for workforce users and group access' and the surrounding artwork (two AWS accounts, directory, source/portal nodes) is image-only. Only the two clean labels are transcribed."
  - "p46: the figure strapline OCR's as 'AWS IAM Identity Center Scale identifies and access for workforce agility and workload innovation' - garbled beyond resolution; not transcribed as a claim."
  - "p49: the sentence 'IAM Access Analyzer is about the permissions lifecycle to get the right permissions, setting permissions, verifying permissions, and refining permissions' has a garbled verb (printed as 'is about'). The four lifecycle phases that follow it are legible and are the only part used."
  - "p48/p49 figure 'Working of IAM Access Analyzer': the middle step label is printed out of order as 'Verify who can be accessed by who'. Reproduced as printed; not rewritten into the conventional 'who can access what' form."
  - "p44: 'The operations are defined by a service and can be viewing, creating, editing, and deleting the resource. IAM supports 40 actions for a user resource.' The second sentence reads oddly in the source and its context is not given; quoted as printed, not interpreted."
  - "p50 Figure 12 'IAM Access Rules and Permissions': one policy-type label OCR's as 'Ide based Policies' (truncated). It is paired in the figure with 'Resource-based Policies', but the token itself is left as printed rather than completed."
  - "p50 figure also contains an unreadable string ('Authorization aaaaa') between the diagram nodes; not transcribed."
---

[[MOC-Module-12]]

# AWS IAM Features (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · area 2 of 6: **AWS IAM features and best
> practice to implement IAM securely** _(Mod 12 p40)_
> Covers pp. 44–51: IAM core (p44) · IAM security features (p45) · IAM Identity Center (pp46–47) ·
> IAM Access Analyzer (pp48–49) · IAM access rules and permissions (pp50–51).

## AWS Identity and Access Management _(Mod 12 p44)_

- "AWS Identity and Access Management (IAM) is a **web service** that secures access to AWS
  services and resources, as well as the **creation and management of AWS users and groups**,
  in addition to the use of **permissions to allow or prohibit access** to AWS services." _(Mod 12 p44)_
- IAM helps set and manage **guardrails** and **fine-grained access controls** for the
  **workforce and workloads**. _(Mod 12 p44)_
- Manage identities **across different AWS accounts**, or **centrally connect** identities to
  various AWS accounts. _(Mod 12 p44)_
- **Temporary security credentials** can be granted to workloads that access your AWS
  resources using IAM. _(Mod 12 p44)_
- "You can **examine access to right-size permissions** on a regular basis, which will lead to
  **least privilege**." _(Mod 12 p44)_

**Figure 12.3 — IAM as the who/what bridge** _(Mod 12 p44)_

| Who | Can access | What | Resources |
|---|---|---|---|
| Workforce users and workloads with IAM | Permissions with IAM policies | AWS services | Within organization |

### Request flow _(Mod 12 p44)_

```
principal (user | workload) → requests a resource
   → AWS IAM authenticates + authorizes
   → IAM approves the actions/operations
operations = viewing · creating · editing · deleting
   → must be defined in a policy
```

- "The operations that are to be performed on the resource by the principal **must be defined
  in a policy**." _(Mod 12 p44)_
- Features panel printed on p44: **AWS Access Analyzer · AWS IAM Identity Center · Manage IAM
  permissions · Manage IAM roles · Multi-Factor Authentication (MFA)**.

## Security features of AWS IAM _(Mod 12 p45)_

| # | Feature | Printed statement |
|---|---|---|
| 1 | **Manage IAM permissions** | Fine-grained access control; policies define **who** has access to which AWS resources **under what conditions** |
| 2 | **Manage IAM roles** | Roles are **entities that define and provide specific permissions**, allowing trusted identities (workforce identities, applications) to conduct actions in AWS |
| 3 | **Multi-factor authentication** | A best practice for AWS IAM; needs a **two-step verification factor in addition to** username + password sign-in credentials |
| 4 | **Identity Center** | Earlier called **AWS Single Sign-On**; a central place to administer users and their access to cloud applications and AWS accounts |
| 5 | **Access Analyzer** | Identifies resources, **generates** IAM policies based on access activity, and **validates policies against policy grammar** |
| 6 | **Shared access to AWS account** | Other users can utilize and administer resources **without sharing an access key and password** |
| 7 | **Identity federation** | Users who already have passwords elsewhere get **temporary access** to an AWS account |
| 8 | **PCI DSS compliance** | IAM assists the processing, transmission, and storage of credit card data by a service provider and **has been approved as being compliant with PCI DSS** |
| 9 | **EC2 application credentials** | For applications running on EC2 instances, IAM **supplies credentials** |

_(Mod 12 p45)_

## AWS IAM Identity Center _(Mod 12 pp46–47)_

Formerly **AWS Single Sign-On** _(p45–46)_. "Provides the administrator **a central place** to
work together on the administration of users and their access to **AWS accounts and cloud
applications**." _(Mod 12 p46)_

- Manage **sign-in security for the workforce** by establishing or connecting users and groups
  to AWS **in a single place**. _(Mod 12 p46)_
- Assign workforce identities to AWS accounts with **multi-account permissions**; use
  **application assignments** to give users access to **SaaS applications**. _(Mod 12 p46)_
- "IAM Identity Center can work with **organizations of any size and type**." _(Mod 12 p46)_

| Key feature | Printed statement |
|---|---|
| **Workforce identities** | Administrator can **create** workforce users and groups in IAM Identity Center, **or connect and synchronize** to an existing set of users and groups for use across all AWS accounts and applications |
| **Application assignments for SAML applications** | Single sign-on access to **SAML 2.0** applications, e.g. **Salesforce** and **Microsoft 365** |
| **Identity Center enabled applications** | AWS applications and services **discover and connect** to IAM Identity Center automatically to receive sign-in and user directory services |
| **Multi-account permissions** | Centrally implement IAM permissions across multiple AWS accounts **at one time without configuring each account manually**; create **fine-grained permissions based on common job functions** and define custom permissions |
| **AWS access portal** | **One-click access** to all assigned AWS accounts and cloud applications through a simple web portal |

_(Mod 12 pp46–47)_

Figure 12.4 banner labels (readable part) _(Mod 12 p46)_: *One place to manage AWS account
access* · *Application assignments — one place to manage access to AWS and cloud applications*.

## IAM Access Analyzer _(Mod 12 pp48–49)_

"Helps in identifying resources, generating, and validating policies" — a service that "helps
process management of cycle toward the **least privilege** in **three steps**." _(Mod 12 p48)_

| Step | What Access Analyzer does |
|---|---|
| **Set / Grant fine-grained permissions** | **Policy generation** produces a fine-grained policy from access activity captured in your logs; **policy validation** eases authoring with **more than 100 policy checks** |
| **Verify intended permissions** | Easier to **review and validate public and cross-account access** before deploying permission changes |
| **Refine by removing overly broad / unused access** | **Last-accessed information** shows when AWS services were last used → identify opportunities to tighten permissions |

_(Mod 12 p48)_

### 1 · Identifying resources shared with an external entity _(Mod 12 p48)_

- Identifies resources and accounts — "such as **IAM roles** or **Amazon S3 buckets**" — that
  are shared with an external entity; helps recognise **accidental access to data and
  resources**, "which is a security risk". _(Mod 12 p48)_
- Uses **logic-based reasoning** to recognise resources shared with **external principals** and
  analyse the **resource-based policies** in the AWS environment. _(Mod 12 p48)_

**Resource types analysed** _(Mod 12 pp48–49)_:

| # | Resource type |
|---|---|
| 1 | AWS IAM roles |
| 2 | AWS Key Management Service keys |
| 3 | Amazon Simple Storage Service buckets |
| 4 | AWS Secrets Manager secrets |
| 5 | AWS Lambda functions and layers |
| 6 | Amazon Elastic Block Store volume snapshots |
| 7 | Amazon Simple Queue Service queues |
| 8 | Amazon Simple Notification Service topics |
| 9 | Amazon Relational Database Service DB snapshots |
| 10 | Amazon Relational Database Service DB cluster snapshots |
| 11 | Amazon Elastic Container Registry repositories |
| 12 | Amazon Elastic File System file systems |

### 2 · Validating policies _(Mod 12 p49)_

- Policies can be created or edited with the **AWS API, AWS CLI, or the JSON policy editor in
  the IAM console**; Access Analyzer validates the policy against **IAM policy grammar and
  best practices**. _(Mod 12 p49)_
- Findings show **security errors, warnings, suggestions, and general warnings**, each with
  **actionable recommendations**. _(Mod 12 p49)_
- "Policy validation is a security feature provided by IAM Access Analyzer, which
  **continuously monitors and reviews resources** to identify any permissions that might result
  in security risks." _(Mod 12 p49)_

### 3 · Generating policies _(Mod 12 p49)_

- Analyses **AWS CloudTrail logs** to identify the actions and services used by an **IAM entity
  (user or role)** within a **specified date range**, then generates an IAM policy from that
  access activity. _(Mod 12 p49)_
- Use the generated policy to **refine an entity's permissions** by attaching it to an **IAM
  user or role**. _(Mod 12 p49)_
- Refinement also uses the **last-used role** and **last-used access key** to update the policy
  and remove unused access. _(Mod 12 p49)_

## IAM access rules and permissions _(Mod 12 p50)_

- IAM "enables you to **control access** to AWS services and resources **securely**… It allows
  establishment of **access rules and permissions** to specific **users and applications**." _(Mod 12 p50)_
- It controls **who is authenticated (signed in)** and **who is authorized (has permissions)**
  for resource access. _(Mod 12 p50)_
- Figure 12 objects (legible) _(Mod 12 p50)_: `Account` · `Admins` (Harry, Mike) ·
  `Group: Developers` (Oliver, Jack) · `DevApp1` · `Group: Test` (George, Jacob) · `TestApp1` ·
  `Actions (Console) or Operations (API/CLI)` · `Resource-based Policies` · one truncated policy
  label (see `unresolved:`).

### IAM features list _(Mod 12 pp50–51)_

| # | Feature | Printed statement |
|---|---|---|
| 1 | Shared access to AWS account / enhanced security | Create usernames and passwords for other users/groups to delegate access to specific AWS service APIs and resources **without sharing your password or access key** |
| 2 | Granular permissions | Different permissions to different people for different resources |
| 3 | Secure access for applications on Amazon EC2 | Provide credentials for applications running on EC2 so they can access other AWS resources |
| 4 | MFA | Add two-factor authentication to your **account** and to **individual users** |
| 5 | Identity federation | Users who already have passwords elsewhere need just **one password** for on-premises and cloud work |
| 6 | Identity information for assurance | Receiving log records if you use **AWS CloudTrail** |
| 7 | **PCI DSS compliance** | Supports the information security standard PCI DSS for organizations that handle **branded credit cards from the major card schemes** |
| 8 | Integrated into AWS services | Define access controls from **one place** in the AWS Management Console, effective **throughout your AWS environment** |
| 9 | Password policy | **Reset or rotate passwords remotely**; set rules for password usage |
| 10 | **Policies and groups** | "Use IAM groups for easier permissions management and to follow IAM best practices. IAM allows organizing IAM users into IAM groups and applies a policy to that group. **Individual users still possess their credentials.**" |

_(Mod 12 pp50–51)_

Upstream: [[12-LO04a-AWS-Shared-Responsibility-Models]] · generic IAM concepts:
[[03-LO03-IAM-Authentication-Authorization]] · PCI DSS: [[02-LO02a-Regulatory-Frameworks-Laws]]







