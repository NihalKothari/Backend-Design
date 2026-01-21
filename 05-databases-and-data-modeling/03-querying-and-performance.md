# Querying and Performance

## Why it matters
Performance issues are often data access problems. Indexing and query design
directly affect latency, cost, and user experience.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Write correct queries and joins. |
| Intermediate | Use indexes and EXPLAIN to reduce scans. |
| Senior | Choose pagination and query patterns for scale. |
| Principal | Set performance budgets and query standards. |

## Key concepts
- Index types: B-tree, hash, composite, covering.
- Query plans and EXPLAIN output.
- Pagination: offset vs cursor.
- N+1 query pattern and query batching.

## Real-world example: Support ticket search
A support tool lists open tickets ordered by newest first. Use a composite
index to avoid a full table scan and apply cursor-based pagination.

```sql
CREATE INDEX idx_tickets_status_created_at
ON tickets (status, created_at DESC);

SELECT id, subject, created_at
FROM tickets
WHERE status = 'open'
  AND created_at < :cursor
ORDER BY created_at DESC
LIMIT 50;
```

## Diagram
```mermaid
flowchart LR
  Q[Query] --> P{Index usable?}
  P -- yes --> I[Index scan]
  P -- no --> F[Full table scan]
  I --> R[Rows returned]
  F --> R
```

## Practical checklist
- Index columns used in WHERE and ORDER BY together.
- Use cursor pagination for large datasets.
- Inspect query plans and track slow queries over time.
