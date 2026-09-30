---
type: note
module: "12"
lo: "06"
tags: [bestpractice, command, mod/12, flashcard/12]
topic: "GCP service account key rotation"
exam_weight: unknown
status: done
unresolved:
  - "pp262-263 SCOPE CONTRADICTION: the section title, the preceding rule and every best-practice bullet say SERVICE ACCOUNT keys, but both rotation methods are demonstrated with `gcloud kms keys ...` commands, i.e. Cloud KMS key versions. The courseware never reconciles the two; both are reproduced as printed and no KMS behaviour is asserted as service account key behaviour."
  - "p262 CONTRADICTION: GCP-managed keys are said to 'cannot be downloaded or automatically rotated', yet p263 presents an 'Automatic key rotation' method on the same two pages. No automatic rotation is stated for service account keys themselves - only for the KMS key the gcloud commands address."
  - "CROSS-PAGE CONTRADICTION: p251 gives the rotation order as four steps (create new key, switch apps to the new key, DISABLE the old key, delete the old key); the p262 figure compresses it to three ('creating a new key to switch applications to use the new key and delete the old key', no disable step). Both readings are kept."
  - "p262/p263: every flag in both gcloud commands OCR's as a replacement-character run, and the argument separators (`--`, `=`) are unrecoverable. Only the subcommand and the argument names are readable, so the commands are reproduced with `<flag>` placeholders and must NOT be treated as copy-pasteable CLI invocations."
  - "p262: the figure writes the API method as 'serviceAccount.keys.deIete()' (OCR of the lowercase l). It is read as serviceAccount.keys.delete() on the strength of the paired serviceAccount.keys.create() and the surrounding verb 'automate rotation'; the raw OCR form is recorded here in case that reading is wrong."
  - "p262/p263: NO count of key versions is printed. The only quantities given anywhere in this range are the two key TYPES, the GCP-managed lifetime ('within two weeks'), the user-managed expiry ('after ten years'), and the list of three roles permitted to rotate."
---

[[MOC-Module-12]]

# GCP Service Account Key Rotation (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)** _(Mod 12 p245)_
> Covers pp. 262–263: rotate service account keys. Source list:
> [[12-LO06b-GCP-Service-Accounts]] (best practice 5, "Rotate service account keys").

## The two key types _(Mod 12 p262)_

"Service account keys are categorized into **two types**".

| Type | Printed as |
|---|---|
| **GCP-managed keys** | "These keys **cannot be downloaded or automatically rotated**, and should be used **within two weeks**. GCP-managed keys are utilized by GCP services such as **App Engine and Compute Engine**." |
| **User-managed keys** | "Users can **create, download, and manage** the keys. The keys **expire after ten years**." |

## Why rotate — the stated rules _(Mod 12 p262)_

- "The service account keys should be **rotated (generate a new key version of the key and mark
  that version as the primary version) periodically**."
- **Prerequisite** — "For key rotation, the user should have the cloud IAM role
  (**`roles/cloudkms.admin`, `roles/owner`, or `roles/editor`**)."
- **Automate it** — "Use the **cloud IAM service account API**"; "**Use
  `serviceAccount.keys.create()` and `serviceAccount.keys.delete()` to automate rotation**."
- Also printed in the same figure: "Implement processes to manage **user-managed** service
  account keys" · "**Do not delete service accounts that are in use by running instances**" ·
  "**Use the display name** of a service account" · "**Do not check in** the service account
  keys into the source code."

_(Mod 12 p262)_

## Automatic vs manual key rotation _(Mod 12 pp262–263)_

| | **Automatic key rotation** _(p262)_ | **Manual key rotation** _(p263)_ |
|---|---|---|
| **Definition** | "set a **rotation schedule** that determines when the key should be automatically rotated" | "**generate a new key version, disable automatic rotation, and set the new key version as the primary key version**" |
| **How** | "set the rotation schedule through the **`gcloud` tool**" | "This can be accomplished by the **`gcloud` tool**" |
| **Command** | `gcloud kms keys update` | `gcloud kms keys versions create` |

**Automatic — command as printed** _(p262)_, flags unreadable:

```
gcloud kms keys update key<name> \ <flag>location location \ <flag> <flag>keyring keyring<name> \
    <flag><flag>rotation<period> rotation<period> \ next<flag>rotation<flag>time
```

Readable tokens: `gcloud kms keys update` · a **key** name · a **location** · a **keyring**
name · a **rotation period** · a **next rotation time**.

**Manual — command as printed** _(p263)_, flags unreadable:

```
gcloud kms keys versions create \ <flag> location location \ <flag>keyring keyring<name> \
    <flag> key key<name> \ <flag>primary
```

Readable tokens: `gcloud kms keys versions create` · a **location** · a **keyring** name · a
**key** name · **primary** — i.e. the newly created key version is made primary.

## What happens to the old key versions _(Mod 12 p263)_

- "After key rotation, the **previous versions of the keys are neither disabled nor
  destroyed**. This feature **prevents data loss**."
- "if the user rotates the key, the **data encrypted with the old key version would not be
  automatically decrypted and re-encrypted with the new key version**."
- "Hence, for re-encrypting the data, the user should **decrypt and re-encrypt with the new key
  version**."
- "Then, the user can **schedule the old key version to be destroyed if it is not protecting
  any data**."

_(Mod 12 p263)_

## Cards

The two categories of GCP service account key
?
GCP-managed — cannot be downloaded or automatically rotated, used within two weeks, utilized by GCP services such as App Engine and Compute Engine; User-managed — the user creates, downloads and manages them, and they expire after ten years

The courseware's definition of key rotation
?
Generate a new key version of the key and mark that version as the primary version — done periodically; the user needs roles/cloudkms.admin, roles/owner or roles/editor

Automatic vs manual key rotation
?
Automatic — set a rotation schedule that determines when the key is rotated (gcloud kms keys update) · Manual — generate a new key version, disable automatic rotation, and set the new version as primary (gcloud kms keys versions create … primary)

What happens to previous key versions after rotation
?
They are neither disabled nor destroyed — this prevents data loss, so data encrypted under the old version is NOT automatically re-encrypted; the user must decrypt and re-encrypt with the new version, and may schedule the old version for destruction only once it protects no data

Which service account API methods automate rotation
?
serviceAccount.keys.create() and serviceAccount.keys.delete()
