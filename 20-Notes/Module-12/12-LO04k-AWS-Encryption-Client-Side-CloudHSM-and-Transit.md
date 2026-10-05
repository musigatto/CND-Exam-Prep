---
type: note
module: "12"
lo: "04"
tags: [crypto, tool, bestpractice, mod/12]
topic: "AWS client-side encryption libraries, CloudHSM key management, TLS in transit and AWS Certificate Manager"
exam_weight: unknown
status: done
unresolved:
  - "p122: the body sentence reads 'The Bounty Castle architecture comprises two key components…' — 'Bounty Castle' is an OCR corruption of Bouncy Castle in the same sentence, and is normalized silently. The 17-item API list is attributed to Bouncy Castle."
  - "p124: the industry-standard API is printed as 'PKCS#II' (roman numeral). It is most likely PKCS#11 but the printed form is not legible enough to assert, so the printed 'PKCS#II' is kept and not corrected."
  - "p124-p125: the 'AWS CloudHSM Secured Design' slide prints 'he AWS CloudHSM is secure and highly available by design comprises the following' but only ONE sub-item ('Secure Virtual Private Cloud Access') survives the OCR. Whether the slide carried further sub-items cannot be determined; only the one legible item is used."
  - "p127 Figure 12.65 'AWS Certificate Manager': the diagram OCRs as 'a certitute from c«tifiOte certificate auth«ity (CAY that of AWS a certificate Crote *Wate certificate Ãƒâ€ž'ttvity (CA,) Create a CA e pricing (US) SSL'TL S' — the 'How it works' flow did not OCR. No fact is taken from it."
  - "p129 Figure 12.67: the screenshot OCRs the CloudFront certificate store as 'IAN certificate store'. This is not a readable name; the courseware's term is NOT resolved to 'IAM' here, though that reading is the likely one."
  - "p129 Figure 12.67: the Default CloudFront Certificate name OCRs as 'C.Cloudfront net)'. An earlier draft of this note supplied the well-known AWS placeholder 'd111111abcdef8.cloudfront.net' instead; that string does NOT occur anywhere in the module OCR (verified against all 316 pages) and has been REMOVED as a fabrication. The OCR form is now given and the domain is not resolved."
  - "p129 Figure 12.67: the Important note OCRs as 'If you choose tlis option. Clou$ront requires tlat browsers or deuces support TLSvI or later to access your content'. Read as: If you choose this option, CloudFront requires that browsers or devices support TLSv1 or later. 'TLSvI' is the OCR of TLSv1 (capital I for the digit 1); 'deuces' is the OCR of 'devices'. No TLS version other than 'or later' is stated."
  - "p123: the Figure 12.63 diagram is repeated on p123; on p123 it additionally carries the garbled caption fragments 'key rn•n.nwnt in your center' and 'AWS SOK with Amazon S3 encryption client / AWS with Amazon SS enayption dient'. Nothing is taken from those fragments."
---

[[MOC-Module-12]]

# AWS Encryption: Client-Side, CloudHSM, in Transit & ACM (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · client-side encryption (pp122–123) ·
> key management in AWS CloudHSM (pp124–125) · data in transit (p126) · AWS Certificate Manager
> (pp126–129). Covers pp. 122–129.

## Client-side encryption _(Mod 12 pp120, 122–123)_

- "**Amazon S3 APIs allow uploading the data encrypted by any encryption method and decrypting
  the data when taking it back.**" _(Mod 12 p122)_
- "The most common **open source tools** are: **Bouncy Castle** · **open SSL**." _(pp120, 122)_
- Placement: client-side encryption = "**Encrypt data before sending to Amazon S3 and decrypt
  data after receiving it**"; the client's own key management infrastructure sits outside S3.
  _(p120, Fig 12.63)_

### Bouncy Castle _(Mod 12 p122)_

- "The **lightweight Bouncy Castle Crypto APIs** are used in cryptography; they include APIs
  for **both Java and C#**."
- "The Bouncy Castle architecture comprises **two key components**, namely **Light-weight
  API** and **Java Cryptography Extension (JCE) provider**, that support cryptography."
- "The remaining components **built upon the JCE provider** support additional functionalities
  (**PGP support, S/MIME**)."
- "These APIs operate with everything from the **J2ME to JDK 1.11**."

**Bouncy Castle APIs currently comprise** _(p122, as printed)_

| # | API |
|---|---|
| 1 | A lightweight cryptography API for **Java and C#** |
| 2 | A provider for **JCE** and the **Java Cryptography Architecture (JCA)** |
| 3 | A provider for the **Java Secure Socket Extension (JSSE)** |
| 4 | A clean room implementation of **JCE 1.2.1** |
| 5 | A library for reading and writing encoded **ASN.1** objects |
| 6 | Lightweight APIs for **TLS (RFC 2246, RFC 4346)** and **DTLS (RFC 6347 / RFC 4347)** |
| 7 | Generators for **Version 1 and Version 3 X.509 certificates, Version 2 CRLs, and PKCS12 files** |
| 8 | Generators for **Version 2 X.509 attribute certificates** |
| 9 | Generators/processors for **S/MIME and CMS (PKCS7 / RFC 3852)** |
| 10 | Generators/processors for **OCSP (RFC 2560)** |
| 11 | Generators/processors for **TSP (RFC 3161 & RFC 5544)** |
| 12 | Generators/processors for **CMP and CRMF (RFC 4210 & RFC 4211)** |
| 13 | Generators/processors for **OpenPGP (RFC 4880)** |
| 14 | Generators/processors for **Extended Access Control (EAC)** |
| 15 | Generators/processors for **Data Validation and Certification Server (DVCS) — RFC 3029** |
| 16 | Generators/processors for **DANE (DNS-based Authentication of Named Entities)** |
| 17 | Generators/processors for **RFC 7030 Enrollment over Secure Transport (EST)** |
| + | A **signed jar** version suitable for **JDK 1.4–1.11 and Sun JCE** |

### OpenSSL _(Mod 12 p123)_

- "OpenSSL is a strong, commercial, non-commercial, and **full-featured free toolkit for the
  Transport Layer Security (TLS) and Secure Sockets Layer (SSL) protocols**."
- "The **core library** of OpenSSL implements **basic cryptographic functions**."

## Encryption key management in AWS CloudHSM _(Mod 12 pp124–125)_

- "The AWS CloudHSM service **helps you to control the encryption keys and cryptographic
  operations performed by the HSM**." _(Mod 12 p124)_
- "**AWS has administrative credentials** to manage and maintain the appliance."
- "**Administrative credentials cannot access the HSM partitions** on the appliance." â† *the
  whole separation-of-duties argument in one line* _(Mod 12 p124)_
- "AWS CloudHSM is a **managed hardware security module (HSM) on the AWS Cloud**. It allows
  users to easily add **secure key storage and high-performance crypto operations** to AWS
  applications." _(Mod 12 p124)_

**Advantages and features** _(Mod 12 p124)_

1. "Helps in controlling the encryption keys and cryptographic operations using **FIPS 140-2
   Level 3 validated HSMs**."
2. "Offers flexible integration of user applications using **industry-standard APIs**, i.e.,
   **PKCS#II, JCE, and Microsoft CryptoNG (CNG) libraries**."
3. "Enables users to **export their keys** to most of the other commercially available HSMs,
   subject to user configurations."
4. "**Automates time-consuming administrative tasks** for users such as **hardware
   provisioning**."
5. "Provides users with **access to their HSMs over a secure channel to create users and set
   HSM policies**."
6. "Allows the configuration of **AWS KMS to use the AWS CloudHSM cluster as a custom key
   store** instead of the default KMS key store."

**Secured design — Secure Virtual Private Cloud Access** _(Mod 12 pp124–125)_

- "AWS CloudHSM runs in the **Amazon Virtual Private Cloud (VPC) of users**", enabling use with
  applications running on EC2 instances.
- "Customers with CloudHSM can use **standard VPC security controls** to manage the access to
  HSMs."
- "Applications connected to HSMs using **mutually authenticated SSL channels** are
  established by **HSM client solutions**."
- "The **network latency** between applications and HSMs versus an on-premise HSM can be
  **reduced** because HSMs are located in Amazon data centers **near EC2 instances**."

**Figure 12.64 — Secure Virtual Private Cloud Access, as printed** _(Mod 12 p125)_

| | Statement |
|---|---|
| **A** | "AWS manages the HSM appliance but **does not have access to your keys**." |
| **B** | "**You control and manage your own keys.**" |
| **C** | "Application performance improves owing to the **close proximity to AWS workloads**." |
| **D** | "Secure key storage in **tamper-resistant hardware** available in **multiple regions and availability zones (AZs)**." |
| **E** | "HSMs are located in **VPCs and isolated from other AWS networks**." |

**Separation of duties** _(Mod 12 p125)_

> "**AWS monitors the health and network availability of user HSMs** but **users control the
> HSMs as well as the generation and use of their encryption keys**."

## Encrypting data in transit — TLS + s2n _(Mod 12 p126)_

**To set up the encryption of data in transit** _(Mod 12 p126)_

1. "**Use TLS with every AWS API** to protect data **upload/download and configuration
   files**."
2. "**Use S2N**, a TLS library designed for developers to implement."
3. "**Use AWS Certificate Manager**, a service that lets you easily provision, manage, and
   deploy **SSL/TLS certificates** for use with AWS services."

**Signal to Noise (S2N)** _(Mod 12 p126)_

- "The **open-source implementation of the TLS protocol**; `s2n` is a **C99 implementation** of
  the TLS/SSL protocols that are designed to be **simple, small, fast, and with security as a
  priority**."

| Feature | As printed |
|---|---|
| Protocols implemented | **SSLv3, TLS1.0, TLS1.1, TLS1.2** |
| Encryption | **128-bit and 256-bit AES**; **ChaCha20, 3DES, and RC4** in the **CBC and GCM** modes |
| Forward secrecy | "Supports both **DHE and ECDHE**" |
| TLS extensions | **SNI** (Server Name Indicator), **ALPN** (Application-Layer Protocol Negotiation), **OCSP** (Online Certificate Status Protocol) |

## AWS Certificate Manager _(Mod 12 pp126–129)_

- "ACM is a service that lets you easily **provision, manage, and deploy SSL/TLS
  certificates** for use with the AWS services." _(Mod 12 p126)_
- "ACM can be used to create **wildcard SSL certificates** to secure **subdomains**."
  _(Mod 12 p126)_
- "ACM certificates can be used to secure **multiple domain names and multiple names within
  a domain**." _(Mod 12 p126)_
- Easily **provision, manage, deploy, and renew** SSL/TLS certificates. _(Mod 12 p127)_

### ACM best practices — the six the courseware names _(Mod 12 pp126–128)_

| # | Practice | Courseware detail |
|---|---|---|
| 1 | **AWS CloudFormation** | "Create a **template** that describes the AWS resources that they want to use" · "**Provisions and configures** the resources for users" · "Provision resources that are **supported by ACM** such as **ELB, Amazon CloudFront, and Amazon API Gateway**." |
| 2 | **Certificate Pinning** | "Also called **SSL pinning**." "Used in applications to **validate a remote host by associating that host directly with its X.509 certificate or public key**. Then, the application uses pinning to **bypass the SSL/TLS certificate chain validation**." |
| 3 | **Domain Validation** | "**All domains** specified in a user request should be validated using ACM, **irrespective of whether these domains are owned by the user**, before the **Amazon Certificate Authority (CA)** issues a certificate for the user website. Note that **email/DNS validation can be performed as well**." |
| 4 | **Adding or Deleting Domain Names** | "**Request a new certificate** with the revised list of domain names **instead of adding/removing** domain names from an existing ACM Certificate." |
| 5 | **Opting Out of Certificate Transparency Logging** | "Use the **`Options` parameter** of the **`request-certificate` AWS CLI command** or the **`RequestCertificate` API** to opt-out of transparency logging when certification is requested." |
| 6 | **Turn on AWS CloudTrail** | "Turn on CloudTrail logging **before starting ACM** to monitor your AWS deployments by retrieving a **history of AWS API calls for your account**." |

### ACM architecture with CloudFront _(Mod 12 p128, Fig 12.66)_

- "**ACM automates certificate creation and certificate renewal** and deploys them to AWS
  resources such as **CloudFront distribution** and **Elastic Load Balancing (ELB) load
  balancers**."
- "**Over HTTPS, the users communicate with CloudFront. CloudFront terminates the SSL/TLS
  connection at the edge location.**"
- "**Configure CloudFront to communicate to the origin over HTTP or HTTPS** if needed."
- Diagram flow as printed _(legible labels only)_: users over **HTTPS** → **Amazon CloudFront**
  → **Origins** (**Amazon S3** / **Elastic Load Balancing** instances) over **HTTP/HTTPS**.

### Walkthrough — provision and deploy certificates _(Mod 12 pp128–129)_

> Console click-path, transcribed as printed.

1. "Open the **AWS Certificate Manager Console** and click on **Get started**."
2. "Enter the **Domain name\*** of the site that you need to secure."
3. "Click **Review and request**."
4. "Go to your mail inbox, find the email or emails (**one per domain**) from Amazon
   (**certificates.amazon.com**), and click the link **Amazon Certificate Approvals**."
5. "Click **I Approve**. Certificate is visible in the console."

### Walkthrough — deploy certificates _(Mod 12 p129)_

1. "**Deploy the issued certificate to your elastic load balancers and/or CloudFront
   distributions.**"
2. "For a CloudFront distribution, select **Custom SSL Certificate (example.com)**."

**Figure 12.67 — the two CloudFront SSL options, as printed** _(Mod 12 p129)_

| Option | Printed meaning |
|---|---|
| **Default CloudFront Certificate** (the certificate name OCRs as `C.Cloudfront net)` — garbled, see `unresolved:`) | "Choose this option if you want your users to **use HTTPS or HTTP** to access your content." "**Important:** If you choose this option, CloudFront requires that **browsers or devices support TLSv1 or later** to access your content." _(OCR as printed: "If you choose tlis option. Clou$ront requires tlat browsers or deuces support TLSvI or later to access your content")_ |
| **Custom SSL Certificate (example.com)** | "Choose this option if you want your users to access your content by using an **alternate domain name**, such as `https://www.example.com/logo.jpg`." "You can use either certificates that you created in **AWS Certificate Manager (ACM)** or certificates stored in the **certificate store printed as 'IAN certificate store'** (see `unresolved:`)." |

Related: encryption at rest models — [[12-LO04j-AWS-Encryption-Data-at-Rest]] · ACM architecture
uses ELB — [[12-LO04l-AWS-VPC-and-Network-Security]] · TLS fundamentals —
[[03-LO08-Network-Security-Protocols]]







