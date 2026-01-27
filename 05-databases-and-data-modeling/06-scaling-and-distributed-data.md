# Scaling and Distributed Data

## Why it matters
As traffic grows, single-node databases become bottlenecks. Scaling requires
careful tradeoffs around consistency, latency, and operational complexity.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand replicas and basic sharding ideas. |
| Intermediate | Route reads and writes correctly. |
| Senior | Plan partition keys and rebalancing. |
| Principal | Set consistency and availability standards. |

## Key concepts
- Read replicas and write scaling.
- Sharding and partitioning strategies.
- Consistent hashing and rebalancing.
- Replication lag and read-your-writes issues.

## Detailed explanation
- **Read replicas** scale reads but introduce lag; clients need read-your-writes
  strategies for critical flows.
- **Sharding** splits data across nodes to scale writes. Choose shard keys that
  avoid hotspots and allow rebalancing.
- **Consistent hashing** reduces data movement when adding or removing nodes.
- **Replication lag** affects freshness; route user-specific reads to primaries
  when strict consistency is required.

## Real-world example: Social app scaling
User data is sharded by `user_id`, with read replicas for feed reads.

```mermaid
flowchart LR
  A[App] --> R[Router]
  R --> S1[(Shard 1)]
  R --> S2[(Shard 2)]
  S1 --> R1[(Replica 1)]
  S2 --> R2[(Replica 2)]
```

## Additional real-world examples
- Hot partition caused by time-based keys; switch to hashed keys for balance.
- Read-after-write consistency achieved by pinning a user to the primary.
- Resharding plan includes dual writes during migration to avoid downtime.

## Practical checklist
- Choose shard keys that balance load and avoid hot spots.
- Decide which reads can tolerate replica lag.
- Plan resharding and migration paths early.

## Official documentation
- https://www.postgresql.org/docs/current/warm-standby.html
- https://cassandra.apache.org/doc/latest/cassandra/architecture/overview.html
- https://cloud.google.com/spanner/docs/overview
