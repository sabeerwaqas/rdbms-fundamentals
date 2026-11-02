# Assignment 02 — University Database ER Diagram

**Marks:** 20  
**Course coverage stated in the brief:** Lab 3–Lab 4  
**Due date stated in the brief:** 03 November 2026  
**Required submission format:** Microsoft Word document (.docx) containing the final ER diagram

> This page is a concise study-oriented restatement of the assignment brief supplied for this repository. Follow the instructions on your official VU assignment page if any detail differs.

## Scenario

A university needs to maintain information about students, courses, instructors, departments, and textbooks.

The brief specifies these many-to-many relationships:

- A student may register for multiple courses, and a course may have multiple students.
- An instructor may teach multiple courses, and a course may be taught by multiple instructors.
- A department may offer multiple courses, and a course may be offered by multiple departments.
- A course may use multiple textbooks, and a textbook may be used by multiple courses.

## Tasks

1. **Identify entities:** Identify the entity types required by the scenario.
2. **Identify attributes:** Propose suitable attributes for each entity.
3. **Identify relationships:** Identify and describe the relationships between the entities.
4. **Draw the ER diagram:** Produce an ERD based on your work in Tasks 1–3.

## Submission requirements

Submit the final ER diagram by placing it in a Microsoft Word document. The supplied brief states that other file formats will not be accepted and may receive zero marks.

Before submitting, check the official assignment portal for the exact upload procedure and deadline.

## Modelling checklist

- [ ] Include the five entity types named in the scenario: Student, Course, Instructor, Department, and Textbook.
- [ ] Give each entity a suitable identifier (primary key).
- [ ] Add attributes that make sense for the scenario.
- [ ] Represent all four many-to-many relationships.
- [ ] Label relationships clearly so their meaning is understandable.
- [ ] Show cardinality using one consistent ER notation.
- [ ] Make any assumptions explicit.
- [ ] Check that every relationship in the diagram is supported by the scenario or a clearly stated assumption.
- [ ] Export or paste a readable final diagram into a Word document (.docx).

## Important modelling notes

### The scenario explicitly gives four many-to-many relationships

A relational implementation cannot represent a many-to-many relationship directly with only one foreign key on either of the two participating entity tables. It is normally resolved using an associative entity (also called a junction or bridge entity).

Possible associative-entity names include:

| Relationship | Possible associative entity |
| --- | --- |
| Student ↔ Course | Registration or Enrollment |
| Instructor ↔ Course | CourseTeaching or TeachingAssignment |
| Department ↔ Course | CourseOffering |
| Course ↔ Textbook | CourseTextbook |

These names are suggestions, not names mandated by the brief. Your ERD should make the relationship and its meaning clear.

### The brief does not provide attributes

You are expected to propose attributes. For example, Student could have a student identifier, name, and email; Course could have a course identifier, title, and credit hours. These are illustrative choices, not facts specified by the assignment. Select appropriate attributes and explain any assumptions.

### Some business rules remain unspecified

The brief says that the relationships are many-to-many, but does not define minimum participation, relationship attributes, or additional rules such as whether a student can register for the same course more than once in different semesters. Do not silently invent these rules. If your model needs them, state your assumptions.

The scenario also does not specify a relationship between Instructor and Department. Do not add one as if it were required; include it only if you clearly identify it as an assumption and can justify it.

## Self-review questions

1. Have you included all five entities and all four relationships from the scenario?
2. Can your model represent multiple students in a course and multiple courses for a student?
3. Can it represent multiple instructors per course, and vice versa?
4. Can a course be offered by more than one department?
5. Can the same textbook be associated with multiple courses?
6. Have you selected identifiers and stated assumptions where the brief is silent?

## Final submission reminder

The brief specifies a **Word document (.docx)** containing the final ERD. A standalone image, PDF, or diagram source should not be submitted instead unless the official assignment instructions are updated.
