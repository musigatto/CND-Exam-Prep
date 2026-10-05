---
type: note
module: "12"
lo: "04"
tags: [bestpractice, tool, concept, mod/12]
topic: "AWS DDoS mitigation, Amazon S3 and EBS storage security, data classification and Amazon Macie"
exam_weight: unknown
status: done
unresolved:
  - "p147: the 'Data Classification based on Sensitivity' slide shows only two legible entries, 'Public Data' and 'Critical Data'; a third entry OCRs only as 'Encrypted Ãƒ¼Ãƒ¥cie C) usus' and is NOT resolved to a classification name. If the courseware intends three levels, the third is missing here."
  - "p144: the sentence 'The AWS config rule consists of ten built-in rules to monitor the S3 security configurations' is grammatically broken (singular 'rule' vs plural 'rules') and it is not stated whether the count 'ten' is correct or an OCR artefact. Quoted verbatim, not relied on."
  - "p149: the Macie search string OCRs as 'filesystem metadata . bucket: / amazon-macie-activity-generator-defaults3bucket. * / s'. The exact Lucene field syntax (dots vs spaces, leading/trailing wildcards) is garbled and is NOT reconstructed."
  - "pp. 142-143 Figure 12.71 vs Table 12.3: the figure and the 'Summary of the Best Practices' table assign INCONSISTENT BP numbers to the same items (figure: BP1 CloudFront, BP2 AWS WAF, BP3 Route 53, BP4 API Gateway, BP5 public subnet/AZ, BP6 load balancing, BP7 auto scaling; table: CloudFront BP1, AWS WAF (unnumbered), Global Accelerator BP1, Route 53 BP5, Elastic Load Balancing BP6, security groups and network ACLs BP5, EC2 Auto Scaling BP7). The BP numbers are NOT reconciled here."
  - "p142: the 'AWS Shield Standard' slide itself prints the Shield **Advanced** sentence ('It is available for CloudFront, Route 53, and Global Accelerator and organizations can use it with Elastic IP addresses to secure Network Load Balancer (NLBs) or Amazon EC2 instances'), which p143 then prints again under 'AWS Shield Advanced (optional)'. Both placements are preserved; the courseware does not reconcile them."
  - "pp. 144-146: the 'Adding System-Defined Metadata' / 'Adding User-Defined Metadata' and Amazon EBS figures are images whose contents did not OCR; only the labelled console steps in the body are transcribed."
---

[[MOC-Module-12]]

# AWS DDoS Mitigation, Storage Security & Data Classification (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · DDoS mitigation (pp142–143) · Amazon S3
> security (pp144–146) · data identification and classification + Amazon Macie (pp147–150).
> Covers pp. 142–150.

## AWS DDoS mitigation techniques _(Mod 12 pp142–143)_

"Although AWS services provide some forms of DDoS mitigation automatically, organizations can
enhance further DDoS resiliency using the following services in AWS architecture." _(Mod 12 p142)_

### AWS Shield Standard _(Mod 12 pp142–143)_

- "A **threat protection service** that **protects the first point of entry** for application
  traffic coming from **outside the AWS network**."
- "Provides **all AWS customers automatic DDoS protection at no additional charge** and is
  offered on **all AWS services and in all AWS regions**."
- "It is **always on, pre-configured, static**, and provides **no reporting or analytics**."
- "To **detect malicious traffic in real time** it applies a combination of **traffic
  signatures, anomaly algorithms, and analysis techniques**." _(Mod 12 p143)_
- "Shield Standard **automatically mitigates basic network layer attacks** by using
  **deterministic packet filtering** and **priority-based traffic techniques**." _(Mod 12 p143)_

### AWS Global Edge Network _(Mod 12 p143)_

- "**Protects against all known infrastructure layer attacks.**"
- "Enhances the DDoS resilience of application(s) when serving **any type of application
  traffic from edge locations**."
- "Services such as **Amazon CloudFront, AWS Global Accelerator, and Amazon Route 53** are
  part of it."

| Service | As printed |
|---|---|
| **Amazon CloudFront** | "**Customizes the web content delivery** to improve latency and **protect the client application**." |
| **AWS Global Accelerator** | "**Moves network traffic onto AWS's congestion-free private network infrastructure**, thereby solving the issue of **slow connections and dropped data**." |
| **Amazon Route 53** | "Addresses issues such as **failed connections caused by inefficiencies in network traffic** routed between devices and applications by **routing and managing network traffic**." |

### AWS Shield Advanced (optional) _(Mod 12 p143)_

- "Available for **CloudFront, Route 53, and Global Accelerator**."
- "Organizations can use it **with Elastic IP addresses** to secure **Network Load Balancers
  (NLBs)** or **Amazon EC2 instances**."

### The mitigation layers named on the slide _(Mod 12 p143)_

- **Layer 3** (e.g. **UDP reflection**) attack mitigation
- **Layer 4** (e.g. **SYN flood**) attack mitigation
- **Layer 6** (e.g. **TLS**) attack mitigation
- **Reduce attack surface**
- **Scale to absorb application layer traffic**
- **Layer 7** (application layer) attack mitigation
- **Geographic isolation and dispersion of excess traffic** and larger DDoS attacks **if used
  with AWS WAF**

**Table 12.3 — Summary of the Best Practices** _(p143; BP numbers as printed)_

| BP | Best practice |
|---|---|
| **BP1** | Using **Amazon CloudFront** (figure also lists BP1) |
| — | Using **Amazon CloudFront with AWS WAF** |
| **BP1** | Using **Global Accelerator** |
| **BP5** | Using **Amazon Route 53** |
| **BP6** | Using **Elastic Load Balancing with AWS WAF** |
| **BP5** | Using **Security Groups and network ACLs in Amazon VPC** |
| **BP7** | Using **Amazon EC2 Auto Scaling** |

Figure 12.71 (DDoS Resilient Reference Architecture) also shows **API Gateway (BP4)**, a
**public subnet** and a **private subnet** across **two Availability Zones** inside an
**AWS Cloud Region** — see `unresolved:` for the BP-number mismatch.

## AWS storage security: Amazon S3 _(Mod 12 p144)_

- "Amazon S3 allows users to **upload and retrieve data anytime from anywhere on the
  internet**. It stores data as **objects** (text file/photo/video) **within buckets**."
- "In the **default state, all Amazon S3 buckets can be accessed by authorized users**."
- "**Restrict access to your S3 resources by combining bucket policies, ACLs, and IAM
  policies** to give access to the right entities."
- "Users can utilize **IAM policies to implement TLS encryption** for the S3 requests or
  **S3 SSE using keys from KMS**."
- "Users can establish a **private connection from the user VPC to S3 through VPC endpoints**
  by enforcing the **VPC endpoint policy**."
- "The AWS config rule consists of **ten built-in rules** to monitor the S3 security
  configurations." _(quoted verbatim — see `unresolved:`)_

### S3 Block Public Access _(Mod 12 p144)_

> "**S3 Block Public Access ensures that the objects do not have public permissions.** For
> example, if a user has written an object in an S3 bucket by **enabling the S3 Block Public
> Access** and that object has **public permissions through ACL or any other policy**, then
> **that permission will be blocked**."

### S3 Object Lock _(Mod 12 p144)_

- "**S3 Object Lock** allows users to **establish a specific retention date** for the S3
  object to **prevent the deletion of object**."

- "Amazon S3 supports **SSE with three key management options and client-side encryption** for
  data uploads." → [[12-LO04j-AWS-Encryption-Data-at-Rest]]
- "While adding a file to Amazon S3, you can use **options metadata** with the file and
  **set permissions** to control access to the file." _(Mod 12 p144)_

### S3 object metadata — key-value pairs _(Mod 12 p144)_

- "**Add metadata (Key—Value pair) to the S3 objects**; these metadata help in
  **identifying, organizing, and assigning objects to specific resources**."
- "Metadata starting with the prefix **`x-amz-meta-`** represent **user-defined metadata**."
  _(Mod 12 p145)_

**Walkthrough — add system metadata** _(p144–145)_

1. "Sign in to the AWS Management Console and open the Amazon S3 console at
   `https://console.aws.amazon.com/s3/`."
2. "Select the **name of the bucket** that contains the object in the **Bucket name** list."
3. "Select the **name of the object** that you want to add metadata to in the **Names** list."
4. "Select **Properties** tab, and then select **Metadata**."
5. "Select **Add Metadata**, and then select a **key** from the **Select a key** menu."
6. "Depending on the selected key, select a **value** from the **Select a value** menu **or
   type a value**."
7. "Select **Save**."

**Walkthrough — add user-defined metadata** _(Mod 12 p145)_

1. "Select **Add Metadata**, and then select the **`x-amz-meta-`** key from the **Select a
   key** menu."
2. "Type a **custom name** following the `x-amz-meta-` key." — printed example: custom name
   `alt-name` → metadata key **`x-amz-meta-alt-name`**.
3. "Enter a **value** for the custom key, and then select **Save**."

## AWS storage security: Amazon EBS _(Mod 12 pp146)_

- "**Amazon Elastic Block Store (EBS) is a block storage system that can be attached to Amazon
  EC2 instances**."
- "In EBS, **access is restricted to the AWS account that created the volume** and the users
  under the AWS account **created with IAM**." (slide) · "**Permission to view and access EBS
  is denied to all AWS users**." (slide)
- "The block storage service is used with **Amazon EC2 instances** … for both **throughput and
  transaction-intensive workloads**."
- Workloads deployed on Amazon EBS: **relational and non-relational databases** · **enterprise
  applications** · **containerized applications** · **big data analytics engines, file systems,
  and media workflows**.
- "**Amazon EBS supports KMS.** Its encryption provides **data at rest security** by
  **encrypting data volumes, boot volumes, and snapshots** using **Amazon-managed keys** or
  the **keys created and managed by users via AWS KMS**."

## Data identification and classification _(Mod 12 pp147–148)_

"The identification and classification of data based on the **sensitivity levels** helps in
determining the **required security controls**. It also helps in **designing data retention
policies**." _(Mod 12 p147)_

| Level | Courseware attributes |
|---|---|
| **Public Data** | "Not sensitive" · "Available to everyone" · "**Unencrypted**" |
| **Critical Data** | "**Not accessible directly on the internet**" · "**Requires authentication and authorization**" · "**Encrypted**" |

_(A third level appears on the slide but did not OCR — see `unresolved:`.)_

### AWS resource tagging _(Mod 12 p147)_

- "To classify and identify resources, AWS resources should be configured with **tags**. A tag
  comprises a **customer-defined key and an optional value** and describes the **labels
  assigned to an AWS resource**."
- "Tagging enables the **organization of the resources** of a company and helps in simplifying
  **resource management, access management, and cost allocation**."
- "Resource tags can be implemented for **S3 buckets and objects, EBS volumes, RDS
  databases**, and other AWS services that store data to **identify their classification
  level easily**."

**Tagging best practices** _(pp147–148)_

1. "Implement a **standardized, case-sensitive format** for tags consistently across **all
   resource types**."
2. "Consider **tag dimensions** that support the ability to manage: **resource access control**
   · **cost tracking** · **automation** · **organization**."
3. "Implement **automated tools** to help manage resource tags."
4. "Consider the **ramifications of future changes**, especially related to **tag-based access
   control, automation, or upstream billing reports**."

### Amazon Macie _(Mod 12 p148)_

- "Amazon Macie is a **security service that automatically discovers, classifies, and
  protects sensitive data in AWS using machine learning**."
- "It can **identify critical data such as personally identifiable information (PII)**, and
  provide **dashboards and alerts** to know how the data are accessed and processed."

**Macie workflow** _(p148, Fig 12.72 — legible step text only)_

| # | Step | As printed |
|---|---|---|
| 1 | Enablement | "Enable with **one selection in the AWS Management Console**" · "a **single API call**" |
| 2 | **Automated sensitive data discovery** | "Automatically build an **interactive data map of sensitive data** in Amazon S3 and provide **insights on level of security and access controls** based on results from the **data discovery jobs**" |
| 3 | Findings | "Generate findings and send to **Amazon EventBridge** and **AWS Security Hub** for **automated remediation and workflow integration**" |
| 4 | — | "**Enroll your AWS account with Amazon Macie.**" |
| 5 | — | "Select the **Buckets for Content Discovery and Classification**." |
| 6 | — | "Review your **Alerts in the Amazon Macie Dashboard**." |

**Walkthrough — create the `amazon-macie-activity-generator` (AMG) CloudFormation stack**
_(pp148–149)_
- "Deploy AMG in your AWS account according to either of the following methods:"
  - "Use the **CloudFormation Template**:
    `https://s3.amazonaws.com/amazon-macie-activity-generator-us-east-1-fb58a9df3468/CloudFormationTemplate.yml`"
  - "Use the **One-click CloudFormation launch stack**."
- Steps: "**Log in to the AWS Console in a region supported by Amazon Macie**." → "Select the
  **One-click CloudFormation launch stack** or launch CloudFormation using the aforementioned
  template." → "**Read our terms, select the Acknowledgement box, and then select Create.**"

**Walkthrough — add sample data / classify objects** _(Mod 12 p149)_
1. "**Log in to Amazon Macie.**"
2. "Select **Integrations**, followed by **Services**."
3. "Select **your account**, and then select **Details** from the **Amazon S3** card."
4. "Select your **newly created buckets for Full classification, including existing data**."
5. "Open the **Research tab** in Macie, and then select the **S3 Objects index** to view the
   objects in your test sample set."
6. "Use the **regular expression search capability** in Macie to find the objects written to
   buckets that start with `amazon-macie-activity-generator-defaults3bucket`." → type the
   search text into the Macie search box and select the **magnifying glass** icon. *(Search
   string garbled — see `unresolved:`.)* → Fig 12.73 "View the Objects in Your Test Sample".
7. "**Create an advanced search using Lucene Query Syntax and save it as an alert** to be
   matched against **any newly created data**." _(p150, Fig 12.74)_

VPC endpoints and private S3 access: [[12-LO04l-AWS-VPC-and-Network-Security]] ·
logging side: [[12-LO04n-AWS-Monitoring-Inspector-and-Checklist]]







