---
type: note
module: "10"
lo: "03"
tags: [concept, process, command, crypto, mod/10]
topic: "Database Encryption — SQL Server TDE, Always Encrypted, Oracle TDE"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Database Encryption (§10.3.6)

## Why encrypt at DB level
- Protects specific DB subset or entire DB; countermeasure vs malicious insiders; data-at-rest

## MS SQL Server — Transparent Data Encryption (TDE)
- Encrypts **one or more database files** (data + log) transparently at I/O layer; app unchanged
- Cipher support: AES-128/192/256, 3DES; default AES-128
- **Key hierarchy**: database encryption key (DEK) → certificate → master key
- Setup (TSQL):
  1. Create master key `CREATE MASTER KEY ENCRYPTION BY PASSWORD='...'`
  2. Create/import cert in master DB `CREATE CERTIFICATE ...`
  3. Create DEK: `CREATE DATABASE ENCRYPTION KEY WITH ALGORITHM = AES_128 ENCRYPTION BY SERVER CERTIFICATE ...`
  4. `ALTER DATABASE ... SET ENCRYPTION ON`
- Verify: `SELECT name, is_encrypted FROM sys.databases`

## MS SQL Server — column/cell-level encryption
- Encrypt individual columns with symmetric key; DB decrypts on SELECT (`DECRYPTBYKEY`)
- Keys stored in DMK (master key); decrypt fn requires session key context

## MS SQL Server — Always Encrypted
- Client-side encryption; **database engine never sees plaintext/keys** → protects at rest AND in transit
- Column encryption types:
  | Type | Behavior |
  |---|---|
  | **Randomized** | Same plaintext → different ciphertext; no equality ops |
  | **Deterministic** | Same plaintext → same ciphertext; enables equality lookups/joins, grouping, indexing |
- Keys: Column Master Key + Column Encryption Key; supports on-prem + Azure SQL DB

## Oracle TDE
- Encrypts **specific table columns or entire tablespace**; transparent
- Wallet-based keystore; enable per column/tablespace; `ALTER SYSTEM SET ENCRYPTION WALLET OPEN`

## Best practices
- Strong passwords + key management; rotate certs; test restore; never store keys in plaintext; encrypt at rest + in transit

## Cards
Q:: TDE: key hierarchy order and default algorithm?
A:: DEK → certificate → master key; default AES-128 (also AES-192/256, 3DES).
#flashcard
Q:: Which statement turns on TDE for a database?
A:: `ALTER DATABASE <db> SET ENCRYPTION ON`.
#flashcard
Q:: Always Encrypted randomized vs deterministic?
A:: Randomized = different ciphertext each time, no equality ops; Deterministic = same ciphertext for same plaintext, enables equality lookups/joins.
#flashcard
Q:: Where are Always Encrypted keys held, and what does the engine see?
A:: Keys stored client-side (Column Master Key/Column Encryption Key); engine never sees plaintext or keys → protects at rest + in transit.
#flashcard
Q:: Oracle TDE: what can be encrypted and what enables the keystore?
A:: Specific table columns or entire tablespace; wallet opened via `ALTER SYSTEM SET ENCRYPTION WALLET OPEN`.
#flashcard