# GitHub Copilot Custom Agent Configuration

This directory contains the configuration for the GitHub Copilot Enterprise RFI Assistant custom agent with Model Context Protocol (MCP) integration.

## What's New: MCP Integration

The agent now uses **Model Context Protocol (MCP)** to dynamically access documentation and resources, providing more accurate and up-to-date information than static knowledge sources.

### MCP Servers Configured

1. **Microsoft Learn MCP Server**
   - Endpoint: `https://learn.microsoft.com/api/mcp`
   - Tools: `microsoft_docs_search`, `microsoft_docs_fetch`
   - Access to: Microsoft Learn documentation, GitHub Copilot docs, Azure docs
   - No authentication required (public documentation)

2. **GitHub MCP Server**
   - Package: `@modelcontextprotocol/server-github`
   - Access to: GitHub repositories, documentation, issues, PRs
   - Requires: GitHub Personal Access Token (automatically provided in GitHub Copilot)

## Files in This Directory

### `agent.yml`
Main agent configuration file defining:
- Agent metadata (name, version, description)
- MCP server connections
- Knowledge domains and documentation sources
- Conversation starters and capabilities
- Response formatting guidelines

### `rfi-assistant.md`
Agent persona and instructions in markdown format. Contains:
- Detailed role description
- Instructions for answering RFI questions
- Guidelines for citing sources and maintaining professional tone

### `mcp.json`
MCP server configuration for IDE integration. Defines:
- MCP server endpoints and connection details
- Environment variables for authentication
- Allowed domains for documentation access

## How to Use

### In GitHub Copilot Chat

The agent is automatically available in GitHub Copilot when this repository is part of your organization:

```
@rfi-assistant What data does GitHub Copilot collect?
```

### In VS Code

1. Ensure you have GitHub Copilot installed
2. The MCP servers will be automatically configured
3. Use the agent in Copilot Chat:
   ```
   @rfi-assistant /data-collection
   ```

### With CLI

```bash
gh copilot chat --agent rfi-assistant
```

## MCP Server Benefits

### Microsoft Learn MCP Server
✅ **Real-time documentation access** - Always get the latest official docs
✅ **Search capabilities** - Find specific topics across Microsoft Learn
✅ **Full page fetching** - Get complete documentation pages with code samples
✅ **No authentication needed** - Public documentation is freely accessible

### GitHub MCP Server
✅ **Repository access** - Read files and documentation from GitHub repos
✅ **Issue and PR integration** - Reference existing issues and discussions
✅ **Organization context** - Access your organization's documentation
✅ **Authenticated access** - Secure access to private resources if needed

## Configuration Details

### Environment Variables

The GitHub MCP server uses the `GITHUB_TOKEN` environment variable, which is automatically provided when using GitHub Copilot. No manual configuration needed.

### Allowed Domains

The agent is configured to access documentation from:
- `docs.github.com` - Official GitHub documentation
- `learn.microsoft.com` - Microsoft Learn documentation
- `resources.github.com` - GitHub resource center including Trust Center
- `github.com` - GitHub repositories and content

## Upgrading from Previous Version

The agent has been upgraded from simple URL-based knowledge sources to dynamic MCP integration:

**Before (v1.x):**
- Static `knowledge_sources` with URLs
- Documentation accessed via web links
- Limited to configured URLs

**After (v2.0):**
- Dynamic MCP server integration
- Real-time documentation search and fetch
- Access to entire documentation platforms
- Automatic updates as docs change

## Testing MCP Connections

To verify MCP servers are working:

```
@rfi-assistant Can you search Microsoft Learn for "GitHub Copilot security"?
```

The agent should respond with current documentation from Microsoft Learn.

## Troubleshooting

### Microsoft Learn MCP Server Not Working
- Check network connectivity to `https://learn.microsoft.com/api/mcp`
- Verify no firewall is blocking the endpoint
- MCP server is public and requires no authentication

### GitHub MCP Server Issues
- Ensure `GITHUB_TOKEN` is available (automatic in GitHub Copilot)
- Check GitHub status: https://www.githubstatus.com
- Verify npm package `@modelcontextprotocol/server-github` can be accessed

### Agent Not Responding
- Verify the repository is part of your GitHub organization
- Check that GitHub Copilot Enterprise or Business is enabled
- Ensure you're using `@rfi-assistant` to invoke the agent

## Documentation

For more information about MCP and custom agents:

- [Enhancing GitHub Copilot agent mode with MCP](https://docs.github.com/copilot/tutorials/enhancing-copilot-agent-mode-with-mcp)
- [Creating custom agents for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/coding-agent/create-custom-agents)
- [Microsoft Learn MCP Server](https://learn.microsoft.com/en-us/training/support/mcp-developer-reference)
- [GitHub MCP Server](https://github.com/github/github-mcp-server)

## Support

For issues or questions:
- Open an issue in this repository
- Contact GitHub Copilot support
- Review the main project documentation in the repository root
