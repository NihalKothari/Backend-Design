# Async Processing and Batching

## Why it matters
Async processing reduces user latency and batching improves throughput.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Offload work to background jobs. |
| Intermediate | Batch writes and reads. |
| Senior | Balance latency vs batch size. |
| Principal | Standardize async patterns. |

## Key concepts
- Queues and background workers.
- Batch size and flush intervals.
- Backpressure and retry handling.

## Detailed explanation
- **Queues** decouple producers from consumers and absorb spikes.
- **Batch sizes** trade latency for throughput; tune based on SLA.
- **Retry handling** should avoid infinite loops and use dead-letter queues.

## Real-world example: Analytics events
Events are buffered and written to storage in batches to reduce I/O overhead.

## Diagram
```mermaid
flowchart LR
  A[Events] --> B[Buffer]
  B --> C[Batch write]
  C --> D[Storage]
```

## Additional real-world examples
- Payments service batches ledger writes every 50 ms to reduce I/O.
- Event processor uses a max batch size to bound memory.
- Dead-letter queue alerts on repeated failures.

## Practical checklist
- Use async for slow side effects.
- Set batch limits and timeouts.
- Monitor queue depth and lag.

## Official documentation
- https://kafka.apache.org/documentation/
