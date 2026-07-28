# JetBrains AI Assistant

**IntelliJ / WebStorm / PyCharm**

## Install

Replace `<your_token>` with your personal access token from [salt.security/getsaltcode](https://salt.security/getsaltcode).

```json
{
  "mcpServers": {
    "salt-code-mcp": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://salt-code.secured-api.com/mcp",
        "--header",
        "Authorization: Bearer <your_token>"
      ]
    }
  }
}
```

## Verify

Once connected, run this in JetBrains AI Assistant:

```
What security policies and guidelines are active?
```

Salt Code should respond with the list of 40 active policies.

## Need help?

Visit the [interactive setup page](https://salt.security/getsaltcode/setup) for full step-by-step instructions, or [open an issue](https://github.com/salt-security/salt-code/issues/new).
