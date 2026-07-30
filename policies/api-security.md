# API Security Policies

Salt Code enforces the OWASP API Security Top 10 and additional API-specific security guidelines.

## Categories

- **Broken Object Level Authorization (BOLA)** — Missing or insufficient object-level access controls
- **Broken Authentication** — Weak authentication mechanisms, insecure token handling, query string auth
- **Broken Object Property Level Authorization** — Excessive data exposure, mass assignment vulnerabilities
- **Unrestricted Resource Consumption** — Missing rate limiting, lack of request size validation
- **Broken Function Level Authorization** — Missing function-level access controls
- **Unrestricted Access to Sensitive Business Flows** — Business logic flaws in API design
- **Server-Side Request Forgery** — SSRF vulnerabilities in API endpoints
- **Security Misconfiguration** — Insecure defaults, verbose error messages, missing security headers
- **Improper Inventory Management** — Undocumented endpoints, deprecated API versions
- **Unsafe Consumption of APIs** — Insecure third-party API integrations

## Examples Salt Code flags

- API keys or tokens passed in query strings
- User IDs or PII passed in query string parameters
- Missing authentication on sensitive endpoints
- Endpoints returning more data than necessary
- Missing pagination on list endpoints
