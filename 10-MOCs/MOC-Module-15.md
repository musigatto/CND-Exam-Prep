---
type: moc
module: "15"
tags: [concept, process, tool, command, bestpractice, mod/15]
topic: "Module 15 — Network Logs Monitoring and Analysis"
exam_weight: unknown
status: done
unresolved:
  - "p152 THE MODULE SUMMARY ENUMERATES EIGHT STEPS WHERE THE BODY NUMBERS SEVEN. p135 = Step 3 Log Storage, p137 = Step 4 Log Normalization, p140 = Step 5 Log Correlation, p142 = Step 6 Log Analysis, p145 = Step 7 'Alerting and Reporting' (one step, heading printed singular). The summary slide splits Step 7 into 'alerting' and 'reporting'. Both printed forms are kept and the difference is NOT reconciled. Reproduced in [[15-LO08g-Alerting-Reporting-Best-Practices-Tools-Challenges]]."
  - "p152 THE SUMMARY USES THE ABBREVIATION 'CLM' AND NEVER EXPANDS IT — 'local logging and CLM concepts'. The string 'CLM' occurs nowhere else in the 152 pages and no expansion exists in the courseware. None supplied."
  - "p152 THE SUMMARY DROPS A WORD FROM THE TRIAD. Slide: 'Centralized logging, monitoring, and analysis are done through a series of steps'. p121: 'In centralized logging, logging, monitoring, and analysis of logs are performed through a series of steps' — four phases, not three."
  - "STEP 4 HAS THREE PRINTED WORDINGS. p121–p122 figure: 'Normalization' · p137 heading: 'Step 4: Log Normalization' · p152: 'log normalization'. All kept."
  - "p145 THE RUNNING PROSE HEADING OCRS AS 'Step Z: Alerting and Reporting' while the slide heading prints 'Step 7'. Rendered as Step 7 to match the slide; the OCR form is recorded."
  - "THE 0–7 SEVERITY SCALE IS NAMED FIVE DIFFERENT WAYS ACROSS THE MODULE, AND NEVER CONSISTENTLY PRINTED WITH ITS NUMBERS. p60 (firewall intro): 'emergency, alert, critical, error, warning, notification, informational, and debugging' as a bare ordered list with no number beside any name. p43 (Linux): 'Emergency, Alert, Critical, Error, Waming, Notice, Info' + Debug named only in the prose, and the printed Severity Value column carries no value for the Emergency row. p76–p77 (ASA): 'Emergencies, Alerts, Critical, Errors, Warnings, Notifications, Informational, Debugging'. p91–p92 (router): the same plural set plus the UNIX names 'LOG EMERG'…'LOG DEBUG'. p131 (syslog): the abbreviations 'Emerg, Alert, Crit, Error, Warn, Notice, Info, Debug' with NO numeric column. Also p60 and p91 print the lowest level as the letter 'O' while the surrounding prose prints '0 to 7'."
  - "TABLE 15.20 FACILITY NUMBERING IS OFF BY ONE AND CANNOT BE REPAIRED. p130 prints codes 1–12 and p131 prints 13, 14, 15, 16–23, but THIRTEEN facility names print before the p131 continuation. Code 0 is never printed, so the name-to-code alignment cannot be fixed from the page. Both rows reproduced as printed with no reassignment."
  - "p126 REFERS TO 'the standard syslog port' AND 'a TCP port' BUT PRINTS NO PORT NUMBER ANYWHERE in pp125–134. No number is supplied for syslog UDP, syslog TCP or encrypted syslog."
  - "p63 AND p65 GIVE TWO DIFFERENT DEFAULT WINDOWS DEFENDER FIREWALL LOG LOCATIONS. p63's callout: 'Default firewall log location in windows is C:\\Firewall'. p65's prose: '\\LogFi1es\\Firewa11\\Pfirewa11. log'. The page contradicts itself; neither was corrected. p63 prints the filename lower case as 'pfirewall.log', p65 prints 'Pfirewa11. log'."
  - "p69 AND p71 GIVE TWO DIFFERENT MAC APPLICATION-FIREWALL LOG LOCATIONS. p69's callout: '/private/var/log/'. p71's Console procedure searches for '/var/log'. Both recorded, neither corrected."
  - "p108 CONTRADICTS ITSELF ON THE APACHE LOG PATH. The page states the RHEL / Red Hat / CentOS / Fedora default access-log path as /var/log/httpd/access_log, then gives the RHEL 'tail' command against /etc/httpd/logs/access_log. The same /etc/httpd/logs/ vs /var/log/httpd/ split appears on p109 for the error log."
  - "p99 THE THREE IIS DEFAULT LOCATIONS PRINT THREE DIFFERENT CASE VARIANTS: '%system32%\\LogFiles\\W3SVCN' (IIS 6.0) · '%SystemDrive%\\Inetpub\\Logs\\LogFiles\\w3svcN' (7.0) · '%SystemDrive%\\inetpub\\logs\\LogFiles' (8.0 and 10.0). Also the leading percent sign of the 8.0 entry was not legible and was restored from the identically-worded 10.0 entry printed beneath it."
  - "p74 TABLE 15.8 CANNOT BE PAIRED. The field-name column prints 8 names in block 1 and 8 in block 2 while the description column prints 10 + 11 entries. The two columns are listed separately and are NOT paired. 'DPT' appears in the printed sample log line but NOT in the printed field-name column."
  - "p74 THE TWO PRINTINGS OF THE SAMPLE IPTABLES LOG LINE DISAGREE, AND NO '=' PRINTS AFTER 'OUT' IN EITHER: 'RULE 08a—ACCEEPT' · 'IN=eth1' (first copy) vs 'IN—ethi' (second copy) · 'OUT ethO' (no '=' either copy) · 'Tos=oxoo' vs 'TOS=OxOO' · 'WINDOW-32767' vs 'WINDOW=32767'. Quoted as printed; the interface names are not recoverable."
  - "p85 AND p87 PRINT THE 'fw log' SYNTAX TWICE AND NEITHER PRINTING IS CLEAN. The bracket nesting is scrambled and the p87 line ends on the command with no closing bracket. Neither line was completed from the other. The parameter tables cannot be paired either: p85 prints 5 parameter names against 10 description entries ('-e endtirne' with a letter r), p86 prints 4 names against 7 descriptions."
  - "p79 TABLE 15.10 PRINTS 10 MESSAGE IDs AGAINST 9 DESCRIPTIONS — 710003 carries no description on the page. The list is NOT truncated: all ten IDs (106015 106016 106017 106018 106020 106021 106022 106023 106100 710003) are legible in the source."
  - "p90 TABLE 15.11 DUPLICATES THREE MNEMONICS. It prints 10 rows, of which IPACCESLOGP, IPACCESLOGDP and IPACCESLOGNP reappear as rows 8–10. The pairings are sequential and unambiguous and the duplicates are reproduced as printed."
  - "p112 TABLE 15.19 PRINTS '%P' FOR BOTH 'Server Port' AND 'Server Process ID'. Only Filename (%f), Request Method (%m), Transport Protocol (%H), Server Port (%P), Request Stem (%U) and Time to Serve (%T) are legible; Request Query String, Server Name, Session Identifier Field, Visitor Identifier Field and General Purpose Fields 1–10 are left blank."
  - "p111 TABLE 15.18 PRINTS THE REFERRER DIRECTIVE WITH A DOUBLE R AS '%{Referrer}' while the LogFormat example line and the explanatory paragraph on the same page print 'Referer' with a single r. Both forms kept. p110 prints the Remote Logname directive so that it reads as the digit 1 while the same page's LogFormat example prints %l."
  - "p52 PRINTS TEN 'Mac Log Files Location' ENTRIES AGAINST NINE LOG-FILE NAMES — an extra generic '/Library/Logs' row shifts the whole column down one. Row alignment was taken from p53's per-file prose; the printed cell values are reproduced byte-exact and were NOT repaired."
  - "p54 THE PRINTED 'Syntax:' STRING IS DAMAGED AND THE TWO PRINTINGS ON THE PAGE DO NOT AGREE: the callout box prints 'MW DD Host Service: Message' and the body prints 'ION DD HH:bN: ss Host Service: Message'. Both quoted verbatim and NEITHER was repaired into 'MMM DD HH:MM:SS Host Service: Message'. Only 'DD', 'Host Service:' and 'Message' are legible in both."
  - "p72 TABLE 15.7 PRINTS 16 FIELD NAMES AGAINST 15 DESCRIPTIONS, AND ITS DESCRIPTIONS CONTRADICT ITS OWN FIELD NAMES — HOSTNAME is described as 'Client IP address trying to get access of a given port' and SERVER as 'Port to which access is attempted by the user'. Reproduced verbatim, not reconciled with the field names."
  - "p19–p21 PRINT THE EVT SIGNATURE TWO WAYS ('0x654c664c' and 'Ox654c664c'), HeaderSize as '0 x 30', and ReservedFlags as 'O x 0000' / 'O x 8000'. The page prints 'Ox' for zero throughout this module and it was NOT normalised. The EVENTLOGRECORD declaration prints 20 types against only 16 named members; both are reproduced."
  - "p140 LISTS SIX INPUTS FOR MACRO-LEVEL CORRELATION (rule, vulnerability, profile (fingerprint), anti-port, watch list, geographic location) BUT DESCRIBES ONLY THREE. Watch list correlation and geographic location correlation are named with no description anywhere in pp140–141. Nothing is supplied for them."
  - "p147 THE FIGURE TILE GRID NAMES TWELVE LOG-ANALYSIS TOOLS (Splunk, Logmatic, Logstash, Sumo Logic, Papertrail, LogRhythm, Retrace, Logentries, Graylog, Xpolog, LOGalyze, Loggly) WHILE THE RUNNING PROSE DESCRIBES ONLY TEN. LOGalyze and Logentries appear in the FIGURE ONLY. Figure tiles are screenshot non-evidence, so neither is given a capability."
  - "p133 CONTRADICTS ITS OWN 'Source:' CAPTIONS TWICE. The figure gives Kiwi Syslog Server as 'https://www.kiwisyslog.com' while the prose says 'Source: www.solarwinds.com'; the figure gives SNMPSoft Sys-log Watcher as 'https://www.netadmintools.com' while the prose says 'Source: www.ezfive.com'. Both printed forms recorded; neither is declared correct. The figure additionally prints 'https.//www.whatsupgold.com', 'https://www.sysbg-ng.com' and 'https://www.fastvue.c0'."
  - "p125 AND p129 PRINT FIGURE 15.37'S FORMAT STRING TWO DIFFERENT WAYS: 'TIMESTAMP HOSTNAME TAG MESSAGEID STRUCTURED-DATA MSG' vs 'TIMESTAMP HOSTNAME TAG MESSAGED STRUCTURED-DATA MSG'. 'MESSAGED' is quoted as printed and not corrected to 'MESSAGEID'."
  - "p52/p53 PRINT THE CUPS SERVER-NAME TOKEN AS '-8s' in both the AccessLog and the ErrorLog examples, and p53 prints the stray word 'can' inside the example: 'ErrorLog can /var/log/cups/error log-8s'. Kept verbatim, NOT read as '%s'."
  - "p39/p40 PRINT '/var/log/x' FILE NAMES WITH STRAY SPACES ('auth. log', 'kern. log', 'mail . log', 'boot. log', 'mysqld. log', '/vat/ log/btmp'), p39 prints the messages-file alias as '/ vat/ log/ syslog', p40 prints '/var/log/daemon.log/' with a trailing slash although the entry describes a file, and p39 prints the boot init script as '/etc/ init. d/bootmisc. sh'. All reproduced exactly as printed and NOT repaired."
  - "p43 TABLE PRINTS THE SYSLOG.CONF ALERT EXTENSION AS '-alert' (leading hyphen, not a dot) and Info as '. info' with a stray space. Reproduced exactly as printed and NOT corrected."
  - "p74 THE THIRD IPTABLES COMMAND PRINTS THE LEVEL FLAG AS '--10g-1eve1 4'; the fourth command on the same page prints '--log-prefix' cleanly. Neither '--log-level' nor '--10g-1eve1' was completed by inference."
  - "p62 PRINTS A LONE BULLET 'Tear down in connection' THAT pp59–p62 NEVER DEFINE, EXPAND OR PLACE IN THE 5-STEP LIST. Quoted as printed; no meaning inferred."
  - "p60 FIGURE 15.18'S LEGEND LABELS ARE OCR-DAMAGED BEYOND LEGIBILITY ('Seage prwate Area', 'Firewall Log pub\"c', 'Spec&d tramc Owed', 'Resmc&d unknown tramc'). The legend was NOT transcribed and no label was guessed."
  - "p137/p138/p139 PRINT THE SAME FIREWALL EVENT STREAM THREE TIMES AND THE OCR RETURNS A DIFFERENT CORRUPTED FORM OF EVERY ADDRESS TOKEN EACH TIME ('srcipz10.10.O.1', 'srcip=lo.lo.o.l', 'srcip=10.O.O.1'; 'dstip-10.16.1.1', 'dstip=10.16.1.I', 'dstip=IO.16.I.I'). All three quoted as printed and NOT repaired. The clean values the pages do print are the normalized-table figures 10.0.0.1 / 10240 / 10.16.1.1 / 111."
  - "p138 THE TWO PARSING REGEXES IN FIGURE 15.39 ARE TRUNCATED AND UNBALANCED AS PRINTED: 'IP=\"dstip\\\\=(\\d{1,3}\\\\\\d{1,3})\\d{' and 'Source Port=\"srcport\\\\=(\\d{I,5})\"'. The class '{I,5}' is not corrected to a digit range."
  - "p138 NAMES 'Common Event Expression (CEE)' EXACTLY ONCE. No CEE schema, field set or standard number is printed anywhere in pp135–139."
  - "p135 THE THREE STORAGE-DECISION HEADINGS PRINT IN THE SLIDE AS 'Storage Duration', 'Ways of Accessing the Logs' and 'Volume of Data to Be Stored', BUT THE RUNNING PROSE DISCUSSES THEM IN THE ORDER storage duration, volume of the data, way of accessing. Both orders given; neither declared canonical."
  - "p118 THE FIGURE SAYS ALERTS ARE GENERATED 'based on metrics defined IN the log' WHILE THE PROSE SAYS 'ON the log'. The page is internally inconsistent on the preposition."
  - "p118 THE FIGURE LISTS 4 'Centralized Log Management Capabilities' AND THE PROSE LISTS 9. The 4 figure items are each covered by a prose item (store centrally, access important data, alerts on metrics, share dashboards) but the page does not state the lists are the same set."
  - "p119/p120 THE ONLY THREE TIER NAMES IN THE MODULE ARE: log generator · log analysis and storage · log monitoring. 'Clock daemon' and 'Security/authorization messages' are syslog FACILITY names, not tier names. The p119 figure also prints the collection-server box as 'Cdkction Server' and the storage list as 'MY SQL' against the p120 prose's 'collection servers' and 'Oracle, MS SQL, etc.'"
  - "p143 THE HEADING AND PROSE SAY 'automated log analysis' WHILE THE SLIDE SAYS 'In automatic log analysis'. The slide also says manual analysis is 'based on experience and knowledge of the EXAMINER' while the prose says 'the NETWORK DEFENDER'. Both printed forms kept."
  - "p144 THE SLIDE PRINTS FIVE LOG-ANALYSIS BEST PRACTICES AND THE RUNNING PROSE PRINTS TWELVE. The five slide items are a subset of the twelve. The page's own hedge is 'Below are some of the best practices', so the twelve are not treated as a closed list."
  - "p150 THREE SLIDE BULLETS UNDER 'Centralized Logging Challenges' HAVE NO PROSE ELABORATION ANYWHERE IN pp150–p151: 'Managing the available resources with continuously increasing log data' · 'With the changing threat landscape, it is difficult to monitor using existing capabilities' · 'Difficulty in determining the purpose and importance of data sources'."
  - "p150–p151 THE PROSE INTRODUCES FOUR SUB-ITEMS UNDER 'Challenges in log generation and storage' (many log sources, inconsistent log content, inconsistent timestamps, inconsistent log formats) WHILE THE SLIDE PRINTS ONLY THREE BULLETS. Both lists are given; neither is aligned to the other."
  - "p151 PRINTS 'an incorrect timestamps could display that event M occurred 30 s before event N' — the singular/plural slip is as printed and the event letters M and N are the page's own."
  - "p152 THE SUMMARY'S OPENING TRIAD 'incidents, events, and logs' HAS NO BODY COUNTERPART. The module body begins at logging concepts (LO#01) and never defines 'incidents' or 'events' as such."
  - "SCREENSHOT AND FIGURE PAGES ARE NON-EVIDENCE THROUGHOUT: the '/var/log' listing and 'Yum command log file' captures (p37, p38) · the Windows 'Various Windows Event Types' view (p27) · the Mac Console, Finder, 'Go to the folder', 'Find' and 'Database Search' dialogs (pp57–58, p71) · the Check Point 'fw log' example capture (p86) · the ASA 'show logging' and 'grep' captures (pp80, p82, p83) · the p93 and p94 router log and include-filter captures · the Apache access/error callout diagrams (p113) · the syslog message callout diagram (p130) · the p147 log-analysis tool tile grid. No dashboard value, panel label, sidebar entry, file size or version string was read out of any of them; only printed callout labels and numbered body steps were used."
---

[[MOC-Module-14]]

# Module 15 — Network Logs Monitoring and Analysis

> [!abstract] Scope
> **8 LOs** · PDF pp. 4–151 (book pp. 2244–2391) · **152 pages** · 35 notes · 190 cards.
> What a log is and why you need one → the **Windows** event pipeline down to the EVT binary
> header → **Linux** (`/var/log`, syslog.conf, severities) → **Mac** (five log types, the Console) →
> **firewalls** (Windows Defender, macOS application firewall, iptables, Cisco ASA, Check Point) →
> **routers** (Cisco severity levels, `show logging`) → **web servers** (IIS/W3C, Apache) → and then
> **centralized logging**, the seven-step pipeline that closes it.
> **The shape trap:** the module teaches the *same* 0–7 severity scale on **five different devices**
> and names it **five different ways**, printing the number beside the name on only some of them.
> Anything asking "which severity is X" is testing the *device's* table, not a global standard.
> The second trap is the **format tables whose two columns do not line up** — Tables 15.1, 15.3, 15.5,
> 15.7, 15.8, 15.10, 15.11, 15.19 and 15.20 each print a different number of names and descriptions.
> The vault lists the columns **separately rather than pairing them**, and says so.

## Sections
| LO   | §    | Section                                             | PDF pp. | Book pp.    | Notes |
| ---- | ---- | --------------------------------------------------- | ------- | ----------- | ----- |
| LO01 | 15.1 | Logging concepts                                    | 4–13    | 2244–2253   | 3 |
| LO02 | 15.2 | Log monitoring and analysis on Windows systems      | 14–35   | 2254–2275   | 5 |
| LO03 | 15.3 | Log monitoring and analysis on Linux systems        | 36–46   | 2276–2286   | 3 |
| LO04 | 15.4 | Log monitoring and analysis on Mac systems          | 47–58   | 2287–2298   | 3 |
| LO05 | 15.5 | Log monitoring and analysis on firewalls           | 59–88   | 2299–2328   | 6 |
| LO06 | 15.6 | Log monitoring and analysis on routers              | 89–97   | 2329–2337   | 3 |
| LO07 | 15.7 | Log monitoring and analysis on web servers          | 98–115  | 2338–2355   | 5 |
| LO08 | 15.8 | Centralized log monitoring and analysis             | 116–151 | 2356–2391   | 7 |

p152 is the Module Summary and is carried in `15-LO08g`. p1 the module divider, p2 the
intentionally-blank page, p3 the objective list — which **is** clean here: all eight subjects print
correctly in both the numbered column and the prose list at the foot of the page. p3 also carries the
module's only framing sentence: "To enhance the security of an organization, extensive monitoring and
analysis of network logs is critical."

## Technical focus

- **LO01 — logging concepts.** Four types of logging _(Mod 15 p5)_: **Security** (identifying and
  *responding* to security activity — threats, viruses, malware, data loss; records user login and
  unauthorized access) · **Operational** (system-processing activities; failures and potentially
  actionable conditions; service provisioning and financial decisions) · **Compliance** (explicitly
  "**a part of security logging**" — regulations that enhance the security of systems and data) ·
  **Application debug** (for *developers, not system administrators*; enable/disable on circumstantial
  requirement). Two **transfer mechanisms** _(Mod 15 p6)_: **push-based** (save to local disk **or send
  over the network**, which then needs a **log collector**) with **syslog** and **SNMP** named as the
  two main push protocols, and **pull-based** (the system pulls from the source, client–server model,
  usually a **proprietary format** — the printed example is **Check Point's OPSEC C library**). The
  six **needs** _(Mod 15 p7)_: identify security incidents · monitor policy violations · identify
  fraudulent activity · identify operational and long-term problems · establish baselines · ensure
  compliance with laws, rules, and regulations. The three uses _(Mod 15 p8)_: **troubleshooting**
  (and the page's own catch — ordinary logs are *not enough for network problems*, "**Syslog need to
  be utilized**"), **forensics** (a "permanent source of record that cannot be altered through the
  normal course of actions", chronological, and a **backup source of evidence** if the original is
  suspected tampered), and **incident response** (correlate events across devices because the devices
  usually cannot). Ten things a log carries _(Mod 15 pp10–11)_: user identification information · date
  and time · type of event · success or failure indication · event origination point · description ·
  severity · service name · protocol · user. **The nine logging requirements** _(Mod 15 p9)_ are the
  highest-yield list in the module.
  → [[15-LO01a-Log-Types-Sources-and-the-Need-for-Logs]]
  [[15-LO01b-Troubleshooting-and-Logging-Requirements]]
  [[15-LO01c-Typical-Log-Format-and-Logging-Approaches]]

- **LO02 — Windows.** **Event Viewer** and its log/registry location, then the file format, which is
  the part examiners like. The `.EVT` file is an **ELF LOGFILE HEADER** + a sequence of
  **EVENTLOGRECORD** blocks; the header carries `HeaderSize` printed as `0 x 30` and a `Signature`
  printed both `0x654c664c` and `Ox654c664c` (Tables 15.1–15.3, pp16–21). Records **wrap** — the
  p18 figure shows record numbers 102, 103, 299, 300, 301, 400. The **ten fields of a log entry**
  _(Mod 15 pp24–25)_: **Level** (Error, Warning, Information, Success Audit, Failure Audit) ·
  **Keywords** (AuditFailure, AuditSuccess, Classic, Correlation Hint, Response Time, SQM, WDI
  Context, WDI Diag) · **Date and time** · **Source** · **Event ID** ("a unique event ID is assigned
  for each type of event") · **Task category** · **User** · **Operational code** · **Log** ·
  **Computer**. p23 prints an abridged **six**-item version of the same list — both are in the notes.
  → [[15-LO02a-Windows-Logs-and-Event-Viewer]]
  [[15-LO02b-Windows-Event-Log-File-Format]]
  [[15-LO02c-Windows-Event-Log-Types-and-Entries]]
  [[15-LO02d-Monitoring-and-Analyzing-Windows-Logs]]
  [[15-LO02e-Filtering-and-Examining-Event-Log-Entries]]

- **LO03 — Linux.** The `/var/log` inventory _(Mod 15 pp39–40)_ — **messages**, **auth.log**,
  **kern.log**, **cron.log**, **maillog**, **mail.log**, **boot.log**, **btmp** ("a record of all
  unsuccessful logon attempts"), **xferlog** ("a record of FTP file transfers"), **daemon.log**,
  **mysqld.log**, plus Apache **access_log**/**error_log**. The **syslog.conf** machinery
  _(Mod 15 p42)_ uses **selector.action** pairs, with the printed selectors `*.info.none;news.none;authpriv.none;cron.none`,
  `kern.*`, `authpriv.*`, `mail.*` and the facilities auth, authpriv, cron, kern, mail. The severity
  table _(Mod 15 p43)_ is where the trap lives: the printed **Severity Level** column carries only
  **seven** labels (the eighth is named only in the prose) and the **Severity Value** column carries
  only **1–7** — **no value is printed for the Emergency row**, and the page states the range is
  "starting from level 0 to level 7 … the highest severe message is at level 0". The page prints
  "**Waming**" in the table and "Level 4—Warning" in the prose.
  → [[15-LO03a-Linux-Logs-and-Log-Files]]
  [[15-LO03b-Linux-Log-Format-and-Severity-Levels]]
  [[15-LO03c-Commands-to-Monitor-and-Analyze-Linux-Logs]]

- **LO04 — Mac.** Five log types _(Mod 15 pp50–53)_: **secure.log** in `/private/var/log`
  (login/logout; attempted and successful unauthorized activity) · **appfirewall.log** at
  `/private/var/log/appfirewall.log` (written by `appfwlogd`) · **user-specific logs** — the page
  prints "found in the folder" and **never names it** · **`.bash_history`** in the root user's home
  · **system.log**. The **log line format** _(Mod 15 p54)_ names only **three** parts — the date and
  time in the `DD HH SS` format, the **host service**, and the **message** — and the two printed
  renderings of the `Syntax:` string disagree with each other, so the vault quotes both and repairs
  neither. Then **system.log** and the **Console** walkthrough, whose dialogs are GUI non-evidence.
  → [[15-LO04a-Mac-Logs-and-Console]]
  [[15-LO04b-Mac-Types-of-Logs-and-Log-Files]]
  [[15-LO04c-Mac-Log-Format-and-System-Logs]]

- **LO05 — firewalls.** The largest section, 30 pages, five vendors. The **definition** _(Mod 15 p60)_:
  "the capability of a firewall to log users' activities in a network" — and the page's own claim that
  it is "the most important source for determining post attack scenarios", because **attackers leave
  footprints**. The **levels** are **O to 7** with level O of greatest importance, and the **seven
  items to look for** _(Mod 15 p61)_ are: IP addresses that are rejected and dropped · unsuccessful
  logins to the firewall and other critical servers · suspicious outbound activities from internal
  servers · **source-routed packets** · ports on which no application is running · stop/start/restart
  of firewall · change in firewall configuration. The **five steps** _(Mod 15 p62)_ run from "find the
  location of the log file" to "identify the location of the source IP address using IP address
  tracking tools". Then: **Windows Defender Firewall** (`wf.msc`, `pfirewall.log`, header + body,
  `-` for an empty field) · **macOS application firewall** (Table 15.7, whose descriptions contradict
  its own field names) · **iptables** (`/var/log/kern.log`, `tail -5`, `--log-prefix`) · **Cisco ASA**
  (**two** log formats — the **default** and **EMBLEM** — plus `show logging`, `grep`, and the
  ten message IDs of Table 15.10) · **Check Point** (`fw log`, `$FwDIR`, unification mode
  **initial / semi / raw**, the real-time flag printed as `-ftn`).
  → [[15-LO05a-Firewall-Logging-and-Analysis-Steps]]
  [[15-LO05b-Windows-Defender-Firewall-Logs]]
  [[15-LO05c-Mac-OS-X-Firewall-Logs]]
  [[15-LO05d-Linux-iptables-Logs]]
  [[15-LO05e-Cisco-ASA-Firewall-Logs]]
  [[15-LO05f-Check-Point-Firewall-Logs]]

- **LO06 — routers.** Cisco router log messages carry **no numerical identifiers** _(Mod 15 p89)_, are
  **at most 80 characters** and begin with a **percent sign** followed by an optional sequence number
  or timestamp. The **eight severity levels O to 7** come with the **UNIX syslog names** in Table 15.12
  — `LOG EMERG`, `LOG ALERT`, `LOG CRIT`, `LOG ERR`, `LOG WARNING`, `LOG NOTICE`, `LOG INFO`,
  `LOG DEBUG` — and the page states the rule plainly: "**The lower severity number represents a higher
  severity and vice-versa**". Ten `%SEC-` mnemonics in Table 15.11, three of which the page **repeats**
  as rows 8–10. Configuration is `service timestamps log [datetime | log]` plus `show logging`,
  `show logging history`, and the `show logging | include 172.16.1.92 .* \(137\)` filter.
  → [[15-LO06a-Cisco-Router-Log-Messages-and-Severity]]
  [[15-LO06b-Monitoring-and-Analyzing-Router-Logs]]
  [[15-LO06c-Router-Logging-Configuration-and-Sample-Log]]

- **LO07 — web servers.** **IIS** first: the **three default locations** for 6.0, 7.0 and 8.0/10.0,
  then the **W3C Extended** fields of Table 15.15 and the **IIS vs NCSA** comparison of Table 15.16 —
  where IIS is **fixed, comma-separated, local time** and NCSA is **space-separated, local time**, and
  the page adds that NCSA is "used for websites and not for FTP sites". The analysis walkthrough
  _(Mod 15 p105–p106)_ reads `u_ex180405.log` under `C:\inetpub\logs\LogFiles\W3SVC1\` and its
  punchline is the **`sc-status`** column — "the capability of the server in responding to requests" —
  where the printed capture shows the **same request answered 301 and then 403**, `sc-substatus` 14
  on the 403. Then **Apache**: `access_log` and `error_log`, the `tail -100` and RHEL path
  contradiction, and the `LogFormat` directive tables (15.17 common, 15.18, 15.19 combined) — the last
  of which prints **`%P` for both Server Port and Server Process ID**.
  → [[15-LO07a-IIS-Logs-and-Fields]]
  [[15-LO07b-IIS-Field-Tables-and-Request-Types]]
  [[15-LO07c-Monitoring-and-Analyzing-IIS-Log-Files]]
  [[15-LO07d-Apache-Error-and-Access-Logs]]
  [[15-LO07e-Apache-Access-Log-Fields-and-Monitoring]]

- **LO08 — centralized logging.** The **why** _(Mod 15 pp117–118)_ and the **three tiers** of the
  architecture — **log generator** · **log analysis and storage** · **log monitoring** — then the
  **seven steps** _(Mod 15 pp121–122)_ that are the spine of the module: **Log Collection → Log
  Transmission → Log Storage → Normalization → Log Correlation → Log Analysis → Alerting and
  Reporting**. Transport mechanisms are **syslog UDP, syslog TCP, encrypted syslog, HTTP/HTTPS, SOAP
  over HTTP**, plus **SNMP** and **FTP/SCP** named without detail. The **syslog** mechanism and the
  **RFC 5424** format `TIMESTAMP HOSTNAME TAG MESSAGEID STRUCTURED-DATA MSG` with **APP-NAME**,
  **PROCID** and **MSGID**, the **collector vs relay** split, Table 15.20's **facilities** and Table
  15.21's **severities** (names only — no numbers are printed), and the collector tools. Then
  **storage and normalization** (three decision headings, the parsing-regex figure, and the one
  mention of **Common Event Expression (CEE)**), **correlation** (**micro-level** — "also known as
  atomic correlation", field + rule correlation — versus **macro-level** with its six inputs, of which
  only three are described), **log analysis** (manual vs automated), the **twelve best practices**,
  and the **challenges** — for which the slide's three bullets and the prose's four sub-items were
  never aligned.
  → [[15-LO08a-Why-Centralized-Logging]]
  [[15-LO08b-Centralized-Logging-Infrastructure]]
  [[15-LO08c-Log-Collection-and-Log-Transmission]]
  [[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]]
  [[15-LO08e-Log-Storage-and-Log-Normalization]]
  [[15-LO08f-Log-Correlation-and-Log-Analysis]]
  [[15-LO08g-Alerting-Reporting-Best-Practices-Tools-Challenges]]

## Exam facts
- Exam **312-38** · 4 h · 100 questions. Module-level weight not stated in the courseware →
  `exam_weight: unknown`. Module 15 sits in blueprint domain 6 **Incident Detection = 10%** (10 of
  100) **shared with module 14** — see [[Exam-Facts]]. The bank uses a **flat 5 per module**.
- Strong question sources, in rough order of yield:
  - **The nine Requirements for Logging** (p9) and the five-item "You should be able to" subset —
    two overlapping printed lists on one page, and the trap is that "prevent unauthorized access and
    manipulation **to** the logs" (callout) vs "**of** the logs" (list) are both printed.
  - **The four types of logging** and the two transfer mechanisms — specifically that **syslog and
    SNMP are the two main *push*-based** protocols and that **pull** means a proprietary format.
  - **The 0–7 severity scale and the rule "the lower number = the higher severity"** — then which
    device's *table* is being asked about.
  - **The seven steps of centralized logging** and the p152 eight-step variant.
  - **The five log types on Mac** and the two **unrecoverable** details (the unnamed user-specific
    folder, the self-contradicting `Syntax:` string).
  - **The seven items to look for in a firewall log** and the **five steps** of firewall log analysis.
  - **The W3C `#Fields:` order** and `sc-status` as the server-capability column; the printed 301-then-403
    pattern.
  - **IIS vs NCSA** — fixed/comma/local vs space/local, and "not for FTP sites".
  - **The three tiers** of centralized-logging infrastructure and the six **macro-level correlation**
    inputs (of which watch list and geographic location are never defined).
  - **The twelve log-analysis best practices** — and the first two are the exam-shaped ones
    (synchronize with **NTP**; treat log analysis as **proactive**, not reactive).
  - **Trivia-looking items that are printed and therefore fair**: the `-` for an empty Windows
    firewall field, `wf.msc`, `pfirewall.log`, `appfwlogd`, the `Ox` (letter O) hex prefix,
    `initial`/`semi`/`raw` unification modes, `EMBLEM`, `0 x 30`, `0x654c664c`, and Check Point's
    **OPSEC C library** as the printed pull-mechanism example.
- Deliberate distractors to expect:
  - **"Ordinary log files are enough to troubleshoot network problems"** — p8 says the opposite and
    names syslog as the answer.
  - **"Compliance logging is a separate category from security logging"** — the page says compliance
    logging **is a part of** security logging.
  - **"Application debug logging is for system administrators"** — the page says developers.
  - **"A higher severity number means a more severe event"** — the page states the reverse.
  - **"The 0–7 numbering is printed next to every severity name in the module"** — it is not. Table
    15.21 prints **no numbers at all**, and the p43 table leaves the Emergency value cell blank.
  - **"The standard syslog port is 514"** — the module **never prints a syslog port number**. p126
    refers to "the standard syslog port" and stops. Nothing was supplied from outside the PDFs.
  - **"The three IIS versions share one default log path"** — three different paths, three different
    case variants.
  - **"Table 15.20 numbers the syslog facilities from 0"** — code 0 is never printed and the
    name-to-code alignment is off by one.
  - **"Manual log analysis is faster than automated"** — the page's best practice is to *automate* it
    because it "takes less time and minimizes human interaction".
  - **"Log analysis is a reactive activity"** — the page says the opposite.
  - **"Watch list correlation is described as a macro-level correlation input"** — it is *named* as
    one and described nowhere.
  - **Any Wireshark, Windows or Apache version number** — none is printed in body text in this module.
  - **Any syslog port, CEE standard number, or expansion of "CLM"** — none is printed.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("20-Notes/Module-15")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/15-network-logs-monitoring-and-analysis-map.canvas|Network Logs Monitoring and Analysis Map]]
- Flow to visualize: **what a log is** (four types → two transfer mechanisms → six needs → nine
  requirements → ten things a log carries) → **one host OS at a time**, each with its own file
  inventory, its own field list and its own severity table: **Windows** (Event Viewer → the `.EVT`
  ELF header and EVENTLOGRECORD) → **Linux** (`/var/log` inventory → `syslog.conf`
  selector.action → severities) → **Mac** (five log types → the three-part line format → system.log
  and the Console) → **firewalls**, one vendor each (Windows Defender → macOS application firewall →
  iptables → Cisco ASA with its two formats → Check Point) → **routers** (no numeric IDs, 80 chars,
  `%` prefix, 0–7 with the UNIX names) → **web servers** (IIS locations → W3C fields → `sc-status`
  → Apache directives) → then the **pivot to centralization**: why → three tiers → the **seven-step
  pipeline** (collection → transmission → storage → normalization → correlation → analysis →
  alerting and reporting) → syslog/RFC 5424 and the collector tools → storage and normalization →
  correlation (micro vs macro) → analysis (manual vs automated) and the twelve best practices →
  tools and the challenges.

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]] · [[Exam-Facts]]
- Related modules: [[MOC-Module-14]] (Network Traffic Monitoring — the other half of blueprint domain
  6; this module is the log-record side of the same detection problem) · [[MOC-Module-18]]
  (Preventing and Securing Against Attacks — the endpoint and firewall logging the courseware
  presupposes) · [[MOC-Module-19]] (Managing Network Security — the policy, risk and SLA layer that
  "ensure compliance" and "audit trail" point at) · [[MOC-Module-13]] (Enterprise Wireless — the
  only other module in the vault with a named event-log platform, WIDS) ·
  [[MOC-Module-08]] (Network Device Security and Hardening — the device configuration whose logs
  LO05/LO06 read) · [[MOC-Module-11]] (Auditing and Continuous Monitoring — the audit-trail
  framing that runs through LO01) · [[MOC-Module-03]] (Technical Network Security — the protocol
  names the log fields refer to).

## Unresolved
- **The p152 Module Summary enumerates EIGHT steps where the body numbers SEVEN** — it splits
  Step 7 into "alerting" and "reporting" (see frontmatter).
- **"CLM" is used once and never expanded anywhere in the 152 pages.**
- **The p152 summary drops "logging" from the p121 triad**, so the slide names three phases where
  the body names four.
- **The 0–7 severity scale is named five different ways across five devices**, and the number is
  printed beside the name on only some of them (see frontmatter for the full set).
- **Table 15.20's facility codes are off by one** and code 0 is never printed — the alignment cannot
  be repaired from the page.
- **Table 15.21 prints severity names with no numeric column at all.**
- **No syslog port number is printed anywhere in pp125–134**, though p126 names "the standard syslog
  port".
- **Two default Windows Defender Firewall log locations** (p63 vs p65) and **two Mac firewall log
  locations** (p69 vs p71) — the pages contradict themselves in both cases.
- **p108 contradicts itself on the Apache access-log path** — `/var/log/httpd/` in the text,
  `/etc/httpd/logs/` in the command.
- **Three IIS default paths print three different case variants** (p99).
- **Eight tables print mismatched name/description columns** and are reproduced as two unpaired
  lists rather than as tables: 15.1 · 15.3 · 15.5 · 15.7 · 15.8 · 15.10 · 15.11 · 15.19 · 15.20.
- **Table 15.7's descriptions contradict its own field names** — HOSTNAME described as a client IP
  address, SERVER described as a port.
- **Table 15.19 prints `%P` for both Server Port and Server Process ID**, and five of its directives
  are illegible.
- **Table 15.11 repeats three of its own mnemonics** as rows 8–10.
- **Table 15.10 prints ten message IDs against nine descriptions**; 710003 has none.
- **p52 prints ten Mac log locations against nine log-file names.**
- **p54's `Syntax:` string is printed two different ways on one page** and neither was repaired.
- **p74's two printings of the iptables sample line disagree**, and no `=` prints after `OUT` in
  either copy — the interface names are not recoverable.
- **p85 and p87 print the `fw log` syntax twice and neither printing is clean.**
- **Printed OCR damage kept verbatim rather than "fixed"** — `Ox` for hex zero throughout,
  `Waming` (p43), `08a—ACCEEPT` (p74), `endtirne` (p85), `DPT` missing from Table 15.8's field-name
  column, `lcmptype`/`lcmpcode` (p68), `/vat/ log/ syslog` and `'/vat/ log/btmp'` (pp39–40),
  `-8s` for `%s` (pp52–53), `'ErrorLog can …'` (p53), `MESSAGED` (p129), `-alert` for `.alert`
  (p43), `--10g-1eve1 4` (p74), `-ftn` (p86), `MOVE`/case drift in the three IIS paths (p99).
- **p143 "automated" vs "automatic"**, and the slide's **EXAMINER** against the prose's **NETWORK
  DEFENDER**.
- **p144's slide prints five best practices where the prose prints twelve** — and the page hedges with
  "some of the best practices".
- **p140 names six macro-level correlation inputs and describes three**; watch list and geographic
  location correlation are undefined anywhere.
- **p147's figure names twelve log-analysis tools and the prose describes ten** — LOGalyze and
  Logentries are figure-only, and figure tiles are non-evidence.
- **p133 contradicts its own source captions twice** (kiwisyslog.com vs solarwinds.com;
  netadmintools.com vs ezfive.com).
- **Three "Centralized Logging Challenges" slide bullets have no prose elaboration**, and the
  prose's four sub-items are never aligned to the slide's three bullets.
- **Screenshot and figure pages are non-evidence throughout** — 14 page/figure locations listed in
  the frontmatter, from which no dashboard value, panel label, sidebar entry or file size was read.
- **Deliberately not guessed**: the syslog port number · the expansion of "CLM" · the name of the
  Mac user-specific log folder · the exact printed spacing of the IIS user-agent string · the digit
  boundaries inside the IIS trailing numeric run (`301001076`, `40314030`) · five of Table 15.19's
  directives · the eight numeric column in Table 15.21 · the CEE schema · the Windows Defender
  Firewall's true default path · the Check Point `fw log` syntax.

## Quick review
How many learning objectives does module 15 have, and what is LO#08's span
?
Eight. LO#01 logging concepts · LO#02 Windows · LO#03 Linux · LO#04 Mac · LO#05 firewalls · LO#06 routers · LO#07 web servers · LO#08 centralized log monitoring and analysis (pp116–151, book pp2356–2391)

The four types of logging printed on p5
?
Security logging (identifying and responding to security activity) · Operational logging (system-processing activities, failures and potentially actionable conditions) · Compliance logging, which the page says is "a part of security logging" · Application debug logging, for application/system developers and not for system administrators

What is the relationship between compliance logging and security logging as the page states it
?
Compliance logging is "a part of security logging" — the regulations are developed to enhance the security of systems and data. It is not a separate category

The two mechanisms by which log sources transfer records
?
Push-based and pull-based. In a push-based mechanism the system or application either saves records on the local disk or sends them over the network, and a log collector is needed to collect them; syslog and SNMP are the two main push-based protocols. In a pull-based mechanism a system or application pulls the log records from a log source on a client-server model, usually stored in a proprietary format — the page's example is Check Point's OPSEC C library

The six tasks the page says logs can help with
?
To identify security incidents · to monitor policy violations · to identify fraudulent activity · to identify operational and long-term problems · to establish baselines · to ensure compliance with laws, rules, and regulations

Why does the page say ordinary log files are not enough, and what is the fix it names
?
Because they are not enough to troubleshoot network problems. The page names syslog: "Syslog need to be utilized for this purpose" — it records events and arranges them into log files, which is beneficial in monitoring OS activities and troubleshooting issues

What makes a log useful as evidence in forensics
?
Logs are a permanent source of record that cannot be altered through the normal course of actions, and they are stored in chronological sequence, so they describe not only what happened but also when and how it happened. When sent to another host or a central log collector they act as a backup source of evidence, especially useful if the original copy is suspected to have been tampered

The five things you should know before enabling logging capability
?
What to log · where to store the logs · methods for logging · tools required for logging · log format

Name four of the nine Requirements for Logging printed on p9
?
Any four of: determine applications and systems (including outsourced or cloud) on which event logging is enabled · configure the information system for providing correct security incidents · perform regular tuning and review of logs to minimize false positives · store events in event logs · normalize and aggregate security-related events · correlate the data sources to identify any malicious activity · synchronize timestamps of all the sources to perform correlation · prevent unauthorized access and manipulation of the logs · analyze security-based events that are to be stored in the event logs

The ten types of information the page says a typical log includes
?
User identification information · date and time · type of event · success or failure indication · event origination point · description · severity · service name · protocol · user

What is a Windows .EVT file made of
?
An ELF LOGFILE HEADER followed by a sequence of EVENTLOGRECORD blocks. The header carries HeaderSize printed as 0 x 30 and a Signature printed both 0x654c664c and Ox654c664c; records wrap, and the figure on p18 shows record numbers 102, 103, 299, 300, 301 and 400

The five values the Level field of a Windows log entry can take
?
Error, Warning, Information, Success Audit, Failure Audit

Name three Linux log files under /var/log and what btmp records
?
btmp "maintains a record of all unsuccessful logon attempts" and xferlog "maintains a record of FTP file transfers". The page also lists messages, auth.log, kern.log, cron.log, maillog, mail.log, boot.log, daemon.log and mysqld.log

What is the syslog.conf selector.action form, and which selectors does the page print
?
A facility/severity selector paired with an action, separated by a dot — the page prints *.info.none;news.none;authpriv.none;cron.none, kern.*, authpriv.* and mail.*, with the facilities auth, authpriv, cron, kern and mail

How many severity levels does the Linux table on p43 print a number for, and what is missing
?
Seven. The printed Severity Value column carries only 1 through 7 and no value is printed for the Emergency row, even though the prose on the same page states the range is level 0 to level 7 and that the highest severe message is at level 0. The Severity Level column likewise captures only seven labels, the eighth being named only in the prose as Level 7—Debug

The five types of Mac log and where secure.log lives
?
Security logs in secure.log, found in the /private/var/log directory, recording login/logout activities · Firewall logs in appfirewall.log · user-specific logs, whose folder the page never names · command line logs in .bash_history, in the root user's home directory · system logs in system.log

How many parts of a Mac log line does the page name, and what are they
?
Three only: the date and time in the DD HH SS format, the host service, and the messages. The page never splits the host-service part into separate hostname and process fields and names no facility or severity field, so none was supplied

What is firewall logging, and why does the page call it the most important source
?
"The capability of a firewall to log users' activities in a network." Firewall logging should be enabled for security reasons as it is the most important source for determining post attack scenarios — attackers leave their footprints when trying to pass through a firewall, so the logs give basic information about the attack

The seven severity levels of firewall logging, in the page's printed order
?
Emergency, alert, critical, error, warning, notification, informational, and debugging — level O to level 7, where the events at level O are of the greatest importance and those at level 7 are of least importance

Name four of the seven items the page says to look for in a firewall's log
?
Any four of: IP addresses that are rejected and dropped · unsuccessful logins to the firewall and other critical servers · suspicious outbound activities from internal servers · source-routed packets · ports on which no application is running · stop/start/restart of firewall · change in firewall configuration

The five steps of firewall log analysis
?
Find the location of the log file in the local computer/server · identify and analyze the fields in the firewall logs to collect evidence · interpret the firewall log for incoming and outgoing connections from different sources · find out the source IP address, destination IP address, and the action performed by the firewall to the incoming connection · identify the location of the source IP address using IP address tracking tools

What does the page say about a field with no value in a Windows Defender Firewall log
?
"If there is no value for a field, it is represented by (-)". The log file is divided into two parts, a header describing the static information about the log version and the available fields, and a body

Which two log formats does the Cisco ASA section give
?
The default log format and the EMBLEM log format. The ASA is also read with show logging, show logging history and a grep on a specified severity

What is printed for a Cisco router log message, and what does it not contain
?
A maximum of 80 characters beginning with a percent sign, followed by an optional sequence number or timestamp if configured. Router log messages do not contain numerical identifiers that assist in identifying the messages

The rule the page gives for Cisco router severity numbering
?
Log messages are categorized into eight severity levels ranging from 0 to 7, each with a number, a name and a UNIX syslog definition — and "The lower severity number represents a higher severity and vice-versa"

The eight UNIX syslog names printed in the router severity table
?
LOG EMERG · LOG ALERT · LOG CRIT · LOG ERR · LOG WARNING · LOG NOTICE · LOG INFO · LOG DEBUG

What is the default log location for IIS 8.0 and 10.0 as printed
?
%SystemDrive%\inetpub\logs\LogFiles — the W3SVC instance number is appended. The page prints three different case variants across versions: %system32%\LogFiles\W3SVCN for 6.0, %SystemDrive%\Inetpub\Logs\LogFiles\w3svcN for 7.0, and %SystemDrive%\inetpub\logs\LogFiles for 8.0 and 10.0

Which W3C field tells you the server could actually serve the request, and what does the printed capture show
?
sc-status — the page says to use it to find out the capability of the server in responding to requests. The printed capture shows the same GET /ECWebsite request from the same client answered 301 and then 403, with sc-substatus 14 on the 403

How do the IIS and NCSA log file formats differ as printed
?
The IIS log file format is fixed, comma-separated and uses local time. The NCSA Common format is fixed, uses spaces as separators and uses local time, and the page notes it is used for websites and not for FTP sites

The seven steps of centralized logging, monitoring and analysis
?
Log Collection → Log Transmission → Log Storage → Normalization → Log Correlation → Log Analysis → Alerting and Reporting. The p152 Module Summary instead enumerates eight, splitting the last step into alerting and reporting

Which three transport mechanisms does the page describe in prose for log transmission
?
Syslog UDP, syslog TCP and encrypted syslog, plus HTTP/HTTPS and SOAP over HTTP. SNMP and FTP/SCP are printed in the mechanism list but have no description section

The three tiers of the centralized logging infrastructure
?
Log generator · log analysis and storage · log monitoring. Clock daemon and Security/authorization messages are syslog facility names, not tier names

The RFC 5424 syslog message format as printed in the module
?
TIMESTAMP HOSTNAME TAG MESSAGEID STRUCTURED-DATA MSG — p129's figure prints MESSAGED instead of MESSAGEID, which is quoted as printed. APP-NAME identifies the originator of the message, PROCID the process name or process ID, and MSGID the type of message sent

What is the difference between micro-level and macro-level log correlation
?
Micro-level correlation correlates fields within a single event or set of events, is also known as atomic correlation, is performed only when raw event data is normalized, and is divided into field correlation and rule correlation. Macro-level correlation gains information from rule, vulnerability, profile (fingerprint), anti-port, watch list and geographic location correlation to validate and gain intelligence on the event stream

Two of the twelve log-analysis best practices
?
Log analysis system should be synchronized with the NTP server to avoid timing differences between the systems, and log analysis should always be considered as a proactive security initiative rather than a reactive one as it is often performed after an incident has occurred

Which of the module's values could NOT be recovered and are therefore not asserted anywhere
?
The syslog port number (p126 names "the standard syslog port" but prints no number) · the expansion of "CLM" used once on p152 · the name of the Mac user-specific log folder (p51 prints "found in the folder") · the numeric column of Table 15.21 · five directives in Table 15.19, where Server Port and Server Process ID both read %P
