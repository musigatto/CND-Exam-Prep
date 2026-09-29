---

type: note
module: "10"
lo: "05"
tags: [concept, process, command, tool, mod/10, flashcard/10]
topic: "Data Masking — Algorithms, Techniques, Implementations"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-10]]

# Data Masking Algorithms (§10.5.2)

Data masking = data obfuscation/anonymization: replace/hide/scramble original data with fictitious or pseudonymous data **preserving format and structure**.

| Algorithm | Behavior |
|---|---|
| **Character Scrambling** | Characters jumbled into a random order (mask original data) |
| **Lookup Substitution** | Lookup table provides an alias for the original value |
| **Nulling Out / Deletion** | Data becomes **null** for unauthorized users |
| **Shuffling** | Data in an individual column randomly shuffled/swapped |
| **Number/Date Variance** | Dataset changed by a **random percentage** of its real value |
| **Masking Out** | Only part masked with a mask character (e.g., **X**) |
| **Date Aging** | Dates masked via policies applied to each field to **confuse the real date** |
| **Pseudonymization** | Sensitive data replaced with a **pseudonym** (privacy compliance + analytics) |
| **Averaging/Data Generalization** | Table values replaced with **average values** |

# Data Masking Techniques (§10.5.3)

| Technique | Behavior | Notes |
|---|---|---|
| **Nulling out/nullifying** | Null replaces actual values | Easy, but null column can't be used in queries/analysis → damages dev/test data quality |
| **Substitution** | Replace data with different value | Preserves original look-and-feel; harder than scrambling but higher security; e.g., valid card numbers |
| **Shuffling** | Same column, random order (e.g., employee names, birthdates) | Output accurate but prone to reverse engineering if algorithm known |
| **Data shifting** | Add/subtract dates within an acceptable policy range | Randomly relocates position of each character by key value |
| **Tokenization** | Replace with unique tokens mapping back to original | Protects credit cards, ID cards, SSNs, social identity proofs |
| **Format-Preserving Encryption (FPE)** | Encrypt preserving length + character set | Phone numbers, bank cards, restructuring databases |
| **Hashing** | Fixed-length output from input | Digital signatures, MACs, stored passwords |

## SQL Server Dynamic Data Masking
- Masks query results for unauthorized users; e.g., `alter table employee alter column empname varchar(50) masked with (Function='default()');`
- Mask types: **Default** (masks entire field per data type) · **Email** (masks email fields) · Partial/Custom · Random

## Oracle data masking — F.A.S.T. (Oracle Data Masking Pack)
Four-step approach: **F**ind → **A**ccess → **S**ecure → **T**est
1. **Find**: locate sensitive data via Enterprise Manager discovery jobs (data patterns: 15/16-digit credit card, 9-digit US SSN; Create Sensitive Column Type e.g. `CREDITCARDNUMBER`)
2. **Access**: define access/authorization to masked data
3. **Secure**: apply a masking definition (e.g., masking job over target tables)
4. **Test**: validate masked output / data usefulness

- Improves security, accelerates analytics/development; remains compliant across sources (preserves referential integrity)

## Cards
Name the 4 data masking types by environment.
?
Static (at rest), Dynamic (in transit/role-based), On-the-fly (between environments); plus DB proxies for DDM.

Three distinguishing masking algorithms for numbers/dates/IQ.
?
Number/Date Variance (random %), Date Aging (policy per field), Averaging/Data Generalization (average values).

What technique replaces card numbers w/ valid-looking but fake numbers?
?
Substitution (meets card-provider validation rules).

Tokenization vs format-preserving encryption?
?
Tokenization = unique tokens map back to original (IDs, cards); FPE = encrypts preserving length/character set (phones, cards).

What does the F.A.S.T. acronym in Oracle data masking mean?
?
Find → Access → Secure → Test.

Which SQL Server DDM mask function masks the entire field per data type?
?
`default()` — e.g., `alter table employee alter column empname ... masked with (Function='default()')`.
