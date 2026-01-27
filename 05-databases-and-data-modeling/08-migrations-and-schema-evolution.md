# Migrations and Schema Evolution

## Why it matters
Schema changes can break production if not planned. Safe migrations allow
continuous delivery without downtime.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Apply simple schema changes safely. |
| Intermediate | Use expand/contract for compatibility. |
| Senior | Handle large backfills and long-running changes. |
| Principal | Define org-wide migration standards. |

## Key concepts
- Expand/contract patterns.
- Backward compatible changes.
- Online migrations and backfills.
- Feature flags and dual writes.

## Detailed explanation
- **Expand/contract** avoids breaking running code. Add new columns first,
  backfill, then remove old fields in a later deploy.
- **Backward compatibility** keeps old clients working during rollouts.
- **Online migrations** minimize locks by batching and throttling writes.
- **Dual writes** are useful during migrations but need reconciliation plans.

## Real-world example: Add a new column
Add `phone_number` as nullable, backfill, then enforce NOT NULL.

```mermaid
flowchart LR
  A[Add nullable column] --> B[Write new column]
  B --> C[Backfill old rows]
  C --> D[Enforce NOT NULL]
```

## Additional real-world examples
- Index created concurrently to avoid blocking writes during a deploy.
- Large backfill throttled during peak hours to reduce DB load.
- Old column removed only after verifying no reads for two release cycles.

## Practical checklist
- Avoid destructive changes in a single deploy.
- Measure backfill impact and throttle jobs.
- Ensure app code supports old and new schemas during rollout.

## Official documentation
- https://www.postgresql.org/docs/current/sql-altertable.html
- https://dev.mysql.com/doc/refman/8.0/en/innodb-online-ddl.html
