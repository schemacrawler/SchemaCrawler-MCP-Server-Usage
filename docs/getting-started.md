# Getting Started With the SchemaCrawler AI MCP Server

The SchemaCrawler AI MCP Server runs with either the "stdio" or "http" (streamable HTTP) transports. The server is available as a Docker-verified image from [the Docker MCP Catalog](https://hub.docker.com/mcp/server/schemacrawler-ai/overview), or more recent images from [DockerHub](https://hub.docker.com/repository/docker/schemacrawler/schemacrawler-ai).


## Prerequisites

1. Install supporting software
   - [Docker](https://docs.docker.com/engine/install/)
   - Docker Compose
   - [Visual Studio Code](https://code.visualstudio.com/download)
2. Read [Use MCP servers in VS Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers)
3. Clone this project, and open it in Visual Studio Code


## Start from the Docker MCP Catalog

These instructions are for using Visual Studio Code as a client, but with small modifications can work for other clients as well.

1. Ensure that you have Docker installed. If you have Docker Desktop, it will be easier to configure the MCP server. You can download the Docker image aheads of time to make startup quicker. Run `docker pull mcp/schemacrawler-ai`.
2. Set the following configuration in Docker Desktop for the SchemaCawler AI MCP Server.
     - "schemacrawler-ai.server_connection.server" to "sqlite"
     - "schemacrawler-ai.server_connection.database" to "sc.db"
3. In your Visual Studio Code project, create a file called ".vscode/mcp.json", with the following server definition.
    ```json
    {
      "servers": {
        "schemacrawler_sqlite": {
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
4. Use Visual Studio Code Agent mode to ask questions about your database. The server should start up automatically.
  Additional "Agent" chat modes are provided in this project too. Use the "database-expert" or "sql-query-assistant" modes for fine-tuned help for specific tasks.
  A good question to start with is "What tables are available in my database?".


## Configure Your Database

1. Configure a connection to your database in Docker Desktop, and follow the steps above again. See [additional configuration parameters which can be set as environmental variables](https://github.com/schemacrawler/SchemaCrawler-AI/blob/main/schemacrawler-ai-mcpserver/mcp-server-registration.json).


## Next Steps

Start the SchemaCawler AI MCP Server with the [HTTP transport](./server-http-transport.md).
