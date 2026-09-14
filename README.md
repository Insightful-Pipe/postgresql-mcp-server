# PostgreSQL MCP Server by Insightful Pipe

[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://insightfulpipe.com/mcp-servers/postgresql)
[![Insightful Pipe](https://img.shields.io/badge/Insightful_Pipe-MCP_Servers-purple)](https://insightfulpipe.com/mcp-servers)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Connect PostgreSQL to AI assistants: schemas, tables, SQL and database health.**

Part of the [Insightful Pipe MCP Server Collection](https://insightfulpipe.com/mcp-servers) — use PostgreSQL from Claude, ChatGPT, Cursor, and other AI assistants through the Model Context Protocol (MCP).

<img src="images/postgresql-icon.svg" alt="PostgreSQL MCP Server" width="64" height="64">

## MCP Server URL

```
https://postgresql.insightfulmcp.com/
```

## What is PostgreSQL MCP?

PostgreSQL MCP is a **remote Model Context Protocol server** hosted by InsightfulPipe. Browse schemas and tables, inspect columns, run SQL, and read pg_stat insights against your own PostgreSQL database. Read vs. read-write is decided by the GRANT/REVOKE privileges on the role this connector logs in as.

## Installation

### Claude

1. Copy the MCP Server URL: `https://postgresql.insightfulmcp.com/`
2. Open [Claude Connectors Settings](https://claude.ai/settings/connectors)
3. Scroll to the bottom and click **Add custom connector**
4. Paste the URL and click **Add**
5. Click **Connect** on the connector to start authorization
6. Click **Authorize access** in the browser to complete the connection

### ChatGPT

Custom MCP servers are added through ChatGPT's **Developer mode**. Availability depends on your ChatGPT plan, and workspace admins may need to allow it.

1. Turn on **Developer mode** in ChatGPT settings
2. Create a new app for a remote MCP server and paste the URL: `https://postgresql.insightfulmcp.com/`
3. Authorize with your InsightfulPipe account

See OpenAI's guide: [Developer mode and MCP apps in ChatGPT](https://help.openai.com/en/articles/12584461-developer-mode-and-mcp-apps-in-chatgpt)

### Claude Code

```bash
claude mcp add --transport http postgresql https://postgresql.insightfulmcp.com/
```

### Cursor

Add the server to `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "postgresql": {
      "url": "https://postgresql.insightfulmcp.com/"
    }
  }
}
```

Then authorize the connection when Cursor prompts you.

## Available Actions

8 actions: 7 read, 1 write.

### Read Actions (7)

| Action | Description |
|--------|-------------|
| `analyze_db_health` | Report database health (connections, vacuum age, replication slots, cache hit rates, invalid constraints) |
| `explain_query` | Return the EXPLAIN plan for a query |
| `get_table_metadata` | Full metadata for a table or view: columns, constraints, indexes, estimated row count, size |
| `get_table_schema` | Return the column list (name, data_type, is_nullable, default) for a table or view |
| `get_top_queries` | Slowest or most resource-intensive queries from the pg_stat_statements extension |
| `list_schemas` | List all schemas in the connected database |
| `list_tables` | List tables, views, sequences, or extensions in a schema |

### Write Actions (1)

| Action | Description |
|--------|-------------|
| `run_query` | Execute a SQL statement against the connected database |

## Usage Examples

```
"List the tables in the public schema"
```

```
"Show the schema of the orders table"
```

```
"Check my database health"
```

## Explore More MCP Servers by Insightful Pipe

Visit **[insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)** to discover our full collection of MCP servers.

- [MySQL MCP](https://insightfulpipe.com/mcp-servers/mysql)
- [SQL Server MCP](https://insightfulpipe.com/mcp-servers/mssql)
- [BigQuery MCP](https://insightfulpipe.com/mcp-servers/bigquery)

**[View All MCP Servers →](https://insightfulpipe.com/mcp-servers)**

## Resources

- [Documentation](https://insightfulpipe.com/docs)
- [Video Tutorial](https://www.youtube.com/playlist?list=PLJNzvjxzI5Xwe__BJJLAelSF0ewO3mEFk)
- [InsightfulPipe Blog](https://insightfulpipe.com/blog)

## Support

- **Documentation**: [insightfulpipe.com/docs](https://insightfulpipe.com/docs)
- **All MCP Servers**: [insightfulpipe.com/mcp-servers](https://insightfulpipe.com/mcp-servers)
- **Email**: support@insightfulpipe.com

---

**[Insightful Pipe](https://insightfulpipe.com)** — AI-powered marketing analytics through MCP servers. [Explore all integrations →](https://insightfulpipe.com/mcp-servers)

## License

MIT License - see [LICENSE](LICENSE) for details.
