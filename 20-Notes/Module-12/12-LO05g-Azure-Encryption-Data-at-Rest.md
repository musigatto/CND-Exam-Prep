---
type: note
module: "12"
lo: "05"
tags: [crypto, process, mod/12, flashcard/12]
topic: "Azure encryption at rest — models, SSE, Key Vault, TDE"
exam_weight: unknown
status: done
unresolved:
  - "p193/p196 CONTRADICTION on SSE: the body says SSE 'automatically encrypts the data during storage' and is 'applied to the entire storage system of Microsoft Azure', yet also says 'users can enable or disable this feature' and 'the data are encrypted only when SSE is enabled'. The p193 figure shows a storage account with Encryption 'Disabled'. Both readings preserved; not reconciled."
  - "p196 SSE scope claim 'SSE is applied to any type of data and the encrypted data are stored in Blob Storage' is narrower than p193's figure text ('Azure Blobs and Files'). Both printed; not reconciled."
  - "pp196-197 Steps to Enable SSE: steps 4 and 5 both end 'then click on Create' — step 4 is the 'select from the Key Vault' path and step 5 reads 'Select Encryption key and enter the details, then click on Create'. The two steps are transcribed exactly as printed; which key-source each belongs to (Own key/Enter URI vs Select from Key Vault) is NOT asserted."
  - "p197 Figure 12.125 is partly garbled: 'By default, in the account is encrypted using Wcrosoft Managed Keys You nuy choose to bring your o. and may to bring key nd nd Wcrosdt M.n.ged note that •ter enabling Storage E neryptie•n only w• be encrypted, •nd •ny existing in t' reroacüvely get euryged by a background encryption process.' Readable: default = Microsoft Managed Keys; choices appear as 'Your own key' / 'Enter URI' and 'Select from Key Vault Key'; 'after enabling Storage Encryption only [new data] will be encrypted, and any existing [data] will retroactively get encrypted by a background encryption process'. The exact option labels are not asserted."
  - "The key created in the Key Vault walkthrough prints garbled as 'user%l' (Fig 12.123 'The userSWV has been successfully created. Name user%l') and 'user%l' again in Fig 12.125. The real key name is NOT asserted."
  - "p195 Figure 12.119 field values legible: Subscription, Resource group (MyResourceGroups), Key vault name (KeyVaultPorta…), Region (East US), Pricing tier (Standard), Recovery options, and 'Soft delete protection will automatically be enabled on this key vault'. Whether 'Recovery options' is a field or the soft-delete note is a field caption is not resolvable from the OCR."
  - "p196 Figure 12.122 lists RSA key size options 2048 / 3072 / 4096 with Key type RSA; the step text names 'Options, Name, Key Type, RSA Key Size' plus 'click on Yes to Enable it'. The field called 'Options' in the step is not matched to anything legible in the figure."
  - "p199 Figure 12.129 breadcrumb/URL strings OCR as 'Microscft.SQLDatabase.newDatabaseExistingSetver_a1a727cecb134595' and '(qhk01/example5525)' — resource/server names only, not protocol defaults; not asserted."
  - "p192 slide 'Azure Disk Encryption for Windows and Linux IaaS VMs — Encrypts disk on Azure VMs' appears with no matching body text in pp192-199. No configuration steps for ADE are printed in this range."
---

[[MOC-Module-12]]

# Azure Encryption — Data at Rest (§12.05)

> Covers pp. 192–199: data encryption models (pp192–193) · Azure Key Vault (pp192, 194–196) ·
> Azure Storage Service Encryption (pp193, 196–197) · Transparent Data Encryption (pp197–199).
> Compare AWS: `[[12-LO04j-AWS-Encryption-Data-at-Rest]]`, `[[12-LO04k-AWS-Encryption-Client-Side-CloudHSM-and-Transit]]`.

## Data Encryption Models — exactly as printed _(Mod 12 pp192–193)_

**1. Server-side Encryption Model** — "In this type of model, the encryption and decryption
operations are performed by the **Azure resource provider**." _(p193)_
Three sub-models (p192 slide names / p193 body):

| Sub-model | Who encrypts/decrypts | Who holds the key | Extra printed |
|---|---|---|---|
| SSE using **service-managed keys** | Azure resource provider | "The keys are managed by **Microsoft Azure**. Microsoft Azure **creates, stores, and retrieves the keys** as required." | "quickly fulfills the requirement of encryption at rest with **less expenditure for the customer**" |
| SSE using **customer-managed keys in Azure Key Vault** | "Microsoft Azure encrypts and decrypts the data" | "managed by the **customer through the Azure Key Vault**" | "**Loss of encryption keys lead to loss of data**; therefore, users should **not delete the encryption keys**, but **keep a backup of the creation or rotation of keys**" |
| SSE using **customer-managed keys on customer-controlled hardware** | Azure resource provider | "The **customer** manages the keys on **customer-controlled hardware**" | — |

**2. Client-side Encryption Model** — "In this model, encryption is performed **outside the Azure
service provider** by the service or calling application. The Azure service provider **receives
encrypted data, which it cannot decrypt**. The **users manage and store the keys, which cannot be
accessed by the resource provider**." _(p193)_

Figure flow (p192): Server-side = `Resource Provider` → `Application`.
Client-side = `Application` → **Encryption and Key Management** → `Resource Provider`.
_(i.e. key management sits between the app and the provider.)_

## Azure Key Vault _(Mod 12 pp192, 194–196)_

"Azure Key Vault is a **secure storage for the keys used to encrypt the data at rest in Azure
services**." _(p192, 194)_

- "Azure **disk encryption** can be performed through the Azure Key Vault to control and manage the
  encrypted keys. The encryption of virtual disks **requires the creation of Azure Key Vault** to
  store the cryptographic keys that help in encrypting or decrypting the virtual disks." _(p194)_
- p192 slide also carries: **"Azure Disk Encryption for Windows and Linux IaaS VMs — Encrypts disk on
  Azure VMs."** (no steps printed for it in this range)

**Concerns it addresses** _(p194)_

| Concern | Printed |
|---|---|
| Secrets management | "securely store and **tightly control the access** to **tokens, passwords, and API keys**" |
| Key management | "**create and control the encryption keys**" |
| Certificate management | "manage the **SSL/TLS certificates** to use with Azure and the internal connected resources" |
| Store secrets backed by HSM | "The secrets and keys are protected by **software or FIPS 140-2 Level 2 validated hardware security modules**" |

**Advantages** _(p194, five as printed)_ — Centralized application secrets · Securely stores secrets
and keys · Monitors access and use · Simplified administration of application secrets · Integrates
with other Azure services.

### Steps to create a Key Vault _(Mod 12 pp194–196)_

1. From the Microsoft Azure Portal, navigate to **All Services**.
2. Click on **Key vaults**, then select **Add** to create a key vault.
3. "Fill the details in **Create key vault** and Click on **Review + create**."
4. "After validation, Click on **Go to resource**."
5. "In the **Settings** Section, click on **Keys**. Click on **Generate/Import** to create a key."
6. "Fill in the details such as **Options, Name, Key Type, RSA Key Size**, and click on **Yes to
   Enable it**. Click on **Create** for creating a key."

**Fields readable in the figures** _(pp195–196)_: Create key vault — *Subscription · Resource group ·
Key vault name · Region · Pricing tier · Recovery options*; soft delete protection is
"automatically enabled" on the key vault.
Create key — *Name · **Key type: RSA** · **RSA key size: 2048 / 3072 / 4096** · Set activation date ·
Set expiration date · Enabled: Yes*.

## Azure Storage Service Encryption (SSE) _(Mod 12 pp193, 196)_

- "Protects data by encrypting them using **256-bit AES** encryption **before storing**, and
  **decrypts them upon retrieval**." _(p193)_
- "SSE **automatically encrypts** the data during storage and **decrypts the data at the time of
  retrieval**. It uses **256-bit AES encryption**. SSE is applied to the **entire storage system** of
  Microsoft Azure, and users can **enable or disable** this feature. The data are encrypted only when
  SSE is enabled." _(p196 — see `unresolved:`)_
- "SSE is applied to **any type of data** and the encrypted data are stored in **Blob Storage**." _(p196)_

### Steps to Enable SSE _(Mod 12 pp196–197)_

1. From the Microsoft Azure Portal, navigate to **All Services**. Click on **Storage Account**.
2. "Select and Click on **Storage Account** (`labexample`) to enable SSE."
3. "Under **Settings**, click on **Encryption**. Select **Encryption key** as per requirement."
4. "To select from the **Key Vault**, select **Key Vault** and enter the details; then, click on
   **Create**."
5. "Select **Encryption key** and enter the details, then click on **Create**."
6. "Click on **Save** to enable SSE in Microsoft Azure."

## Transparent Data Encryption (TDE) _(Mod 12 pp197–199)_

- "Transparent Data Encryption (TDE) is an **SQL Azure feature** to encrypt data at both the
  **database and server levels**." _(p193, 197)_
- "It **encrypts data at rest** and protects the **Azure SQL Database, Azure SQL Managed Instance,
  and Azure Data Warehouse** against cyber threats." _(p197)_
- "TDE executes encryption and decryption of the **database, backups, and transaction log files at
  rest** **without modifying the application**." _(p197)_
- Scope: "**To enable TDE, go to each database.**" _(p199, figure text)_

### Steps to enable TDE _(Mod 12 pp198–199)_

1. "From the Microsoft Azure **Home Page**, select **SQL databases**."
2. "Click on **Add** and enter the required details to create SQL Database; next, click on
   **Review + create**."
3. "After deployment, click on **Go to resource**."
4. "Under the **Security** section, click on **Transparent data encryption**."
5. "Click **On** for **Data encryption** and **Save**."

Security-section items visible in Fig 12.129 _(p199)_: *Advanced data security · Auditing · Dynamic
Data Masking · Transparent data encryption*; controls **Data encryption ON/OFF** and **Encryption
status: Encrypted**.

## Cards

The two data encryption models in Microsoft Azure and who performs the crypto
?
1. Server-side — the Azure resource provider performs encryption and decryption; 2. Client-side — encryption is performed outside the Azure service provider by the service or calling application, and the provider receives data it cannot decrypt

The three sub-models under the server-side encryption model
?
SSE with service-managed keys (Microsoft manages the keys) · SSE with customer-managed keys in Azure Key Vault · SSE with customer-managed keys on customer-controlled hardware

What the courseware warns about when you manage your own keys in Azure Key Vault
?
Loss of encryption keys leads to loss of data — do not delete the encryption keys, but keep a backup of the creation or rotation of keys

What Azure Key Vault is used for, and the three concerns it addresses plus HSM backing
?
A secure storage for the keys used to encrypt data at rest in Azure services — secrets management (tokens, passwords, API keys), key management, certificate management (SSL/TLS), and secrets/keys protected by software or FIPS 140-2 Level 2 validated HSMs

Azure Storage Service Encryption — the algorithm and the encryption point
?
256-bit AES — data is encrypted before storing and decrypted upon retrieval; it is applied to the entire Azure storage system, users can enable or disable it, and data is encrypted only when SSE is enabled

Transparent Data Encryption in Azure — what it is and what it covers
?
An SQL Azure feature that encrypts data at both the database and server levels, covering the database, backups and transaction log files at rest without modifying the application; protects Azure SQL Database, SQL Managed Instance and Data Warehouse; it must be enabled per database