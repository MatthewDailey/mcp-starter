# MCP Starter Server

A minimal [ModelContextProtocol](https://modelcontextprotocol.io) server template for building AI assistant tools. This starter provides a basic structure for creating MCP tools that can be used with AI assistants like Claude.

<a href="https://glama.ai/mcp/servers/z0fby9t6i1"><img width="380" height="200" src="https://glama.ai/mcp/servers/z0fby9t6i1/badge" alt="Starter Server MCP server" /></a>

## Features

- Simple "hello world" tool example
- TypeScript + esbuild setup
- Development tools preconfigured

## Setup with Claude

1. Download and install Claude desktop app from [claude.ai/download](https://claude.ai/download)

2. Configure Claude to use this MCP server. If this is your first MCP server, run:

```bash
echo '{
  "mcpServers": {
    "mcp-starter": {
      "command": "npx",
      "args": ["mcp-starter"]
    }
  }
}' > ~/Library/Application\ Support/Claude/claude_desktop_config.json
```

If you have existing MCP servers, add the `mcp-starter` block to your existing config.

3. Restart Claude Desktop.

4. Look for the hammer icon with the number of available tools in Claude's interface to confirm the server is running.

## Development Setup

### Running with Inspector

For development and debugging purposes, you can use the MCP Inspector tool. The Inspector provides a visual interface for testing and monitoring MCP server interactions.

Visit the [Inspector documentation](https://modelcontextprotocol.io/docs/tools/inspector) for detailed setup instructions.

To test locally with Inspector:
```
npm run inspect
```

Or run both the watcher and inspector:
```
npm run dev
```

### Local Development

1. Clone the repository
2. Install dependencies:
```bash
npm install
```
3. Build the project:
```bash
npm run build
```
4. For development with auto-rebuilding:
```bash
npm run watch
```

## Available Tools

The server provides:

- `hello_tool`: A simple example tool that takes a name parameter and returns a greeting

## Creating New Tools

To add new tools:

1. Define the tool schema in `index.ts`
2. Add it to the tools array in the `ListToolsRequestSchema` handler
3. Add the implementation in the `CallToolRequestSchema` handler

See the `hello_tool` implementation as an example.
