# MCP client for iPhone: connect MCP tools to Vanta

Vanta can connect to remote Model Context Protocol servers and expose their tools to a compatible model. A server can supply documentation, search, live data or actions. The tool runs at the connected server, even if your chat model runs on your phone.

## What you need

Use a reachable **HTTPS MCP endpoint**, rather than a server's marketing homepage or ordinary REST API. Vanta supports Streamable HTTP and older SSE servers. Its setup flow does not launch desktop `stdio` commands such as `npx` on your phone.

If a server's instructions only provide a command to run locally, you need a remotely hosted MCP endpoint or a secured bridge. Follow the server operator's instructions for its endpoint and authentication. The [official MCP architecture guide](https://modelcontextprotocol.io/docs/learn/architecture) explains the client/server arrangement.

## Add a server

1. Open **Settings → MCP Servers** and add a server.
2. Enter its HTTPS endpoint, for example an endpoint ending in `/mcp`.
3. Choose **HTTP** for a Streamable HTTP server, or **SSE** if the operator specifies that transport. Vanta can fall back when a server requests the older protocol.
4. Select **No authentication**, **Bearer token** or **Custom header**, matching the server's instructions.
5. Run the connection check and review the discovered tool count.
6. Save the server and confirm that it connects.

Secrets belong in the authentication fields. Vanta stores MCP authentication secrets in the Keychain. A plain `http://` MCP address is refused; put the server behind HTTPS or an appropriate secure tunnel.

## Use a compatible model

Enable the tools you want in **Settings → Tools**. Use a remote model that supports tool calls, a selected tool-capable MLX model, or available Apple Intelligence. GGUF models do not make model tool calls in Vanta.

Ask a specific question that needs the tool, then inspect the tool activity and result. A connected server does not guarantee that a model will choose its tool. Apple Intelligence also has system context and schema limits that can prevent an otherwise connected tool from being offered.

## Understand execution and access

Enabled tool calls run automatically during a turn. Do not assume Vanta will ask for approval before each action. Connect trusted servers, restrict their credentials to the access you intend to grant, and disable tools you do not need.

Tool arguments go to the server. That server may call other services or change external state; its result can then go to your chat model. A local model does not prevent those external requests. [Privacy and data flow](https://vantaclient.app/privacy/) covers these boundaries.

## If it does not work

Confirm the endpoint, transport and authentication first. A zero-tool server may be connected without exposing any tools. If discovery succeeds but execution fails, check the tool's required inputs and server-side permissions. If only one model fails, test a simple tool with another compatible model.

See [compatibility](https://vantaclient.app/compatibility/) and [troubleshooting](https://vantaclient.app/docs/troubleshooting/), or send a redacted report to [support](https://vantaclient.app/support/).

---
This page mirrors [https://vantaclient.app/docs/mcp/](https://vantaclient.app/docs/mcp/).
