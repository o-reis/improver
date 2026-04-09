# Workflow Execution

Step-by-step procedures for Improver operation.

## Phase Execution Order

```
/improve [problem]
    ↓
[Load Command] commands/improve.md
    ↓
[Identify Domain] skills/*/skill.yaml
    ↓
┌─────────────────────────────────────┐
│ PHASE 1: GATHER                      │
│ Read: prompts/01_gather.md           │
│ Read: skills/{domain}/gather.md      │
│ Ask: domain-specific questions       │
│ Wait: user responses                 │
│ Stop: when context is complete        │
└─────────────────────────────────────┘
    ↓
┌─────────────────────────────────────┐
│ PHASE 2: RESEARCH                    │
│ Read: prompts/02_research.md         │
│ Read: skills/{domain}/research.md    │
│ Generate: search queries              │
│ Execute: web searches                 │
│ Synthesize: findings                  │
│ Iterate: if new topics emerge         │
└─────────────────────────────────────┘
    ↓
┌─────────────────────────────────────┐
│ PHASE 3: RECOMMEND                   │
│ Read: prompts/03_recommend.md        │
│ Read: patterns/{domain}.md           │
│ Read: patterns/base.md               │
│ Search: memory/history/ for similar   │
│ Generate: prioritized recommendations │
│ Assess: risks and alternatives        │
└─────────────────────────────────────┘
    ↓
┌─────────────────────────────────────┐
│ PHASE 4: STORE                       │
│ Create: memory/history/{date}_{id}.md │
│ Update: memory/INDEX.md              │
│ Extract: new patterns if applicable  │
│ Update: patterns/{domain}.md          │
└─────────────────────────────────────┘
    ↓
[Present Recommendations to User]
```

## Question Flow

```
Start with universal questions
    ↓
Detect domain from keywords
    ↓
Switch to domain-specific questions
    ↓
Follow up on interesting answers
    ↓
Close gaps with targeted questions
    ↓
Summarize and confirm
    ↓
Proceed to research
```

## Research Flow

```
Extract key concepts from context
    ↓
Generate 3-5 search queries
    ↓
Execute searches
    ↓
Evaluate source quality
    ↓
Extract key findings
    ↓
Identify contradictions
    ↓
Synthesize into insights
    ↓
Check for new topics
    ↓
If new topics: iterate, else proceed
```

## Recommendation Flow

```
Load applicable patterns
    ↓
Search memory for similar problems
    ↓
Identify what worked for similar cases
    ↓
Generate recommendations by timeframe
    ↓
Prioritize by impact/effort ratio
    ↓
Assess risks
    ↓
Format for user
    ↓
Store for future reference
```
