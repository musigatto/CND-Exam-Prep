---
type: note
module: "10"
lo: "03"
tags: [concept, process, command, crypto, mod/10]
topic: "Data at Rest Encryption — Windows Device Encryption, BitLocker, TPM"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Data at Rest Encryption (§10.3)

## Overview
- Encrypt data stored on physical media → unreadable even if attacker steals the device
- **4 categories**:
  1. **Disk encryption** — encrypt part or whole disk/partition
  2. **File-level encryption** — encrypt individual files/folders
  3. **Removable media encryption** — USB drives, portable disks, cameras, smartphones, tablets
  4. **Database encryption** — specific subset or entire DB

### Disk encryption advantages
| Disk encryption | File-level encryption |
|---|---|
| Simple, clear, coherent design | Per-file key material |
| Hardware support → high performance | Access control via public-key cryptography |
| Encrypts decoy files too (less focus slowing legit work) | Increased protection for decoy files |

## Windows device encryption (built-in)
- **Caveat: NOT a full-security measure**; protects only where users have privileges to decrypt
- Prerequisites: **TPM** + **UEFI**; whole system + secondary drives encrypted
- Check: `msinfo32` → "Device Encryption Support" → "Meets prerequisites"
- Enable: Settings → Update & Security → Device encryption → Turn on
- Key: Auto unlock (via BitLocker) vs manual wake/passphrase

## TPM 2.0
- Hardware **protective countermeasures**: measured boot, cert, hmac key, PCR, sealed keys
- Required for Windows 11; store keys in hardware vs software
- Enable steps:
  1. Settings → Update & Security → Recovery → **Restart now**
  2. Troubleshoot → Advanced Options → **UEFI Firmware Settings**
  3. Enable TPM 2.0 in firmware
- Verify: `tpm.msc` → status "The TPM is ready for use"; spec version

## BitLocker
- Full Volume Encryption; **AES-CBC ~ AES-XTS**; **Support: 128-bit / 256-bit**
- Enable: Control Panel → System and Security → **Manage BitLocker** → Turn on BitLocker
- (TPM required; recovery key fallback)

## Cards
Q:: Name the 4 categories of data-at-rest encryption.
A:: Disk · file-level · removable media · database.
#flashcard
Q:: Which two prereqs does Windows device encryption require?
A:: TPM + UEFI.
#flashcard
Q:: How to check TPM status?
A:: `tpm.msc` → "The TPM is ready for use"; spec version shown.
#flashcard
Q:: BitLocker cipher support?
A:: AES-CBC and AES-XTS, 128-bit or 256-bit.
#flashcard