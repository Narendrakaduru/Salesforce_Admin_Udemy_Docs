# Lesson 7 — Difference Between Standard Objects and Custom Objects in Salesforce

## Lesson Summary

This lesson explains the differences between **Standard Objects** and **Custom Objects** in Salesforce. Standard Objects are prebuilt by Salesforce and support common CRM operations, while Custom Objects are created by administrators or developers to support unique business requirements. The lecture also introduces practical differences such as **deletion, sharing settings, truncation, API naming conventions, and field behavior**.

---

## Key Points

- **Standard Objects** are provided by Salesforce.
- **Custom Objects** are created based on business requirements.
- Standard Objects **cannot be deleted**.
- Custom Objects **can be deleted**.
- Only Custom Objects support configurable **Grant Access Using Hierarchies**.
- Only Custom Objects support the **Truncate** operation.
- Custom Objects use the naming convention:
    - **`__c`**
- Standard Objects can be extended with **custom fields**.
- Custom Objects automatically include standard **system fields**.

---

## Detailed Notes

### What are Standard Objects?

Standard Objects are prebuilt objects that come with Salesforce.

**Purpose:**
- Provide default CRM functionality
- Support common business operations

**Examples:**
- **Account**
- **Lead**
- **Opportunity**
- **Contact**
- **Campaign**

These objects are available immediately after creating a Salesforce org.

**Standard Objects List:**
- `Account`
- `Lead`
- `Opportunity`
- `Contact`

---

### What are Custom Objects?

Custom Objects are objects created by users based on business requirements.

**Purpose:**
- Store organization-specific information
- Extend Salesforce capabilities

**Examples from lecture:**

#### Car Dealership Company
- **Create:** `Dealer__c`
- **Purpose:** Track dealers.

---

#### Healthcare Company
- **Create:**
    - `Hospital__c`
    - `Patient__c`
    - `Doctor__c`
- **Purpose:** Store healthcare-related information.

---

### Difference 1 — Deletion

#### Standard Object
- ❌ Cannot be deleted
- Salesforce protects built-in objects.
- *Example:* You cannot delete `Account`.

---

#### Custom Object
- ✅ Can be deleted
- *Example:* `Employee__c`
- Delete option is available under Object Manager.

**Important:**
You may stop using standard objects by removing their tabs from visibility, but you cannot delete them.

---

### Difference 2 — Grant Access Using Hierarchies

This controls record access through the organizational role hierarchy.

**Setting:**
`Grant Access Using Hierarchies`

#### Standard Objects
- ❌ Cannot modify
- Default behavior is already enabled and cannot be unchecked.

---

#### Custom Objects
- ✅ Can enable or disable
- **Location:** `Setup → Sharing Settings → Edit`
- This checkbox is configurable for custom objects.

*(Note: Details are covered later under Profiles and Roles.)*

---

### Difference 3 — Truncate Operation

#### What is Truncate?
Truncate removes all records from an object while keeping the object structure (fields, layouts, etc.) intact.

**Example:**

*Before:*
`Employee__c` → 100 Records

*After Truncate:*
`Employee__c` → 0 Records (Object still exists)

---

#### Standard Object
- ❌ Cannot truncate

---

#### Custom Object
- ✅ Supports truncate
- Must enable the setting first via:
  `Setup → User Interface → Enable Custom Object Truncate`

---

### Difference 4 — Fields Behavior

#### Standard Objects
You can create:
- ✅ Custom Fields
- *Example:* `Account` (standard) + `Industry__c` (custom)

---

#### Custom Objects
Automatically include standard system fields such as:
- Created By
- Owner
- Last Modified By
- Name

These fields are added automatically by Salesforce.

---

### Difference 5 — Naming Convention

Custom Objects follow a specific API naming convention.

**Rule:**
`ObjectName__c`

**Example:**
- `Employee__c`
- `Dealer__c`
- `Patient__c`

**Meaning:**
`__c` = Custom

---

### API Name vs Label

#### Label
User-friendly display name.

**Example:**
`Employee`

---

#### API Name
Internal technical identifier.

**Example:**
`Employee__c`

**Used in:**
- Code (Apex/LWC)
- Automation (Flows)
- Integrations

---

### Standard Object vs Custom Object — Quick Comparison Table

| Feature | Standard Object | Custom Object |
| --- | --- | --- |
| **Delete Object** | ❌ Cannot delete | ✅ Can delete |
| **Grant Access Using Hierarchies** | ❌ Cannot change setting | ✅ Can change setting |
| **Truncate Object** | ❌ Cannot truncate | ✅ Can truncate |
| **Fields Behavior** | ✅ Can create custom fields | ✅ Automatically includes standard fields (Name, Created By, Last Modified By, Owner) |
| **Naming Convention** | No special suffix | Ends with **`__c`** |
| **Created By** | Salesforce | Admin / Developer |
| **Purpose** | General CRM functionality | Business-specific requirements |
| **Examples** | Account, Lead, Contact, Opportunity | Employee__c, Dealer__c, Hospital__c |

### Quick Memory Trick
```
Standard → Built by Salesforce → Fixed Structure
Custom → Built by Business → Flexible Structure
```

### Certification Shortcut
```
Delete → Custom Only
Truncate → Custom Only
Hierarchy Setting → Custom Only
__c Suffix → Custom Only
```

---

## Steps / Process

### Delete Custom Object

1. Open **Setup**
2. Open **Object Manager**
3. Select the custom object (e.g., `Employee__c`)
4. Click **Delete** from the action dropdown

---

### Configure Sharing Access

1. Open **Setup**
2. Go to **Sharing Settings**
3. Click **Edit**
4. Configure hierarchy access for custom objects

---

### Enable Truncate

1. Open **Setup**
2. Search for **User Interface** in Quick Find
3. Check **Enable Custom Object Truncate**
4. Click **Save**

---

## Important Terms

| Term | Meaning |
| --- | --- |
| **Standard Object** | Prebuilt Salesforce object |
| **Custom Object** | User-created object |
| **Truncate** | Remove records but keep object |
| **Grant Access Using Hierarchies** | Access inherited through hierarchy |
| **API Name** | Internal object identifier |
| **Label** | Display name |
| **Custom Field** | User-created field |
| **__c** | Custom object identifier |

---

## Commands / Syntax / Configuration

### Sharing Settings
```
Setup → Sharing Settings
```

### Enable Truncate
```
Setup → User Interface → Enable Custom Object Truncate
```

### Open Object Manager
```
Setup → Object Manager
```

### Custom Object Naming
- `Employee__c`
- `Hospital__c`
- `Dealer__c`

---

## Examples

### Example 1 — Standard Object
- **Requirement:** Track customers
- **Use:** `Account`

---

### Example 2 — Custom Object
- **Requirement:** Track hospitals
- **Create:** `Hospital__c`

---

### Example 3 — Truncate
- **Requirement:** Delete all employee records quickly while keeping the object structure.
- **Use:** Truncate `Employee__c` (object remains).

---

## Certification Focus

### Important for Exam

Memorize:

| Feature | Standard | Custom |
| --- | --- | --- |
| Delete | ❌ | ✅ |
| Truncate | ❌ | ✅ |
| Hierarchy Access Configurable | ❌ | ✅ |
| Ends with `__c` | ❌ | ✅ |

Know:
`API Name ≠ Label`

---

### Common Mistakes

- Thinking standard objects can be deleted
- Forgetting `__c` suffix when referencing custom objects
- Confusing truncate with delete object
- Assuming hierarchy access is configurable for standard objects

### Remember

```
Standard = Salesforce Created
Custom = Business Requirement Created
```

---

## Real-World Application

| Business | Custom Object |
| --- | --- |
| Car Dealer | `Dealer__c` |
| Hospital | `Patient__c` |
| Education | `Student__c` |
| HR | `Employee__c` |

Companies combine **Standard CRM Objects** with **Custom Business Objects**.

---

## Quick Revision (30 sec)

- Standard Objects → Built-in
- Custom Objects → User-created
- Standard Objects cannot be deleted
- Custom Objects can be deleted
- Truncate → Custom only
- Hierarchy access configurable → Custom only
- Custom Objects end with `__c`
- Standard objects support custom fields
- Custom objects include system fields
- API Name is used internally