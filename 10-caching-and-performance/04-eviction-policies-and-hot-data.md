# Eviction Policies and Hot Data

## Why it matters
Caches have limited memory. Eviction policies decide what stays and what goes.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand LRU and TTL. |
| Intermediate | Use LFU for repeated access. |
| Senior | Identify hot vs cold data. |
| Principal | Set policies by workload type. |

## Key concepts
- LRU, LFU, FIFO policies.
- Hot key detection and skew.
- Cache size and memory limits.

## Real-world example: Session cache
Active sessions stay in cache while idle sessions are evicted.

## Diagram
```mermaid
flowchart LR
  A[Access key] --> B[Move to front]
  B --> C[LRU list]
  C --> D[Evict tail]
```

## Practical checklist
- Pick eviction based on access patterns.
- Monitor hit ratios and key distribution.
- Protect against hot-key overload.
