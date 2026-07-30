# OpenAPI / Swagger Compliance Policies

Salt Code enforces OpenAPI specification best practices and common compliance requirements.

## Categories

- **Missing Authentication Schemes** — Endpoints without defined security schemes
- **Undocumented Endpoints** — Implementation endpoints not reflected in the spec
- **Improper Response Schemas** — Missing or overly permissive response definitions
- **Insecure Parameter Handling** — Sensitive data in path/query parameters
- **Missing Rate Limit Headers** — No `X-RateLimit-*` or `Retry-After` headers defined
- **Spec-to-Implementation Drift** — Generated code that doesn't match the spec
- **Improper Error Responses** — Missing or overly verbose error response schemas
- **Missing Pagination** — List endpoints without pagination parameters

## Examples Salt Code flags

- `securitySchemes` missing from OpenAPI spec
- API key authentication defined as query parameter
- User IDs in path parameters without authorization checks
- 500 responses with implementation details exposed
