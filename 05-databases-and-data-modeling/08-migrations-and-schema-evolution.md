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

## Real-world example: Add a new column
Add `phone_number` as nullable, backfill, then enforce NOT NULL.

```mermaid
flowchart LR
  A[Add nullable column] --> B[Write new column]
  B --> C[Backfill old rows]
  C --> D[Enforce NOT NULL]
```

## Practical checklist
- Avoid destructive changes in a single deploy.
- Measure backfill impact and throttle jobs.
- Ensure app code supports old and new schemas during rollout.
