---
type: note
module: "12"
lo: "04"
tags: [bestpractice, policy, mod/12]
topic: "AWS IAM permissions, roles, best practices, root keys"
exam_weight: unknown
status: done
unresolved:
  - "pp57 (MFA): the fourth device type OCR's as 'IJ2F device' in the figure and 'IJ2F security keys' in the body. The token is not resolvable from the slice and is left un-normalised; the enablement rule is quoted with the token as printed."
  - "p57 password symbol set: the printed list of permitted symbols reads '! @ # $ % & * () <> [l I ...\"+-=' - the characters between the brackets are OCR noise. Only the unambiguous symbols are transcribed."
  - "p49: the figure/loop labels 'Set or Grant organization's fine-grained permissions', 'Verify', 'Refine', 'Refine by removing overly broad access' appear as a caption band rather than as a single readable statement; they are reproduced as the three lifecycle steps and not expanded."
  - "p56/p57: the delete/rotate walkthrough ends at 'Manage access keys in the Access keys section' - no further step, and no console field names beyond that, are printed. Nothing about the console screen is reconstructed here."
---

[[MOC-Module-12]]

# AWS IAM Roles and Best Practices (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · area 2 of 6: **AWS IAM features and best
> practice to implement IAM securely** _(Mod 12 p40)_
> Covers pp. 52–57: manage IAM permissions (p52) · manage IAM roles (p53) · access workloads
> within AWS (p54) · IAM security best practices (p55) · lock the root user access keys (pp56–57).

## Manage IAM permissions _(Mod 12 p52)_

- IAM "allows implementing **fine-grained access control** by establishing permissions that
  specify access control to specific AWS resources… help safeguard your AWS resources to
  achieve **least-privilege**." _(Mod 12 p52)_
- "Using policies, you can define **who** has access to your AWS resources." Policies are
  attached to **IAM roles** in your accounts **and to your AWS resources** — they work
  together. _(Mod 12 p52)_
- "**IAM approves each AWS request by matching it to your policies and allowing or denying the
  request.**" The IAM expresses access requirements with granularity using **JSON**. _(Mod 12 p52)_

| Mechanism | Printed statement |
|---|---|
| **Preventive guardrails** | Define the **maximum permissions** allowed for your IAM roles |
| — the three limiters | **Service control policies · permission boundaries · session policies** — "To limit the permissions that are granted to an IAM role" |
| **Attribute-based access control (ABAC)** | Fine-grained permissions based on **IAM role parameters such as departments and job roles**; "you do not have to update policies for each new resource that is going to be added in the future" |

_(Mod 12 p52)_

Figure 12.6: ABAC spans **Identities · Permissions · Resources**. _(Mod 12 p52)_

## Manage IAM roles _(Mod 12 p53)_

> "AWS IAM roles are **entities that you define and provide specific permissions to**, allowing
> **trusted identities such as workforce identities and applications** to conduct actions in
> AWS." _(Mod 12 p53)_

- "Using IAM roles is a **security best practice since they provide temporary credentials that
  need not be rotated**." _(Mod 12 p53)_
- Use IAM roles "to provide users **temporary credentials that are not required to be
  rotated**". _(Mod 12 p53)_

### The five role scenarios _(Mod 12 pp53–54)_

| Scenario | Printed statement |
|---|---|
| **Federate workforce identities into AWS** | "With IAM roles, while accessing AWS accounts you can specify the permissions user should have" |
| **Access workloads within AWS** | "Workload is an **application that requires an identity to make requests to AWS services**. Workloads running in the AWS compute environment can access resources with **temporary credentials instead of managing long-term credentials**" |
| **Access workloads that run outside of AWS** | "Use **IAM Roles Anywhere**, which gives temporary access to AWS resources for applications that are outside of AWS" |
| **Enable cross-account access** | "IAM roles provide access to your identities in **one AWS account** to access resources on **another AWS account**" |
| **Grant access to AWS services** | "IAM defines a **role for the service on your behalf** to perform actions in AWS account when you set up an AWS service environment. The **service role performs only those actions that are specified**" |

_(Mod 12 pp53–54)_

## AWS IAM security best practices — all 14 _(Mod 12 p55)_

| # | Best practice |
|---|---|
| 1 | **Lock your AWS Account Root User Access Keys** |
| 2 | **Create Individual IAM Users** |
| 3 | **Use Groups to Assign Permissions to IAM Users** |
| 4 | **Grant Least Privilege** |
| 5 | **Use AWS-Managed Policies** |
| 6 | **Use Customer-Managed Policies instead of Inline Policies** |
| 7 | **Use Access Levels to Review IAM Permissions** |
| 8 | **Configure a Strong Password Policy for Users** |
| 9 | **Use Roles for Amazon EC2 Instances** |
| 10 | **Rotate Security Credentials Regularly** |
| 11 | **Use Roles to Delegate Permissions and Do Not Share Access Keys** |
| 12 | **Remove Unnecessary Credentials** |
| 13 | **Use Policy Conditions for Extra Security** |
| 14 | **Monitor Activity in AWS Account** |

_(Mod 12 p55)_

## Lock your AWS account root user access keys _(Mod 12 pp56–57)_

**What an access key is.** "The access key (an **access key ID** and **secret access key**)
allows making **programmatic requests** to AWS." _(Mod 12 p56)_

**Why root keys are dangerous — stated rules, not console steps** _(Mod 12 p56)_:

- The root user access key "can provide **full access to all your resources for all AWS
  services**" and "**You cannot reduce the permissions** associated with your AWS account root
  user access key."
- "Because they grant **complete access to all of the resources for all AWS services, including
  personal billing information, we **do not advise creating access keys for the root user**."
- "**Use a different user than root for routine activities**"; use root only for actions that
  **can only be performed by the root user**.
- "**Temporary credentials should be used instead of long-term credentials** such as access
  keys whenever possible."
- "If there is a need for IAM users with programmatic access and long-term credentials,
  **access keys should be rotated**."

### To protect the root user access key _(Mod 12 p56)_

- Do not create AWS root user account access keys **unless required** or if you do not have
  it already. _(Mod 12 p56)_
- Change the root access key **regularly** or **delete it** if you already have one. _(Mod 12 p56)_
- **Never share** the AWS root user account password or access keys — "to avoid having to
  **embed them in an application**". _(Mod 12 p57)_
- Use **strong passwords** for logging into the AWS Management Console. _(Mod 12 p57)_
- **Enable AWS MFA** on the root user account. _(p56–57)_
- Root credentials: "keep them secure, **just like any credit card information or any other
  private information**"; "protect the root user credentials in the same way as you protect
  other sensitive personal data" — set up **MFA**. _(Mod 12 p56)_

### AWS password requirements (stated rules) _(Mod 12 p57)_

- Minimum **8** characters, maximum **128** characters.
- Must include **a minimum of three** of the following mix of character types: **uppercase,
  lowercase, numbers**, and the symbol set `! @ # $ % & * ( ) < > [ ] … +-=`.
- Must **not** be identical to the AWS **account name or email address**.

## MFA — stated rules _(Mod 12 p57)_

- "You can enable **only one MFA device per AWS account root user or IAM user**." _(Mod 12 p57)_
- Device types listed: **Virtual MFA device** · **Hardware-based MFA device** · **Mobile
  phone** — plus one further type whose name did not OCR (see `unresolved:`). _(Mod 12 p57)_

| Principal / device | Where MFA may be enabled |
|---|---|
| IAM users with **virtual or hardware** MFA devices | AWS Management Console, **AWS CLI, or the IAM API** |
| IAM users with the `IJ2F` device or a **mobile phone receiving SMS text messages** | AWS Management Console **only** |
| **AWS account root users**, any MFA device type **except SMS MFA** | AWS Management Console **only** |

_(Mod 12 p57)_

Upstream: [[12-LO04b-AWS-IAM-Features]] · practice application:
[[12-LO04e-AWS-Least-Privilege-and-Policy-Types]]







