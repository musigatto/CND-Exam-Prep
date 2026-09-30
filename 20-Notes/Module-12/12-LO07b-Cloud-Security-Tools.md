---
type: note
module: "12"
lo: "07"
tags: [tool, bestpractice, mod/12, flashcard/12]
topic: "Cloud security tools (Scout Suite, Qualys, CloudPassage Halo, Core CloudInspect) and the module summary"
exam_weight: unknown
status: done
unresolved:
  - "p312: Scout Suite receives only the two sentences quoted below. NO feature list, NO separate target/goal statement and no readable screenshot content for Scout Suite appears anywhere in pp. 312-316. The 'Features:' list that sits at the top of p313 comes AFTER 'Figure 12.207: Screenshot of Qualys Cloud Platform', so it belongs to Qualys Cloud Platform and is NOT Scout Suite's. Nothing is transferred between the two products and no Scout Suite capability is asserted beyond the printed description."
  - "pp. 312-316: the tokens 'WAF' and 'web application firewall' do not occur in the slice. The nearest printed items are CloudPassage Halo's 'Workload firewall management' (p313), its 'dynamic firewall policies' (p313) and Core CloudInspect's 'cross-site scripting' susceptibility (p314). No WAF feature is asserted for any tool."
  - "p313: the Qualys Cloud Platform 'Features:' list prints five bullets but only four are legible - 'Sensors provide continuous visibility', 'All data can be analyzed in real time', 'Respond to threats immediately', 'Visualize results in one place with AssetView'. The intervening OCR 'Active vulnerability / ICMP Timestamp Request' reads as Qualys screenshot UI (the adjacent chrome OCRs as 'Policies', '< ArnazonLif%1x', 'DemoAmazon4' and 'Environment Events Policies'). That bullet is omitted rather than guessed, so the list is transcribed as 4 legible features with one unreadable bullet - see `unresolved:` above."
  - "p312: the printed sources OCR as 'https://github.com' (Scout Suite), 'https://www.qualys.com' and 'https://www.qualys.cotn' (Qualys, twice), 'https://www.cloudpassage.com' (CloudPassage Halo), 'https://www.coresecurity.com' (Core CloudInspect), plus a stray 'https://fidelissecurity.corn/' hanging off a Qualys screenshot. The '.cotn' / '.corn' endings are read as the '.com' domain printed elsewhere on the same page and are not treated as distinct sources; the fidelissecurity URL is screenshot chrome and is not attributed to any product named in the text."
  - "p312: the Qualys provider list prints a readiness qualifier for only some clouds - Amazon Web Services (none printed) · Microsoft Azure (beta) · Google Cloud Platform (none printed) · Alibaba Cloud (early alpha) · Oracle Cloud Infrastructure (early alpha). No qualifier is supplied for AWS or GCP and none is invented."
  - "p316 CONFLICT (unrepaired): the module summary states 'AWS devised three AWS shared responsibility models for dictating the boundaries of responsibility between AWS and customers. These models include shared responsibility model for infrastructure services, shared responsibility model for container services, and shared responsibility model for abstract services.' pp. 40-43 of the SAME module present ONE AWS shared responsibility model decomposed into two control types (Inherited Controls / Shared Controls) plus a six-item customer responsibility list, and contain no infrastructure / container / abstract taxonomy at all. Both readings are preserved here and neither is reconciled. See [[12-LO04a-AWS-Shared-Responsibility-Models]]."
  - "p316: the closing paragraph OCR interleaves the cloud-provider names - 'It discussed the security features provided by cloud, and Google Cloud Platform in detail' followed by the page footer 'Page 2048 the Amazon cloud, Microsoft Azure'. The intended reading is 'It discussed the security features provided by Amazon cloud, Microsoft Azure and Google Cloud Platform in detail'; the stray 'cloud,' and the footer interleave are recorded rather than smoothed away."
  - "p316: 'compared the security features provided by major cloud service provides' - 'provides' is the printed word, not 'providers'. Reproduced as printed."
---

[[MOC-Module-12]]

# Cloud Security Tools (§12.07)

> **LO#07: Discuss general security best practices and tools for cloud security** _(Mod 12 p303)_
> The LO#07 scope statement names the tool half of the section: "…various cloud security tools such
> as **Scout Suite, Qualys Cloud Platform**." _(p303)_
> **This note = the tool half (pp. 312–316)** plus the module summary page.
> Companion: [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]] (the practices and the
> organization/provider checklists, pp. 303–311).

## Tool map — every product the courseware names, and how far each is described _(Mod 12 pp312–315)_

| Tool | One-line description as printed | Extent in the courseware |
|---|---|---|
| **Scout Suite** | "an open source multi-cloud security-auditing tool" | 2 sentences, **no feature list** _(p312)_ |
| **Qualys Cloud Platform** | "an end-to-end IT security solution" | description + provider list + 4 legible features _(pp312–313)_ |
| **CloudPassage Halo** | "a cloud server security platform" | description + **10 features** _(pp312–314)_ |
| **Core CloudInspect** | — (no one-liner; described in a paragraph) | paragraph + **6 enabled actions** _(pp314–315)_ |
| 9 further tools | — **name + URL only, no description** | p315 |

### Scout Suite _(Mod 12 p312)_

- "**Scout Suite is an open source multi-cloud security-auditing tool, which enables the security
  posture assessment of cloud environments**"
- "**Using the APIs exposed by cloud providers, Scout Suite gathers configuration data for manual
  inspection and highlights risk areas**"
- Source as printed: `https://github.com`

> The whole Scout Suite entry is these two sentences plus its source line. No targets, no goals, no
> feature list are printed for it — see `unresolved:`.

### Qualys Cloud Platform _(Mod 12 pp312–313)_

- "**Qualys Cloud Platform is an end-to-end IT security solution that provides a continuous,
  always-on assessment of the global security and compliance posture, with visibility across all
  IT assets, irrespective of their location**" _(p312, repeated in the p312 page footer)_

**"The following cloud providers are currently supported/planned:"** _(p312)_

| Provider | Readiness qualifier as printed |
|---|---|
| **Amazon Web Services** | — |
| **Microsoft Azure** | **(beta)** |
| **Google Cloud Platform** | — |
| **Alibaba Cloud** | **(early alpha)** |
| **Oracle Cloud Infrastructure** | **(early alpha)** |

**Features** _(p313, 4 legible of 5 bullets — see `unresolved:`)_

- Sensors provide continuous visibility
- All data can be analyzed in real time
- Respond to threats immediately
- Visualize results in one place with AssetView

_(Mod 12 p313)_

### CloudPassage Halo _(Mod 12 pp312–314)_

- "**CloudPassage Halo is a cloud server security platform comprising the security functions
  required to safely deploy servers in public and hybrid clouds**" _(p312)_
- "The CloudPassage Halo **software-defined security (SDSec)** platform was built to **protect
  private clouds, public IaaS, and hybrid/multi-cloud infrastructure**." _(p313)_
- "It is a **security and compliance automation technique from the development to deployment**,
  across clouds, data centers, servers, and containers, **implemented at the DevOps speed and cloud
  scale**." _(p313)_
- "It **automates and orchestrates** layered access control, vulnerability management, compromise
  prevention, compliance monitoring, and security intelligence collection." _(p313)_

**Features — all 10** _(pp313–314)_

| # | Feature | What it does, as printed |
|---|---|---|
| 1 | **Workload firewall management** | "Deploys and manages dynamic firewall policies across public, private, and hybrid cloud environments." |
| 2 | **Multifactor network authentication** | "Enables secure remote network access using two-factor authentication via SMS or uses a YubiKey with no additional software or infrastructure." |
| 3 | **Configuration security monitoring** | "Automatically monitors the OS and application configurations, processes, network services, and privileges." |
| 4 | **Software vulnerability assessment** | "Performs rapid and automatic scans for vulnerabilities in packed software across all cloud environments." |
| 5 | **File integrity monitoring** | "Protects the integrity of cloud servers by continually monitoring for unauthorized or malicious changes to essential system binaries and configuration files." |
| 6 | **Server account management** | "Determines who has accounts on which cloud servers, what privileges they operate under, and the usage of accounts." |
| 7 | **Event logging and alerting** | "Detects a broad range of events and system states and alerts when they occur." |
| 8 | **Halo REST API** | "Provides full automation of cloud deployment and integrates the security platform with other systems." |

_(Mod 12 pp313–314)_

> What Halo is, in the courseware's own words: a **cloud server security platform** · **SDSec** ·
> security **and compliance automation** · deployed at **DevOps speed and cloud scale**.

### Core CloudInspect _(Mod 12 pp314–315)_

- "**Core CloudInspect helps in validating when cloud deployment is secure and gives actionable
  remediation information when it is not.**" _(p314)_
- "The service conducts **proactive, real-world security tests using the techniques employed by
  attackers seeking to breach AWS cloud-based systems and applications**." _(p314)_

**"Core CloudInspect enables users to:"** _(pp314–315, 6 actions)_

1. Proactively verify the security of their AWS deployments against real and current attack techniques
2. Safely pinpoint and validate critical OS and services vulnerabilities with no false positives
3. Measure the susceptibilities to SQL injection, cross-site scripting, and other web-application attacks
4. Validate the security controls required by industry and government regulations
5. Get actionable information required to apply patches and implement code fixes
6. Certify systems before they go live and frequently test them to reconfirm their security position over time

_(Mod 12 pp314–315)_

### Other cloud security tools _(Mod 12 p315)_

Printed as "**Other cloud security tools include:**" — **name + URL only, no description is given
for any of them**:

| Tool as printed | URL as printed |
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

**Reading discipline:** the courseware supplies no capability, platform or licensing claim for these
nine. They are reproduced as a bare name list.

## Module Summary (p316) _(Mod 12 p316)_

The closing page, transcribed as printed:

- "**Cloud computing is an on-demand delivery of IT capabilities that provides an IT infrastructure
  and applications to subscribers as a metered service over a network.**"
- "**Cloud services are broadly divided into three categories: Infrastructure-as-a-Service (IaaS),
  Platform-as-a-Service (PaaS), and Software-as-a-Service (SaaS).**"
- "**Cloud security and compliance are the shared responsibility of the cloud provider and
  consumer.**"
- "**AWS devised three AWS shared responsibility models for dictating the boundaries of
  responsibility between AWS and customers. These models include shared responsibility model for
  infrastructure services, shared responsibility model for container services, and shared
  responsibility model for abstract services.**" ⚠ **conflicts with pp. 40–43 — see `unresolved:`**
- "**AWS IAM controls access to AWS services and resources by establishing access rules and
  permissions for specific users and applications.**"
- "**Azure IAM enables users to manage and control their identities by enabling single-sign-on,
  turning on conditional access, and enforcing multi-factor authentication.**"
- "**GCP IAM provides granular access to specific Google Cloud resources and prevents unauthorized
  access to resources.**"
- "This module described the features of enterprise cloud security. It provided insights about the
  various elements of cloud security that should be followed by an organization to secure the
  cloud. It highlighted the importance of **evaluating the CSP before consuming cloud services**
  and compared the security features provided by major cloud service provides. It discussed the
  security features provided by Amazon cloud, Microsoft Azure and Google Cloud Platform in detail."

_(Mod 12 p316)_

### The AWS three-model claim vs. what the module actually teaches

| Source | Structure presented |
|---|---|
| **p316 module summary** | **three** models — *infrastructure services* · *container services* · *abstract services* |
| **pp. 40–43 (LO#04)** | **one** model (the AWS shared responsibility model) → **two** control types (**Inherited Controls** / **Shared Controls**) → **three** shared controls (Patch Management · Configuration Management · Awareness and Training) → a **six-item** customer responsibility list |

_(Mod 12 p316 vs pp. 40–43 — see [[12-LO04a-AWS-Shared-Responsibility-Models]])_

Both are recorded; neither is repaired. Answer the three-model taxonomy only if the question cites
the summary, and the Inherited/Shared split if it cites LO#04.

## Cards

Scout Suite — the entire description the courseware gives
?
An open source multi-cloud security-auditing tool that enables the security posture assessment of cloud environments. Using the APIs exposed by cloud providers it gathers configuration data for manual inspection and highlights risk areas. Source: https://github.com

Qualys Cloud Platform — description, supported clouds, and readable features
?
An end-to-end IT security solution providing a continuous, always-on assessment of the global security and compliance posture, with visibility across all IT assets irrespective of location. Supported/planned: Amazon Web Services · Microsoft Azure (beta) · Google Cloud Platform · Alibaba Cloud (early alpha) · Oracle Cloud Infrastructure (early alpha). Features: sensors provide continuous visibility · all data can be analyzed in real time · respond to threats immediately · visualize results in one place with AssetView

CloudPassage Halo — the ten printed features
?
Workload firewall management · multifactor network authentication · configuration security monitoring · software vulnerability assessment · file integrity monitoring · server account management · event logging and alerting · Halo REST API

Core CloudInspect — what it is and what it enables
?
Validates when a cloud deployment is secure and gives actionable remediation information when it is not, using proactive real-world security tests with the techniques attackers use to breach AWS systems. Enables users to verify AWS deployments against current attack techniques · pinpoint OS and service vulnerabilities with no false positives · measure susceptibility to SQL injection, cross-site scripting and other web-application attacks · validate controls required by industry and government regulations · get actionable information to apply patches and code fixes · certify systems before they go live

The nine tools listed with no description
?
Nessus Enterprise for AWS · Symantec Cloud Workload Protection · Alert Logic · Deep Security · SecludIT · Panda Cloud Office Protection · Data Security Cloud · Cloud Application Control · Intuit Data Protection Services — the courseware prints each with a vendor URL and nothing else

What the p316 module summary claims about AWS shared responsibility
?
Three models — shared responsibility model for infrastructure services, for container services, and for abstract services. Note this conflicts with pp. 40-43, which teach one AWS model split into Inherited Controls and Shared Controls plus a six-item customer responsibility list