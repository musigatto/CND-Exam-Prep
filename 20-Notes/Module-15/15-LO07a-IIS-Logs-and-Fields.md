---
type: note
module: "15"
lo: "07"
tags: [tool, protocol, concept, mod/15]
topic: "IIS logs: default location, enabling logging, W3C Extended format"
exam_weight: unknown
status: done
unresolved:
  - "p99 the default-location callout renders some path separators as a slash or as the letter l; backslashes are shown here, which is also how the p99 body prose prints them."
  - "p99 the leading percent sign of the IIS 8.0 callout entry was not legible; it is restored from the IIS 10.0 entry printed directly beneath it, which reads the same."
  - "p100 the 'IIS Log File Format' section is broken by the page break mid-sentence: 'Different log formats use different time' - it completes on p101 as 'zones to determine when a specific event is generated.'"
  - "p101 Table 15.15 spans pp101–103. Only the p101 rows are reproduced here; the p102 rows are carried in 15-LO07b-IIS-Field-Tables-and-Request-Types."
  - "p101 the Server name row description cell prints 'Windows hostname assigned to the system that generated the log entry' - no article is legible before 'Windows'."
---

[[MOC-Module-15]]

# IIS Logs and Fields (§15.07)

> **LO#07: Discuss log monitoring and analysis on web servers** _(Mod 15 p3)_
> Covers pp98–101.

Section objective _(Mod 15 p98)_: "The objective of this section is to explain how to monitor and analyze
logs in a web server. Specifically, it demonstrates how to monitor and analyze **Internet Information
Services (IIS)** and **Apache** logs."

Related: [[15-LO07b-IIS-Field-Tables-and-Request-Types]] ·
[[15-LO07c-Monitoring-and-Analyzing-IIS-Log-Files]] ·
[[15-LO07d-Apache-Error-and-Access-Logs]] ·
[[15-LO01c-Typical-Log-Format-and-Logging-Approaches]].

## Why IIS logs matter _(Mod 15 p99)_

Figure 15.27, as printed:

- IIS is a **web server for Windows server that hosts anything on the Web**.
- IIS "consists of **many log files**; log file formats provide different information of the users IP
  address, **different Sites visited by the user with date and time**".
- "IIS log file provides useful information regarding **the person who visited your site, what
  information was viewed and when it was viewed**, the activity of various web applications, etc."
- "**Proper analysis of IIS log files provides demographic information and usage of IIS server.**"

In the body _(Mod 15 p99)_: analysis also gives **demographic information and usage of the IIS server**; "by
monitoring data usage, web providers can effectively **organize their services to support specific
regions, time frames, or IP ranges**", and "**Log filters** also facilitate providers to determine
only that specific data that is required for analysis."

## Default log-file location _(Mod 15 p99)_

The default location **differs by IIS version**:

| Version | Default location |
|---|---|
| IIS 6.0 | `%system32%\LogFiles\W3SVCN` |
| IIS 7.0 | `%SystemDrive%\Inetpub\Logs\LogFiles\w3svcN` |
| IIS 8.0 | `%SystemDrive%\inetpub\logs\LogFiles` |
| IIS 10.0 | `%SystemDrive%\inetpub\logs\LogFiles` |

Note the pattern: **the `W3SVC` instance sub-folder is appended in 6.0 and 7.0; 8.0 and 10.0 share one
path.** The body prose on the same page states the identical list.

### When the log files are not in the default location _(Mod 15 pp99–100)_

Numbered walkthrough, as printed:

1. **Open IIS Manager.**
2. **Double click on the `Logging` icon** that appears in the middle pane under the section `IIS`.
3. "Logging setting screen will appear, where you can find **the location of the IIS log files under
   the `Directory` field**."
4. "**Navigate to the IIS log files location mentioned in the `Directory` field.** The folders store
   the log files having a naming pattern such as **`W3SVC1`, `W3SVC2`**, etc."

## IIS log file formats _(Mod 15 pp100–101)_

IIS "logs keep records of site activity in **different formats**":

| Format | Character |
|---|---|
| **W3C Extended log file format** | *customizable* — "different properties can be selected for each request" |
| **IIS log file format** | *fixed* (cannot be customized) |
| **NCSA Common log file format** — National Center for Supercomputing Applications | *fixed* |

- "**All these log file formats are ASCII text formats.**"
- "In **NCSA and IIS log format, logged data is fixed for each request**. However, in **W3C Extended
  log format, logged data is not fixed**; instead, different properties can be selected for each
  request."
- "Different log formats use different time zones to determine when a specific event is generated.
  **W3C Extended format uses Coordinated Universal Time (UTC) whereas other formats use local time.**"

> Exam discriminator: **W3C = UTC + selectable fields. IIS and NCSA = local time + fixed fields.**

## W3C Extended log file format _(Mod 15 p101)_

> "It is a **customizable ASCII format with different properties, separated with spaces**. This format
> enables **removal of unwanted property fields to limit the log size**. Here, log records are recorded
> in **UTC time zone**."

Sample, with properties "such as time, client IP address, method, URI stem, protocol status, and
protocol version":

```text
#Software: Internet Information Services 10.0
#Version: 1.0
#Date: 2019-05-02
#Fields: time c-ip cs-method cs-uri-stem sc-status cs-version
17:42:15 172.16.255.255 GET /default.htm 200 HTTP/1.0
```

Note the shape: **four `#` comment/header lines, then one space-separated record per request.**

### Table 15.15: Types of Fields in "W3C Extended" Log File Format — rows printed on p101

Columns `Field name` · `Description` · `Uses` — reproduced verbatim. The table continues on p102
(see [[15-LO07b-IIS-Field-Tables-and-Request-Types]]).

| Field name | Description | Uses |
|---|---|---|
| Date (`date`) | The date of the request | Event correlation |
| Time (`time`) | The UTC time of the request | Event correlation, determine time zone |
| Client IP address (`c-ip`) | The IP address of the client or proxy server that sent the request | Identify user or proxy user |
| Username (`cs-username`) | The username used to authenticate to the resource | Identify compromised user passwords |
| Service name (`s-sitename`) | The W3SVC instance number of the site accessed | Can verify the site accessed if the log files are later moved from the system |
| Server name (`s-computername`) | Windows hostname assigned to the system that generated the log entry | Can verify the server accessed if the log files are later moved from the system |
| Server IP address (`s-ip`) | The IP address that received the request | Can verify the IP address accessed if the log files are later moved from the system or if the server is moved to a new location |

Read the **`Uses`** column as an examiner's hint list: every one of these fields exists to answer a
question — *who* (`c-ip`, `cs-username`), *what* (`cs-uri-stem`), *did it work* (`sc-status`,
`sc-win32-status`), *was it abused* (`cs-method`, `cs-version`, `time-taken`), *where from*
(`cs(Referer)`).





