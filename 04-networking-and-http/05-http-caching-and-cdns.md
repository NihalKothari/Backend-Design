# HTTP Caching and CDNs

## Why it matters
Caching reduces latency and load. Misconfigured caches can serve stale data or
invalidate incorrectly.

## Progression checkpoints
| Level | Focus |
| --- | --- |
| Beginner | Understand Cache-Control and ETag basics. |
| Intermediate | Use CDN caching and purge strategies. |
| Senior | Design cache hierarchies and stampede prevention. |
| Principal | Set global cache policies and governance. |

## Key concepts
- Cache-Control, Expires, ETag, If-None-Match.
- Stale-while-revalidate and cache invalidation.
- CDN edge caching vs origin caching.
- Private vs public caches.

## Detailed explanation
- **Cache-Control directives** define freshness and revalidation behavior.
  `public` allows shared caches; `private` restricts to the client.
- **ETags** support conditional requests so clients can avoid full downloads.
- **Stale-while-revalidate** keeps latency low while edges refresh in the
  background, reducing stampedes.
- **Cache invalidation** should be explicit and testable to prevent serving
  outdated content.

## Real-world example: News traffic spike
A news site uses CDN caching with short TTLs for headlines and longer TTLs for
static assets to handle a traffic surge during a breaking event.

```http
Cache-Control: public, max-age=60, stale-while-revalidate=300
ETag: "v3-landing-page"
```

## Diagram
```mermaid
flowchart LR
  C[Client] --> E[CDN edge]
  E -->|Miss| O[Origin]
  O --> E
  E --> C
```

## Additional real-world examples
- Product images use long-lived immutable caching with versioned URLs.
- API returns `Cache-Control: no-store` for personalized responses.
- CDN purge API is called on content updates to refresh critical assets.

## Practical checklist
- Cache static assets aggressively; tune TTLs for dynamic data.
- Use ETags to reduce payloads on revalidation.
- Ensure cache purge paths are tested and documented.

## Official documentation
- https://www.rfc-editor.org/rfc/rfc9111
- https://www.rfc-editor.org/rfc/rfc5861
