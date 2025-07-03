<!-- markdownlint-disable MD041 -->
[![Docker Pulls](https://img.shields.io/docker/pulls/schemacrawler/schemacrawler?color=FFDAB9)](https://hub.docker.com/r/schemacrawler/schemacrawler/)
![GitHub Repo stars](https://img.shields.io/github/stars/schemacrawler/schemacrawler?style=social)


# <img src="https://raw.githubusercontent.com/schemacrawler/SchemaCrawler/main/schemacrawler-website/src/site/resources/images/schemacrawler_logo.png" height="100px" width="100px" valign="middle"/> SchemaCrawler - MCP Server Usage

> [!NOTE]  
> * Please see the [SchemaCrawler website](https://www.schemacrawler.com/) for more details.
> * Explore the SchemaCrawler command-line with a [live online tutorial](https://killercoda.com/schemacrawler).

## About

SchemaCrawler is a free database schema discovery and comprehension tool. SchemaCrawler has a good mix of useful features for data governance. You can [search for database schema objects](https://www.schemacrawler.com/schemacrawler-grep.html) using regular expressions, and output the schema and data in a readable text format.

This is a bare project that acts as an MCP client for the [SchemaCrawler MCP Server](https://github.com/schemacrawler/SchemaCrawler-AI) for use in "Agent" mode.

## Prerequisites

1. Supporting software
   - Docker
   - Docker Compose
   - Visual Studio Code
2. Clone this projects, and open it in Visual Studio Code


## Start the SchemaCrawler MCP Server

1. Pull the latest image for SchemaCrawler MCP Server
   ```sh
   docker pull schemacrawler/schemacrawler-ai:early-access-release
   ```
2. Run the SchemaCrawler MCP Server
   ```sh
   docker compose -f schemacrawler-mcpserver.yaml up -d
   ```
3. Check server health in a browser [http://localhost:8080/health](http://localhost:8080/health)


## Use Visual Studio Code MCP Client

1. Read [Use MCP servers in VS Code](https://code.visualstudio.com/docs/copilot/chat/mcp-servers)
2. Connect to the MCP Server in Visual Studio Code (the server is configured in the ".vscode/mcp.json" file)
3. Ask questions about your database in "Agent" mode - here are some examples:
   - "What tables are available in my database?"
   - "Show me the columns in the Books table"
   - "What foreign keys reference the Authors table?"
   - "Are there any design issues with my database schema?"
   - "Write SQL to find books and their authors"


## Connect to Your Database

1. Stop the SchemaCrawler MCP Server
   ```sh
   docker compose -f schemacrawler-mcpserver.yaml down -t0
   ```
2. Edit the "schemacrawler-mcpserver.yaml" file to add [your database connection details](https://www.schemacrawler.com/database-support.html)
3. Restart the SchemaCrawler MCP Server
