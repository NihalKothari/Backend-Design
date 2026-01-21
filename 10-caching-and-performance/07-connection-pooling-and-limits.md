# Connection Pooling and Limits

## Why it matters
Unbounded connections can overload databases and cause cascading failures.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use a connection pool. |
| Intermediate | Tune pool sizes for workload. |
| Senior | Apply backpressure and timeouts. |
| Principal | Define connection policies across services. |

## Key concepts
- Pool size and queue limits.
- Connection timeouts and retries.
- Backpressure and load shedding.

## Real-world example: API spike
A sudden traffic spike exhausts DB connections. Pool limits prevent overload
and shed excess traffic.

## Diagram
```mermaid
flowchart LR
  A[Requests] --> B[Connection pool]
  B --> C[Database]
  B --> D[Queue]
```

## Practical checklist
- Set max connections per service.
- Use timeouts for pool acquisition.
- Monitor pool saturation and queue depth.
