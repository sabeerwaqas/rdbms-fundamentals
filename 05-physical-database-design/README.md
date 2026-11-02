# 05 — Physical Database Design

**Handout coverage:** Lectures 22–24

This section follows the handout's transition from normalized logical relations to technical decisions about storing and accessing data.

## Topics

- Data-volume and usage analysis.
- Field design and data-type selection.
- Coding techniques and data-integrity considerations.
- Grouping attributes and selecting physical storage structures.
- Partitioning and replication topics included in the handout.

## Logical versus physical design

Logical design describes the data structure and relationships. Physical design translates that structure into technical decisions for storage and retrieval. Choices at this stage depend on data volume, usage patterns, performance needs, security, backup requirements, and the selected DBMS.

## Practice direction

For a small database design, describe the expected data volume and access patterns. Choose suitable data types and explain the trade-offs behind those choices. Keep logical design decisions separate from DBMS-specific implementation choices.

## Completion checklist

- [ ] Notes on physical-design inputs and decisions.
- [ ] A small field and data-type design example.
- [ ] Exercises on usage analysis and physical-design trade-offs.
