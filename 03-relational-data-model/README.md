# 03 — Logical Database Design and the Relational Data Model

**VU CS403 handout:** Lectures 14–18

## 1. Conceptual versus logical design

| Conceptual design | Logical design |
|---|---|
| Describes required information and relationships | Describes the structure using a selected data model |
| Commonly represented with an ER model | In this course, developed using the relational data model |
| Independent of a specific DBMS | Uses a data model that can later be implemented |

An ER diagram is not yet a set of SQL tables. Mapping it into relations is a separate design step.

## 2. Relational data model

The relational data model represents data using **relations**, commonly displayed as tables.

- Relation: logical table structure.
- Tuple: one row.
- Attribute: one column.
- Domain: permitted values for an attribute.
- Degree of a relation: number of columns.
- Cardinality of a relation: number of rows.

Do not confuse relation degree/cardinality with ER relationship degree/cardinality.

## 3. Basic properties of a relation

The handout discusses these key properties:
- Each relation has a distinct name.
- Each cell contains a single value from its domain.
- Values in a column belong to the same domain.
- Duplicate tuples are not part of the mathematical definition of a relation.
- Row order has no logical significance.
- Column order has no logical significance in a database relation.

## 4. Integrity

- **Entity integrity:** a primary key uniquely identifies a row and cannot be NULL.
- **Referential integrity:** a foreign-key value refers to an existing key in the referenced relation, subject to permitted NULL rules.
- **Domain integrity:** values belong to the defined domain.

## 5. Mapping ER relationships to relations

- **1:M:** place the primary key from the one-side relation as a foreign key in the many-side relation.
- **M:N:** create an associative relation containing the keys of the participating relations. These keys commonly form a composite primary key; relationship attributes can also be stored there.
- **1:1:** place a foreign key on an appropriate side, considering participation and optionality.

### Worked example — Student and Course

Conceptual relationship: a student can register for many courses, and a course can have many students.

~~~text
STUDENT(regNo, studentName)
COURSE(courseCode, courseName)
ENROLLMENT(regNo, courseCode, registrationDate)
~~~

- STUDENT.regNo identifies a student.
- COURSE.courseCode identifies a course.
- ENROLLMENT.regNo references STUDENT.
- ENROLLMENT.courseCode references COURSE.
- (regNo, courseCode) identifies one student-course registration if each student can register for a course only once in this model.
- registrationDate describes the registration, so it belongs in ENROLLMENT.

Check the uniqueness assumption against system rules; if repeated attempts are recorded, the key needs an attempt/term identifier.

## 6. Relational operations

The handout introduces mathematical/database relations and operations including Cartesian product and joins.

- **Cartesian product:** pairs every tuple from one relation with every tuple from another. If A has 2 rows and B has 3 rows, A × B has 6 row combinations.
- **Join:** combines related tuples using a condition. It retrieves information stored across multiple relations.

A join is not the same as a Cartesian product, although a Cartesian product followed by a selection condition can express a join.

## Practice

1. A relation has 4 columns and 12 rows. State its degree and cardinality.
2. Why does row order not define a relation?
3. Map a 1:M Department–Employee relationship.
4. Map a M:N Student–Course relationship with an enrollment date.
5. If A has 4 tuples and B has 5 tuples, how many tuples are in A × B?

## Next
[04 — Normalization](../04-normalization/README.md).
