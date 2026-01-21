# File Systems and Storage

## Why it matters
Disk I/O is slower than memory. Understanding file systems helps avoid data
loss and performance bottlenecks.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Read/write files and understand buffering. |
| Intermediate | Understand fsync and durability. |
| Senior | Optimize I/O patterns and batching. |
| Principal | Define storage standards and data durability. |

## Key concepts
- File descriptors and buffering.
- fsync, durability, and write barriers.
- Sequential vs random I/O.
- File system journaling.

## Real-world example: Log ingestion
A log service batches writes and fsyncs on intervals to balance durability and
throughput.

## Diagram
```mermaid
flowchart LR
  A[App write] --> B[OS buffer]
  B --> C[Disk write]
  C --> D[fsync]
```

## Practical checklist
- Batch small writes to reduce overhead.
- Use fsync for critical data.
- Monitor disk queue depth and latency.
