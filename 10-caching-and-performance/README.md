# Caching and Performance

This module teaches how to optimize latency and throughput. Each subtopic
includes key concepts, a real-world example, and a diagram.

## Progression expectations

| Level | Outcomes |
| --- | --- |
| Beginner | Understand caching basics, TTLs, and eviction. |
| Intermediate | Apply cache-aside and stampede prevention. |
| Senior | Profile bottlenecks and tune services. |
| Principal | Define performance budgets and testing standards. |

## How to use this module
- Start with caching layers and strategies.
- Create a small artifact per subtopic (diagram, benchmark, checklist).
- Pair each section with a real service for measurement.

## Subtopics
1. [Cache Layers](01-cache-layers.md)
2. [Caching Strategies](02-caching-strategies.md)
3. [Invalidation and Stampedes](03-invalidation-and-stampedes.md)
4. [Eviction Policies and Hot Data](04-eviction-policies-and-hot-data.md)
5. [Profiling and Bottlenecks](05-profiling-and-bottlenecks.md)
6. [Database Performance Patterns](06-database-performance-patterns.md)
7. [Connection Pooling and Limits](07-connection-pooling-and-limits.md)
8. [Async Processing and Batching](08-async-processing-and-batching.md)
9. [Load Testing and Budgets](09-load-testing-and-budgets.md)

## Suggested artifacts
- Cache hierarchy diagram for a service.
- Performance budget with latency targets.
- Load test plan with success criteria.

## Additional real-world practice ideas
- Run a cache hit/miss analysis and document eviction policy changes.
- Create a p99 latency budget for a critical API.

## Official documentation
- https://www.rfc-editor.org/rfc/rfc9111
- https://redis.io/docs/
