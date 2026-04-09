# Architecture Documentation

Detailed technical specifications for Improver.

## System Overview

Improver is a context engineering architecture that enhances AI agentic tools through:
- Structured prompt templates
- Domain-specific skills
- Pattern-based recommendations
- Persistent memory

## File Types

| Type | Purpose | Format |
|------|---------|--------|
| Commands | Workflow definitions | Markdown |
| Prompts | Instruction templates | Markdown |
| Rules | Behavior constraints | YAML |
| Skills | Domain knowledge | Markdown + YAML |
| Memory | Problem history | Markdown |
| Patterns | Learned insights | Markdown |

## Context Assembly

When Improver activates:

1. **Load System Prompt** → `prompts/system.md`
2. **Detect Domain** → Match keywords to `skills/*/skill.yaml`
3. **Check Memory** → Search `memory/history/` for similar problems
4. **Apply Patterns** → Load from `patterns/*.md`
5. **Execute Phases** → Gather → Research → Recommend
6. **Store Results** → Save to `memory/history/`

## Rule Priority

When rules conflict:
1. Safety rules (highest)
2. Context rules
3. Skill-specific rules
4. User preferences

## Pattern Matching

Patterns are matched by:
1. Domain tag
2. Problem keywords
3. Outcome similarity
4. Recency weight

## Memory Format

Each memory entry:
```markdown
# [Problem Title]

**Date:** YYYY-MM-DD  
**Domain:** skill name  
**Tags:** relevant tags  

## Problem
[User's stated problem]

## Context
[Gathered information]

## Recommendations
1. [Action]
2. [Action]

## Outcome
[Follow-up when available]
```
