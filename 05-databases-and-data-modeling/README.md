# Databases and Data Modeling

This module takes a developer from fundamentals to principal-level database
design. Each subtopic file includes key concepts, a real-world example, and
at least one diagram.

## Progression expectations

| Level | Outcomes |
| --- | --- |
| Beginner | Model entities and write basic SQL queries. |
| Intermediate | Use indexes, transactions, and normalization effectively. |
| Senior | Plan migrations, tune queries, and handle replication. |
| Principal | Select tech, define data ownership, and plan DR. |

## How to use this module
- Start at Fundamentals and proceed in order.
- Build a small artifact per subtopic (diagram, query, or plan).
- Revisit advanced sections as you move up the ladder.

## Subtopics
1. [Fundamentals](01-fundamentals.md) - Relational vs NoSQL, SQL basics, keys.
2. [Data Modeling](02-data-modeling.md) - ER design, normalization, constraints.
3. [Querying and Performance](03-querying-and-performance.md) - Indexes, EXPLAIN, pagination.
4. [Transactions and Consistency](04-transactions-and-consistency.md) - ACID, isolation, locks.
5. [Storage Engines and Internals](05-storage-engines-and-internals.md) - WAL, buffer pool, indexing.
6. [Scaling and Distributed Data](06-scaling-and-distributed-data.md) - Replication, sharding, rebalancing.
7. [Reliability and Disaster Recovery](07-reliability-and-disaster-recovery.md) - Backups, PITR, RPO/RTO.
8. [Migrations and Schema Evolution](08-migrations-and-schema-evolution.md) - Expand/contract, backfills.
9. [Security and Governance](09-security-and-governance.md) - RBAC, encryption, retention.
10. [Observability and Operations](10-observability-and-operations.md) - Metrics, slow queries, capacity.
11. [Specialized Datastores](11-specialized-datastores.md) - OLTP vs OLAP, search, time-series.

## Suggested artifacts
- Data model diagram for a real domain.
- Index and query performance report using EXPLAIN.
- Migration plan with rollback steps.
- DR runbook with RPO/RTO targets.
- Security and governance checklist.
