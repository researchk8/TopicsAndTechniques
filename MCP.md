# Model Context Protocol (MCP)

The Model Context Protocol (MCP) lets you build servers that expose data and functionality to LLM applications in a secure, standardized way. Think of it like a web API, but specifically designed for LLM interactions. MCP servers can:

- Expose data through Resources (think of these sort of like GET endpoints; they are used to load information into the LLM's context)
- Provide functionality through Tools (sort of like POST endpoints; they are used to execute code or otherwise produce a side effect)
- Define interaction patterns through Prompts (reusable templates for LLM interactions)


## Core Concepts

### Server
The FastMCP server is your core interface to the MCP protocol. It handles connection management, protocol compliance, and message routing:

### Resources
Resources are how you expose data to LLMs. They're similar to GET endpoints in a REST API - they provide data but shouldn't perform significant computation or have side effects. Some examples:

- File contents
- Database schemas
- API responses
- System information


### Tools
Tools let LLMs take actions through your server. Unlike resources, tools are expected to perform computation and have side effects. They're similar to POST endpoints in a REST API.


### Prompts
Prompts are reusable templates that help LLMs interact with your server effectively. They're like "best practices" encoded into your server. 

### Images
FastMCP provides an Image class that automatically handles image data in your server:
Images can be used as the result of both tools and resources.

### Context
The Context object gives your tools and resources access to MCP capabilities. To use it, add a parameter annotated with fastmcp.Context:


## Reference servers

* AWS KB Retrieval - Retrieval from AWS Knowledge Base using Bedrock Agent Runtime
* Brave Search - Web and local search using Brave's Search API
* EverArt - AI image generation using various models
* Everything - Reference / test server with prompts, resources, and tools
* Fetch - Web content fetching and conversion for efficient LLM usage
* Filesystem - Secure file operations with configurable access controls
* Git - Tools to read, search, and manipulate Git repositories
* GitHub - Repository management, file operations, and GitHub API integration
* GitLab - GitLab API, enabling project management
* Google Drive - File access and search capabilities for Google Drive
* Google Maps - Location services, directions, and place details
* Memory - Knowledge graph-based persistent memory system
* PostgreSQL - Read-only database access with schema inspection
* Puppeteer - Browser automation and web scraping
* Redis - Interact with Redis key-value stores
* Sentry - Retrieving and analyzing issues from Sentry.io
* Sequential Thinking - Dynamic and reflective problem-solving through thought sequences
* Slack - Channel management and messaging capabilities
* Sqlite - Database interaction and business intelligence capabilities
* Time - Time and timezone conversion capabilities


# Resources
- https://github.com/modelcontextprotocol/servers
- https://github.com/jlowin/fastmcp
- https://github.com/modelcontextprotocol/python-sdk