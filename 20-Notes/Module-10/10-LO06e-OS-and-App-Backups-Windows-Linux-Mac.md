---

type: note
module: "10"
lo: "06"
tags: [process, tool, command, mod/10, flashcard/10]
topic: "OS and Application Backups — Windows, Linux, macOS"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# OS & Application Backups (§10.6.5)

## Windows — File History
- Built-in file backup (libraries, desktop, contacts, favorites)
- Settings → Update & Security → Backup → **Add a drive** → File History ON
- Frequency options: **every 10 minutes → daily**; retention slider (keep forever / custom)
- **Back up now** button; saved versions browsable by date

## Linux backup tools
- `tar` archives: `# tar -czvf backup.tar.gz /home`
- `rsync` incremental sync: `# rsync -av /source/ /backup/`
- `dd` raw block copy for whole disk images

## macOS — Time Machine
- System Preferences → **Time Machine** → Select Backup Disk → Time Machine ON / Back Up Automatically
- Schedule: **hourly** for past 24h → **daily** for past month → **weekly** for all history
- **Encrypt backups** toggle; exclude specific volumes from backups

## Application backups
- Backup app configs + databases consistently (see LO06f): coordinate app stops / VSS writers / dump+log shipping.

## Cards
File History frequency range?
?
Every 10 minutes up to daily (saved versions browsable by time).

Time Machine retention schedule?
?
Hourly (past 24 h), daily (past month), weekly (all remaining history); supports encrypted backups.

Two CLI tools for Linux file backup?
?
`tar` (archives) and `rsync` (incremental sync); `dd` for raw block images.
