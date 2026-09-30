---
type: note
module: "12"
lo: "04"
tags: [tool, bestpractice, mod/12, flashcard/12]
topic: "AWS account monitoring services and IAM Identity Center single sign-on"
exam_weight: unknown
status: done
unresolved:
  - "p105 Figure 12.51 'Enable IAM Identity Center': the banner is legible for its strapline ('IAM Identity Center (successor to AWS Single Sign-On) — Manage workforce access to multiple AWS accounts and cloud applications') but the checklist text OCRs as 'started / Enable IAM / and features / use cases'. Only the strapline is used."
  - "p106/p107 Figure 12.52 'Identity Source': the breadcrumb 'IAM Identity Center > Settings > Change identity source' and the three option names are legible; the per-option explanation text OCRs as 'ard in Center. ugr. an through thr Avr (3 Active Directory Will manage all ard qrwpz In .-WS Managed AD. ar can D-rrct-y ty uvn9 AVO, in through the AWS / External identity provider You au users and in identitv grov.det n to ttv AWS Atte tv can AWS arcmntg and atinnq.' Unusable. The three identity sources are described from the p106/p107 body prose instead."
  - "p108 Figure 12.53 'Specify Permission Set': two tabs are legible ('Specify policies', 'Permissions boundary') each showing 'Not set'; the rest of the screenshot did not OCR."
  - "p109 Figure 12.54 'AWS Users and Groups': the group name after 'IAM > Groups >' did not OCR and the two Inline Policies policy-ARN rows OCR as 'DtsaNe'/'Datal'. The managed policy names 'AmazonS3FullAccess' and 'AdministratorAccess' are legible; the third prints as 'FullAdrnhPmissioru' and is NOT resolved to a policy name."
  - "p111 Figure 12.56 'Management Console from the User Portal': the portal chrome OCRs as 'Single Sign-On / AWS Account / 1 ) Todd Rowe - Bengard / MFA devices / I Sign Out / Q Search / Managernent console / I Command tine or programmatic access T-ms'. The two account/alias names are not confidently readable; only 'MFA devices', 'Sign Out', 'Management console' and 'Command line or programmatic access' are used."
  - "p112/p113 Figures 12.59 and 12.60 are screenshots ('Selecting Expanded Desktop View', 'Showing AWS IAM Identity Center username in Amazon EC2 Windows instance event log') whose tab names and event-log entries did not OCR. The only fact taken from p113 is the body sentence that AWS Fleet Manager used the credentials it created to sign into the EC2 Windows server from the Windows Event Viewer."
  - "p110 Figure 12.55 'AWS IAM Identity Center Setting Summary': the settings rows are legible (Go to settings; Identity source = Identity Center directory; Region = US East (N. Virginia); AWS access portal URL; Customize) but the portal URL OCRs as 'https://o L. awsapps.com/start' and is NOT completed to a hostname."
  - "p115 Figure 12.61 'Single Sign-On Page': a garbled welcome screenshot. Only the three recommended-setup step headings survive ('Choose your identity source', 'Manage SSO access to your AWS accounts', 'Manage SSO access to your cloud applications'); the body text is unreadable and not quoted."
  - "p110 Figure 12.55 'Recommended setup steps' is a three-step banner but the OCR only preserves Step 1 and Step 2 labels; no Step 3 label is asserted."
---

[[MOC-Module-12]]

# AWS Account Monitoring and Identity Center SSO (§12.04)

> **LO#04 — Discuss security in Amazon Cloud (AWS)** · **monitor activity of AWS account**
> (pp103–104) · **Identity Center: enable single sign-on** (pp105–110) · **enable SSO access to
> Amazon EC2 Windows instances** (pp111–115).
> Covers pp. 103–115.

## Monitor activity of the AWS account — the logging services _(Mod 12 pp103–104)_

- "The logging features are used to determine the **user actions** in the AWS account and the
  **resources used by the users**." _(p103)_
- "These log files display: **time and date of actions**; **source IP** for an action; **actions
  that failed owing to inadequate permissions**, among others." _(p103)_

| Service | Role | Printed detail |
|---|---|---|
| **Amazon CloudFront** | Monitor the user requests received by CloudFront | "These access logs are available for **web and RTMP distributions**. Logging can be enabled while **creating or updating a distribution**. To enable logging, select an **Amazon S3 bucket** for the access logs. … The log files for **multiple distributions can be stored in the same bucket**. After enabling logging, specify an **optional prefix** for the file names… It is recommended to **not use the same bucket** for log files if **Amazon S3 is used as the origin**; a **separate bucket** should be used for simplified maintenance." _(p103)_ |
| **AWS CloudTrail** | View account activities and events for supported services | "**CloudTrail is enabled on the AWS account.** It records the activities of the AWS account in a **CloudTrail event**. The recent events in the CloudTrail console can be obtained by viewing the **event history**. Next, **create a trail** for the **ongoing record** of activities and events." _(p103)_ |
| **AWS Config** | Detailed historical configuration information | "including **IAM users, groups, roles, and policies**." _(p104)_ |
| **Amazon S3** | Details of access requests to buckets | "Amazon S3 also supports **Audit Logs** that list the requests made against S3 resources for complete visibility regarding **who is accessing which data**." _(p104)_ |
| **Amazon CloudWatch logs** | Monitor, store and access log files | "from **Amazon EC2** instances, **AWS CloudTrail**, or **Route 53**; this helps in **centralizing logs** from all systems, applications, and AWS services." _(p104)_ |

### CloudTrail features _(Mod 12 p104)_

| Feature | Printed statement |
|---|---|
| **Event history** | "allows users to **view, search, and download** the recent AWS account activities" |
| **Log file integrity validation** | "helps in log file integrity validation in the **IT security and auditing** processes" |
| **Log file encryption** | "allows the encryption of all log files delivered to specified Amazon S3 buckets using **Amazon S3 server-side encryption (SSE)**" |
| **Data events** | "insights regarding the resource (**'data plane'**) operations performed **on or within the resource itself**" |
| **Management events** | "insights about the **management ('control plane')** operations performed on resources in the AWS account" |
| **CloudTrail Insights** | "helps in **identifying unusual activities** in AWS accounts" |

### AWS Config features _(Mod 12 p104)_

| Feature | Printed statement |
|---|---|
| Configuration history of AWS resources | provides the configuration history |
| Configuration history of software | "record the changes in **software configuration** within the Amazon EC2 instances and servers **running on-premise**, as well as the servers and virtual machines in environments provided by **other cloud providers**" |
| Resource relationships tracking | "allows **discovering, mapping, and tracking** the AWS resource relationships in your account" |

### CloudWatch logs features _(Mod 12 p104)_

| Feature | Printed statement |
|---|---|
| **Query log data** | "Amazon CloudWatch log can help in **searching and analyzing** the log data and perform **queries** to respond to operational issues" |
| **Monitor AWS CloudTrail logged events** | "creating **alarms in CloudWatch** and receive **notifications of particular API activity** as captured by CloudTrail; these notifications can be used for **troubleshooting**" |
| **Monitor logs from Amazon EC2 instances** | "use CloudWatch Logs to **monitor applications and systems** using log data" |

Mnemonic: **F**ront**E**nd logs → **T**rail (CloudTrail) · **C**onfig history · **S**3 audit logs ·
**W**atch (CloudWatch). Data plane = **data events**; control plane = **management events**.

Upstream: [[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

## Identity Center: enable single sign-on _(Mod 12 pp105–110)_

- "Organizations integrate Identity Center with applications (**Amazon SageMaker Studio, AWS
  Systems Manager Change Manager, and AWS IoT SiteWise**) for **zero-configuration
  authentication and authorization**." _(p105)_
- "To enable SSO access to AWS applications using Identity Center, use the **IAM Identity
  Center's identity store** which comprises **user and group attributes, excluding sign-in
  credentials**." _(p105)_
- "To use Identity Center enabled AWS applications, **enable IAM Identity Center firstly** to
  allow them access." _(p105)_
- Slide objective: "Organizations can use the IAM Identity Center's **preconfigured settings** to
  configure **SSO access to SAML 2.0**." _(p105)_

**Step 1 — Enable AWS IAM Identity Center** _(Mod 12 p105)_

1. Log in to the AWS Management Console with the **root user** credentials.
2. Open the **IAM Identity Center** console and select **Enable** under **Enable IAM Identity
   Center**.
3. Select **Create AWS organization** to create an organization if haven't been created earlier.
4. "AWS organization will send the **verification email automatically** to the registered email
   address to verify."

**Step 2 — select the identity source** _(Mod 12 pp106–107)_

> "The identity source in IAM Identity Center defines **where the users and groups are
> managed**. There are **three identity sources**; an administrator can select the identity
> source as per the requirements." _(Mod 12 p106)_

| # | Identity source | Printed description |
|---|---|---|
| 1 | **Identity Center directory** | "If the IAM Identity Center is enabled for the **first time**, it is automatically configured with an Identity Center directory as the **default** identity source. An administrator can create users and groups, and **assign their level of access** to the AWS accounts and applications in the Identity Center directory." |
| 2 | **Active Directory** | "an administrator can continue managing users in either the **AWS Managed Microsoft AD** directory using **AWS Directory Service** or the **self-managed directory in Active Directory (AD)**." |
| 3 | **External identity provider** | "an administrator can manage users in an **external identity provider (IdP) such as Okta or Azure Active Directory**." |

_(Mod 12 pp106–107)_

**Step 3 — create an administrative permission set** _(Mod 12 pp107–108)_

1. Login to AWS with **root user** and open the IAM Identity Center console.
2. In the navigation pane, under **Multi-account permissions**, select **Permission sets**.
3. Select **Create permission set**.
4. **Select permission set type** page → keep the **default** settings → **Next**.
5. **Specify permission set details** page → keep the **default** settings → **Next**.
6. **Review and create** page → confirm the permission set type is **`AdministratorAccess`**.
7. "Review the AWS managed policy and confirm that it is **`AdministratorAccess`**. Select
   **Create**."

**Step 4 — set up AWS account access for an administrative user** _(Mod 12 pp108–109)_

1. Login with **root user** → IAM Identity Center console → **Multi-account permissions** →
   **AWS accounts**.
2. Select the **check box** next to the AWS account to assign administrative access.
3. Select **Assign users or groups**.
4. On **Assign users and groups to "AWS-account-name"**, select the user → **Next**.
5. On **Assign permission sets to "AWS-account-name"**, select the **`AdministratorAccess`**
   permission set → **Next**.
6. On **Review and submit assignments**, review the selected user and permission set → **Submit**.

**Step 5 — sign in to the AWS access portal** _(Mod 12 pp109–110)_

1. Login with **root user** → IAM Identity Center console → **Dashboard**.
2. Under **Settings summary**, copy the **AWS access portal URL**.
3. Paste the URL in the browser and press **Enter**.
4. Sign in using **Active Directory**, an **external identity provider (IdP)**, or the **default
   Identity Center directory**, as your identity source.
5. Select the **AWS account icon** in the portal — the **account name, account ID, and email
   address** appear.
6. Select the name of the account to display the **`AdministratorAccess`** permission set and
   select the **Management Console** link. "The role will appear in the AWS access portal as
   **`AdministratorAccess/username`**."
7. "If the administrative access to the AWS account is successfully finished, it will **redirect
   to the AWS access portal**."
8. "Open the browser and set up IAM Identity Center, and **log out from the AWS account root
   user**."

**p110 Figure 12.55 — Recommended setup steps, as printed** _(Mod 12 p110)_

> - **Step 1 — Choose your identity source.** "The identity source is where you **administer users
>   and groups**, and is the service that **authenticates your users**."
> - **Step 2 — Manage access to multiple AWS accounts.** "Give users and groups access to
>   **specific AWS accounts in your organization**." *Or* — "Set up **Identity Center enabled
>   applications**".

Settings summary rows shown _(Mod 12 p110)_: **Go to settings** · Identity source =
**Identity Center directory** · Region = **US East (N. Virginia)**, `us-east-1` · **AWS access
portal URL** · **Customize** (URL host unreadable, see `unresolved:`).

**Step 6 — set up access to AWS applications** _(Mod 12 p110)_

1. Open the IAM Identity Center console → **Applications** → **Add application**.
2. Under **Applications**, search for an application and choose it from the list → **Next**.
3. Under **Configure application**, the **Display name** and **Description** pre-populate with
   the chosen application; both can be edited.
4. Under **IAM Identity Center metadata**:
   - **Download** → the identity provider metadata under **IAM Identity Center SAML metadata
     file**.
   - **Download certificate** → the identity provider certificate under **IAM Identity Center
     certificate**.
5. Under **Application metadata**, one of:
   - **Upload application SAML metadata file** → **Choose file** to find and select it; or
   - if no metadata file is available, **Manually type your metadata values** and provide the
     **Application ACS URL** and **Application SAML audience** values.
6. **Submit**, then see the details page of the application that was added.

## Enable SSO access to Amazon EC2 Windows instances _(Mod 12 pp111–113)_

- "Users can securely access their **EC2 Windows instances with the existing credentials
  provided by their organizations and MFA devices**. They do not have to **share administrator
  credentials, repeatedly access credentials, or configure remote access client software**."
  _(p111)_
- "Organizations can grant access **centrally across multiple AWS accounts** to EC2 Windows
  instances." _(p111)_

| # | Action |
|---|---|
| 1 | Go to the **AWS IAM Identity Center user portal URL** and login as **any AWS IAM Identity Center user** |
| 2 | Select **Management console** → go to the **Fleet Manager** console that shows the **EC2 Windows managed instance** |
| 3 | Choose a managed Windows instance → **Instance actions** → **Connect with Remote Desktop** |
| 4 | Select **IAM Identity Center** and then **Connect** |
| 5 | "You will **automatically be logged in** using your AWS IAM Identity Center credentials. If connecting to the instance at **first time**, a **new local user will be created**." |
| 6 | After connecting, see the instance in the **All sessions** tab — "enabling to have **up to four concurrent sessions in a single view**". Select the **Instance ID** tab for a single session view. |
| 7 | "From the single session tab, see that a **local Windows Server user is created by AWS Fleet Manager** for the AWS IAM Identity Center user (here, it is **`demoUser1`**)." |
| 8 | "After creating the local user, **AWS Fleet Manager used the credentials it created to sign into the EC2 Windows server from the Windows Event Viewer**, giving an **individual user logging on** EC2 Windows servers." |

_(Mod 12 pp111–113)_

## Enable SSO access to SAML 2.0 cloud applications _(Mod 12 pp113–114)_

- "Organizations can use the IAM Identity Center's **preconfigured settings** to configure SSO
  access to **SAML 2.0 supported cloud applications** such as **Datadog, SumoLogic, Salesforce,
  Box, Microsoft 365**, etc." _(p113)_
- "Most of the cloud applications provide **instructions to set up the trust** between IAM
  Identity Center and the cloud app's service provider." "Once the application is configured,
  **assign access to the groups/users that require application**." _(p113)_
- Prerequisite printed: "To efficiently set up the trust, ensure that the **service provider's
  metadata exchange file is available** before beginning the below steps. Otherwise, you will
  have to **configure it manually**." _(p113, grammar as printed)_
- The steps repeat Step 6 (p110) with one addition: "**Note:** These files would be **required
  later** while setting up the cloud application **from the service provider's website**."
  _(p114)_

## Multi-account access to AWS accounts _(Mod 12 p114)_

- "The **assigned roles in AWS accounts are displayed on the organization clients' personalized
  web user portal at one place**. Allow clients to use their **directory credentials** for
  single sign-on (SSO) access to multiple AWS accounts." _(p114)_
- "To assign permissions **centrally for each AWS account**, use **permission sets**. A
  **permission set tells what users can do in the AWS Management Console**." _(p114)_
- **Sign-in process** _(p114)_: use directory credentials to sign into the **AWS access
  portal** → choose the **AWS account name** for federated access to the Management Console for
  that account → users assigned **multiple permission sets choose which IAM role to use**.

**Steps — assign user or group access to AWS accounts** _(Mod 12 pp114–115)_

1. Open the IAM Identity Center console → **AWS accounts** under **Multi-account permissions**.
2. "On the AWS accounts page, a **tree view list of your organization** appears. Select the
   **check box** next to one or more AWS accounts."
3. Choose **Assign users or groups**.
4. On **Assign users and groups to "AWS-account-name"**: **Users** tab → select one or more users;
   **Groups** tab → select one or more groups; expand **Selected users and groups** with the
   **sideways triangle** to confirm the selection → **Next**.
5. On **Assign permission sets to "AWS-account-name"**: select one or more permission sets, or
   under **Permission sets** select the existing permission sets to apply → **Next**.
6. On **Review and submit assignments**: review the selected users, groups, and permission sets
   → **Submit**.

Figure 12.61's three recommended-setup headings, as printed _(Mod 12 p115)_: **Choose your
identity source** · **Manage SSO access to your AWS accounts** · **Manage SSO access to your
cloud applications**.

Upstream: [[12-LO04b-AWS-IAM-Features]] · federated access background:
[[03-LO03-IAM-Authentication-Authorization]] · logging context:
[[12-LO02c-Cloud-Monitoring-Logging-and-Compliance]]

## Cards

What the AWS log files display
?
Time and date of actions · source IP for an action · actions that failed owing to inadequate permissions, among others

The five logging services and what each is for
?
Amazon CloudFront — user requests received, web and RTMP distributions · AWS CloudTrail — account activities and events, event history plus a trail for the ongoing record · AWS Config — detailed historical configuration of AWS resources · Amazon S3 — details of access requests to buckets, plus Audit Logs · Amazon CloudWatch logs — centralize logs from EC2, CloudTrail, and Route 53

CloudTrail — data events, management events, Insights and log encryption
?
Data events — resource ('data plane') operations on or within the resource itself · management events — management ('control plane') operations on resources in the account · CloudTrail Insights — identifies unusual activities · log file encryption — Amazon S3 server-side encryption (SSE) on log files delivered to S3 buckets

The three IAM Identity Center identity sources
?
Identity Center directory — the default when Identity Center is first enabled · Active Directory — AWS Managed Microsoft AD via AWS Directory Service, or a self-managed AD · External identity provider — e.g. Okta or Azure Active Directory

The six steps to implement SSO with IAM Identity Center
?
Step 1 enable IAM Identity Center (root user) · Step 2 select the identity source · Step 3 create an administrative permission set · Step 4 set up AWS account access for an administrative user · Step 5 sign in to the AWS access portal · Step 6 set up access to AWS applications

How SSO to an EC2 Windows instance works
?
AWS IAM Identity Center user portal → Management console → Fleet Manager → Instance actions → Connect with Remote Desktop → select IAM Identity Center and Connect; on first connect a new local user is created and AWS Fleet Manager uses the credentials it created to sign in — the All sessions tab then shows up to four concurrent sessions in a single view
