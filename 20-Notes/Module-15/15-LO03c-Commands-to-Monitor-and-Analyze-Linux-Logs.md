---
type: note
module: "15"
lo: "03"
tags: [command, mod/15]
topic: "cat, tail, head, less, more, grep for Linux log analysis"
exam_weight: unknown
status: done
unresolved:
  - "p44 summary box prints 'cat [filename)' with a closing parenthesis and ': head —n) [filename]' with a stray leading colon and an em dash; both reproduced as printed and NOT corrected."
  - "p44 summary box prints 'grep \"search_string\" (filename)' while the p46 prose prints 'grep \"search string\" [filename]\" — both kept as printed."
  - "p44 summary box prints the tail syntax as 'tail [n] [filename]' while the p45 prose prints 'tail [options] [filename (s) ]' — both kept."
  - "p44 the cat two-file variant prints the label 'cat [filename2]' and then the sentence 'This command will display the content of cat filename1 ] filename1 and filename2.' — the OCR has scrambled the label into the sentence; quoted as printed, label NOT reconstructed."
  - "p44 the cat copy-to-another-file variant prints only the label 'cat [filename1]' with no redirect operator captured; p45 prints the same label again for the append variant. Neither has been completed."
  - "p45 tail prints the label 'tail C -n] [filename]' and p45 head prints the n-lines variant simply as 'head [filename]'; both kept as printed, neither repaired."
  - "p46 grep option list prints '-1: It displays file names' list.' — reproduced as '-1' and NOT changed to '-l'."
  - "p44–46 the OCR renders the number 1 in 'filename1' as a lowercase l throughout ('filenamel'). Rendered here as 'filename1' throughout; no redirect operator or option letter was inferred from that."
---

[[MOC-Module-15]]

# Commands to Monitor and Analyze Linux Logs (§15.LO#03c)

> **LO#03: Discuss log monitoring and analysis on Linux systems** _(Mod 15 p36)_
> Covers pp44–46.

"Monitoring and analysis of Linux logs helps **determine security issues before they can significantly harm the system**." Various types of commands are provided by Linux to monitor and analyze log files.

## Summary box — commands used to monitor and analyze Linux log files _(Mod 15 p44)_

Reproduced from the printed summary box:

| Command | Printed behaviour | Printed syntax |
|---|---|---|
| `cat` | displays file contents | `cat [filename)` |
| `tail` | displays **last 10 lines** from a given text file by default | `tail [n] [filename]` |
| `head` | displays **first 10 lines** from a given text file by default | `: head —n) [filename]` |
| `less` | displays the contents of a text file **one page (one screen) per time** | `less [filename]` |
| `more` | displays the number of lines from a text file **as much as the screen can fit** | `more` |
| `grep` | used for **searching a specific string in a file** | `grep "search_string" (filename)` |

## `cat` command _(Mod 15 p44)_

- `cat` stands for **concatenate**; "one of the **most important** commands used in Linux OS"
- Reads data from the file and displays its content
- Can **combine** the contents of two files by appending the content of the second file to the end of the first file
- Can also **copy** the content of one file to another file
- Syntax: `cat [option] [filename]`

| Printed variant | Printed behaviour |
|---|---|
| `cat [filename]` | Displays the content of a given filename |
| `cat [filename2]` | "This command will display the content of cat filename1 ] filename1 and filename2." _(label scrambled by the OCR — see `unresolved:`)_ |
| `cat>newfilename` | Creates a **new file** with the name "newfilename." |
| `cat -n [filename]` | Displays the content of a given file **with line number** |
| `cat [filename1]` _(p44)_ | "This command **copies** the content of filename1 to filename2." _(no redirect operator printed)_ |
| `cat -s [filename]` | **Suppresses repeated empty lines** |
| `cat [filename1]` _(p45)_ | "This command **appends** the content of filename1 to the end of filename2." |
| `tac [filename]` | Displays the file **in reverse order** |
| `cat -E [filename]` | **Highlights the end of the line** |

## `tail` command _(Mod 15 p45)_

- Displays the **last 10 lines** from a given text file **by default**
- Allows options **n** = number of lines and **c** = number of characters
- Syntax: `tail [options] [filename (s) ]`

| Printed variant | Printed behaviour |
|---|---|
| `tail [filename]` | Displays the **last 10 lines** from a given file |
| `tail [filename1] [filename2]` | Displays the **last 10 lines of both** the files |
| `tail C -n] [filename]` _(as printed)_ | Displays the **last n number of lines** from a given file — e.g. if 5 is used in place of n, only the **last five lines** are displayed |
| `tail [ -c] [n] [filename]` | Displays the **last n number of characters** from a given file |

## `head` command _(Mod 15 p45)_

- Displays the **first 10 lines** from a given text file **by default**
- Allows options **n** = number of lines and **c** = number of characters
- Syntax: `head [options] [filename (s) ]`

| Printed variant | Printed behaviour |
|---|---|
| `head [filename]` | Displays the **first 10 lines** from a given file |
| `head [filename1] [filename2]` | Displays the **first 10 lines of both** the files |
| `head [filename]` _(label as printed)_ | Displays the **first n number of lines** from a given file — e.g. if 5 is used in place of n, only the **first five lines** are displayed |
| `head [ -c] [n] [filename]` | Displays the **first n number of characters** from a given file |

## `less` command _(Mod 15 p45)_

- Syntax: `less filename`
- Displays the contents of a text file, **one page (one screen) per time**
- On a large file it **does not access the complete file** — it accesses **page by page**
- Page example: any text editor reading a large file "will get loaded **completely to main memory**"; `less` **loads part by part, thus making it faster**

## `more` command _(Mod 15 p46)_

- Syntax: `more filename`
- Displays a number of lines from a text file — **as much as the screen can fit**
- Helps view files in a **scrollable manner** and **search the text, strings, and regular expressions**

## `grep` command _(Mod 15 p46)_

- Used for **searching a specific string in a file**
- Syntax: `grep "search string" [filename]`

| Option | Printed behaviour |
|---|---|
| `-c` | Displays a **count of number of lines** that match a pattern |
| `-h` | Displays the **matched lines but not the filenames** |
| `-i` | **Ignores the case** for matching |
| `-1` _(as printed)_ | Displays **file names' list** |
| `-n` | Displays the **line numbers as well as the matched line** |
| `-v` | Displays **all the lines without a matching pattern** |
| `-w` | **Matches the whole word** |

The files these commands are pointed at → [[15-LO03a-Linux-Logs-and-Log-Files]] · shell discipline around them → [[15-LO05d-Linux-iptables-Logs]] · [[MOC-Module-06]]





