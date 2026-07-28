<div align="center">

```
salt/code
```

**Security superpowers for your AI coding assistant.**

Give your AI coding assistant real-time expertise in API security, agentic security, MCP security, LLM security, and OpenAPI/Swagger compliance. All enforced as you code, not after you ship.

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![MCP](https://img.shields.io/badge/transport-MCP%20over%20HTTP-purple.svg)](https://modelcontextprotocol.io)
[![Coding Assistants](https://img.shields.io/badge/Tested%20Coding%20Assistants-16-brightgreen.svg)](#supported-coding-assistants)
[![Policies](https://img.shields.io/badge/active%20policies-40+-orange.svg)](#what-salt-code-enforces)

[Get your token](https://salt.security/getsaltcode) · [Setup page](https://salt.security/getsaltcode/setup) · [salt.security](https://salt.security)

</div>

---

## What is Salt Code?

Salt Code is a remote MCP (Model Context Protocol) server that connects to your AI coding assistant and enforces security policies in real time. When you ask your assistant to write an API, design a Swagger spec, or review a codebase, Salt Code steps in — flagging insecure patterns, suggesting fixes, and guiding you toward compliance before your code ever reaches production.

- **40 active policies** across API security, agentic security, LLM security, and OpenAPI/Swagger compliance
- **Works with 16 AI coding tools** — Cursor, Claude Code, VS Code, Windsurf, Kiro, and more
- **One token, every tool** — configure once, works across your entire stack
- **Free to use** — no credit card required

---

## How it works

```
1. Get your token      →  salt.security/getsaltcode
2. Connect your tool   →  paste one config block (or one command)
3. Start coding        →  Salt Code enforces security policies in real time
```

That's it. No agents to deploy, no proxies to configure, no infrastructure to manage. Salt Code is a remote MCP server — your coding assistant connects to it over HTTP with a Bearer token.

---

## Quickstart

**Claude Code (one command):**

```bash
claude mcp add salt-code-mcp \
  https://salt-code.secured-api.com/mcp \
  --transport http \
  --header "Authorization: Bearer <your_token>"
```

**Cursor / VS Code / most editors (config block):**

```json
{
  "mcpServers": {
    "salt-code-mcp": {
      "type": "http",
      "url": "https://salt-code.secured-api.com/mcp",
      "headers": {
        "Authorization": "Bearer <your_token>"
      }
    }
  }
}
```

Replace `<your_token>` with your personal access token from [salt.security/getsaltcode](https://salt.security/getsaltcode).

For step-by-step instructions for every supported tool, visit the **[interactive setup page](https://salt.security/getsaltcode/setup)** — it embeds your token directly into every command.

---

## Supported Coding Assistants

Any coding assistant that supports an MCP configuration can work with Salt Code. Below are coding assistants that have been tested and verified.

| Tool | Type | Transport |
|------|------|-----------|
| [Claude Code](plugins/claude-code/) | CLI | HTTP |
| [Cursor](plugins/cursor/) | Editor | HTTP |
| [VS Code + GitHub Copilot](plugins/vscode/) | Editor | HTTP |
| [GitHub Copilot CLI](plugins/copilot-cli/) | CLI | HTTP |
| [Windsurf](plugins/windsurf/) | Editor | HTTP |
| [Kiro](plugins/kiro/) | IDE | HTTP |
| [Codex](plugins/codex/) | CLI | HTTP |
| [Gemini CLI](plugins/gemini-cli/) | CLI | HTTP |
| [Antigravity](plugins/antigravity/) | IDE | HTTP |
| [OpenCode](plugins/opencode/) | CLI | HTTP |
| [JetBrains AI Assistant](plugins/jetbrains/) | IDE | HTTP (via mcp-remote) |
| [Grok](plugins/grok/) | CLI | HTTP |
| [Lovable](plugins/lovable/) | Builder | HTTP |
| [Cline](plugins/cline/) | Extension | Streamable HTTP |
| [Bolt](plugins/bolt/) | Builder | HTTP |
| [Any MCP Client](plugins/generic/) | Universal | HTTP / stdio |

Don't see your tool? [Open an issue](https://github.com/salt-security/salt-code/issues/new?template=issue.md) and we'll add it.

---

## What Salt Code enforces

Salt Code ships with 40 policies across four security domains:

### API Security (OWASP API Top 10)
Broken object level authorization, broken authentication, excessive data exposure, lack of rate limiting, broken function level authorization, mass assignment, security misconfiguration, injection, improper asset management, and more.

### Agentic Security (MCP)
Prompt injection via MCP tools, tool poisoning, excessive tool permissions, unsafe agent-to-agent communication, unvalidated tool outputs, and insecure MCP server configurations.

### LLM Security
Indirect prompt injection, insecure output handling, training data poisoning vectors in generated code, model denial of service patterns, and supply chain risks in AI-generated dependencies.

### OpenAPI / Swagger Compliance
Missing authentication schemes, undocumented endpoints, improper response schemas, insecure parameter handling (query string auth, PII in URLs), missing rate limit headers, and spec-to-implementation drift.

---

## Try these prompts

Once connected, try these in your AI assistant to see Salt Code in action:

**Explore active policies:**
```
What security policies and guidelines are active?
```

**Watch Salt Code catch a violation:**
```
Design me a Swagger spec for a delete-user API that authenticates 
via a key in the query string and passes the deleted user ID in 
the query string as well.
```
> Salt Code will flag query string authentication (OWASP API2) and PII in the URL before you write a single line of implementation code.

**Audit your codebase:**
```
Can you look at this repository and tell me if it complies with 
the Salt Code policies?
```

---

## MCP server details

| Property | Value |
|----------|-------|
| Server URL | `https://salt-code.secured-api.com/mcp` |
| Transport | HTTP / Streamable HTTP (MCP spec compliant) |
| Authentication | Bearer token (Personal Access Token) |
| Token validity | 180 days |
| Protocol | [Model Context Protocol](https://modelcontextprotocol.io) |

---

## Repository structure

```
salt-code/
├── README.md
├── LICENSE
├── plugins/              # Per-tool config files and install guides
│   ├── claude-code/
│   ├── cursor/
│   ├── vscode/
│   ├── copilot-cli/
│   ├── windsurf/
│   ├── kiro/
│   ├── codex/
│   ├── gemini-cli/
│   ├── antigravity/
│   ├── opencode/
│   ├── jetbrains/
│   ├── grok/
│   ├── lovable/
│   ├── cline/
│   ├── bolt/
│   └── generic/
├── mcp/                  # MCP server manifest and schema
│   └── salt-code.json
├── policies/             # Policy index and documentation
│   ├── api-security.md
│   ├── agentic-security.md
│   ├── llm-security.md
│   └── openapi-compliance.md
└── docs/                 # Additional documentation
    ├── quickstart.md
    ├── token-management.md
    └── troubleshooting.md
```

---

## Get your token

Salt Code is free. No credit card required.

**[→ Get your personal access token at salt.security/getsaltcode](https://salt.security/getsaltcode)**

After signing up, your token arrives by email. Paste it into the [interactive setup page](https://salt.security/getsaltcode/setup) and every install command is pre-filled — one copy, one paste, done.

---

## Contributing

Found a bug or want to request support for a new tool or policy?

[Open an issue](https://github.com/salt-security/salt-code/issues/new) and let us know.

---

## License

MIT — see [LICENSE](LICENSE) for details.

---

<div align="center">

Built by [Salt Security](https://salt.security) · The leader in Agentic AI Connectivity Security

[salt.security](https://salt.security) · [LinkedIn](https://www.linkedin.com/company/saltsecurity/) · [Twitter / X](https://x.com/SaltSecurity)

</div>