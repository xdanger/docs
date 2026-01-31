# File & Folder Naming Conventions

> CLI-safe, sortable, semantic naming rules for PARA-based file organization.

## Character Rules

```
Files:   A-Z a-z 0-9 _ + , -
Folders: A-Z a-z 0-9 _ + , - @
```

**Notes:**

- `.` is reserved for file extension separator only (e.g., `.pdf`)
- `@` is forbidden in filenames (many upload services reject it)

## Separator Hierarchy

| Symbol | Purpose                         | Scope            | Example                     |
| ------ | ------------------------------- | ---------------- | --------------------------- |
| `_`    | Semantic block separator        | Files & Folders  | `Date_Name_Type`            |
| `-`    | Word connector (replaces space) | Files & Folders  | `Court-Opinion`             |
| `+`    | Combination (union)             | Files & Folders  | `Yunjie+Yunruo`             |
| `,`    | Enumeration (list)              | Files & Folders  | `Beijing,Shanghai,Hangzhou` |
| `@`    | Group/person prefix             | **Folders only** | `@family/`, `@veronica/`    |
| `.`    | File extension only             | Files            | `.pdf`                      |

### `@` — Group/Person Folder Prefix

Marks shared spaces or person-specific folders (**directories only**, not filenames):

```
@family/           # Shared family folder
@parents/          # Parents' files
@veronica/         # Veronica's personal folder
```

**Why folders only?** Many web services and upload forms reject `@` in filenames.

### `+` — Combination/Union

Multiple elements **merged as one unit**:

```
# Multiple people (joint ownership)
Contract_Yunjie+Yunruo_v20250101.pdf    # Co-signed by both
Account_Joint_Yunjie+Yunruo.pdf         # Joint account

# Combined types
CN+US_Tax-Return_2024.pdf               # Combined tax filing
Hotel+Flight_Invoice_20251220.pdf       # Bundled booking
```

### `,` — Enumeration/List

Multiple **independent items** listed:

```
# Multiple locations
Photo_Beijing,Shanghai,Hangzhou_2024.jpg

# Multiple sources
Receipt_Amazon,Costco,Target_202412.pdf

# Multiple languages/versions
Manual_EN,CN,JP.pdf
```

### `+` vs `,` Quick Reference

| Symbol | Semantics | Relationship        | Example                      |
| ------ | --------- | ------------------- | ---------------------------- |
| `+`    | Union     | A and B as one      | `Dad+Mom` = parents together |
| `,`    | List      | A, B, C independent | `NYC,LA,SF` = three cities   |

**Tip:** If list exceeds 3 items, consider splitting files or using folder structure instead.

## Date Format

**Base format:** `YYYYMMDD` (8 digits, no separator)

```
20251219    Document/creation date
v20250101   Valid from (effective date)
x20261231   Expires on
```

**Combined:** `vYYYYMMDDxYYYYMMDD` for validity period

```
v20250522x20350521   Valid 2025.05.22 → Expires 2035.05.21
```

## Date Position Strategy

| Scenario                                  | Date Position | Reason             |
| ----------------------------------------- | ------------- | ------------------ |
| Time-series files (logs, notes, receipts) | **Prefix**    | Sort by date       |
| Persistent files (credentials, contracts) | **Suffix**    | Group by type/name |

### Prefix Pattern (Sort by Date)

```
YYYYMMDD_[Name]_[Details].[ext]
```

Examples:

```
20251219_Tornetta-v-Musk_DE-Supreme-Court-Opinion.pdf
20251220_Meeting-Notes_Project-Alpha.md
20240315_Invoice_CompanyX_USD1500.pdf
```

### Suffix Pattern (Group by Type)

```
[Type]_[Owner]_[ID]_[Validity].[ext]
```

    Examples:
    ```
    CN-PP_Yunjie_E12345678_v20200101x20300101.pdf
    HRP_Yunjie_H12345678_v20250522x20350521.pdf
    US-Visa_Yunjie_B1B2_x20280915.pdf
    Contract_Apartment-Lease_v20250101x20261231.pdf
    ```

## Naming Components

### For Credentials & Official Documents

```
[Type]_[Holder]_[ID]_[Validity].[ext]
   │       │       │       │
   │       │       │       └─ v/x dates (suffix)
   │       │       └─ Official ID number
   │       └─ Person name
   └─ Country-DocType (hyphen-connected)
```

**Document type codes:**

| Code                  | Description                               |
| --------------------- | ----------------------------------------- |
| **Identity Cards**    |                                           |
| CN-ID                 | 中国身份证                                |
| HKID                  | 香港身份证                                |
| SG-NRIC               | 新加坡身份证                              |
| US-GC                 | 美国绿卡                                  |
| US-SSN                | 美国社保卡                                |
| US-DL                 | 美国驾照                                  |
| US-StateID            | 美国州身份证                              |
| **Passports**         |                                           |
| CN-PP                 | 中国护照                                  |
| HK-PP                 | 香港护照                                  |
| US-PP                 | 美国护照                                  |
| **Travel Permits**    |                                           |
| HRP                   | 回乡证 (Home Return Permit)               |
| MTP                   | 台胞证 (Mainland Travel Permit)           |
| **Singapore Permits** |                                           |
| SG-EntryPermit        | 新加坡 PR 入境许可 (Form 5A)              |
| SG-REP                | 新加坡再入境许可 (Form 7)                 |
| **Other**             |                                           |
| Visa                  | 签证 (with country prefix, e.g., US-Visa) |
| Bank                  | 银行卡/账单                               |
| Insurance             | 保险单                                    |

### For General Files

```
YYYYMMDD_[Primary-Name]_[Secondary-Info].[ext]
             │                  │
             │                  └─ Source, version, type, etc.
             └─ Main subject (kebab-case)
```

### For Project Files

```
YYYYMMDD_[Deliverable]_[Project]_[Version].[ext]
```

Examples:

```
20251219_Wireframe_Website-Redesign_v2.pdf
20251220_Budget_Q1-Marketing_Draft.xlsx
```

## ID Numbers in Filenames

**Include when:**

- Multiple similar documents exist (old/new passport)
- Quick lookup needed (searching by ID)
- Official reference required

**Position:** After holder name, before validity dates

    **Format:** Continuous characters without separators (remove dashes/spaces from original)
    ```
    E12345678       Passport number
    H12345678       HRP number
    S1234567A       Singapore NRIC
    123456789       LPR/Green Card (A#)
    987654321       SSN (no dashes)
    4000xxxx5678    Credit card (masked middle digits for privacy)
    ```

## Folder Naming

### PARA Top-Level

```
0-Inbox/
1-Projects/
2-Areas/
3-Resources/
4-Archives/
```

### Category Conventions

| PARA Category | Style                           | Example                              |
| ------------- | ------------------------------- | ------------------------------------ |
| Projects      | Emoji prefix (optional) + Title | `Bathroom-Renovation/`               |
| Areas         | UPPERCASE                       | `HEALTH/`, `FINANCES/`               |
| Resources     | lowercase                       | `cooking-recipes/`, `design-assets/` |
| Archives      | Date prefix                     | `2024-Q4/`, `Archive-20241201/`      |

## Quick Reference

```
# Time-series (prefix date, sort by time)
YYYYMMDD_Name_Details.ext
20251219_Court-Opinion_Tornetta-v-Musk.pdf

# Credentials (suffix date, group by type)
Type_Holder_ID_vYYYYMMDDxYYYYMMDD.ext
CN-PP_Yunjie_E12345678_v20200101x20300101.pdf

# Joint ownership
Contract_Yunjie+Yunruo_v20250101.pdf

# Expiry-only document
US-Visa_Yunjie_B1B2_x20280915.pdf

# No date needed
README.md
API-Documentation.pdf
```

## Anti-Patterns

```
❌ My Document (1).pdf          # Spaces, parentheses
❌ final_FINAL_v2_really final  # Ambiguous versioning
❌ 2025.12.19_file.pdf          # Dots in date (use 20251219)
❌ v1.2.3_release.zip           # Dots in version (use v1-2-3)
❌ file_name_.pdf               # Trailing underscore
❌ FILE NAME.PDF                # Spaces, shouty
❌ CN-PP@Yunjie.pdf             # @ in filename (use _ instead)
```

---

_The goal: any file can be found by sorting, searching, or browsing—pick the pattern that optimizes for your most common access method._
