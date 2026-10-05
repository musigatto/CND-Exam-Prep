---
type: moc
module: "12"
tags: [concept, mod/12]
topic: "Module 12 — Enterprise Cloud Network Security"
exam_weight: unknown
status: done
unresolved:
  - "MAJOR INTERNAL CONTRADICTION — AWS shared responsibility models. PDF p316 (book p2048) module summary states: 'AWS devised THREE AWS shared responsibility models for dictating the boundaries of responsibility between AWS and customers. These models include shared responsibility model for infrastructure services, shared responsibility model for container services, and shared responsibility model for abstract services.' But pp.41-43 (book 1773-1775), the module's own AWS section, present ONE model decomposed into TWO control types — Inherited Controls and Shared Controls — and none of the three terms 'infrastructure services / container services / abstract services' occurs anywhere in that page range. The courseware never reconciles the two. Both readings are preserved as printed; neither is treated as authoritative. Carried in [[12-LO04a-AWS-Shared-Responsibility-Models]] and [[12-LO07b-Cloud-Security-Tools]]."
  - "PDF p303 (book p2035) LO#07 objective statement announces 'the use of Cloud Access Security Broker (CASB) solutions to secure the cloud environment', but NO CASB content exists anywhere in pp.303-316 — not a definition, a vendor, or a capability. Announced-but-never-covered; recorded, not supplied from outside knowledge."
  - "PDF p3 (book p1735) LO#03 objective line drops its subject: it reads 'Evaluate for security before consuming a doud service' with no object, whereas the p34 (book p1766) section header reads 'Evaluate CSPs for Security Before Consuming a Cloud Service'. The section header supplies the missing object; the p3 line is reproduced as printed."
  - "PDF p316 (book p2048) summary paragraph carries a column-wrap defect — 'It discussed the security features provided by cloud, and Google Cloud Platform in detail' — the word 'Amazon' is displaced by the OCR column order. The same paragraph prints 'cloud service provides' for 'providers'. Both are the PDF's own defects, reproduced not corrected."
  - "Per-module exam blueprint weights are not stated in the courseware. Module 12 sits in domain 5 'Enterprise Virtual, Cloud, and Wireless Network Protection' (15%, 15 of 100 questions) shared with modules 11 and 13 — see [[Exam-Facts]]. The bank uses a flat 5 items per module."
---

[[MOC-Module-11]]

# Module 12 — Enterprise Cloud Network Security

> [!abstract] Scope
> **7 LOs** (this module has 7, not 9) · PDF pp. 4–316 (book pp. 1736–2048) · **316 pages, the
> largest module in the course** · 51 notes · 293 cards.
> Cloud computing fundamentals (12 characteristics, 30 benefits, service + deployment models,
> NIST reference architecture) → cloud security insights (shared responsibility, data, network,
> monitoring/logging/compliance) → **evaluating a CSP** → **AWS** (116 pp) → **Azure** (89 pp) →
> **GCP** (58 pp) → general best practices, NIST recommendations, compliance checklists, tools.
> The spine is *cloud fundamentals → shared responsibility → how each of the three hyperscalers
> actually implements it (IAM → encryption → network → monitoring)*, then the cross-provider
> checklists and tools.
> **Note the shape trap:** the three provider LOs (LO04/05/06) are near-parallel in structure
> but are *not* interchangeable — each provider's IAM, encryption and network primitives have
> different names, different boundaries and different stated behaviours.

## Sections
| LO   | §    | Section                                                     | PDF pp. | Book pp.   | Notes |
| ---- | ---- | ----------------------------------------------------------- | ------- | ---------- | ----- |
| LO01 | 12.1 | Cloud Computing Fundamentals                                | 4–19    | 1736–1751  | 4 |
| LO02 | 12.2 | Cloud Security Insights                                     | 20–33   | 1752–1765  | 3 |
| LO03 | 12.3 | Evaluate CSPs for Security Before Consuming a Cloud Service  | 34–39   | 1766–1771  | 2 |
| LO04 | 12.4 | Security in Amazon Cloud (AWS)                              | 40–155  | 1772–1887  | 14 |
| LO05 | 12.5 | Security in Microsoft Azure Cloud                           | 156–244 | 1888–1976  | 15 |
| LO06 | 12.6 | Security in Google Cloud Platform (GCP)                     | 245–302 | 1977–2034  | 11 |
| LO07 | 12.7 | General Security Best Practices and Tools for Cloud Security | 303–316 | 2035–2048  | 2 |

## Technical focus

- **LO01 cloud computing fundamentals:** def = "on-demand delivery of IT capabilities where the IT infrastructure and applications are provided to subscribers as a **metered service over a network**". **12 characteristics** in printed order: on-demand self service · distributed storage · broad network access · rapid elasticity · automated management · resource pooling · measured service · virtualization technology · multi-tenancy · resilient computing · flexible pricing models · sustainability. **Benefits = 30 items in 4 groups**: Economic 8 · Operational 7 · Staffing 7 · Security 8. **Limitations**: limited control/flexibility · prone to outage and technical issues · security/privacy/compliance issues · contracts and lock-in · dependence on network connections. **Service delivery models** IaaS/PaaS/SaaS with a per-model responsibility split. **Deployment models** public / private / community / hybrid + **multi-cloud**. **NIST reference architecture — the five significant actors are: cloud consumer · cloud provider · cloud carrier · cloud auditor · cloud broker** (the broker's three service categories = **service intermediation / service aggregation / service arbitrage**). SLA: the *consumer* specifies QoS, security and remedies; the CSP may add limitations and obligations. → [[12-LO01a-Cloud-Computing-Fundamentals]] [[12-LO01b-Cloud-Service-Delivery-Models]] [[12-LO01c-Cloud-Deployment-Models]] [[12-LO01d-NIST-Cloud-Reference-Architecture]]

- **LO02 cloud security insights:** the *measures* do not change, the *focus* does. Shared-responsibility boundary **shifts per service model** (IaaS customer-heavy → SaaS provider-heavy). Consumer-side elements include **IAM** and the identity lifecycle. Data storage security, testing cloud data security, and cloud network security challenges (chiefly **lack of network visibility** in monitoring/management). **Monitoring** → thresholds/rules, alert the data owner, one platform to report all data. **Logging** → threat detection, data analysis, compliance audits. Plus compliance. → [[12-LO02a-Cloud-Security-Shared-Responsibility]] [[12-LO02b-Cloud-Data-and-Network-Security]] [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

- **LO03 evaluate a CSP:** the **CSP market-share figures and provider names** (p35), then **gap analysis** — assess your own security capabilities against the provider's *before* consuming the service. Then two comparison tables: **Table 12.1** AWS/Azure/GCP security-feature comparison and **Table 12.2** on-premise vs third-party security controls. Read those tables **column-wise, not row-wise** — they are provider columns. → [[12-LO03a-CSP-Landscape-and-Evaluation]] [[12-LO03b-CSP-Security-Feature-Comparison]]

- **LO04 AWS (116 pp — the largest LO):** shared responsibility = **one model, two control types** — **Inherited Controls** (inherited completely from AWS, e.g. physical/environmental) and **Shared Controls** (applied to both layers with separate perspectives: **patch management · configuration management · awareness and training**); **six** customer responsibility items. **IAM** is the bulk of the LO: **IAM Identity Center** (formerly AWS Single Sign-On) · **IAM Access Analyzer** (generate policy from CloudTrail events, up to **90 days**; validate policy) · **3 policy types** (AWS-managed / customer-managed / inline) · **5 access levels** (List · Read · Write · Permissions management · Tagging) · **3 AWS-managed policy classes** (Full access, Power user, Partial access) · **3 policy summary tables** · **4 IAM MFA methods** (**FIDO security keys · virtual authenticator apps · TOTP hardware tokens · TOTP hardware tokens for AWS GovCloud (US) Regions**) · **roles for EC2** via instance profile · credential rotation with the **Access Key Last Used** attribute · **SAML session tags for ABAC** · policy **conditions** · **service-linked roles** and the **permissions boundary**. **Encryption — three data-at-rest models**: **A** customer manages encryption + key storage + key management · **B** AWS provides key storage (**CloudHSM**, keys inaccessible to AWS employees), customer supplies the KMI and manages algorithm + key management over **SSL** · **C** AWS provides everything (**transparent server-side encryption**). **S3 SSE: SSE-S3 / SSE-KMS / SSE-C** (SSE-S3 = 256-bit AES with a master key; SSE-KMS = CMKs in AWS KMS, and the response **ETag is not the MD5** of the object). **Client-side encryption** (S3 encryption client, Java/C# crypto API, OpenSSL, Bouncy Castle), **ACM** (certificate types, CloudFront **Default vs Custom SSL certificate**; Default requires browsers to support **TLSv1 or later**). **Network:** VPC · **security groups (stateful, instance/subnet level)** vs **network ACLs (stateless, subnet level)** · VPC peering · **VPG** / **Internet Gateway** · EC2-Classic vs EC2-VPC · Regions / Availability Zones / Local Zones / **GovCloud** / **Direct Connect** / DMZ. **DDoS** mitigation · S3 + EBS storage security · **Amazon Macie** data classification. **Amazon Inspector** · AWS security checklist. → [[12-LO04a-AWS-Shared-Responsibility-Models]] [[12-LO04b-AWS-IAM-Features]] [[12-LO04c-AWS-IAM-Roles-and-Best-Practices]] [[12-LO04d-AWS-IAM-Users-and-Groups]] [[12-LO04e-AWS-Least-Privilege-and-Policy-Types]] [[12-LO04f-AWS-Password-Policy-and-MFA]] [[12-LO04g-AWS-EC2-Roles-Credential-Rotation-and-Delegation]] [[12-LO04h-AWS-ABAC-and-Policy-Conditions]] [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]] [[12-LO04j-AWS-Encryption-Data-at-Rest]] [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]] [[12-LO04l-AWS-VPC-and-Network-Security]] [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]] [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]

- **LO05 Azure (89 pp):** shared responsibility model (physical hosts/network/data retained by the provider). **Identity:** SSO + **Seamless SSO** · **Conditional Access** · **SSPR** · **Azure AD password protection** (banned-password lists pushed to on-prem AD FS agents) · **Security Defaults** · **RBAC** with scopes **subscription / resource group / resource** and principals **user, group, service principal, managed identity** · **PIM** (eligibility, activation, MFA, justification, notifications) · **emergency access accounts** (at least two) · **Microsoft Authenticator** passwordless phone sign-in · **PAW** · **AD FS** · **password hash synchronization**. **Encryption:** data encryption models · **Azure Key Vault** (RSA key sizes) · **SSE** · **TDE** · in transit (**HTTPS/SSL**, **Site-to-Site vs Point-to-Site VPN**, IPsec). **Network:** SSL inbound to VMs · **endpoint ACLs** · **disable direct RDP/SSH** · load balancing — the courseware says **external/internal** (it never says "public") and prints **no Layer 4/7 distinction** · **Application Gateway** · **Azure Firewall** · **Azure WAF** · **NSGs** (default rules "cannot be deleted, but can be overruled"). **Microsoft Antimalware** (the courseware names **no PowerShell cmdlet**). **Azure network architecture + production network** (circuits among data centers owned by Microsoft; only select internal nodes reach the firewall; VMs blocked inbound and outbound at creation). **Active geo-replication** (the slide says "Windows Azure Storage", the body and walkthrough say **Azure SQL Database** — both preserved). **Monitoring:** Table 12.4 **8 log types** · **Microsoft Defender for Cloud** · **Activity Log** (no retention/export fact is stated) · **Network Watcher** (a *regional* service). **Azure security checklist = 19 body items** (18 on the slide; the slide is identity/guest-only). → [[12-LO05a-Azure-Shared-Responsibility-Model]] [[12-LO05b-Azure-AD-SSO-and-Conditional-Access]] [[12-LO05c-Azure-Password-Management-and-MFA]] [[12-LO05d-Azure-RBAC]] [[12-LO05e-Azure-Privileged-Identity-Management]] [[12-LO05f-Azure-Centralized-Identity-and-Password-Hash-Sync]] [[12-LO05g-Azure-Encryption-Data-at-Rest]] [[12-LO05h-Azure-Encryption-in-Transit]] [[12-LO05i-Azure-Inbound-Access-Control]] [[12-LO05j-Azure-Load-Balancing]] [[12-LO05k-Azure-Firewall-and-Network-Security-Groups]] [[12-LO05l-Azure-Antimalware-and-Network-Architecture]] [[12-LO05m-Azure-Network-Best-Practices-and-Geo-Replication]] [[12-LO05n-Azure-Monitoring-Logging-and-Compliance]] [[12-LO05o-Azure-Security-Checklist]]

- **LO06 GCP (58 pp):** shared responsibility; **GCP IAM gives granular access to specific Google Cloud resources**. **Service account** = "a special account that belongs to an application or VM instance, **but not to end-user**". Permission format **`<service>.<resource>.<verb>`** (e.g. `pubsub.subscriptions.consume`), correlating one-to-one with REST API methods. **Fine-grained vs project-level grants** (project-level is inherited by all resources). **The 8 GCP IAM best practices**: grant least privileges to avoid primitive roles · create separate service account · check granted policy on each resource · restrict who acts as service accounts · **rotate service account keys** · restrict access to create and manage service accounts · grant predefined roles · **use logging roles for log auditing**. **Two key types** — **GCP-managed** (cannot be downloaded or automatically rotated; used within two weeks; App Engine / Compute Engine) and **user-managed** (create/download/manage; expire after ten years). Automatic vs manual rotation. **Organization policies** with **hierarchical inheritance** (`Inherit parent's policy`). **Predefined roles** for granular access; **custom roles**; **logging roles**. **Encryption:** Google encrypts by default; **Cloud KMS**; key hierarchy **Project → Location → Key Ring → Key → Key version**; **envelope encryption** (KEK in KMS). **Network:** defense-in-depth (**enforce WAF policies at the edge**, **utilize VPC**, micro-segmentation) · **Shared VPC** to centralize control · **firewall rules** · **routes**. **DDoS** — GCP infrastructure mitigates DoS by default. **Monitoring/logging/compliance:** GCP Logging console · **Cloud Audit Logs** (3 types) · **Operation Suite** · compliance standards · **Google security checklist = 18 items**. → [[12-LO06a-GCP-Shared-Responsibility-and-IAM]] [[12-LO06b-GCP-Service-Accounts]] [[12-LO06c-GCP-IAM-Security-Best-Practices]] [[12-LO06d-GCP-Primitive-Roles-and-Separate-Service-Accounts]] [[12-LO06e-GCP-Service-Account-Key-Rotation]] [[12-LO06f-GCP-Organization-Policies]] [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]] [[12-LO06h-GCP-Encryption-and-Cloud-KMS]] [[12-LO06i-GCP-Defense-in-Depth-and-VPC]] [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]] [[12-LO06k-GCP-Monitoring-Logging-and-Compliance]]

- **LO07 general best practices and tools:** **34 best practices** printed as four unnumbered blocks (the courseware never numbers or totals them) — data/key/lifecycle, identity/authentication/credentials, vendor/SLA/supply chain, transparency/logging/disclosure, perimeter/infrastructure, API and interface surface, breach handling. High-yield singles: **AICPA SAS 70 Type II audits** · **SLAs for patching and vulnerability remediation** · **prohibit user credential sharing** · **disclose infrastructure information, security patching, and firewall details** · **physical security 24 — 7 — 365** · **IDS, IPS and firewall** · **delete data from the primary servers along with replicas on disposal** · **SSL for sensitive transmission** · **SLA minimum uptime and penalties**. **7 NIST recommendations**, including **renew SLAs if security gaps are found** and **determine who is responsible for data privacy**. **Compliance checklists** — Tables **12.6** (Operations 17 items + Technology 8 items), **12.7/12.8** (Management 9 items) plus an unnumbered security-team checklist; all two-column **Organization | Provider** tables whose column assignment did not survive OCR. **Tools:** **Scout Suite** (open source, multi-cloud, uses provider APIs to gather configuration data) · **Qualys Cloud Platform** (end-to-end, always-on posture; providers listed as *supported/planned* with **Azure = beta**, **Alibaba Cloud and OCI = early alpha**) · **CloudPassage Halo** (SDSec; 8 features incl. workload firewall management, multifactor network authentication via **SMS or YubiKey**, file integrity monitoring, **Halo REST API**) · **Core CloudInspect** (AWS-only; validates real attack techniques, no false positives, SQL injection / XSS susceptibility, and can **certify systems before they go live**); plus **9 further tools named with URLs and no description**. → [[12-LO07a-Cloud-Security-Best-Practices-and-Compliance]] [[12-LO07b-Cloud-Security-Tools]]

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware → `exam_weight: unknown`. Module 12 sits in blueprint domain 5 **Enterprise Virtual, Cloud, and Wireless Network Protection = 15%** (15 of 100) shared with modules 11 and 13 — see [[Exam-Facts]]. The bank uses a **flat 5 per module**.
- Strong question sources, in rough order of yield:
  - **The five NIST actors** — consumer, provider, **carrier**, **auditor**, **broker** — and the broker's **intermediation / aggregation / arbitrage**.
  - **12 characteristics** and **30 benefits in 4 groups (Economic 8 · Operational 7 · Staffing 7 · Security 8)**.
  - **The AWS three data-at-rest models A/B/C** — who manages encryption, algorithm and key management in each; and **SSE-S3 / SSE-KMS / SSE-C**.
  - **The four IAM MFA methods**, including the **AWS GovCloud (US)** variant; and the two response styles (typed code vs tap-and-complete).
  - **Five IAM access levels** (List/Read/Write/Permissions management/Tagging) and the **three policy types**.
  - **Azure RBAC scopes** (subscription / resource group / resource) and the four principals (user, group, service principal, managed identity).
  - **Azure says "external/internal"** for load balancers — **not** "public" — and prints **no L4/L7 distinction**.
  - **GCP permission format** `<service>.<resource>.<verb>` and the **two service-account key types** with **two weeks** / **ten years**.
  - **GCP key hierarchy**: Project → Location → Key Ring → Key → Key version, with **envelope encryption** (KEK in KMS).
  - **CloudPassage Halo's two MFA methods** — **SMS or YubiKey, no additional software**.
  - **Qualys provider maturity labels** — Azure *beta*, Alibaba Cloud and OCI *early alpha*.
  - **Seven NIST recommendations**, especially **renewing SLAs on a gap**.
  - **Checklist items that read as trivia but are printed**: **AICPA SAS 70 Type II**, **UK Data Protection Act**, **24/7 CSP support**, **shadow IT**, **data disposal including replicas**.
- Deliberate distractors to expect:
  - **"AWS has three shared responsibility models"** — p316 says three; **pp. 41–43 say one model with two control types**. Both are printed; the courseware never reconciles them.
  - **Confusing the three providers' IAM primitives** — e.g. Azure RBAC vs AWS IAM policies vs GCP IAM roles; all three are "role/permission"-shaped but the *objects* differ.
  - **Treating the Azure checklist as covering the whole cloud** — it is **identity/guest-only**.
  - **Assuming Core CloudInspect is multi-cloud** — the courseware scopes it to **AWS only**.
  - **Inventing a CASB section** — LO07 announces CASB and never delivers it.
  - **Assuming "public" load balancer** — Azure load balancers are printed as **external/internal**.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-12")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/12-enterprise-cloud-network-security-map.canvas|Enterprise Cloud Network Security Map]]
- Flow to visualize: cloud computing definition → 12 characteristics → 30 benefits (4 groups) → service delivery models (IaaS/PaaS/SaaS + responsibility split) → deployment models (public/private/community/hybrid/multi-cloud) → NIST reference architecture (5 actors + separation of responsibilities) → **shared responsibility** and how the boundary moves per model → data/network security → monitoring/logging/compliance → **evaluate the CSP** (gap analysis + feature comparison) → then three near-parallel provider trunks: **AWS** (shared responsibility → IAM → encryption → VPC → DDoS/storage/classification → monitoring/Inspector/checklist) · **Azure** (shared responsibility → identity/RBAC/PIM → encryption → network perimeter → antimalware/architecture → monitoring/checklist) · **GCP** (shared responsibility → IAM/service accounts → roles/policies → KMS → VPC/firewall/routes/DDoS → logging/compliance/checklist) → converge on **best practices + NIST recommendations + compliance checklists + tools**.

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]] · [[Exam-Facts]]
- Related modules: [[MOC-Module-11]] (enterprise virtual — same blueprint domain 5) · [[MOC-Module-13]] (enterprise wireless — same domain 5) · [[MOC-Module-05]] (Windows — AD FS / AD / BitLocker / PowerShell lineage used by LO05) · [[MOC-Module-06]] (Linux — OpenSSL, the crypto stack used by LO04k) · [[MOC-Module-03]] (technical network security — VPC/ACL/TLS fundamentals reused in LO04l) · [[MOC-Module-10]] (data security — encryption at rest and key management that LO04j/LO05g/LO06h instantiate per cloud) · [[MOC-Module-09]] (application security — WAF and API security referenced by LO06i and LO04h) · [[MOC-Module-08]] (incident detection — logging/monitoring threads picked up in LO02c, LO05n, LO06k).

## Unresolved
- **AWS shared responsibility: p316 says three models, pp. 41–43 say one model with two control types** (see frontmatter — the module's biggest internal contradiction).
- **CASB announced on p303, never covered** (see frontmatter).
- **p3 LO#03 objective line drops its subject**; the p34 section header supplies it (see frontmatter).
- **p316 summary column-wrap defect and "cloud service provides" typo** (see frontmatter).
- Per-module blueprint weights are not in the courseware; domain weights come from [[Exam-Facts]].
- **Azure geo-replication:** p230 slide says "Windows Azure Storage", body and walkthrough say **Azure SQL Database**. Both preserved, not reconciled.
- **Azure load balancing:** pp. 208–212 print **no Layer 4/Layer 7 distinction** and never the word "public" for a load balancer. Neither is asserted.
- **Azure Antimalware:** pp. 221–222 name **no PowerShell cmdlet**; the label "Using Antimalware PowerShell cmdlets" is all that is printed.
- **Azure Activity Log:** **no retention period and no export setting** is printed anywhere in pp. 239–240.
- **GCP service account scope:** p249 says *project-level grants* are inherited by all project resources; the blanket-access claim in the module appears only on p258 and refers to *all resources of the service account*. Kept distinct, not merged.
- **GCP key rotation scope:** the section and every bullet say *service account* keys, but both demonstrated rotation methods use `gcloud kms keys …` (Cloud KMS). Unreconciled. Also p262 says GCP-managed keys "cannot be … automatically rotated" while p263 presents an "Automatic key rotation" method.
- **GCP roles:** p255 states "Cloud IAM roles are of **three** types" but defines only **Primitive**; the other two type names are not printed in the LO. Not supplied.
- **GCP org policy constraint name differs between figure and body on p264** (`…disableServiceAccountCreation` vs `…disableServiceAccountKeyCreation`). Both printed.
- **gcloud commands in LO06h/LO06e have unreadable flags** — reproduced with `<flag>` placeholders and explicitly **not** copy-pasteable.
- **OCR gaps, all recorded in the individual notes:** this module is screenshot-heavy. Figure cells that did not OCR include the AWS shared-responsibility grid, the AWS encryption-model figure (Fig 12.62), the IAM policy tables, the CSP comparison tables (Table 12.1/12.2), the Azure shared-responsibility grid, the Azure Firewall/NSG blades, the GCP shared-responsibility grid (p246), the GCP network-controls diagram (Fig 12.192), and all three tool dashboards (Figs 12.207–12.209). Console values, ARNs, account IDs and menu paths were transcribed only where legible.
- **Two fabrications were caught and removed during verification** and are recorded in the notes that previously carried them: the CloudFront example domain `d111111abcdef8.cloudfront.net` (p129 OCRs as `C.Cloudfront net)`) and a GCP button label `Skip now` (absent from all 316 pages). `TLSv1` was *kept* — p129 OCRs it as `TLSvI`.

## Quick review

How many learning objectives does module 12 have, and how long is the PDF
?
Seven — not nine. 316 pages (book 1736–2048), the largest module in the course: AWS 116 pp, Azure 89 pp, GCP 58 pp

The five significant actors in the NIST cloud reference architecture
?
Cloud consumer · Cloud provider · Cloud carrier · cloud auditor · cloud broker

The three service categories a cloud broker provides
?
Service intermediation (improves a given function, value-added) · Service aggregation (combines multiple services into new services) · Service arbitrage (like aggregation but the services are not fixed)

The three AWS data-at-rest encryption models
?
Model A — the customer manages the encryption, key storage and key management · Model B — AWS provides the key storage layer (CloudHSM, keys inaccessible to AWS employees), the customer provides the KMI and manages the encryption algorithm and key management over SSL · Model C — AWS provides key storage, algorithm and key management (transparent server-side encryption)

The three Amazon S3 server-side encryption options
?
SSE-S3 — Amazon S3-managed keys, 256-bit AES with a master key · SSE-KMS — CMKs in AWS Key Management Service, and the response ETag is not the MD5 of the object · SSE-C — customer-provided keys, never stored by S3

The four IAM MFA methods as listed in the courseware
?
FIDO security keys · virtual authenticator apps · TOTP hardware tokens · TOTP hardware tokens for the AWS GovCloud (US) Regions

The two GCP service account key types and their stated lifetimes
?
GCP-managed keys — cannot be downloaded or automatically rotated, used within two weeks, used by services such as App Engine and Compute Engine · User-managed keys — the user creates, downloads and manages them and they expire after ten years

GCP permission format, with an example
?
<service>.<resource>.<verb> — e.g. pubsub.subscriptions.consume; calling topics.publish() needs pubsub.topics.publish, and permissions correlate one-to-one with REST API methods

The GCP Cloud KMS key hierarchy
?
Project → Location → Key Ring → Key → Key version, with envelope encryption and the KEK stored in KMS

Azure RBAC scopes and the four security principals
?
Scopes: subscription, resource group, resource · Principals: user, group, service principal, managed identity

Which of the four cloud security tools the courseware scopes to AWS only
?
Core CloudInspect — it proactively verifies AWS deployments against real and current attack techniques, pinpoints OS and services vulnerabilities with no false positives, and can certify systems before they go live

Which two audit and vendor items appear verbatim among the cloud best practices
?
Vendors should regularly undergo AICPA SAS 70 Type II audits · Enforce SLAs for patching and vulnerability remediation

The NIST recommendation that turns on the SLA itself
?
Renew SLAs if security gaps are found between the security requirements of the organization and the standards of the cloud provider