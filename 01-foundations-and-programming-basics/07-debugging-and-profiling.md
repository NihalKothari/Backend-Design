# Debugging and Profiling

## Why it matters
Debugging and profiling turn incidents into clear fixes. They also prevent
performance regressions.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use breakpoints and logs to inspect state. |
| Intermediate | Reproduce bugs with minimal examples. |
| Senior | Profile CPU and memory bottlenecks. |
| Principal | Create debugging playbooks for teams. |

## Key concepts
- Breakpoints, watch expressions, and log inspection.
- Reproduction steps and minimal failing cases.
- CPU and memory profiling.
- Flame graphs and hotspots.

## Detailed explanation
- **Breakpoints and watch expressions** let you inspect live state at the moment
  a bug occurs. Combine this with logs to understand the full request context.
- **Reproduction steps** reduce debugging time. A minimal failing case isolates
  the root cause and prevents chasing unrelated symptoms.
- **CPU and memory profiling** show where time and allocations are spent.
  Profiling should happen with realistic data to avoid misleading results.
- **Flame graphs** visualize hotspots across call stacks. They help prioritize
  optimizations that deliver the biggest impact.

## Real-world example: Slow endpoint
A report endpoint slows down. Profiling reveals a slow JSON serialization step.

## Diagram
```mermaid
flowchart LR
  A[Symptom] --> B[Reproduce]
  B --> C[Profile]
  C --> D[Identify hotspot]
  D --> E[Fix + verify]
```

## Practical checklist
- Always capture exact inputs and timestamps.
- Profile with realistic traffic when possible.
- Verify fixes with regression tests.
