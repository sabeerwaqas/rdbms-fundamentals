# 09 — Views and Transaction Management

**Handout coverage:** Lectures 39–45

This final section follows the handout's material on views and transaction management.

## Topics

- Views and their role in presenting selected data.
- Creating views and limitations when updating views.
- Transactions as units of work.
- ACID properties.
- Concurrency-control problems.
- Serial and interleaved schedules, serializability, and locking.
- Other transaction-management topics covered in the final lectures.

## Think in transactions

A bank transfer may involve debiting one account and crediting another. Treating the two operations as a single transaction helps prevent a partially completed transfer from leaving the data inconsistent. Use this example to reason about atomicity, consistency, isolation, and durability.

## Practice direction

Describe a two-step bank transfer as a transaction. Identify what could go wrong if only one step completes, then explain how transaction properties and concurrency control help protect consistency. Use small schedules when practising concurrency concepts.

## Completion checklist

- [ ] One view example with a clear explanation of its purpose.
- [ ] One transaction walkthrough using ACID properties.
- [ ] Schedule and locking practice with checked explanations.
