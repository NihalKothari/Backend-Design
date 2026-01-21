# Observability and Network Debugging

## Why it matters
Network issues often appear as latency spikes and intermittent failures.
Observability makes these issues diagnosable and repeatable.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Collect logs, metrics, and traces. |
| Intermediate | Correlate requests across services. |
| Senior | Use tracing to pinpoint slow hops. |
| Principal | Define observability standards and SLIs. |

## Key concepts
- Distributed tracing and correlation IDs.
- Metrics: latency, error rate, throughput.
- Structured logs and request context.
- Synthetic checks and network probes.

## Real-world example: API gateway latency regression
A new proxy rule increases latency. Traces show the delay at the gateway,
and a config rollback restores performance.

## Diagram
```mermaid
flowchart LR
  A[Client] --> B[API Gateway]
  B --> C[Service A]
  C --> D[Service B]
  B -. trace span .-> B
  C -. trace span .-> C
  D -. trace span .-> D
```

## Practical checklist
- Propagate trace IDs across every hop.
- Alert on p95 and p99 latency at the edge.
- Keep request logs structured and searchable.
