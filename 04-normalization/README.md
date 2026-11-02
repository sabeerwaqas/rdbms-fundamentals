# 04 — Normalization

**Handout coverage:** Lectures 19–21

This section follows the handout's normalization sequence, including functional dependencies and the normal forms discussed in the course.

## Topics

- Why normalization is used and which data anomalies it aims to reduce.
- Functional dependencies and their role in identifying redundancy.
- First, Second, and Third Normal Forms.
- Boyce–Codd Normal Form and the higher normal forms mentioned in the handout.
- Decomposition and checking whether the resulting relations preserve the information needed by the design.

## A repeatable method

1. Write the relation and identify its candidate key or keys.
2. Identify the functional dependencies supported by the scenario.
3. Look for repeated facts and insertion, update, or deletion anomalies.
4. Apply the relevant normal-form rules one step at a time.
5. Show the resulting relations and their keys.
6. Explain why each decomposition is appropriate.

Do not normalize by guessing dependencies from sample rows alone. Dependencies should come from the meaning and rules of the data.

## Practice direction

Start with a relation containing repeated facts. Identify its key and functional dependencies, describe the anomalies, and normalize it step by step. Explain each decomposition rather than only presenting the final tables.

## Completion checklist

- [ ] One worked normalization example from an unnormalized relation.
- [ ] Clear explanations of the dependencies used in the example.
- [ ] Practice questions with checked solutions.
