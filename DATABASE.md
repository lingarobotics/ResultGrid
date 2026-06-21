# Database Design

## Overview

ResultGrid uses PostgreSQL as its primary persistence layer.

The schema is designed around structured academic relationships and normalized data organization.

---

## Design Objectives

* Maintain data integrity
* Reduce redundancy
* Support efficient retrieval
* Enable future scalability
* Preserve clear entity relationships

---

## Core Entities

### District

Represents geographic administrative regions.

Examples:

* Chennai
* Kanchipuram
* Chengalpattu

---

### College

Represents educational institutions.

Relationships:

District

1 → N

College

---

### Department

Represents academic departments.

Examples:

* Robotics and Automation
* Computer Science
* Mechanical Engineering

Relationships:

College

1 → N

Department

---

### Academic Year

Represents student progression.

Examples:

* First Year
* Second Year
* Third Year
* Final Year

---

### Student

Stores student-specific information.

Attributes:

* Register Number
* Name
* Department
* Academic Year

---

### Semester

Stores semester metadata.

Attributes:

* Semester Number
* Examination Session

---

### Subject

Stores subject information.

Attributes:

* Subject Code
* Subject Name
* Credits

---

### Result

Stores student performance records.

Relationships:

Student

1 → N

Result

---

## Normalization Strategy

The schema prioritizes:

* Elimination of redundant data
* Consistent academic metadata
* Efficient update operations

Normalization reduces duplication while preserving query flexibility.

---

## Indexing Strategy

Planned indexes include:

* Register Number
* College Identifier
* Department Identifier
* Semester Identifier

The objective is predictable retrieval performance under read-heavy workloads.

---

## Future Considerations

Potential future additions:

* Historical result tracking
* Academic analytics
* Performance trends
* Department-level reporting
* Institution-level dashboards
