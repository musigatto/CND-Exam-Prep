---
type: note
module: "15"
lo: "07"
tags: [tool, process, bestpractice, command, mod/15]
topic: "Apache access-log locations, monitoring procedure, and the bridge to centralized logging"
exam_weight: unknown
status: done
unresolved:
  - "p113 'Access Logs' and 'Error Logs' are callout diagrams: printed labels sit on arrows pointing into a sample log line. Only the labels are reproduced; the arrowed sample values (including the access-log sample line and the error-log sample line) were NOT transcribed."
  - "p113 the two callout lists are labelled with cut-off captions ('Timestamp of', 'Username of', 'Identity of', 'Severity', 'Process ID', 'Thread ID'); the full caption text is not legible."
  - "p114 under the heading 'Monitoring Apache Error Log' the paragraph begins 'To monitor Apache access log file' - printed wording, reproduced as-is and not corrected."
  - "p114 the page calls the log paths 'directives' ('navigate to one of the following two directives based on the OS'); they are file paths. Printed wording kept."
---

[[MOC-Module-15]]

# Apache Access Log Fields and Monitoring (§15.07)

> **LO#07: Discuss log monitoring and analysis on web servers** _(Mod 15 p3)_
> Covers pp113–115.

Related: [[15-LO07d-Apache-Error-and-Access-Logs]] ·
[[15-LO08a-Why-Centralized-Logging]] ·
[[15-LO08c-Log-Collection-and-Log-Transmission]] ·
[[15-LO03c-Commands-to-Monitor-and-Analyze-Linux-Logs]].

## Default Apache access-log location in various OSes _(Mod 15 p113)_

Printed list, reproduced verbatim:

| OS | Default access log |
|---|---|
| **FreeBSD** | `/var/log/httpd-access.log` |
| **Debian / Ubuntu Linux** | `/var/log/apache2/access.log` |
| **RHEL / Red Hat / CentOS / Fedora Linux** | `/var/log/httpd/access_log` |

Three shapes, three conventions: **FreeBSD joins `httpd` and the log name with a hyphen**; **Debian
uses the `apache2` directory with a dotted filename**; **Red Hat uses the `httpd` directory with an
underscored filename**.

> These are the same three distributions and the same three paths printed on p108 — p113 repeats
> them without the FreeBSD/SUSE-style trailing `/logs` differences. See
> [[15-LO07d-Apache-Error-and-Access-Logs]].

## What the two Apache log lines are made of _(Mod 15 p113)_

The page prints two callout diagrams labelling the parts of an access-log record and an error-log
record. The printed callout labels, as a field list:

**Access Logs** — `Remote Host` · `Username of the Visitor` · `Timestamp of the Request` ·
`Method` (`GET/POST/HEAD`) · `Status Code of the Request` · `Bytes of Data Transferred` ·
`Protocol & Version` · `Identity of the Visitor (e-mail …)` · `Time Zone (UTC)`

**Error Logs** — `Timestamp of the Message` · `Module that Produces` · `Severity of Error or LogLevel
Value` · `Process ID` · `Thread ID` · `Client's Address that Requested` · `Server` · `Detailed Error
Message`

Access log answers **who / when / what / how much**; error log answers **what broke, how badly, and
for which client**.

## Monitoring and Analysis of Apache Log _(Mod 15 p113)_

> "The Apache access and error logs provide **actionable insights regarding potential server
> configuration and web application problems**. However, **a concern with them is that important
> information is concealed inside a large number of log messages**. Therefore, **the goal of Apache log
> analysis is to extract only the important information** to gain an understanding about the issues and
> **how to respond to them before they affect the users**. However, **monitoring of Apache access and
> error logs is required before analyzing them**."

The order is fixed: **monitor first, then analyse** — and the enemy is **volume**, not absence of data.

### Monitoring Apache Access Log _(Mod 15 p114)_

> "To monitor Apache access log file, **navigate to one of the following two directives based on the
> OS**:
>
> - `/var/log/httpd/access_log`, or
> - `/var/log/apache2/access.log`
>
> If the Apache access log file is **unreachable at the given path, then it may be due to a custom
> configuration in the Apache config file**. In this case, **open the Apache configuration file
> `httpd.conf` to find the location of the access log file**."

So: **known default path → follow the fallback → read `httpd.conf`.**

### Monitoring Apache Error Log _(Mod 15 p114)_

> "To monitor Apache access log file, navigate to one of the following two directives based on the OS:
>
> - `/var/log/httpd/error_log`, or
> - `/var/log/apache2/error.log`
>
> **Apache does not allow use of a custom error log format.**"

Two points to remember: the **error log cannot be re-formatted** — unlike the access log, whose
`CustomLog` format is "highly configurable", the error log format is fixed and you must read it as
printed.

## Bridge into LO#08 — centralized logging _(Mod 15 p115)_

> "**Monitoring and analyzing log files of different devices locally can be a difficult task.
> Centralized logging helps you to simplify the process.**"

This is the closing line of LO#07 and the reason the next LO exists. The local, per-device approach
covered above breaks down as soon as the estate spans devices — every IIS server, every Apache host,
every firewall and router keeps its own file in its own path with its own format, and a defender has to
reach each one to compare them. Centralizing the collection and analysis is what makes correlation
across devices possible: see [[15-LO08a-Why-Centralized-Logging]] and
[[15-LO08c-Log-Collection-and-Log-Transmission]].

Local per-device monitoring also assumes you are *on* the device. `cat`, `grep` and
`sudo tail -100` (see [[15-LO03c-Commands-to-Monitor-and-Analyze-Linux-Logs]]) all run where the log
lives.





