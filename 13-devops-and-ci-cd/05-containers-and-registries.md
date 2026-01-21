# Containers and Registries

## Why it matters
Containers package services consistently. Registries provide secure storage and
distribution.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Build and push images. |
| Intermediate | Use tags and digests. |
| Senior | Scan images for vulnerabilities. |
| Principal | Define image standards and base images. |

## Key concepts
- Image layers and caching.
- Tagging vs digest pinning.
- Vulnerability scanning.

## Real-world example: Base image policy
Teams use a standard base image that is patched monthly.

## Diagram
```mermaid
flowchart LR
  A[Build image] --> B[Registry]
  B --> C[Deploy]
```

## Practical checklist
- Use minimal base images.
- Pin images by digest for production.
- Scan images on every build.
