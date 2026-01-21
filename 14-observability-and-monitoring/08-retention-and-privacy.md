# Retention and Privacy

## Why it matters
Logs and traces can contain sensitive data. Retention policies reduce risk and
cost.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand retention policies. |
| Intermediate | Apply redaction and masking. |
| Senior | Balance compliance and operational needs. |
| Principal | Define org-wide privacy standards. |

## Key concepts
- Retention periods by data type.
- PII redaction and masking.
- Sampling and storage costs.

## Real-world example: Log retention
Debug logs are kept for 7 days, audit logs for 1 year, with PII redaction.

## Diagram
```mermaid
flowchart LR
  A[Logs] --> B[Redaction]
  B --> C[Retention tiers]
```

## Practical checklist
- Redact PII in logs and traces.
- Define retention tiers by data sensitivity.
- Review retention policy annually.
