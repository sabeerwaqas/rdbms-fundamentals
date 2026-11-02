# Assignment 01 — Examination System Design

**Related sections:** Database fundamentals and conceptual database design  
**Handout coverage:** Primarily the conceptual database design topics in Lectures 7–13  
**Type:** Original practice assignment  
**Database engine:** Not required

## Relevant CS403 learning material

- [Lectures 7 — Entities and Attributes](../02-conceptual-database-design/README.md#lecture-7--entities-and-attributes)
- [Lecture 8 — Keys](../02-conceptual-database-design/README.md#lecture-8--keys)
- [Lecture 9 — Relationships](../02-conceptual-database-design/README.md#lecture-9--relationships)
- [Lecture 10 — Cardinality, Roles, and Dependencies](../02-conceptual-database-design/README.md#lecture-10--minimum-cardinality-roles-and-dependencies)
- [Lectures 12–13 — Examination-System Case Study](../02-conceptual-database-design/README.md#lectures-12-13--examination-system-case-study)

Study the relevant explanations and worked examples before attempting the tasks. The case study is a reference for the modelling process; your design should still follow the requirements and assumptions you state for this assignment.

## Learn the ERD symbols before drawing

Review [Learn the ERD symbols gradually](../02-conceptual-database-design/README.md#learn-the-erd-symbols-gradually), especially entity rectangles, attribute ovals, underlined key attributes, relationship diamonds, and cardinality notation.

## Scenario

A university needs to organize information about students, academic programs, courses, teachers, semesters, course offerings, registrations, and examination results.

Your task is to produce a conceptual model that can support the university's basic academic and examination record-keeping needs.

## Tasks

1. List the main information requirements you believe the system must support.
2. Identify candidate entities. For each entity, suggest attributes and a possible identifier.
3. Identify relationships between the entities and state the cardinality of each relationship.
4. Draw an ER diagram using a notation that clearly distinguishes entities, attributes, and relationships.
5. State the assumptions you made where the scenario does not specify a business rule.
6. Check your model against at least five example questions the university might ask, such as finding the courses offered in a semester or the results recorded for a student.

## Deliverables

- A short requirements list.
- An ER diagram (image, PDF, or editable diagram source).
- A table listing entities, key attributes, and identifiers.
- A list of assumptions and example questions used to validate the model.

## Self-review checklist

- [ ] Each entity represents a distinct type of thing the system needs to remember.
- [ ] Every relationship has a stated meaning and cardinality.
- [ ] Identifiers are clearly marked.
- [ ] The model can answer the example questions without inventing missing data.
- [ ] Assumptions are explicit rather than hidden in the diagram.

## Submission note

Do not use real student records or personal information. Use fictional sample data only if you create examples.
