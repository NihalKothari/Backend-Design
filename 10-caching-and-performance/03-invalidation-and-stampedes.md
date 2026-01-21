# Invalidation and Stampedes

## Why it matters
Cache invalidation is hard and stampedes can take services down.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use TTL and explicit invalidation. |
| Intermediate | Apply request coalescing. |
| Senior | Use soft TTL and refresh-ahead. |
| Principal | Define invalidation standards. |

## Key concepts
- Explicit invalidation vs TTL expiry.
- Cache stampedes and thundering herds.
- Request coalescing and locking.

## Real-world example: Flash sale pricing
Price changes trigger invalidation; a mutex prevents multiple DB reads per key.

## Diagram
```mermaid
flowchart LR
  A[Cache miss] --> B{Lock?}
  B -- acquired --> C[Fetch from DB]
  B -- blocked --> D[Wait for value]
  C --> E[Update cache]
```

## Practical checklist
- Use jittered TTLs to avoid synchronized expiry.
- Coalesce concurrent misses for hot keys.
- Monitor miss rates during peak traffic.
