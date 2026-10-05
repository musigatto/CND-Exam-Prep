---
type: note
module: "12"
lo: "07"
tags: [tool, bestpractice, mod/12]
topic: "Cloud security tools (Scout Suite, Qualys, CloudPassage Halo, Core CloudInspect)"
exam_weight: unknown
status: done
unresolved:
  - "CROSS-MODULE CONTRADICTION, p316 vs pp41-43: the p316 module summary states 'AWS devised THREE AWS shared responsibility models for dictating the boundaries of responsibility ... These models include shared responsibility model for infrastructure services, shared responsibility model for container services, and shared responsibility model for abstract services.' pp.41-43 of this same module present ONE model (the AWS shared responsibility model) decomposed into TWO control types - Inherited Controls and Shared Controls - and NONE of the three terms 'infrastructure services / container services / abstract services' appears anywhere in that page range. The courseware never reconciles the two. Both readings are reproduced as printed; neither is treated as authoritative. See [[12-LO04a-AWS-Shared-Responsibility-Models]]."
  - "p316 summary paragraph carries a column-wrap defect: 'It discussed the security features provided by cloud, and Google Cloud Platform in detail.' The word 'Amazon' is displaced out of place by the OCR column order, so the intended three-provider list is not recoverable as written. The defective line is reproduced below and is NOT silently repaired. p316 also prints 'cloud service provides' (for 'providers') - the PDF's own typo, recorded not corrected."
  - "p313 Qualys Cloud Platform feature list has 5 bullets but the 4th is TRUNCATED mid-phrase in the source: 'Active vulnerability' - the feature name is incomplete. It is reproduced as printed and is NOT completed to 'Active vulnerability scanning' or any other expansion."
  - "Figures 12.207 (Qualys Cloud Platform), 12.208 (CloudPassage Halo) and 12.209 (Core CloudInspect) are dashboard screenshots whose contents did not OCR beyond garbled instance IDs, EC2 type strings and button labels. NO feature, capability or value is read from any of them - every claim above comes from the body prose."
  - "p315 'Other cloud security tools include:' lists 9 tools with vendor URLs and NO description of any of them. Nothing is asserted here about what those 9 tools do - their capability is not supplied from outside knowledge."
  - "No support matrix exists for Scout Suite, CloudPassage Halo or Core CloudInspect. Only Qualys carries an explicit provider list (p312) and that list is qualified as 'currently supported/planned' with maturity labels (beta / early alpha) that are reproduced verbatim. Do not generalise the Qualys list to the other tools."
---

[[MOC-Module-12]]

# Cloud Security Tools (§12.07)

> **LO#07: Discuss general security best practices and tools for cloud security** _(Mod 12 p303)_
> Covers pp. 312–316. Four tools are described in prose; nine further tools are named without
> description. Best practices and checklists are in
> [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]].

## Scout Suite _(Mod 12 p312)_

- "an **open source multi-cloud security-auditing tool**, which enables the **security posture
  assessment** of cloud environments"
- "**Using the APIs exposed by cloud providers**, Scout Suite **gathers configuration data for
  manual inspection** and **highlights risk areas**"
- Source as printed: `https://github.com`

_(Mod 12 p312)_ — the courseware gives Scout Suite **no feature list at all**; only the two
statements above.

## Qualys Cloud Platform _(Mod 12 pp312–313)_

- "an **end-to-end IT security solution** that provides a **continuous, always-on assessment**
  of the **global security and compliance posture**, with visibility across **all IT assets,
  irrespective of their location**"

_(Mod 12 p312)_

### Providers currently supported / planned _(Mod 12 p312)_

Printed with an explicit maturity caveat — "The following cloud providers are currently
**supported/planned**":

| Provider | Maturity as printed |
|---|---|
| Amazon Web Services | _(no label)_ |
| Microsoft Azure | **beta** |
| Google Cloud Platform | _(no label)_ |
| Alibaba Cloud | **early alpha** |
| Oracle Cloud Infrastructure | **early alpha** |

_(Mod 12 p312)_

### Features _(Mod 12 p313)_

- **Sensors provide continuous visibility**
- **All data can be analyzed in real time**
- **Respond to threats immediately**
- **Active vulnerability** _(truncated in the source — see `unresolved:`)_
- **Visualize results in one place with AssetView**

_(Mod 12 p313)_

## CloudPassage Halo _(Mod 12 pp312–314)_

- p312: "a **cloud server security platform** comprising the security functions required to
  **safely deploy servers in public and hybrid clouds**"
- p313: "The CloudPassage Halo **software-defined security (SDSec) platform** was built to
  protect **private clouds, public IaaS, and hybrid/multi-cloud infrastructure**. It is a
  security and compliance **automation technique from the development to deployment**, across
  clouds, data centers, servers, and containers, implemented at the **DevOps speed and cloud
  scale**. It **automates and orchestrates** layered access control, vulnerability management,
  compromise prevention, compliance monitoring, and security intelligence collection."
- Source as printed: `https://www.cloudpassage.com`

_(Mod 12 pp312–313)_

### Features _(Mod 12 pp313–314)_

| Feature | As printed |
|---|---|
| **Workload firewall management** | Deploys and manages **dynamic firewall policies** across public, private, and hybrid cloud environments |
| **Multifactor network authentication** | Enables secure remote network access using **two-factor authentication via SMS** or uses a **YubiKey** with no additional software or infrastructure |
| **Configuration security monitoring** | Automatically monitors the **OS and application configurations, processes, network services, and privileges** |
| **Software vulnerability assessment** | Performs rapid and automatic scans for vulnerabilities in **packed software** across all cloud environments |
| **File integrity monitoring** | Protects the integrity of cloud servers by continually monitoring for unauthorized or malicious changes to **essential system binaries and configuration files** |
| **Server account management** | Determines **who has accounts on which cloud servers, what privileges they operate under, and the usage of accounts** |
| **Event logging and alerting** | Detects a broad range of events and system states and **alerts when they occur** |
| **Halo REST API** | Provides **full automation of cloud deployment** and integrates the security platform with other systems |

_(Mod 12 pp313–314)_ — 8 features.

## Core CloudInspect _(Mod 12 pp314–315)_

OCR renders the name as "Core Cloudlnspect" throughout (lowercase l for capital I); read as
**Core CloudInspect**.

- "helps in **validating when cloud deployment is secure** and gives **actionable remediation
  information** when it is not. The service conducts **proactive, real-world security tests**
  using the techniques employed by **attackers seeking to breach AWS cloud-based systems and
  applications**"
- Source as printed: `https://www.coresecurity.com`

_(Mod 12 p314)_

### What it enables users to do _(Mod 12 pp314–315)_

1. Proactively verify the security of their **AWS deployments** against real and current attack
   techniques
2. Safely pinpoint and validate **critical OS and services vulnerabilities with no false
   positives**
3. Measure the susceptibilities to **SQL injection, cross-site scripting**, and other
   web-application attacks
4. Validate the **security controls required by industry and government regulations**
5. Get **actionable information required to apply patches and implement code fixes**
6. **Certify systems before they go live** and frequently test them to reconfirm their security
   position over time

_(Mod 12 pp314–315)_ — Core CloudInspect is the only tool of the four the courseware scopes
explicitly to **AWS**.

## Other cloud security tools _(Mod 12 p315)_

"Other cloud security tools include:" — nine tools, **URL only, no description**:

| Tool | URL as printed |
|---|---|
| Nessus Enterprise for AWS | `https://www.tenable.com` |
| Symantec Cloud Workload Protection | `https://www.symantec.com` |
| Alert Logic | `https://www.alertlogic.com` |
| Deep Security | `https://www.trendmicro.com` |
| SecludIT | `https://secludit.com` |
| Panda Cloud Office Protection | `https://www.pandasecurity.com` |
| Data Security Cloud | `https://www.informatica.com` |
| Cloud Application Control | `https://www.zscaler.com` |
| Intuit Data Protection Services | `https://security.intuit.com` |

_(Mod 12 p315)_

## Module summary _(Mod 12 p316)_

Printed as seven statements plus a closing paragraph:

1. "Cloud computing is an **on-demand delivery of IT capabilities** that provides an IT
   infrastructure and applications to subscribers as a **metered service over a network**"
   — cf. [[12-LO01a-Cloud-Computing-Fundamentals]]
2. "Cloud services are broadly divided into **three categories: IaaS, PaaS, and SaaS**"
   — cf. [[12-LO01b-Cloud-Service-Delivery-Models]]
3. "Cloud security and compliance are the **shared responsibility of the cloud provider and
   consumer**" — cf. [[12-LO02a-Cloud-Security-Shared-Responsibility]]
4. "AWS devised **three** AWS shared responsibility models … infrastructure services, container
   services, and abstract services" — **contradicts pp. 41–43; see `unresolved:`**
5. "AWS IAM controls access to AWS services and resources by **establishing access rules and
   permissions** for specific users and applications" — cf. [[12-LO04b-AWS-IAM-Features]]
6. "Azure IAM enables users to manage and control their identities by enabling
   **single-sign-on, turning on conditional access, and enforcing multi-factor
   authentication**" — cf. [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]]
7. "GCP IAM provides **granular access to specific Google Cloud resources** and prevents
   unauthorized access to resources" — cf. [[12-LO06a-GCP-Shared-Responsibility-and-IAM]]

Closing paragraph as printed: "This module described the features of enterprise cloud security.
It provided insights about the various elements of cloud security that should be followed by an
organization to secure the cloud. It highlighted the importance of **evaluating the CSP before
consuming cloud services** and compared the security features provided by major cloud service
provides. It discussed the security features provided by cloud, and Google Cloud Platform in
detail." _(Mod 12 p316)_ — reproduced with the PDF's own column-wrap defect and typo intact; see
`unresolved:`.






