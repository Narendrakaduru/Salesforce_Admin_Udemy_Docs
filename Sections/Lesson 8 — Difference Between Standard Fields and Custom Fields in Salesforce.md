# Lesson 8 — Difference Between Standard Fields and Custom Fields in Salesforce

## Lesson Summary

This lesson explains the difference between **Standard Fields** and **Custom Fields** in Salesforce. Standard Fields are automatically provided by Salesforce and appear on objects by default, while Custom Fields are created to meet business requirements. The lesson also covers system-generated fields, field naming conventions, deletion rules, and customization options.

---

## Key Points

- **Standard Fields** are predefined and automatically available.
- **Custom Fields** are created manually based on business needs.
- Standard fields **cannot be deleted**.
- Custom fields **can be created and deleted**.
- Custom fields always end with:
    - **`__c`**
- Standard fields exist on both **Standard Objects** and **Custom Objects**.
- Both field types support **custom help text**.
- Some standard fields appear only when specific Salesforce features are enabled.

---

## Detailed Notes

### What are Standard Fields?

Standard Fields are predefined fields automatically created by Salesforce.

**Purpose:**
- Provide system-level tracking
- Maintain object information
- Store standard metadata

These fields are automatically added when:
- Creating a custom object
- Using standard objects

**Examples:**
- Name
- Created Date
- Last Modified Date
- Owner

**Important:**
- You cannot remove these fields permanently.
- You may remove non-required fields from the page layout.

---

### Characteristics of Standard Fields

**Features:**
- Automatically generated
- Available across objects
- Cannot be deleted
- Support customization such as help text

**Examples of standard fields:**
- Created By
- Created Date
- Last Modified By
- Owner
- Name

---

### Standard Fields Automatically Added to Custom Objects

When creating a custom object, Salesforce automatically adds system fields.

---

### 1. Created By ID

**Purpose:**
Stores the ID of the user who created the record.

**API Name:**
`CreatedById`

**Meaning:**
Who created this record?

---

### 2. Currency Field

**Purpose:**
Stores record currency.

**Condition:**
Only available when:
`Multi-Currency = Enabled`

If multi-currency is disabled:
Field does not appear.

---

### 3. Division Field

**Purpose:**
Used to segment data.

**Condition:**
Only appears if organization supports divisions.

**Example:**
- Sales Division
- Support Division

---

### 4. Last Modified By ID

**Purpose:**
Stores user ID of the latest editor.

**API Name:**
`LastModifiedById`

**Meaning:**
Who changed the record last?

---

### 5. Name Field

**Purpose:**
Primary identifier for records. This field is mandatory.

Record Name can be:
- **Text Type** (e.g., *Employee Name*)
- **Auto Number** (e.g., *EMP-0001, EMP-0002*)

Every object requires a Record Name field.

---

### 6. Owner ID

**Purpose:**
Stores owner information.

**API Name:**
`OwnerId`

**Represents:**
Assigned owner of the record.

---

### Standard Fields for Custom Objects

| Field Name | Description |
| --- | --- |
| **CreatedById** | Stores the **ID of the user who created the record**. |
| **Currency** | Stores the **currency of the record** (available only if **Multi-Currency** is enabled). |
| **Division** | Represents the **division to which the custom object record belongs**. Available only if the organization uses **Divisions** for data segmentation. |
| **LastModifiedById** | Stores the **ID of the user who most recently modified the record**. |
| **Name** | Acts as the **identifier for the custom object record** (Record Name field). |
| **OwnerId** | Stores the **ID of the assigned owner** of the custom object record. |

**Notes:**
- These fields are **automatically created by Salesforce**.
- They appear on **Custom Objects** by default.
- **Currency** appears only when **Multi-Currency** is enabled.
- **Division** appears only if **Divisions** are enabled.
- These fields are **Standard Fields** and **cannot be deleted**.

**Certification Shortcut:**
- `CreatedById` → Who created?
- `LastModifiedById` → Who changed?
- `OwnerId` → Who owns?
- `Name` → Record identifier
- `Currency` → Multi-currency only
- `Division` → Division-enabled org only

---

### What are Custom Fields?

Custom Fields are fields created manually based on business requirements.

**Purpose:**
Store additional business data.

**Example:**
- **Object:** Employee
- **Custom Fields:**
    - Phone Number
    - Address
    - Department

These fields did not exist by default.

---

### Custom Field Naming Convention

Every custom field ends with:
`__c`

**Examples:**
- `Phone_Number__c`
- `Address__c`
- `Salary__c`

**Meaning:**
`__c` = Custom

---

### Where Can Custom Fields Be Created?

Custom Fields can be added to:

**Standard Objects:**
- `Account`
- `Lead`
- `Opportunity`

**Custom Objects:**
- `Employee__c`
- `Hospital__c`

---

### Field Deletion Rules

| Field Type | Delete Allowed |
| --- | --- |
| Standard Field | ❌ No |
| Custom Field | ✅ Yes |

**Exception:**
Non-required standard fields may be removed from page layout.

---

### Help Text Customization

Both Standard Fields and Custom Fields support:
`✅ Help Text`

**Purpose:**
Explain field usage to users.

**Example:**
- **Field:** Phone Number
- **Help Text:** *Enter employee contact number*

---

## Steps / Process

### Create Custom Field

1. Open **Setup**
2. Open **Object Manager**
3. Select desired **Object**
4. Open **Fields & Relationships**
5. Click **New**
6. Select Field Type, configure settings, and click **Save**

---

### Remove Standard Field from Layout

1. Open desired **Object**
2. Open **Page Layouts**
3. Drag field off the layout
4. Click **Save**

*(Note: The field still exists on the database level, but is hidden from the UI).*

---

## Important Terms

| Term | Meaning |
| --- | --- |
| **Standard Field** | Salesforce predefined field |
| **Custom Field** | User-created field |
| **CreatedById** | Creator of record |
| **OwnerId** | Assigned record owner |
| **LastModifiedById** | Last editor |
| **Record Name** | Main identifier |
| **Multi-Currency** | Supports multiple currencies |
| **Division** | Data segmentation |
| **Help Text** | User guidance |

---

## Commands / Syntax / Configuration

### Custom Field Naming
`FieldName__c`

**Examples:**
- `Phone__c`
- `Address__c`
- `Salary__c`

---

### Create Custom Field
```
Setup → Object Manager → Fields & Relationships → New
```

---

### Record Name Types
- Text
- Auto Number

---

## Examples

### Example 1 — Standard Field

- **Object:** `Employee__c`
- **Fields automatically created:**
    - `CreatedById`
    - `OwnerId`
    - `Name`

---

### Example 2 — Custom Field
- **Requirement:** Store employee phone number
- **Create:** `Phone_Number__c`

---

### Example 3 — Auto Number
Record Name format:
`EMP-001, EMP-002`

---

## Certification Focus

### Important for Exam

Remember:

| Standard Field | Custom Field |
| --- | --- |
| System Generated | User Created |
| Cannot Delete | Can Delete |
| No `__c` | Ends with `__c` |

Know:
- Record Name is mandatory
- `CreatedById` and `OwnerId` are system fields
- Currency field depends on Multi-Currency settings

---

### Common Mistakes

- Confusing object naming with field naming
- Trying to delete standard fields
- Forgetting `__c` suffix
- Assuming every organization has Currency and Division fields enabled

### Remember

```
Standard = Salesforce Created
Custom = Business Created
```

---

## Real-World Application

**Examples:**

| Requirement | Field |
| --- | --- |
| Employee Contact | `Phone__c` |
| Hospital Patient ID | `Patient_ID__c` |
| Student Roll Number | `Roll_Number__c` |

Standard fields help with:
- Audit tracking
- Ownership
- Record identification

---

## Quick Revision (30 sec)

- Standard fields are predefined
- Custom fields are user-created
- Standard fields cannot be deleted
- Custom fields end with `__c`
- `CreatedById` → Creator
- `OwnerId` → Record owner
- `LastModifiedById` → Latest editor
- Record Name is mandatory
- Currency field depends on settings
- Both support help text