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
- **Artifact versioning** ties deploys to immutable outputs (container images,
  jars, wheels). Use checksums or digests to avoid ambiguity.
- **Build caching** speeds up CI. Cache dependencies and compiled outputs, but
  invalidate caches when inputs change to prevent stale artifacts.

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

## Additional real-world examples
- CI builds a container image, scans it, and pushes it to a registry with a
  commit SHA tag.
- Monorepo uses a shared lint config so all services enforce the same rules.
- Dependency lock files are updated only through a scheduled maintenance PR.

## Practical checklist
- Pin dependencies with lock files.
- Fail fast on lint and test failures.
- Keep build steps documented and repeatable.

## Official documentation
- https://docs.github.com/en/actions
- https://doc.rust-lang.org/cargo/
- https://docs.npmjs.com/cli/v10/configuring-npm/package-lock-json
- https://pip.pypa.io/en/stable/topics/dependency-resolution/
