# Database Performance Patterns

## Why it matters
Databases are often the bottleneck. Query patterns determine latency and cost.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Avoid obvious N+1 queries. |
| Intermediate | Use indexes and batching. |
| Senior | Analyze query plans and tune schema. |
| Principal | Define DB performance standards. |

## Key concepts
- N+1 query pattern and batching.
- Indexing and covering indexes.
- Query plan analysis.

## Real-world example: Order list
Instead of loading items per order, fetch all items in a single query.

## Diagram
```mermaid
flowchart LR
  A[N+1 queries] --> B[Many DB calls]
  C[Batched query] --> D[Single DB call]
```

## Practical checklist
- Use batch queries for related data.
- Index columns used in WHERE/ORDER BY.
- Review slow query logs regularly.
