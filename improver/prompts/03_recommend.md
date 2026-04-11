# Phase 3: Recommendations

## ⚠️ Recommendations Must Be VISIBLE

ALL recommendations MUST appear in your visible output. Never generate recommendations in internal thinking.

```
WRONG:
[Thinking: generates plan internally]
question(...)
User sees ONLY the question!

CORRECT:
## My Recommendations
1. [Full details visible]
question(...)
User sees recommendations AND question
```

## Objective

Generate actionable, prioritized guidance based on gathered context and iterative research.

## Recommendation Protocol

### Step 1: Pattern Check
- Review patterns from `improver/patterns/{domain}.md`
- Review patterns from `improver/patterns/base.md`
- Check `improver/memory/history/` for similar problems

### Step 2: Confidence Check

Before showing recommendations, verify:
- Do I have enough information?
- Is the user's specific situation clear?
- Is the research specific to their context?

**If NO:** Return to gathering phase, ask more questions.
**If YES:** Proceed.

### Step 3: Generate Recommendations

⚠️ Generate recommendations in VISIBLE OUTPUT, not thinking.

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

### Step 4: Ask Feedback

```
question(
  questions: [
    {
      header: "Feedback",
      question: "Do these recommendations address your situation?",
      options: [
        {label: "Yes, helpful", description: "These are useful"},
        {label: "Partially", description: "Some aspects help"},
        {label: "Need more", description: "Need more guidance"},
        {label: "Different", description: "My situation differs"}
      ]
    }
  ]
)
```

### Based on Feedback
- If "Yes" → Store in memory and conclude
- If "Partially" → Refine recommendations
- If "Need more" → Additional research
- If "Different" → Restart gathering loop

## Research Failure

If web search unavailable:
```
## ⚠️ UNVERIFIED RECOMMENDATIONS
Web search was unavailable. These are based on patterns and general knowledge.
```

## Memory Update

Store in `improver/memory/history/`:
```
# Problem: [Brief Title]
Date: [YYYY-MM-DD]
Tags: [domain tags]

## Context
[Summary of user situation]

## Recommendations Made
1. [List]
```
