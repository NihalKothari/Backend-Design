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

## Detailed explanation
- **File descriptors** represent open file handles. Each read/write is buffered
  by the OS, so data may not hit disk immediately.
- **fsync** forces buffered data to disk. Use it for durability boundaries such
  as transaction commits or log segment flushes.
- **Sequential I/O** is faster than random I/O on spinning disks and still
  matters for SSDs due to wear and queue depth.
- **Journaling** reduces corruption after crashes by recording intent before
  data is written.

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

## Additional real-world examples
- Write-ahead log flushed on commit so recovery can replay consistent data.
- Media service streams large files with sequential reads to maximize throughput.
- Database uses periodic fsync on checkpoint files to bound recovery time.

## Practical checklist
- Batch small writes to reduce overhead.
- Use fsync for critical data.
- Monitor disk queue depth and latency.

## Official documentation
- https://man7.org/linux/man-pages/man2/open.2.html
- https://man7.org/linux/man-pages/man2/read.2.html
- https://man7.org/linux/man-pages/man2/write.2.html
- https://man7.org/linux/man-pages/man2/fsync.2.html
