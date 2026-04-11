# /improve Command

## Purpose
Structured problem analysis and recommendation system.

## Invocation
```
/improve <problem statement>
```

---

## ⚠️ CRITICAL: question() SYNTAX

**The `options` array MUST have brackets:**

```
options: [         ← YOU MUST ADD THIS BRACKET!
  {label: "A", description: "..."},
  {label: "B", description: "..."}
]                  ← YOU MUST ADD THIS BRACKET!
```

**WRONG (will fail):**
```
options: 
  {label: "A", description: "..."},
  {label: "B", description: "..."}
```

**CORRECT:**
```
options: [
  {label: "A", description: "..."},
  {label: "B", description: "..."}
]
```

---

## File Loading Sequence

Load these files in order before asking questions:

1. Load: improver/skills/{domain}/skill.yaml → Domain config
2. Load: improver/skills/{domain}/gather.md → Questions to ask
3. Load: improver/skills/{domain}/research.md → How to research
4. Load: improver/skills/{domain}/patterns.md → Applicable patterns
5. Load: improver/skills/base/gather.md → Universal questions
6. Load: improver/skills/base/research.md → Universal research
7. Load: improver/skills/base/patterns.md → Universal patterns
8. Load: improver/prompts/system.md → Foundation prompt
9. Load: improver/prompts/01_gather.md → Phase 1
10. Load: improver/prompts/02_research.md → Phase 2
11. Load: improver/prompts/03_recommend.md → Phase 3
12. Load: improver/patterns/{domain}.md → Domain patterns
13. Load: improver/patterns/base.md → Base patterns
14. Load: improver/memory/history/ → Check similar problems
15. Load: improver/rules/context.yaml → Context rules
16. Load: improver/rules/safety.yaml → Safety rules

Then: Search web + memory for related information.

⚠️ DO NOT ASK QUESTIONS UNTIL ALL FILES ARE LOADED.

## Domain Detection

Detect domain from keywords:
- **creative**: music, art, singer, musician, writer, band
- **career**: job, career, interview, resume, salary
- **business**: startup, business, entrepreneur, funding
- **tech**: programming, code, developer, software
- **health**: fitness, workout, diet, nutrition
- **education**: learning, study, course, certification
- **base**: general (fallback)

## Execution Flow

```
1. Load all files
2. Detect domain
3. Initial web search
4. Ask SPECIFIC questions using question() tool
5. User answers
6. Continue: search based on answer, ask more questions
7. Repeat until gathering complete
8. Show recommendations (visible)
9. Ask feedback
10. Store in memory
```

## Question Syntax

Use the `question()` tool with this format:

```javascript
question(
  questions: [
    {
      header: "Label",
      question: "Your question?",
      options: [
        {label: "Option 1", description: "Desc"},
        {label: "Option 2", description: "Desc"}
      ]
    }
  ]
)
```

⚠️ The `options` array MUST have brackets: `options: [{...}, {...}]`

See CLAUDE.md for complete rules.
