---
type: note
module: "15"
lo: "07"
tags: [tool, protocol, concept, mod/15]
topic: "IIS field tables (Table 15.15, 15.16), request types, NCSA Common format"
exam_weight: unknown
status: done
unresolved:
  - "Table 15.15 spans pp101–103 and its caption ('Table 15.15: Types of Fields in \"W3C Extended\" Log File Format') only prints on p103. The p101 rows are in 15-LO07a-IIS-Logs-and-Fields."
  - "p102–103 the 'Uses' cell for the Referer field runs over the page break: p102 ends with 'Can help identify the source of an attack or see if an attacker is using search' and p103 continues 'engines to find vulnerable sites'. Rejoined here; the cell is not truncated."
  - "p103 the IIS log file format example is printed as one wrapped line: '192.168.100.150, 03/6/11, 8:45:30, w3SVC2, SERVER, 172.15.10.30, 4210, 125, 3524, 100, 0, GET, /dollerlogo.gif, -'. Comma separators and single spaces are as printed."
  - "p103 Table 15.16 has two rows whose 'Appear as' cell is EMPTY in the printed table: Username (Description 'User is anonymous') and Windows status code (Description 'Request was fulfilled successfully'). Not filled in."
  - "p103 Table 15.16 prints the date as '03/06/2011' and the time as '8:45:30' in the 'Appear as' column, while the example log line on the same page prints '03/6/11' and '8:45:30'. Both kept as printed."
  - "p104 the NCSA example line prints 'a=10' in the request URI; the glyph is ambiguous between 0 and letter o in the scan. Rendered as 10."
---

[[MOC-Module-15]]

# IIS Field Tables and Request Types (§15.07)

> **LO#07: Discuss log monitoring and analysis on web servers** _(Mod 15 p3)_
> Covers pp102–104.

Related: [[15-LO07a-IIS-Logs-and-Fields]] ·
[[15-LO07c-Monitoring-and-Analyzing-IIS-Log-Files]] ·
[[15-LO01c-Typical-Log-Format-and-Logging-Approaches]].

## Table 15.15: Types of Fields in "W3C Extended" Log File Format — rows printed on p102

Continuation of the table whose p101 rows are in [[15-LO07a-IIS-Logs-and-Fields]]. Columns
`Field name` · `Description` · `Uses` — reproduced verbatim.

| Field name | Description | Uses |
|---|---|---|
| Server port (`s-port`) | The TCP port that received the request | The TCP port that received the request will verify the port when correlating with other types of request log files |
| Method (`cs-method`) | The HTTP method used by the client | Can help track down abuse of scripts or executables |
| URI stem (`cs-uri-stem`) | The resource accessed on the server | Can identify attack vectors |
| URI query (`cs-uri-query`) | The contents of the query string portion of the URI | Can identify injection of malicious data |
| Protocol status (`sc-status`) | The result code sent to the client | Can identify CGI scans, SQL and other injection, intrusions |
| Win32 status (`sc-win32-status`) | The win32 error code produced by the request | Can help identify script abuse |
| Bytes sent (`sc-bytes`) | The number of bytes sent to the client | Can help identify unusual traffic from a single script |
| Bytes received (`cs-bytes`) | The number of bytes received from the client | Can help identify unusual traffic from a single script |
| Time taken (`time-taken`) | The amount of server time, in milliseconds, taken to process the request | Can help identify unusual traffic from a single script |
| Protocol version (`cs-version`) | The HTTP protocol version supplied by the client | Can help identify older scripts or browsers |
| Host (`cs-host`) | The contents of the HTTP host header sent by the client | Can determine if the user browsed to the site by IP address or hostname |
| User agent (`cs(User-Agent)`) | The contents of the HTTP user agent header sent by the client | Can help uniquely identify users or attack scripts |
| Cookie (`cs(Cookie)`) | The contents of the HTTP cookie header sent by the client | Can help uniquely identify users |
| Referer (`cs(Referer)`) | The contents of the HTTP referer header sent by the client | Can help identify the source of an attack or see if an attacker is using search engines to find vulnerable sites |

**Field-name traps.** Three of the W3C field names are *not* hyphenated like the rest:
`cs(User-Agent)`, `cs(Cookie)` and `cs(Referer)` use parentheses, whereas the core ones use hyphens
(`c-ip`, `cs-method`, `cs-uri-stem`, `cs-uri-query`, `sc-status`, `sc-bytes`, `cs-bytes`,
`time-taken`, `cs-version`, `cs-host`, `s-port`, `s-sitename`, `s-computername`, `s-ip`,
`cs-username`).

**`s-bytes` vs `cs-bytes`** — the pair is genuinely asymmetric in this table: **`sc-bytes`** is the
number of bytes sent *to* the client, **`cs-bytes`** is the number of bytes received *from* the
client.

## IIS log file format _(Mod 15 p103)_

> "It is a **fixed (cannot be customized) ASCII text-based format**. It **records more information as
> compared to the NCSA Common format**. This format includes basic items such as client IP address,
> user information, date and time, service and instance, service status code, server name, and IP
> address, request type, number of bytes received, number of bytes sent, the target of operation,
> etc. Here, **each item is separated by comma and it uses local time to record time**."

```text
192.168.100.150, 03/6/11, 8:45:30, W3SVC2, SERVER, 172.15.10.30, 4210, 125, 3524, 100, 0, GET, /dollerlogo.gif, -
```

### Table 15.16: Types of Fields in IIS Log File Format _(Mod 15 pp103–104)_

Columns `Field` · `Appear as` · `Description` — reproduced verbatim, including the two empty
`Appear as` cells.

| Field | Appear as | Description |
|---|---|---|
| Client IP address | `192.168.100.150` | IP address of the client |
| Username | *(empty)* | User is anonymous |
| Date | `03/06/2011` | Log file entry was made on June 03, 2011 |
| Time | `8:45:30` | Log file entry was recorded at 8:45 A.M. |
| Service and instance | `W3SVC2` | This is a website, and the site instance is 2 |
| Server name | `SERVER` | Name of the server |
| Server IP | `172.15.10.30` | IP address of the server |
| Time taken | `4210` | This action took 4,210 ms |
| Client bytes sent | `125` | Number of bytes sent from client to server |
| Server bytes sent | `3524` | Number of bytes sent from server to client |
| Service status code | `100` | Request was fulfilled successfully |
| Windows status code | *(empty)* | Request was fulfilled successfully |

The last three rows of the table are printed on p104:

| Field | Appear as | Description |
|---|---|---|
| Request type | `GET` | User issued a GET or download command |
| Target of operation | `/dollerlogo.gif` | User wanted to download the DeptLogo.gif file |
| Parameters | | No parameters passed |

**Direction rule to hold on to:** `Client bytes sent` = 125 = bytes **client → server**;
`Server bytes sent` = 3524 = bytes **server → client**. Same words, opposite directions — the field
name tells you which endpoint the count is measured *from*.

## NCSA Common log file format _(Mod 15 p104)_

> "**Similar to the IIS log file format, it is also is a fixed ASCII text-based format.** However, it
> is **used for websites and not for FTP sites**. It records items related to user requests such as
> **remote hostname, username, date, time, request type, HTTP status code, and the number of bytes sent
> by the server**. Here, **each item is separated by spaces**, and it record time based on the
> **local time**."

```text
13.45 - Microsoft\fred [08/Apr/2001:17:39:04 -0800] "GET /scripts/iisadmin/ism.dll?http/serv HTTP/1.0" 200 3401
```

Three IIS formats side by side:

| | W3C Extended | IIS log file format | NCSA Common |
|---|---|---|---|
| Customizable? | **Yes** | No — fixed | No — fixed |
| Field separator | **spaces** | **comma** | **spaces** |
| Time basis | **UTC** | local | local |
| Scope | configurable property set | more fields than NCSA | **websites, not FTP** |




