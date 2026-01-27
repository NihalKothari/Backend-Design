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

## Detailed explanation
- **Lock files** ensure reproducible builds across dev, CI, and production.
- **Artifact versioning** ties deployments to immutable build outputs.
- **SBOMs** improve supply chain visibility and vulnerability response.

## Real-world example: Service build pipeline
Each commit builds an artifact with a pinned dependency set.

## Diagram
```mermaid
flowchart LR
  A[Source] --> B[Dependency install]
  B --> C[Build]
  C --> D[Artifact]
```

## Additional real-world examples
- CI generates an SBOM and stores it alongside the build artifact.
- Dependency updates grouped into weekly maintenance PRs.
- Build cache reduces install time in CI for large monorepos.

## Practical checklist
- Pin dependencies to avoid drift.
- Track vulnerabilities and upgrades.
- Cache builds for faster CI.

## Official documentation
- https://slsa.dev/
- https://spdx.dev/specifications/
- https://cyclonedx.org/specification/overview/
