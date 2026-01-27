# Storage Engines and Internals

## Why it matters
Engine internals determine performance, durability, and operational behavior.
Knowing how writes and reads flow helps you tune the system.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Know that engines differ in behavior and guarantees. |
| Intermediate | Understand WAL, buffer pool, and indexing basics. |
| Senior | Tune engine settings for workload patterns. |
| Principal | Choose engines based on operational tradeoffs. |

## Key concepts
- WAL or redo logs and checkpoints.
- Buffer pool and page cache behavior.
- B-tree indexes and page splits.
- Compaction and vacuum in log-structured engines.

## Detailed explanation
- **WAL/redo logs** allow crash recovery by replaying committed changes.
- **Buffer pools** keep hot pages in memory; low hit rates indicate I/O
  pressure and poor cache sizing.
- **B-tree page splits** can fragment data; sequential keys often reduce splits.
- **Log-structured engines** trade write speed for background compaction work.

## Real-world example: Order service write path
An order service uses InnoDB to get crash recovery and row-level locking.

```mermaid
flowchart LR
  A[App writes order] --> B[DB receives write]
  B --> C[WAL / redo log]
  B --> D[Buffer pool]
  D --> E[Data pages to disk]
  C --> E
```

## Additional real-world examples
- Write-heavy tables move to an LSM engine to improve ingest throughput.
- Buffer pool increased after monitoring showed frequent disk reads.
- Vacuum tuned to reclaim space after large deletes.

## Practical checklist
- Monitor buffer pool hit rate and disk IO.
- Size redo logs and checkpoints to match write volume.
- Avoid over-indexing write-heavy tables.

## Official documentation
- https://dev.mysql.com/doc/refman/8.0/en/innodb-storage-engine.html
- https://www.postgresql.org/docs/current/wal-intro.html
- https://github.com/facebook/rocksdb/wiki
