# Programming Fundamentals

## Why it matters
Backend systems are built from simple building blocks. Strong fundamentals make
your code predictable and easier to reason about under pressure.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Variables, control flow, and functions. |
| Intermediate | Modularize code and reuse functions safely. |
| Senior | Design APIs and handle edge cases consistently. |
| Principal | Set coding standards and review guidelines. |

## Key concepts
- Data types, variables, and operators.
- Control flow: if/else, loops, early returns.
- Functions and parameter passing.
- Input validation and basic error handling.

## Detailed explanation
- **Data types and variables** define how values are stored and manipulated.
  Choosing the right type prevents bugs (for example, using integers for counts
  and decimals for money) and avoids accidental type coercion.
- **Control flow** determines which code executes under which conditions.
  Early returns reduce nesting and make error paths clear, which matters when
  handling invalid inputs or partial failures.
- **Functions** turn repeated logic into reusable building blocks. Treat
  function boundaries as small APIs: define clear inputs, outputs, and side
  effects to keep behavior predictable.
- **Input validation** is your first line of defense. Validate at boundaries,
  return actionable errors, and avoid passing bad data deeper into the system.

## Real-world example: Simple rate limiter
A small script rejects requests after a threshold.

```python
def allow_request(count, limit):
    if count >= limit:
        return False
    return True
```

## Diagram
```mermaid
flowchart TD
  A[Request] --> B{count >= limit?}
  B -- yes --> C[Reject]
  B -- no --> D[Allow]
```

## Practical checklist
- Use guard clauses for invalid input.
- Keep functions small and focused.
- Write tests for common and edge cases.
