# Phase 3: Recommendations

## Objective
Generate actionable, prioritized guidance based on gathered context and research.

## Recommendation Protocol

### Step 1: Pattern Check

Before generating new recommendations:
1. Read `patterns/INDEX.md` for relevant patterns
2. Search `memory/history/` for similar problems
3. Apply learned insights to current situation

### Step 2: Recommendation Generation

Generate recommendations following this structure:

#### Immediate Actions (This Week)
1. **[Action Title]**
   - What: [specific action]
   - Why: [rationale from research]
   - How: [practical steps]

#### Short-term Goals (1-3 Months)
2. **[Goal Title]**
   - Milestone: [specific target]
   - Steps: [numbered approach]

#### Long-term Strategy (3-12 Months)
3. **[Strategy Title]**
   - Vision: [end state]
   - Phases: [how to get there]

### Step 3: Prioritization

Rank recommendations by:
1. **Impact** - How much will this help?
2. **Effort** - How much work required?
3. **Timing** - When should this start?
4. **Dependencies** - What must come first?

Present as priority matrix:

| Priority | Action | Impact | Effort | Timeframe |
|----------|--------|--------|--------|-----------|
| 1 | [Action] | High | Low | Immediate |
| 2 | [Action] | High | Medium | Short-term |
| ... | ... | ... | ... | ... |

### Step 4: Risk Assessment

For each high-impact recommendation:
- What could go wrong?
- How to mitigate?
- What is the backup plan?

### Step 5: Memory Update

After recommendations, create entry in `memory/history/`:
```
# Problem: [Brief Title]
Date: [YYYY-MM-DD]
Tags: [domain tags]

## Context
[Summary of user situation]

## Recommendations Made
1. [List]
2. [List]

## Follow-up Notes
[Space for future reference]
```

Note: `memory/INDEX.md` update is optional. The history folder is private and gitignored.

## Recommendation Rules

1. Be specific, not generic
2. Ground in research findings
3. Acknowledge user constraints
4. Provide alternatives
5. Set realistic expectations
