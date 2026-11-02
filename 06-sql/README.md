# 06 — Structured Query Language (SQL)

**VU CS403 handout:** Lectures 25–31

SQL defines database structures, manipulates stored data, retrieves information, and controls access.

> **Dialect note:** The handout contains examples for Microsoft SQL Server 2000 / Query Analyzer. Confirm the current CS403P lab engine before treating a script here as a practical submission. Syntax and data types differ by DBMS and version.

## 1. SQL command groups

| Group | Purpose | Examples |
|---|---|---|
| DDL | Define/change structures | CREATE, ALTER, DROP |
| DML | Insert/change/remove data | INSERT, UPDATE, DELETE |
| Query | Retrieve data | SELECT |
| DCL | Control permissions | GRANT, REVOKE |

## 2. Example schema

~~~text
STUDENT(regNo, studentName, city)
COURSE(courseCode, courseName)
ENROLLMENT(regNo, courseCode, grade)
~~~

Assume regNo and courseCode identify their respective entities. The composite key (regNo, courseCode) identifies one registration if duplicate registrations are not allowed by the model.

## 3. Retrieve, filter, and sort

~~~sql
SELECT regNo, studentName
FROM STUDENT;
~~~

Filter rows with WHERE:

~~~sql
SELECT regNo, studentName
FROM STUDENT
WHERE city = 'Karachi';
~~~

Sort with ORDER BY:

~~~sql
SELECT regNo, studentName
FROM STUDENT
ORDER BY studentName;
~~~

## 4. Aggregate and group

Aggregate functions summarize rows: COUNT, SUM, AVG, MIN, and MAX.

~~~sql
SELECT COUNT(*) AS student_count
FROM STUDENT;
~~~

GROUP BY forms groups before aggregate calculations:

~~~sql
SELECT city, COUNT(*) AS student_count
FROM STUDENT
GROUP BY city;
~~~

## 5. Join related tables

A join combines rows using a relationship between tables:

~~~sql
SELECT s.studentName, e.courseCode, e.grade
FROM STUDENT AS s
JOIN ENROLLMENT AS e
  ON e.regNo = s.regNo;
~~~

The join condition connects each enrollment to its student. Without an appropriate condition, unrelated rows may be combined.

## 6. Permissions

The handout introduces GRANT and REVOKE as DCL commands. They grant and withdraw privileges. Exact permission names and syntax depend on the DBMS.

## Practice

1. Return all students from one city.
2. Sort students by name.
3. Count students in each city.
4. Join STUDENT to ENROLLMENT to display student names and grades.
5. Explain the difference between DDL, DML, and DCL.

## Script policy

Every executable script must state the database engine/version tested, required schema, sample data, and expected output. Do not claim a script was tested if it was not executed against the stated DBMS.

## Next
[07 — Database Applications](../07-database-applications/README.md).
