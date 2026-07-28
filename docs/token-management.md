# Token Management

## Your personal access token

Your Salt Code personal access token (PAT) is issued when you register at [salt.security/getsaltcode](https://salt.security/getsaltcode).

- **Validity** — 180 days from issue date
- **Scope** — Personal and non-transferable
- **Storage** — Stored in your tool's MCP config file, never sent to Salt servers except as a Bearer header to authenticate MCP requests

## Security best practices

- Do not commit your token to version control
- Do not share your token with others
- Store it in your tool's config file, not in environment variables checked into repos
- Rotate it if you believe it has been compromised

## Token rotation

After your token expires or if you need to rotate it:

1. Register for a new token at [salt.security/getsaltcode](https://salt.security/getsaltcode)
2. Update the `Authorization` header in your tool's MCP config
3. Restart your tool to pick up the new token

## Revoking a token

To revoke your token, contact [security@salt.security](mailto:security@salt.security).
