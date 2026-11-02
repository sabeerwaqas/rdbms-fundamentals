# 02 — Conceptual Database Design and ER Modelling

**VU CS403 handout:** Lectures 7–13  
**Related assignments:** [Assignment 01 — Examination System](../assignments/assignment-01-examination-system-design.md) · [Assignment 02 — University Database ERD](../assignments/assignment-02-university-database-erd.md)

This section teaches the steps needed to understand and draw an Entity–Relationship Diagram (ERD). Study it in order.

## Lecture 7 — Entities and attributes

### What is an ER model?
The Entity–Relationship (ER) model is a semantic data model used to represent conceptual database design graphically. It is implementation-independent: it describes the information and relationships an organization needs before a DBMS is selected.

Its three main constructs are **entities, attributes, and relationships**.

### Entity type, instance, and set
- **Entity type:** a category of things with common properties, e.g. STUDENT.
- **Entity instance:** one particular member of that category, e.g. student S104.
- **Entity set:** the collection of instances of an entity type, e.g. all students.

A useful test: does the system need to store multiple instances of this kind of thing and remember properties about them?

### Strong and weak entities
- **Strong entity type:** its instances can exist independently and have their own identification.
- **Weak entity type:** its instances depend on another entity type for existence.

The handout's example is an employee-owned vehicle record that depends on the employee record. In the handout's notation, a strong entity uses a single rectangle and a weak entity a double rectangle.

### Attributes and domains
An **attribute** describes a property of an entity type. A **domain** is the set of legal values for an attribute. For example, a credit-hours attribute should have a numeric domain with a sensible permitted range. Domains help prevent invalid values.

| Attribute type | Meaning | Example |
|---|---|---|
| Simple | Not usefully divided into smaller parts | A code |
| Composite | Can be divided into meaningful components | Address: street, city |
| Single-valued | One value per entity instance | Date of birth |
| Multi-valued | Multiple values may be associated with an instance | Phone numbers |
| Stored | Value is retained in the database | Date of birth |
| Derived | Calculated from other values | Age derived from date of birth |

The handout's attribute notation uses ovals; a composite attribute connects to its components, a multi-valued attribute uses a double oval, a derived attribute uses a dashed oval, and a key attribute is underlined.

### Worked example
For STUDENT, possible attributes are registration number, name, date of birth, and email. Registration number may identify a student. One instance could be (VU-1024, Ayesha Khan, 2004-03-12, ayesha@example.test). The entity type defines the structure; the instance supplies actual values. This is fictional data.

## Lecture 8 — Keys

A **key** is an attribute or combination of attributes used to identify an entity instance.

| Key type | Meaning |
|---|---|
| Super key | One or more attributes that uniquely identify an instance |
| Candidate key | A minimal super key; no proper subset is still a key |
| Primary key | The candidate key selected as the main identifier |
| Alternate key | A candidate key not selected as primary |
| Secondary key | Used for searching; uniqueness is not guaranteed |

A **composite key** contains more than one attribute. A primary key must uniquely identify an instance and cannot be NULL.

### Worked example
Assume STUDENT has attributes regNo, nationalId, name, and city. If regNo and nationalId are each unique:
- regNo and nationalId are candidate keys.
- If regNo is selected as primary, nationalId is an alternate key.
- city can be a secondary search key because many students may live in the same city.
- (regNo, name) is a super key but not a candidate key because regNo alone is sufficient.

**Common mistake:** using a person's name as a primary key. Names can repeat and may change.

## Lecture 9 — Relationships

A **relationship** is a meaningful association between entity types. Examples: a student registers for a course; an instructor teaches a course; a department offers a course. A relationship should have a clear name and meaning.

### Relationship degree
Degree tells how many entity types participate:
- **Unary / recursive:** an entity type relates to itself, e.g. an employee supervises another employee.
- **Binary:** two entity types participate, e.g. STUDENT registers for COURSE.
- **Ternary:** three entity types participate in one relationship.
- **N-ary:** more than three entity types participate.

Do not confuse relationship degree with cardinality.

### Relationship cardinality
Cardinality describes how many instances on one side can be associated with an instance on the other.

| Type | Meaning | Example |
|---|---|---|
| 1:1 | At most one on each side | Person–Passport, if rules permit one passport per person |
| 1:M | One on one side can relate to many on the other | Department–Employee |
| M:1 | Many on one side relate to one on the other | Employee–Department |
| M:N | Many on each side can relate to many on the other | Student–Course |

### Relationship attributes
A fact may belong to the association rather than either entity alone. For example, registrationDate describes a student's registration in a particular course, not the student generally or the course generally.

## Lecture 10 — Minimum cardinality, roles, and dependencies

### Maximum and minimum cardinality
- **Maximum** tells the greatest number of related instances allowed.
- **Minimum** tells the least number required.
- Minimum 0 means optional participation.
- Minimum 1 means mandatory participation.

In min/max notation, 0..* means zero or many; 1..1 means exactly one. Read each end carefully and use one notation consistently. The scenario and business rules determine the cardinalities; do not guess them.

### Roles and recursive relationships
A **role** describes how an entity participates in a relationship. Roles are especially useful when an entity relates to itself or when two entity types have more than one relationship. For example, an instructor may teach a student and separately supervise that student's project. Label the roles to avoid ambiguity.

### Dependencies
The handout distinguishes:
- **Existence dependency:** an entity instance cannot exist without a related instance of another entity.
- **Identifier dependency:** the dependent entity uses the parent's identifier as part of its own identification.
- **Referential dependency:** the dependent entity has its own identifier but also refers to a parent through a reference attribute.

These ideas help decide whether an entity is dependent and how its identity and participation should be represented.

## Lectures 10–11 — Supertype, subtype, and inheritance

A **supertype** stores properties shared by a general category. A **subtype** represents a more specific category and inherits common properties from its supertype.

Example: PERSON may be a supertype, with STUDENT and INSTRUCTOR as subtypes. Shared attributes such as name belong at PERSON level; student-specific or instructor-specific attributes belong in their subtype.

Two independent constraints apply:

**Completeness**
- **Total:** every supertype instance must belong to at least one subtype.
- **Partial:** a supertype instance may belong to no subtype.

**Disjointness**
- **Disjoint:** one supertype instance can belong to only one subtype in the classification.
- **Overlapping:** one supertype instance may belong to multiple subtypes.

The four combinations are complete-disjoint, complete-overlapping, partial-disjoint, and partial-overlapping. A **subtype discriminator** is an attribute used to indicate which subtype an instance belongs to.

Do not add a subtype hierarchy just because two entities share one attribute. Use it only when the requirements support a genuine general/specialized relationship.

## Lectures 12–13 — Examination-system case study

The handout uses an educational institute's examination system to demonstrate analysis and conceptual design.

### Understand the system
The case study describes students enrolled in programs; programs based on courses; courses offered in semesters; students registering for offered courses subject to prerequisites; teachers assigned to course offerings; teachers submitting assessment marks; and results/GPA calculated from student performance.

### Users and outputs
The handout identifies students, teachers, and the controller's office as participants. Outputs include transcripts, semester result cards, attendance sheets, and class results.

### From analysis to ERD
1. Use DFDs to understand processes and data movement.
2. List outputs and their required data items.
3. Use a cross-reference matrix to relate report fields to outputs.
4. Identify candidate entity types and attributes.
5. Identify relationships and cardinalities.
6. Draw the ERD and validate it against required outputs.

The handout's candidate entities include STUDENT, COURSES, TEACHERS, PROGRAMS, SEMESTER, and COURSE OFFERED. It discusses why a single controller instance need not be an entity type and why “results” requires careful analysis rather than being added as one vague entity.

The case study relationships include PROGRAM–COURSE, STUDENT–PROGRAM, SEMESTER–COURSE through COURSE OFFERED, COURSE OFFERED–TEACHER, STUDENT–COURSE OFFERED through ENROLLED, and STUDENT–SEMESTER through result/GPA information.

The key lesson is that an ER model must support the required outputs. If an attendance sheet or transcript cannot be produced from the model, revisit the entities, attributes, and relationships before moving to logical design.

## A repeatable method for any ERD assignment

1. **Extract nouns:** list candidate entity types.
2. **Check each noun:** does the system need to store multiple instances and their properties?
3. **Extract facts:** list attributes required for each entity.
4. **Choose identifiers:** select keys that uniquely identify instances.
5. **Extract verbs:** turn meaningful associations into named relationships.
6. **Set degree and cardinality:** identify unary/binary/ternary and 1:1, 1:M, M:N.
7. **Set minimum participation:** decide optional or mandatory participation from stated rules.
8. **Check relationship attributes:** put facts such as registration date on the association when appropriate.
9. **Draw and validate:** use consistent notation and check required outputs.

## Practice before attempting assignments

1. Identify entities and attributes for a library system.
2. Explain entity type, instance, and entity set.
3. Give one strong and one weak entity example.
4. For STUDENT(regNo, nationalId, name, city), identify candidate keys if regNo and nationalId are unique.
5. Classify Student–Course by degree and cardinality.
6. Explain 0..* versus 1..*.
7. Give a recursive relationship and label both roles.
8. Give an example of total completeness and disjointness.

## Assignments

- [Assignment 01 — Examination System Design](../assignments/assignment-01-examination-system-design.md)
- [Assignment 02 — University Database ER Diagram](../assignments/assignment-02-university-database-erd.md)

For Assignment 02, focus first on Lectures 7–10: entity/attribute identification, keys, relationships, and minimum/maximum cardinality. Lectures 11–13 provide additional modelling context and the handout's case study.

## Next
Continue to [03 — Relational Data Model](../03-relational-data-model/README.md). Conceptual ER design is not yet a set of relational tables.
