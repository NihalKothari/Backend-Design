# Transactions and Consistency

## Why it matters
Transactions protect correctness when multiple changes must succeed or fail
together. Understanding isolation avoids subtle data bugs.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use transactions for multi-step updates. |
| Intermediate | Understand isolation levels and anomalies. |
| Senior | Choose optimistic vs pessimistic locking. |
| Principal | Define consistency guarantees and retry policies. |

## Key concepts
- ACID properties and transaction boundaries.
- Isolation levels and anomalies (dirty read, non-repeatable read, phantom).
- Locks, deadlocks, optimistic vs pessimistic concurrency.
- Idempotency and retry-safe operations.

## Detailed explanation
- **ACID** guarantees keep data correct under failures. Define clear transaction
  boundaries so related updates succeed or fail together.
- **Isolation levels** trade concurrency for consistency. Read committed is
  common; serializable is safest but can reduce throughput.
- **Locking** avoids races but can cause deadlocks. Use consistent lock order
  and short transactions.
- **Optimistic concurrency** uses version checks to reduce locking for
  low-conflict workloads.

## Real-world example: Wallet transfer
Transfer funds between two accounts in a single transaction.

```sql
BEGIN;
SELECT balance FROM accounts WHERE id = 101 FOR UPDATE;
UPDATE accounts SET balance = balance - 100 WHERE id = 101;
UPDATE accounts SET balance = balance + 100 WHERE id = 202;
COMMIT;
```

## Diagram
```mermaid
sequenceDiagram
  participant App
  participant DB
  App->>DB: BEGIN
  App->>DB: SELECT balance FOR UPDATE
  App->>DB: UPDATE account 101
  App->>DB: UPDATE account 202
  App->>DB: COMMIT
```

## Additional real-world examples
- Order creation uses a transaction to insert order, items, and ledger entries.
- Inventory updates use optimistic locking with a version column.
- Background reconciliation job retries transactions after serialization errors.

## Practical checklist
- Keep transactions short to reduce lock contention.
- Handle retries for serialization or deadlock errors.
- Use idempotency keys for external-facing write APIs.

## Official documentation
- https://www.postgresql.org/docs/current/transaction-iso.html
- https://dev.mysql.com/doc/refman/8.0/en/innodb-locking.html
