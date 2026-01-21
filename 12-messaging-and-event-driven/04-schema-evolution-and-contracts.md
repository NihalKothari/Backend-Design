# Schema Evolution and Contracts

## Why it matters
Event schemas change over time. Compatibility rules prevent breaking consumers.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use versioned schemas. |
| Intermediate | Apply backward-compatible changes. |
| Senior | Enforce schema registry policies. |
| Principal | Define org-wide contract governance. |

## Key concepts
- Backward/forward compatibility.
- Schema registries and validation.
- Default values and optional fields.

## Real-world example: Add field safely
Add an optional `coupon_code` field with a default value.

## Diagram
```mermaid
flowchart LR
  A[Schema v1] --> B[Schema v2]
  B --> C[Old consumers still work]
```

## Practical checklist
- Use schema registries when possible.
- Avoid removing fields abruptly.
- Test consumers against new versions.
