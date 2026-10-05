---
type: note
module: "15"
lo: "07"
tags: [tool, protocol, process, command, mod/15]
topic: "Monitoring and analyzing IIS log files: steps, W3C fields, time-taken"
exam_weight: unknown
status: done
unresolved:
  - "p105 the Notepad++ capture (uncaptioned, under the section title 'Monitoring and Analyzing Log Files in IIS') shows only the truncated header '#Software: Microsoft Internet Information Services 10.0 / #version: 1.0 / #Date: 2018-04-05 12:43:23 / #Fields: date time'; its log entries are cut off at the right edge of the window and were not transcribed."
  - "p105–106 the figure callouts ('Timestamp', 'IP Address of the Server', 'Client IP Address', 'sc-status', 'cs-method user issued a GET', 'The server port') are printed captions on callout diagrams, not body prose. Reproduced as caption labels only."
  - "p106 Figures 15.30 and 15.31 interleave the Notepad++ capture with annotation callouts, so the running prose of the figure cannot be transcribed as prose; only the printed window contents and the callout labels are reproduced."
  - "p106 in the cs(User-Agent) value the OCR renders word spaces as '+' and the letter l as the digit 1 (e.g. 'Mozi1la', 'APpleWebKit', '1ike'). Every token is individually legible but the exact printed spacing of the string could not be confirmed from the scan."
  - "p106 Figure 15.31 the four trailing numeric fields print with no separator between them - the raw run reads '301001076' and '40314030'. The split into sc-status / sc-substatus / sc-win32-status / time-taken is read off the digit counts against the '#Fields:' header, not from any separator the page prints."
  - "p105 Figure 15.30 its record lines are cut off at the right edge of the Notepad++ window mid-string at 'Chrome/52'; only Figure 15.31 on p106 shows the full record. Both figures show the same file, u_ex180405.log."
---

[[MOC-Module-15]]

# Monitoring and Analyzing IIS Log Files (§15.07)

> **LO#07: Discuss log monitoring and analysis on web servers** _(Mod 15 p3)_
> Covers pp105–107.

Related: [[15-LO07a-IIS-Logs-and-Fields]] ·
[[15-LO07b-IIS-Field-Tables-and-Request-Types]] ·
[[15-LO07d-Apache-Error-and-Access-Logs]] ·
[[15-LO01c-Typical-Log-Format-and-Logging-Approaches]].

## Why _(Mod 15 p105)_

> "Monitoring and analysis of web server logs **helps network defenders in determining intrusion
> attempts or successful intrusions**. Web server logs record **information about requests made by the
> users or clients**."

## Steps to monitor and analyze IIS log files _(Mod 15 pp105–106)_

Numbered walkthrough, as printed:

1. **Open the log file in a text editor**; "the **six digits of the log file name represent the day,
   month, and year** when the file was created (e.g., `ex011012.log`)."
2. **Trace the header information line that starts with `#Fields:`** — "this line is used to
   **determine the corresponding values of each column**."
3. **Identify when the request is created** with the date and time; **"`sitename`" and
   "`computername`" indicate which server responded to the request.**
4. **Identify who visited the web server** using **`c-ip`** (visitor computer's IP address).
5. "The **`cs-method`** column contains **"post" or "get" requests** made by the visitor's browser;
   **`cs-uri-stem`** and **`cs-uri-query`** represent the **resource (image/website) requested by the
   visitor**."
6. "Use the **`sc-status`** column to find out the **capability of the server in responding to
   requests**."
7. "Use **`cs(User-Agent)`** to find out **which type of browser was used by the visitor**."

| Step | Question it answers | Field |
|---|---|---|
| 1–2 | What is in each column? | `#Fields:` header |
| 3 | When, and which server answered? | date/time, `sitename`, `computername` |
| 4 | Who? | `c-ip` |
| 5 | What did they want, and how? | `cs-method`, `cs-uri-stem`, `cs-uri-query` |
| 6 | Did it work? | `sc-status` |
| 7 | What browser? | `cs(User-Agent)` |

## The `#Fields:` header and record shape _(Mod 15 p106)_

Figure 15.31 prints the W3C header for this capture cleanly; the record is one **space-separated**
line per request:

```text
#Software: Microsoft Internet Information Services 10.0
#Version: 1.0
#Date: 2018-04-05 12:43:23
#Fields: date time s-ip cs-method cs-uri-stem cs-uri-query s-port cs-username c-ip cs(User-Agent) cs(Referer) sc-status sc-substatus sc-win32-status time-taken
```

Read the header left to right and you get the record layout. Figure 15.31 prints **four records**;
the first, complete:

```text
2018-04-05 12:43:58 195.129.104.112 GET /ECWebsite - 80 - 213.69.168.60 Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/52.0.2743.116 Safari/537.36 Edge/15.15063 - 301 0 0 1076
```

Note the user-agent **wraps onto a second visual line** inside the Notepad++ window — it is one
logical field, not two. `Edge/15.15063` carries **no second dot**.

Reading the record against the header: `date` `time` → `s-ip` = **195.129.104.112** → `cs-method` =
**GET** → `cs-uri-stem` = `/ECWebsite` → `cs-uri-query` = `-` → `s-port` = **80** → `cs-username` = `-`
→ `c-ip` = **213.69.168.60** → `cs(User-Agent)` = the browser string → `cs(Referer)` = `-` → then the
four numeric fields. Only those last five vary between the four records:

| `time` | `cs(Referer)` | `sc-status` | `sc-substatus` | `sc-win32-status` | `time-taken` |
|---|---|---|---|---|---|
| 12:43:58 | `-` | **301** | 0 | 0 | 1076 |
| 12:43:58 | `-` | **403** | 14 | 0 | 30 |
| 12:44:07 | `-` | **301** | 0 | 0 | 159 |
| 12:44:07 | `-` | **403** | 14 | 0 | 0 |

All four records are the same `s-ip` / `cs-method` / `cs-uri-stem` / `c-ip` / user-agent. What the
capture shows is the **same request answered twice** — once **301** and once **403** — which is
exactly the pattern step 6 exists to catch: *the server redirecting, then refusing*.

> The callout captions printed on the figures name the same fields: **Timestamp**, **IP Address of
> the Server**, **Client IP Address**, **`sc-status`**, **`cs-method` user issued a GET**, and
> **The server port**.

"**Log files are created every time a request appears on the server session.**" _(Mod 15 p106)_
"The above example shows log file entries in W3C format with properties, date, time, client IP,
username, server sitename, server computername, server IP, method, URI stem, URI query, status,
time-taken, cookie, and user agent fields."

## The `time-taken` field _(Mod 15 p107)_

- "The **`time taken` field is initialized when the first byte is received by the HTTP server API**.
  This is performed **before parsing the request**."
- "The `time taken` field is **stopped when the last transmission is completed**."
- "The **first request to the site takes more time** as compared to the remaining requests; this is
  because the **HTTP server API needs to open the log file for logging the first request**."

> So `time-taken` is measured in **milliseconds** (p102), starts **before** parsing, ends at the
> **last transmission**, and the **first hit on a site is always the slowest** — that is a log-file
> open, not an attack.





