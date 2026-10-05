---
type: note
module: "15"
lo: "05"
tags: [tool, command, concept, mod/15]
topic: "Linux iptables logs"
exam_weight: unknown
status: done
unresolved:
  - "p73 the 'Sample Firewall Log File' capture is heavily OCR-damaged: hostname reads 'oealhost'/'localhost', '=' is read as '—' or 'Z', 0x literals read as 'OxOO'/'–xOO', 'TTL' reads as 'rn'/'TTI.', and the first line is interleaved with the running footer ('31.85 Exam 312-38 CND the logento'). Only the two most legible lines are quoted; the rest is not reconstructed."
  - "p74 the field-name column of Table 15.8 prints 8 names in block 1 (Time, Machine Name, Action, IN, OUT, SRC-IP, DEST-IP, LEN) and 8 in block 2 (Field, PREC, FRAG, PROTO, SPT, WINDOW, RES, SYN, URGP) while the description column prints 10 + 11 entries; the two columns are therefore listed separately and are NOT paired, because the pairing is not recoverable from the page. 'DPT' appears in the printed sample log line but not in the printed field-name column."
  - "p74 the printed sample log line is damaged and the two printings disagree: 'RULE 08a—ACCEEPT', 'IN=eth1' (first copy) vs 'IN—ethi' (second copy), 'OUT ethO' (no '=' prints in either copy), 'Tos=oxoo' (first copy) / 'TOS=OxOO' (second copy), 'WINDOW-32767' (first copy) / 'WINDOW=32767' (second copy). Quoted as printed; the interface names are not recoverable."
  - "p74 the third command prints the level flag as '--10g-1eve1 4'; the fourth command on the same page prints '--log-prefix' cleanly, so only the level flag is garbled. Neither '--log-level' nor '--10g-1eve1' is completed by inference."
  - "p75 '/var/log/kern. log' — the OCR inserts a space before 'log'; written here as /var/log/kern.log."
  - "p75 the recent-entries command prints as 'tail — 5 / var/log/messages' (em dash where the flag separator belongs); written here as 'tail -5 /var/log/messages'. The value 5 is stated in the following sentence ('displays five most recent entries of iptables log')."
  - "p75 walkthrough step 2 is printed incomplete: 'Execute the command to get the details of recent logs in iptables stored'."
---

[[MOC-Module-15]]

# iptables Logs (§15.05)

> **LO#05: Discuss log monitoring and analysis on firewalls** _(Mod 15 p59)_
> Covers pp73–75.

Related: the four firewall log sources as a set —
[[15-LO05a-Firewall-Logging-and-Analysis-Steps]] · [[15-LO05b-Windows-Defender-Firewall-Logs]] ·
[[15-LO05c-Mac-OS-X-Firewall-Logs]] · [[15-LO05e-Cisco-ASA-Firewall-Logs]] ·
[[15-LO05f-Check-Point-Firewall-Logs]].
Linux log mechanics: [[15-LO03a-Linux-Logs-and-Log-Files]] ·
[[15-LO03c-Commands-to-Monitor-and-Analyze-Linux-Logs]].

## What iptables is _(Mod 15 p73)_

> "iptables is a **rule-based inbuilt firewall** in different versions of Linux OS."

- "It can **allow, drop, or modify** network traffic coming in and going out of a system through a set of **configurable table rules**."
- "It contains a set of **tables** that help process packets in some specific manner. These tables include multiple **chains** that investigate network traffic at various points."
- "These chains have built-in or user-defined rules that describe the action to be performed on a packet."
- "When a packet appears, iptables **matches it against the rules**. If a match is found, a **TARGET** is given to it. A target can be another chain to match with or any of the given values."

| TARGET | Printed behaviour |
|---|---|
| `Accept` | "The packet is allowed to pass through." |
| `Drop` | "The packet is disallowed to pass through." |
| `Return` | "The packet is returned to the chain from where it was called in a table." |

"If a match is not found, the **default action** is followed."

## Log storage _(Mod 15 p73)_

> "By default, iptables log entries are stored in **/var/log/messages**."

- Slide bullet _(p73)_: iptables logs "messages to a **/var/log/messages** file through the Linux **syslogd daemon**".

## Sample firewall log file _(Mod 15 p73)_

The page prints a "Sample Firewall Log File" capture — `localhost kernel:` lines. Two of the least
damaged lines, **as printed**:

```text
localhost kernel: IN—ethO OUT— SRC—69.89.31.85 DST=206.253.165.112 LENZ60 TOS=OxOO PREC=OxOO TTL=57 ID=6671 DF PROTO=TCP SPT=57972 DPT=873 WINDOW=5840 RES—OxOO SYN URGP=O sep 19

localhost kernel: IN=ethO OUT— SRC=206.253.165.168 : DST=206.253.165.255 LEN—137 TOS—OxOO PREC—OxOO TTL=128 ID=12680 PROTO=UDP SPT=17500 DPT=17500 LEN—II 7
```

Values visible across the capture: `SRC=69.89.31.85` and `SRC=206.253.165.168` → `DST=206.253.165.112`
and `DST=206.253.165.255`; `PROTO=TCP` with `SPT`/`DPT` pairs `57361→5432`, `57972→873`, `58049→873`,
`57438→5432`; `PROTO=UDP` with `SPT=137 DPT=137` and `SPT=17500 DPT=17500`; `TTL=57` / `TTL=128`; `sep 19`.
See `unresolved` — the capture is badly damaged and is not completed by inference.

## iptables log format and fields _(Mod 15 p74)_

> "The iptables log file is displayed in the following format:"

The page prints the format example **twice**, and the two printings differ. First printing, prefixed
`Eg:`, has `IN=eth1`, `Tos=oxoo` and `WINDOW-32767`; the second, as reproduced here, has `IN—ethi`,
`TOS=OxOO` and `WINDOW=32767`:

```text
June 16 21:12:56 FW2 kernel : RULE 08a—ACCEEPT IN—ethi OUT ethO SRC= 192.42.93.30 DST= 192.168.1.102 LEN=96 TOS=OxOO PREC=OxOO TTL=64 ID=61495 DF PROTO=UDP SPT=53981 DPT=127 WINDOW=32767 RES=OxOO SYN URGP=O
```

Left to right this line carries `June 16` · `21:12:56` · `FW2` · `kernel` · `RULE` · `08a—ACCEEPT` ·
`IN` · `OUT` · `SRC=` · `DST=` · `LEN=` · `TOS=` · `PREC=` · `TTL=` · `ID=` · `DF` · `PROTO=`
· `SPT=` · `DPT=` · `WINDOW=` · `RES=` · `SYN` · `URGP=`.

> The two interface values are the **least reliable tokens on the page**: the printings disagree
> (`IN=eth1` vs `IN—ethi`) and **no `=` prints after `OUT` at all** in either copy. The token is
> reproduced as printed; the interface *names* are not recoverable.

### Table 15.8: iptables Log Fields _(Mod 15 p74)_

The printed table has a `Field` column and a `Description` column. The two columns are reproduced
side by side **without pairing** — the page prints 8 + 8 field names against 10 + 11 descriptions, so
the row alignment is not recoverable (see `unresolved`).

| Block | `Field` column, as printed | `Description` column, as printed |
|---|---|---|
| 1 | `Time` · `Machine Name` · `Action` · `IN` · `OUT` · `SRC-IP` · `DEST-IP` · `LEN` | "Displays the date of the log transaction" · "Displays the time of the log transaction" · "Name of the machine" · "Action performed by the firewall (Allow, Deny, Blocked, Etc.)" · "Incoming network interface" · "Outgoing interface" · "Source IP Address" · "Destination IP Address" · "Length of a packet" · "Type of Service field" |
| 2 | `Field` · `PREC` · `FRAG` · `PROTO` · `SPT` · `WINDOW` · `RES` · `SYN` · `URGP` | "TOS field's top 3 precedence bits" · "Time to live" · "Packet's datagram ID" · "Fragment flags field" · "Type of Protocol" · "Source port" · "Destination port" · "Size of the window" · "Reserved field in the TCP header" · "TCP state field" · "Urgent pointer" |

The field tokens actually present in the printed sample line above are `TOS`, `PREC`, `TTL`, `ID`,
`DF`, `PROTO`, `SPT`, `DPT`, `WINDOW`, `RES`, `SYN`, `URGP`.

## Enabling iptables logging _(Mod 15 p74)_

```bash
$ iptables -A INPUT -j LOG
```

- "In the above command, source IP or range can be defined in the following manner:"
  ```bash
  $ iptables -A INPUT -s 192.168.10.0/24 -j LOG
  ```
- "Similarly, the level of LOG can be defined to generate a specific level of logs:"
  ```bash
  $ iptables -A INPUT -s 192.168.10.0/24 -j LOG --10g-1eve1 4
  ```
  Printed as `--10g-1eve1 4` — see `unresolved`.
- "Prefixes can be added to search for specific logs in a large file:"
  ```bash
  $ iptables -A INPUT -s 192.168.10.0/24 -j LOG --log-prefix SUSPECT
  ```

## Monitoring and analysis of iptables logs _(Mod 15 p75)_

> "Linux firewall log helps monitor and analyze **incoming and outgoing network traffic**. It also
> enables determining the **number of hits from any IP address**."

Walkthrough steps _(p75)_:

1. "Use `tail` command for finding recent iptables logs"
2. "Execute the command to get the details of recent logs in iptables stored" — printed incomplete

Figure captions _(p75)_: "Recent 5 entries Of iptables logs" · "Output:" · "Timestamp Of the log
entry" · "Location Of the firewall logs" · "Action Performed" · "Source IP" · "Destination IP".

### Viewing iptables log _(Mod 15 p75)_

"To view the log, the following command are used (**varies with distribution**)."

| Distribution | Printed command |
|---|---|
| "On Ubuntu and Debian" | `$ tailf /var/log/kern.log` |
| "On CentOS/RHEL and Fedora" | `# tailf /var/log/messages` |

"For example, to get the details of recent log records in iptables, execute the following command:"

```bash
$ tail -5 /var/log/messages
```

"The above command displays **five most recent entries** of iptables log."






