# Getting Started With the SchemaCrawler AI MCP Server

The SchemaCrawler AI MCP Server runs with either the "stdio" or "sse" transports. The server is available as a Docker-verified image from [the Docker MCP Catalog](https://hub.docker.com/mcp/server/schemacrawler-ai/overview), or more recent images from [DockerHub](https://hub.docker.com/repository/docker/schemacrawler/schemacrawler-ai/general).

## Prerequisites

1. Install supporting software
   - Docker
   - Docker Compose
   - Visual Studio Code
2. Clone this project, and open it in Visual Studio Code

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
        "schemacrawler-sqlite": {
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
4. Use Visual Studio Code Agent mode to ask questions about your database. The server should start up automatically. Predefined Visual Studio Code chat modes is available in this projet, and it is better to use those chat modes than plain Agent mode.


> See [additional configuration parameters](./configuration-parameters.md)
