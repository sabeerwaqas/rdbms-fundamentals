# 06 — Structured Query Language (SQL)

**Handout coverage:** Lectures 25–31

This section follows the SQL topics in the handout, from defining database structures to retrieving and changing data.

## Topics

- SQL command structure and basic syntax.
- Data Definition Language (DDL) and Data Manipulation Language (DML).
- Filtering and sorting query results.
- Aggregate functions and grouping.
- Joins and combining data from multiple relations.
- Data Control Language (DCL), including the `GRANT` and `REVOKE` commands discussed in the handout.

## SQL dialect policy

The handout's examples refer to Microsoft SQL Server 2000 and Query Analyzer. This is historical course material; the current CS403P lab engine must be confirmed before choosing a target dialect for executable scripts.

The repository will explain the SQL concept first and identify the dialect for each executable example. Do not assume that all examples are portable across database engines.

## Practice direction

Use a small relational schema and build queries progressively: define the structure, insert sample rows, retrieve filtered data, aggregate results, and join related tables. Every script must state the engine and version against which it was tested.

## Completion checklist

- [ ] Organize notes in the same sequence as the handout.
- [ ] Confirm the current CS403P database engine.
- [ ] Add tested scripts with sample data and expected output.
