# MCP Client in Visual Studio Code

Bare project that acts as an MCP client, and allows connections to MCP servers for use in "Agent" mode.

## Start MCP Server

Run the MCP Server

```sh
docker-compose -f schemacrawler-mcpserver.yaml up -d
```

Check health in a browser [http://localhost:8080/health](http://localhost:8080/health)

## Use Visual Studio Code MCP Client

- Connect to the MCP Server in Visual Studio Code
- Ask questions about the database in "Agent" mode
