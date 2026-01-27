# Specialized Datastores

## Why it matters
Not every workload fits a relational database. Specialized stores solve
specific problems more efficiently.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Know common datastore types and use cases. |
| Intermediate | Choose OLTP vs OLAP based on workload. |
| Senior | Combine stores safely with clear ownership. |
| Principal | Define data platform strategy and governance. |

## Key concepts
- OLTP vs OLAP vs HTAP.
- Search, time-series, graph, and document stores.
- Cache vs DB vs search tradeoffs.
- Data pipelines and consistency boundaries.

## Detailed explanation
- **OLTP** optimizes for many small writes; **OLAP** optimizes for large scans
  and aggregations; **HTAP** blends both with tradeoffs.
- **Search stores** optimize full-text queries and relevance ranking.
- **Time-series stores** handle high ingest and retention policies.
- **Consistency boundaries** must be documented when data is replicated across
  multiple stores.

## Real-world example: Analytics and search
Transactional data is stored in OLTP, then streamed to a warehouse for BI.
Search uses an index optimized for full-text queries.

```mermaid
flowchart LR
  A[App writes] --> B[(OLTP DB)]
  B --> C[CDC stream]
  C --> D[(Data warehouse)]
  B --> E[(Search index)]
```

## Additional real-world examples
- Product search uses a search index for autocomplete and relevance tuning.
- Metrics pipeline writes to a time-series store with retention policies.
- Graph store models social connections for friend recommendations.

## Practical checklist
- Pick the simplest store that meets requirements.
- Document data ownership and sync guarantees.
- Measure cost and operational overhead per store.

## Official documentation
- https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html
- https://prometheus.io/docs/introduction/overview/
- https://neo4j.com/docs/
