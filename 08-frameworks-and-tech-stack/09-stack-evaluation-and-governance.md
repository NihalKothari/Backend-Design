# Stack Evaluation and Governance

## Why it matters
Consistent stack choices reduce operational risk and improve maintainability.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Learn why standards exist. |
| Intermediate | Evaluate tradeoffs for a service. |
| Senior | Propose changes with evidence. |
| Principal | Define standards, reviews, and exceptions. |

## Key concepts
- Decision criteria: performance, cost, maintainability.
- Upgrade cadence and deprecation policies.
- Exception process and risk review.

## Detailed explanation
- **Decision criteria** should be explicit and weighted (latency, cost, support).
- **Upgrade cadence** reduces security risk and avoids large, risky jumps.
- **Exceptions** need clear ownership, timelines, and risk mitigation plans.

## Real-world example: New framework proposal
A team proposes a new framework and documents risks, maintenance cost, and a
support plan before approval.

## Diagram
```mermaid
flowchart LR
  A[Proposal] --> B[Review]
  B --> C[Decision]
  C --> D[Adopt or reject]
```

## Additional real-world examples
- New framework approved only after a pilot service meets SLOs.
- Deprecation policy includes a 6-month support window with migration guides.
- Tech radar tracks experiments vs approved stacks.

## Practical checklist
- Require evidence for new tech adoption.
- Document ownership and support plans.
- Revisit decisions on a fixed cadence.

## Official documentation
- https://learn.microsoft.com/en-us/azure/architecture/guide/decision-making
- https://learn.microsoft.com/en-us/azure/architecture/framework/
