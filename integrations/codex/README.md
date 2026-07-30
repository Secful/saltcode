# Codex

**OpenAI CLI · ~/.codex/config.toml**

## Install

Replace `<your_token>` with your personal access token from [salt.security/getsaltcode](https://salt.security/getsaltcode).

```toml
[mcp_servers.salt-code-mcp]
type = "http"
url  = "https://salt-code.secured-api.com/mcp"

[mcp_servers.salt-code-mcp.headers]
Authorization = "Bearer <your_token>"
```

## Verify

Once connected, run this in Codex:

```
What security policies and guidelines are active?
```

Salt Code should respond with the list of 40 active policies.

## Need help?

Visit the [interactive setup page](https://salt.security/getsaltcode/setup) for full step-by-step instructions, or [open an issue](https://github.com/salt-security/salt-code/issues/new).
