# Excel Data Cleaning Steps

All initial data cleaning was performed in Excel prior to importing into MySQL.  
Below are the steps and formulas used:

---

## 1. Extract state code from address

**Tables:** `customers`, `suppliers` <br>
**Original column:** `address` (e.g., "123 Main St, Springfield, IL") <br>
**Goal:** Extract the state code (e.g., "IL") into a new column `state_code` <br>

**Formula :**
```excel
=TRIM(TEXTAFTER(D2,",",-1))
```

**Explanation:**
- TEXTAFTER(D2,",",-1) extracts everything after the last comma
- TRIM() removes extra spaces
- This creates a clean two-character state code for easier regional analysis

## 2. Standardize phone number format

**Tables:** `suppliers` <br>
**Original column:** `phone_number` (e.g., "(555) 484-6922") <br>
**Goal:** Convert all phone numbers to the standard XXX-XXX-XXXX format

**Step :**
- Used Excel Find & Replace:
- Find: (555) → Replace with 555-
- This converted phone numbers like (555) 484-6922 → 555-484-6922

**Explanation:**
- Quick and effective for this dataset
- Ensures consistent phone number format for database import





