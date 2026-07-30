# Troubleshooting

## Salt Code isn't showing up in my tool

1. **Check your config file** — make sure the JSON/TOML is valid and saved correctly
2. **Restart your tool fully** — most tools only reload MCP config on startup, not on window reload
3. **Check the URL** — it should be exactly `https://salt-code.secured-api.com/mcp`
4. **Check the transport** — use `http` or `streamableHttp`, not `sse`

## I'm getting 401 Unauthorized

- Your token may be expired (valid for 180 days) — register for a new one at [salt.security/getsaltcode](https://salt.security/getsaltcode)
- Check that the header is exactly `Authorization: Bearer <your_token>` with no extra spaces
- For Cline users: make sure `"type": "streamableHttp"` is set — legacy SSE often drops custom headers

## Salt Code connects but doesn't flag issues

- Try the prompt: `What security policies and guidelines are active?` — if it responds, it's working
- Some tools require you to explicitly enable MCP tools for a session — check your tool's settings

## Still stuck?

[Open an issue](https://github.com/salt-security/salt-code/issues/new) and we'll help.
