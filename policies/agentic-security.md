# Agentic Security Policies

Salt Code enforces security guidelines specific to AI agents, MCP servers, and agentic workflows.

## Categories

- **Prompt Injection via MCP Tools** — Tool descriptions or outputs that manipulate agent behavior
- **Tool Poisoning** — Malicious or misleading tool definitions
- **Excessive Tool Permissions** — Tools requesting broader access than needed
- **Unsafe Agent-to-Agent Communication** — Unvalidated messages between agents
- **Unvalidated Tool Outputs** — Agents acting on unverified tool results
- **Insecure MCP Server Configurations** — Misconfigured transport, missing auth, open endpoints
- **Sensitive Data Leakage** — Agents exposing credentials or PII in tool calls
- **Denial of Service via Agent Loops** — Unbounded recursive agent calls

## Examples Salt Code flags

- MCP tools without input validation
- Agent workflows that pass raw user input to system commands
- Tools with overly broad resource access
- Missing authentication on MCP endpoints
