---
type: note
module: "12"
lo: "07"
tags: [bestpractice, policy, mod/12, flashcard/12]
topic: "Cloud security best practices, NIST recommendations, org/provider compliance checklists"
exam_weight: unknown
status: done
unresolved:
  - "p303: the LO#07 scope statement announces 'It explains the use of Cloud Access Security Broker (CASB) solutions to secure the cloud environment', but no CASB text, definition, or vendor appears anywhere in pp. 304-316. CASB is recorded here only as an announced scope item, never expanded."
  - "pp. 305-306 print a SECOND, near-duplicate rendering of the p304-305 'Best Practices for Securing Cloud' figure with wording variants (see the delta table). The p304-305 figure reading is used as canonical here and both readings are kept; the courseware does not reconcile them. The variant 'is a 24 x 7 x 365 affair' (p305) against 'is implemented 24 x 7 x 365' (p304) is reproduced as printed - 'affair' is not corrected or resolved."
  - "p307: the section is titled 'NIST Recommendations for Cloud Security' but the slice prints no NIST publication number, document title, or standard reference. Only the bare label 'NIST' is asserted; no specific NIST document is attributed."
  - "p307: the figure and the body print the same 7 recommendations with different wording - the last one reads 'Determine who is responsible for data privacy and security issues in the cloud' (figure) vs 'Enquire about who is responsible for the data privacy and security issues in the cloud' (body); also 'Ensure audit procedures' vs 'Ensure effective audit procedures', and 'deployment model' vs 'deployment models'. Both readings are preserved; neither is treated as a correction."
  - "p308: an UNNUMBERED two-column figure headed 'Organization/Provider Cloud Security Compliance' (section label 'Management', columns 'Organization | Provider') carries 9 rows that are the same Management set that reappears numbered as Table 12.8 on pp. 310-311. The p308 figure prints no table number and no 'Checklist to Determine...' caption, so it is treated here as the un-numbered Management rendering, not as a separate checklist."
  - "p310: 'Do the procurement processes contain cloud security requirements?' sits alone at the top of p310, above the 'Table 12.6: Checklist to Determine if the Organization/Provider is Fit for Cloud Security Based on its Operations' caption. It is assigned to Table 12.6 as the continuation of the p309 Operations list on the caption-below-table layout used throughout pp. 308-311; the page geometry makes this an inference, not a printed row label."
  - "Table 12.6 row 14 is printed as 'Has the CSP has implemented perimeter security controls...' - a doubled auxiliary verb in the courseware. Reproduced as printed, not corrected."
  - "pp. 308-311: the checklist tables are headed only 'Organization' and 'Provider' (and 'Security Checklist | Team' for Table 12.5). The courseware never marks which rows are asked of the organization and which of the provider, so no row is assigned to one side or the other in this note."
---

[[MOC-Module-12]]

# Cloud Security Best Practices and Compliance (§12.07)

> **LO#07: Discuss general security best practices and tools for cloud security** _(Mod 12 p303)_
> Section heading as printed: "**General Security Best Practices and Tools for Cloud Security**".
>
> Scope statement, verbatim: "The objective of this section is to explain various security
> best practices and tools used by enterprises for cloud security. This section explains the
> **NIST recommendations** for cloud security and various cloud security tools such as
> **Scout Suite, Qualys Cloud Platform**. It explains the use of **Cloud Access Security Broker
> (CASB)** solutions to secure the cloud environment." _(Mod 12 p303)_
>
> **This note = the non-tool half (pp. 303–311).** The tools and the p316 module summary are in
> [[12-LO07b-Cloud-Security-Tools]].
> Related: [[12-LO02a-Cloud-Security-Shared-Responsibility]] (the compliance split this page set
> operationalises) · [[12-LO03a-CSP-Landscape-and-Evaluation]] (evaluating the provider).

## Best practices for securing the cloud — all 34, verbatim and in printed order _(Mod 12 pp304–305)_

### Block 1 — "Best Practices for Securing Cloud" (12) _(p304)_

1. Enforce data protection, backup, and retention mechanisms
2. Enforce SLAs for patching and vulnerability remediation
3. Vendors should regularly undergo AICPA SAS 70 Type II audits
4. Verify one's own cloud in public domain blacklists
5. Enforce legal contracts in the employee behavior policy
6. Prohibit user credential sharing among users, applications, and services
7. Implement strong authentication, authorization, and auditing mechanisms
8. Check for data protection in both the design and during runtime
9. Implement strong key generation, storage and management, and destruction practices
10. Monitor the client traffic for any malicious activities
11. Prevent unauthorized server access using security checkpoints
12. Disclose applicable logs and data to customers

### Block 2 — "Best Practices for Securing Cloud (Cont'd)" (12) _(p304)_

13. Analyze cloud provider security policies and SLAs
14. Assess the security of cloud APIs and log the customer network traffic
15. Ensure that the cloud undergoes regular security checks and updates
16. Ensure that physical security is implemented 24 x 7 x 365
17. Enforce security standards during installation/configuration
18. Ensure that the memory, storage, and network access is isolated
19. Leverage strong two-factor authentication techniques where possible
20. Baseline the security breach notification process
21. Analyze the API dependency chain software modules
22. Enforce stringent registration and validation processes
23. Perform vulnerability and configuration risk assessment
24. Disclose infrastructure information, security patching, and firewall details

### Block 3 — "Best Practices for Securing Cloud (Cont'd)" (5) _(p305)_

25. Enforce stringent cloud security compliance, SCM (Software Configuration Management), and management practice transparency
26. Employ security devices such as IDS, IPS, and firewall to guard and stop unauthorized access to the data stored in the cloud
27. Enforce strict supply chain management and conduct a comprehensive supplier assessment
28. Enforce stringent security policies and procedures such as access control policy, information security management policy, and contract policy
29. Ensure infrastructure security through proper management and monitoring, availability, secure VM separation, and service assurance

### Block 4 — "Best Practices for Securing Cloud" (5) _(p305)_

30. Use VPNs to secure the client data and ensure the complete deletion of data from the main servers along with its replicas when requested for data disposal
31. Ensure Secure Sockets Layer (SSL) is used for sensitive and confidential data transmission
32. Analyze the security model of cloud provider interfaces
33. Understand the terms and conditions in SLA such as minimum level of uptime and penalties in case of failure to adhere to the agreed level
34. Enforce basic information security practices, namely strong password policy, physical security, device security, encryption, data security, and network security.

### Thematic index _(grouping is this note's; wording and numbering above are as printed)_

| Theme | Items |
|---|---|
| **Data protection & lifecycle** | 1, 8, 9, 12, 30 |
| **Contract, SLA, vendor due diligence** | 2, 3, 5, 13, 27, 33 |
| **Identity, access, authentication** | 6, 7, 19, 22, 31 |
| **Isolation & physical security** | 16, 17, 18, 29 |
| **Infrastructure & API surface** | 14, 15, 21, 26, 32 |
| **Monitoring, detection, breach handling** | 10, 11, 20, 23 |
| **Governance, compliance, policy** | 24, 25, 28, 34 |

### The second rendering (pp. 305–306) — wording deltas only

The same 34 practices are printed a second time across pp. 305–306. Only the items that
**change wording** are listed; every other item is word-for-word identical in both renderings.

| # | Figure reading (pp. 304–305) | Body reading (pp. 305–306) |
|---|---|---|
| 4 | "Verify one's **own** cloud in public domain blacklists" | "Verify one's cloud in public domain blacklists" |
| 5 | "in **the** employee behavior **policy**" | "in employee behavior **policies**" |
| 7 | "Implement **strong** authentication, authorization, and auditing mechanisms" | "Implement **secure** authentication, authorization, and auditing mechanisms" |
| 8 | "in **both the** design and **during** runtime" | "**during** design and runtime" |
| 16 | "physical security **is implemented** 24 x 7 x 365" | "physical security **is a 24 x 7 x 365 affair**" |
| 18 | "memory, storage, and network access **is** isolated" | "…**are** isolated" |
| 20 | "Baseline **the** security breach notification process" | "Baseline security breach notification process" |
| 21 | "Analyze **the** API dependency chain software modules" | "Analyze API dependency chain software modules" |
| 24 | "Disclose … firewall details" | "…firewall details **to customers**" |
| 28 | "such as **access control** policy" | "such as **the access control** policy" |
| 30 | "complete deletion of data from the **main** servers along with **its** replicas" | "the data are completely deleted from the **primary** servers along with **their** replicas" |
| 31 | "**Secure Sockets Layer (SSL) is used** for …" | "Ensure **the use of SSL** for …" |

_(Mod 12 pp. 304–306)_

## NIST Recommendations for Cloud Security — all 7 _(Mod 12 p307)_

1. Assess risks posed to client data, software, and infrastructure
2. Select appropriate deployment model according to the requirements
3. Ensure audit procedures for data protection and software isolation
4. Renew SLAs if security gaps are found between the security requirements of an organization and the standards of the cloud provider
5. Establish appropriate incident detection and reporting mechanisms
6. Analyze the security objectives of the organization
7. Determine who is responsible for data privacy and security issues in the cloud

_(Mod 12 p307, figure)_

**Same list, body rendering (p307)** — deltas only: 1 "Assess **the** risks posed to **the** client
data…" · 2 "deployment **models**" · 3 "Ensure **effective** audit procedures" · 4 "of the
organization **and** standards of the cloud provider" · 7 "**Enquire about** who is responsible for
**the** data privacy and security issues in the cloud".

**Reading order (this note's):** *assess → select model → audit → renew SLAs → detect/report →
re-check objectives → assign the privacy/security owner.* The courseware does not number the list
or link it to the checklists below; the cross-reference is this note's — recommendations 3 (audit
procedures), 4 (renew SLAs) and 7 (who owns data privacy/security) are the three that map onto the
Table 12.5 / 12.6 / 12.8 rows on pp. 308–311.

## Organization/Provider Cloud Security Compliance — the four checklists _(Mod 12 pp308–311)_

Lead-in, verbatim: "Given below are checklists for determining whether the **security team**, the
**rest of the organization**, and any **proposed cloud provider** can ensure cloud security."
_(p308)_

| Table | Caption as printed | Rows | Page |
|---|---|---|---|
| **12.5** | Checklist to Determine if the **Security Team** is Fit for Cloud Security | 8 | p308 |
| **12.6** | …if the Organization/Provider is Fit for Cloud Security Based on its **Operations** | 18 | pp309–310 |
| **12.7** | …Based on its **Technology** | 8 | p310 |
| **12.8** | …Based on its **Management** | 9 | pp310–311 |

### Table 12.5 — Security Team (8) _(p308)_

| # | Question as printed |
|---|---|
| 1 | Are the members of the security team formally trained in cloud technologies? |
| 2 | Do the organization security policies consider the cloud infrastructure? |
| 3 | Has the security team ever been involved in the implementation of the cloud infrastructure? |
| 4 | Has the organization defined security assessment procedures for the cloud infrastructure? |
| 5 | Has the organization ever been audited for cloud security threats? |
| 6 | Does the adoption of cloud by the organization complies with the security standards that the organization follows? |
| 7 | Has security governance been adapted to include the cloud? |
| 8 | Does the team have adequate resources to implement the cloud infrastructure and security? |

### Table 12.6 — Operations (18) _(pp309–310)_

| # | Question as printed |
|---|---|
| 1 | Are regulatory compliance reports, audit reports, and reporting information available from the provider? |
| 2 | Are the organization's incident handling and business continuity policies and procedures designed considering cloud security issues? |
| 3 | Are the cloud service provider's compliance and audit reports accessible to the organization? |
| 4 | Does the CSP SLA addresses incident handling and business continuity concerns? |
| 5 | Does the CSP have clear policies and procedures to handle digital evidence in the cloud infrastructure? |
| 6 | Is the CSP compliant with the industry standards? |
| 7 | Does the CSP have skilled and sufficient staff for incident resolution and configuration management? |
| 8 | Does the CSP have defined procedures to support the organization in the case of incidents involving several clients in a multi-tenant environment? |
| 9 | Does the use of a cloud provider give the organization an environmental advantage? |
| 10 | Does the organization know the application or database in which each data entity is stored or mastered? |
| 11 | Is the cloud-based application maintained and disaster tolerant (i.e., would it recover from an internal or externally caused disaster)? |
| 12 | Are all personnel appropriately vetted, monitored, and supervised? |
| 13 | Does the CSP provide flexibility of service relocation and switchovers? |
| 14 | Has the CSP has implemented perimeter security controls such as IDS and firewalls, and does it provide regular activity logs to the organization? |
| 15 | Does the CSP provide reasonable assurance of quality or availability of service? |
| 16 | Is it easy to securely integrate the cloud-based applications at runtime and contract termination? |
| 17 | Does the CSP provide 24/7 support for cloud operations and security-related issues? |
| 18 | Do the procurement processes contain cloud security requirements? |

### Table 12.7 — Technology (8) _(p310)_

| # | Question as printed |
|---|---|
| 1 | Are there appropriate access controls (e.g., federated SSO) that give users controlled access to cloud applications? |
| 2 | Is data separation maintained between the organization and customer information at runtime and during backup (including data disposal)? |
| 3 | Has the organization considered and addressed backup, recovery, archiving and decommissioning of data stored in a cloud environment? |
| 4 | Have mechanisms been established for authentication, authorization, and key management in a cloud environment? |
| 5 | Are mechanisms in place to manage network congestion, misconnection, misconfiguration, and lack of resource isolation, which affect the services and security? |
| 6 | Has the organization implemented sufficient security controls on the client devices used to access the cloud? |
| 7 | Are all cloud-based systems, infrastructure, and physical locations suitably protected? |
| 8 | Are the network designs suitably secure for the organization's cloud adoption strategy? |

### Table 12.8 — Management (9) _(pp310–311)_

| # | Question as printed | Variant on the p308 figure |
|---|---|---|
| 1 | Is everyone aware of their cloud security responsibilities? | — |
| 2 | Is there a mechanism for assessing the security of a cloud service? | — |
| 3 | Does business governance mitigate the security risks **that can result from** cloud-based "shadow IT"? | "…**arising from** cloud-based 'shadow IT'" |
| 4 | Does the organization know the jurisdictions within which its data can reside? | — |
| 5 | Is there a mechanism for managing cloud-related risks? | — |
| 6 | Does the organization understand the data architecture **required** to operate with appropriate security at all levels? | "…**needed** to operate…" |
| 7 | Can the organization be confident **regarding** end-to-end service continuity across several cloud service providers? | "Can the organization be confident **of** end-to-end…" |
| 8 | Does the provider comply with all relevant industry standards (e.g., the UK Data Protection Act)? | — |
| 9 | Does the compliance function understand the specific regulatory issues **related to the adoption of cloud services by an organization**? | "…**pertaining to the organization's adoption of cloud services**" |

_(Mod 12 pp308–311 — Table 12.8 rows 3, 6, 7 and 9 have variant wording on the un-numbered p308
figure; both readings are printed by the courseware)_

### The un-numbered p308 Management figure (9)

The figure headed "**Organization/Provider Cloud Security Compliance**" (section label
"**Management**", with two column headers **Organization** and **Provider**) prints the same nine
rows as Table 12.8 in the same order, with the wording variants in the right-hand column above. It
carries **no table number** — see `unresolved:`.

_(Mod 12 p308)_

### How the four checklists divide the work

| Table | Axis | Anchor nouns the courseware uses |
|---|---|---|
| **12.5 Security Team** | people + skills | formally trained · policies · implementation involvement · assessment procedures · audited · governance adapted · resources |
| **12.6 Operations** | run + prove | compliance/audit reports · incident handling · business continuity · **digital evidence** · **multi-tenant** · vetting · **service relocation and switchovers** · perimeter IDS/firewalls · **24/7 support** · procurement |
| **12.7 Technology** | controls in place | **federated SSO** · data separation at runtime and backup · key management · **network congestion, misconnection, misconfiguration, lack of resource isolation** · client devices · physical locations · network design |
| **12.8 Management** | govern + locate | responsibilities · **shadow IT** · **jurisdictions where data can reside** · end-to-end continuity · **UK Data Protection Act** · compliance function |

_(Mod 12 pp308–311; the mapping of questions to themes is this note's)_

**The most distinctive rows** _(all printed verbatim above)_: Table 12.6 #5 *policies and procedures
to handle digital evidence in the cloud infrastructure* · Table 12.6 #8 *incidents involving several
clients in a multi-tenant environment* · Table 12.6 #13 *flexibility of service relocation and
switchovers* · Table 12.8 #4 *the jurisdictions within which its data can reside*. The courseware
assigns no weight to any row.

## Cards

The seven NIST recommendations for cloud security
?
Assess risks posed to client data, software, and infrastructure · select appropriate deployment model according to the requirements · ensure audit procedures for data protection and software isolation · renew SLAs if security gaps are found between the security requirements of an organization and the standards of the cloud provider · establish appropriate incident detection and reporting mechanisms · analyze the security objectives of the organization · determine who is responsible for data privacy and security issues in the cloud

The four organization/provider compliance checklists and their axes
?
Table 12.5 Security Team (8 rows, p308) · Table 12.6 Operations (18 rows, pp309-310) · Table 12.7 Technology (8 rows, p310) · Table 12.8 Management (9 rows, pp310-311)

Table 12.6 — the operational rows about forensics, multi-tenancy and exit
?
Does the CSP have clear policies and procedures to handle digital evidence in the cloud infrastructure · does the CSP have defined procedures to support the organization in the case of incidents involving several clients in a multi-tenant environment · does the CSP provide flexibility of service relocation and switchovers · does the CSP provide 24/7 support for cloud operations and security-related issues

Table 12.7 — the four failure modes of cloud network design
?
Network congestion · misconnection · misconfiguration · lack of resource isolation. Plus: appropriate access controls such as federated SSO, data separation between the organization and customer information at runtime and during backup including data disposal, and authentication/authorization/key management mechanisms in a cloud environment

Table 12.8 — the governance rows
?
Is everyone aware of their cloud security responsibilities · is there a mechanism for assessing the security of a cloud service · does business governance mitigate the security risks from cloud-based "shadow IT" · does the organization know the jurisdictions within which its data can reside · is there a mechanism for managing cloud-related risks · does the organization understand the data architecture required to operate with appropriate security at all levels · can the organization be confident regarding end-to-end service continuity across several cloud service providers · does the provider comply with all relevant industry standards such as the UK Data Protection Act · does the compliance function understand the specific regulatory issues related to the adoption of cloud services

Five best practices that target identity and access
?
Prohibit user credential sharing among users, applications, and services · implement strong authentication, authorization, and auditing mechanisms · leverage strong two-factor authentication techniques where possible · enforce stringent registration and validation processes · use VPNs to secure the client data