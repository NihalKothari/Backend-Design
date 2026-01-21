# Messaging and Event-Driven Systems

This module focuses on asynchronous communication and event-driven design.
Each subtopic includes key concepts, a real-world example, and a diagram.

## Progression expectations

| Level | Outcomes |
| --- | --- |
| Beginner | Understand queues, pub/sub, and streams. |
| Intermediate | Apply delivery semantics, retries, and DLQs. |
| Senior | Handle ordering, idempotency, and schema evolution. |
| Principal | Define messaging standards and operational readiness. |

## How to use this module
- Start with messaging models and delivery semantics.
- Create a small artifact per subtopic (diagram, checklist, or schema).

## Subtopics
1. [Messaging Models](01-messaging-models.md)
2. [Delivery Semantics](02-delivery-semantics.md)
3. [Ordering and Partitioning](03-ordering-and-partitioning.md)
4. [Schema Evolution and Contracts](04-schema-evolution-and-contracts.md)
5. [Retries and Dead Letter Queues](05-retries-and-dlq.md)
6. [Outbox and Inbox Patterns](06-outbox-and-inbox-patterns.md)
7. [Event Sourcing vs Event-Driven](07-event-sourcing-vs-event-driven.md)
8. [Consumer Scaling and Backpressure](08-consumer-scaling-and-backpressure.md)

## Suggested artifacts
- Message schema with versioning rules.
- DLQ policy and retry strategy.
- Consumer scaling plan with backpressure signals.
