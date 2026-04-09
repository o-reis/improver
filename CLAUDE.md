# Improver - Context Engineering for AI Coding

This project uses Improver, a context engineering architecture for structured problem analysis.

## Quick Start

```
/improve <your problem>
```

## What Happens

1. **Gather** - Questions to understand your situation
2. **Research** - Web search for relevant insights
3. **Recommend** - Actionable, prioritized guidance
4. **Store** - Saves to memory for future reference

## Architecture

```
improver/
├── commands/improve.md     # Workflow definition
├── prompts/                # Phase templates
│   ├── system.md          # Foundation
│   ├── 01_gather.md       # Questions
│   ├── 02_research.md     # Search & synthesis
│   └── 03_recommend.md   # Recommendations
├── skills/                 # Domain knowledge
│   ├── base/
│   ├── career/
│   ├── creative/
│   └── ...
├── patterns/              # Learned patterns
├── rules/                 # Constraints
│   ├── context.yaml
│   └── safety.yaml
└── memory/                # Problem history (private)
```

## Integration

Improver prompts are loaded by the AI when `/improve` is invoked. The architecture files are referenced during execution.

## Skills Available

- **base** - General purpose
- **career** - Job and professional development
- **creative** - Arts, music, writing
- **business** - Startups and entrepreneurship
- **tech** - Software development
- **health** - Fitness and wellness
- **education** - Learning and academia

## Workflow

1. User invokes `/improve`
2. AI loads `commands/improve.md`
3. Detects domain from keywords → loads `skills/{domain}/`
4. Executes Phase 1: Gather questions
5. Executes Phase 2: Web research
6. Executes Phase 3: Recommendations
7. Stores in `memory/history/`

## Privacy

The `memory/` folder is gitignored to protect user privacy.
