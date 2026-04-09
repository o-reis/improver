# Improver Architecture Specification

**Version:** 0.1.0  
**Date:** 2026-04-09

---

## Overview

Improver is a context engineering architecture for AI agentic tools (Claude Code, OpenCode, etc.) that provides systematic information gathering, research, and recommendation capabilities.

## Directory Structure

```
improver/
├── commands/              # Command definitions
│   └── improve.md         # /improve workflow
│
├── prompts/               # Core prompt templates
│   ├── system.md          # Foundation
│   ├── 01_gather.md       # Phase 1
│   ├── 02_research.md     # Phase 2
│   └── 03_recommend.md    # Phase 3
│
├── skills/                # Domain-specific knowledge
│   ├── INDEX.md
│   ├── base/              # Universal skill
│   ├── career/            # Professional development
│   └── creative/          # Arts, music, writing
│       ├── skill.yaml
│       ├── gather.md
│       ├── research.md
│       └── patterns.md
│
├── patterns/              # Learned patterns
│   ├── INDEX.md
│   ├── base.md
│   ├── career.md
│   └── creative.md
│
├── rules/                 # Behavior constraints
│   ├── context.yaml
│   └── safety.yaml
│
├── memory/                # Persistent storage
│   └── INDEX.md
│
├── docs/                  # Documentation
│   ├── ARCHITECTURE.md
│   ├── CONFIGURATION.md
│   └── WORKFLOW.md
│
├── IMPROVER.md            # Main documentation
└── README.md              # Quick reference
```

## Implementation Phases

| Phase | Status | Contents |
|-------|--------|----------|
| Phase 1 | ✅ Complete | Core structure, prompts, rules, memory |
| Phase 2 | ✅ Complete | Skills (base, career, creative), patterns |
| Phase 3 | 📋 Pending | MCP server configurations |
| Phase 4 | 📋 Pending | Additional skills (business, tech, health, education) |
| Phase 5 | 📋 Pending | CLI wrapper (optional) |

## Execution Flow

```
User: /improve [problem]
    ↓
1. Load commands/improve.md
2. Detect domain → Load skills/{domain}/
3. Phase 1: Gather questions
4. Phase 2: Web research
5. Phase 3: Recommendations
6. Store in memory/history/
```

## Storage Format

All stored as **Markdown only** (human and AI readable).

## Next Steps

1. Add more domain skills as needed
2. Configure MCP servers for web search
3. Test with example problems
4. Iterate based on results
