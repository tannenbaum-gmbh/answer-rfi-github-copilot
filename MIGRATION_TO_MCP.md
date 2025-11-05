# Migration Guide: Moving to Custom Agent Mode with MCP

This guide explains the upgrade from the previous configuration to Custom Agent Mode with Model Context Protocol (MCP) integration.

## What Changed?

### Version 1.x (Previous)
- Used static `knowledge_sources` with URL links
- Documentation accessed via web search
- Limited to pre-configured URLs
- Manual updates needed when docs changed

### Version 2.0 (Current)
- Uses **Custom Agent Mode** with MCP servers
- Real-time documentation access via Microsoft Learn and GitHub MCP servers
- Dynamic search and fetch capabilities
- Automatic updates as documentation changes
- Better integration with GitHub Copilot's agent infrastructure

## Key Improvements

### 1. Model Context Protocol (MCP) Integration

**Microsoft Learn MCP Server:**
- Endpoint: `https://learn.microsoft.com/api/mcp`
- Tools: `microsoft_docs_search`, `microsoft_docs_fetch`
- Real-time access to Microsoft and GitHub Copilot documentation
- No authentication required for public docs

**GitHub MCP Server:**
- Package: `@modelcontextprotocol/server-github`
- Access to GitHub repositories and documentation
- Authenticated access via GitHub token (automatic in Copilot)

### 2. New Directory Structure

```
.github/
├── agents/                     # NEW: Custom agent configuration
│   ├── agent.yml              # Main agent config with MCP servers
│   ├── rfi-assistant.md       # Agent instructions (markdown)
│   ├── mcp.json              # MCP server configuration
│   └── README.md             # Agent documentation
└── copilot/                   # LEGACY: Old configuration (kept for compatibility)
    ├── agent.yml             # Old static configuration
    └── agents/
        └── rfi-assistant.json # Old VS Code config
```

### 3. Enhanced Capabilities

**New Agent Capabilities:**
- `search_microsoft_learn_docs` - Search across Microsoft Learn
- `access_github_documentation` - Fetch GitHub docs dynamically
- Real-time documentation updates
- Better context understanding

## Migration Steps

### For Users

**No action required!** The new configuration is backwards compatible. Your existing workflows continue to work:

1. **Prompt files** in `prompts/` directory - ✅ Still work
2. **Slash commands** - ✅ Still work
3. **Direct questions** to `@rfi-assistant` - ✅ Still work

**New features available immediately:**
- The agent now has real-time access to documentation
- Responses include the latest information from Microsoft Learn
- Citations link to current documentation pages

### For Developers/Administrators

If you've customized the agent configuration:

1. **Review new configuration**: Check `.github/agents/agent.yml`
2. **MCP server settings**: Review `.github/agents/mcp.json`
3. **Environment variables**: No new variables needed (GitHub token is automatic)
4. **Network access**: Ensure access to:
   - `https://learn.microsoft.com/api/mcp`
   - `https://api.githubcopilot.com/mcp/`

## File Changes

### New Files

| File | Purpose |
|------|---------|
| `.github/agents/agent.yml` | Main custom agent configuration with MCP |
| `.github/agents/rfi-assistant.md` | Agent instructions in markdown |
| `.github/agents/mcp.json` | MCP server connection details |
| `.github/agents/README.md` | Agent documentation |
| `MIGRATION_TO_MCP.md` | This migration guide |

### Deprecated Files

| File | Status | Notes |
|------|--------|-------|
| `.github/copilot/agent.yml` | Legacy | Kept for backwards compatibility |
| `.github/copilot/agents/rfi-assistant.json` | Legacy | VS Code-specific config |

**Note:** Legacy files are kept to ensure compatibility with older Copilot versions.

## Benefits of MCP Integration

### 1. Real-Time Documentation Access
```
Before: Static URLs in configuration
After:  Dynamic search and fetch via MCP

Example:
@rfi-assistant What's new in GitHub Copilot Enterprise?
# Now returns the latest features, not just what was in the config
```

### 2. Better Search Capabilities
```
Before: Limited to pre-configured pages
After:  Search entire Microsoft Learn and GitHub Docs

Example:
@rfi-assistant Search for "GitHub Copilot data retention policy"
# MCP server searches all relevant docs and returns current info
```

### 3. Automatic Updates
```
Before: Manual config updates when docs changed
After:  Always current information via MCP

Example:
When GitHub updates SOC 2 certification info:
- Old: Required config update
- New: Automatically reflects latest info
```

## Testing the New Configuration

### Test MCP Connectivity

```bash
# In GitHub Copilot Chat
@rfi-assistant Can you search Microsoft Learn for "GitHub Copilot security"?
```

Expected: The agent should search and return current results from Microsoft Learn.

### Test Documentation Fetch

```bash
@rfi-assistant Fetch the latest information about GitHub Copilot data collection
```

Expected: Current documentation with proper citations.

### Test GitHub MCP Server

```bash
@rfi-assistant What GitHub Copilot documentation is available in the GitHub docs?
```

Expected: List of relevant documentation pages from docs.github.com.

## Troubleshooting

### Agent Not Using MCP Servers

**Symptom:** Agent responds but doesn't seem to search documentation dynamically.

**Solutions:**
1. Verify GitHub Copilot Enterprise/Business is enabled
2. Check that the repository is in your organization
3. Ensure IDE has latest GitHub Copilot extension
4. Try reloading the IDE window

### MCP Server Connection Errors

**Symptom:** Error messages about MCP servers.

**Solutions:**
1. Check network connectivity to `learn.microsoft.com` and GitHub
2. Verify no corporate firewall blocks the MCP endpoints
3. Ensure GitHub token is available (automatic in Copilot)
4. Check IDE error logs for specific MCP issues

### Documentation Out of Date

**Symptom:** Agent returns old information.

**This should not happen with MCP!** If it does:
1. Verify MCP servers are actually being used (check agent logs)
2. Test MCP connectivity with test queries
3. Report issue if MCP is working but data seems stale

## FAQ

### Q: Do I need to change my prompt files?
**A:** No, all existing prompt files continue to work without changes.

### Q: Will my slash commands still work?
**A:** Yes, slash commands work exactly as before, but now with better documentation access.

### Q: Do I need to configure GitHub tokens?
**A:** No, GitHub Copilot automatically provides the necessary authentication.

### Q: Can I still use the old configuration?
**A:** Yes, the old configuration is kept for backwards compatibility, but the new MCP-based agent provides better results.

### Q: How do I know if MCP is working?
**A:** Ask the agent to search or fetch documentation. If it returns current information with proper citations, MCP is working.

### Q: What if my firewall blocks MCP endpoints?
**A:** Work with your IT team to allow access to:
- `https://learn.microsoft.com/api/mcp`
- `https://api.githubcopilot.com/mcp/`
- Or fallback to legacy configuration if needed

## Additional Resources

- [GitHub Copilot Custom Agents Documentation](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/coding-agent/create-custom-agents)
- [Enhancing Copilot with MCP](https://docs.github.com/copilot/tutorials/enhancing-copilot-agent-mode-with-mcp)
- [Microsoft Learn MCP Server](https://learn.microsoft.com/en-us/training/support/mcp-developer-reference)
- [GitHub MCP Server](https://github.com/github/github-mcp-server)

## Support

If you encounter issues with the migration:
1. Check this guide's troubleshooting section
2. Review `.github/agents/README.md` for configuration details
3. Open an issue in this repository
4. Contact GitHub Copilot support

---

**Welcome to Custom Agent Mode with MCP!** 🚀

The agent now has real-time access to documentation and provides more accurate, up-to-date responses for your RFI questionnaires.
