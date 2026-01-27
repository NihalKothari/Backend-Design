# Error Handling and Logging

## Why it matters
Errors happen in production. Consistent error handling and logs speed up
debugging and reduce outages.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Return errors and avoid silent failures. |
| Intermediate | Standardize error codes and messages. |
| Senior | Use structured logs and correlation IDs. |
| Principal | Define logging standards and retention policies. |

## Key concepts
- Error propagation vs swallowing errors.
- Typed errors and error codes.
- Structured logging and log levels.
- Correlation IDs for request tracing.

## Detailed explanation
- **Error propagation** means returning failures to the caller with context.
  Swallowing errors hides problems and makes incidents harder to diagnose.
- **Typed errors and codes** let clients act on failures (retry, fix input, or
  escalate). Stable error codes also help with analytics and alerting.
- **Structured logging** emits consistent fields (timestamp, level, request ID)
  to enable filtering and correlation. Free-form logs are harder to search.
- **Correlation IDs** tie a request across services and logs. They should be
  generated at the edge and propagated through every hop.
- **Error classification** separates retryable failures (timeouts) from
  non-retryable ones (invalid input). That distinction drives safer retry and
  alerting behavior.
- **Log hygiene** matters. Sample noisy logs, redact secrets, and avoid logging
  entire payloads unless needed for debugging.

## Real-world example: API error response
A service returns a consistent error shape with a request ID for debugging.

```json
{
  "error": {
    "code": "USER_NOT_FOUND",
    "message": "User does not exist",
    "request_id": "req-7f9a"
  }
}
```

## Diagram
```mermaid
flowchart LR
  A[Request] --> B[Handler]
  B --> C{Error?}
  C -- no --> D[Success response]
  C -- yes --> E[Log error]
  E --> F[Error response]
```

## Additional real-world examples
- Ingress generates a request ID, forwards it via headers, and every service
  logs it to stitch traces during incident response.
- Payment API returns a stable error code that maps to a user-friendly message
  in the UI and a retry policy in the backend.
- Background jobs log failures with job ID and attempt number to distinguish
  transient from permanent errors.

## Practical checklist
- Never hide errors; return or log them.
- Add request IDs to logs and responses.
- Avoid logging sensitive data.

## Official documentation
- https://www.rfc-editor.org/rfc/rfc9457
- https://www.w3.org/TR/trace-context/
- https://opentelemetry.io/docs/concepts/context-propagation/
