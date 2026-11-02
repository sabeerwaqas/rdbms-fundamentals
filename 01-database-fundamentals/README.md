# 01 — Database Fundamentals

**VU CS403 handout:** Lectures 1–6

## 1. Data, information, database, and DBMS

- **Data:** recorded facts, such as a student's registration number or course code.
- **Information:** data processed to answer a question, such as a list of students registered in a course.
- **Database:** an organized collection of related data.
- **DBMS:** software used to define, store, retrieve, update, and control access to a database.

A database is the stored collection; a DBMS is the software that manages it.

## 2. File processing and the database approach

Separate file-based applications can store the same fact in multiple places. This creates:
- **Redundancy:** repeated copies of the same fact.
- **Inconsistency:** copies disagree after an incomplete update.
- **Isolation:** combining data across unrelated formats is difficult.
- **Integrity problems:** rules are hard to enforce consistently.
- **Access/security problems:** controlling who can see or change information is harder.

A DBMS provides shared data management, constraints, controlled access, concurrent use, and recovery facilities. It also introduces costs: software, hardware, administration, maintenance, training, and operational complexity.

## 3. Three levels of database architecture

- **External level:** how a particular user or application sees data.
- **Conceptual level:** the overall logical structure of the database.
- **Internal level:** how data is physically stored.

Separation between levels supports data independence: some changes to storage or logical structure can be made without forcing every user view or application to change. These levels are not the same as the stages of database design.

## 4. Development process and analysis

The handout describes database design, application programs, and implementation as major parts of database application development. Preliminary study and analysis help establish what users need.

A practical analysis sequence:
1. Identify people/systems interacting with the proposed system.
2. Understand the information they provide and require.
3. Model data movement using Data Flow Diagrams (DFDs).
4. Examine required reports and outputs.
5. Identify facts that must be stored before creating the database design.

A **DFD** describes processes, external entities, data flows, and data stores. It shows how information moves; it is not an ER diagram and does not define database tables.

A **cross-reference matrix** relates data items to required reports. It helps identify which facts are needed and can help discover candidate entities and attributes.

## Worked example — University result system

Students need semester result cards and transcripts, teachers submit marks, and the examination office produces class results.

- External participants include students, teachers, and the examination office.
- Processes include result submission and result calculation.
- Outputs include result cards, transcripts, and class results.
- Stored data may include student identity, course information, semester information, and marks/results.

The DFD describes information flow. The outputs help determine what data must be stored. The ER model is developed later.

## Check your understanding

1. How is a DBMS different from a database?
2. Give an example of redundancy and inconsistency in a student record system.
3. Distinguish external, conceptual, and internal levels.
4. What does a DFD show that an ER diagram does not?
5. How can a cross-reference matrix help identify data requirements?

## Practice

Choose a university registration or result system. Write down two user groups, three processes, three required outputs, and the data items needed to produce those outputs. Do not draw tables yet; this is requirements analysis.

## Next
[02 — Conceptual Database Design](../02-conceptual-database-design/README.md).
