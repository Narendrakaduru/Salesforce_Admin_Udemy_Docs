# Lesson 12 — Create Fields Using Schema Builder (Date Fields, Picklist & Page Layout)

## Lesson Summary

In this lesson, we continue building the **Position Object** and introduce a faster way of creating fields using **Schema Builder**. Instead of creating fields one-by-one through Object Manager, Schema Builder allows visual field creation. We create multiple fields including **Open Date, Hire By, Close Date, and Location**, and learn an important concept: **fields created through Schema Builder are NOT automatically added to Page Layout** and must be added manually.

---

## Key Points

- Fields can be created faster using **Schema Builder**.
- Added fields:
    - Open Date
    - Hire By
    - Close Date
    - Location
- Date fields provide a calendar selection popup.
- Location uses a **Picklist** (dropdown list).
- Schema Builder does not support every field type (e.g., Geolocation).
- **Geolocation** must be created through Object Manager.
- Fields created through Schema Builder must be manually added to the Page Layout.
- Field-Level Security can be adjusted after creation.

---

## Navigation — Open Schema Builder

**Navigation Path:**
```
Gear Icon → Setup → Quick Find → Schema Builder
```

**Alternative Navigation:**
```
Setup → Object Manager → Schema Builder
```

**Purpose:**
- Create fields visually
- View object schemas and relationships
- Design data models quickly using drag-and-drop

---

## Detailed Notes

### Why Use Schema Builder?

Schema Builder provides a faster way to create fields.

**Advantages:**
- Much faster than stepping through the Object Manager wizard.
- Visual, drag-and-drop interface.
- Easy to view object structures and relationships.

**Disadvantages:**
- Not all field types are available for creation (e.g., Geolocation).
- Fields created are **not** automatically added to the Page Layout and must be positioned manually.

---

### Fields Added in This Lesson

| Field | Type | Purpose |
| --- | --- | --- |
| **Open Date** | Date | Position opening date |
| **Hire By** | Date | Hiring deadline |
| **Close Date** | Date | Position closing date |
| **Location** | Picklist | Position location |

---

## Steps / Process — Create Fields via Schema Builder

### Step 1 — Open Schema Builder

1. Navigate to: `Setup → Schema Builder`
2. In the left panel, search and select the **Position** object.

---

### Step 2 — Create Open Date Field

1. Select the **Elements** tab in the sidebar.
2. Find the **Date** field element and drag it onto the **Position** object box on the canvas.
3. Configure the following properties:

| Property | Value |
| --- | --- |
| **Field Label** | Open Date |
| **Field Name** | Open_Date *(Auto-generated)* |
| **Required** | No |
| **Default Value** | *Empty* |

4. Click **Save**.

**Result:**
The field `Open_Date__c` is created.

---

### Step 3 — Create Hire By Field

1. Drag the **Date** element onto the **Position** object box.
2. Configure:

| Property | Value |
| --- | --- |
| **Field Label** | Hire By |
| **Field Name** | Hire_By *(Auto-generated)* |
| **Required** | No |

3. Click **Save**.

**Result:**
The field `Hire_By__c` is created.

---

### Step 4 — Create Close Date Field

1. Drag the **Date** element onto the **Position** object box.
2. Configure:

| Property | Value |
| --- | --- |
| **Field Label** | Close Date |
| **Field Name** | Close_Date *(Auto-generated)* |

3. Click **Save**.

**Result:**
The field `Close_Date__c` is created.

---

### Step 5 — Create Location Field

1. Find the **Picklist** element under **Elements** and drag it onto the **Position** object box.
2. Configure:

| Property | Value |
| --- | --- |
| **Field Label** | Location |
| **Field Name** | Location *(Auto-generated)* |

3. **Values entered (separate by new line):**
```
San Francisco, California
New York
Dallas, Texas
Austin, Texas
Delhi, India
Mumbai, India
```

4. Leave default options (do **NOT** sort alphabetically; do **NOT** use first value as default).
5. Click **Save**.

**Result:**
The field `Location__c` is created.

---

## Schema Builder Limitations

Not every field type is available under the Schema Builder elements list.

**Example not supported:**
- **Geolocation**

Additional limited examples:
- Some advanced relationships.
- External lookup scenarios.

**When a field type is unsupported:**
Use the **Object Manager** to create the field instead.

---

## Navigation — Add Fields to Page Layout

> [!IMPORTANT]
> Fields created through Schema Builder are **not** automatically added to the Page Layout. You must add them manually.

**Navigation Path:**
```
Gear Icon (on Position record page) → Edit Object → Page Layouts → Position Layout
```
*OR*
```
Setup → Object Manager → Position → Page Layouts
```

---

## Steps / Process — Add Fields to Page Layout

1. Open **Position Layout**.
2. Locate the following fields in the top palette:
   - `Location`
   - `Open Date`
   - `Close Date`
   - `Hire By`
3. Drag and drop them into the desired sections of the layout.
4. Click **Quick Save** (or **Save**).

**Resulting Layout Structure:**
```
Position
 ├── Position Title
 ├── Status
 ├── Location
 ├── Open Date
 ├── Close Date
 └── Hire By
```

---

## Optional — Create Sections in Layout

**Navigation:**
Inside the page layout editor, drag the **Section** element down into the layout.

**Options:**

| Layout Type | Purpose |
| --- | --- |
| **One Column** | Vertical layout flow |
| **Two Column** | Side-by-side layout flow |

**Tab Key Order:**
- Left to Right
- Top to Bottom

**Purpose:**
Organizes large forms to improve user readability.

---

## Field-Level Security

Fields created through Schema Builder receive default visibility settings. To modify security:

**Navigation:**
```
Object Manager → Position → Fields & Relationships → Select Field → Set Field-Level Security
```

**Configure:**
- [x] Visible (to toggle visibility for specific profiles)
- [x] Read-Only (to lock the field values)

---

## Final Position Screen

After refreshing the browser:

**Navigate:**
`App Launcher → Recruiting → Position → New`

**Expected Fields Displayed:**
- Position Title
- Status
- Location (displays as a dropdown picklist: `▼ Picklist`)
- Open Date (displays with a calendar popup: `📅 Calendar popup`)
- Close Date (displays with a calendar popup: `📅 Calendar popup`)
- Hire By (displays with a calendar popup: `📅 Calendar popup`)

---

## Important Terms

| Term | Meaning |
| --- | --- |
| **Schema Builder** | Salesforce drag-and-drop tool to visually build the data model |
| **Date Field** | Field type designed for date inputs |
| **Picklist** | Dropdown list allowing a single value selection |
| **Page Layout** | Configuration defining layout of fields on the user interface |
| **Field-Level Security** | Security settings restricting field visibility based on user profile |
| **Quick Save** | Saves changes in page layout editor without closing the editor window |

---

## Commands / Syntax / Configuration

### Open Schema Builder
```
Setup → Schema Builder
```

### Add Field
```
Select Field → Drag to Object → Save
```

### Add Layout Fields
```
Page Layout → Drag → Quick Save
```

---

## Examples

### Example Position Layout Output

- **Position Title:** Salesforce Developer
- **Location:** Mumbai, India
- **Open Date:** 01/01/2026
- **Hire By:** 15/01/2026
- **Close Date:** 30/01/2026

---

## Certification Focus

### Important for Exam

- **Schema Builder = Fast Creation**
- **Schema Builder ≠ Auto Page Layout** (Fields created must be placed manually).
- **Picklist = Single Value**
- **Date = Calendar Input**

### Common Mistakes
- Expecting fields created in Schema Builder to show up in the UI automatically without editing the page layout.
- Forgetting to configure Field-Level Security for fields created via Schema Builder.
- Using Schema Builder to create unsupported fields like Geolocation.

### Remember
```
Create Field → Save → Add to Layout → Configure Security
```

---

## Real-World Application

Companies use Schema Builder to:
- Design database structures quickly.
- Build custom HR/recruiting applications.
- Prototype objects and relations visual diagrams.
- Visualize complex data models across standard and custom objects.

---

## Quick Revision (30 sec)

- Schema Builder enables rapid, visual object and field creation.
- Open Date, Hire By, Close Date, and Location fields were added.
- Geolocation fields are not supported in Schema Builder.
- Drag new fields manually onto the Position Page Layout.
- Edit Field-Level Security to manage profile visibility.
- Refresh the browser and click "New" to verify fields.