# Improver - Context Engineering Architecture

**Version:** 0.1.0  
**Date:** 2026-04-09

---

## IMPORTANT: DO NOT SKIP THE FILE LOADING SEQUENCE

⚠️ **When `/improve` is invoked, you MUST load ALL files in the exact order specified in `improver/commands/improve.md`.**

**DO NOT jump straight to questions. DO NOT use this file as a shortcut.**

The correct workflow is:
1. Load `improver/commands/improve.md` FIRST
2. Load all 16 files listed in the file loading sequence
3. Perform initial web search
4. ONLY THEN ask questions

See `improver/commands/improve.md` for the complete file loading sequence.

---

## Purpose

Improver is a **context engineering architecture** for AI agentic tools that provides:

1. **Structured Information Gathering** - Systematic question protocols
2. **Research Execution** - Web search and synthesis
3. **Context Optimization** - Memory management and patterns
4. **Decision Enhancement** - Skill-based recommendations

## Architecture

```
improver/
├── commands/           # /improve workflow definition
├── prompts/            # Phase templates (Gather, Research, Recommend)
├── skills/             # 7 domain skills
│   ├── base/           # Universal
│   ├── career/         # Professional development
│   ├── creative/       # Arts, music, writing
│   ├── business/       # Entrepreneurship
│   ├── tech/           # Software development
│   ├── health/         # Fitness and wellness
│   └── education/      # Learning and academia
├── patterns/           # Learned patterns by domain
├── rules/              # Context & safety constraints
├── memory/             # Problem history (Markdown)
├── mcp/                # External tool integrations
└── docs/               # Technical documentation
```

## How It Works

1. **Gather** → Questions to understand your situation
2. **Research** → Web search for relevant insights
3. **Recommend** → Actionable, prioritized guidance
4. **Store** → Memory for future reference

## Available Skills

| Skill | Keywords |
|-------|----------|
| Base | general, help, advice, improve |
| Career | job, career, promotion, interview, resume |
| Creative | music, art, singer, writer, creative |
| Business | startup, business, entrepreneur, launch |
| Tech | programming, code, developer, software |
| Health | fitness, workout, diet, nutrition, mental |
| Education | learning, study, course, certification |

## Core Principles

- Never recommend without sufficient context
- Ground recommendations in research
- Learn from patterns and history
- Prioritize user success and safety

## Documentation

- `IMPROVER.md` - This overview
- `docs/ARCHITECTURE.md` - Technical specification
- `docs/WORKFLOW.md` - Execution procedures
- `docs/CONFIGURATION.md` - Configuration reference