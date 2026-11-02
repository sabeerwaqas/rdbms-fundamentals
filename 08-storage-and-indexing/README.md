# 08 — Storage, Hashing, and Indexing

**Handout coverage:** Lectures 35–38

This section covers the storage and access topics grouped in this part of the handout.

## Topics

- File organization and the way records are stored.
- Hashing and collision handling.
- Indexes and their purpose in supporting data retrieval.
- Index classifications discussed in the handout, including clustered/non-clustered, dense/sparse, and primary/secondary distinctions where applicable.
- Composite search keys.

## Key trade-off

An index can provide a faster access path for selected queries, but it also consumes storage and may add work when data is inserted, updated, or deleted. Indexes should be discussed in terms of the access patterns they support, not as an automatic improvement for every column.

## Practice direction

Compare a table scan with an indexed lookup. Then work through a small hashing example and show how a collision is handled. Explain the storage and update overhead that comes with indexes.

## Completion checklist

- [ ] Notes on file organization and hashing.
- [ ] One worked collision-handling example.
- [ ] One index-classification comparison and practice questions.
