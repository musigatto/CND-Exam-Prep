---
type: note
module: "12"
lo: "06"
tags: [crypto, process, mod/12]
topic: "GCP encryption layers and Cloud KMS / envelope encryption"
exam_weight: unknown
status: done
unresolved:
  - "p275: the four encryption layers print only as the bare words 'Application / Platform / Infrastructure / Hardware' under 'Google's default encryption of data at rest'. No product names are attached to each layer, so none are asserted here."
  - "p275/p276: the figure 'GCP Data Encryption Options for Customers' and the body list on p276 are NOT the same taxonomy. The figure uses Server-side Encryption / [customer-managed via] GCP KMS / Client-side Encryption; the body uses Server-side encryption / Customer-supplied encryption keys / Customer-managed encryption keys / Client-side encryption. Both sets are transcribed and kept separate."
  - "p277: the 'gcloud services enable' command OCR's as 'gcioud services enable cloudkms . googleapis . com'. Restored to gcloud services enable cloudkms.googleapis.com - the same command is printed cleanly on p279, which confirms the reading."
  - "p277: 'Distributed file system: data chunks in storage systems protected by AES256 encryption with integrity' - 'with integrity' is the printed phrase; the mechanism behind it is not described, so none is added."
  - "p277 Fig 12.193: the caption prints the typos 'Cloud KMS exterds custornet control over encryption keys' (extends customer); reproduced as printed."
  - "p280/p281 CONTRADICTION in the example key names: p280 body and its figure say the encryption key is \"demolab\" / \"dem01ab\", while the p281 command creates a key called \"democode\". The key ring is \"testkey\" in both the figure and the p281 command. All three spellings are kept as printed."
  - "p280 CONTRADICTION in the gcloud commands: the p280 figure shows the key-ring create using the shell variable '$KEYRING NABE' (OCR of $KEYRING_NAME) while the p280 body prints the same command with the literal key name 'demo' and a garbled flag. Both renderings are shown; the body form is not reconstructed."
  - "p280/p281: the gcloud flags OCR with a doubled dash ('——location global', '——10cation global', '——purpose encryption', '——keyring testkey'). The token 'location' is legible as 'location' in the p280 figure but OCR's as '10cation' in the p280 body and the p281 body, so '--location' is given once with that caveat rather than three different flags. The key-ring name value inside the p280 body command is unreadable."
  - "p280/p281 CONTRADICTION in the Web UI name: p280 says 'View the created resources in Encryption Keys Web UI under IAM & Admin' and p281 says 'View the created resources in Cryptographic Keys Web UI under IAM & Admin'. Both are printed; neither is treated as the correct menu name."
  - "p280: the key-ring level text says a key ring 'is a collection of keys that are grouped for an organizational purpose' and that 'The key ring resource ID, a fully qualified key ring name is used by some API calls and gcloud command-line tool.' The sentence is printed with that run-on; reproduced as printed."
---

[[MOC-Module-12]]

# GCP Encryption and Cloud KMS (§12.06)

> **LO#06: Discuss security in Google Cloud Platform (GCP)**
> Covers pp. 275–281: GCP encryption (pp275–276) · Cloud KMS (pp277–281).
> Downstream: [[12-LO06i-GCP-Defense-in-Depth-and-VPC]] (VPC) ·
> [[12-LO06g-GCP-Predefined-Roles-and-Logging-Roles]] (roles/permissions for KMS API use).

## Google uses encryption layers to protect data _(Mod 12 p275)_

- **Figure rule** — "Google uses **encryption layers** to protect data; Google's **default
  encryption of data at rest** is given below:"
- The printed layer stack, top to bottom: **Application → Platform → Infrastructure →
  Hardware**.
- "Google provides **several layers of encryption** to protect the customer data **at rest** in
  GCP products. In the GCP, the data are **encrypted at rest in multiple layers**."
- "At the **hardware device layer**, Google encrypts **hard disks and solid-state drives**
  with a **device-level key**."

| GCP Platform services | Printed protection |
|---|---|
| **Database and file storage** | "Protected by **AES256 or AES128** encryption" |
| **Distributed file system** | "**data chunks** in storage systems protected by **AES256** encryption **with integrity**" |
| **Block Storage** | "**Storage devices**: protected by **AES256 or AES128** encryption" |

_(Mod 12 p275)_

### The chunking / key-per-chunk statement — p276 verbatim

> "At the **storage level**, the data are broken into **chunks of different sizes**. **Each
> chunk is encrypted with a distinct encryption key.** The encryption keys **do not match with
> each other** in the Google Cloud Storage even though they **belong to the same customer or
> are stored on the same system**."

- "Google Cloud Storage **encrypts the customer data on the server side without any extra
  charge**." _(Mod 12 p276)_
- "In Google Cloud Storage, the stored customer content is encrypted using **AESes such as
  AES256 or AES128**." _(Mod 12 p277)_

## GCP data encryption options for customers _(Mod 12 pp275–276)_

**Figure set (p275)** — "Customers create and manage their own **customer-supplied encryption
keys**" · "Customers create and manage their own **customer-managed encryption keys using GCP
KMS**" · "**Client-side encryption** — **occurs before data are sent to the GCP**".

**Body set (p276)** — "In addition to the **standard cloud storage encryption**, there are
other ways to encrypt data before using the Cloud Storage such as:"

| Option | Printed definition |
|---|---|
| **Server-side encryption** | "Encryption of data on the server **before writing them on the disk**." |
| **Customer-supplied encryption keys** | "The customers **supply their own encryption keys** that act as an **extra encryption layer** along with the standard cloud storage encryption. The customers create and manage their own customer-supplied encryption keys." |
| **Customer-managed encryption keys** | "The customers use the **keys generated by KMS**, which acts as an **additional encryption layer**. The customers generate and manage their own customer-managed encryption keys." |
| **Client-side encryption** | "The clients **encrypt the data before sending it** to cloud storage. The data reaches the cloud storage **in an encrypted format**." |

## Cloud Key Management Service (KMS) — the stated rules _(Mod 12 p277)_

- "Google Key Management Service (KMS) is a **repository for storing keys**."
- "It is a **cloud-hosted key management service** that lets consumers **manage cryptographic
  keys** for their cloud services."
- "The **Key Encryption Keys (KEKs)** that encrypt the **Data Encryption Keys (DEKs)** are
  **stored in the Cloud KMS**."
- "The users can **generate, destroy, or rotate** their own cryptographic keys."
- "Cloud KMS **enables the protection of confidential and sensitive data** on the GCP."
- "**Access control lists (ACLs)** allow users with an **authorized role** to decrypt the data
  in Google services."
- "Google stores the **encrypted keys with the data**."
- "These keys are **stored and utilized by Google's central KMS**, which **tracks and controls
  data access from the central point**."
- "Cloud KMS can be enabled by **typing the following command in the `gcloud` command-line
  utility**: `gcloud services enable cloudkms.googleapis.com`" · or "**Using Cloud Console UI**".

### Envelope encryption — because one key envelops another _(Mod 12 p277)_

- "The **Data Encrypted Keys (DEKs) are wrapped by the Key Encryption Keys (KEKs)** for
  storage. **Because one key envelops another, it is also termed as Envelope Encryption.**"

**Envelope Encryption** _(p277, as printed)_
1. "To generate a **DEK locally**, open a source library such as **OpenSSL**, and mention the
   **cipher type and password** for key generation."
2. "Employ a **DEK locally** to encrypt the data."
3. "In Cloud KMS, **generate a new key or use an existing key that acts as a KEK**."
4. "Use the **KEK to wrap the DEK**."
5. "**Store the encrypted data with the wrapped DEK**."

**Envelope Decryption** _(p277, as printed)_
1. "**Retrieve the stored encrypted data** with the wrapped DEK."
2. "To **unwrap the DEK**, utilize the **key stored in cloud KMS**."
3. "To **decrypt the encrypted data**, use the **plaintext DEK**."

**Storage shape** _(Fig 12.193)_

| Object | Where it lives |
|---|---|
| **Wrapped DEK** | stored **with the encrypted data chunk** in the storage system |
| **KEK** | stored **in KMS** |

### Walkthrough — enable Cloud KMS _(Mod 12 pp278–279)_

> "Cloud KMS can be enabled via the **GCP User Interface** or **`gcloud` command-line
> utility/cloud console user interface**." _(Mod 12 p278)_

1. "From the Google console dropdown menu, navigate to **IAM & admin** and select **Audit
   Logs** on the Menu tab." _(p278, Fig 12.194)_
2. "Go to **Filter Table** and select **Title: Cloud Key Management Service (KMS) API**."
   _(p278, Fig 12.195)_
3. "**Check the Cloud Key Management Service (KMS) API box**, **select the required service**,
   and click on **Save**." _(p279, Fig 12.196)_

CLI alternative _(Mod 12 p279)_ — "Use the **`gcloud` command-line utility**
(`gcloud services enable cloudkms.googleapis.com`) or cloud console user interface to enable
the cloud KMS."

## The key hierarchy — the stated rules _(Mod 12 p280)_

- "In cloud KMS, the **cryptographic keys are stored hierarchically** for effective access
  control management."
- "**Key ring is a collection of keys grouped for organizational purposes**"; "**Key rings are
  specific to a project and reside in a specific location**."
- "Create key rings with keys that possess **common permissions**, which would enable users to
  **grant, revoke, or modify permissions to all keys at the key ring level**."

| Level | Printed meaning |
|---|---|
| **Project** | "Because the cloud KMS resources **belong to the project**, the accounts with **primitive cloud IAM roles can access all resources**. Therefore, the user **should run the cloud KMS in a separate project**." |
| **Location** | "In a project, the user can create cloud KMS resources in **many locations**. These locations are the **geographical regions where the resource requests are processed** and their respective **cryptographic keys are stored**." |
| **Key Ring** | "Cloud KMS utilizes **object hierarchy**, in which the **keys inherit the property from the key rings** and reside at a location. A key ring is a **collection of keys** that are grouped for an **organizational purpose**. The **key rings are specific to a project**." |
| **Key** | "a **representation of a cryptographic key that safeguards the data**. The **key material** includes the **actual bits** used for encryption." |
| **Key version** | "a **representation of the key material related to the key**." |

_(Mod 12 p280)_

### Example — create a key ring and an encryption key _(Mod 12 pp280–281)_

Printed names: **KEYRING NAME — `testkey`**, **CRYPTOKEY NAME — `demolab`** _(p280 figure)_

**Create the key ring** — p280 figure:

```
gcloud kms keyrings create $KEYRING_NAME --location global
```

p280 body, same command, different rendering (key name garbled — **not** reconstructed):

```
gcloud kms keyrings create demo <flag garbled> <flag garbled>10cation global
```

**Create the encryption key** — p280 figure:

```
gcloud kms keys create $CRYPTOKEY_NAME --location global \
    --keyring $KEYRING_NAME \
    --purpose encryption
```

p281 body, the command actually printed there:

```
gcloud kms keys create democode ——purpose encryption \
    ——10cation global \
    ——keyring testkey\
```

> Flags are transcribed as printed. The OCR renders the leading dashes as `——` and reads
> `location` as `10cation` in two of the three places; `purpose` and `keyring` are legible
> everywhere. The literal key name differs between the p280 text (`demolab`) and the p281
> command (`democode`). See `unresolved:`.

**Verify** — "View the created resources in the **Encryption Keys / Cryptographic Keys Web UI
under IAM & Admin**." _(p280 says *Encryption Keys*, p281 says *Cryptographic Keys* — both
printed)_







