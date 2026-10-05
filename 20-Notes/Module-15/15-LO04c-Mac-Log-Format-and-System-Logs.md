---
type: note
module: "15"
lo: "04"
tags: [concept, protocol, process, command, mod/15]
topic: "Mac Unix log format, system.log, and the search procedures"
exam_weight: unknown
status: done
unresolved:
  - "p54 the printed 'Syntax:' string is OCR-damaged and the two printings on the page do not agree: the callout box prints 'MW DD Host Service: Message' and the body prints 'ION DD HH:bN: ss Host Service: Message'. Both are quoted verbatim and NEITHER was repaired into 'MMM DD HH:MM:SS Host Service: Message'. Only the tokens 'DD', 'Host Service:' and 'Message' are legible in both."
  - "p54 the page names only THREE parts of the line - 'the date and time in the DD HH SS format', 'the host service', and 'the messages'. It never splits the host-service part into separate hostname and process fields, and it names no facility or severity field. The field list was therefore NOT expanded from outside knowledge."
  - "p54 the two renderings of the example rows disagree because of OCR: the body prints 'b4000000 : 00800000' where the table prints '>4000000: 00800000', and the process token prints as 'IOVendorSurface:' in the table but 'UniNEnet:' in the body against the table's 'pniNEnet:'. All printed forms are kept."
  - "p54 the Ethernet address on the last example row prints as '00: Oa:27 : eI : 09: 52 Hmt bit' in the table and is simply 'Ethernet address' in the body prose; not reconciled, not repaired."
  - "p54 the third example row is a two-column interleave in the OCR ('(Ix1@OHz , 32 bpp) . Display Rage128 : . Display Rage128 : user using'); reproduced as printed and not split into two lines."
  - "p55 the system.log sample excerpt was NOT reproduced. Its OCR interleaves two columns and mangles most tokens ('nacintoshsn', 'nepd', 'uSOC', 'minp011 12 maxpoii 17', 'nacineo.h.n eroti (2671'), and the running prose on p55 explains none of the lines, so no line was reconstructed. The one clean fragment, '17.254.0.27 offset 0.218634 sec', appears inside a mangled NTP line and is recorded here only as evidence that an NTP time-server address is present."
  - "p55 and p56 give the same path two ways: p55 prints '/private/var/log/system.log' and p56 prints '/private/var/log/system. log' (stray space before 'log'). Both kept."
  - "p56 prints the application-log path with scrambled word order - 'such as web server, Windows sharing components, and firewall and located at are /Users/Mac/Library/App1ication' (singular 'App1ication', digit 1 for letter l). Kept verbatim."
  - "p55/p57 the 'Go to folder' worked example is printed twice with slightly different wording - p55 and the p55 callout list 'web server, Windows sharing components, firewall (apache, samba, ipfw)'; the p57 body lists 'web server, firewall (apache, samba, ipfw)' and drops the Windows sharing components. Both kept."
  - "pp57–58 Figures 15.14 (Finder), 15.15 ('Go to the folder' dialog), 15.16 ('Find' dialog) and 15.17 ('Database Search' dialog) are GUI captures - treated as NON-EVIDENCE. Nothing was read from them: not the sidebar, not 'Go to the folder: /private/var', not 'Search in: Home', not 'Search for items whose: Name Content contains includes', not the example query 'Console without ObnoxiousLogger'/'does not contain', and not the option-key '+' / '-or-' hint. Only the numbered body steps were used."
---

[[MOC-Module-15]]

# Mac Log Format and System Logs (§15.LO#04c)

> **LO#04: Discuss log monitoring and analysis on Mac systems** _(Mod 15 p47)_
> Covers pp54–58.

## Mac uses standard Unix log format _(Mod 15 p54)_

> "**Mac computer system follows standard Unix log format**; most of the logs can be found in **plaintext form**."

⇒ the same format family as Linux → [[15-LO03b-Linux-Log-Format-and-Severity-Levels]] · Linux CLI for reading logs → [[15-LO03c-Commands-to-Monitor-and-Analyze-Linux-Logs]]

### Printed syntax _(Mod 15 p54)_

Two damaged printings of the same string, both quoted as printed:

| Where on p54 | As printed |
|---|---|
| Callout box | `Syntax: MW DD Host Service: Message` |
| Body prose | `that is, ION DD HH:bN: ss Host Service: Message` |

### The only field names the page gives _(Mod 15 p54)_

> "In the above example, **`May 14 18:20:12` represents the date and time** in the **DD HH SS format**; **`cannondale mach kernel` represents the host service**; and `00800000`, `. Display_Rage128 : user ranges num:l start:b6408000`, `. Display Rage128 : using (lx1@OHz , 32 bpp)`, **etc. represent the messages**."

| Part | Example value | Named by p54 as |
|---|---|---|
| 1 | `May 14 18:20:12` | date and time |
| 2 | `cannondale mach kernel` | host service |
| 3 | everything after the service | message |

The page stops at three parts — it does not name a separate hostname/process split, and no facility or severity field.

### Example lines _(Mod 15 p54)_

```
May 14 18:20 : 12 cannondale mach kernel: b4000000 : 00800000
May 14 18 : 20 : 12 cannondale mach kernel : ranges num:l start:b6408000 size: 180
May 14 18 : 20 : 12 cannondale mach kernel : (Ix1@OHz , 32 bpp) . Display Rage128 : . Display Rage128 : user using
May 14 18:20:12 cannondale mach kernel : IOVendorSurface: : set id mode: surface mode contains obsolete bit
May 14 18 : 20 : 12 cannondale mach kernel: UniNEnet: Ethernet address
```

Constant across every row: host `cannondale`, service `mach kernel`. Messages are **kernel graphics/display and Ethernet driver events**.

## Three log files by scope _(Mod 15 pp55–56)_

> "In Mac OS, the activities related to the **system, user, and application** are logged in **three types of log files: system log, user log, and the application log**." _(Mod 15 p56)_

| Log | What it gives details of | Path (as printed) |
|---|---|---|
| **System log** — `system.log` | "issues regarding the **whole Mac system** such as **DNS, networking**, and **Adium** messages" | **`/private/var/log/system.log`** _(p55)_ / `/private/var/log/system. log` _(p56)_ |
| **User log** | "issues regarding **user activities** such as **login/logout**" | `/Users/Mac/Library/Logs` |
| **Application log** | "issues regarding **installed applications** such as **web server, Windows sharing components, and firewall**" | `/Users/Mac/Library/App1ication` |

> "**The important things to notice in log files are timestamps and message.**" _(Mod 15 p56)_

`system.log` is the Mac counterpart of `/var/log/messages` → [[15-LO03a-Linux-Logs-and-Log-Files]] · the rest of the inventory → [[15-LO04b-Mac-Types-of-Logs-and-Log-Files]] · Console as the viewer → [[15-LO04a-Mac-Logs-and-Console]]

## Procedure 1 — finding logs with "Go to Folder" _(Mod 15 pp55–57)_

"**"Go to Folder" is the most useful Mac OS keyboard shortcut.** It is used to open the required log folder." _(p56)_
"There are **two ways** of accessing the Go to Folder option, **one is from Finder** and **the other is from desktop**." _(p56)_

**Using Finder _(Mod 15 pp56–57):**

1. "Go to the Finder in Mac operating and then click on the **"Go" menu**."
2. "Navigate down and select the **"Go to Folder" option**."

**Using the desktop _(Mod 15 p57)_:** use the **`Cmd+Shift+G`** key combination "to open "Go to the folder" utility".

**Worked example _(Mod 15 p55, p57):** "To find application logs such as web server, Windows sharing components, firewall (**apache, samba, ipfw**), etc. specify the **`/private/var`** in the "Go to the folder" box."

## Procedure 2 — searching for a particular log _(Mod 15 pp56–58)_

> "There are **two methods** to search a particular log in Mac OS: **one is through using the Edit menu** and **another is from the File menu**." _(Mod 15 p57)_

### Method 1 — Edit menu _(Mod 15 p58)_

1. "Click the **Edit menu** of Menu bar available at the top of the Mac desktop."
2. "Navigate to the **Find** option and then click it."
3. "**Provide the additional parameters to refine the search.**"

_(p56 callout: "Search the specific interest of logs by **`Edit->Find` Menu option** / Provide the additional parameters to refine the search.")_

### Method 2 — File menu → "New Database Search" _(Mod 15 p58)_

1. "Click the **File menu** of Menu bar available at the top of the Mac desktop."
2. "Navigate to the **"New Database Search"** option and then click it."
3. "**Implement the customized filter** in the popped up dialog box."
4. "**Granular search is possible by giving a sender-process name, facility-sending system destination, level-severity**, etc."

_(p56 callout: "Complex log search can be done by selecting **`File->New Database Search`** / Customized filter can be implement in the popped up dialog box / Granular search is possible **name — Facility-Sending system destination — Level-Severity**.")_

**Filter keys printed on p58:** `sender-process name` · `facility-sending system destination` · `level-severity` → same facility/severity idea as [[15-LO03b-Linux-Log-Format-and-Severity-Levels]]

Ship these records off-box → [[15-LO08a-Why-Centralized-Logging]] · Mac endpoint hardening → [[MOC-Module-07]]





