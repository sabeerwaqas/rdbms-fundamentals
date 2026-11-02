# Assignment 02 — University Database ER Diagram

<small>**Marks:** 20 · **Lab coverage stated in brief:** Lab 3–Lab 4 · **Deadline stated in brief:** 03 November 2026</small>

**Related repository section:** [02 — Conceptual Database Design](../02-conceptual-database-design/README.md)  
**Related CS403 handout lectures:** Lectures 7–13 — conceptual database design and ER modelling  
**Task type:** Entity identification, attribute identification, relationship analysis, and ER diagram

> **Course alignment note:** The supplied assignment brief identifies Lab 3–Lab 4 as its coverage. The lecture range above points to the related conceptual-design material in the CS403 theory handout; it does not claim that Lab 3–Lab 4 are the same as Lectures 7–13.

## Scenario

A university maintains records of students, courses, instructors, departments, and textbooks.

The scenario specifies these relationships:

- Each student can register for many courses, and each course can have many students.
- Each instructor can teach many courses, and each course can be taught by many instructors.
- Each department can offer many courses, and each course can be offered by many departments.
- Each course can use many textbooks, and each textbook can be used in many courses.

## Tasks

1. **Identify entities.** Identify the entities required by the scenario.
2. **Identify attributes.** Propose suitable attributes for each entity.
3. **Identify relationships.** Identify the relationships between the entities.
4. **Draw the ER diagram.** Create an Entity–Relationship Diagram from the entities, attributes, and relationships identified in Tasks 1–3.

## Modelling notes

The five entity types explicitly named in the scenario are:

- Student
- Course
- Instructor
- Department
- Textbook

The scenario explicitly describes four many-to-many relationships:

| Relationship | Cardinality stated in the scenario |
| --- | --- |
| Student registers for Course | Many-to-many (M:N) |
| Instructor teaches Course | Many-to-many (M:N) |
| Department offers Course | Many-to-many (M:N) |
| Course uses Textbook | Many-to-many (M:N) |

The scenario does **not** provide attributes, identifiers, or additional business rules. You must propose reasonable attributes and identifiers, and state any assumptions you make. Do not present assumptions as facts supplied by the assignment.

For this task, focus on the conceptual ER diagram. If you later convert the design into relational tables, each many-to-many relationship will need an appropriate relational mapping, commonly through an associative table. Do not confuse that implementation step with the conceptual relationship itself; follow the notation required by your instructor.

## Submission requirements

The supplied brief requires:

- Complete all four tasks.
- Prepare the final ER diagram.
- Paste the final ER diagram into a **Microsoft Word document**.
- Submit the Word document by the stated deadline.

**Format warning from the supplied brief:** Any other format will not be entertained and will receive zero marks. Treat the Word document requirement as mandatory unless your instructor issues an updated instruction.

**Deadline in the supplied brief:** 03 November 2026. Confirm the submission portal and any updated deadline with your course instructor/LMS.

## Suggested Word document structure

1. Assignment title and student details.
2. Task 1 — identified entities.
3. Task 2 — attributes for each entity, with identifiers clearly marked.
4. Task 3 — relationships and cardinalities.
5. Task 4 — final ER diagram pasted clearly and legibly.

The brief specifically requires the final ERD to be pasted into Word. The suggested ordering above is a practical way to present all four tasks in one document.

## Final self-check

- [ ] All five scenario entities are represented.
- [ ] Attributes are listed for every entity.
- [ ] All four many-to-many relationships are shown.
- [ ] Identifiers are clear and consistent.
- [ ] Any additional assumptions are stated.
- [ ] The ER diagram is readable when viewed in the Word document.
- [ ] All four tasks are included.
- [ ] The final file is saved as a Word document (.docx).

## Readiness assessment

The assignment brief is sufficiently clear to begin. The main design work is choosing sensible attributes and identifiers because the scenario does not specify them. The four many-to-many relationships are explicit, so their cardinalities are not ambiguous. Make your assumptions visible and check that the ERD matches the written relationship list.
