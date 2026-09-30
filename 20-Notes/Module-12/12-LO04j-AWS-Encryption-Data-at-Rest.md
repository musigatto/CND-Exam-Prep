---
type: note
module: "12"
lo: "04"
tags: [concept, crypto, policy, mod/12, flashcard/12]
topic: "AWS data-at-rest encryption models and Amazon S3 server-side encryption options"
exam_weight: unknown
status: done
unresolved:
  - "p116 Figure 12.62 'AWS Data at Rest Encryption Models': the image OCRs only as the axis labels 'Model A / Model B / Model C', the column labels 'Keys / Storage / Key Management' and the legend 'Customer Managed / AWS Managed'. Which model owns which axis cell could not be read from the figure; the three per-model one-liners printed on the same slide are used instead."
  - "pp118-119: the courseware uses the acronym 'KMI' ('their own KMI to generate, store, and manage access to keys', 'the storage component of the KMI', 'the customer provides KMI') but never expands it anywhere in pp. 116-121. The expansion is NOT supplied here."
  - "p121: the SSE-KMS sentence prints the parenthetical as 'CMKs stored in AWS Key Management Service (SSE-KMS)' — the parenthetical repeats the SSE-KMS acronym instead of naming it, so it is left exactly as printed rather than repaired."
  - "p120 Figure 12.63 / p123 Figure 12.63 (client-side encryption diagram): labels 'Your key management infrastructure', 'Your applications in Amazon EC2', 'Your applications in data center', 'Your encryption client' and 'AWS SDK with Amazon S3 encryption client' are legible, but one further label OCRs only as 'Your encryption OR' and the arrows between boxes did not OCR. The diagram is described from the five legible labels only."
---

[[MOC-Module-12]]

# AWS Encryption: Data at Rest (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · encrypting data at rest
> Covers pp. 116–121.

## The three data-at-rest encryption models _(Mod 12 pp116–119)_

> "It is important to understand **who has access to encryption keys or data under which
> conditions** while deploying encryption for various data classifications in AWS. There are
> **three different models** for how a customer and AWS provide the **encryption method** and
> the **KMI**." _(Mod 12 p118)_

| | **Model A** | **Model B** | **Model C** |
|---|---|---|---|
| **Encryption** | Customer manages | Customer manages | AWS provides |
| **Key storage** | Customer manages | **AWS provides the key storage layer** | **AWS provides** |
| **Key management** | Customer manages | Customer manages | **AWS provides** |
| **One-liner as printed** _(p116)_ | "The customer manages the encryption, key storage, and key management" | "AWS provides the key storage layer and customer manages the encryption algorithm and key management" | "AWS provides the key storage layer, encryption algorithm, and key management" |

Mnemonic: **A**ll customer → **B** AWS stores the keys (algorithm still yours) → **C** Cloud/AWS
does everything (server-side, transparent).

**Model A — customer manages encryption** _(p118)_
- "Customers use **their own KMI** to generate, store, and manage access to keys. They also
  control **all encryption methods** present in their applications."
- "This encryption method is a combination of **open-source tools, AWS SDKs, third-party
  software, and/or hardware**."

**Model A — customer manages key storage and key management** _(p118)_
- "**Only the customer** has full control over the encryption keys **and the execution
  environment** that utilizes those keys in the encryption code."
- "Customer is responsible for **key storage and key management, as well as key usage** to
  ensure the **confidentiality, integrity, and availability** of data."

**Model B — AWS provides the key storage layer / storage component of the KMI** _(p118)_
- "The keys are stored in the **AWS environment (AWS CloudHSM)** and are **inaccessible to any
  employee at AWS**."

**Model B — customer manages the encryption algorithm and key management** _(p119)_
- "The customer provides KMI that can be deployed either **on-premise or within Amazon EC2**."
- "The customer KMIs can **securely communicate with AWS CloudHSM instances over SSL** to
  protect the data and encryption keys."

**Model C — AWS controls everything** _(p119)_
- "AWS enables the control of the **key storage layer, encryption algorithm, and key
  management**."
- "AWS provides **server-side encryption** of customer data, **transparently managing** the
  encryption method and keys."

→ CloudHSM control/separation of duties: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

## Protecting data at rest — the courseware's best practices _(Mod 12 pp116–118)_

"It is recommended to create an **encrypted file system** using an industry-standard (for
example, **AES-256**) encryption algorithm if your organization is subject to
corporate/regulatory policies that require the encryption of **data and metadata at rest**."
_(p116)_

**Steps to Protect Data at Rest in AWS** _(pp116–117)_

1. Define data management and protection at rest requirements such as **encryption and data
   retention** to meet **organizational**, **legal** and **compliance** requirements.
2. Implement **secure key management** — securely **storing and rotating** the encryption keys
   with **strict access control** using services such as **AWS KMS**. "Additionally, use
   **different keys for the segregation of different data classification levels and retention
   requirements**."
3. Enforce encryption at rest based on the **latest standards and best practices**.
4. Enforce access control with the **least privileges and mechanisms, including backups,
   isolation, and versioning**.
5. Consider **which types of data are publicly accessible**.
6. Provide mechanisms to **keep users away from accessing sensitive data**, which involves
   providing a **dashboard and tools**. _(p117)_

**Define Data at Rest Protection Requirements** _(Mod 12 p117)_

| # | Step | Courseware detail |
|---|---|---|
| 1 | Identify compliance requirements | "Find the organizational, legal, and compliance requirements that must be complied with by the workload of the organization." |
| 2 | Identify AWS compliance resources | "Find the resources that AWS has for assisting; for example, **AWS cloud compliance**." |
| 3 | Define encryption standards | "Based on the **latest available and supported encryption ciphers and protocols**." |
| 4 | Define key management solutions | "Consider the use of **AWS Key Management Services** (for example) for encryption at rest for workloads using **Amazon S3**." |
| 5 | Define data protection controls | "Secure data **according to the classification level**." |
| 6 | Define data retention requirements | "Amount of time required to keep different types of data" · "Number of **previous versions and copies**" |
| 7 | Identify data management tools | "to manage your data at rest" |
| 8 | Keep users away from data | "Define mechanisms to keep users away from accessing sensitive data **directly**." |

**Implement controls for the protection of data at rest** _(Mod 12 pp117–118)_

1. Enforce encryption at rest based on the latest standards and best practices.
2. Enforce access control with the **least privileges, including access to encryption keys**.
3. **AWS Secrets Manager** — "manage secrets (**database credentials, passwords, third-party
   API keys, and even arbitrary text**)."
4. "**Separate data based on different classification levels using different AWS accounts.**"
5. Mechanisms to keep people away from data:
   - **Dashboards** (for example, **Amazon QuickSight**) to display data to end users.
   - **Automated configuration** for administrators such as **AWS CloudFormation**.
6. **Review AWS KMS policies** to review the level of access granted.
7. "Configure encryption in **Amazon S3** using **client-side or server-side** techniques."
8. "Review **S3 bucket and object permissions** regularly… by **eliminating publicly readable
   or writeable buckets**." → "Consider using **AWS Config** to detect buckets that are open
   and **Amazon CloudFront** to serve content from S3."
9. "Enable **Amazon S3 versioning**."
10. "Configure **encrypted AMIs** to automatically encrypt **root volumes and snapshots**." _(p118)_
11. "Review **Amazon EBS** and **AMI sharing permissions** to allow images and volumes to be
    shared to AWS accounts external to your workload." _(p118)_
12. "Configure **Amazon RDS** encryption by enabling the encryption option." _(p118)_
13. "Configure **Amazon DynamoDB** encryption to encrypt data at rest using an **AWS
    KMS-managed encryption key**." _(p118)_
14. "Consider **AWS encryption SDK with AWS KMS integration** when your application needs to
    encrypt **client-side** data." _(p118)_

## Encrypting data at rest in Amazon S3 _(Mod 12 pp120–121)_

"Amazon S3 is a data storage service that **stores and retrieves data on the cloud**. It
provides the following methods to encrypt the data:" _(p120)_

| Method | Courseware statement |
|---|---|
| **Server-side encryption** | Amazon S3 provides the following options of encryption and keys management: **Amazon S3-managed keys (SSE-S3)** · **AWS KMS-managed keys (SSE-KMS)** · **Customer-provided keys (SSE-C)** |
| **Client-side encryption** | "**Encrypt data before sending to Amazon S3 and decrypt data after receiving it.**" "The most common open source tools are: **Bouncy Castle**, **open SSL**." |

Client-side encryption from the on-premise system or within an EC2 application _(Fig 12.63,
pp120/123)_ — legible labels only: **Your key management infrastructure** · **Your applications
in Amazon EC2** · **Your applications in data center** · **Your encryption client** · **AWS SDK
with Amazon S3 encryption client**.

### SSE-S3 — Amazon S3-Managed Encryption Keys _(Mod 12 p121)_

- "Amazon S3 protects data using server-side encryption with Amazon S3-Managed Encryption
  Keys (SSE-S3)."
- "It **encrypts each object with a unique key**; additionally, it **encrypts this key with a
  master key** to provide additional security."
- "Amazon S3 SSE uses the **256-bit Advanced Encryption Standard (AES-256)** to encrypt data."
- "A **bucket policy** can be used here if **SSE is required for all objects** stored in the
  bucket."

**API support for server-side encryption** _(p121)_

- "Provide the **`x-amz-server-side-encryption`** request header to request SSE using the
  object creation REST APIs."
- Supported APIs: **PUT operations** (specify the header when uploading data using the PUT
  API) · **Initiate Multipart Upload** (header in the initiate request when uploading large
  objects using the multipart upload API) · **COPY operations** (users have both a source
  object and target object when copying an object).

### SSE-KMS — AWS KMS-Managed Keys _(Mod 12 p121)_

- "AWS KMS-managed keys (SSE-KMS) protect data using SSE with **CMKs stored in AWS Key
  Management Service**."
- "AWS KMS can be used via the **AWS Management Console or AWS KMS APIs** if using CMKs to
  **centrally create CMKs**."
- "**Define the policies** that control how CMKs can be used and **audit the CMK usage**; these
  CMKs can be used to **secure data in Amazon S3 buckets**."

**SSE-KMS highlights** _(p121)_

1. "Allows the selection of a **customer-managed CMK that you create and manage** or an
   **AWS-managed CMK that Amazon S3 creates in the AWS account and manages for you**."
2. "**Create, rotate, and disable** auditable customer-managed CMKs from the **AWS KMS
   console**."
3. "Provide the **encryption of data keys** that are used to encrypt customer data."
4. "Provide **encryption-related compliance requirements**."
5. Printed caveat: "**The ETag in the response is not the MD5 of the object data.**"

### SSE-C — Customer-provided Keys _(Mod 12 p121)_

- "Amazon S3 supports Server-side Encryption with **Customer-provided Keys (SSE-C)**."
- "**SSE-C allows Amazon S3 to encrypt data using keys provided by users. The keys are never
  stored by S3.**"
- "Customers can use encryption keys **without the cost of writing or executing the encryption
  code** because the **Amazon S3 performs the encryption**."

| | Who holds the key | Where the encryption runs | Courseware key fact |
|---|---|---|---|
| **SSE-S3** | Amazon S3 (S3-managed) | Amazon S3 | Per-object unique key, itself wrapped by a master key; **AES-256** |
| **SSE-KMS** | AWS KMS (customer-managed or AWS-managed **CMK**) | Amazon S3 | CMK policies + CMK usage audit; encrypts the data keys |
| **SSE-C** | **The customer** — "**never stored by S3**" | Amazon S3 | You keep the key; S3 does the crypto |

Client-side libraries: [[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]] ·
storage services: [[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]]

## Cards

The three AWS data-at-rest encryption models — who does what
?
Model A — customer manages the encryption, key storage and key management · Model B — AWS provides the key storage layer, customer manages the encryption algorithm and key management · Model C — AWS provides the key storage layer, encryption algorithm and key management (transparent server-side encryption)

In AWS data-at-rest Model B, where are the keys stored and who controls the algorithm?
?
Keys are stored in the AWS environment (AWS CloudHSM) and are inaccessible to any AWS employee; the customer provides the KMI (on-premise or in Amazon EC2) and manages the encryption algorithm and key management, communicating with CloudHSM over SSL

The three Amazon S3 server-side encryption key-management options
?
SSE-S3 — Amazon S3-managed keys · SSE-KMS — AWS KMS-managed keys (CMKs in AWS Key Management Service) · SSE-C — customer-provided keys, never stored by S3

Amazon S3 SSE-S3 as described by the courseware
?
Each object is encrypted with a unique key, and that key is additionally encrypted with a master key; Amazon S3 SSE uses 256-bit AES (AES-256); a bucket policy can enforce SSE for all objects in the bucket

Which Amazon S3 APIs support the `x-amz-server-side-encryption` request header
?
PUT operations (uploading with the PUT API) · Initiate Multipart Upload (header in the initiate request for large objects) · COPY operations (source and target object)

Amazon S3 SSE-KMS — the printed highlights
?
Select a customer-managed CMK you create/manage or an AWS-managed CMK that Amazon S3 creates and manages for you · create, rotate and disable auditable customer-managed CMKs from the AWS KMS console · provides encryption of the data keys that encrypt customer data · provides encryption-related compliance requirements · the ETag in the response is not the MD5 of the object data
