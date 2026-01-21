# Domain-Driven Design

## Why it matters
DDD helps align software models with business domains and reduces ambiguity.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Identify entities and aggregates. |
| Intermediate | Define bounded contexts. |
| Senior | Design contracts between contexts. |
| Principal | Align org boundaries with domain boundaries. |

## Key concepts
- Ubiquitous language.
- Entities, value objects, aggregates.
- Bounded contexts and context maps.

## Real-world example: Commerce domains
Orders and Billing use separate models to avoid coupling.

## Diagram
```mermaid
flowchart LR
  A[Orders context] --> B[Shared contract]
  C[Billing context] --> B
```

## Practical checklist
- Use a shared vocabulary with stakeholders.
- Keep aggregates small and consistent.
- Avoid cross-context direct database access.
