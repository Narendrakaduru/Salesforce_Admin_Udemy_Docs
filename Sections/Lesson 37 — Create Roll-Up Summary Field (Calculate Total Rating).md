# Lesson 37 — Create Roll-Up Summary Field (Calculate Total Rating)

## Lesson Summary

In this lesson, we create a **Roll-Up Summary Field** on the **Job Application Object** to automatically calculate the **Total Rating** received from all related Review records.

Previously, we created:
- **Review Object**
- **Master-Detail Relationship** between **Job Application → Review**
- **Rating field** on Review

Now we will use those Review ratings and calculate the overall score automatically.

This lesson introduces:
- Roll-Up Summary Fields
- SUM operation
- Master-Detail dependency
- Automatic calculation
- Read-only calculated values

---

## Business Requirement

Each Job Application receives multiple reviews from interviewers.

Example:

| Reviewer | Rating |
| --- | --- |
| Deepika | 8 |
| Simran | 7 |

Business wants:
`Total Rating = 15`

Instead of calculating manually every time, Salesforce should automatically calculate and display the total.

---

## Key Points

- Roll-Up Summary works only on **Master Objects**
- Requires **Master-Detail Relationship**
- Values update automatically
- Supports:
    - COUNT
    - SUM
    - MIN
    - MAX
- Roll-Up fields are **Read Only**

---

## Steps / Process — Create Roll-Up Summary Field

### Navigation — Create Roll-Up Summary Field

```
Gear Icon → Setup → Object Manager → Job Application → Fields & Relationships → New
```

---

### Why Roll-Up Summary Is Available Here

Relationship created earlier:
```
Job Application (Master)
↓
Review (Detail)
```

Because Job Application is the **Master Object**, Salesforce allows Roll-Up Summary.

If you try creating it on:
- Position
- Candidate
- Review

the option appears disabled.

---

### Step 1 — Create New Field

Navigate:
```
Setup → Object Manager → Job Application → Fields & Relationships → New
```

Select:
```
Roll-Up Summary
```

Click:
```
Next
```

---

### Step 2 — Configure Field

Enter:

| Property | Value |
| --- | --- |
| Field Label | Total Rating |
| Field Name | Total_Rating |
| Data Type | Roll-Up Summary |

Click:
```
Next
```

---

### Step 3 — Configure Roll-Up Settings

Choose:

| Setting | Value |
| --- | --- |
| Summarized Object | Reviews |
| Roll-Up Type | SUM |
| Field to Aggregate | Rating |
| Filter Criteria | All Records |

Meaning:
`Add all Review ratings for current Job Application`

Example:
```
Review 1 → 8
Review 2 → 7
Total = 15
```

Click:
```
Next
```

---

### Step 4 — Configure Security

Set:
```
Visible to: System Administrator
```

Click:
```
Next → Save
```

---

## How Roll-Up Summary Works

```
Job Application
↓
Get Related Reviews
↓
Read Rating Values
↓
SUM()
↓
Display Total Rating
```

---

## Example 1 — Two Reviews

Job Application:
`JA001`

Reviews:

| Reviewer | Rating |
| --- | --- |
| Deepika | 8 |
| Simran | 7 |

Calculation:
`8 + 7 = 15`

Result:
`Total Rating = 15`

---

## Example 2 — Rating Updated

Original:
`8 + 7 = 15`

Update:
`Reviewer changes 8 → 9`

New Calculation:
`9 + 7 = 16`

Salesforce automatically updates Total Rating.
No manual action required.

---

## Example 3 — Multiple Reviews

Job Application:
`JA003`

Reviews:

| Reviewer | Rating |
| --- | --- |
| Reviewer 1 | 5 |
| Reviewer 2 | 7 |
| Reviewer 3 | 5 |

Calculation:
`5 + 7 + 5 = 17`

Result:
`Total Rating = 17`

---

## Roll-Up Summary Operations

| Operation | Purpose |
| --- | --- |
| COUNT | Count child records |
| SUM | Add numeric values |
| MAX | Highest value |
| MIN | Lowest value |

Examples:
```
COUNT → Total Reviews
SUM → Total Rating
MAX → Highest Rating
MIN → Lowest Rating
```

---

## Important Concepts

### Read Only Field

Roll-Up Summary values cannot be edited.
Even System Administrator cannot manually change them.

---

### Automatic Recalculation

Salesforce recalculates when:
- Child record created
- Child record updated
- Child record deleted

---

## Important Limitation

Once Roll-Up Summary exists:
`Master-Detail`
cannot be converted into:
`Lookup Relationship`

because Lookup does not support Roll-Up Summary.

---

## Certification Focus

> [!IMPORTANT]
> **Important for Exam**
>
> Remember:
> `Roll-Up Summary = Master Object Only`
> `Lookup Relationship = Not Supported`
>
> Supported operations:
> `COUNT`
> `SUM`
> `MIN`
> `MAX`

### Common Mistakes
❌ Creating Roll-Up Summary on child object
❌ Using Text fields in SUM
❌ Expecting editable values
❌ Forgetting Master-Detail requirement

---

## Real-World Applications

Roll-Up Summary is commonly used for:
- Total Interview Score
- Total Order Amount
- Number of Applications
- Employee PTO Totals
- Candidate Evaluation Score

---

## Quick Revision (30 sec)

- Created Total Rating field
- Used Roll-Up Summary
- Applied SUM on Rating
- Calculated child record values
- Auto-updated values
- Read-only field
- Works only with Master-Detail relationship