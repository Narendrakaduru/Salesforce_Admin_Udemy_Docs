# Lesson 30 — Relationship Types in Salesforce (One-to-Many Relationship & Lookup Introduction)

## Lesson Summary

In this lesson, we start learning **Relationship Types in Salesforce**.

Previously, we identified that our Recruiting Application has two independent objects:
- Position
- Candidate

To connect related data, Salesforce provides **Object Relationships**.

This lesson focuses on:
- One-to-Many Relationship
- Parent and Child Objects
- Where Relationship Fields are created
- Introduction to Lookup Relationship
- Real-world relationship examples

---

## Key Points

- Relationships connect objects.
- One-to-Many is the most common relationship type.
- Parent = One side.
- Child = Many side.
- Relationship field is always created on the child object.
- Lookup Relationship is loosely coupled.

---

## Relationship Types Overview

Salesforce supports multiple relationship models.

```mermaid
flowchart TB
    REL["Salesforce Relationships"]
    REL --> OTM["One To Many"]
    REL --> MTM["Many To Many"]
    REL --> SELF["Self Relationship"]
```

This lesson starts with:
`One → Many Relationship`

---

## What Is One-to-Many Relationship?

One record can be associated with multiple records.

General form:
```
One Parent
↓
Multiple Child Records
```

---

## One-to-Many Architecture

```mermaid
flowchart LR
    PARENT["Parent (One)"]
    CHILD1["Child"]
    CHILD2["Child"]
    CHILD3["Child"]
    PARENT --> CHILD1
    PARENT --> CHILD2
    PARENT --> CHILD3
```

---

## Example 1 — Hiring Manager & Positions

Business Scenario:

A company has hiring managers.
One manager can manage multiple positions.
But one position can only have one manager.

Relationship:

```mermaid
flowchart LR
    MANAGER["Hiring Manager"]
    POSITION1["Position"]
    POSITION2["Position"]
    POSITION3["Position"]
    MANAGER --> POSITION1
    MANAGER --> POSITION2
    MANAGER --> POSITION3
```

### Parent vs Child

| Object | Type |
| --- | --- |
| Hiring Manager | Parent |
| Position | Child |

Relationship Field goes on:
`Position Object`

---

## Example 2 — Doctor & Patient

One doctor treats multiple patients.
One patient belongs to one doctor.

```mermaid
flowchart LR
    DOCTOR["Doctor"]
    PATIENT1["Patient"]
    PATIENT2["Patient"]
    PATIENT3["Patient"]
    DOCTOR --> PATIENT1
    DOCTOR --> PATIENT2
    DOCTOR --> PATIENT3
```

| Object | Role |
| --- | --- |
| Doctor | Parent |
| Patient | Child |

---

## Example 3 — Teacher & Students

```mermaid
flowchart LR
    TEACHER["Teacher"]
    S1["Student"]
    S2["Student"]
    S3["Student"]
    TEACHER --> S1
    TEACHER --> S2
    TEACHER --> S3
```

One teacher teaches many students.

---

## Example 4 — School & Students

```mermaid
flowchart LR
    SCHOOL["School"]
    STUDENT1["Student"]
    STUDENT2["Student"]
    STUDENT3["Student"]
    SCHOOL --> STUDENT1
    SCHOOL --> STUDENT2
    SCHOOL --> STUDENT3
```

| Object | Type |
| --- | --- |
| School | Parent |
| Student | Child |

---

## Recruiting Application Example

Business Requirement:

One Position receives multiple Job Applications.

Example:

```mermaid
flowchart LR
    POSITION["Salesforce Developer Position"]
    APP1["Application — John"]
    APP2["Application — Stacy"]
    APP3["Application — Jason"]
    POSITION --> APP1
    POSITION --> APP2
    POSITION --> APP3
```

Meaning:
- One Position → Many Applications
- One Application → One Position

---

## Most Important Rule

> [!IMPORTANT]
> **Relationship Field ALWAYS goes on Child Object.**

Rule:
`Relationship Field → Child Object`

Because:
Child stores the reference to Parent.

Examples:

| Parent | Child | Relationship Field Goes On |
| --- | --- | --- |
| School | Student | Student |
| Doctor | Patient | Patient |
| Manager | Position | Position |
| Position | Job Application | Job Application |

---

## Relationship Creation Navigation

*(Note: As covered in Lesson 29, the navigation to create a relationship is as follows)*

```
Gear Icon → Setup → Object Manager → Select Object → Fields & Relationships → New
```

---

## One-to-Many Relationship Types

One-to-many relationships are implemented using:

```mermaid
flowchart TB
    ONE["One To Many"]
    ONE --> LOOKUP["Lookup Relationship"]
    ONE --> MASTER["Master Detail Relationship"]
```

---

## Lookup Relationship (Introduction)

Lookup Relationship is:
`Loosely Coupled Relationship`

Meaning:
Parent and Child are independent.

Characteristics:
- Parent can exist independently
- Child can exist independently
- Child survives parent deletion
- Separate sharing settings

---

## Lookup Relationship Architecture

```mermaid
flowchart LR
    PARENT["Parent"]
    CHILD["Child"]
    PARENT -. Lookup .-> CHILD
```

---

## Example — Meetup & Participants

Business Scenario:

One meetup event.
Multiple participants.

```mermaid
flowchart LR
    MEETUP["Meetup"]
    P1["Participant"]
    P2["Participant"]
    P3["Participant"]
    MEETUP -. Lookup .-> P1
    MEETUP -. Lookup .-> P2
    MEETUP -. Lookup .-> P3
```

If Meetup gets deleted:
✅ Participants remain.

---

## Lookup Relationship Characteristics

| Feature | Lookup |
| --- | --- |
| Relationship Type | Loose |
| Parent Required | No |
| Child Independent | Yes |
| Parent Delete Removes Child | No |
| Separate Security | Yes |

---

## Recruiting Application — Next Implementation

Next lesson objective:

Create:
`Hiring Manager Field`

Relationship:

```mermaid
flowchart LR
    USER["Hiring Manager"]
    POSITION["Position"]
    USER -. Lookup .-> POSITION
```

We will create:
- Lookup Relationship
- Parent → User
- Child → Position

---

## Important Terms

| Term | Meaning |
| --- | --- |
| Parent Object | One side |
| Child Object | Many side |
| Lookup Relationship | Loose relationship |
| Relationship Field | Field connecting objects |
| One-to-Many | One record → Multiple records |

---

## Certification Focus

> [!IMPORTANT]
> **Relationship Field ALWAYS → Child Object**

Lookup Relationship:
- Child survives deletion
- Independent objects
- Separate sharing settings

Common mistakes:
❌ Creating relationship on parent
❌ Confusing parent and child
❌ Assuming child deletes automatically

---

## Quick Revision (30 sec)

- Started relationship types.
- Learned One-to-Many relationship.
- Parent = One side.
- Child = Many side.
- Relationship field goes on child.
- Introduced Lookup Relationship.
- Parent and child stay independent.
- Next lesson → Create Hiring Manager lookup relationship.