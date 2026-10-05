---
type: note
module: "15"
lo: "07"
tags: [tool, protocol, concept, command, port, mod/15]
topic: "Apache access and error logs: locations, common and combined log formats"
exam_weight: unknown
status: done
unresolved:
  - "p108 the page states the RHEL/Red Hat/CentOS/Fedora default access-log path as /var/log/httpd/access_log but then gives the RHEL tail command with the path /etc/httpd/logs/access_log. The page contradicts itself; both are reproduced as printed. The same /etc/httpd/logs/ vs /var/log/httpd/ split appears for the error log on p109."
  - "p108 the tail option is printed as a hyphen before 100 (the OCR alternates between a hyphen, an em dash and the digits rendered as 1oo); rendered here as tail -100 and not upgraded."
  - "p109 the example access-log entry was legible only on the full-page pass; tighter re-crops of the same band returned nothing. The token 808840 and the single spaces between fields are reproduced as read."
  - "p109 the example error-log entry prints the client address as '50.0.134.125' and the path in upper case as /VAR/WWW/FAVICON.ICO. Kept as printed, not normalised."
  - "p110 Table 15.17 prints the Remote Logname directive so that it reads as the digit 1, but the same page's own LogFormat example prints it as %l. Rendered here as %l because that is the form the page prints in the format string."
  - "p110 Table 15.17 prints %a for Client IP Address, %h for Client Hostname and %A for Server IP Address; reproduced exactly, not corrected."
  - "p111 Table 15.18 prints the Referrer field directive with a double r as \"%{Referrer}\" while the LogFormat example line and the explanatory paragraph on the same page print Referer with a single r. Both forms kept as printed."
  - "p112 Table 15.19 'Field directive' column: legible only for Filename (%f), Request Method (%m), Transport Protocol (%H), Server Port (%P), Request Stem (%U) and Time to Serve (%T). Server Port and Server Process ID BOTH read %P in the scan. The directives for Request Query String, Server Name, Session Identifier Field, Visitor Identifier Field and General Purpose Fields 1-10 could not be read and are left blank."
---

[[MOC-Module-15]]

# Apache Error and Access Logs (§15.07)

> **LO#07: Discuss log monitoring and analysis on web servers** _(Mod 15 p3)_
> Covers pp108–112.

Related: [[15-LO07e-Apache-Access-Log-Fields-and-Monitoring]] ·
[[15-LO07a-IIS-Logs-and-Fields]] ·
[[15-LO03c-Commands-to-Monitor-and-Analyze-Linux-Logs]] ·
[[15-LO04b-Mac-Types-of-Logs-and-Log-Files]] ·
[[15-LO01c-Typical-Log-Format-and-Logging-Approaches]].

> **Do not confuse** the CUPS `access_log` / `error_log` in
> [[15-LO04b-Mac-Types-of-Logs-and-Log-Files]] — those are **printer** logs, not Apache.

## Two primary log files _(Mod 15 p108)_

"Apache server maintains **two primary log files: access log and error log**."

Figure caption, as printed: **Two Primary Log Files of Apache Server**

| | Access Log | Error Log |
|---|---|---|
| Records | "Record file of **all incoming and processed requests**" | "Apache error log records the **problems encountered in the server**" |
| Configured by | **`CustomLog` directive** | **`ErrorLog` directive** |

> "Apache monitors the usage of the server by extensively tracking the log files… Apache provides
> various mechanisms to log **everything — from the first request to the final resolution of
> connection, including errors, alerts, warnings**, etc." _(Mod 15 p108)_

## Apache access log _(Mod 15 p108)_

> "This log records **all incoming and processed requests** into a log file. Its location and content
> are managed by the **`CustomLog` directive**, and **its format is highly configurable**. The
> information recorded by access log files helps in **analyzing web traffic to the server**."

**Default location depends upon the distribution:**

| Distribution | Default access-log path |
|---|---|
| RHEL / Red Hat / CentOS / Fedora Linux | `/var/log/httpd/access_log` |
| Debian / Ubuntu Linux | `/var/log/apache2/access.log` |
| FreeBSD | `/var/log/httpd-access.log` |

View the **last 100 lines**:

```bash
# RHEL / Red Hat / CentOS / Fedora Linux
sudo tail -100 /etc/httpd/logs/access_log

# Debian / Ubuntu Linux
sudo tail -100 /var/log/apache2/access.log
```

> Note the filename convention difference: **Red Hat uses `access_log` (underscore), Debian/Ubuntu
> uses `access.log` (dot).** The RHEL path in the command above does **not** match the RHEL default
> path stated above it — see `unresolved:`.

Example entry _(Mod 15 p109)_:

```text
10.185.248.71 - - [09/JAN/2018:19:12:06 +0000] 808840 "GET /INVENTORYSERVICE/INVENTORY/PURCHASEITEM?USERID=20253471&ITEMID=23434300 HTTP/1.1" 500 17 "APACHE-HTTPCLIENT/4.2.6 (JAVA 1.5)"
```

Read against the field list further down: client IP `-` (logname) `-` (user) `[date +zone]` — request
line — status **`500`** — bytes `17` — the `Apache-HttpClient` user agent.

## Apache error log _(Mod 15 p109)_

> "This log records the **problems encountered in the server**. It records both **minor problems (such
> as startup and shutdown messages)** and **major problems (such as warnings related to specific event
> and configuration)**. Its location is configured through the **`ErrorLog` directive**. In case of any
> problem, **this log file is the first resource to be checked out using `cat`, `grep`, or any other
> UNIX/Linux command line utilities**. This log file provides information regarding problems that have
> occurred and **how to fix them**."

| Distribution | Default error-log path |
|---|---|
| RHEL / Red Hat / CentOS / Fedora Linux | `/var/log/httpd/error_log` |
| Debian / Ubuntu Linux | `/var/log/apache2/error.log` |
| FreeBSD | `/var/log/httpd-error.log` |

```bash
# RHEL / Red Hat / CentOS / Fedora Linux
sudo tail -100 /etc/httpd/logs/error_log

# Debian / Ubuntu Linux
sudo tail -100 /var/log/apache2/error.log
```

Example entry:

```text
[FRI JAN 12 18:04:18 2019] [ERROR] [CLIENT 50.0.134.125] FILE DOES NOT EXIST: /VAR/WWW/FAVICON.ICO
```

Note the shape: **`[timestamp] [ERROR] [CLIENT <ip>] <message>`** — unlike the access log, there is no
request line and no status code.

## Log Format _(Mod 15 pp109–112)_

> "Apache generally uses the common log formats, namely, **Apache common log format** and **Apache
> combined log format**." _(Mod 15 p109)_

### Apache common log format _(Mod 15 pp109–110)_

> "In this log format, **basic web log parameters are included**. It **only displays information that
> is needed to determine the host and the request**. Additionally, information about the **agent,
> cookie string, domain name, referrer, time to serve**, etc. **is excluded** in this format."

```apache
LogFormat "%h %l %u %t "%r" %>s %b" common
```

> "The above format string includes **percent directives**, which direct the server to log a specific
> piece of information. If the format string includes **literal characters, they will simply be copied
> into the log output**. The character with quotation marks (`"`) **can be escaped by placing a
> backslash before the quotation mark**. Special control characters such as **`\n` (for a new line)**
> and **`\t` (for tab)** may also be included in this log format string." _(Mod 15 p110)_

### Table 15.17: Different Fields in Apache Common Log Format _(Mod 15 p110)_

Columns `Fields` · `Description` · `Field directive` — reproduced verbatim.

| Fields | Description | Field directive |
|---|---|---|
| Client IP Address | Host IP address making the request | `%a` |
| Remote Logname | Remote log name. **This field is almost always null (`_`)** | `%l` |
| Authenticated Username | Authenticated user's identifier name | `%u` |
| Request Date and Time | Date and time at which the request was received by the server (in Common log time format) | `%t` |
| Request Line | An HTTP request line that holds the method, request-URI, and protocol **ending with `<CR><LF>`** | `%r` |
| Status Code | Response code of the HTTP server | `%s` |
| Bytes Sent | Data (in bytes) sent from the server to the client | `%b`, `%B` |
| Client Hostname | DNS hostname of the host making the request | `%h` |
| Server IP Address | IP address of the host fulfilling the request | `%A` |

Example:

```apache
LogFormat "%h %l %u %t "%r" %>s %b" common
```

```text
203.93.249.11 - oracleuser [17/Sep/2018:18:45:05 -0700] "GET /files/search/search.jsp?s=driver&a=10 HTTP/1.0" 200 2374
```

Walked through, as printed _(pp110–111)_:

| Token | Directive | Meaning as printed |
|---|---|---|
| `203.93.249.11` | `%h` | IP address of the host (remote) making the request |
| `-` | `%l` | "The hyphen represents that specific information, that is, **remote log name, is not available**" |
| `oracleuser` | `%u` | Authenticated user's identifier name |
| `[17/Sep/2018:18:45:05 -0700]` | `%t` | Date and time at which the request was received by the server |
| `"GET /files/search/search.jsp?s=driver&a=10 HTTP/1.0"` | `%r` | An HTTP request line that holds the method, request-URI, and protocol ending with `<CR><LF>` |
| `200` | `%s` | "Response code of the HTTP server. **This is very important information.** It determines whether the request is **responded successfully, redirected, a client error (unauthorized request from the client), or a server error (server is unable to process the request due to some reason)**" |
| `2374` | `%b` | "Data (in bytes) sent from the server to the client. If no data is sent from the server to the client, then this value will be denoted as **`-`**. **To display `0` in place of `-`, use `%B` instead of `%b`**" |

### Apache combined log format _(Mod 15 p111)_

> "This log format is **similar to common log format but contains two additional fields (referrer and
> user agent)**. In other words, it is an **extended version of the common log format**. Information
> regarding **domain name and transfer time is not provided** in this format."

```apache
LogFormat "%h %l %u %t "%r" %>s %b "%{Referer}i" "%{User-Agent}i" combined
```

### Table 15.18: Additional Fields in Apache Combined Log Format _(Mod 15 p111)_

| Fields | Description | Field directive |
|---|---|---|
| Referrer | URI of the resource (typically a website) from which the requested URI was obtained | `"%{Referrer}"` |
| User Agent | Browser information of the visitor | `"%{User-Agent}i"` |

Example:

```apache
LogFormat "%h %l %u %t "%r" %>s %b "%{Referer}i" "%{User-Agent}i" combined
```

```text
203.93.249.11 - oracleuser [17/Sep/2018:18:45:05 -0700] "GET /files/search/search.jsp?s=driver&a=10 HTTP/1.0" 200 2374 "http://datawarehouse.us.oracle.com/datamining/contents.htm" "Mozilla/4.7 [en] (WinNT; I)"
```

Described as printed _(Mod 15 p111)_: the referrer value "is a **"Referer" HTTP request header** or URI of
the resource (typically a website) from which the requested URI was obtained"; the user-agent value
"is the **user-agent HTTP request header or browser information that made the request**".

### Table 15.19: Name of Parsed Fields _(Mod 15 p112)_

> "Given below is the name of the **parsed fields that are used to parse other log formats**."

| Fields | Description | Field directive |
|---|---|---|
| Filename | Filename of the requested URI | `%f` |
| Request Method | HTTP method of the request | `%m` |
| Transport Protocol | HTTP protocol version string | `%H` |
| Server Port | **Port number of the listener fulfilling the request** | `%P` |
| Server Process ID | Identifier of the process that fulfilled the request | `%P` |
| Request Stem | Stem (path) component of the requested URI | `%U` |
| Request Query String | Query component of the requested URI | *(not legible)* |
| Time to Serve | Time taken to serve the request (**in seconds**) | `%T` |
| Server Name | Server name of the host fulfilling the request | *(not legible)* |
| Session Identifier Field | Session identifier as a separate field | *(not legible)* |
| Visitor Identifier Field | Visitor identifier (such as a cookie) as a separate field | *(not legible)* |
| General Purpose Fields 1-10 | "**Users may define (customize) up to ten log fields**" | *(not legible)* |

Note the **unit difference** between the two tables: Table 15.17's *Bytes Sent* is in **bytes**;
Table 15.19's *Time to Serve* is in **seconds**, while the IIS W3C `time-taken` field is in
**milliseconds**.






