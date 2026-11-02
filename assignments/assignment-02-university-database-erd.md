# Assignment 02 — University Database ER Diagram

**Marks:** 20  
**Lab coverage stated in the supplied brief:** Lab 3–Lab 4  
**Deadline stated in the supplied brief:** 03 November 2026

## Relevant CS403 learning material

Study these topics before attempting the assignment:

- [Lecture 7 — Entities and Attributes](../02-conceptual-database-design/README.md#lecture-7--entities-and-attributes)
- [Lecture 8 — Keys](../02-conceptual-database-design/README.md#lecture-8--keys)
- [Lecture 9 — Relationships](../02-conceptual-database-design/README.md#lecture-9--relationships)
- [Lecture 10 — Minimum Cardinality, Roles, and Dependencies](../02-conceptual-database-design/README.md#lecture-10--minimum-cardinality-roles-and-dependencies)
- [Lectures 10–11 — Supertype, Subtype, and Inheritance](../02-conceptual-database-design/README.md#lectures-10-11--supertype-subtype-and-inheritance)
- [Lectures 12–13 — Examination-System Case Study](../02-conceptual-database-design/README.md#lectures-12-13--examination-system-case-study)

**Lab/theory distinction:** The supplied brief says Lab 3–Lab 4. The lecture links above point to related conceptual-design material in the CS403 theory handout; lab numbers and theory lecture numbers are not interchangeable.

## Scenario

A university maintains records of students, courses, instructors, departments, and textbooks.

- Each student can register for many courses, and each course can have many students.
- Each instructor can teach many courses, and each course can be taught by many instructors.
- Each department can offer many courses, and each course can be offered by many departments.
- Each course can use many textbooks, and each textbook can be used in many courses.

## Tasks

1. Identify entities.
2. Identify attributes of the entities.
3. Identify relationships between the entities.
4. Draw the Entity–Relationship Diagram (ERD) using the information from Tasks 1–3.

## Learn the ERD symbols before drawing

Read [Learn the ERD symbols gradually](../02-conceptual-database-design/README.md#learn-the-erd-symbols-gradually) before starting Task 4. It introduces the rectangle, oval, underlined key attribute, relationship diamond, double rectangle, double oval, dashed oval, and double diamond with examples.

For this assignment, at minimum you should know:
- Rectangle: entity type.
- Oval: attribute.
- Underlined attribute: key.
- Diamond: relationship.
- Relationship lines/cardinality: how entity types are associated.

The scenario does not explicitly require weak entities or multi-valued/derived attributes. Do not add them just to use every symbol; use a symbol only when the requirements justify it.

## Concepts needed

### Entities
An entity type is a category of things the system needs to store information about. The five entity types named in the scenario are Student, Course, Instructor, Department, and Textbook.

### Attributes
Attributes describe entity instances. Propose relevant attributes for each entity, including an identifier. The scenario does not prescribe attribute names or keys, so these are design decisions you must justify.

### Keys
Choose an attribute or combination of attributes that uniquely identifies each entity instance. Do not assume a person's name is unique. Mark identifiers clearly in your ERD.

### Relationships and cardinality
The scenario explicitly gives four many-to-many relationships:

| Relationship | Cardinality |
|---|---|
| Student registers for Course | M:N |
| Instructor teaches Course | M:N |
| Department offers Course | M:N |
| Course uses Textbook | M:N |

Do not change these cardinalities unless the instructor clarifies or changes the scenario. The brief does not specify minimum participation, so state assumptions rather than presenting them as given requirements.

### ERD notation
Use one consistent notation for entities, attributes, keys, and relationships. Make relationship names and cardinalities readable. If the instructor or lab manual requires a particular notation, follow it.

## Submission requirements

The supplied brief requires all four tasks and the final ER diagram pasted into a **Microsoft Word document**. It says other formats will not be accepted and will receive zero marks.

**Deadline in supplied brief:** 03 November 2026. Check the VU LMS or instructor announcement for any revised deadline or submission instructions.

## Suggested Word document structure

1. Assignment title and student details.
2. Task 1 — identified entities.
3. Task 2 — attributes for each entity, with identifiers marked.
4. Task 3 — relationships and cardinalities.
5. Task 4 — final ERD pasted clearly into the document.

## Self-check

- [ ] All five named entities are included.
- [ ] Attributes are listed for each entity.
- [ ] Identifiers are clearly marked and justified.
- [ ] All four M:N relationships are shown.
- [ ] Any assumptions about optional/mandatory participation are stated.
- [ ] The ERD is legible in the Word document.
- [ ] All four tasks are included.
- [ ] The final document is saved as .docx.

This guide explains the concepts needed to attempt the work. It does not provide a completed answer to submit.
