# 01 — Database Fundamentals

**Handout coverage:** Lectures 1–6

This section introduces databases and DBMSs, explains why organizations use database systems, and places database design in the wider development process.

## Learning goals

After studying this section, you should be able to:

- Distinguish data from information and explain the role of a database schema.
- Describe the purpose of a DBMS and compare file processing with the database approach.
- Explain important benefits and costs of using a DBMS.
- Identify database users and describe the levels of database architecture covered in the handout.
- Outline the database application development process and explain the purpose of data-flow diagrams.

## Core concepts

### Data, information, and schema

**Data** consists of recorded facts. **Information** is data processed or interpreted so that it has meaning for a particular purpose. A **schema** describes the structure and organization of a database; it is not the actual collection of business facts.

### Database and DBMS

A **database** is an organized collection of related data. A **database management system (DBMS)** is software used to define, store, retrieve, update, and manage that data, including controlling access to it.

A database and a DBMS are not the same thing: one is the data being managed, and the other is the software that manages it.

### Why use a DBMS?

The database approach can support controlled data sharing, reduced unnecessary duplication, integrity, security, and data independence. It also introduces costs such as software, hardware, administration, maintenance, training, and operational complexity. Whether a DBMS is appropriate depends on the needs of the system.

### Development process

The handout introduces database application development through database design, application programs, and implementation. These activities can overlap rather than always being performed as isolated stages. Data-flow diagrams help represent how data moves through a system and support the analysis that precedes design.

## Check your understanding

1. Explain the difference between data, information, a database, and a DBMS.
2. Give two examples of problems that controlled redundancy can help prevent.
3. Why does data independence matter to an application that uses a database?
4. Name two costs an organization should consider before adopting a DBMS.
5. What does a data-flow diagram help an analyst understand?

## Practice

Choose a familiar system, such as a library, clinic, or university registration system. List the data it needs to store, identify two groups of users, and describe three operations those users need to perform. Then explain why a database approach may be suitable.
