---
type: note
module: "15"
lo: "04"
tags: [concept, tool, command, mod/15]
topic: "Mac log types and the printed log-file inventory"
exam_weight: unknown
status: done
unresolved:
  - "p52 the 'Mac Log Files Location' column prints TEN entries against NINE log-file names — it carries an extra generic '-/Library/Logs' entry that shifts the whole column down one row. Row alignment here was taken from p53's per-file prose, which states each path explicitly; the printed cell values themselves are reproduced byte-exact and were NOT repaired. The table's Log file column prints no name for the generic '-/Library/Logs' row; p53's prose calls that directory 'Logs'."
  - "p52 prints 'access _ log' with a stray space in the Log file column while its Location cell prints '/var/log/cups/access_log'; both printed forms are kept."
  - "p51 prints the history file as '. bash history' and the p50 callout prints '.bach history file' (likely both a garbling of '.bash_history'); quoted verbatim, NOT repaired."
  - "p51 'User-specific logs' prints 'which is found in the folder.' — the folder NAME is missing from the sentence. No path was supplied from outside; the p50 callout's '-/Library/Logs' and p53's '&/Library/Logs' are the only printed forms of it."
  - "p52/p53 CUPS filenames print with a stray space before 'log' ('/var/log/cups/access log', '/var/log/cups/error log', '/var/log/daily. out', '/var/log/samba/log. nmbd') while the p52 table cells print them unspaced. All printed forms kept."
  - "p52/p53 the CUPS server-name token prints as '-8s' in both 'AccessLog /var/log/cups/access log-8s' and 'ErrorLog ... error log-8s'; kept verbatim, NOT read as '%s'."
  - "p53 prints 'ErrorLog can /var/log/cups/error log-8s' — the stray word 'can' appears inside the example. Kept as printed."
  - "p53 prints 'DiscRecording.Iog' with a capital I, '/ Library/ Logs / Di scRecording. log', and DiskUtility's location as '•dLibrary/Logs/DiskUti1ity. log'; the leading tilde characters are OCR-mangled in all three. Kept verbatim."
  - "p50 prints the Console folder as '/App1ications/Uti1ities' (digit 1 for letter l); kept verbatim."
---

[[MOC-Module-15]]

# Mac Types of Logs and Log Files (§15.LO#04b)

> **LO#04: Discuss log monitoring and analysis on Mac systems** _(Mod 15 p47)_
> Covers pp50–53.

## Why the log files matter _(Mod 15 p50)_

> "Mac OS stores **a variety of log files**. While some of them are very detailed, **only a small portion of that is used forensically**; some others are harmless with **direct or indirect evidence to a user's activities**. Some log files **represent malicious activities** performed by the user, while other log files act such as **indirect circumstantial evidence for identifying an attack**."

"These types of logs are found in `/App1ications/Uti1ities` folder in Console application." _(p50)_

## The five types of logs in Mac _(Mod 15 pp50–51)_

| Type | File / location (as printed) | What it records |
|---|---|---|
| **Security logs** | `secure.log` — "found in **`/private/var/log`** directory" | **login/logout activities**; "helps in determining **attempted and successful unauthorized activities**" |
| **Firewall logs** | `appfirewall.log` — "found at **`/ private/var/log/appfirewall . log`**" | Logs "that are **not acceptable by the application firewall**" are written by **`appfwloggerd`**; "enables management of **incoming and outgoing network traffic** and helps check against **abnormal/repeated attempts on ports**" |
| **User-specific logs** | "found in **the folder**" _(name not printed)_ | OS component + third-party application log information; "can be **accessed only by the specific user**"; "While this **guards against privacy issues**, it **makes troubleshooting difficult**" |
| **Command line logs** | `. bash history` — "found in the **root user's home directory**" | Shell history — "Forensic investigators examine history files to **evaluate suspicious command-line activities**" |
| **Shared application logs** | `/Library` folder | Logs "that correspond to **components shared across multiple applications**" — e.g. **CrashReporter** logs, application-crash information, **server and directory service** logs |

**`appfirewall.log` is a built-in firewall** that "can log a large amount of data using a program called **`appfwloggerd`**" _(p50)_ → the Mac firewall log itself → [[15-LO05c-Mac-OS-X-Firewall-Logs]]

### Command line history specifics _(Mod 15 p51)_

- "The history file is **distinct for each shell** in which the user is performing different activities."
- "Each history file stores **only 150 commands**; when new commands are added, **old commands automatically expire**."
- `history` — "Using the history command **(without any arguments) displays the history**"
- `history -c` — "which can also be **cleared** using the same command through `history -c`"

## Mac Log Files — the printed inventory _(Mod 15 p52)_

> Values reproduced **exactly as printed**, including OCR damage. Row alignment confirmed against p53's per-file prose. Do not "fix".

| Log file (as printed) | Mac Log Files Location (as printed) | Description (as printed) |
|---|---|---|
| `crashreporter.log` | `/var/log/crashreporter.log` | "Application usage history and application crash information written to this file" |
| `access _ log` | `/var/log/cups/access_log` | "Printer access log information" |
| `error_log` | `/var/log/cups/error_log` | "printer connection information and its error logs found here" |
| `daily.out` | `/var/log/daily.out` | "Network interface history" |
| `log.nmbd` | `/var/log/samba/log.nmbd` | "Samba (Windows-based machine) connection information" |
| _(no name printed)_ — p53 calls it "Logs" | `-/Library/Logs` | "Home directory users and application-specific logs can find here" |
| `DiscRecording.log` | `w/Library/Logs/DiscRecording.log` | "Home users' **CD & DVD media burning** logs written to this file" |
| `DiskUtiIity.Iog` | `N/Library/Logs/DiskUtility.Iog` | "hard disk partitioning logs, CD/DVD burned media logs; SO/DMG images files mount, unmount history, and **file permission repair history**" |
| `iChatConnectionErrors` | `/Library/Logs/iChatConnectionErrors` | "Log history of iChat connection attempts. Data such as **username, IP address, and date & time** of the attempt" |
| `Sync` | `(Library/Logs/Sync` | "information on **synchronized Mac systems and mobile devices such as cell phones and iPods** as well as their activities with date and time" |

Note the CUPS pair — `access_log` / `error_log` under `/var/log/cups/` are **printer** logs, not web-server logs. Compare Apache → [[15-LO07d-Apache-Error-and-Access-Logs]]

### `crashreporter.log` _(Mod 15 p52)_

- Standard crash reporter located at **`/ System/ Library/ CoreServices/Crash Reporter . app`**
- Sends the warning **"[App] has quit unexpectedly."**
- Check immediately by clicking the **`"Report..."` button** or by using Console app; in Console click **`"User Reports"` in the left menu**
- All crash files "have a **`.crash`** extension" and "include the **date and crashed application** in the title"
- "The **right pane** contains details regarding the crash report … information about **what, when, and why** an application/component crashed"

### CUPS directives `AccessLog` and `ErrorLog` _(Mod 15 pp52–53)_

| Directive | What it sets | Printed rules |
|---|---|---|
| **`AccessLog`** _(p52)_ | "sets the name of the **access log** file" | If the name is **not absolute**, it is "considered as **relative to the `ServerRoot` directory**"; "saved in **common log format**"; "can be utilized in producing reports on **Common UNIX Printing System (CUPS)** server operations"; server name included "by using `8s` such as `AccessLog /var/log/cups/access log-8s`"; to send to the system log, **`"syslog"` is used in spite of a plain file such as `AccessLog syslog`**" |
| **`ErrorLog`** _(p53)_ | "sets the name of the **error log** file" | If the name is **not absolute**, it is "considered as **relative to the `ServerRoot` directory**"; server name included "such as `ErrorLog can /var/log/cups/error log-8s`"; to send to the system log, **`"syslog"` is used in spite of a plain file such as `ErrorLog syslog`**" |

**Defaults:** access log → **`/var/log/cups/access log`** _(p52)_ · error log → **`/var/log/cups/error log`** _(p53)_

## Per-file notes _(Mod 15 p53)_

- **`Daily.out log`** — "generated based on the **daily activities performed overnight** when your system is **running but not logged in**"; "stores **network interface history**"; located at `/var/log/daily. out`
- **`log.nmbd`** — "contains **Samba (Windows-based machine) connection information**"; stored in `/var/log/samba/log. nmbd`
- **`Logs`** — "the **home directory** that contains **users and application-specific logs**, which are **plain-text files** stored in `&/Library/Logs`"
- **`DiscRecording.Iog`** — "stores **CD and DVD media burning logs** that are specific to **Home user**"; located at `/ Library/ Logs / Di scRecording. log`
- **`DiskUtility.log`** — "all the activities performed by the **Disk Utility** application such as **hard disk partitioning** logs, **CD/DVD burned media** logs, **ISO/DMG images** files mount, unmount history, and **file permission repair** history"; located at `•dLibrary/Logs/DiskUti1ity. log`
  - **"Such a type of log cannot be rotated or cleared on a regular basis, thereby helping in detection of abnormal behavior in the system."**
- **`iChatConnectionErrors log`** — "log history of **iChat connection attempts**, including data such as **username, IP address, and date and time**"; stored at `/ Library/ Logs/ iChatConnectionErrors`
- **`Sync`** — "information on **synchronized Mac systems and mobile devices** such as cell phones and iPods and their activities with date and time"; located at `/ Library/ Logs/ Sync .`

Format & how to read them → [[15-LO04c-Mac-Log-Format-and-System-Logs]] · Console → [[15-LO04a-Mac-Logs-and-Console]] · collect centrally → [[15-LO08a-Why-Centralized-Logging]]






