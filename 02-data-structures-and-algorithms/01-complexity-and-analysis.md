# Complexity and Analysis

## Why it matters
Complexity determines whether a feature will scale. Small changes in algorithm
choice can reduce latency and infrastructure cost.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Big O notation and basic growth rates. |
| Intermediate | Analyze time and space tradeoffs. |
| Senior | Use amortized analysis and realistic constraints. |
| Principal | Translate complexity to cost and SLO impact. |

## Key concepts
- Big O, Theta, and Omega.
- Common growth rates: O(1), O(log n), O(n), O(n log n), O(n^2).
- Amortized analysis and average vs worst case.
- Memory vs CPU tradeoffs.

## Real-world example: Request deduplication
A service removes duplicate requests before processing. Using a hash set
reduces work from O(n^2) to O(n).

## Diagram
```mermaid
flowchart LR
  A[Input size grows] --> B[O(n): linear growth]
  A --> C[O(n log n): moderate growth]
  A --> D[O(n^2): steep growth]
```

## Practical checklist
- Always estimate input size and frequency.
- Prefer linear or log-linear algorithms for hot paths.
- Track memory usage when optimizing time.
