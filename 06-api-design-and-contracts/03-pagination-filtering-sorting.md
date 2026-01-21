# Pagination, Filtering, Sorting

## Why it matters
Large datasets require consistent pagination and filtering to avoid slow
queries and unstable results.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use basic pagination parameters. |
| Intermediate | Implement stable sorting and filtering. |
| Senior | Use cursor-based pagination at scale. |
| Principal | Set org-wide list and filter standards. |

## Key concepts
- Offset vs cursor pagination.
- Filter syntax and allow-lists.
- Stable sorting with tie-breakers.
- Sparse fieldsets to reduce payload size.

## Real-world example: Orders list
A dashboard uses cursor pagination and filters by status.

```
GET /orders?status=paid&limit=50&cursor=2024-01-10T10:12:00Z
```

## Diagram
```mermaid
flowchart LR
  A[Client] --> B[Query + cursor]
  B --> C[Stable sort + filter]
  C --> D[Page results]
```

## Practical checklist
- Use stable ordering for pagination.
- Validate filter fields server-side.
- Keep default limits conservative.
