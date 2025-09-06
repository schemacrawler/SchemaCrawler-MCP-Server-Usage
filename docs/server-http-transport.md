# Use the SchemaCrawler AI MCP Server with HTTP Transport

## Pre-requisites

1. Pull the latest image for SchemaCrawler MCP Server
   ```sh
   docker pull schemacrawler/schemacrawler-ai:latest
   ```

## Start the SchemaCrawler AI MCP Server with HTTP Transport

1. Run the SchemaCrawler MCP Server
   ```sh
   docker compose -f schemacrawler-mcpserver.yaml up -d
   ```
2. Check server health in a browser [http://localhost:9292/health](http://localhost:9292/health)


## Use Visual Studio Code MCP Client

1. Connect to the MCP Server in Visual Studio Code (the server is configured in the ".vscode/mcp.json" file)
2. Ask questions about your database in "Agent" mode - here are some examples:
   - "What tables are available in my database?"
   - "Show me the columns in the Books table"
   - "What foreign keys reference the Authors table?"
   - "Are there any design issues with my database schema?"
   - "Write SQL to find books and their authors"
3. Additional "Agent" chat modes are provided in this project too. Use the "database-expert" or "sql-query-assistant" modes for fine-tuned help for specific tasks.


## Use Other MCP Clients

Try other MCP Clients:
- [Microsoft AI Shell](https://learn.microsoft.com/en-us/powershell/utility-modules/aishell/overview?view=ps-modules) for a shell
- ... and more at [Awesome MCP Clients](https://github.com/punkpeye/awesome-mcp-clients)

