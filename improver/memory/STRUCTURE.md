# Memory Structure & Examples

How to create and maintain problem memory entries.

## Directory Structure

```
memory/
├── INDEX.md              # This index
└── history/
    └── {YYYY-MM-DD}_{slug}.md   # Individual problem entries
```

## Creating Memory Entries

After completing `/improve` session, create entry in `improver/memory/history/`:

### Filename Format
```
{date}_{problem-slug}.md
```
Example: `2026-04-09_rock-singer-success.md`

### Required Fields

```markdown
# Problem: [Brief Title]

Date: YYYY-MM-DD
Domain: [skill-name]
Tags: [relevant, tags]
Status: [active/resolved/ongoing]
```

### Optional Fields

```markdown
## Problem Statement
[Original user input]

## Context
[Gathered information summary]

## Research Findings
### Key Insight 1: [Title]
- Finding: [what was learned]
- Source: [where from]
- Relevance: [why it matters]
```

## Example Entry

```markdown
# Problem: Career Transition to Data Science
Date: 2026-04-09
Domain: career
Tags: career-transition, data-science, skills, job-search
Status: resolved

## Problem Statement
I want to transition from marketing to data science. What skills do I need?

## Context

**User Profile:** Marketing analyst with 3 years experience
**Goal:** Become a data scientist within 12 months
**Constraints:** Full-time job, limited budget
**Resources:** Basic Excel skills, some Python

## Research Findings

### Key Insight 1: Python is Essential
- Finding: 90% of data science job postings require Python
- Source: Indeed job analysis
- Relevance: Prioritize Python learning

## Recommendations Made

1. **Learn Python basics (Month 1)**
2. **Master pandas and scikit-learn (Month 2-3)**
3. **Build 3 portfolio projects (Month 4-6)**
4. **Network with data scientists (Ongoing)**

## Follow-up Notes
[User reported landing first data analyst role in Month 8]
```

## Indexing

After creating entry, update `improver/memory/INDEX.md`:
1. Add to Recent Problems table
2. Add relevant tags
3. Note status
