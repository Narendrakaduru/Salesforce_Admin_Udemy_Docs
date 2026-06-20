# Lesson 4 — Salesforce Lightning UI Overview

## Lesson Summary

This lesson provides a walkthrough of the **Salesforce Lightning User Interface (Lightning UI)**. It explains how to navigate Salesforce using **App Launcher, Setup, Quick Find, Applications, Tabs, Users, and Profiles**. The lecture also introduces standard Salesforce data and profiles that come preconfigured inside a Developer Org.

---

## Key Points

- **Lightning UI** is Salesforce's modern user interface.
- **App Launcher (9 dots)** is used to access applications.
- Applications contain multiple **Tabs**.
- Tabs provide access to **Objects** and their records.
- Salesforce provides **sample data** and **standard profiles**.
- **Quick Find** is used to search configuration items.
- Every **User** must have exactly **one Profile**.
- Profiles determine **visibility and access control**.
- Standard profiles can be **cloned** to create custom profiles.

---

## Detailed Notes

### What is Salesforce Lightning UI?

Salesforce Lightning UI is the modern interface used to:
- Navigate applications
- Access records
- Configure settings
- Manage users
- Customize the platform

After login, users land on the **Home Page**.

---

### Logging into Salesforce

To access Salesforce, go to:
`login.salesforce.com`

**Required:**
- Username
- Password

After successful login:
- Home page opens
- Lightning UI loads

---

### Quick Find

Quick Find is Salesforce's internal search tool.

**Purpose:**
- Search setup options quickly
- Locate users
- Open profiles
- Find configuration items

**Example searches:**
- Users
- Profiles
- Email
- Objects

**Key Idea:**
- You do not need to memorize where settings exist.

---

### App Launcher (9 Dots)

The **App Launcher** allows users to switch applications.

**Location:**
Top-left navigation area.

**Functions:**
- View available apps
- Switch between apps
- Search tabs and applications

**Examples of standard apps:**
- Sales
- Service
- Marketing
- Community
- Console

**Navigation:**
```
App Launcher → View All → Select Application
```

---

### Applications and Tabs

Applications consist of multiple tabs.

**Examples:**

#### Sales App
Contains:
- Accounts
- Opportunities
- Leads
- Tasks

#### Service App
Contains:
- Accounts
- Contacts
- Cases

**Important:**
- Some tabs can exist in multiple applications.

**Relationship:**
```
Application
     ↓
Multiple Tabs
     ↓
  Objects
```

---

### Accessing Tabs Directly

You can access tabs by:

**Method 1:**
- Open App
- Select tab

**Method 2:**
- Search in App Launcher

**Example:**
```
Search → Accounts
Search → Cases
Search → Contacts
```

---

### Salesforce Sample Data

Developer Accounts are not empty.

Salesforce provides:
- Existing objects
- Sample records
- List views

**Examples:**
- Accounts records
- Contacts records
- Cases data

**Purpose:**
- Help users practice immediately

---

### Setup Menu

Setup is the administration area.

**Access:**
```
Gear Icon → Setup
```

**Purpose:**
- Configure Salesforce
- Manage users
- Create profiles
- Control applications

Quick Find inside Setup allows searching configurations.

---

### Users in Salesforce

Users represent people who access Salesforce.

**Navigate:**
```
Setup → Users → Users
```

Each user record contains:
- Name
- Username
- Profile

**Example:**
Developer account automatically receives a user.

---

### Profiles

Profiles determine **what users can access**.

Profiles control:
- Application visibility
- Object access
- User permissions

**Rule:**
- One User → One Profile
- One Profile → Multiple Users

**Example:**
System Administrator Profile

**Access:**
- Applications
- Objects
- Administration

---

### Standard Profiles vs Custom Profiles

Salesforce provides built-in profiles.

**Examples:**
- System Administrator
- Standard User
- Community User

**Limitations:**
- Standard profiles have restricted editing.

**Best Practice:**
- Create custom profiles by cloning.

---

### Clone Profile

**Purpose:**
- Duplicate existing profile
- Modify permissions

**Process:**
```
Profiles → Clone → Create Custom Profile
```

---

## Steps / Process

### Switch Applications

1. Open App Launcher
2. Select View All
3. Choose application

---

### Search Configuration

1. Click Gear Icon
2. Open Setup
3. Use Quick Find

---

### View User Profile

1. Setup
2. Users
3. Open User
4. View Profile

---

### Create Custom Profile

1. Setup
2. Profiles
3. Select Standard Profile
4. Click Clone
5. Modify settings
6. Save

---

## Important Terms

| Term | Meaning |
| --- | --- |
| **Lightning UI** | Modern Salesforce interface |
| **App Launcher** | Tool for switching applications |
| **Quick Find** | Search utility inside Setup |
| **Application** | Collection of tabs |
| **Tab** | Navigation entry for objects |
| **User** | Account accessing Salesforce |
| **Profile** | Controls visibility and permissions |
| **System Administrator** | Highest standard access profile |
| **Clone** | Copy an existing profile |

---

## Commands / Syntax / Configuration

### Login
```
login.salesforce.com
```

### Open Setup
```
Gear Icon → Setup
```

### Open Users
```
Setup → Users → Users
```

### Open Profiles
```
Setup → Profiles
```

### Clone Profile
```
Profiles → Clone
```

---

## Examples

### Example 1 — Switch Application

Open:
`Sales → Service`

Tabs update automatically.

---

### Example 2 — Search Object

Search:
```
Accounts
```
Salesforce directly opens the Accounts tab.

---

### Example 3 — Profile Assignment

- **User:** Deepika
- **Profile:** System Administrator

---

## Certification Focus

### Important for Exam

- **App Launcher = Application navigation**
- **Quick Find = Setup search**
- **One User → One Profile**
- **One Profile → Multiple Users**
- Profiles control **visibility and permissions**
- Standard profiles are commonly **cloned**

### Common Mistakes

- Confusing App Launcher with Setup
- Thinking apps and objects are identical
- Assuming users can have multiple profiles
- Editing standard profiles directly

### Remember

```
Application → Tabs → Objects
User → Profile → Access
```

---

## Real-World Application

Admins use Lightning UI daily to:
- Manage users
- Configure permissions
- Navigate applications
- Customize business processes
- Create access controls

**Example:**
- Sales Team → Sales App
- Support Team → Service App
- Admin → Setup & Profiles

---

## Quick Revision (30 sec)

- Login → `login.salesforce.com`
- Lightning UI = Main interface
- App Launcher = Switch apps
- Apps contain tabs
- Tabs access objects
- Quick Find searches Setup
- Setup controls Salesforce
- User must have one profile
- Profiles define access
- Clone standard profiles for customization