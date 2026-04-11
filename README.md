# Improver

**Context Engineering Architecture for AI Agentic Tools**

A systematic framework for Claude Code or OpenCode  for improving AI decision-making through structured information gathering, research, and recommendations. 

## IMPORTANT

This README.md as well as all the files were initially made using OpenCode "Big Pickle" AI "agentic" model. There may exist some inaccuracies that I haven't found yet. I am still doing tests to ensure the framework works properly. **This framework is token-intensive, since the model has to load all relevant files (around 18 small files) to fully implement the framework. For that reason, I recommend using this framework with OpenCode, since its free (11/04/2026).**

## What Is Improver?

Improver provides AI agents with:

- **Structured question protocols** - Gather complete context before recommending
- **Research workflows** - Web search integration and knowledge synthesis
- **Pattern memory** - Learn from past recommendations
- **Domain expertise** - 7 skill domains ready to use

## Quick Start

```
/improve <your problem>
```

Example:
```
/improve I want to start a tech startup but don't know where to begin
/improve I'm struggling to land my first software developer job
/improve How can I build an audience for my music?
```

## Features

| Feature | Description |
|---------|-------------|
| **3-Phase Workflow** | Gather → Research → Recommend |
| **7 Domain Skills** | Career, Creative, Business, Tech, Health, Education, Base |
| **100+ Patterns** | Proven approaches per domain |
| **Memory System** | Learn from past sessions |
| **MCP Integration** | Web search and file access |

## Architecture

```
improver/
├── commands/          # /improve workflow
├── prompts/           # Phase templates
├── skills/            # Domain knowledge
├── patterns/          # Learned patterns
├── rules/              # Constraints
├── memory/             # Problem history
├── mcp/                # Tool configs
└── docs/               # Documentation
```

## Documentation

- [Installation Guide](improver/docs/INSTALL.md)
- [Architecture](improver/docs/ARCHITECTURE.md)
- [Workflow](improver/docs/WORKFLOW.md)
- [Configuration](improver/docs/CONFIGURATION.md)
- [Changelog](improver/docs/CHANGELOG.md)

## Available Skills

| Skill | Use For |
|-------|---------|
| `base` | General purpose, fallback |
| `career` | Job hunting, promotions, transitions |
| `creative` | Music, art, writing, performance |
| `business` | Startups, entrepreneurship |
| `tech` | Software development |
| `health` | Fitness, nutrition, wellness |
| `education` | Learning, studying, certifications |

## How It Works

1. **User invokes `/improve`** with a problem statement
2. **AI detects domain** from keywords and loads relevant skill
3. **Phase 1: Gather** - Asks structured questions
4. **Phase 2: Research** - Searches web for insights
5. **Phase 3: Recommend** - Generates prioritized actions
6. **Phase 4: Store** - Saves to memory for future reference

## Privacy

User memory (`improver/memory/history/`) is gitignored by default to protect privacy.

## Contributing

Contributions welcome! See [the documentation](improver/docs/) for architecture details.

## License

MIT
