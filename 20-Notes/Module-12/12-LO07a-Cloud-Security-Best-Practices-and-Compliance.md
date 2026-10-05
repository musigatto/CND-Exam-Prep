---
type: note
module: "12"
lo: "07"
tags: [bestpractice, policy, mod/12]
topic: "Cloud security best practices, NIST recommendations, compliance checklists"
exam_weight: unknown
status: done
unresolved:
  - "p303 LO OBJECTIVE ANNOUNCES A TOPIC THAT IS NEVER COVERED: the LO#07 objective statement says 'It explains the use of Cloud Access Security Broker (CASB) solutions to secure the cloud environment.' No CASB content exists anywhere in pp.303-316 - not a definition, not a vendor, not a capability. CASB is therefore named here as announced-but-uncovered and is NOT expanded from outside knowledge."
  - "p308 'Checklist to determine if the security team is fit for cloud security' (Team / Organization columns) IS TRUNCATED in the OCR at 2000 characters, mid-8th item: 'Does the team have adequate resources to implement the clou...'. Only the first seven items plus that fragment are readable; any items after it are omitted rather than reconstructed."
  - "TABLE CAPTION GARBLE: p310 prints 'Table 12.7: Checklist to Determine if the Organization/Provider is Fit for Cloud Security Based on its Technology Management' - one caption merging what should be two (12.7 Technology, 12.8 Management). Only three numbered captions are legible in the range: Table 12.6 (Operations + Technology), Table 12.7, Table 12.8 (Management). The p308 management list carries NO table number. No numbering is asserted here beyond those three."
  - "COLUMN ASSIGNMENT IS UNRECOVERABLE: Tables 12.6/12.7/12.8 are two-column (Organization | Provider) tables whose shaded cell assignments did not OCR - the OCR flattened both columns into one question stream. Every checklist question below is therefore reproduced as TEXT with no assertion about which column it belongs to."
  - "p310 'Do the procurement processes contain cloud security requirements?' appears BEFORE the Table 12.6 caption and above the Technology list, with no column header attached. Its table (Technology vs Operations) cannot be determined; reproduced as printed."
  - "SLIDE/BODY WORDING DRIFT across the best-practices list (both readings kept, not merged): 'Implement strong authentication, authorization, and auditing mechanisms' (p304 slide) vs '...secure...' (p305 body); 'Check for data protection in both the design and during runtime' (p304) vs '...during design and runtime' (p305); 'Verify one's own cloud in public domain blacklists' (p304/p306) vs 'Verify one's cloud...' (p305); 'Enforce legal contracts in the employee behavior policy' (p304) vs '...in employee behavior policies' (p305); 'Ensure Secure Sockets Layer (SSL) is used' (p305) vs 'Ensure the use of SSL' (p306); 'complete deletion of data from the main servers' (p305) vs 'the data are completely deleted from the primary servers' (p306)."
  - "NIST list drift on p307: 'Ensure audit procedures for data protection and software isolation' (slide) vs 'Ensure EFFECTIVE audit procedures...' (body); 'Select appropriate deployment MODEL' (slide) vs 'deployment MODELS' (body); 'Determine who is responsible for data privacy and security issues in the cloud' (slide) vs 'ENQUIRE about who is responsible...' (body)."
  - "p308 vs pp310-311: the nine Management questions are printed twice with drift - 'mitigate the security risks ARISING FROM cloud-based shadow IT' (p308) vs 'the security risks THAT CAN RESULT FROM cloud-based shadow IT' (p310); 'the data architecture NEEDED TO operate with appropriate security at all levels' (p308) vs 'the data architecture REQUIRED TO operate...' (p310)."
  - "THE 34-ITEM COUNT IS EDITORIAL: the courseware prints the best-practices list as four unnumbered blocks (p304 slide, p304 'Cont'd' slide, p305 slide, p305 running prose) and then restates the whole thing a fifth time as running prose on p306. The source never numbers or totals them; 34 is this note's de-duplication of the four printed blocks, not a courseware figure."
---

[[MOC-Module-12]]

# Cloud Security Best Practices, NIST Recommendations, Compliance Checklists (§12.07)

> **LO#07: Discuss general security best practices and tools for cloud security** _(Mod 12 p303)_
> Section header as printed: "LO#OZ: General Security Best Practices and Tools for Cloud
> Security" (`LO#OZ` = `LO#07`).
> Covers pp. 303–311. Objective statement: "This section explains the NIST recommendations
> for cloud security and various cloud security tools such as **Scout Suite**, **Qualys Cloud
> Platform**. It explains the use of **Cloud Access Security Broker (CASB)** solutions to secure
> the cloud environment." _(Mod 12 p303)_ — see `unresolved:` for CASB.

## Best practices for securing the cloud — the four printed blocks _(Mod 12 pp304–305)_

The courseware prints an unnumbered, ungrouped list across four blocks. Reordered by theme
below; **the grouping is editorial** — see `unresolved:`.

### Data, key, and lifecycle handling

- Enforce data protection, backup, and retention mechanisms _(Mod 12 p304)_
- Check for data protection in both the design and during runtime _(Mod 12 p304)_
- Implement strong key generation, storage and management, and destruction practices _(Mod 12 p304)_
- Use VPNs to secure the client data and ensure the **complete deletion of data from the main
  servers along with its replicas when requested for data disposal** _(Mod 12 p305)_
- Perform vulnerability and configuration risk assessment _(Mod 12 p305)_

### Identity, authentication, credentials

- Prohibit user credential sharing among users, applications, and services _(Mod 12 p304)_
- Implement strong authentication, authorization, and auditing mechanisms _(Mod 12 p304)_
- Leverage strong two-factor authentication techniques where possible _(Mod 12 p305)_
- Enforce basic information security practices, namely strong password policy, physical
  security, device security, encryption, data security, and network security _(Mod 12 p305)_
- Enforce stringent registration and validation processes _(Mod 12 p305)_

### Vendor, SLA, and supply chain

- Enforce SLAs for **patching and vulnerability remediation** _(Mod 12 p304)_
- **Vendors should regularly undergo AICPA SAS 70 Type II audits** _(Mod 12 p304)_
- Enforce strict supply chain management and conduct a comprehensive supplier assessment _(Mod 12 p305)_
- Enforce stringent cloud security compliance, **SCM (Software Configuration Management)**, and
  management practice transparency _(Mod 12 p305)_
- Understand the terms and conditions in SLA such as **minimum level of uptime and penalties in
  case of failure to adhere to the agreed level** _(Mod 12 p305)_
- Enforce stringent security policies and procedures such as access control policy, information
  security management policy, and contract policy _(Mod 12 p305)_

### Transparency, logging, and disclosure

- Disclose applicable logs and data to customers _(Mod 12 p304)_
- Disclose infrastructure information, security patching, and firewall details _(Mod 12 p305)_
- Monitor the client traffic for any malicious activities _(Mod 12 p304)_
- Analyze cloud provider security policies and SLAs _(Mod 12 p305)_

### Perimeter and infrastructure

- Prevent unauthorized server access using **security checkpoints** _(Mod 12 p304)_
- Employ security devices such as **IDS, IPS, and firewall** to guard and stop unauthorized
  access to the data stored in the cloud _(Mod 12 p305)_
- Ensure infrastructure security through proper management and monitoring, availability, secure
  VM separation, and service assurance _(Mod 12 p305)_
- Ensure that the cloud undergoes regular security checks and updates _(Mod 12 p305)_
- Ensure that physical security is implemented **24 — 7 — 365** _(Mod 12 p305)_
- Enforce security standards during installation/configuration _(Mod 12 p305)_
- Ensure that the memory, storage, and network access are isolated _(Mod 12 p305)_

### API and interface surface

- Assess the security of cloud APIs and log the customer network traffic _(Mod 12 p305)_
- Analyze the API dependency chain software modules _(Mod 12 p305)_
- Analyze the security model of cloud provider interfaces _(Mod 12 p305)_

### Breach handling

- Baseline the security breach notification process _(Mod 12 p305)_

_(all items _(Mod 12 pp304-305)_)_

### Two items that read oddly — reproduced as printed

- "**Verify one's own cloud in public domain blacklists**" — the wording is ambiguous; it may mean
  verify that one's cloud appears on public blacklists, or verify one's cloud *against* them.
  The courseware does not disambiguate. _(Mod 12 p304)_
- "**Enforce legal contracts in the employee behavior policy**" _(Mod 12 p304)_

## NIST recommendations for cloud security _(Mod 12 p307)_

Seven recommendations, printed as both slide and body:

1. **Assess the risks posed to the client data, software, and infrastructure** _(Mod 12 p307)_
2. **Select appropriate deployment model(s) according to the requirements** _(Mod 12 p307)_ —
   cf. [[12-LO01c-Cloud-Deployment-Models]]
3. **Ensure (effective) audit procedures for data protection and software isolation** _(Mod 12 p307)_
4. **Renew SLAs if security gaps are found between the security requirements of an organization
   and the standards of the cloud provider** _(Mod 12 p307)_
5. **Establish appropriate incident detection and reporting mechanisms** _(Mod 12 p307)_
6. **Analyze the security objectives of the organization** _(Mod 12 p307)_
7. **Determine / enquire about who is responsible for the data privacy and security issues in
   the cloud** _(Mod 12 p307)_

## Organization / provider cloud security compliance _(Mod 12 pp308–311)_

"Given below are checklists for determining whether the **security team**, the **rest of the
organization**, and any **proposed cloud provider** can ensure cloud security." _(Mod 12 p308)_

The checklists are two-column (**Organization** | **Provider**) tables. The column assignment
did not survive OCR — see `unresolved:` — so each question is given as text only.

### Management — Table 12.8 _(pp308, 310–311)_

1. Is everyone aware of their cloud security responsibilities?
2. Is there a mechanism for assessing the security of a cloud service?
3. Does business governance mitigate the security risks that can result from cloud-based
   **"shadow IT"**?
4. Does the organization know the **jurisdictions within which its data can reside**?
5. Is there a mechanism for managing cloud-related risks?
6. Does the organization understand the data architecture required to operate with appropriate
   security at all levels?
7. Can the organization be confident regarding end-to-end service continuity across several
   cloud service providers?
8. Does the provider comply with all relevant industry standards (e.g., **the UK Data
   Protection Act**)?
9. Does the compliance function understand the specific regulatory issues related to the
   adoption of cloud services by an organization?

### Operations — Table 12.6 _(Mod 12 p309)_

1. Are regulatory compliance reports, audit reports, and reporting information available from
   the provider?
2. Are the organization's incident handling and business continuity policies and procedures
   designed considering cloud security issues?
3. Are the cloud service provider's compliance and audit reports accessible to the
   organization?
4. Does the CSP SLA address incident handling and business continuity concerns?
5. Does the CSP have clear policies and procedures to **handle digital evidence** in the cloud
   infrastructure?
6. Is the CSP compliant with the industry standards?
7. Does the CSP have skilled and sufficient staff for incident resolution and configuration
   management?
8. Does the CSP have defined procedures to support the organization in the case of incidents
   involving several clients in a **multi-tenant** environment?
9. Does the use of a cloud provider give the organization an **environmental advantage**?
10. Does the organization know the application or database in which **each data entity is stored
    or mastered**?
11. Is the cloud-based application maintained and **disaster tolerant** (i.e., would it recover
    from an internal or externally caused disaster)?
12. Are all personnel appropriately vetted, monitored, and supervised?
13. Does the CSP provide flexibility of **service relocation and switchovers**?
14. Has the CSP implemented perimeter security controls such as **IDS and firewalls**, and does
    it provide regular activity logs to the organization?
15. Does the CSP provide reasonable assurance of quality or availability of service?
16. Is it easy to securely integrate the cloud-based applications at runtime and contract
    termination?
17. Does the CSP provide **24/7 support** for cloud operations and security-related issues?

_(Mod 12 p309)_

### Technology — Table 12.6 _(Mod 12 p310)_

- Do the procurement processes contain cloud security requirements? _(p310 — table placement
  ambiguous, see `unresolved:`)_
1. Are there appropriate access controls (e.g., **federated SSO**) that give users controlled
   access to cloud applications?
2. Is **data separation** maintained between the organization and customer information at
   runtime and during backup (including data disposal)?
3. Has the organization considered and addressed backup, recovery, archiving and
   decommissioning of data stored in a cloud environment?
4. Have mechanisms been established for **authentication, authorization, and key management**
   in a cloud environment?
5. Are mechanisms in place to manage **network congestion, misconnection, misconfiguration, and
   lack of resource isolation**, which affect the services and security?
6. Has the organization implemented sufficient security controls on the **client devices** used
   to access the cloud?
7. Are all cloud-based systems, infrastructure, and physical locations suitably protected?
8. Are the network designs suitably secure for the organization's cloud adoption strategy?

_(Mod 12 p310)_

### Security team — unnumbered checklist _(Mod 12 p308)_

Truncated in the source after 7 items; see `unresolved:`.

- Are the members of the security team **formally trained in cloud technologies**?
- Do the organization security policies consider the cloud infrastructure?
- Has the security team ever been involved in the implementation of the cloud infrastructure?
- Has the organization defined **security assessment procedures** for the cloud infrastructure?
- Has the organization ever been audited for cloud security threats?
- Does the adoption of cloud by the organization comply with the security standards that the
  organization follows?
- Has **security governance been adapted** to include the cloud?
- Does the team have adequate resources to implement the clou… _(truncated)_






