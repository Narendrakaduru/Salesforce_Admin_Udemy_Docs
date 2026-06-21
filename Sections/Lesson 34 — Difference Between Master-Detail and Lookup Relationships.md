# Lesson 34 — Difference Between Master-Detail and Lookup Relationships

Source transcript and lesson content referenced from uploaded notes.

## Lesson Summary

In this lesson, we learn about **Master-Detail Relationship** and compare it with **Lookup Relationship**.

In previous lessons, we created **Lookup Relationships**:
- Job Application → Position
- Job Application → Candidate

Those were loosely connected relationships.

Now we introduce **Master-Detail Relationship**, which is a stronger relationship model in Salesforce where the child record depends heavily on the parent.

This lesson focuses on:
- Understanding Master-Detail Relationship
- Understanding Roll-Up Summary fields
- Comparing Lookup vs Master-Detail
- Understanding Ownership and Cascade Delete

---

## Key Points

- Both are **One-to-Many Relationships**
- Lookup → Loose coupling
- Master-Detail → Strong coupling
- Roll-Up Summary only works with Master-Detail
- Child ownership behaves differently
- Parent deletion behavior changes

---

## Relationship Types

```mermaid
flowchart LR
    ONE["Parent (One)"]
    MANY["Child (Many)"]
    ONE --> MANY
```

Salesforce supports:
- Lookup Relationship
- Master-Detail Relationship

---

## What is Lookup Relationship?

A **Lookup Relationship** is a loosely connected relationship.

Child records can exist independently.

Example:
`Candidate → Job Application`

Even if Candidate is deleted:
`Job Application remains`

---

## What is Master-Detail Relationship?

A **Master-Detail Relationship** is a strongly connected relationship.

If parent is deleted:

```
Parent Deleted
↓
Child Records Deleted Automatically
```

This is called:
`Cascade Delete`

Example:
```
Employee
↓
PTO (Paid Time Off)
```

If employee leaves company:
```
Employee deleted
↓
PTO records deleted
```
because PTO has no meaning without Employee.

---

## Roll-Up Summary Field

One major advantage of Master-Detail:
`Roll-Up Summary Field`

This field can:
- Count child records
- Sum values
- Find Min values
- Find Max values

Example:
```
Employee
↓
Total PTO Days
```

Salesforce automatically calculates:
`Total PTO Taken`

Important:
`Roll-Up Summary exists ONLY on Master Object`

---

## Relationship Field Placement Rule

Always remember:
```
Relationship Field
↓
Placed on Child Object
```

Example:
```
Employee (Master)
↓
PTO (Detail)
```

Relationship field goes on:
`PTO`

---

## Difference Table — Lookup vs Master-Detail

| Lookup Relationship | Master-Detail Relationship |
| --- | --- |
| Loosely coupled | Strongly coupled |
| Roll-Up Summary cannot be created | Roll-Up Summary can be created |
| Parent record not required while creating child | Parent always required |
| Lookup field not mandatory | Relationship field mandatory |
| Standard object can be child of custom object | Standard object cannot be child |
| Child ownership independent | Parent controls child ownership |
| Child can exist without parent | Child cannot exist without parent |
| Maximum **40 Lookup Relationships** per object | Maximum **2 Master-Detail Relationships** per object |
| No Cascade Delete | Cascade Delete available |

---

## Detailed Comparison

### 1. Coupling

#### Lookup
`Objects work independently`

Example:
```
Candidate
↓
Job Application
```

Delete Candidate:
`Job Application still exists`

#### Master-Detail
`Child depends completely on Parent`

Delete Employee:
`PTO deleted`

---

### 2. Roll-Up Summary

#### Lookup
❌ Not available

#### Master-Detail
✅ Available

Example:
```
Employee
↓
Count PTO Requests
```

---

### 3. Parent Requirement

#### Lookup
Parent optional.

Example:
```
Create Job Application
↓
Position optional
```

#### Master-Detail
Parent mandatory.

Example:
`Cannot create PTO without Employee`

---

### 4. Ownership

#### Lookup
`Child Owner ≠ Parent Owner`

Separate ownership.

#### Master-Detail
```
Parent Owner
↓
Child Owner inherited
```

Owner field disappears from child.

Manual sharing:
❌ Not available

Queues:
❌ Not available

Sharing Rules:
❌ Not available

---

### 5. Delete Behavior

#### Lookup
```
Delete Parent
↓
Child survives
```

#### Master-Detail
```
Delete Parent
↓
Delete Child
```

---

## Example Scenarios

### Use Lookup When
- Candidate ↔ Job Application
- Position ↔ Hiring Manager
- Contact ↔ Referral

### Use Master-Detail When
- Order ↔ Order Items
- Invoice ↔ Invoice Lines
- Employee ↔ PTO

---

## Certification Focus

> [!IMPORTANT]
> **Important for Exam**
>
> Remember:
> - `Lookup = Flexible`
> - `Master Detail = Dependent`
> 
> Roll-Up Summary:
> - `Master Only`
> 
> Relationship Field:
> - `Always on Child`
> 
> Maximum Limits:
> - `Lookup → 40`
> - `Master Detail → 2`

### Common Mistakes
❌ Expecting Roll-Up Summary in Lookup
❌ Creating child without parent in Master-Detail
❌ Assuming child ownership exists in Master-Detail
❌ Forgetting Cascade Delete

---

## Real-World Application

Companies use:

Lookup:
`Employee → Manager`

Master Detail:
`Order → Order Items`

This helps:
- Maintain data integrity
- Automate totals
- Control sharing
- Remove orphan records

---

## Quick Revision (30 sec)

- Lookup = Loosely Coupled
- Master-Detail = Strongly Coupled
- Roll-Up Summary → Master only
- Parent required in Master-Detail
- Child ownership inherited
- Lookup supports independent records
- Master supports Cascade Delete
- Relationship field always goes on Child Object