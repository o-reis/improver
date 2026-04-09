# Installation Guide

## IMPORTANT

**For OpenCode, instead of CLAUDE.md write AGENTS.md!**

## Prerequisites

- Claude Code, OpenCode, or any agentic AI tool that reads configuration from project directories

## Quick Install

### 1. Download or Clone

```bash
# Clone the repository
git clone https://github.com/o-reis/improver.git

# Or download and extract
```

### 2. Place in Project Root

Copy the `improver/` folder into your project root:

```
your-project/
├── improver/              # Copy this folder
├── src/
├── docs/
└── ...
```

### 3. Create CLAUDE.md (If Not Exists)

If your project doesn't have a `CLAUDE.md`, create one:

```markdown
# Project Name

[Your project description]

## Improver Integration

This project uses Improver for structured problem solving.

```
/improve <your problem>
```

For details, see `improver/IMPROVER.md`.
```

### 4. Link to Existing CLAUDE.md

If you already have a `CLAUDE.md`, add this line:

```markdown
<!-- improver:start -->
This project uses Improver. See `improver/CLAUDE.md` for context engineering setup.
<!-- improver:end -->
```

## Verification

Test that Improver is loaded:

```
/improve test
```

You should receive a response initiating the gather phase.

## Folder Structure

After installation:

```
your-project/
├── improver/
│   ├── commands/improve.md      # /improve workflow
│   ├── prompts/                 # Phase templates
│   ├── skills/                  # 7 domain skills
│   ├── patterns/                # Learned patterns
│   ├── rules/                   # Context & safety
│   ├── memory/                  # Problem history (empty)
│   ├── mcp/                     # Tool configs
│   └── docs/                    # Documentation
│
├── CLAUDE.md                     # Your project config
└── ...
```

## Configuration

### MCP Servers (Optional)

For web search functionality (Opencode already has this feature!), configure MCP servers:

1. Install required packages:
```bash
npm install -g @modelcontextprotocol/server-tavily
npm install -g @modelcontextprotocol/server-filesystem
```

2. Set environment variable:
```bash
export TAVILY_API_KEY=your_api_key_here
```

3. Configure in your AI tool's MCP settings

### Memory Location

By default, memory is stored in `improver/memory/history/`. This location is gitignored by default to protect user privacy.

To track memory in git (optional), modify `.gitignore`:
```gitignore
# improver/memory/history/
# Uncomment to track:
# !improver/memory/history/.gitkeep
```

## Usage

### Basic Usage

```
/improve I want to learn guitar
```

### With Context

```
/improve I'm a beginner guitarist wanting to play in a band
```

### Specific Domain

```
/improve I want to start a SaaS business
```

## Uninstall

Simply remove the `improver/` folder and remove the Improver reference from `CLAUDE.md`.

## Troubleshooting

| Issue | Solution |
|-------|----------|
| `/improve` not recognized | Ensure `CLAUDE.md` exists in project root |
| Commands not loading | Check that `improver/commands/improve.md` exists |
| Skills not detected | Verify `improver/skills/` contains subfolders |
| Web search not working | Configure MCP servers and set `TAVILY_API_KEY` |

## Updating

Pull latest changes and review `improver/docs/CHANGELOG.md` for updates.
