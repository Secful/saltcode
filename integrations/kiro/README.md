# Kiro

**AWS agentic IDE**

## Install as a Kiro Power (recommended)

Salt Code ships as a [Kiro Power](https://kiro.dev/docs/powers/) under [`power/`](power/).

1. Get a personal access token from [salt.security/getsaltcode](https://salt.security/getsaltcode).
2. Set the `SALT_CODE_TOKEN` environment variable to that token, and approve it when Kiro prompts (required for `${SALT_CODE_TOKEN}` expansion in the power’s MCP config).
3. In Kiro, open the **Powers** panel → **Add Custom Power** → **Import power from a folder**.
4. Select the `integrations/kiro/power` directory from this repository (the folder that contains `POWER.md`).

You can also import from GitHub once this repo is available: use **Import power from GitHub** and point at this repository, selecting the `integrations/kiro/power` path if prompted.

### Verify

Once the power is installed and the token is approved, ask Kiro:

```
What security policies and guidelines are active?
```

Salt Code should respond with the list of 40 active policies. Mentions of keywords like “API security”, “OpenAPI”, or “MCP security” should activate the power automatically.

### Optional project steering

For workspace-level steering outside Powers, copy [`instructions/salt-code.md`](instructions/salt-code.md) into your project’s Kiro steering configuration.

## Manual MCP install (fallback)

If you prefer to configure MCP directly instead of installing the power, add this to your Kiro MCP settings. Replace `<your_token>` with your personal access token from [salt.security/getsaltcode](https://salt.security/getsaltcode).

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

## Need help?

Visit the [interactive setup page](https://salt.security/getsaltcode/setup) for full step-by-step instructions, or [open an issue](https://github.com/Secful/saltcode/issues).
