---

type: note
module: "10"
lo: "02"
tags: [concept, process, protocol, command, mod/10]
topic: "Data Access Control — Models, ACLs (Windows/Linux), Restrictions"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Logical Access Control (§10.2.1)

## Access control models
- **RBAC** (role-based) — permissions tied to roles
- **Rule-based** (RB-RBAC) — rules combine roles
- **MAC** — mandatory, clearance-based
- **DAC** — owner sets discretionary access
- Models are **not mutually exclusive**; logically implemented via:
  - Access control lists (ACLs)
  - Group policies
  - Account restrictions
  - Passwords / access tokens

## Windows access control lists (ACL)
- Contains **access control entries (ACEs)**; each ACL = table of access rights for an object
- At logon OS builds **access token** (identity + user info); on access request OS compares token vs ACEs
- **6 ACE types**: 3 generic (access-denied ACE in **DACL** · access-allowed ACE in **DACL** · system-audit ACE in **system ACL**) + 3 object-specific (access-denied/access-allowed object-specific ACE in DACL · system-audit object-specific ACE in system ACL)
- Explicit permissions set directly on object; **inherited** flow from parent

### Share vs NTFS permissions
| Share | NTFS |
|---|---|
| Full control, Change, Read | **Files**: Full control, Modify, Read & execute, Read, Write · **Folders**: + List folder contents |
| Applies at share level; FAT also | FAT/FAT32 cannot set per-file permissions |

- Special permissions via Properties → Security → Advanced → Add/Edit

## Linux ACLs
- Install: `# yum install acl`
- Mount with ACL: `# mount -t ext3 -o acl [device] [mount]` (or `/etc/fstab` `acl` option)
- **Access ACL** (file/dir) vs **Default ACL** (dirs only, applied to new objects)
- Manage: `getfacl` (view) · `setfacl -m u:user:perms FILE` (add) · `setfacl -x u:user FILE` (remove) · `setfacl -b` (remove all)
- Default dir ACL: `# setfacl -m d:o:rx /Testdir`
- `getfacl` output sample: `user::rw-` · `user:alice:r-` · `group::r-` · `mask::r-` · `other:r--`

## Group policies
- Fine-grained control: security settings, least privilege, account lockout polices

## Account restrictions
- **Logon hours** + **account expiration** (Windows: AD Users & Computers → Properties → Account tab → uncheck "Never expire"; Logon hours)
- **Linux**: `pam_time` module; config `/etc/security/time.conf`, e.g. `Login;*;!Martin;MoTuWeThFr0800-2000` (all services, all tty, user Martin barred except weekdays 08:00–20:00)

## Passwords / tokens
- Logical control examples: passwords + access tokens
- Third-party folder tools: **Folder Guard**, **Folder Lock**, **Protected Folder**








> Matched word-for-word to the module PDF. See [[External-Flashcards-Verification]].





