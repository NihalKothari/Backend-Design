# Build Systems and Dependencies

## Why it matters
Reliable builds enable consistent deployments and reduce "it works on my
machine" issues.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use package managers and lock files. |
| Intermediate | Reproducible builds and artifact versioning. |
| Senior | Optimize build time and caching. |
| Principal | Define dependency policies and upgrade cadence. |

## Key concepts
- Package managers and lock files.
- Build artifacts and versioning.
- Dependency scanning and SBOMs.

## Real-world example: Service build pipeline
Each commit builds an artifact with a pinned dependency set.

## Diagram
```mermaid
flowchart LR
  A[Source] --> B[Dependency install]
  B --> C[Build]
  C --> D[Artifact]
```

## Practical checklist
- Pin dependencies to avoid drift.
- Track vulnerabilities and upgrades.
- Cache builds for faster CI.
