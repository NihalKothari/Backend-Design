# API Design and Contracts

This module teaches how to design stable, predictable APIs. Each subtopic
includes key concepts, a real-world example, and a diagram.

## Progression expectations

| Level | Outcomes |
| --- | --- |
| Beginner | Use REST basics, status codes, and resource modeling. |
| Intermediate | Design pagination, filtering, and validation rules. |
| Senior | Apply versioning, idempotency, and error conventions. |
| Principal | Set org standards and enforce compatibility and security. |

## How to use this module
- Start with resource modeling and HTTP conventions.
- Produce a small artifact per subtopic (contract, diagram, checklist).
- Align examples with an existing API in your org for realism.

## Subtopics
1. [Resource Modeling and Naming](01-resource-modeling-and-naming.md)
2. [Requests, Responses, and Errors](02-requests-responses-and-errors.md)
3. [Pagination, Filtering, Sorting](03-pagination-filtering-sorting.md)
4. [Idempotency and Retries](04-idempotency-and-retries.md)
5. [Versioning and Compatibility](05-versioning-and-compatibility.md)
6. [AuthN/AuthZ Integration](06-authn-authz-integration.md)
7. [Rate Limiting and Quotas](07-rate-limiting-and-quotas.md)
8. [Contracts: OpenAPI and gRPC](08-contracts-openapi-grpc.md)

## Suggested artifacts
- OpenAPI spec for a core resource.
- Error format and status code policy.
- Versioning and compatibility checklist.

## Additional real-world practice ideas
- Draft a rate limit policy with headers and error codes for a public API.
- Write a migration guide for a breaking change you avoided via versioning.

## Official documentation
- https://spec.openapis.org/oas/latest.html
- https://www.rfc-editor.org/rfc/rfc9110
