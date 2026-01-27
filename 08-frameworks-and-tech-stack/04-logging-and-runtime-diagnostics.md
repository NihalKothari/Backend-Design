# Logging and Runtime Diagnostics

## Why it matters
Logs and runtime diagnostics are essential for debugging production issues.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use structured logging basics. |
| Intermediate | Add correlation IDs and log levels. |
| Senior | Standardize logging across services. |
| Principal | Define retention and privacy rules. |

## Key concepts
- Structured logs and JSON output.
- Log levels and sampling.
- Correlation IDs and tracing fields.

## Detailed explanation
- **Structured logs** improve searchability and aggregation in log systems.
- **Log levels** separate signal from noise; sampling reduces cost on hot paths.
- **Correlation IDs** connect logs across services for end-to-end debugging.

## Real-world example: Payment tracing
A payment request logs a correlation ID that appears in every downstream log.

## Diagram
```mermaid
flowchart LR
  A[Service] --> B[Log sink]
  B --> C[Search and alerts]
```

## Additional real-world examples
- Warning logs sampled to 10 percent during peak traffic to control cost.
- Log fields include tenant ID for faster customer support investigations.
- Runtime diagnostics endpoint exposes health and build metadata.

## Practical checklist
- Log one line per event with key fields.
- Avoid logging PII or secrets.
- Keep log formats consistent across services.

## Official documentation
- https://opentelemetry.io/docs/
- https://www.rfc-editor.org/rfc/rfc5424
