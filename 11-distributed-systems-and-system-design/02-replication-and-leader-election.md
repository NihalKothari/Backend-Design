# Replication and Leader Election

## Why it matters
Replication improves availability and read scalability but introduces lag and
consistency challenges.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand leader/follower replication. |
| Intermediate | Handle replica lag and failover. |
| Senior | Design leader election and health checks. |
| Principal | Define replication topologies and SLAs. |

## Key concepts
- Leader/follower replication.
- Synchronous vs asynchronous replication.
- Replica lag and failover.

## Detailed explanation
- **Leader/follower** simplifies writes but can become a single bottleneck.
- **Synchronous replication** improves durability at the cost of write latency.
- **Replica lag** affects read freshness; detect and route accordingly.

## Real-world example: Read scaling
An API writes to a primary database and reads from replicas for reporting.

## Diagram
```mermaid
flowchart LR
  A[Primary] --> B[Replica 1]
  A --> C[Replica 2]
```

## Additional real-world examples
- Analytics reads routed to replicas to protect the primary workload.
- Failover drills simulate leader loss and measure recovery time.
- Read-your-writes achieved by pinning a session to the leader.

## Practical checklist
- Monitor replication lag.
- Define failover and promotion procedures.
- Route critical reads to the leader.

## Official documentation
- https://www.postgresql.org/docs/current/warm-standby.html
- https://zookeeper.apache.org/doc/current/zookeeperAdmin.html
