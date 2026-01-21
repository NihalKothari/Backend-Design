# Observability and Operations

## Why it matters
Without visibility, database issues become outages. Observability enables early
warnings, capacity planning, and faster recovery.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Track basic metrics and logs. |
| Intermediate | Monitor slow queries and index usage. |
| Senior | Define SLOs and run capacity reviews. |
| Principal | Standardize dashboards and alert policies. |

## Key concepts
- Metrics: latency, throughput, errors, saturation.
- Slow query logs and query analytics.
- Index usage, bloat, and vacuum metrics.
- Capacity planning and forecasting.

## Real-world example: Marketplace latency alerts
The marketplace alerts on p99 query latency and replica lag during sales peaks.

```mermaid
flowchart LR
  A[DB metrics] --> B[Metrics collector]
  B --> C[Dashboard]
  B --> D[Alert rules]
  D --> E[On-call]
```

## Practical checklist
- Track p95 and p99 query latency per service.
- Alert on replica lag and storage utilization.
- Review slow query logs weekly.
