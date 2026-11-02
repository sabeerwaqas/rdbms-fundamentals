# 09 — Views and Transaction Management

**VU CS403 handout:** Lectures 39–45

## 1. Views

A view is a named query that presents selected data from one or more base tables. It can simplify what a user sees and support security by exposing only required rows or columns.

Example (illustrative SQL; confirm dialect before execution):

~~~sql
CREATE VIEW KarachiStudents AS
SELECT regNo, studentName
FROM STUDENT
WHERE city = 'Karachi';
~~~

A view does not necessarily store a separate copy of underlying rows; it presents data according to its query definition.

The handout covers views for focusing data, data independence, security, views from one or more tables, views of views, functions in views, and updates on views. Not every view is updatable; restrictions depend on its definition and DBMS.

## 2. Transactions and ACID

A **transaction** is a logical unit of work. A bank transfer is a useful example: debit one account and credit another. These changes should not be treated as unrelated operations.

- **Atomicity:** all operations happen, or none do.
- **Consistency:** a transaction preserves defined integrity rules.
- **Isolation:** concurrent transactions do not interfere in a way that violates required correctness.
- **Durability:** committed changes survive failures according to the DBMS's guarantees.

## 3. Concurrency problems

When transactions execute at the same time, their operations may interleave. Without suitable control, problems include lost updates, dirty reads, and inconsistent results when one transaction reads data while another changes it.

The handout discusses serial and interleaved schedules, serializability, and locking.

## 4. Serializability

A **serial schedule** runs one transaction completely before another. An **interleaved schedule** mixes operations from multiple transactions.

A schedule is serializable if its effect is equivalent to some serial execution. The aim is to allow concurrency while preserving correctness.

## 5. Locking and deadlocks

Locks control concurrent access to data. A transaction may need to wait when another transaction holds an incompatible lock.

A **deadlock** occurs when transactions wait on one another in a cycle, so none can proceed without intervention. The final handout lectures discuss deadlock handling, wait-for graphs, resolution, and timestamping rules.

## Practice

1. Give one reason a view can improve security.
2. Which ACID property relates to an all-or-nothing transfer?
3. Distinguish serial and interleaved schedules.
4. Explain a lost update with two transactions.
5. Draw a wait-for cycle involving two transactions and explain why it is a deadlock.

## Next
Review the [course map](../README.md) and revisit earlier design choices that affect transaction correctness.
