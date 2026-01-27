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

## Detailed explanation
- **Monoliths** simplify deployment and debugging but can slow team autonomy as
  codebases grow.
- **Modular monoliths** keep single deploys while enforcing internal boundaries.
- **Microservices** enable independent scaling and deployments but increase
  operational complexity and coordination costs.
- **Service boundaries** should align with ownership and data responsibilities.

## Real-world example: Startup evolution
A startup starts with a modular monolith, then extracts payments into a
separate service as scale and compliance needs grow.

## Diagram
```mermaid
flowchart LR
  A[Monolith] --> B[Modular monolith]
  B --> C[Microservices]
```

## Additional real-world examples
- Compliance requirements drive isolation of PII into a dedicated service.
- A monolith stays in place but adds module boundaries and interface contracts.
- A service split is rolled back after operational overhead outweighs benefits.

## Practical checklist
- Start simple and extract only when needed.
- Align architecture with team structure.
- Document boundaries before splitting services.

## Official documentation
- https://aws.amazon.com/microservices/
- https://learn.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices
