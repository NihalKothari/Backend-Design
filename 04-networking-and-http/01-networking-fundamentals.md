# Networking Fundamentals

## Why it matters
Every backend system depends on moving bytes across a network. Understanding
how packets move and where latency comes from helps you design reliable APIs.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Learn TCP/IP basics and what a packet is. |
| Intermediate | Understand MTU, fragmentation, and latency vs bandwidth. |
| Senior | Diagnose packet loss, jitter, and noisy neighbors. |
| Principal | Set network budgets and cross-team standards. |

## Key concepts
- OSI vs TCP/IP model and where your code runs.
- Packets, frames, MTU, and fragmentation.
- Latency, bandwidth, jitter, and packet loss.
- Throughput vs response time tradeoffs.

## Real-world example: Video streaming buffering
A video service sees buffering spikes in a region. Analysis shows high packet
loss and reduced throughput. The team tunes CDN routing and increases segment
size to reduce overhead.

## Diagram
```mermaid
flowchart LR
  A[App data] --> B[TCP segments]
  B --> C[IP packets]
  C --> D[Link frames]
  D --> E[Network]
  E --> D2[Link frames]
  D2 --> C2[IP packets]
  C2 --> B2[TCP reassembly]
  B2 --> F[App receives]
```

## Practical checklist
- Track p95 and p99 latency at each hop.
- Watch MTU mismatches across VPNs and tunnels.
- Use packet loss metrics to explain tail latency.
