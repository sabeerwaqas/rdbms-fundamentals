# 05 — Physical Database Design

**VU CS403 handout:** Lectures 22–24

Physical database design turns the logical design into implementation decisions for a particular DBMS and workload.

## 1. Logical and physical design

- **Logical design:** relations, attributes, keys, and constraints representing required data.
- **Physical design:** how the chosen DBMS stores and accesses that data.

Physical decisions should follow logical requirements; they should not change the meaning of the data.

## 2. Analyse usage first

For each table or data item, ask:
- How much data is expected?
- How frequently is it read or updated?
- Which queries are most important?
- How quickly must they run?
- Are there availability, backup, or recovery requirements?

A design optimized for frequent reads may differ from one optimized for frequent updates.

## 3. Field and data-type design

Choose types that represent required values and constrain invalid data.

| Attribute | Suitable conceptual type |
|---|---|
| Registration number | Character/string, especially if letters or leading zeroes occur |
| Date of birth | Date |
| Credit hours | Numeric |
| Email | Character/string with validation |

Use NOT NULL, UNIQUE, CHECK, and key constraints where supported and appropriate. Exact syntax depends on the DBMS.

## 4. Physical techniques

The handout discusses field design, coding, partitioning, and replication.

- **Coding:** represent a repeated category using a controlled code rather than inconsistent free text.
- **Partitioning:** divide a large table or dataset into manageable parts according to a chosen key or rule.
- **Replication:** maintain copies of data in multiple locations/systems to support availability or access needs; copies introduce consistency and update considerations.

Do not apply these techniques without a requirement. They add complexity and should solve a real storage, performance, or availability problem.

## Practice

For a student registration database:
1. Suggest data types for registration number, name, date of birth, and credit hours.
2. Identify two fields that should not be nullable and explain why.
3. Describe one query pattern that might justify an index.
4. Explain one benefit and one trade-off of replication.

## Next
[06 — SQL](../06-sql/README.md).
