---
type: note
module: "15"
lo: "02"
tags: [concept, tool, mod/15]
topic: "Windows event log file format — ELF LOGFILE HEADER, EVENTLOGRECORD, wrapping"
exam_weight: unknown
status: done
unresolved:
  - "p16 the sentence 'These Windows event log files are stored in c : folder' is truncated in the source — the full folder path is not legible in the body text and has not been completed."
  - "p17/p18/p19 the structure name is printed both as 'ELF LOGFILE HEADER' and as 'ELF _ LOGFILE _ HEADER'; the underscores are OCR spacing and have been rendered as spaces."
  - "p18-p20 the code lines are printed with OCR breaks inside member names ('Maj orVers ion', 'Re ten tion', 'T imeGenera ted', 'User SidLength', 'ClosingRecordNu1nber', 's eruct', 'typede f'). Below they are given with the unspaced spellings printed in Tables 15.1 and 15.3."
  - "p19/p20 the Table 15.1 description column ends mid-sentence on 'Retention' ('The retention value of the file when it is created and'); no description is printed for EndHeaderSize, and the sentence about the signature is repeated under it."
  - "p19 HeaderSize is printed as '0 x 30' and the Signature as '0x654c664c'; p20 and p21 print the signature as 'Ox654c664c' and the ReservedFlags values as 'O x 0000' / 'O x 8000'. All printed forms are kept as-is."
  - "p18 the wrapping-method figure prints record numbers 102, 103, 299, 300, 301, 400 and eight (EVENTLOGRECORD) boxes; the spatial arrangement of the boxes is not recoverable from the OCR and has not been redrawn."
  - "p20-p21 the EVENTLOGRECORD declaration prints 10 DWORD, 4 WORD, 4 DWORD then 2 DWORD (20 types) against only 16 named members — the printed type list and the member list do not line up; both are reproduced verbatim."
  - "p20/p21 the member name is printed as 'EventlD' and 'ReservedF1ags' in both the code line and the table; the digit/l ambiguity is unresolved and the printed form is kept."
---

[[MOC-Module-15]]

# Windows Event Log File Format (§15.LO#02b)

> **LO#02: Discuss log monitoring and analysis on Windows systems** _(Mod 15 p14)_
> Covers pp16–22.

## Event log files as databases _(Mod 15 p16)_

> "In simple terms, Windows event log files are **databases** with records related to the **system, security, and applications**."

| Category | File |
|---|---|
| System database | `System.evtx` |
| Security database | `Security.evtx` |
| Application database | `Application.evtx` |

- These files are stored in a `c:` folder — **the rest of the path is not legible in the page text**
- **`.evtx` files can be opened and read with Event Viewer**

## Anatomy of an event log file _(Mod 15 p17)_

Each event log consists of:

1. a **header of fixed size** — the **ELF LOGFILE HEADER** structure
2. a **variable number of event records** — **EVENTLOGRECORD** structures
3. an **end-of-file record** — the **ELF EOF RECORD** structure

- When the event log is **created and updated**, **both** the ELF LOGFILE HEADER structure **and** the ELF EOF RECORD structure are written to it
- When an application calls the **`ReportEvent`** function, the system passes the parameters to the **event-logging service**, which uses them to write an **EVENTLOGRECORD** structure to the log file

```
Application  --ReportEvent-->  Event-Logging Service  -->  Event Log File
                                            writes:  EVENTLOGRECORD
                                                     EVENTLOGRECORD
                                                     ELF EOF RECORD
```

## The two ways of arranging event records

### 1. Nonwrapping method _(Mod 15 p17)_

> "The **oldest record is inserted just after the event log header** and **new records are inserted just before the ELF EOF RECORD**."

```
HEADER | EVENT RECORD 1 | EVENT RECORD 2 | EOF RECORD
         (ELF LOGFILE HEADER) (EVENTLOGRECORD) (EVENTLOGRECORD) (ELF EOF RECORD)
```

- Applied **every time an event log is generated or deleted**
- Records keep this arrangement **until its size reaches the maximum limit**
- Log size depends on either the **`MaxSize` configuration value** or **the number of system resources**
- **After the size reaches its limit → the wrapping method**

### 2. Wrapping method _(Mod 15 p18)_

> "Event logs are arranged in the form of a **circular buffer**, in which the **oldest event logs are replaced by the new event log**."

Printed contents of the p18 figure (arrangement not recoverable from the source text):

```
HEADER · Part of EVENT RECORD 300 · EVENT RECORD · EVENT RECORD · EOF RECORD
Wasted space · EVENT RECORD · EVENT RECORD · EVENT RECORD
301   400   102   103   299
Part of EVENT RECORD 300
labels: (ELF LOGFILE HEADER) (EVENTLOGRECORD) (ELF EOF RECORD)
```

Rules as printed:

- **Record 102 is the oldest record instead of 1** — "the oldest event records from **1 to 101** have been replaced with the newest ones"
- **Size of an event log file is fixed**
- Free-space arithmetic: if the newest record is **100 bytes** and the **two oldest records are 65 bytes each**, the system erases **both**; the **remaining 30 bytes** are used later when new event logs occur
- **A record at the end of the file is divided into two**: record size **200 bytes**, space before the end of the file **100 bytes** → **first 100 bytes** recorded at the end of the file, **the other 100 bytes** recorded **just after the ELF LOGFILE HEADER**
- If the space at the end of the file is **less than the fixed size of `EVENTLOGRECORD`**, **all new event log records are recorded just after the ELF LOGFILE HEADER** and the **unutilized space at the end of the file will be occupied by the pattern**

## ELF LOGFILE HEADER structure _(Mod 15 pp18–19)_

> "The event-logging service adds the ELF LOGFILE HEADER at the **start of the event log**, which **describes information about the event log**."

```c
typedef struct EVENTLOGHEADER {
ULONG HeaderSize;
ULONG Signature;
ULONG MajorVersion;
ULONG MinorVersion;
ULONG StartOffset;
ULONG EndOffset;
ULONG CurrentRecordNumber;
ULONG OldestRecordNumber;
ULONG MaxSize;
ULONG Flags;
ULONG Retention;
ULONG EndHeaderSize;
} EVENTLOGHEADER, *PEVENTLOGHEADER;
```

### Table 15.1 — members _(Mod 15 pp19–20)_

| Member | Description as printed |
|---|---|
| **HeaderSize** | The size of the header structure, which is always `0 x 30` |
| **Signature** | The signature is always `0x654c664c` (p19) / `Ox654c664c` (p20), which is **ASCII for `eLfL`** |
| **MajorVersion** | The major version number of the event log and is **always set to 1** |
| **MinorVersion** | The minor version number of the event log and is **always set to 1** |
| **StartOffset** | The offset to the **oldest record** in the event log |
| **EndOffset** | The offset to the **ELF EOF RECORD** in the event log |
| **CurrentRecordNumber** | The number of the **next record that will be added** to the event log |
| **OldestRecordNumber** | The number of the **oldest record** in the event log. Its value is **set to 0 for an empty file** |
| **MaxSize** | The **maximum size, in bytes**, of the event log. It is **defined when the event log is created** |
| **Flags** | The **status of the event log** — one of the four values in Table 15.2 |
| **Retention** | "The retention value of the file when it is created and" — **sentence breaks at the page edge** |
| **EndHeaderSize** | **No description printed** — the p19 description column ends mid-sentence on `Retention`, and the text repeating the signature description sits under `EndHeaderSize` on p20 |

### Table 15.2 — values of `Flags` _(Mod 15 p20)_

Printed as concatenated name + hex (the source prints no underscore between them).

| Value | Meaning |
|---|---|
| `ELF LOGFILE HEADER DIRTY` `Ox0001` | Indicates that **records have been written to an event log, but the event log file has not been properly closed** |
| `ELF LOGFILE HEADER WRAP` `Ox0002` | Indicates that **records in the event log are wrapped** |
| `ELF LOGFILE LOGFULL WRITTEN` `Ox0004` | Indicates that **the most recent write attempt failed due to insufficient space** |
| `ELF LOGFILE ARCHIVE SET` `Ox0008` | Indicates that **the archive attribute has been set for the file**. Normal file APIs can also be used to determine the value of this flag |

## EVENTLOGRECORD structure _(Mod 15 pp20–22)_

> "The EVENTLOGRECORD structure contains information on a **single event**."

```c
typedef struct EVENTLOGRECORD {
DWORD Length;
DWORD Reserved;
DWORD RecordNumber;
DWORD TimeGenerated;
DWORD TimeWritten;
DWORD EventlD;
WORD  EventType;
WORD  NumStrings;
WORD  EventCategory;
WORD  ReservedFlags;
DWORD ClosingRecordNumber;
DWORD StringOffset;
DWORD UserSidLength;
DWORD UserSidOffset;
DWORD DataLength;
DWORD DataOffset;
} EVENTLOGRECORD, *PEVENTLOGRECORD;
```

The printed declaration also runs a flat type line before the member names:

```
DWORD DWORD DWORD DWORD DWORD DWORD DWORD WORD WORD WORD WORD DWORD DWORD DWORD DWORD
```
…followed on p21 by `DWORD DataLength; DWORD DataOffset;`.

### Table 15.3 — members _(Mod 15 pp21–22)_

| Component | Size | Description as printed |
|---|---|---|
| **Length** | 4 bytes | Size in bytes of the structure |
| **Reserved** | 4 bytes | Serves as a **signature** for the structure |
| **RecordNumber** | 4 bytes | It is **mapped directly from the record ID** |
| **TimeGenerated** | 4 bytes | Time when the event was **generated** |
| **TimeWritten** | 4 bytes | Time when the event was **written** |
| **EventlD** | 4 bytes | **EventlD** generated by the event source |
| **EventType** | 2 bytes | Type of event |
| **NumStrings** | 2 bytes | Number of strings in the `Strings` field. **Value must be between 1 and 256** |
| **EventCategory** | 2 bytes | Event category |
| **ReservedFlags** | 2 bytes | Specifies whether or not the **last string in the `Strings` field contains well-formed XML**. `O x 0000` = the event does **not** contain XML; `O x 8000` = the event **does** contain XML |
| **ClosingRecordNumber** | 4 bytes | **MUST be set to zero when sent** and **MUST be ignored on receipt** |
| **StringOffset** | 4 bytes | **MUST be the offset in bytes from the beginning of the structure to the `Strings` field.** If `Strings` is not present (`NumStrings` is zero), this can be set to any arbitrary value when sent and MUST be ignored on receipt by the client |
| **UserSidLength** | 4 bytes | Size in bytes of the user's **security identifier**, located within the `UserSid` field. If there is no `UserSid` field for this event, this field **MUST be set to zero** |
| **UserSidOffset** | 4 bytes | **MUST be the offset in bytes from the beginning of the structure to the `UserSid` field.** If `UserSid` is not present (i.e. `UserSidLength` is zero), this can be set to any arbitrary value when sent and MUST be ignored on receipt by the client |
| **DataLength** | 4 bytes | **MUST be the size in bytes of the `Data` field.** If the `Data` field is not used, this field **MUST be set to zero** |
| **DataOffset** | 4 bytes | **MUST be the offset in bytes from the beginning of the structure to the `Data` field.** If `Data` is not present (i.e. `DataLength` is zero), this can be set to any arbitrary value when sent and MUST be ignored on receipt |

**High-value pattern:** every member is **4 bytes** except the four WORD-sized ones — **`EventType`, `NumStrings`, `EventCategory`, `ReservedFlags`** — at **2 bytes**.

## Where to go next

- The abstract view of these logs → [[15-LO02a-Windows-Logs-and-Event-Viewer]]
- The log types and the fields a log entry displays → [[15-LO02c-Windows-Event-Log-Types-and-Entries]]
- What the logs are monitored for → [[15-LO02d-Monitoring-and-Analyzing-Windows-Logs]]
- Normalization/parsing of log content → [[15-LO08e-Log-Storage-and-Log-Normalization]]






