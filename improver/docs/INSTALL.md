# Installation Guide

## Prerequisites

- Claude Code, OpenCode, or any agentic AI tool that reads configuration from project directories

## Quick Install

### 1. Download or Clone

```bash
# Clone the repository
git clone https://github.com/yourusername/improver.git

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

### 3. Copy CLAUDE.md

Copy the `CLAUDE.md` file from the improver folder to your project root:

```bash
cp improver/CLAUDE.md ./CLAUDE.md
```

This file contains all the Improver integration rules that the AI model needs to follow.

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
│   ├── memory/                  # Problem history (gitignored)
│   ├── mcp/                     # Tool configs
│   └── docs/                    # Documentation
│
├── CLAUDE.md                     # Copy this from improver/CLAUDE.md
└── ...
```

## Configuration

### MCP Servers (Optional)

For web search functionality, configure MCP servers:

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

By default, memory is stored in `improver/memory/history/`. This location is gitignored by default to protect your privacy.

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
/improve I'm a 2nd year student looking for an internship
/improve How do I build an audience for my music?
```

## How It Works

1. **Gather** - Answer questions about your situation
2. **Research** - AI researches best practices for your case
3. **Recommend** - Receive actionable recommendations

## Privacy

Your memory (`improver/memory/history/`) is gitignored to protect your privacy.

## Uninstall

Simply remove the `improver/` folder and the `CLAUDE.md` file from your project.

## Troubleshooting

| Issue | Solution |
|-------|----------|
| `/improve` not recognized | Ensure `CLAUDE.md` exists in project root |
| Commands not loading | Check that `improver/` folder is present |
| Skills not detected | Verify `improver/skills/` contains subfolders |
| Web search not working | Configure MCP servers and set `TAVILY_API_KEY` |

## Updating

Pull latest changes and review `improver/docs/CHANGELOG.md` for updates. Remember to also update your `CLAUDE.md` if needed.
