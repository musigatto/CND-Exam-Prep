---
type: note
module: "15"
lo: "05"
tags: [tool, command, concept, mod/15]
topic: "Check Point firewall logs"
exam_weight: unknown
status: done
unresolved:
  - "p85 the syntax line under 'Syntax:' prints as 'log ( —f [ —c action] ( —h host) starttime] ( —e endtimel [ —b starttime endtime] [ —u unification scheme file] unification mode (initial I semi I raw) J (alert name lall)) I—gl [logfile]' — scrambled and not the same as the p87 printing. Reproduced as printed; not reconstructed."
  - "p87 the syntax line prints as 'fw log [ —f [ e endtime] [ —b starttime endtime] unification mode (initial I semi I raw) ] [logfile] action] [ —h host] [ —s starttime] [ —u unification scheme file] [ —m [ —k (alert name I all) ]' — the bracket nesting is scrambled and the line ends on the command with no closing bracket. Reproduced as printed."
  - "p85 the parameter table prints 5 parameter names (-c action, -h host, -s starttime, -e endtirne, -b Starttime endtime) against 10 description entries; '-e endtirne' is printed with a letter r. The two lists are therefore given separately and are NOT paired."
  - "p86 the parameter table prints 4 parameter names (-u unification scheme file, -m unification mode, -k alert_name logfile, -m unification_mode) against 7 description entries. The two lists are given separately and are NOT paired. Only the initial/semi/raw unification-mode values are self-identifying and are tabulated."
  - "p86 the default log file path prints as 'SFWDIR/Iog/fw.Iog' (letter l in 'log'); kept as printed."
  - "p86 the sentence 'The log ins/log under can be found in the installation directory—$FwDIR' is damaged between 'The log' and '$FwDIR'; quoted as printed."
  - "p86 the real-time flag prints as 'fw log —ftn'; the em dash is rendered here as a hyphen (fw log -ftn)."
  - "p86 the 'Ew log Example' capture is heavily damaged ('dam.chechpoint.com', ':reeson:', 'denie#', 'Intarnal', 'Ga way', 'Cookiel'); not reproduced. The p87 prose examples carry the same records with far less damage and are used instead."
  - "pp84–88 print the fw log syntax twice (p85 and p87) and neither printing is clean; neither line is completed from the other."
---

[[MOC-Module-15]]

# Check Point Firewall Logs (§15.05)

> **LO#05: Discuss log monitoring and analysis on firewalls** _(Mod 15 p59)_
> Covers pp84–88.

Related: the four firewall log sources as a set —
[[15-LO05a-Firewall-Logging-and-Analysis-Steps]] · [[15-LO05b-Windows-Defender-Firewall-Logs]] ·
[[15-LO05c-Mac-OS-X-Firewall-Logs]] · [[15-LO05d-Linux-iptables-Logs]] ·
[[15-LO05e-Cisco-ASA-Firewall-Logs]].
Transport: [[15-LO08a-Why-Centralized-Logging]] · [[15-LO08d-Syslog-Mechanism-Collector-Relay-and-Tools]].

## What the Check Point firewall is _(Mod 15 p84)_

- "Check Point firewall examines **all communication layers' packets** and extracts the relevant
  communication and application state information."
- "Check Point firewall uses **stateful inspection** technology for packet analysis."
- "It is integrated with an **inspection module that lives in the OS kernel**."
- "Inspection modules operate **below the network layer**, inspecting all the traffic **before they
  reach the OS**."
- "This leads to high performance as it **saves OS's processing time and resources**."

In the body _(p84)_: stateful inspection means "incoming packets are inspected intelligently and the
packets that seem to be dangerous are **blocked**". The inspection module "operates below the network
layer, inspecting each packet and ensuring that it will not enter in a network until it **complies
with the network's security policy**".

| Check Point vs traditional firewalls _(p84)_ | |
|---|---|
| "Traditional firewalls analyze **only the message headers**" | Check Point "inspects the **complete raw message** and analyzes **all data from packet communication layers**" |

Decision path printed on p84:

1. "**Initially, it inspects the IP addresses, port numbers, and other information** to identify whether
   packets are according to the network security policy."
2. "**Then, it verifies whether the connection is coming from the appropriate source or not.**"
3. "For this, it has to **match the incoming packet against state and context information**, which is
   located in **dynamic static tables**. These are tables that store cumulative data through which
   Check Point firewall checks upcoming transmissions."
4. "If the incoming traffic does not match with the network standards and policy, then the firewall
   generates **real-time alerts to the network defenders**."

## Monitoring and analyzing Check Point firewall logs _(Mod 15 p85)_

> "**`fw log` command is used to display the log file content.**"

### Syntax _(Mod 15 p85)_, as printed

```text
log ( —f [ —c action] ( —h host) starttime] ( —e endtimel [ —b starttime endtime] [ —u unification scheme file] unification mode (initial I semi I raw) J (alert name lall)) I—gl [logfile]
```

### `fw log` parameters — p85

`Parameter` column, as printed: `-c action` · `-h host` · `-s starttime` · `-e endtirne` ·
`-b Starttime endtime`

`Description` column, as printed (10 entries against 5 printed names — not paired):

1. "Continue displaying the file until the log is being written."
2. "Specification of -t parameter displays only newly created records"
3. "Is used to **speed up the process by not performing IP addresses DNS resolution** in the log files"
4. "**Display both the date and the time** for each log record"
5. "Displays **detailed log chains** (all the log segments a log record consists of)"
6. "Retrieves **action events** (accept, drop, reject, authorize, deauthorize, encrypt, and decrypt) only"
7. "only display the logs of **specified host name/IP address**"
8. "Retrieves only events that were logged **after** the specified time"
9. "Show events that were logged **before** the specified time"
10. "Shows events that were logged **between the specified start and end times**"

### `fw log` parameters — p86

`Parameter` column, as printed: `-u unification scheme file` · `-m unification mode` ·
`-k alert_name logfile` · `-m unification_mode`

`Description` column, as printed (7 entries against 4 printed names — not paired):

1. "Unification scheme file name"
2. "This flag specifies the unification mode."
3. "Display **account** log records only"
4. "Display only events that match a **specific alert type**. The default is `all`, for any alert type"
5. "**Do not use a delimited style.** The default is: `:` after field name `;` after field value"
6. "Use **`logfile`** instead of the **default log file (`SFWDIR/Iog/fw.Iog`)**"
7. "Unification scheme file name" (the table text is repeated in the following prose)

### Unification mode values _(Mod 15 p86)_

Self-identifying, fully printed — safe to tabulate:

| Value | Printed description |
|---|---|
| `initial` | "**the default mode**, specifying **complete unification** of log records. To display updates, use the **`semi`** parameter" |
| `semi` | "**step-by-step unification**, that is, for each log record, output a record that unifies this record with **all previously encountered records with the same id**" |
| `raw` | "**output all records, with no unification**" |

### Where the records live and how you read them _(Mod 15 p86)_

- "Check Point firewall log records can be viewed via Check Point GUI by issuing the `fw log` command.
  The log **ins/log under** can be found in the installation directory—**`$FwDIR`**." — damaged, see `unresolved`.
- "Check Point firewall log records can also be viewed via **CLI**. For this, first connect to the
  Check Point firewall platform through **SSH or a console over a TCP/IP network** and then enter the
  credentials to log into the CLI."

## Traffic logs vs audit logs _(Mod 15 p86)_

> "Check Point firewall log contains **traffic log** and **audit log** entries."

| | Traffic logs _(p86)_ | Audit logs _(p86)_ |
|---|---|---|
| What | "the **most useful** log entries in the main log" · "traffic that is **allowed, dropped, or denied**" | "**all changes performed through the GUI**" |
| Each entry records | — | "the **user** who logged in, the **machine name** from where they came from, the **component** they used, the **authentication technique** they applied, and the **change** performed" |
| Alerts | "generates **accept** alerts when network traffic is allowed and **deny or drop** alerts when network traffic is not allowed. These alerts include a **rule** that helps in troubleshooting issues." | — |
| Use | "beneficial for detecting **port scans, host sweeps, and general probing**" | "useful for general **auditing** and analyzing a **compromised firewall host**" |

## The `fw log` command _(Mod 15 p86–p87)_

> "The `fw log` command is used to display the content of the Check Point log file. Logs can also be
> viewed **in real time** by using the **`fw log -ftn`** command. This command is used by various network
> defenders to **send Check Point logs securely over the network**."

Syntax _(p87)_, as printed (scrambled; see `unresolved`):

```text
fw log [ —f [ e endtime] [ —b starttime endtime] unification mode (initial I semi I raw) ] [logfile] action] [ —h host] [ —s starttime] [ —u unification scheme file] [ —m [ —k (alert name I all) ]
```

### Output line format

- p86: "Each line of `fw log` command's output represents a **single record**; each field of log appears
  in the following format:"
  ```text
  <interface dir and name> [alert] [field name: field value;]
  ```
- p87: the same sentence with time added —
  ```text
  < time> <interface dir and name> [alert] [field name: field value; ]
  ```

p86 figure labels the five parts: **Time** · **Action** · **Origin** · **Interface directory and name** ·
**Alert**.

### Fields _(Mod 15 p87)_

| Field | Printed description |
|---|---|
| `date` | "Date on which action is generated in the **`MMM DD, YYYY`** format; for example, **Feb 16, 2018**" |
| `time` | "Time at which action is generated in the **`HH:MM:SS`** format; for example, **15:22:00**" |
| `action` | "Action performed by the firewall such as **accept, drop, reject, authorize, deauthorize, encrypt, and decrypt**" |
| `origin` | "**Firewall that wrote the record**" |
| `interface dir` | "Firewall **interface directory**" |
| `interface name` | "Firewall **interface name**" |
| `alert` | "**Type of alert generated**" |
| `field name` | "Name of the other field name" |
| `field value` | "**Specified field value**" |

### Example records _(Mod 15 p87)_

```text
reject dam. checkpoint. com >daemon alert src : rule : O ; veredr . checkpoint . com; dst : dam. checkpoint.com; user : a; reason: Client Encryption: Access denied — wrong username or password; scheme: IKE; reject category: Authentication error; product: Security Ga teway 15:57:49

authcrypt dam.checkpoint.com >daemon src : veredr . checkpoint . com; user: a; rule: O; reason: Client Encryption : Authenticated by Internal Password; scheme : IKE; methods: AES- 256 , IKE , SHAI; product: Security Gateway ; 15 : 57 : 49

keyinst dam. checkpoint. com >daemon src: veredr . checkpoint . com; peer gateway : veredr . checkpoint . com ; scheme: IKE; IKE: Main Mode 32f09ca38aeaf4a3 ; CookieR: 73b91d59b378958c; completion. ; Cookiel : msgid: 47ad4a8d; methods: AES—256 + SHAI, Internal Password; user: a; product: Security Gateway ;
```

Reading of the example _(p87–p88)_:

| Part | Values the page names |
|---|---|
| time | `15:56:39`, `15:57:49` |
| action | `reject dam.checkpoint.com >daemon alert`, `authcrypt dam.checkpoint.com >daemon`, `keyinst dam.checkpoint.com >daemon` |
| origin | `src: veredr.checkpoint.com` (—3) |
| interface directory and name | `user: a`, `user: a`, `peer gateway: veredr.checkpoint.com` |
| alert | `reason: Client Encryption: Access denied—wrong username or password` |

## Check Point firewall-specific logging issues and challenges _(Mod 15 p88)_

- "Logs generated by Check Point firewall are **not in a readable format**."
- "**GUI log viewer does not provide real-time log analysis view.**"
- "For this, you have to look at **checkpoint devices**."
- "It is **not beneficial for batch analysis**."
- "It is **limited to filtering and sorting**."






