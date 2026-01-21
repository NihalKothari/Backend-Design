# Tooling and Builds

## Why it matters
Reliable tooling reduces errors and keeps teams productive.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Use formatters and linters locally. |
| Intermediate | Manage dependencies and builds. |
| Senior | Automate checks in CI. |
| Principal | Standardize tooling across teams. |

## Key concepts
- Formatters and linters.
- Dependency management and lock files.
- Build systems and artifacts.
- CI hooks and quality gates.

## Detailed explanation
- **Formatters and linters** enforce consistent style and catch common bugs.
  Automated formatting reduces review noise and keeps diffs clean.
- **Dependency management** with lock files ensures reproducible builds. It
  prevents accidental upgrades that can change runtime behavior.
- **Build systems and artifacts** package code into deployable units. A clean
  build process should be deterministic and documented.
- **CI hooks and quality gates** make quality a default. Gating merges on tests
  and lint reduces regressions in shared codebases.

## Real-world example: CI pipeline for a service
A pipeline formats code, runs tests, and publishes an artifact.

## Diagram
```mermaid
flowchart LR
  A[Commit] --> B[Lint + format]
  B --> C[Test]
  C --> D[Build artifact]
  D --> E[Publish]
```

## Practical checklist
- Pin dependencies with lock files.
- Fail fast on lint and test failures.
- Keep build steps documented and repeatable.
