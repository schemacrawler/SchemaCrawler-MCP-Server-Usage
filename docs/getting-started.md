# Getting Started With the SchemaCrawler AI MCP Server

The SchemaCrawler AI MCP Server runs with either the "stdio" or "sse" transports. The server is available as a Docker-verified image from [the Docker MCP Catalog](https://hub.docker.com/mcp/server/schemacrawler-ai/overview), or more recent images from [DockerHub](https://hub.docker.com/repository/docker/schemacrawler/schemacrawler-ai/general).


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


## Configuration Parameters

| Docker Catalog MCP Server Configuration | Description | Environment Variable | SchemaCawler CLI Argument |
|----------|----------|----------|----------|
| schemacrawler-ai.database_user | Database user name. Can be optional depending on the database connection type. | `SCHCRWLR_DATABASE_USER` | `--user` |
| schemacrawler-ai.database_password | Database user password.Can be optional depending on the database connection type. | `SCHCRWLR_DATABASE_PASSWORD` | `--password` |
| schemacrawler-ai.url_connection.jdbc_url | JDBC URL for database connection. If this is provided, the server, host, port and database are not used. | `SCHCRWLR_JDBC_URL` | `--url` |
| schemacrawler-ai.server_connection.server | SchemaCrawler database plugin, for example, "sqlserver" or "sqlite". Used only if the JDBC URL is not provided. | `SCHCRWLR_SERVER` | `--server` |
| schemacrawler-ai.server_connection.host | Database host. Defaults to localhost. Used only if the JDBC URL is not provided. | `SCHCRWLR_HOST` | `--host` |
| schemacrawler-ai.server_connection.port | Database port. Defaults to the default port for the server type. Used only if the JDBC URL is not provided. | `SCHCRWLR_PORT` | `--port` |
| schemacrawler-ai.server_connection.database | Database to connect to (optional). Used only if the JDBC URL is not provided. | `SCHCRWLR_DATABASE` | `--database`|
| schemacrawler-ai.general.info_level | How much database metadata to retrieve. Values are "minimum", "standard", "detailed" or "maximum". | `SCHCRWLR_INFO_LEVEL` | `--info-level` |
| schemacrawler-ai.general.log_level | Logging verbosity level. Values are "SEVERE", "WARNING", "INFO", "CONFIG", or "FINE".  | `SCHCRWLR_LOG_LEVEL` | `--log-level` |
