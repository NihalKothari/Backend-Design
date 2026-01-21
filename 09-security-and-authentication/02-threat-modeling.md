# Threat Modeling

## Why it matters
Threat modeling identifies risks early and prioritizes mitigation work.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Identify assets and entry points. |
| Intermediate | Use STRIDE or similar frameworks. |
| Senior | Prioritize risks and mitigations. |
| Principal | Make threat modeling a standard practice. |

## Key concepts
- Assets, threats, and attack surfaces.
- STRIDE categories.
- Risk impact and likelihood.

## Real-world example: Payment API
The team models threats like credential stuffing and replay attacks.

## Diagram
```mermaid
flowchart LR
  A[User] --> B[API Gateway]
  B --> C[Payments service]
  C --> D[Bank]
```

## Practical checklist
- Document assets and critical flows.
- Identify trust boundaries.
- Track mitigations and owners.
