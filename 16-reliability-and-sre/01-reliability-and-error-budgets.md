# Reliability Principles and Error Budgets

## Why it matters
Error budgets balance reliability and delivery speed.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand reliability goals. |
| Intermediate | Track error budgets. |
| Senior | Use budgets to prioritize work. |
| Principal | Define org-wide reliability policies. |

## Key concepts
- SLIs and SLOs.
- Error budgets and burn rate.
- Reliability vs velocity tradeoffs.

## Real-world example: Search service
Search has a 99.9% SLO. When the error budget is exhausted, releases pause.

## Diagram
```mermaid
flowchart LR
  A[SLO target] --> B[Error budget]
  B --> C[Release policy]
```

## Practical checklist
- Define SLIs for critical user journeys.
- Track budget burn rate.
- Link budgets to release decisions.
