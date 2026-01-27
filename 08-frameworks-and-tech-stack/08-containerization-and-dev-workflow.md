# Containerization and Dev Workflow

## Why it matters
Containers provide consistent environments across dev, test, and prod.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Build and run a container locally. |
| Intermediate | Use compose for dependencies. |
| Senior | Optimize images and startup time. |
| Principal | Standardize service templates and tooling. |

## Key concepts
- Dockerfiles and image layers.
- Local development with compose.
- Base images and security updates.

## Detailed explanation
- **Dockerfiles** should be deterministic and cache-friendly to speed builds.
- **Compose** orchestrates local dependencies for consistent dev workflows.
- **Base images** should be kept updated to reduce vulnerabilities.

## Real-world example: Local service stack
A developer runs the API with a local database using docker compose.

## Diagram
```mermaid
flowchart LR
  A[Code] --> B[Build image]
  B --> C[Run container]
  C --> D[Local dev]
```

## Additional real-world examples
- Multi-stage builds reduce image size and remove build tools from runtime.
- Local compose file mirrors production env variables for parity.
- Health checks restart services when dependencies are unavailable.

## Practical checklist
- Keep images small and secure.
- Use health checks in compose.
- Mirror production configs where possible.

## Official documentation
- https://docs.docker.com/engine/reference/builder/
- https://docs.docker.com/compose/
