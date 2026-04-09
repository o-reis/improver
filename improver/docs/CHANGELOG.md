# Improver Changelog

All notable changes to this project will be documented in this file.

## [0.1.0] - 2026-04-09

### Added
- Initial architecture release
- Core prompts (system, gather, research, recommend)
- 7 domain skills (base, career, creative, business, tech, health, education)
- Pattern system with domain-specific patterns
- Context and safety rules
- MCP configuration for Tavily and Filesystem servers
- Memory structure with INDEX
- Comprehensive documentation (ARCHITECTURE, WORKFLOW, CONFIGURATION, INSTALL)

### Structure
```
improver/
├── commands/          # Workflow definitions
├── prompts/           # Phase templates
├── skills/            # Domain skills
├── patterns/          # Learned patterns
├── rules/             # Constraints
├── memory/            # User history (gitignored)
├── mcp/               # Tool integrations
└── docs/              # Documentation
```

## Future Plans

- [ ] Additional domain skills
- [ ] MCP server implementations
- [ ] CLI wrapper
- [ ] Pattern learning automation
