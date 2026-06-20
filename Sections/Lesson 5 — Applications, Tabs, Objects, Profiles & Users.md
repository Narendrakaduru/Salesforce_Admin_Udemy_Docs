# Lesson 5 — Salesforce Architecture Recap: Applications, Tabs, Objects, Profiles & Users

## Lesson Summary

This lesson provides a **visual recap of Salesforce architecture** and explains the relationship between **Applications, Tabs, Objects, Profiles, and Users**. The lecture reinforces how Salesforce organizes data and how **profiles control application visibility and access permissions**. It also demonstrates practically how changing profile settings immediately changes what users can see.

---

## Key Points

- Salesforce provides multiple **Applications** (Sales, Service, Marketing, etc.).
- Applications are collections of **Tabs**.
- Tabs are access points to **Objects**.
- Objects behave similarly to **database tables**.
- Profiles control:
    - Application visibility
    - Object access
    - User permissions
- One **User** can have **only one Profile** at a time.
- One **Profile** can be assigned to **multiple Users**.
- Changes made to profiles immediately affect user access.

---

## Detailed Notes

### Salesforce Architecture Overview

Salesforce organizes components in layers.

**Architecture Flow:**
```
Applications
     ↓
   Tabs
     ↓
  Objects
     ↓
  Records
```

**Access Control:**
```
Profiles
   ↓
 Users
```

---

### Applications in Salesforce

Salesforce comes with predefined applications.

**Examples:**
- **Sales Application**
- **Marketing Application**
- **Service Application**
- Additional standard applications

Applications group business functionality together.

---

### Tabs Inside Applications

Each application contains multiple tabs.

**Example:**

#### Sales Application
Contains:
- Accounts
- Contacts
- Opportunities

#### Service Application
Contains:
- Cases
- Accounts
- Other service-related tabs

**Important:**
- Some tabs may appear across multiple applications.

---

### Objects = Tables

Tabs represent access to underlying objects.

**Object characteristics:**
- Store data
- Similar to database tables

**Examples:**
- `Accounts` → Object
- `Contacts` → Object
- `Opportunities` → Object
- `Cases` → Object
- `Leads` → Object

Inside objects:
- Data is stored as records

**Example:**
```
Lead Object
     ↓
Multiple Records
```

---

### Profiles Control Visibility

Profiles determine what users can access.

**Profiles control:**
- Applications
- Objects
- Fields
- Permissions
- Visibility

**Example:**

**Profile:**
System Administrator

**Can control:**
- Sales App
- Service App
- Marketing App
- Object permissions

---

### Relationship Between Users and Profiles

This is one of the most important concepts.

**Relationship:**
- One User → One Profile
- One Profile → Multiple Users

**Example:**

**Users:**
- Akshay
- Sanjay
- Madhuri

All users may share:
```
System Administrator Profile
```

But, Akshay cannot have:
```
System Admin + Standard User
```
at the same time.

---

### Practical Profile Visibility Example

- **Current User:** Deepika
- **Assigned Profile:** System Administrator

Because of that profile:
- Service App visible
- Sales App visible
- Marketing App visible

---

### Removing Application Access

If access is removed from a profile:

**Example:**
Remove:
- Service
- Sales
- Marketing
- Sales Console

**Effect:**
User immediately loses access.

**Important Flow:**
```
Profile change
      ↓
User experience changes
```
No direct modification is required on the user record itself.

---

### Restoring Access

If profile permissions are restored:
- Applications become visible again.

This proves:
```
User visibility = Profile permissions
```

---

## Steps / Process

### View User Profile

**Navigate:**
1. Go to `Setup → Users → Users`
2. Select the specific **User**
3. View the assigned **Profile**

---

### Modify Application Visibility

**Navigate:**
1. Go to `Setup → Profiles`
2. Select the specific **Profile**
3. Click **Edit**
4. Under **Application Settings**, modify visibility (e.g., remove access)
5. Save changes
6. Refresh the user's browser page

**Result:**
The application disappears from the user's view.

---

### Restore Visibility

**Navigate:**
1. Open the specific **Profile**
2. Click **Edit**
3. Enable the desired applications
4. Save changes

---

## Important Terms

| Term | Meaning |
| --- | --- |
| **Application** | Collection of tabs |
| **Tab** | Navigation entry to an object |
| **Object** | Salesforce table |
| **Record** | Individual data entry |
| **Profile** | Controls visibility and permissions |
| **User** | Individual Salesforce account |
| **System Administrator** | Standard profile with broad access |
| **Visibility** | Determines what users can access |

---

## Commands / Syntax / Configuration

### Open Users
```
Setup → Users → Users
```

### Open Profiles
```
Setup → Profiles
```

### Edit Profile Access
```
Profiles → Select Profile → Edit → Application Visibility
```

### Architecture Mapping
```
Application
     ↓
   Tabs
     ↓
  Objects
     ↓
  Records
```

### User Assignment Model
- One User → One Profile
- One Profile → Multiple Users

---

## Examples

### Example 1 — Sales Application

- **Application:** Sales
- **Contains Tabs:** Accounts, Contacts, Opportunities

---

### Example 2 — Restrict User Access

- **User:** Deepika
- **Profile:** System Administrator
- **Action:** Remove Sales App access
- **Result:** Sales application disappears from the interface.

---

### Example 3 — Shared Profile

- **Users:** Akshay, Sanjay, Madhuri
- **All use:** System Administrator

---

## Certification Focus

### Important for Exam

Memorize:
```
Application → Tabs → Objects
```

Remember:
- `Object = Table`

Critical Rules:
- **One User → One Profile**
- **One Profile → Multiple Users**

Profiles control:
- Visibility
- Access
- Permissions

### Common Mistakes

- Thinking tabs store data
- Confusing tabs with objects
- Assigning multiple profiles to one user
- Expecting profile changes to affect only one user (it affects all users assigned to that profile)

### Remember

```
Profiles decide WHAT users see.
Users decide WHO logs in.
Objects store DATA.
```

---

## Real-World Application

Companies use profiles to:
- Give the Sales team access only to the Sales App
- Restrict HR records from general staff
- Hide Finance applications from non-finance users
- Allow admins to manage everything

**Example:**

| Role | Access |
| --- | --- |
| Sales User | Sales App |
| Support User | Service App |
| Admin | Full Access |

---

## Quick Revision (30 sec)

- Salesforce has multiple applications
- Apps contain tabs
- Tabs connect to objects
- Objects store records
- Profiles control visibility
- Users receive profiles
- One user → one profile
- One profile → many users
- Removing app access changes UI immediately
- `Setup → Profiles` controls permissions