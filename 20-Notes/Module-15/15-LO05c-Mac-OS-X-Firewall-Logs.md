---
type: note
module: "15"
lo: "05"
tags: [concept, port, command, process, mod/15]
topic: "Mac OS X firewall log: appfirewall.log and the ipfw field list"
exam_weight: unknown
status: done
unresolved:
  - "Two default locations are printed and they disagree: p69's callout gives '/private/var/log/' and p71's Console procedure searches for '/var/log'. Both recorded, neither corrected."
  - "p72 prints the second header row of the log format with OCR damage as '>ETHOD'. METHOD is used, because Table 15.7 on the same page prints 'METHOD' cleanly."
  - "p72 and p69 print the RESULT description as '0K denotes access granted' with a digit zero (the denied value is printed 'ERR!'). Quoted as printed; not converted to OK."
  - "p69 prints the METHOD description with the protocol list as '(TO, UDP, or ICMP)' while p72's Table 15.7 prints '(TCP, UDP, or ICMP)'. The p72 printing is used."
  - "p72 Table 15.7's descriptions contradict its own field names: HOSTNAME is described as 'Client IP address trying to get access of a given port' and SERVER as 'Port to which access is attempted by the user'. Reproduced verbatim, not reconciled with the field names."
  - "Table 15.7 prints 16 field names (MONTH, DAY, TIME, HOST, IPFW CODE, ACTION, PROTOCOL, SOURCE, DEST, IN OUT, RESULT, HOSTNAME, SERVER, PORT, METHOD, DIRECTION) against only 15 descriptions, on both p69 and p72. The rendering here gives 'Port to which access is attempted by the user' to the SERVER + PORT pair; the page does not say which of the three it belongs to."
  - "p72 prints the format header as two rows with the sample value '02 08:43:31' set between them. The page gives no alignment, so the rows are reproduced unaligned and the sample value is quoted separately."
  - "p72's remaining sample lines are a column interleave in the source (four Deny lines and one Accept line). Tokens are reproduced in the page's reading order and were NOT reassembled into whole log lines."
  - "p72 prints the interface as 'via en1' while p71's figure prints 'via enl' (OCR l/1). Both kept as printed."
  - "p71 Figure 15.26 (appfirewall.log in Console) and the 'Firewall log format' figure are GUI captures - treated as NON-EVIDENCE. Nothing was read from them, including the figure's column headers Timestamp, Name Of Mac, Users, IP address, Destination IP address, Port Number and Firewall Events."
---

[[MOC-Module-15]]

# Mac OS X Firewall Logs (§15.LO#05c)

> **LO#05: Discuss log monitoring and analysis in firewalls** _(Mod 15 p59)_
> Covers pp69–72.

Continuation of the Mac log inventory → [[15-LO04b-Mac-Types-of-Logs-and-Log-Files]] · Mac Unix format and Console → [[15-LO04c-Mac-Log-Format-and-System-Logs]] · [[15-LO04a-Mac-Logs-and-Console]] · concept background → [[15-LO05a-Firewall-Logging-and-Analysis-Steps]]

## What the Mac firewall log is _(Mod 15 p69)_

- "Mac OS X has a **built-in firewall** that helps in monitoring and analysis of the various logs associated with the **system firewall**."
- "Mac OS X firewall logs display the **applications and services that attempted to make a connection to the Mac system**."
- "**Mac OS X firewall is able to record firewall logs only if it is enabled.**"

> **Note _(p69):** "**Firewall logging should be enabled** to record firewall logs."

## Default location and filename _(Mod 15 p69)_

| | As printed |
|---|---|
| Location | **`/private/var/log/`** _(p69 callout)_ · the Console procedure on p71 searches **`/var/log`** |
| File | **`appfirewall.log`** — "open the **recent / most recent** log file" |

## Enabling the Mac OS X firewall log — the printed walkthrough _(Mod 15 pp69–70)_

1. p69 — "Select the **"System Preferences"** option from the **Apple menu**." A new screen will appear.
2. p70 — "Click the **"Security & Privacy"** option located under the **"Personal"** section."
3. p70 — "In the dialog box, click the **"Firewall"** tab and then **click the lock icon** and provide the **administrator username and password**."
4. p70 — "Click the **"Turn On Firewall"** button to turn the firewall on. When the firewall turns on, it **displays a green light** and the **"Firewall: On"** message."
5. p70 — "Click the **"Advanced..."** option located at the **right bottom side** of the "Security & Privacy" dialog box."
6. p70 — "Navigate down and check the **two available options**, **"Automatically allow signed software to receive incoming connections"** and **"Enable stealth mode."**"
7. p70 — "Click **OK** to close the "Advanced" settings dialog box."

_(p69 Figures 15.23 and p70 Figures 15.24–15.25 are GUI captures — NON-EVIDENCE. No preference-pane item, checkbox, radio button or status light was read from them; only the menu items the running prose names are listed above.)_

## Viewing the log — the printed procedure _(Mod 15 p71)_

> "The following are the steps to view Mac OS X firewall logs:"

1. "**Enable the Mac firewall**, if it is not enabled."
2. "Open **Console** application through **`Applications -> Utilities`**."
3. "A new screen will appear."
4. "Search for **`/var/log`** directory in the **sidebar** and click the **disclosure triangle** next to that directory."
5. "Click **`appfirewall.log`** from the sidebar to view the firewall log."
6. "The firewall log will appear into the **right console panel**."

_(p71 Figure 15.26 is a Console screenshot — NON-EVIDENCE.)_

## Log format _(Mod 15 p72)_

> "The Mac OS X firewall logs will appear in the following format:"

```
MONTH   DAY   TIME   HOST   IPFW CODE   ACTION   PROTOCOL   SOURCE   DEST   IN   OUT   RESULT
  HOSTNAME   SERVER   PORT   METHOD   DIRECTION
```

The page also prints the sample value **`02 08:43:31`**; its column position is not given.

## Sample entries _(Mod 15 p72)_

Two lines the page prints complete:

```
Apr 02 08:14:20 mainserver servermgrd[58]: config: Notice: Flushed IPv6 rules
Apr 02 08:14:19 mainserver servermgrd[58]: config: Notice: Enabled firewall
```

The rest of the p72 example is a **column interleave** in the source (four `Deny` lines and one `Accept` line). Tokens in the page's reading order, **not** reassembled:

```
servermgr ipfilter: ipfw            servermgr ipfilter: ipfw
Oct Apr Apr Apr 17 10.0.1.201: 02 10.0.1.201: 17 10.0.1.201: 08:14:24 548 in 08:14:59 548 in 548 in
mainserver via enl mainserver via enl mainserver via enl mainserver in via enl
ipfw[1940] : 1040 ipfw[1940] . •1040 ipfw[1940] . •1040 ipfw[1940] .
Deny Deny Deny TCP TCP TCP 10.2.10.3:49232 10.2.10.3:49232 10.2.10.3:49232
•100 Accept TCP 10.2.0.1 : 721 192.168.10.11:515
```

**Tokens the example prints:**

| Kind | Tokens |
|---|---|
| Host | `mainserver` |
| Process | `servermgrd[58]`, `ipfw[1940]`, `servermgr ipfilter: ipfw` |
| Actions | **`Deny`**, **`Accept`** |
| Protocol | `TCP` |
| Direction / interface | `in`, `via en1` (p72) · `via enl` (p71) |
| Addresses and ports | `10.2.10.3:49232`, `10.0.1.201:1040`, `10.2.0.1:721`, `192.168.10.11:515`, `548 in` |
| Config notices | `config: Notice: Flushed IPv6 rules`, `config: Notice: Enabled firewall` |

## Table 15.7 — types of fields in a Mac OS X firewall log _(Mod 15 p72)_

| Field | Description |
|---|---|
| **MONTH** | Month of the access attempt |
| **DAY** | Day on which access attempt made |
| **TIME** | Access attempt time |
| **HOST** | Hostname |
| **IPFW CODE** | Firewall IPFW code |
| **ACTION** | Firewall response to an activity (**"accept"** or **"deny"**) |
| **PROTOCOL** | Protocol used in the access attempt |
| **SOURCE** | Source IP address from where access attempt made |
| **DEST** | Destination IP address to which access attempt made |
| **IN OUT** | Access direction (coming to the firewall machine, or going out) |
| **RESULT** | `0K` denotes access granted, `ERR!` denotes a denied access |
| **HOSTNAME** | Client IP address trying to get access of a given port |
| **SERVER** · **PORT** | Port to which access is attempted by the user |
| **METHOD** | Protocol used by the access attempt (**TCP**, UDP, or ICMP) |
| **DIRECTION** | Access direction (incoming or outgoing network traffic) |

**Contrasts to hold on to**

- `ACTION` takes the words **`accept` / `deny`**; the sample lines print them capitalised as **`Accept` / `Deny`**.
- `RESULT` takes **`0K`** (granted) vs **`ERR!`** (denied).
- `IN OUT` and `DIRECTION` are **both** "access direction" — the table gives no rule for which applies to which line.
- `PROTOCOL` and `METHOD` are **both** the protocol in the table's descriptions.







