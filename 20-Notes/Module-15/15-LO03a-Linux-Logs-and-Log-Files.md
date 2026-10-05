---
type: note
module: "15"
lo: "03"
tags: [concept, tool, command, mod/15]
topic: "Linux logs and the critical /var/log files"
exam_weight: unknown
status: done
unresolved:
  - "p39 prints the messages-file alias as '/ vat/ log/ syslog' — a garbled rendering of the syslog alias; quoted verbatim and deliberately NOT repaired."
  - "p39 prints '/var/log/auth. log', '/var/log/kern. log', '/var/log/cron. log', '/var/log/maillog', '/var/log/mail . log', '/var/log/boot. log' with a stray space before 'log'; p40 prints '/var/log/mysqld. log' and '/vat/ log/btmp' the same way. All are reproduced exactly as printed and NOT repaired."
  - "p40 prints '/var/log/daemon.log/' with a trailing slash although the entry describes a file, not a directory — kept as printed."
  - "p40 the OCR interleaves the '/var/log/xferlog' label inside the btmp sentence; rendered here as two separate entries. The btmp entry reads 'It maintains a record of all unsuccessful logon attempts.' and the xferlog entry reads 'It maintains a record of FTP file transfers that contains information such as file names and FTP transfers initiated by users.'"
  - "p39 prints the Apache file names as 'access _ log' and 'error _ log' (stray spaces); p39 prints light HTTPD's as 'access_log' and 'error _ log'. Both printed forms are kept."
  - "p39 prints the boot init script as '/etc/ init. d/bootmisc. sh' — garbled; kept verbatim and NOT repaired."
  - "p37 and p38 each carry a GUI screenshot of a file listing / text file open in an application (the /var/log directory listing and /var/log/yum.log). Treated as non-evidence: no file names, sizes or contents were read from those images. The only readable prose is the p38 caption 'Yum command log file'."
---

[[MOC-Module-15]]

# Linux Logs and Log Files (§15.LO#03a)

> **LO#03: Discuss log monitoring and analysis on Linux systems** _(Mod 15 p36)_
> Covers pp36–40.

## What Linux logs are _(Mod 15 p37)_

- "Linux logs are a **record of any activity or event** in a Linux-based OS"; they include messages on just about everything — **system, kernel, package managers, boot processes, Xorg, Apache, and MySQL**
- A useful **troubleshooting tool** when a security issue occurs; help monitor and analyze security threats and vulnerabilities and remediate them; help track communication between systems and networks
- **Location and format** — most logs live in the **`/var/log`** directory and subdirectories, in **plain ASCII text format**
- **Producers** — many are produced by the **system log daemon (`syslogd`)** on behalf of the system and application, while **some applications produce logs directly** into `/var/log`
- **Access** — to change the directory the **`cd`** command is used; **only the root user can view or access Linux log files** _(Mod 15 p37)_

## Four categories of log files _(Mod 15 p38)_

1. **Application logs**
2. **Event logs**
3. **Service logs**
4. **System logs**

These should be monitored to **predict upcoming issues before they actually occur**. Because monitoring every file is cumbersome, p38–40 introduce a few **critical** ones.

## Critical log files _(Mod 15 pp38–40)_

> Paths are reproduced **exactly as printed**, including the printed OCR damage. Do not "fix" them.

| Log file (as printed) | What it records |
|---|---|
| `/var/log/yum.log` _(p38 caption: "Yum command log file")_ / `/var/log/yum. log` _(p40)_ | All information related to **installation of a package using the `yum` command**; proves useful to check whether a package is installed correctly, and helps identify and solve software installation issues |
| `/var/log/messages` **or** `/ vat/ log/ syslog` | **General messages and system-related information** — all informational and noncritical messages across the global system: system error messages, system startups and shutdowns, change in the network configuration, etc. Also logs mail, cron, daemon, kern, auth, etc. "**This is the first place to look if things go wrong in the network/OS**" — e.g. a sound-card issue is checked here. **Plain-text format**, readable by any tool that can examine text files |
| `/var/log/auth. log` **or** `/var/log/secure` | **Authentication logs** — successful and unsuccessful user login attempts and authentication techniques. Beneficial to **examine brute-force attacks** and other vulnerabilities related to the user authorization mechanism |
| `/var/log/kern. log` | What is logged by the **kernel**; helps solve kernel-related errors and warnings plus hardware and connectivity problems; useful in **troubleshooting a custom-built kernel** |
| `/var/log/cron. log` | All **Crond-related messages** (cron jobs) — when the cron daemon begins a job, all information about successful or failed execution is logged here; helps solve issues with scheduled cron |
| `/var/log/maillog` **or** `/var/log/mail . log` | **Mail server** information — postfix, smtpd, MailScanner and other email-related services; keeps records of all emails sent or received within a time zone; helps examine **failed delivery problems** and detect **spamming attempts blocked by the mail server** |
| `/var/log/qmail/` | **Directory** for qmail logs — track all emails sent through a qmail system, the list of every message transmitted by the server, or the number of messages processed |
| `/var/log/httpd/` | **Directory** for the **Apache** web server, which stores information in two log files: `access _ log` and `error _ log`. Detailed information about events and errors raised while processing httpd requests; records every page or file provided or loaded by Apache, plus the **IP address and user ID** of every client that connected; logs the **status of access requests and whether a response was given or not** |
| `/var/log/lighttpd/` | **Directory** for light HTTPD `access_log` and `error _ log` |
| `/var/log/boot. log` | All information related to **system booting**; the booting messages are sent by the system initialization script `/etc/ init. d/bootmisc. sh`. Helps troubleshoot **improper shutdowns, booting failures, or unplanned reboots**, and by checking the file you can determine the **time span of system downtime** caused by an unexpected shutdown |
| `/var/log/mysqld. log` | All **debug, failure, and success** messages about `[mysqld]` and `[mysqld_safe]` daemons; helps detect issues with **starting, running, and stopping** of mysqld |
| `/var/log/utmp` **or** `/var/log/wtmp` | **User login/logout** information; helps determine the **current login state** |
| `/var/log/dmesg` | **Kernel ring buffer** messages; information related to **hardware devices and their drivers** |
| `/var/log/daemon.log/` | Records the **execution of background services** but does not display them in graphical form |
| `/var/log/lastlog` | The **last logon of each user**; a **binary file** read with the **`lastlog`** command |
| `/vat/ log/btmp` | A record of **all unsuccessful logon attempts** |
| `/var/log/xferlog` | A record of **FTP file transfers** containing information such as file names and FTP transfers initiated by users |
| `/var/log/faillog` | **Failed logins** — "handy for examining potential security breaches like login credential hacks and brute-force attacks" |

Format/selector details → [[15-LO03b-Linux-Log-Format-and-Severity-Levels]] · commands → [[15-LO03c-Commands-to-Monitor-and-Analyze-Linux-Logs]] · where these records are shipped → [[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]] · Linux endpoint hardening → [[MOC-Module-06]] · Apache `access_log`/`error_log` → [[15-LO07d-Apache-Error-and-Access-Logs]]






