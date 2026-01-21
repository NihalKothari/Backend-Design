# Containers and Kubernetes

## Why it matters
Containers and orchestration enable scalable, repeatable deployments.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand pods and deployments. |
| Intermediate | Configure services and ingress. |
| Senior | Tune autoscaling and resource limits. |
| Principal | Define cluster standards and policies. |

## Key concepts
- Pods, deployments, and services.
- Ingress and service discovery.
- Resource requests and limits.

## Real-world example: API deployment
An API runs as a deployment with horizontal pod autoscaling.

## Diagram
```mermaid
flowchart LR
  A[Ingress] --> B[Service]
  B --> C[Pods]
```

## Practical checklist
- Set requests and limits for every pod.
- Use readiness and liveness probes.
- Keep manifests versioned and reviewed.
