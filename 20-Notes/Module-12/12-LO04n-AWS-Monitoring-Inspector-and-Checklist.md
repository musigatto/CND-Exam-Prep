---
type: note
module: "12"
lo: "04"
tags: [tool, bestpractice, exam, mod/12, flashcard/12]
topic: "AWS monitoring and logging services, Amazon Inspector, and the AWS security checklist"
exam_weight: unknown
status: done
unresolved:
  - "p152: the heading 'Amazon CloudWatch Events Logs (+SNS)' is garbled — it duplicates 'Amazon CloudWatch events' from the same list. The paragraph beneath it describes CloudWatch Logs sending SNS email notifications when a CloudTrail alarm is triggered, so the body text is used and the duplicate heading is not asserted as a separate service."
  - "p153: the Inspector metrics screenshot OCRs as 'TotalHeaRhyAgents / TotalAssessrnentRuns / TotalMatchingAgents / Totalftndngs' with ARNs as 'arn:awsnspectorus-east-l:...'. The four metric names are legible and used; the ARNs are not resolved."
  - "p154: the SLIDE version of the AWS Security Checklist does not match the BODY list verbatim — the slide says 'Establish CloudTrail log file validation' where the body says 'Set CloudTrail log file validation', the slide says 'Establish MFA for the \"root\" account' / 'Establish MFA for IAM users' where the body says 'Set MFA for the \"root\" account' / 'Set MFA for IAM users', the slide says 'Permit the required parameters in all Redshift clusters' where the body says 'Permit the required SSL parameters in all Redshift clusters', and the body adds 'Permit Redshift audit logging', 'Regularly rotate IAM access keys and standardize the selected number of days' and 'Establish strict password policies', which do not appear on the slide. The body list is transcribed as the checklist; the slide wording is noted beside the differing items."
  - "p155: the checklist item 'Elastic Block Store (EBS) database must be encrypted' is printed exactly; the courseware never explains the relationship between 'database' and EBS volumes, so it is left unrepaired."
  - "p153: the Inspector benefit 'Integrates security into DevOps by analyzing the network configurations in AWS accounts' is printed exactly, but 'network configurations in AWS accounts' is the wording used elsewhere in this module for Amazon VPC — it appears to be a printing error. Printed verbatim, not corrected."
---

[[MOC-Module-12]]

# AWS Monitoring, Inspector & Security Checklist (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · AWS monitoring and logging (pp151–152) ·
> Amazon Inspector (p153) · AWS security checklist (pp154–155). Covers pp. 151–155.

## AWS monitoring and logging _(Mod 12 pp151–152)_

"AWS provides tools for **monitoring the AWS resources and activities** and **responding to
potential incidents**. AWS services **generate security log data**." _(p151)_

**Logging capabilities, as listed on the slide** _(p151)_: AWS Cloud Trail (+SNS) · AWS Config ·
AWS Detailed Billing Reports · Amazon S3 Access Logs · Elastic Load Balancing Access Logs ·
Amazon CloudFront Access Logs · Amazon Redshift Logs · Amazon CloudWatch events · Amazon
Relational Database Service (RDS) Logs · Amazon VPC Flow Logs · Centralized Log Management
Options · Amazon GuardDuty.

| # | Service | Courseware description |
|---|---|---|
| 1 | **AWS CloudTrail (+SNS)** _(p151)_ | "**Amazon SNS** provides a record of actions taken by a **user, role, or an AWS service** in Amazon SNS. It is integrated with AWS CloudTrail that **captures API calls for Amazon SNS as events**. The captured calls consist of calls from the **Amazon SNS console** and **code calls to the Amazon SNS API operations**." |
| 2 | **AWS Config** _(p151)_ | "Allows users to **assess, audit, and evaluate the configuration of AWS resources**. Thus … users can **track the changes to resource configuration**, execute **operational troubleshooting**, and perform **security analysis**." |
| 3 | **AWS Detailed Billing Reports** _(p151)_ | "Can be utilized by users to **analyze the consumption of AWS resources on an hourly, daily, or monthly basis**. Helps in enhancing the **accuracy of cost allocation reports** and facilitates the **billing process**." |
| 4 | **Amazon S3 Access Logs** _(p151)_ | "**Amazon S3 Server Access Logs** … record the **user actions, roles, or AWS services** on Amazon S3 resources and maintain log records for **auditing and compliance** purposes." |
| 5 | **Elastic Load Balancing Access logs** _(pp151–152)_ | "Can be used to **analyze traffic patterns and troubleshoot issues**. ELB provides access logs that capture **detailed information about the requests sent to the load balancer**, and it is an **optional feature that is disabled by default**." |
| 6 | **Amazon CloudFront Access logs** _(p152)_ | "Provide **detailed records about requests made to a distribution**. These logs are useful for many applications such as **security and access audits**." |
| 7 | **Amazon Redshift Logs** _(p152)_ | "Provide information regarding **user logs, user activity logs, and connection logs**. The **connection and user log information can be used for security monitoring**, whereas the **user activity logs can be utilized for troubleshooting activity**." |
| 8 | **Amazon CloudWatch Events** _(p152)_ | "Deliver **system events that describe the changes in AWS resources**. The events can be **matched and routed to one or more target functions or streams using simple rules**." |
| 9 | **CloudWatch Logs (+SNS)** _(p152)_ | "Can be configured to **send a notification when a CloudTrail alarm is triggered**. CloudWatch uses **Amazon SNS to send alerts through emails**; this helps in delivering **quick responses to critical operational events** captured in CloudTrail events and detected by CloudWatch Logs." |
| 10 | **Amazon RDS Logs** _(p152)_ | "**Collects and stores information related to database access, performance, and operation**, which helps in the analysis of **security, performance, and operation of AWS-managed databases**." |
| 11 | **Amazon VPC Flow Logs** _(p152)_ | "**Collects and stores information about the incoming and outgoing IP traffic from Amazon VPC network interfaces**. Can be used for **debugging** or when network flow data are **required by a company for its legal or security policies**." |

**Centralized log management options** _(p152)_

- "There are various options in AWS to **centrally manage log data** such as **Amazon
  CloudWatch Logs** that offer a **centralized service for collecting, storing, and accessing
  the log data**. Users can retrieve such data utilizing the **Amazon CloudWatch console**."

**Amazon GuardDuty** _(p152)_

> "A **threat detection service** that **monitors AWS accounts, instances, users, databases
> and workloads continuously for malicious activity**. It delivers **detailed security
> findings** for visibility and remediation. It uses **anomaly detection, ML, threat
> intelligence feeds, and behavioral modeling** to expose threats."

Earlier in the module: [[12-LO04i-AWS-Monitoring-and-Identity-Center-SSO]] ·
[[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

## AWS monitoring: Amazon Inspector _(Mod 12 p153)_

- "**Amazon Inspector, an automated security assessment service**, helps in improving the
  **security and compliance of applications deployed on AWS**. It works on an
  **application-by-application basis**."
- Slide objectives _(p153)_: "Utilize Amazon Inspector to **automatically evaluate
  applications for vulnerabilities, exposures, and deviations from the specified best
  practices**." · "Amazon Inspector is used for **viewing the complete list of security
  findings based on severity levels**."

**Features and benefits** _(p153)_

1. "**Identifies application security issues** and deviations from the **security best
   practices** in applications."
2. "**Integrates security into DevOps** by analyzing the network configurations in AWS
   accounts and using an **optional agent** for visibility in **Amazon EC2 instances**."
3. "**Increases development agility** to develop and iterate new applications quickly and
   **assess compliance with the best practices and policies**."
4. "**Leverages AWS security expertise** to **continuously assess the AWS environment** and
   **update a knowledge base of the security best practices and rules**."
5. "**Streamlines security compliance** to provide visibility to the **security teams and
   auditors** in security testing performed during the development of applications on AWS."
6. "**Enforces security standards** to define the standards and best practices for your
   applications and **validate their adherence** to these standards."

Metrics console, legible rows _(p153)_: **TotalHealthyAgents** · **TotalAssessmentRuns** ·
**TotalMatchingAgents** · **TotalFindings**.

## AWS security checklist _(Mod 12 pp154–155)_

> Transcribed from the body list, in printed order.

### CloudTrail and logging

| # | Checklist item | Slide wording where it differs |
|---|---|---|
| 1 | Permit **CloudTrail logging** across all Amazon Web Services | — |
| 2 | **Set CloudTrail log file validation** | slide: "**Establish** CloudTrail log file validation" |
| 3 | Permit **CloudTrail multi-region logging** | — |
| 4 | **Combine CloudTrail with CloudWatch** | — |
| 5 | Permit **access logging for CloudTrail S3 buckets** | — |
| 6 | Permit **access logging for ELB** | slide wording: "Permit access logging for **Elastic Load Balancer (ELB)**" |
| 7 | Permit **Redshift audit logging** | *body only — not on the slide* |
| 8 | Permit **VPC flow logging** | slide: "Permit Virtual Private Cloud (VPC) flow logging" |
| 9 | **MFA is required to delete CloudTrail buckets** | — |
| 10 | Set MFA for the "**root**" account | slide: "**Establish** MFA for the \"root\" account" |
| 11 | Set MFA for **IAM users** | slide: "**Establish** MFA for IAM users" |

### IAM, credentials and access

| # | Checklist item |
|---|---|
| 14 | Permit **IAM users for multi-mode access** |
| 15 | **Link IAM policies to groups or roles** |
| 16 | **Regularly rotate IAM access keys** and **standardize the selected number of days** *(body only)* |
| 17 | **Establish strict password policies** *(body only)* |
| 18 | Set the **password termination session to 90 days** |
| 19 | **Limit access to the CloudTrail bucket** |
| 20 | **Provision access to resources using IAM roles** |
| 21 | **Use of root user accounts should be avoided** |
| 22 | **Access keys should not be used with root accounts** |
| 23 | **Reduce the number of IAM groups** |
| 24 | **Terminate the available access keys** |
| 25 | **Disable access for unused or inactive IAM users** |
| 26 | **Remove unused IAM access keys** |

### Encryption and network transport

| # | Checklist item |
|---|---|
| 27 | **Encrypt the CloudTrail log files at rest** |
| 28 | **Elastic Block Store (EBS) database must be encrypted** |
| 29 | **Encrypt Amazon RDS** |
| 30 | **SSL secure ciphers** must be applied when **establishing a connection between the client and ELB** |
| 31 | **SSL secure versions** must be used while **connecting ELB and client** |
| 32 | **Use secure CloudFront SSL versions** |
| 33 | **User HTTPS for CloudFront distributions** |
| 34 | **Expired SSL/TLS certificates should not be used** |
| 35 | **Use a standard naming (tagging) convention for EC2** |
| 36 | **Number of discrete security groups should be minimized** |
| 37 | **Periodically rotate SSH keys** |
| 38 | Permit the required **SSL parameters in all Redshift clusters** _(slide: "Permit the required **parameters** in all Redshift clusters")_ |

Checklist cross-refs: IAM controls → [[12-LO04f-AWS-Password-Policy-and-MFA]] ·
[[12-LO04c-AWS-IAM-Roles-and-Best-Practices]] · S3/EBS encryption →
[[12-LO04m-AWS-DDoS-Storage-and-Data-Classification]] · ACM/SSL →
[[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]

## Cards

What Amazon GuardDuty is and how it works
?
A threat detection service that monitors AWS accounts, instances, users, databases and workloads continuously for malicious activity; it delivers detailed security findings for visibility and remediation, using anomaly detection, ML, threat intelligence feeds and behavioral modeling to expose threats

Amazon VPC Flow Logs vs Amazon CloudWatch Events
?
VPC Flow Logs collect and store information about the incoming and outgoing IP traffic from Amazon VPC network interfaces, for debugging or where network flow data are required by legal or security policies · CloudWatch Events deliver system events describing changes in AWS resources, matched and routed to target functions or streams using simple rules

Amazon Inspector — what it is
?
An automated security assessment service that improves the security and compliance of applications deployed on AWS, working application-by-application; it automatically evaluates applications for vulnerabilities, exposures and deviations from best practices and lists security findings by severity level

The four CloudTrail-related checklist items
?
Permit CloudTrail logging across all Amazon Web Services · set (establish) CloudTrail log file validation · permit CloudTrail multi-region logging · combine CloudTrail with CloudWatch

The credential and root-account hygiene items in the AWS security checklist
?
Set MFA for the root account and for IAM users · avoid use of root user accounts · do not use access keys with root accounts · link IAM policies to groups or roles · rotate IAM access keys regularly and standardize the number of days · establish strict password policies and set password termination session to 90 days · reduce the number of IAM groups · disable unused or inactive IAM users · remove unused IAM access keys · terminate available access keys

The encryption-at-rest and transport items in the AWS security checklist
?
Encrypt the CloudTrail log files at rest · encrypt Amazon RDS · EBS must be encrypted · SSL secure ciphers and versions between client and ELB · use secure CloudFront SSL versions and HTTPS for CloudFront distributions · do not use expired SSL/TLS certificates · permit the required SSL parameters in all Redshift clusters · minimize the number of discrete security groups · use a standard naming (tagging) convention for EC2
