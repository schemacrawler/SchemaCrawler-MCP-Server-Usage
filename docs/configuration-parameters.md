# Configuration Parameters

| Name | Description | Environment Variable | SchemaCawler CLI Argument  | Docker Catalog MCP Server Configuration |
|---|---|---|---|---|
| Username | Database user name | SCHCRWLR_DATABASE_USER | --user  | schemacrawler-ai.database_user |
| Passowrd | Database user password | SCHCRWLR_DATABASE_PASSWORD | --password  | schemacrawler-ai.database_password |
| JDBC URL | JDBC URL for database connection | SCHCRWLR_JDBC_URL | --url  | schemacrawler-ai.url_connection.jdbc_url |
| Database Type | SchemaCrawler database plugin | SCHCRWLR_SERVER | --server  | schemacrawler-ai.server_connection.server |
| Host | Database host (optional, defaults to localhost) | SCHCRWLR_HOST | --host  | schemacrawler-ai.server_connection.host |
| Port | Database port (optional, defaults to standard port) | SCHCRWLR_PORT | --port  | schemacrawler-ai.server_connection.port |
| Database | Database to connect to (optional) | SCHCRWLR_DATABASE | --database  | schemacrawler-ai.server_connection.database |
| Info Level | How much database metadata to retrieve | SCHCRWLR_INFO_LEVEL | --info-level  | schemacrawler-ai.general.info_level |
| Log Level | Logging verbosity level | SCHCRWLR_LOG_LEVEL | --log-level  | schemacrawler-ai.general.log_level |
