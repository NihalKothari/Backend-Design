# Event Sourcing vs Event-Driven

## Why it matters
Event-driven systems use events for communication; event sourcing uses events
as the source of truth.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand the difference. |
| Intermediate | Identify use cases for event sourcing. |
| Senior | Manage projections and replays. |
| Principal | Decide when event sourcing is worth the complexity. |

## Key concepts
- Event-driven architecture and messaging.
- Event sourcing and append-only logs.
- Projections and rebuilding state.

## Real-world example: Audit-ready ledger
A ledger uses event sourcing to reconstruct account balances and provide a full
audit trail.

## Diagram
```mermaid
flowchart LR
  A[Commands] --> B[Event store]
  B --> C[Projections]
  C --> D[Read models]
```

## Practical checklist
- Use event sourcing when auditability is critical.
- Plan for replay and projection rebuilds.
- Keep events immutable.
