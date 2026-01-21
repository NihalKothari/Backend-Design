# Clean Code and Refactoring

## Why it matters
Clean code lowers cognitive load and makes maintenance cheaper.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use clear naming and small functions. |
| Intermediate | Refactor safely with tests. |
| Senior | Reduce complexity and tech debt. |
| Principal | Define code quality standards. |

## Key concepts
- Naming conventions and readability.
- Refactoring patterns: extract function, simplify conditionals.
- Cyclomatic complexity and code smells.
- Incremental improvements with tests.

## Real-world example: Payment rules refactor
A payment rule engine has nested conditions. The team extracts rules into
smaller functions and adds unit tests.

## Diagram
```mermaid
flowchart LR
  A[Complex function] --> B[Extract functions]
  B --> C[Add tests]
  C --> D[Verify behavior]
```

## Practical checklist
- Refactor in small, reviewable steps.
- Add tests before structural changes.
- Avoid premature abstraction.
