# Security and privacy

This repository contains connection metadata and documentation only. It does not
contain the implementation, credentials or account data. A public repository or
registry listing is not a security certification of a hosted service.

## Connect carefully

- Use the exact server URL `https://litak.io/mcp`.
- With OAuth, confirm the client, callback address and requested permissions.
- With a dedicated key, store it in the client's credential settings, not a URL,
  source file, screenshot or conversation.
- Grant only the read/write permissions you need. Sleep requires separate grants.
- Revoke unused connections in Litak settings. Replace a key if you exposed it.
- The AI provider receives the data you authorize it to access; its retention
  practices are separate from Litak's access controls.

Do not submit real keys, private records or exploit details in public issues.
Use [private vulnerability reporting](https://github.com/Givi-hub/litak-mcp/security/advisories/new)
for security reports. There is no promised response SLA or bug-bounty program.
