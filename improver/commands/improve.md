# /improve Command

## Purpose
Structured problem analysis and recommendation system.

## Invocation
```
/improve <problem statement>
```

## Workflow Phases

### Phase 1: Gather
Read: `prompts/01_gather.md`

Execute the information gathering protocol to collect:
- User context and background
- Specific constraints and requirements
- Success metrics and timeline
- Resources available

### Phase 2: Research
Read: `prompts/02_research.md`

Execute research protocol:
- Generate search queries from gathered information
- Search the web for relevant insights
- Synthesize findings into actionable knowledge
- Iterate if new topics emerge

### Phase 3: Recommend
Read: `prompts/03_recommend.md`

Generate recommendations:
- Check memory/history for similar problems
- Apply pattern matching from `patterns/`
- Generate prioritized action items
- Store in `memory/history/` with timestamp

## Rules
All phases must follow rules defined in:
- `rules/context.yaml`
- `rules/safety.yaml`
