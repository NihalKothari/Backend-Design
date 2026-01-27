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

## Detailed explanation
- **Naming and readability** reduce cognitive load. Clear names make intent
  obvious and reduce the need for comments or guesswork.
- **Refactoring patterns** change structure without changing behavior. Small
  steps like extracting functions or simplifying conditionals are safer and
  easier to review.
- **Cyclomatic complexity** signals risk. High-complexity functions are harder
  to test and more likely to contain subtle bugs.
- **Incremental refactoring with tests** provides safety. Add tests before
  structural changes to prevent regressions.
- **Duplication removal** reduces divergence. When the same logic appears in
  multiple places, bugs are fixed once instead of many times.
- **Boundary refactors** clarify ownership. Moving validation to API edges or
  persistence logic to repositories simplifies call sites.

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

## Additional real-world examples
- Refactoring request validation into a shared helper so all endpoints enforce
  the same rules.
- Replacing nested conditionals with early returns in a feature-flag check.
- Splitting a large service class into smaller modules by responsibility.

## Practical checklist
- Refactor in small, reviewable steps.
- Add tests before structural changes.
- Avoid premature abstraction.

## Official documentation
- https://go.dev/doc/effective_go
- https://docs.python.org/3/faq/design.html
- https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/
