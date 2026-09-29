---
type: note
module: "10"
lo: "03"
tags: [process, command, tool, crypto, mod/10]
topic: "File-level Encryption (EFS, third-party) & Removable Media Encryption"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# File-Level Encryption (§10.3.5)

## Windows EFS (Encrypting File System)
- File-level encryption; **not available in all Windows editions** (Home lacks it)
- Enables / disables per file/folder with **user's public key**; transparent access logged-on
- Commands: `cipher /e <file>` (encrypt) · `cipher /w:dir` (dispose of deleted data/clean free space)
- GUI: right-click → Properties → **Advanced → "Encrypt contents to secure data"**
- Encryption Warning: encrypt the file only vs file + parent folder

## macOS
- **Disk utility disk image** → File → New Image → Disk Image from Folder
- Choose disk image format (read/write, DVD/CD master) + **encryption** (AES-128)
- .NET: create with `hdiutil` equivalents

## Third-party file encryption (Windows)
| Tool | Notes |
|---|---|
| **AxCrypt** | AES-256, free/paid |
| **idoo** | file/email encryption |
| **AES Crypt** | free, AES-256 |
| **Cryptomator** | client-side encryption for cloud |
| **Encrypto** | MacPaw, AES-256 drag-drop |
| **Boxcryptor** | cloud file encryption |

## Removable media encryption (Windows/mac/Linux + 3rd party)
- Windows: BitLocker To Go for USB drives
- macOS: encrypt drive via Disk Utility / FileVault-compatible external
- Linux: dm-crypt/LUKS partitions / Cryptmount
- 3rd-party: **VeraCrypt**, **ShareCrypt**, **AlertSec**, **Symantec Drive Encryption** (multiplatform), **Windows Enterprise**

## Cards
Q:: Command to encrypt a file / wipe free space with EFS?
A:: `cipher /e <file>`; `cipher /w:dir` wipes deleted-data area (free-space cleaning).
#flashcard
Q:: Which Windows editions lack EFS?
A:: Windows Home (and similar low-tier editions).
#flashcard
Q:: Two ways Windows guards USB removable media?
A:: BitLocker To Go (TPM-less password/PIN) + third-party USB encryption.
#flashcard
Q:: macOS encrypted disk image: default cipher?
A:: AES-128 (Disk Utility New Image from Folder).
#flashcard