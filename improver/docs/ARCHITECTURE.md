# Architecture Overview

How Improver works under the hood.

## System Overview

Improver is a context engineering system that helps AI assistants provide better recommendations through:

- **Structured Questions** - Understanding your specific situation
- **Research** - Finding relevant information
- **Patterns** - Learning from past cases
- **Memory** - Remembering your history

## Folder Structure

```
improver/
├── commands/          # Workflow definitions
├── prompts/           # Phase templates
├── skills/            # 7 domain skills
├── patterns/          # Learned patterns
├── rules/             # Safety constraints
├── memory/            # Your problem history (private)
└── mcp/              # Tool integrations
```

## How It Works

When you use `/improve`:

1. **Gather** - Questions tailored to your situation
2. **Research** - Web search for relevant information
3. **Recommend** - Actionable guidance based on your context
4. **Remember** - Stores your case for future reference

## Available Skills

Improver has specialized knowledge in:

| Skill | What it helps with |
|-------|-------------------|
| **Career** | Jobs, interviews, promotions, resumes |
| **Creative** | Music, art, writing, performance |
| **Business** | Startups, entrepreneurship, growth |
| **Tech** | Programming, software development |
| **Health** | Fitness, nutrition, wellness |
| **Education** | Learning, studying, certifications |
| **Base** | General problems |

## Privacy

Your memory is stored locally in `improver/memory/history/` and is gitignored by default to protect your privacy.
