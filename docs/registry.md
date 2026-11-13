# Directory submissions

`server.json` describes the hosted remote MCP server. This repository is
metadata-only, with no open-source license or public server implementation.

## Official MCP Registry

Published on November 13, 2026 as `io.litak/mcp`, version `1.2.0`.
The official API reports `active` and `isLatest: true`:

https://registry.modelcontextprotocol.io/v0.1/servers/io.litak%2Fmcp/versions/latest

The official registry supports publicly accessible remote endpoints. A remote-only
server does not require an npm/Docker package or disclosure of the private app.

1. Review `server.json` and verify the live server version and documented tools.
2. Validate it with the official Registry validation endpoint or the current
   `mcp-publisher validate` command.
3. Install `mcp-publisher` from its official release and authenticate the `litak.io`
   domain using HTTP or DNS verification. Do not commit private signing keys,
   publisher authentication files or tokens.
4. Publish the reviewed descriptor using the current publisher instructions.
5. Verify the resulting registry entry and retain its URL.

The namespace `io.litak/mcp` must be authenticated by the domain owner.
Creating this repository alone does not publish a registry entry.

The `mcp-registry-auth` file contains only a public Ed25519 verification key.
It is served at `https://litak.io/.well-known/mcp-registry-auth` for HTTP-based
ownership verification. The private signing key is kept outside this repository.
The optional repository field is intentionally omitted from `server.json`.

Official instructions:

- https://github.com/modelcontextprotocol/registry/blob/main/docs/modelcontextprotocol-io/remote-servers.mdx
- https://github.com/modelcontextprotocol/registry/blob/main/docs/modelcontextprotocol-io/authentication.mdx
- https://github.com/modelcontextprotocol/registry/blob/main/docs/modelcontextprotocol-io/quickstart.mdx

## Other platforms

Each directory sets its own rules. Some require an approved open-source license,
actual server source, independent review or a private demo account. This repository
does not satisfy a requirement for an open-source server. Do not label the closed
implementation as open source or claim review/endorsement that has not happened.

If a platform requests review credentials, use a disposable account through its
private review process, never a real user's key or a server-side service-role key.
