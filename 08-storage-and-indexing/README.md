# 08 — Storage, Hashing, and Indexing

**VU CS403 handout:** Lectures 35–38

This section explains how records can be organized and how a DBMS can locate them efficiently.

## 1. File organization

A database stores records in files/pages managed by the DBMS. File organization affects how records are located, inserted, and scanned. The appropriate approach depends on access patterns and update workload.

## 2. Hashing

Hashing applies a hash function to a search-key value to determine a bucket where the record or data entry can be found.

- **Bucket:** a storage location for records/data entries.
- **Hash function:** maps a key value to a bucket.
- **Collision:** different key values map to the same bucket.
- **Collision handling:** a method for storing/finding entries when a bucket is occupied or full.

Hash-based access is useful for equality lookups. It is not generally suitable for ordered range queries because hash values do not preserve key order.

## 3. Indexes

An index is an auxiliary structure that helps find rows without scanning the entire table. Its search key is the attribute or attributes used to locate entries; it does not have to be unique.

Example: an index on studentId can help find a student by registration number. An index on city can help search for students in a city even though many students may share that value.

## 4. Index trade-offs

Indexes can reduce lookup work, but they consume storage, need maintenance when data changes, and may slow inserts, updates, and deletes. An index is useful when it supports relevant query patterns.

## 5. Index classifications

The handout discusses index classification. Study the distinctions covered in Lectures 37–38, including primary/secondary, clustered/non-clustered, dense/sparse, and single-field/composite search keys. These labels describe different properties; they are not all mutually exclusive categories.

## Practice

1. Explain a hash collision using two keys mapped to the same bucket.
2. Why are hash files suited to equality lookup but not range lookup?
3. Give an example of a non-unique search key.
4. Name two costs of maintaining an index.
5. Why is indexing every column not automatically a good design?

## Next
[09 — Views and Transactions](../09-views-and-transactions/README.md).
