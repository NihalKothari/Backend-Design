# Configuration and Secrets

## Why it matters
Secure configuration prevents outages and data leaks.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use environment variables. |
| Intermediate | Integrate secrets managers. |
| Senior | Rotate secrets and enforce access policies. |
| Principal | Define org-wide config standards. |

## Key concepts
- Secrets managers and access controls.
- Configuration validation and defaults.
- Key rotation and revocation.

## Real-world example: API keys
Services fetch API keys from a secrets manager at startup.

## Diagram
```mermaid
flowchart LR
  A[Service] --> B[Secrets manager]
  B --> C[Key store]
```

## Practical checklist
- Never store secrets in code or config files.
- Rotate keys on a schedule.
- Audit access to secrets.
