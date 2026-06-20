# Lesson 6 — Understanding Objects, Fields, Records & Schema Builder in Salesforce

## Lesson Summary

This lesson explains one of the **core concepts in Salesforce — Objects and Fields**. Salesforce stores information similarly to a database, where **Objects act like tables**, **Fields act like columns**, and **Records act like rows**. The lesson also introduces **Schema Builder** and **Object Manager**, which help visualize and manage Salesforce data structures.

---

## Key Points

- **Object = Table**
- **Field = Column**
- **Record = Row**
- Objects store related business data.
- Fields capture specific information inside an object.
- Records are actual stored entries.
- **Schema Builder** provides a visual representation of objects and relationships.
- **Object Manager** is used to manage and create objects.
- Objects can have relationships with other objects.

---

## Detailed Notes

### What are Objects in Salesforce?

An **Object** in Salesforce is equivalent to a **database table**.

**Purpose:**
- Store related business information
- Organize records
- Define structure of data

**Example:**
Employee information can be stored inside an Employee Object.

**Example Data Structure:**

| Employee Name | Email | Address | DOB | Salary |
| --- | --- | --- | --- | --- |

In Salesforce:
`Employee → Object`

Objects contain:
- Fields
- Records

---

### What are Fields?

Fields are equivalent to **columns** in a table.

**Fields define:**
- What information is stored
- Data format
- Structure

**Example Employee Fields:**
- Employee Name
- Email
- Address
- Date of Birth
- Salary

**Example Mapping:**

| Field | Purpose |
| --- | --- |
| Name | Employee Name |
| Email | Contact Email |
| DOB | Birth Date |
| Salary | Compensation |

---

### What are Records?

Records are equivalent to **rows**.

A record represents one complete entry.

**Example:**

| Name | Email |
| --- | --- |
| John Smith | john@example.com |

This entire row becomes a **Record**.

Every time a new entry is saved:
`→ New Record created`

---

### Salesforce Data Mapping

Memorize this mapping:

| Traditional Database | Salesforce |
| --- | --- |
| Table | **Object** |
| Column | **Field** |
| Row | **Record** |

This is a fundamental Salesforce concept.

---

### Viewing Objects in Salesforce

**Example:**
1. Open **Accounts Tab**
2. Open any account record.
3. Inside **Details**, you will see:
    - Account Name
    - Account Number
    - Industry
    - Address

Those values belong to fields.

**Mapping Visual:**
```
Account Object
     ↓
  Fields
     ↓
Record Values
```

---

### Creating a New Record

**Example shown in lecture:**
1. Navigate: `Accounts → New`
2. Provide values:
    - Account Name
    - Rating
    - Account Number
    - Account Type
    - Industry
    - Address
3. Save.

**Result:**
`New Account Record Created`

Total records increase.

---

### Schema Builder

Schema Builder provides a visual representation of Salesforce data.

**Purpose:**
- View objects
- View fields
- Understand relationships
- Visualize architecture

**Navigation:**
```
Setup → Quick Find → Schema Builder
```

Schema Builder shows:
- Objects
- Fields
- Relationships

---

### Understanding Schema Builder View

**Example:**
Account Object visual block:
```
Account
 ├── Name
 ├── Account Number
 ├── Account Site
 └── Account Source
```

Objects appear like visual tables. You can:
- Expand
- Collapse
- Move objects on canvas

---

### Relationships Between Objects

Schema Builder also displays relationships.

**Example:**
```
Opportunity
     │ (Lookup Relationship)
     ▼
  Account
```

**Meaning:**
Opportunity references Account. This connection appears visually.

*(Note: Details are covered later in the course.)*

---

### Object Manager

Object Manager is another interface to manage objects.

**Purpose:**
- View objects
- Create objects
- Configure fields
- Manage metadata

**Navigation:**
```
Setup → Object Manager
```

**Features:**
- Complete object list
- Object configuration
- Access Schema Builder

---

## Steps / Process

### Create a New Record

1. Open **Accounts Tab**
2. Click **New**
3. Enter field values
4. Save

**Result:**
Record created.

---

### Open Schema Builder

1. Open **Setup**
2. Search for **Schema Builder** in Quick Find
3. Select desired object(s)
4. View fields and relationships

---

### Open Object Manager

1. Open **Setup**
2. Go to **Object Manager** tab
3. Select desired object

---

## Important Terms

| Term | Meaning |
| --- | --- |
| **Object** | Salesforce table |
| **Field** | Salesforce column |
| **Record** | Salesforce row |
| **Schema Builder** | Visual object relationship tool |
| **Object Manager** | Object administration area |
| **Account Object** | Standard Salesforce business object |
| **Relationship** | Connection between objects |
| **Lookup Relationship** | Object reference relationship |

---

## Commands / Syntax / Configuration

### Open Schema Builder
```
Setup → Schema Builder
```

### Open Object Manager
```
Setup → Object Manager
```

### Create Record
```
Accounts → New → Save
```

### Data Structure
```
Object
 ├── Fields
 └── Records
```

---

## Examples

### Example 1 — Employee Object

- **Object:** Employee
- **Fields:** Name, Email, Salary
- **Record:** John Smith

---

### Example 2 — Account Object

- **Fields:** Account Name, Industry, Account Number
- **Record:** My Tutorial Rack

---

### Example 3 — Relationship

```
Opportunity → Lookup → Account
```

---

## Certification Focus

### Important for Exam

Memorize:
```
Table → Object
Column → Field
Row → Record
```

Know:
- Schema Builder → Visualization
- Object Manager → Management

Remember:
Objects contain:
- Fields
- Records

### Common Mistakes

- Calling fields "columns"
- Calling objects "tables" in Salesforce terminology
- Confusing records with fields
- Thinking Schema Builder stores data

### Remember

```
Object = Structure
Field = Data Type
Record = Actual Data
```

---

## Real-World Application

Companies use objects to store:
- Employees
- Customers
- Accounts
- Opportunities
- Cases

Schema Builder helps:
- Understand relationships
- Design applications
- Plan architecture

Object Manager helps:
- Administer business data models

---

## Quick Revision (30 sec)

- Object = Table
- Field = Column
- Record = Row
- Accounts is a standard object
- Fields define stored data
- Records contain values
- Schema Builder visualizes objects
- Object Manager manages objects
- Relationships connect objects
- Salesforce data is object-based