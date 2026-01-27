# CQRS and Event Sourcing

## Why it matters
Separating reads and writes can improve scalability and auditability.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand command vs query separation. |
| Intermediate | Model read and write stores. |
| Senior | Apply event sourcing for audit trails. |
| Principal | Decide when CQRS is worth the complexity. |

## Key concepts
- CQRS: separate read and write models.
- Event sourcing and append-only logs.
- Projections and read models.
- Rebuild and replay strategies.

## Detailed explanation
- **CQRS** splits write models (commands) from read models (queries) to optimize
  each side independently.
- **Event sourcing** stores changes as immutable events, enabling audit trails.
- **Projections** build query-optimized views from the event stream.
- **Replays** require versioned events and careful backfill procedures.

## Real-world example: Audit trail
A finance system stores all account changes as events and builds balances from
projections.

## Diagram
```mermaid
flowchart LR
  A[Command] --> B[Event store]
  B --> C[Projection]
  C --> D[Read model]
```

## Additional real-world examples
- Ledger service stores every balance change as an event for auditing.
- Read model rebuilt after a projection bug using event replay.
- Projection workers scale independently from write throughput.

## Practical checklist
- Use CQRS when read/write needs differ significantly.
- Ensure event schemas are versioned.
- Plan for event replay and backfill.

## Official documentation
- https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs
