# Using SchemaCrawler AI MCP Server from Docker MCP Gateway

The SchemaCawler AI MCP Server is available as a Docker-verified image from [the Docker MCP Catalog](https://hub.docker.com/repository/docker/schemacrawler/schemacrawler-ai/general).


## Prerequisites

1. Install supporting software
   - [Docker](https://docs.docker.com/engine/install/)
   - Docker Compose
   - [Visual Studio Code](https://code.visualstudio.com/download)
2. Read [Use MCP servers in VS Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers)
3. Clone this project, and open it in Visual Studio Code


## Start from the Docker MCP Catalog

These instructions are for using Visual Studio Code as a client, but with small modifications can work for other clients as well.

1. Ensure that you have Docker Desktop installed. If you have Docker Desktop, it will be easier to configure the MCP server. You can download the Docker image aheads of time to make startup quicker. Run 
   ```sh
   docker pull mcp/schemacrawler-ai
   ```
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
Ask questions about your database in "Agent" mode - here are some examples:
   - "What tables are available in my database?"
   - "Show me the columns in the Books table"
   - "What foreign keys reference the Authors table?"
   - "Are there any design issues with my database schema?"
   - "Write SQL to find books and their authors"
5. Additional agents are provided in this project too. Use the "database-expert" or "sql-query-assistant" agents for fine-tuned help for specific tasks.



## Configure Your Database

1. Configure a connection to your database in Docker Desktop, and follow the steps above again. See [additional configuration parameters which can be set as environmental variables](https://github.com/schemacrawler/SchemaCrawler-AI/blob/main/schemacrawler-ai-mcpserver/mcp-server-registration.json).
