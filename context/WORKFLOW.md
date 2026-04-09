# Improver Workflow Specification

**Version:** 0.1.0

---

## Command Invocation

```
/improve <problem statement>
```

## Phase Execution

### Phase 1: Information Gathering

**Read:**
- `prompts/01_gather.md`
- `skills/{domain}/gather.md`

**Execute:**
1. Detect domain from problem keywords
2. Ask universal questions first
3. Switch to domain-specific questions
4. Follow up on responses
5. Stop when all categories covered

**Categories:**
- Identity & Background
- Goal Clarification
- Constraints & Resources
- Context Factors

**Output:** Complete context summary

---

### Phase 2: Research & Synthesis

**Read:**
- `prompts/02_research.md`
- `skills/{domain}/research.md`

**Execute:**
1. Generate 3-5 search queries
2. Execute web searches
3. Evaluate source quality
4. Extract key findings
5. Synthesize insights
6. Iterate if new topics found

**Output:** Structured research findings

---

### Phase 3: Recommendations

**Read:**
- `prompts/03_recommend.md`
- `patterns/{domain}.md`
- `patterns/base.md`
- `memory/history/` for similar cases

**Execute:**
1. Check applicable patterns
2. Search for similar past problems
3. Generate recommendations by timeframe
4. Prioritize by impact/effort
5. Assess risks

**Output:**
- Immediate Actions (This Week)
- Short-term Goals (1-3 Months)
- Long-term Strategy (3-12 Months)

---

### Phase 4: Storage

**Execute:**
1. Create `memory/history/{date}_{id}.md`
2. Update `memory/INDEX.md`
3. Extract new patterns if applicable
4. Update `patterns/{domain}.md`

---

## Question Protocol

```
Universal → Domain-Specific → Follow-up → Close → Summary
```

## Research Protocol

```
Query Generation → Search → Evaluate → Extract → Synthesize
```

## Recommendation Protocol

```
Pattern Check → Memory Search → Generate → Prioritize → Present
```
