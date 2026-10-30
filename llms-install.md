# Installing photoaicompany MCP

Remote server — nothing to install or build.

1. Add the server URL `https://mcp.photoai.company/mcp` to your MCP client's config as a Streamable HTTP server named `photoaicompany` (see README.md for per-client snippets).
2. No API key, account, environment variable, or dependency is required for the public endpoint.
3. Verify: open https://mcp.photoai.company/health (expect {"status":"ok","app":"photoaicompany","tools":43}).

Note: this server mutates designs (create/edit/delete). Confirm destructive actions with the user before calling them. The server is stateless — if a client insists on a session, ensure it supports Streamable HTTP (protocol 2025-03-26). SSE-only clients should use an `mcp-remote` bridge pointing at the same URL.
