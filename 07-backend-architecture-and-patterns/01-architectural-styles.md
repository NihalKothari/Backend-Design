# Architectural Styles

## Why it matters
Architecture style determines team autonomy, deployment speed, and system
complexity.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand monoliths and microservices. |
| Intermediate | Evaluate modular monoliths. |
| Senior | Choose style based on org size and needs. |
| Principal | Set reference architectures and guardrails. |

## Key concepts
- Monolith, modular monolith, microservices.
- Service boundaries and deployment units.
- Tradeoffs: complexity vs autonomy.

## Real-world example: Startup evolution
A startup starts with a modular monolith, then extracts payments into a
separate service as scale and compliance needs grow.

## Diagram
```mermaid
flowchart LR
  A[Monolith] --> B[Modular monolith]
  B --> C[Microservices]
```

## Practical checklist
- Start simple and extract only when needed.
- Align architecture with team structure.
- Document boundaries before splitting services.
