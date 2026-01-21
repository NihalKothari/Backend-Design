# Test Data and Fixtures

## Why it matters
Good test data makes tests reliable and easy to understand.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Create minimal fixtures. |
| Intermediate | Use factories and builders. |
| Senior | Isolate test data per suite. |
| Principal | Standardize data management practices. |

## Key concepts
- Fixtures vs factories.
- Data seeding and cleanup.
- Deterministic test data.

## Real-world example: User fixtures
Tests create a small set of known users and clean them after each run.

## Diagram
```mermaid
flowchart LR
  A[Create fixtures] --> B[Run tests]
  B --> C[Cleanup]
```

## Practical checklist
- Keep fixtures small and explicit.
- Reset state between tests.
- Avoid sharing mutable data across suites.
