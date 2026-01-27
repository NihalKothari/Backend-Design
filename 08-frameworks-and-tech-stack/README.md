# Frameworks and Tech Stack

This module helps you choose and use frameworks, runtimes, and tooling for
production services. Each subtopic includes key concepts, a real-world example,
and a diagram.

## Progression expectations

| Level | Outcomes |
| --- | --- |
| Beginner | Use a framework for routing, middleware, and dependencies. |
| Intermediate | Manage configuration, logging, and packaging. |
| Senior | Evaluate stack tradeoffs for performance and maintainability. |
| Principal | Define approved stacks and upgrade cadence. |

## How to use this module
- Start with runtime selection and frameworks.
- Produce a small artifact per subtopic (decision doc, diagram, or checklist).
- Review at least one existing service to see real tradeoffs.

## Subtopics
1. [Language and Runtime Selection](01-language-and-runtime-selection.md)
2. [Web Frameworks and Middleware](02-web-frameworks-and-middleware.md)
3. [Configuration and Environment](03-configuration-and-environment.md)
4. [Logging and Runtime Diagnostics](04-logging-and-runtime-diagnostics.md)
5. [Data Access: ORM vs Query Builder](05-data-access-orm-vs-query-builder.md)
6. [Background Jobs and Scheduling](06-background-jobs-and-scheduling.md)
7. [Build Systems and Dependencies](07-build-systems-and-dependencies.md)
8. [Containerization and Dev Workflow](08-containerization-and-dev-workflow.md)
9. [Stack Evaluation and Governance](09-stack-evaluation-and-governance.md)

## Suggested artifacts
- Stack selection decision record.
- Standard service template with logging and config.
- Upgrade plan and dependency policy.

## Additional real-world practice ideas
- Compare two runtimes for a sample service and document tradeoffs.
- Build a local dev environment with compose and health checks.

## Official documentation
- https://docs.docker.com/
- https://kubernetes.io/docs/concepts/
