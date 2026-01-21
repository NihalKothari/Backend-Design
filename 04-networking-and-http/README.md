# Networking and HTTP

This module takes a developer from fundamentals to principal-level networking
and HTTP design. Each subtopic file includes key concepts, a real-world
example, and at least one diagram.

## Progression expectations

| Level | Outcomes |
| --- | --- |
| Beginner | Understand packets, HTTP basics, and DNS resolution. |
| Intermediate | Apply TLS, proxies, caching, and load balancing correctly. |
| Senior | Define timeouts, retries, and observability standards. |
| Principal | Architect global, resilient, and secure network strategies. |

## How to use this module
- Start at Networking Fundamentals and proceed in order.
- Build a small artifact per subtopic (diagram, policy, or checklist).
- Revisit advanced sections as you move up the ladder.

## Subtopics
1. [Networking Fundamentals](01-networking-fundamentals.md) - OSI/TCP-IP, latency, MTU.
2. [DNS and Domain Resolution](02-dns-and-domain-resolution.md) - Caching, TTL, records.
3. [TCP, UDP, and TLS](03-tcp-udp-and-tls.md) - Handshakes, reliability, mTLS.
4. [HTTP Core Concepts](04-http-core-concepts.md) - Methods, status codes, headers.
5. [HTTP Caching and CDNs](05-http-caching-and-cdns.md) - Cache-Control, ETag, edges.
6. [Load Balancing and Proxies](06-load-balancing-and-proxies.md) - L4/L7, health checks.
7. [Retries, Timeouts, and Backoff](07-retries-timeouts-and-backoff.md) - Idempotency, jitter.
8. [API Protocols and Streaming](08-api-protocols-and-streaming.md) - REST, gRPC, WebSockets.
9. [Observability and Network Debugging](09-observability-and-network-debugging.md) - Tracing, logs.
10. [Security and DDoS Basics](10-security-and-ddos-basics.md) - WAF, rate limits.
11. [Global Architecture and Edge Strategy](11-global-architecture-and-edge-strategy.md) - Multi-region, failover.

## Suggested artifacts
- Diagram of a full request path with hops and time budgets.
- Standardized timeout and retry policy for your services.
- CDN caching strategy with cache-control directives.
- Global routing and failover plan for a critical API.
