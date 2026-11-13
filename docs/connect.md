# Connect an AI assistant

## OAuth

1. Add `https://litak.io/mcp` as a remote Streamable HTTP MCP server.
2. Start authentication and sign in to Litak.
3. Check the client name, return address and requested permissions.
4. Approve only the permissions you want to grant.

OAuth discovery is available at:

- `https://litak.io/.well-known/oauth-protected-resource/mcp`
- `https://litak.io/.well-known/oauth-authorization-server`

## Dedicated Bearer key

1. Open [Litak settings](https://litak.io/settings) and create a dedicated MCP key.
2. Choose its permissions and expiry.
3. Save the key immediately in your AI client's secure credential settings.
4. Configure the server URL above and `Authorization: Bearer <your-key>`.

Generic configuration; exact syntax depends on the client:

```json
{
  "url": "https://litak.io/mcp",
  "headers": { "Authorization": "Bearer <your-dedicated-key>" }
}
```

The placeholder is not a credential. Do not commit a filled-in configuration.
If a client uses an environment variable, its value must contain the real key,
not the literal text of a variable reference. Keep the value out of conversations.

## Verify without changing data

Ask the assistant to list available tools, then read a week plan or another
category you explicitly permitted. Full permissions expose ten tools. A restricted
connection exposes fewer. Read tests should not create tasks or change check-ins.

For the main daily task, reuse a matching existing task and call `set_task_of_day`.
For habit check-ins, follow the reported planned dates. For sleep, report an exact
date and whole number of hours rather than asking to check a generic habit box.

If the client caches an older tool catalog, use its documented reconnect/refresh
flow. A successful server-side tool listing does not prove the client's cache refreshed.

Opening `/mcp` in a normal browser without credentials returns an authentication
error. It is a protocol endpoint, not a dashboard page.
