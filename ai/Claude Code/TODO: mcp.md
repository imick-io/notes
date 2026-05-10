# MCP Servers

**MCP (Model Context Protocol)** is an open standard that lets AI models like Claude connect to external tools, data sources, and services in a structured way.

An **MCP server** is a small process that exposes capabilities to Claude through that protocol. It sits between Claude and some external system.

Each MCP server exposes one or more of:

- **Tools** — functions Claude can call (e.g., run a SQL query, search the web, send a Slack message)
- **Resources** — data Claude can read (e.g., files, database records, API responses)
- **Prompts** — reusable prompt templates the server provides

## Why It Matters

Without MCP, Claude only knows what's in its context window. With an MCP server, Claude can reach outside that window — query live data, interact with your infrastructure, or trigger real-world actions — all within the conversation.

## 

## Up-to-Date Documentation

One of the most practical uses for MCP is giving Claude access to current documentation. By default, Claude's knowledge has a training cutoff — it may not know about the latest version of Tailwind, Better Auth, or whatever library you're using. An MCP server can bridge that gap by fetching live docs on demand.

A useful tool for this is [Context7](https://context7.com/). It exposes library documentation as an MCP server, so Claude can look up accurate, version-specific docs mid-conversation instead of guessing from stale training data.

Context7 supports both local and remote installation. Since their setup instructions may evolve, follow their official documentation for the current recommended approach.