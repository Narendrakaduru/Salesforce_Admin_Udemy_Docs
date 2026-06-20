# Lesson 3 — Salesforce Architecture, Objects, Fields, Records & Profiles

## Lesson Summary

This lesson introduces the **basic architecture of Salesforce** and explains how Salesforce organizes data. The lecture compares Salesforce with a traditional table structure (similar to spreadsheets or databases) and maps those concepts into Salesforce terminology. It also introduces **Applications, Objects, Tabs, Users, and Profiles**, showing how Salesforce controls visibility and access.

---

## Key Points

- Salesforce stores data using **Objects, Fields, and Records**
- Traditional database concepts map into Salesforce architecture:
    - Table → **Object**
    - Column → **Field**
    - Row → **Record**
- Multiple **Objects** together form an **Application**
- **Tabs** provide easy access to Objects
- **Profiles** control user permissions and visibility
- One **Profile** can be assigned to multiple users
- **System Administrator** profile has the highest access

---

## Detailed Notes

### Understanding Salesforce Architecture

Salesforce organizes data similarly to traditional databases.

**Example:**
If you maintain employee details in a spreadsheet or database:

| Traditional Database | Salesforce |
| --- | --- |
| Table | **Object** |
| Column | **Field** |
| Row | **Record** |

---

### Object = Table

An **Object** stores information.

**Example:**
Employee Object

Stores:
- Employee Name
- Salary
- Designation
- Address

Each category becomes a field.

**Example:**

| Employee Name | Salary | Designation |
| --- | --- | --- |
| John | 50000 | Developer |
| Steve | 70000 | Manager |

Entire structure → **Object**

---

### Field = Column

Fields store individual pieces of information.

**Examples:**
- Account Name
- Parent Account
- Account Number
- Employee Salary
- Address

Fields define **what data can be stored**.

---

### Record = Row

A **Record** is an individual entry inside an object.

**Examples:**
- John → Record
- Steve → Record

Every new row inserted becomes a new Salesforce record.

---

### Applications in Salesforce

An **Application (App)** is a collection of related objects.

**Examples:**
- Sales App
- Call Center App

Each application groups related business functionality.

**Example:**

**Sales Application:**
- Accounts
- Opportunities
- Contacts

**Call Center Application:**
- Home
- Chatter
- Accounts

---

### Tabs in Salesforce

Tabs provide quick navigation to objects.

**Important:**
- Every object is typically associated with a **Tab**
- Tabs make object access easier

**Examples:**
- Accounts Tab
- Opportunities Tab
- Contacts Tab

**Concept:**
- Object → Accessed through Tab
- Multiple Tabs → Form an Application

---

### Profiles in Salesforce

Profiles define **what users can access**.

Profiles control:
- Applications visible
- Objects accessible
- Tabs visible
- User permissions
- Data visibility

**Example:**

#### CEO Profile
Can access:
- Reports
- Employee Data
- Salaries
- Administrative features

#### Employee Profile
Can access:
- Limited business functions
- Assigned applications only

---

### System Administrator Profile

This is Salesforce's highest privilege profile.

**Capabilities:**
- Access all applications
- Manage users
- Configure settings
- Control visibility
- Modify profiles

---

### User and Profile Relationship

Each user receives **one profile**.

**Relationship:**
- One Profile → Multiple Users
- One User → One Profile

Users sharing the same profile:
- Have similar permissions
- See similar application areas

---

## Steps / Process

### How to Check User Profiles in Salesforce

#### Step 1
Open **Setup**

#### Step 2
Navigate to:
`Setup → Users → Users`

#### Step 3
Open the desired user record.

#### Step 4
View the assigned **Profile**.

#### Step 5
Open the profile to manage:
- Applications
- Tabs
- Permissions
- Visibility

---

### Example of Controlling Application Visibility

An Administrator can:
1. Open Profile
2. Edit Application Visibility
3. Remove access to Call Center App
4. Save changes
5. The user no longer sees that application.

---

## Important Terms

| Term | Meaning |
| --- | --- |
| **Object** | Salesforce equivalent of a database table |
| **Field** | Individual data column |
| **Record** | Single row of data |
| **Application (App)** | Collection of related objects |
| **Tab** | Navigation access to an object |
| **Profile** | Controls user permissions and visibility |
| **User** | Individual account accessing Salesforce |
| **System Administrator** | Profile with maximum access |

---

## Commands / Syntax / Configuration

### Navigate to Users
```
Setup → Users → Users
```

### Profile Visibility Concept
```
Profile
 ├── Applications
 ├── Objects
 ├── Tabs
 └── Permissions
```

### Relationship Model
```
Object → Tab → Application
User → Profile
```

---

## Examples

### Example 1 — Employee Table

**Traditional Database:**

| First Name | Salary |
| --- | --- |
| John | 50000 |

**Salesforce:**
- Object → Employee
- Fields → First Name, Salary
- Record → John

---

### Example 2 — Access Restriction

**Profile:**
Employee

**Allowed:**
- Accounts

**Restricted:**
- Reports
- Administration

---

## Certification Focus

### Important for Exam

Memorize this mapping:
- Table → Object
- Column → Field
- Row → Record

Know the difference:
- Tab ≠ Object
- Tab = Access mechanism for Object

Remember:
- Profile controls access
- NOT Object ownership

### Common Mistakes

- Confusing **Object** and **Tab**
- Thinking profiles are assigned to applications instead of users
- Assuming each user must have a unique profile

### Remember

**Objects store data → Tabs access objects → Apps group tabs → Profiles control access**

---

## Real-World Application

Companies use profiles to:
- Restrict employee access
- Separate HR and Finance visibility
- Give managers broader permissions
- Protect sensitive business information

**Example:**
- HR → Employee Records
- Sales → Opportunities
- CEO → Reports and dashboards

---

## Quick Revision (30 sec)

- Table = **Object**
- Column = **Field**
- Row = **Record**
- Multiple Objects = **Application**
- Tabs provide object access
- Profiles control permissions
- Users receive profiles
- One profile → Multiple users
- System Administrator → Highest access
- Setup → Users → Users → Profile