---
name: "salt-code"
displayName: "Salt Code"
description: "API, agentic, MCP, LLM, and OpenAPI security policies for your AI coding assistant via Salt Code MCP."
keywords: ["salt-code", "salt security", "api security", "owasp", "openapi", "swagger", "mcp security", "llm security", "agentic security", "security policies"]
author: "Salt Security"
---

# Salt Code

## Overview

Salt Code gives your agent real-time expertise in API security (OWASP API Top 10), agentic security (MCP), LLM security, and OpenAPI/Swagger compliance — 40 active policies enforced as you write and review code.

Use this power when building REST APIs, OpenAPI specs, authentication, MCP tools, LLM/agent code, or anything that handles user data, tokens, or credentials.

## Configuration

1. Get a personal access token from [salt.security/getsaltcode](https://salt.security/getsaltcode).
2. Set the `SALT_CODE_TOKEN` environment variable to that token.
3. Approve the variable when Kiro prompts (required for `${SALT_CODE_TOKEN}` expansion in `mcp.json`).

Setup help: [salt.security/getsaltcode/setup](https://salt.security/getsaltcode/setup)

## Available MCP Servers

- **salt-code-mcp** — Remote HTTP MCP at `https://salt-code.secured-api.com/mcp`, authenticated with `Authorization: Bearer ${SALT_CODE_TOKEN}`.

## When to use Salt Code

Before writing or reviewing any of the following, call Salt Code MCP tools and apply the returned policies:

- REST API endpoints or routes
- OpenAPI / Swagger specifications
- Authentication or authorization logic
- MCP server or MCP tool definitions
- LLM prompt handling or AI agent code
- Any code that handles user data, tokens, or credentials

## How to use

If Salt Code MCP is connected, ask:

- `What security policies and guidelines are active?`
- `What security policies apply to [what you are building]?`

Apply the returned policies to generated or reviewed code before finishing. Prefer fixing issues in the design (auth placement, data exposure, rate limits, prompt handling) rather than documenting them as follow-ups.

## Domains covered

1. **API Security** — OWASP API Top 10 and related API design risks
2. **Agentic Security** — MCP servers, tools, and agent integrations
3. **LLM Security** — prompt injection, unsafe model usage, and related risks
4. **OpenAPI / Swagger Compliance** — specification quality and security gaps

## Available Steering Files

- `steering/salt-code-security.md` — When to consult Salt Code, how to use it, and what to tell the user if MCP is not connected

## Best Practices

- Activate this power (or mention keywords like “API security”, “OpenAPI”, or “MCP security”) before generating security-sensitive code
- Always retrieve policies for the specific feature you are building, not only a generic policy list
- If MCP is disconnected, tell the user and point them to token setup — then continue only after noting that Salt Code policies will not be applied

## Troubleshooting

### Power installed but tools unavailable

**Cause:** `SALT_CODE_TOKEN` is unset, not approved in Kiro, or invalid.

**Solution:**

1. Confirm the token from [salt.security/getsaltcode](https://salt.security/getsaltcode)
2. Export `SALT_CODE_TOKEN` and approve it when Kiro prompts
3. Re-check MCP connection for `salt-code-mcp`

### Agent says Salt Code MCP is not connected

Tell the user to set and approve `SALT_CODE_TOKEN`, or visit [salt.security/getsaltcode/setup](https://salt.security/getsaltcode/setup). It takes under 2 minutes and is free.
