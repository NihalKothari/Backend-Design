# Reliability and Disaster Recovery

## Why it matters
Backups and recovery plans keep the business running when failures happen. The
best time to design DR is before an incident.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand backups and restore basics. |
| Intermediate | Use PITR and verify restore workflows. |
| Senior | Define RPO and RTO targets. |
| Principal | Design multi-region DR and run drills. |

## Key concepts
- Full, incremental, and point-in-time recovery (PITR).
- RPO (data loss) and RTO (time to recover).
- Multi-region replication and failover.
- Backup retention and verification.

## Detailed explanation
- **Full and incremental backups** reduce recovery time and storage costs.
- **PITR** replays WAL/binlogs to restore to a specific timestamp after issues.
- **RPO/RTO** should be explicit and validated via drills, not just documents.
- **Backup verification** ensures backups are usable, not just present.

## Real-world example: Payment system recovery
A bad migration corrupts data. The team restores to the last safe timestamp.

```mermaid
flowchart LR
  A[Full backup] --> B[Incremental backups]
  B --> C[WAL / binlog]
  C --> D[Restore to timestamp]
```

## Additional real-world examples
- Monthly restore drill uncovers missing WAL segments and fixes retention policy.
- Cross-region replicas used for DR but excluded from read traffic to reduce lag.
- Automated backup tests run on a staging cluster weekly.

## Practical checklist
- Test restores regularly, not just backups.
- Document failover steps and ownership.
- Track backup freshness and alert on failures.

## Official documentation
- https://www.postgresql.org/docs/current/continuous-archiving.html
- https://dev.mysql.com/doc/refman/8.0/en/backup-and-recovery.html
