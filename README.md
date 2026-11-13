# Litak MCP

Connection metadata and documentation for the hosted [Litak](https://litak.io)
Model Context Protocol server.

**MCP server:** `https://litak.io/mcp`

**Transport:** Streamable HTTP

**Authentication:** OAuth with PKCE, or a dedicated Litak Bearer key.

Add the server URL in your AI client and choose the permissions you want to grant.
For key-based clients, create a key in [Litak settings](https://litak.io/settings)
and store it in the client's secure configuration. Never paste keys into an AI
conversation or commit them to a repository.

See [connection instructions](docs/connect.md) and the
[Litak connection guide](https://litak.io/mcp-guide).

## Capabilities

| Tool | Permission | Purpose |
| --- | --- | --- |
| `get_goals` | `goals:read` | Read life, year, quarter or week goals |
| `get_habits` | `habits:read` | Read habits, check-ins and planned dates |
| `get_week_plan` | `planner:read` | Read the week plan and main daily task |
| `get_wheel_result` | `wheel:read` | Read the latest saved Wheel of Life scores |
| `create_task` | `planner:write` | Create an agreed ordinary task |
| `set_task_of_day` | `planner:write` | Set an existing task as the main daily task |
| `set_task_completion` | `planner:write` | Record task completion |
| `set_habit_completion` | `habits:write` | Record completion on a planned day or undo a check |
| `get_sleep` | `sleep:read` | Read recorded sleep hours |
| `set_sleep_entry` | `sleep:write` | Record explicitly reported whole sleep hours, 0–24 |

Available tools depend on the permissions granted to the connection. Writes
require the matching read permission. Sleep has separate read/write permissions.
Creating a task alone does not make it the main daily task. Missing sleep values
mean no value was recorded, not zero hours.

## What this repository contains

This repository contains **only public connection metadata and documentation**.
The Litak application and MCP implementation remain private. No application
source, private Git history, credentials, account records or database exports are
included. This repository is not a self-hostable server or an open-source release.

[`server.json`](server.json) is published in the official MCP Registry as
[`io.litak/mcp`](https://registry.modelcontextprotocol.io/v0.1/servers/io.litak%2Fmcp/versions/latest),
version `1.2.0`. The domain was verified through HTTP. A registry listing is
metadata, not a security review or endorsement. See [submission instructions](docs/registry.md).

## Privacy and rights

A connected AI client can receive data covered by the permissions you grant.
Its own privacy and retention policies also apply. Access can be revoked in Litak
settings. See [Litak privacy](https://litak.io/privacy) and [SECURITY.md](SECURITY.md).

No MIT or other open-source license is granted. See [COPYRIGHT.md](COPYRIGHT.md).
Directories requiring an approved open-source license or actual public server
source may not accept this metadata-only repository.
