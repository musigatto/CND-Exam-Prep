---
type: note
module: "15"
lo: "05"
tags: [concept, port, command, process, mod/15]
topic: "Windows Defender Firewall log: location, header, body fields"
exam_weight: unknown
status: done
unresolved:
  - "p65 first log line prints the destination address as '202.138.103.10Ã˜' - a stray Ã˜ inside an IPv4 octet. Quoted exactly as printed; no octet was completed and the damaged character was not assigned to any field."
  - "p65 prints the default log path with OCR l/1 confusion as '\\LogFi1es\\Firewa11\\Pfirewa11. log'. Quoted as printed, NOT normalised."
  - "p63 and p65 give TWO different default locations: p63's callout says 'Default firewall log location in windows is C:\\Firewall' and p65's prose says '\\LogFi1es\\Firewa11\\Pfirewa11. log'. The page contradicts itself; neither was corrected. The p65 prose is the fuller one."
  - "p63 prints the log filename in lower case as 'pfirewall.log' while p65's prose prints 'Pfirewa11. log'. Both kept as printed."
  - "p68 prints the ICMP fields as 'lcmptype' and 'lcmpcode' (lowercase L). The p67 Table 15.5 field list on the same spread prints 'icmptype' and 'icmpcode' cleanly, so this note uses Icmptype/Icmpcode. Substitution recorded."
  - "p67 Table 15.5 prints '#Vers ion', '#Fie1ds' and 'src— ip' / 'src—port' (OCR damage). This note uses #Version, #Fields, src-ip, src-port, dst-ip, dst-port - all attested in clean form elsewhere on pp63–68 (Table 15.6's Fields column and the #Fields example itself)."
  - "p63's figure prints '*Software: Microsoft Firewall' and stops the field list at 'tcpflag:'; p65/p66 print 'tcpflags' and p67 Table 15.5 prints 'tcpflags ... info path'. The p67 table form is used as canonical."
  - "p63 prints the command as 'wf .msc' with a space between the name and the extension; rendered here as wf.msc."
  - "p65 log block: the page's callout bullets interleave with the log lines, so line 2 loses its date/time prefix (the surviving fragment is '42') and lines 2 and 4 are cut at the tcpflags column. Reproduced as printed with '…' marking the cut; nothing was reassembled."
  - "p65/p66 print the packet-size column as 'e' and 'Ã¸' where p66's larger rendering of the same rows prints '0'. Each page's own characters kept."
---

[[MOC-Module-15]]

# Windows Defender Firewall Logs (§15.LO#05b)

> **LO#05: Discuss log monitoring and analysis in firewalls** _(Mod 15 p59)_
> Covers pp63–68.

> **Note _(p63):** "Windows firewall logging should be **enabled** to record firewall logs."

## What the log is _(Mod 15 p63)_

- "Windows Defender Firewall (**if enabled**) logs **all activities occurred in a network/system**."
- "**Every time when an attacker tries to break through Windows Firewall, the details of the entry are recorded in a log file.**"
- "**By default, Windows Firewall log is disabled** and it does not log any of its actions."
- "It is a **plain-text file** that can be viewed by any text editor such as **Notepad**."

**Stated limits of this log _(p63):**

> "This log is useful in identifying **suspicious and malicious activities**, but it **does not provide information to monitor the source of activity**. It is also **not beneficial when trying to determine the security status of the network**."

Location and format → also covered by [[15-LO02a-Windows-Logs-and-Event-Viewer]] · concept background → [[15-LO05a-Firewall-Logging-and-Analysis-Steps]]

## Location of the log _(Mod 15 pp63, 65)_

| | As printed |
|---|---|
| p63 callout | "Default firewall log location in windows is `C:\Firewall`" |
| p63 callout | "Open the file named as **`pfirewall.log`**" |
| p65 prose | "By default, the location of Windows log entries is **`\LogFi1es\Firewa11\Pfirewa11. log`**" |

**Size limit _(p65):** "it stores up to **4 MB** of data." Changing the log size limit "will affect the **performance** of the system".

> "Therefore, it is suggested to **enable Windows Defender Firewall logging only when you want to troubleshoot an issue actively**." _(p65)

## Enabling the log — the printed walkthrough _(Mod 15 pp63–65)_

1. p63 — "Press **"Win key + R"**", a **Run** box will open. "In that box, type **`wf.msc`** and press Enter."
2. p63 — "The **"Windows Defender Firewall with Advanced Security"** window will appear. Click on the **"Properties"** option located on the **right pane** of the window."
3. p64 — "Once a new dialog box appears, click the **"Private Profile"** tab and then select **"Customize"** available in the **"Logging"** portion of a dialog box."
4. p65 — "A new dialog box will appear where you can set the **location of log entries, maximum log size, whether to log only dropped packets, successful connection, or both**." → **OK**
5. p65 — "click the **"Public Profile"** tab and **repeat the same steps** performed for the "Private Profile" tab."
6. p65 — "On the main window ... click the **"Monitoring"** option located on the **left pane** of the window."
7. p65 — "click the **file path next to "File Name"** located under **"Logging Settings"** in the **details pane** to view the log file in Notepad."

_(p64 Figures 15.19 and 15.20 are GUI captures — NON-EVIDENCE. Nothing was read from the window: not the Domain/Private/Public Profile status text, not the left-pane items, not any dialog control.)_

## Log file structure: header + body _(Mod 15 p66)_

> "Windows Defender Firewall log file is **divided into two parts: header and body**. The **header** describes the **static** information regarding the **log version** and the **available fields**. The **body** displays the **compiled data of network traffic that is trying to move through the firewall**. This list is **dynamic** and keeps on **adding new log entries at the bottom of the log**."

> "**If there is no value for a field, it is represented by `(-)`.**" _(p66)_

## Sample log lines _(Mod 15 p65)_

```
2018-09-18 ALLOW UDP 192.168.0.124 202.138.103.10Ã˜ 51533 53 e - - - -
…42 ALLOW UDP 192.168.0.124 74.125.68.189 49240 443 e -
2018-09-18 ALLOW UDP 192.168.0.124 202.138.103.1Ã¸Ã¸ 63437 53 e - - - -
2018-09-18 ALLOW UDP 192.168.0.124 8.8.8.8 63437 53 - - - - - - -
```

- `…42` = the callout bullet has swallowed the date/time prefix; the surviving fragment is `42`.
- Trailing `-` runs = the `(-)` no-value marker of p66.
- p66 prints the same file's rows with `SEND` / `RECEIVE` in the Info column, e.g. `SEND`, `SEND - RECEIVE -`.

## Header part — Table 15.5 _(Mod 15 p67)_

| Information | Description |
|---|---|
| `#Version` | Displays the **version** of Windows Defender Firewall security log; for example, `#Version: 1.5` |
| `#Software` | Displays the **software name** creating the log; for example, `#Software: Microsoft Windows Firewall` |
| `#Time Format` | Displays **timestamps of the login local time**; for example, `#Time Format: Local` |
| `#Fields` | Displays the **static list of fields that are available for security log entries** (If available); for example, the line below |

```
#Version: 1.5
#Software: Microsoft Windows Firewall
#Time Format: Local
#Fields: date time action protocol src-ip dst-ip src-port dst-port size tcpflags tcpsyn tcpack tcpwin icmptype icmpcode info path
```

⇒ **18 fields**, in that order.

## Body part — Table 15.6 _(Mod 15 pp67–68)_

| Fields | Description |
|---|---|
| **Date** | Displays the date of the log transaction in the **`YYYY-MM-DD`** format; for example, `2015-06-19` |
| **Time** | Displays the time of the log transaction in the **`HH:MM:SS`** format. The hours are displayed in **24-h** format; for example, `22:00:32` |
| **Action** | Displays **which operation was noticed by Windows Defender Firewall**. Available options are **OPEN** (indicates the connection is opened), **CLOSE** (indicates the connection is closed), **DROP** (indicates connection is dropped), **OPEN-INBOUND** (indicates inbound session is opened), and **INFO-EVENTS-LOST** indicates (events appeared but not recorded in the log) |
| **Protocol** | Displays the **protocol** used for communication such as **TCP, UDP, or ICMP** |
| **src-ip** | Displays **source IP address**; for example, `192.168.2.48` |
| **dst-ip** | Displays **destination IP address**; for example, `134.170.108.224` |
| **src-port** | Displays **source port number of the sending computer**; for example, `56092` |
| **dst-port** | Displays the **port number of the destination computer**; for example, `443` |
| **Size** | Displays **packet size (bytes)** |
| **Tcpflags** | Displays **TCP control flags in the TCP header** of an IP packet |
| **Tcpsyn** | Displays **TCP sequence number** in the packet |
| **Tcpack** | Displays **TCP acknowledgment number** in the packet |
| **Tcpwin** | Displays **TCP window size (in bytes)** in the packet |
| **Icmptype** | Displays a number that represents the **Type field of the ICMP message** |
| **Icmpcode** | Displays a number that represents the **Code field of the ICMP message** |
| **Info** | Displays an entry that **depends on the type of action** that occurred; for example, **`SEND`** |
| **Path** | Displays the **direction of the communication** |

### Action values — the exam list _(Mod 15 p67)_

`OPEN` · `CLOSE` · `DROP` · `OPEN-INBOUND` · `INFO-EVENTS-LOST`

### Printed field → value pairs worth memorising _(Mod 15 pp67–68)_

| Field | Printed example |
|---|---|
| Date | `2015-06-19` (`YYYY-MM-DD`) |
| Time | `22:00:32` (`HH:MM:SS`, 24-h) |
| Protocol | TCP / UDP / ICMP |
| src-ip / dst-ip | `192.168.2.48` / `134.170.108.224` |
| src-port / dst-port | `56092` / `443` |
| Info | `SEND` |

## Monitoring and analysis _(Mod 15 p66)_

> "From the available firewall log information, **only part of the information is important for analysis** and monitoring for **malicious activity** or for **debugging application failures**."
>
> "During analysis, if **any suspicious activity is detected**, then open the firewall log file in **any text editor (Notepad, by default)** to troubleshoot the issue."

_(p66 Figure 15.22 and p65 Figure 15.21 are screenshots — NON-EVIDENCE. No column header, row or control was read from them; only the log lines and header keywords that the body text and tables also print are reproduced above.)_







