# Docker MCP

You can use the SchemaCrawler AI MCP Server obtained from the [the Docker MCP Catalog](https://hub.docker.com/mcp/server/schemacrawler-ai/overview) as a Docker-verified image. To use it, configure your "mcp.json" file like this:

```json
{
  "servers": {
    "schemacrawler": {
      "command": "docker",
      "args": [
        "--log-level",
        "debug",
        "mcp",
        "gateway",
        "run",
        "--long-lived",
        "--verbose"
      ],
      "type": "stdio"
    }
  }
}
```
