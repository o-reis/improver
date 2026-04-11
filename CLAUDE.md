# Improver - Context Engineering for AI Coding

This project uses Improver, a context engineering architecture for structured problem analysis.

---

# ⚠️ CRITICAL: question() SYNTAX - BRACKETS REQUIRED ⚠️

**The `options` array MUST have brackets or the tool will FAIL:**

```
options: [       ← YOU MUST ADD THIS BRACKET!
  {label: "A", description: "..."},
  {label: "B", description: "..."}
]                ← YOU MUST ADD THIS BRACKET!
```

**This is WRONG and will FAIL:**
```
options: 
  {label: "A", description: "..."},
  {label: "B", description: "..."}
```

**This is CORRECT:**
```
options: [
  {label: "A", description: "..."},
  {label: "B", description: "..."}
]
```

---

## Quick Start

```
/improve <your problem>
```

## CRITICAL: Read → Search → THEN Ask Questions

When `/improve` is invoked, you MUST follow this sequence BEFORE asking any questions:

```
PHASE 1: READ (Load all files)

FIRST: Load these files FIRST:
→ improver/IMPROVER.md              → Project overview
→ improver/commands/improve.md      → Workflow instructions

THEN Load remaining files in order:
2. Detect: Domain from keywords      → creative, career, business, tech, health, education, base
3. Load: improver/skills/{domain}/skill.yaml  → Domain config
4. Load: improver/skills/{domain}/gather.md   → Questions to ask
5. Load: improver/skills/{domain}/research.md → How to research
6. Load: improver/skills/{domain}/patterns.md → Applicable patterns
7. Load: improver/skills/base/*               → Universal questions, research, patterns
8. Load: improver/prompts/system.md           → Foundation
9. Load: improver/prompts/01_gather.md       → Phase 1
10. Load: improver/prompts/02_research.md     → Phase 2
11. Load: improver/prompts/03_recommend.md    → Phase 3
12. Load: improver/patterns/{domain}.md       → Domain patterns
13. Load: improver/patterns/base.md            → Base patterns
14. Check: improver/memory/history/           → Similar past problems
15. Load: improver/rules/context.yaml          → Context rules
16. Load: improver/rules/safety.yaml          → Safety rules

PHASE 2: SEARCH (Initial web search)
17. Search the web for general information related to the problem
18. Search improver/memory/history/ for similar past problems

⚠️ DO NOT ASK ANY QUESTIONS UNTIL ALL FILES ARE READ AND INITIAL SEARCH IS COMPLETE
```

## CRITICAL RULES

### Rule 1: Use question() Tool - CORRECT Syntax

⚠️ **YOU MUST use the `question()` function with EXACT syntax. Missing brackets will cause errors.**

**WRONG - This will FAIL:**
```
question(
  questions: [
    {
      header: "Genre",
      question: "What genre?",
      options:           // ❌ MISSING BRACKETS!
        {label: "Rock", description: "..."},
        {label: "Pop", description: "..."}
    }
  ]
)
```

**CORRECT - This works:**
```
question(
  questions: [
    {
      header: "Genre",
      question: "What genre?",
      options: [         // ✅ HAS BRACKETS!
        {label: "Rock", description: "..."},
        {label: "Pop", description: "..."}
      ]
    }
  ]
)
```

**MANDATORY:** `options:` must be followed by `[` then `{...}`, then `{...}`, then `]`

### Rule 1b: Ask SPECIFIC Questions - NOT Generic Ones

⚠️ **Questions MUST be tailored to the user's SPECIFIC problem.**

```
WRONG (Generic questions):
User: "I want to grow my music career"
AI: "What's your goal?" "What's your budget?" "What's your experience?"
// ❌ Generic - could be asked to anyone

CORRECT (Specific questions):
User: "I want to grow my music career"
AI: "You mentioned wanting to grow - are you currently releasing music independently or through a label?"
// ✅ Specific to their situation
```

### Rule 2: Continue After User Answers - DO NOT STOP

⚠️ **After every user answer, CONTINUE the workflow. DO NOT stop.**

```
WRONG (Stopping):
User: "I play alternative rock"
AI: "Great! Let me know if you need anything else."
// Workflow stops ❌

CORRECT (Continue):
User: "I play alternative rock"
AI: "Thanks for that."
[Continue: search, then ask next question]
// Workflow continues ✅
```

### Rule 3: Recommendations ONLY at the END

⚠️ **RECOMMENDATIONS ARE ONLY SHOWN AFTER ALL GATHERING IS COMPLETE**

**DO NOT show recommendations during the gathering/research phase.**

```
WRONG (Recommendations too early):
User: "I play alternative rock"
AI: Based on your answer, here are my recommendations...
// ❌ Recommendations shown before gathering is complete

CORRECT (Only research and questions during gathering):
User: "I play alternative rock"
AI: "Thanks for that."
[Research based on answer]
[Ask next question]
// ✅ No recommendations until the very end
```

## Iterative Workflow

The workflow is **ITERATIVE**, not linear:

```
Problem → Initial Search → Questions → Answers → New Search → More Questions → ... → GATHERING COMPLETE → Recommendations
```

**Key principle:** Research → Question → Answer → Research → Question → Answer → ... → Conclude

### During Gathering Phase

ONLY do these:
- Search based on user input/answers
- Ask questions using `question()` tool
- Acknowledge user answers

### AFTER Gathering is Complete

ONLY then:
- Show ALL recommendations (visible)
- Ask feedback using `question()` tool
- Store in memory

## Skills Available

| Skill | Keywords |
|-------|----------|
| **creative** | music, art, singer, musician, writer, band |
| **career** | job, career, interview, resume, salary |
| **business** | startup, entrepreneur, funding, growth |
| **tech** | programming, code, developer, software |
| **health** | fitness, workout, diet, nutrition |
| **education** | learning, study, course, certification |
| **base** | general (fallback) |

## Workflow

1. User invokes `/improve`
2. **Load ALL files (see order above)**
3. **Initial Search** - Search for general information
4. **Ask Questions** - Use `question()` tool
5. **User Answers** - Wait for response
6. **CONTINUE** - Search based on answer
7. **More Questions** - Use `question()` tool
8. **Repeat** - Continue until gathering is complete
9. **Recommendations** - Generate (VISIBLE to user)
10. **Store** - Save to `improver/memory/history/`

## Rules

- **Use question() tool** - NOT plain text questions
- **Ask specific questions** - NOT generic templates
- **Continue after answers** - DO NOT stop the workflow
- **No subagents** - Handle all tasks directly
- **Recommendations only at end** - Never during gathering phase
- **Validate syntax** - Ensure question() options array brackets are correct
- **Iterate until complete** - Don't rush to recommendations

## Privacy

The `improver/memory/` folder is gitignored to protect user privacy.
