---
share: true
---

Relational dbs have transactions, consistency and durability as principles
NoSql dbs relax some of these in order to gain performance


There is a valid though process we should go through when choosing between NoSQL dbs: 

- _Data and query model_: Is your data represented as rows, objects, data structures, or documents? Can you ask the database to calculate aggregates over multiple records?
- _Durability_: When you change a value, does it immediately go to stable storage? Does it get stored on multiple machines in case one crashes?
- _Scalability_: Does your data fit on a single server? Do the amount of reads and writes require multiple disks to handle the workload?
- _Partitioning_: For scalability, availability, or durability reasons, does the data need to live on multiple servers? How do you know which record is on which server?
- _Consistency_: If you've partitioned and replicated your records across multiple servers, how do the servers coordinate when a record changes?
- _Transactional semantics_: When you run a series of operations, some databases allow you to wrap them in a transaction, which provides some subset of ACID (Atomicity, Consistency, Isolation, and Durability) guarantees on the transaction and all others currently running. Does your business logic require these guarantees, which often come with performance tradeoffs?
- _Single-server performance_: If you want to safely store data on disk, what on-disk data structures are best-geared toward read-heavy or write-heavy workloads? Is writing to disk your bottleneck?
- _Analytical workloads_: We're going to pay a lot of attention to lookup-heavy workloads of the kind you need to run a responsive user-focused web application. In many cases, you will want to build dataset-sized reports, aggregating statistics across multiple users for example. Does your use-case and toolchain require such functionality?