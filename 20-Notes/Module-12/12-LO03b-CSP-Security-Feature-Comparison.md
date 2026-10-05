---
type: note
module: "12"
lo: "03"
tags: [tool, bestpractice, mod/12]
topic: "CSP security feature comparison (AWS/Azure/GCP)"
exam_weight: unknown
status: done
unresolved:
  - "p37 Table 12.1: the OCR flattened the table into a header row plus three column reads (AWS, then AZURE, then GCP) and the counts do not reconcile — 8 readable values per provider column but only 7 feature labels (Identity and Access Management, Key Management, Network Security Check, Storage Security, Monitoring, Logging, Compliance). Positions are semantically wrong if taken as rows (e.g. 'Data Encryption for S3' lands under 'Monitoring', 'CloudHSM' under 'Compliance'). The row-to-value mapping is NOT recoverable, so only the per-column inventories are transcribed and NO feature label is bound to any value."
  - "p37: the 8th feature-label row of Table 12.1 is missing from the OCR entirely — the label text for it is unknown and is not guessed."
  - "p38 Table 12.2 'On-premise vs. Third Party Security Controls Provided by Major CSPs': the OCR is column-major and the column entry counts are wildly unequal (panel 1: ON-PREMISE 13, AWS 17, AZURE 15, GOOGLE 13, ORACLE 14, IBM 13; panel 2: 12 / 15 / 14 / 17 / 18 / 9). Row alignment is NOT recoverable, so no control is bound to any provider cell. Only the per-column inventories are transcribed."
  - "p38: 'Third Party Only' cells cannot be attributed to a specific control row. They are reproduced inline in their OCR sequence within each column, which gives a per-column count but says nothing about which control they replace."
  - "p38: the AWS entry read as 'AWS Network' is truncated in the OCR ('AWS Network Third Party Only AWS WAF') — the rest of the product name is lost and is not completed."
  - "p38: 'Virtual Network SSTP' in the AZURE column is garbled and is left unnormalized — no Azure item is asserted for it."
  - "p38: the AZURE column entry 'Microsoft Antim a [ware/ Microsoft Defender for Cloud' is OCR-split; it is rendered as 'Microsoft Antimalware / Microsoft Defender for Cloud' but it may in fact be two separate row cells. Not resolved."
  - "p38: the GOOGLE column contains 'Cloud Armor' twice, which indicates the column read is misaligned by at least one row. The duplicate is reproduced as printed rather than deduplicated."
  - "p38: product names are reproduced in the spelling the OCR gave (e.g. 'Amazon Guard Duty', 'A.zure'→'Azure', 'ExpessRoute'→'ExpressRoute', 'Al P'→'AIP'). No product name has been supplied from outside knowledge."
---

[[MOC-Module-12]]

# CSP Security Feature Comparison (§12.03)

> **LO#03 — Evaluate CSPs for security before consuming a cloud service**
> Section scope: the security features provided by AWS, Azure, and GCP; on-premise vs. third-party
> controls; closing evaluation questions _(Mod 12 p34)_

## ⚠ Read the tables column-wise, not row-wise

Both comparison tables in this note are **dense image tables** whose cell grid did not survive
OCR. Only the **column contents** are readable; the **row alignment is not**. Everything below is
therefore given as a **per-provider inventory in OCR order**. Any pairing of a feature label to a
specific vendor value would be invention — see `unresolved:`.

Context, p38 _(Mod 12 p38)_:

- On-premise security controls **are provided by cloud platforms** to ensure reliable customer
  service.
- **Third-party tools are generally required** for the security controls the CSP does **not**
  provide.
- Before any technology decision: review your **requirements** and the **existing tools** of each
  CSP using a **self-check or requirement-driven approach**.

## Table 12.1 — Security features provided by AWS, Azure, and GCP _(Mod 12 p37)_

**Feature labels printed in the table's feature column** _(7 readable, order as printed)_:
`Identity and Access Management` · `Key Management` · `Network Security Check` ·
`Storage Security` · `Monitoring` · `Logging` · `Compliance`

**Column contents** — the `#` column is **ordinal OCR read order, not the feature row**:

| # | AWS | AZURE | GCP |
|---|---|---|---|
| 1 | AWS IAM | Active Directory | Cloud IAM |
| 2 | KMS | Key Vault | Cloud KMS |
| 3 | VPC | Virtual Network, ExpressRoute | VPC |
| 4 | Trusted Advisor, Amazon Inspector | Microsoft Defender for Cloud | Cloud Security Command Center |
| 5 | Data Encryption for S3 | Storage Service Encryption (SSE) | Data Encryption Key (DEK) |
| 6 | Cloud Watch | Azure Monitor, Application insights | Google Cloud Monitoring, InfluxDB and Grafana, Google Cloud's operations suite (formerly Stackdriver) |
| 7 | CloudWatch Logs, CloudTrail | Log Analytics, Security Event Logs | Cloud Logging |
| 8 | CloudHSM | Trust Center | Cloud HSM |

_(Mod 12 p37)_

## Table 12.2 — On-premise vs. third-party security controls _(Mod 12 p38)_

Columns: **ON-PREMISE · AWS · AZURE · GOOGLE · ORACLE · IBM**

### ON-PREMISE control categories (p38, as printed)

*First panel* _(Mod 12 p38)_
`Firewall and ACLS` · `IPS/IDS` · `Web Application Firewall (WAF)` · `SIEM` ·
`Log Analytics` · `Antimalware` · `Privileged Access Management (PAM)` ·
`Data Loss Prevention (DLP)` · `Vulnerability Assessment` · `Email Protection` ·
`SSL Decryption` · `Reverse Proxy` · `Key Management`

*Second panel* _(Mod 12 p38)_
`Encryption At Rest` · `DDOS` · `MFA` · `Centralized Logging/Auditing` · `Load Balancer` ·
`LAN WAN` · `Endpoint Protection` · `Certificate Management` · `Container Security` ·
`Governance Risk and Compliance` · `Monitoring` · `Backup and Recovery`

### Per-CSP inventories — **unaligned, OCR column order**

> Read the names, not the alignment. A name on line *n* of a column is **not** the value for
> feature row *n*.

| CSP | Panel 1 — readable entries _(Mod 12 p38)_ | Panel 2 — readable entries _(Mod 12 p38)_ |
|---|---|---|
| **AWS** | AWS Security Groups · AWS Network · **Third Party Only** · AWS WAF · AWS Firewall Manager · AWS Security Hub · Amazon Guard Duty · **Third Party Only** · **Third Party Only** · Amazon Macie · Amazon Inspector · AWS Trusted Advisor · **Third Party Only** · Elastic Load Balancer · VPC Customer Gateway · AWS Transit Gateway · Key Management Service (KMS) | Elastic Block Storage · AWS Shield · IAM · AWS MFA · CloudWatch/S3 Bucket · Elastic Load Balancer/CloudFront · Virtual Private Cloud · Direct Connect · **Third Party Only** · AWS Certificate Manager · Amazon EC2 Container Service (ECS) · AWS CloudTrail · AWS Compliance Center · AWS Backup · Amazon S3 Glacier |
| **AZURE** | Network Security Groups (NSGs) · **Third Party Only** · Application Gateway · Advanced Log Analytics · Azure Monitor · Microsoft Antimalware / Microsoft Defender for Cloud · Azure AD · Privileged Identity Management · Information Protection (AIP) · Microsoft Defender for Cloud · Office Advanced Threat Protection · Application Gateway · Virtual Network · `SSTP` *(garbled, unresolved)* · Key Vault | Storage Encryption for Data at Rest · Built-in DDOS defense · Azure Active Directory · Azure Active Directory · Azure Audit Logs · Azure Load Balancer · Virtual Network · ExpressRoute/MPLS · Microsoft Defender ATP · **Third Party Only** · Azure Container Service (ACS) · Azure Policy · Azure Backup · Azure Site Recovery |
| **GOOGLE** | Cloud Armor · VPC Firewall · **Third Party Only** · Cloud Armor · Google Cloud's operations Suite (monitoring / logging) · **Third Party Only** · **Third Party Only** · Cloud Data Loss Prevention API · Cloud Security Scanner · Various controls embedded in G-suite · HTTPS Load Balancing · Google VPN · Cloud Key Management Service | Part of Google Cloud Platform · Cloud Armor · Cloud Identity · Cloud IAM · Security Key Enforcement · VPC Flow Logs · Access Transparency · Cloud Load Balancing · HTTPS Load Balancing · VPC Network · Dedicated interconnects · **Third Party Only** · **Third Party Only** · Kubernetes Engine · Cloud Security Command Center · Object Versioning · Cloud Storage Nearline |
| **ORACLE** | VCN Security Lists · **Third Party Only** · Oracle Dyn WAF · Oracle Security Monitoring and Analytics · **Third Party Only** · **Third Party Only** · **Third Party Only** · Security Vulnerability Assessment Service · **Third Party Only** · **Third Party Only** · Dynamic Routing Gateway (DRG) · Cloud Infrastructure Key Management · **Third Party Only** · Cloud Internet Services | Cloud Infrastructure Block Volume · Built-in DDOS defense · Oracle Cloud Infrastructure IAM · Oracle Cloud Infrastructure IAM · Oracle Cloud Infrastructure Audit · Cloud Infrastructure Load Balancing · Virtual Cloud Network (VCN) · FastConnect · **Third Party Only** · **Third Party Only** · Oracle Container Services · **Third Party Only** · Archive Storage · Hyper Protect Crypto Services · Cloud Internet Services · Cloud IAM · APP ID · App ID |
| **IBM** | Log Analysis · Cloud Activity Tracker · **Third Party Only** · **Third Party Only** · **Third Party Only** · Cloud Security Advisor · Vulnerability Advisor · **Third Party Only** · Cloud Load Balancer · IPsec VPN · Secure Gateway · Key protect · Cloud Security | Log Analysis with LogDNA · Cloud Load Balancer · VLANS · Direct Link · **Third Party Only** · Certificate Manager · Containers-Trusted Compute · **Third Party Only** · IBM Cloud Backup |

_(Mod 12 p38)_

> The same gap is re-opened on p38 with a second panel; treat both panels as name inventories only.

## Closing evaluation questions _(Mod 12 p39)_

1. **How many security tools** are currently required in the organization?
2. **What risks** can the security tools reduce/address?
3. **Rationalize the existing security vendors and tools.**

_(Mod 12 p39)_

Decision rules that close the LO _(Mod 12 p39)_:

- **Match requirements against the solutions the cloud vendor offers** → an effective technology
  decision on provider selection.
- **Ensure third-party products can be integrated with the cloud platform.**
- **Combine** the third-party controls **with** the security controls provided by the CSP.

Upstream: [[12-LO03a-CSP-Landscape-and-Evaluation]]






