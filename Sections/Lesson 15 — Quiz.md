# Lesson 15 — Quiz Answers: Salesforce Field Types

## Lesson Summary

This lesson contains quiz questions and detailed explanations covering **Salesforce Field Types**. It reviews key concepts for the certification exam, including time-based field types, single vs. multi-select picklists, and the differences in text field capacities (Text, Text Area, Long Text, and Rich Text).

---

## Key Points

- Use **Date** for dates only, **Time** for time only, and **Date/Time** for both date and time values.
- **Picklist** allows selecting a single value, whereas **Multi-select Picklist** allows selecting multiple predefined values.
- **Text Area (Long)** is ideal for storing large, multi-line text descriptions (up to 131,072 characters) on separate lines.

---

## Quiz Questions & Answers

### Question 1

**Which field type should be used to record opening and closing hours for store locations?**

✅ **Answer: Time**

#### Explanation

The **Time** field type stores a specific time value without dates.

**Examples:**
- Opening Time → 09:00 AM
- Closing Time → 06:00 PM

**Why other options are incorrect:**

| Option | Reason |
| --- | --- |
| **Time** | ✅ Stores only time values |
| Business Hours | ❌ Salesforce configuration feature (for support hours, SLAs, escalation rules), not a field type |
| Hours | ❌ Not a valid Salesforce field type |

**Exam Tip:**
- Use **Date** → for calendar dates only (e.g. `01/01/2026`)
- Use **Time** → for clock time only (e.g. `09:00 AM`)
- Use **Date/Time** → for both date and time (e.g. `01/01/2026, 09:00 AM`)

---

### Question 2

**On a custom object in Salesforce, which allows a user to make multiple selections from a list of values?**

✅ **Answer: Multi-select picklist**

#### Explanation

A **Multi-select Picklist** allows users to choose **multiple predefined values** from a dropdown list.

**Example:**
- **Skills:**
  - [x] AWS
  - [x] Salesforce
  - [x] DevOps

**Why other options are incorrect:**

| Option | Reason |
| --- | --- |
| Multi-select checkbox | ❌ Not a valid Salesforce field type |
| Multi-select picklist | ✅ Allows multiple selections |
| Picklist | ❌ Allows only one selection |

**Exam Tip:**
- **Picklist** → Select exactly **one** value.
- **Multi-select Picklist** → Select **one or more** values.

---

### Question 3

**Need a field that stores up to 500 characters of text on separate lines. Which data type?**

✅ **Answer: Text Area (Long)**

#### Explanation

**Requirements:**
- Store **up to 500 characters**
- Support **multiple lines**

**Field Type Comparison:**

| Field Type | Supports Requirement |
| --- | --- |
| Text | ❌ Single line (max 255 characters) |
| Text Area | ❌ Multi-line, but smaller text capacity (max 255 characters) |
| Multi-Line Text | ❌ Not an actual Salesforce field type |
| Text Area (Long) | ✅ Multiple lines + large text capacity (up to 131,072 characters) |

**Example:**
```
Job Responsibilities:
- Salesforce administration
- User management
- Reporting
- Automation
```

**Exam Tip:**
- **Text** → Short single line (max 255 chars)
- **Text Area** → Multi-line (max 255 chars)
- **Long Text Area** → Large multi-line content (max 131,072 chars)
- **Rich Text Area** → Formatting (bold, italics, images) allowed (max 131,072 chars)
