# 04 — Normalization

**VU CS403 handout:** Lectures 19–21

Normalization structures relations to reduce unnecessary redundancy and avoid modification anomalies.

## 1. Why normalize?

When one table stores student, course, and registration facts together, names may repeat across many rows. This can cause:
- **Update anomaly:** the same fact must be changed in multiple rows.
- **Insertion anomaly:** a fact cannot be recorded without an unrelated fact.
- **Deletion anomaly:** deleting one row accidentally removes the only record of another fact.

Normalization separates facts according to their dependencies.

## 2. Functional dependency

A functional dependency X → Y means a value of attribute set X determines exactly one value of attribute set Y.

Example:
- studentId → studentName
- courseId → courseName

Dependencies should come from the meaning/business rules of the data, not just a small sample that happens to contain unique values.

## 3. First Normal Form (1NF)

A relation is in 1NF when each attribute value is atomic in the context of the model; do not store a list of multiple values in one cell.

Before:

| studentId | studentName | courses |
|---|---|---|
| S01 | Ali | CS101, CS102 |

After separating the repeating course values:

| studentId | studentName | courseId |
|---|---|---|
| S01 | Ali | CS101 |
| S01 | Ali | CS102 |

This is an illustration of atomic values; repeated student facts still need further design consideration.

## 4. Second Normal Form (2NF)

A relation is in 2NF if it is in 1NF and every non-key attribute is fully functionally dependent on the whole candidate key. This matters especially with composite keys.

Consider:

~~~text
ENROLLMENT(studentId, courseId, studentName, courseName, grade)
Key: (studentId, courseId)
Dependencies:
studentId → studentName
courseId → courseName
(studentId, courseId) → grade
~~~

studentName and courseName depend on only part of the composite key. These are partial dependencies.

Decomposition:

~~~text
STUDENT(studentId, studentName)
COURSE(courseId, courseName)
ENROLLMENT(studentId, courseId, grade)
~~~

## 5. Third Normal Form (3NF)

3NF removes transitive dependencies of non-key attributes on a key. For example:

~~~text
studentId → departmentId
departmentId → departmentName
~~~

departmentName is transitively dependent on studentId through departmentId. A separate DEPARTMENT relation can store departmentName.

## 6. BCNF and higher forms

BCNF is stricter than 3NF: every determinant in a non-trivial functional dependency must be a superkey. The handout also introduces higher normal forms, including 4NF and 5NF. First learn to identify dependencies and apply 1NF, 2NF, 3NF, and BCNF correctly.

## How to solve a normalization question

1. Write the original relation and identify candidate key(s).
2. List functional dependencies.
3. Identify repeating/non-atomic values and reach 1NF.
4. Check partial dependencies and reach 2NF.
5. Check transitive dependencies and reach 3NF.
6. Check BCNF if required.
7. Show each resulting relation, primary key, and foreign key.
8. Explain which anomaly or dependency each decomposition addresses.

## Practice

Using the ENROLLMENT relation above:
1. Identify the composite key.
2. List the partial dependencies.
3. Explain why it is not in 2NF.
4. Write the decomposed relations.
5. Explain why grade remains in ENROLLMENT.

## Next
[05 — Physical Database Design](../05-physical-database-design/README.md).
