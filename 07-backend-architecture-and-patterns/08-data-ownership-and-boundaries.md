# Data Ownership and Boundaries

## Why it matters
Clear ownership prevents data coupling and conflicting changes.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand data ownership. |
| Intermediate | Avoid shared databases across services. |
| Senior | Define contracts for shared data. |
| Principal | Enforce ownership and governance. |

## Key concepts
- Single source of truth per domain.
- Service boundaries and contracts.
- Data duplication vs shared tables.
- Ownership and stewardship.

## Detailed explanation
- **Single source of truth** avoids conflicting updates and unclear authority.
- **Service boundaries** define who can mutate data and how others read it.
- **Duplication** can improve performance but requires clear sync guarantees.
- **Stewardship** assigns accountable owners for schema changes and access.

## Real-world example: User profile ownership
The identity service owns user data; other services consume via API or events.

## Diagram
```mermaid
flowchart LR
  A[Identity service] --> B[User API]
  C[Orders service] --> B
  D[Support service] --> B
```

## Additional real-world examples
- Orders service consumes user updates via events instead of shared tables.
- Shared reporting DB is read-only with explicit data sync intervals.
- Ownership registry lists the team responsible for each dataset.

## Practical checklist
- Avoid direct database access across services.
- Use events or APIs for data sharing.
- Document ownership in system diagrams.

## Official documentation
- https://aws.amazon.com/microservices/
- https://learn.microsoft.com/en-us/azure/architecture/microservices/
