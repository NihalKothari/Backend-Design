# Structures and Modularity

## Why it matters
Well-structured code scales with the team. Modularity reduces coupling and
makes changes safer.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use structs/classes to group data. |
| Intermediate | Apply interfaces and composition. |
| Senior | Create stable module boundaries. |
| Principal | Define shared libraries and conventions. |

## Key concepts
- Structs/classes and encapsulation.
- Interfaces and dependency inversion.
- Composition over inheritance.
- Modules and packaging.

## Detailed explanation
- **Structs/classes and encapsulation** group related data and behavior. By
  hiding internal details behind methods, you reduce the chance that callers
  rely on implementation specifics.
- **Interfaces** define contracts between components. When higher-level code
  depends on interfaces instead of concrete implementations, swapping
  dependencies or testing becomes much easier.
- **Composition over inheritance** favors small, reusable parts that can be
  combined. Deep inheritance hierarchies are hard to reason about and often
  leak state in unexpected ways.
- **Modules and packaging** set boundaries for ownership and reuse. A good
  module exposes a small public surface and keeps internal helpers private.

## Real-world example: Notification providers
An app sends notifications via email or SMS. A common interface makes it easy
to add providers.

```python
class Notifier:
    def send(self, user_id, message):
        raise NotImplementedError()

class EmailNotifier(Notifier):
    def send(self, user_id, message):
        return True

class SmsNotifier(Notifier):
    def send(self, user_id, message):
        return True
```

## Diagram
```mermaid
flowchart LR
  A[Service] --> B[Notifier interface]
  B --> C[Email notifier]
  B --> D[SMS notifier]
```

## Practical checklist
- Keep modules small and cohesive.
- Avoid cyclic dependencies.
- Prefer composition to deep inheritance chains.
