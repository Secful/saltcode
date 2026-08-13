# Cursor

**Editor · macOS / Windows / Linux**

## Install as a Cursor Plugin (recommended)

Salt Code ships as a [Cursor Plugin](https://cursor.com/docs/plugins) under [`plugin/`](plugin/).

1. Get a personal access token from [salt.security/getsaltcode](https://salt.security/getsaltcode).
2. Install the plugin from the `integrations/cursor/plugin` directory (the folder that contains `.cursor-plugin/plugin.json`), via Cursor’s plugin install / Customize flow.
3. Open **Plugins → Configure** on Salt Code and set `SALT_CODE_TOKEN` to your token.

### Verify

Once the plugin is installed and the token is configured, ask Cursor:

```
What security policies and guidelines are active?
```

Salt Code should respond with the list of 40 active policies.

### Optional project rules

For workspace-level rules outside the plugin, copy [`instructions/.cursorrules`](instructions/.cursorrules) into your project.

## Manual MCP install (fallback)

If you prefer to configure MCP directly instead of installing the plugin, add this to your Cursor MCP settings. Replace `<your_token>` with your personal access token from [salt.security/getsaltcode](https://salt.security/getsaltcode).

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
