# Configuration

Customizing Improver for your needs.

## Memory Location

Your problem history is stored in `improver/memory/history/`.

This folder is gitignored by default to protect your privacy. If you want to track it in git:

```gitignore
# To track memory:
!improver/memory/history/.gitkeep
```

## MCP Servers (Optional)

For web search functionality:

### Tavily (Web Search)

1. Get an API key from [tavily.com](https://tavily.com)
2. Install:
   ```bash
   npm install -g @modelcontextprotocol/server-tavily
   ```
3. Set environment variable:
   ```bash
   export TAVILY_API_KEY=your_api_key_here
   ```

### Filesystem

1. Install:
   ```bash
   npm install -g @modelcontextprotocol/server-filesystem
   ```

2. Configure in your AI tool's MCP settings

## Adding New Skills

Skills are stored in `improver/skills/`. Each skill has:
- `skill.yaml` - Configuration
- `gather.md` - Questions to ask
- `research.md` - Research focus
- `patterns.md` - Common patterns

To add a new skill, see `improver/skills/INDEX.md`.

## Pattern Files

Patterns are stored in `improver/patterns/`:
- `base.md` - Universal patterns
- `{domain}.md` - Domain-specific patterns

Patterns are automatically extracted from your sessions to improve future recommendations.
