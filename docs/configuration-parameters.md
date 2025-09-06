# Configuration Parameters

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
