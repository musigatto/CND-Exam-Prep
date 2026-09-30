---
type: note
module: "12"
lo: "06"
tags: [bestpractice, process, mod/12, flashcard/12]
topic: "GCP monitoring, logging, Cloud Audit Logs, compliance, security checklist"
exam_weight: unknown
status: done
unresolved:
  - "p301: the compliance list OCR's as 'SSAE16/lSAE 3402 Type II (including SOC2 and 3)', 'IS027001, 27017, 27018', 'FedRamp', 'PCI-DSS', 'HIPAA'. 'IS027001' is read as ISO 27001 and the figure's mash 'DSS ISO soc 27001' is read as PCI-DSS / ISO / SOC — the figure itself does not confirm the standard numbers, so only the body list is asserted."
  - "p301: the body prints 'SSAE16' and 'ISAE 3402' as one token pair, and '(including SOC2 and 3)'. The version formatting ('SOC 2 and SOC 3') is not printed and is not supplied."
  - "p301: the HIPAA entry carries the parenthetical '(GCP supports HIPAA compliance, but it must be calculated by the customer)' - 'calculated' is the printed word (not 'certified' or 'validated'); reproduced as printed and not interpreted."
  - "p300: the product name oscillates between 'Google Cloud's Operation Suite' (heading and figure caption) and 'Google Cloud's operations suite' (pp283, 297). Both forms are kept; the singular 'Operation' in the heading is printed."
  - "p300: the figure is sourced 'Source: https://cloud.google.com' and the surrounding figure labels OCR as 'Logs / EXPLORER / REFINE / SHARE / LEARN' with 'Logs scope' filters ('All', 'cluster.name'). These are screenshot chrome and are not asserted as a product feature list."
  - "p298: the walkthrough step ends mid-word - 'Select Logs Viewer/Logs-based metrics/Logs Router/Resource requirement. Backup LoWrg'. Only the three legible entries (Logs Viewer, Logs-based metrics, Logs Router) are transcribed; the fourth is not guessed."
  - "p298: the two screenshot menu columns OCR as 'OPERATIONS' (Backup and DR, Monitoring, Error Reporting, Trace, Logging, Profiler, Capacity Planner) and the Logs column (Log Analytics, Logs Dashboard, Log-based metrics, Log Router, Logs Storage). These are console menu labels transcribed as printed, not asserted as a curated feature taxonomy."
  - "p299: the figure bullet for System Event Audit logs ends oddly - 'System Event Audit logs using roles Logging/Logs Viewer or Project/Viewer to view' - and the header bullet says 'Audit the access to service account keys' while the body repeats it. Both are printed; the trailing 'to view' is reproduced as printed."
  - "p302: the checklist exists in two renderings - the p302 figure (Google Security Checklist) prints 14 of the items, the p302 body prints 18. The figure is a strict prefix in the same order except that the figure's last two lines ('Do not automatically share the contact information', 'Validate email with SPF, DKIM, and DMARC') are dropped from the middle of the list and re-appended at the end. The 18-item body order is used as canonical here and the figure discrepancy is recorded."
  - "p302: the checklist is titled 'Google Security Checklist' and item 12 names the 'G Suite core services'. The relationship between the Google-branded checklist and the GCP material is not stated in the courseware; no claim that it is GCP-specific is made here."
  - "pp297-302: no numbered console walkthrough other than the two short ones transcribed (p298 navigate to Logging, p299 click Activity) is printed in this range."
---

[[MOC-Module-12]]

# GCP Monitoring, Logging, and Compliance (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)**
> Covers pp. 297–302: monitoring/logging/compliance (p297) · GCP Logging via the console (p298) ·
> Cloud Audit Logs (p299) · Google Cloud's Operations Suite (p300) · GCP compliance (p301) ·
> the security checklist (p302).
> Upstream roles: [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]] (the `roles/logging.*`
> and `roles/viewer|editor|owner` set p299 reuses) · [[12-LO06i-GCP-Defense-in-Depth-and-VPC]]
> (the "real-time monitoring, logging, and alerting" pillar) ·
> [[12-LO06j-GCP-DDoS-Mitigation-and-Network-Best-Practices]] (telemetry best practice).

## GCP monitoring, logging, and compliance — the stated rules _(Mod 12 p297)_

- "**Google Cloud Services generate structured logs that can be easily queried.**" _(figure)_
- "**GCP provides various tools to monitor the accounts and workloads** in the Google Cloud
  Platform."
- "The GCP provides various tools to **collect and analyze logs**. It provides tools that help
  in **monitoring the workloads** in the GCP as well as various infrastructure services."
- "**Google Cloud's operations suite gives insights about the system with the help of
  dashboards, charts, and alerts**" — "is a **logging and monitoring tool** that provides
  insights regarding the system with the help of dashboards, charts, and alerts."
- **Figure rule** — "**Monitor logs using:** GCP Logging from Console · Cloud Audit Logs ·
  Google Cloud's operations suite."

_(Mod 12 p297)_

## GCP Logging via the Console _(Mod 12 p298)_

- **Figure rule** — "Use **GCP Logging (Console), a central place to view and query logs from
  multiple sources**."
- "GCP logging can be used **from the console to view and query logs from multiple
  sources**."

| GCP Logging feature (verbatim) |
|---|
| "**Predefined or custom queries**" |
| "**Create metrics from logs**" |
| "Get a **live stream of logs** coming from multiple resources across the deployed cloud" |
| "**Export logs to other destinations** (Google Cloud Storage, Google BigQuery, or Google Cloud Pub/Sub)" |

_(Mod 12 p298)_

### Walkthrough _(Mod 12 p298)_

1. "From the Google Cloud Console, **navigate to Logging**."
2. "Select **Logs Viewer / Logs-based metrics / Logs Router**" — a fourth entry begins with
   "Resource" but did not OCR (see `unresolved:`).

_(Mod 12 p298, Fig 12.204)_

## Cloud Audit Logs _(Mod 12 p299)_

- "**Cloud Audit Logs support the audit and compliance requirements** by allowing users to
  **track the administrator actions in the GCP**."
- **Figure rule** — "Use **Cloud Audit Logs to regularly audit the access to service account
  keys**."
- "**Audit following logs for each GCP project, folder, and organization:**"

| Audit log type | Role needed, as printed |
|---|---|
| **Admin Activity Audit logs** | "**Logging/Logs Viewer** or **Project/Viewer**" |
| **Data Access Audit logs** | "**Logging/Private Logs Viewer** or **Project/Owner**" |
| **System Event Audit logs** | "roles **Logging/Logs Viewer** or **Project/Viewer** to view" |

_(Mod 12 p299)_

- "**Viewing Cloud Audit Logs** — From the Google Cloud Console, **click on `Activity`** to
  view the Audit Logs." _(p299, Fig 12.205)_

## Google Cloud's Operation Suite _(Mod 12 p300)_

- "Google Cloud's Operation Suite is a **collection of management tools** that help in
  **securing cloud operations**."
- "Google Cloud's Operation Suite is to **integrate monitoring, logging, and trace managed
  services** for applications and systems running on Google Cloud and beyond."
- "**Use it to collect metrics, traces, and logs** across applications and Google cloud and
  **determine a unique dashboard** that helps cloud admins to **monitor the GCP and
  applications easily**."

**The log path through the suite** _(p300, as printed)_

- "Its **Log Router** allows customers to **control where logs are sent**."
- "**All logs, including audit logs, platform logs, and user logs, are sent to the Cloud
  Logging API** where they **pass through the log router**."
- "The **log router checks each log entry against existing rules** to determine **which log
  entries to discard, which to ingest, and which to include in exports**."

_(Mod 12 p300)_

## GCP compliance _(Mod 12 p301)_

- "**GCP infrastructure is certified for a growing number of compliance standards and
  controls**, and undergoes **several independent third-party audits** to test for **data
  safety, privacy, and security**."
- "The GCP is **certified for compliance standards and controls**; it underwent **numerous
  third-party verification** for **data safety, security, and privacy**."

| Compliance, as printed |
|---|
| **SSAE16/ISAE 3402 Type II** *(including SOC2 and 3)* |
| **ISO 27001, 27017, 27018** |
| **FedRamp** |
| **PCI-DSS** |
| **HIPAA** — "GCP supports HIPAA compliance, but **it must be calculated by the customer**" |

_(Mod 12 p301)_

## Google security checklist — all 18 items, verbatim and in order _(Mod 12 p302)_

1. Enforce two-step verification for users.
2. Do not use a super admin account for daily activities.
3. Do not remain signed into an idle super admin account.
4. Set up admin email alerts.
5. Review the admin audit log.
6. Add recovery options to admin accounts.
7. Enroll a spare security key.
8. Save the backup codes.
9. Use unique passwords.
10. Prevent password reuse with password alert.
11. Regularly review activity reports and alerts.
12. Know and approve the third parties that can access the G Suite core services.
13. Create a whitelist of trusted apps.
14. Limit external calendar sharing.
15. Set up underlying Chrome OS and Chrome Browser policies.
16. Warn users when chatting outside their domain.
17. Do not automatically share the contact information.
18. Validate email with SPF, DKIM, and DMARC.

_(Mod 12 p302 — the p302 figure prints a 14-item subset; see `unresolved:`)_

**Grouped by what they defend** _(grouping is this note's, the items above are the printed
order)_

| Cluster | Items |
|---|---|
| **Account / admin hygiene** | 1, 2, 3, 6, 7, 8, 9, 10 |
| **Detection & auditing** | 4, 5, 11, 18 |
| **Third-party & data-exposure control** | 12, 13, 14, 16, 17 |
| **Endpoint / platform policy** | 15 |

## The three-layer picture

| Layer | Named tool | Printed capability |
|---|---|---|
| **Log source** | "Google Cloud Services **generate structured logs** that can be easily queried" | collection |
| **Query / derive** | **GCP Logging (Console)** | view and query from multiple sources, predefined or custom queries, create metrics from logs, live stream, export to Cloud Storage / BigQuery / Pub/Sub |
| **Govern** | **Cloud Audit Logs** | track administrator actions; audit access to service account keys; three log types per project/folder/organization |
| **Route & analyse** | **Operation Suite / Log Router** | all logs (audit, platform, user) go to the Cloud Logging API through the log router, which discards / ingests / exports per rule |
| **Prove** | **Compliance** | certified standards + independent third-party audits |

_(Mod 12 pp297–301)_

## Cards

Which three tools does the courseware name for monitoring logs
?
GCP Logging from Console · Cloud Audit Logs · Google Cloud's operations suite — and Google Cloud services generate structured logs that can be easily queried

The four GCP Logging console features
?
Predefined or custom queries · create metrics from logs · a live stream of logs from multiple resources across the deployed cloud · export logs to other destinations (Google Cloud Storage, Google BigQuery, or Google Cloud Pub/Sub)

The three Cloud Audit Logs types and the roles that read them
?
Admin Activity Audit logs — Logging/Logs Viewer or Project/Viewer · Data Access Audit logs — Logging/Private Logs Viewer or Project/Owner · System Event Audit logs — Logging/Logs Viewer or Project/Viewer. Audit the access to service account keys regularly, and view them from the console by clicking Activity

What is Google Cloud's Operation Suite and what does the log router do
?
A collection of management tools that integrate monitoring, logging and trace managed services for applications and systems on Google Cloud and beyond, used to collect metrics, traces and logs and build dashboards, charts and alerts. All logs — audit, platform and user — are sent to the Cloud Logging API and pass through the log router, which checks each entry against existing rules to decide which to discard, which to ingest, and which to include in exports

Which compliance standards are printed for GCP
?
SSAE16/ISAE 3402 Type II (including SOC2 and 3) · ISO 27001, 27017, 27018 · FedRamp · PCI-DSS · HIPAA — with the note that GCP supports HIPAA compliance but it must be calculated by the customer

The four administrative-hygiene items on the Google security checklist
?
Enforce two-step verification for users · do not use a super admin account for daily activities · do not remain signed into an idle super admin account · do not automatically share the contact information
