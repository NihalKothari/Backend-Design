# Managed Datastores

## Why it matters
Managed services reduce operational overhead and improve reliability.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use managed databases and caches. |
| Intermediate | Configure backups and replicas. |
| Senior | Tune performance and scaling. |
| Principal | Define data platform standards. |

## Key concepts
- Managed relational and NoSQL databases.
- Managed caches and queues.
- Backup and failover configuration.

## Real-world example: Managed database
A service uses a managed Postgres with automated backups and read replicas.

## Diagram
```mermaid
flowchart LR
  A[App] --> B[Managed DB]
  B --> C[Read replica]
```

## Practical checklist
- Enable automated backups and PITR.
- Monitor replica lag.
- Use maintenance windows for upgrades.
