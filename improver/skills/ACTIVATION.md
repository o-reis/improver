# Skill Activation Protocol

How to identify and load the correct skill for a problem.

## Activation Process

### Step 1: Keyword Matching

When `/improve` is invoked with a problem statement:

1. Extract keywords from user input
2. Compare against skill keywords in `skills/*/skill.yaml`
3. Score each skill by match count
4. Select highest-scoring skill

### Step 2: Priority Resolution

If multiple skills score equally:
- Base skill (priority: 0) is fallback only
- Other skills have priority: 10
- Select non-base skill with highest priority

### Step 3: Skill Loading

Once skill is identified, load:
1. `improver/skills/{domain}/skill.yaml` - Configuration
2. `improver/skills/{domain}/gather.md` - Questions
3. `improver/skills/{domain}/research.md` - Research focus
4. `improver/skills/{domain}/patterns.md` - Domain patterns

### Step 4: Universal Augmentation

Always load base skill alongside domain skill:
- `improver/skills/base/gather.md` - Universal questions
- `improver/skills/base/research.md` - Research framework
- `improver/skills/base/patterns.md` - Universal patterns

## Keyword Examples

| User Input | Detected Domain | Reason |
|------------|----------------|--------|
| "I am a rock singer but not achieving success" | creative | "singer" matches creative keywords |
| "I want to switch careers to software engineering" | career | "career" matches career keywords |
| "I have a startup idea for an AI app" | business | "startup" matches business keywords |
| "How do I build a React application?" | tech | "React" implies tech domain |
| "I want to lose weight and build muscle" | health | "lose weight" + "muscle" match health |
| "I need to learn calculus for my exam" | education | "learn" + "exam" match education |
| "I'm struggling with life decisions" | base | No specific keywords → base |

## Edge Cases

### No Keywords Match
→ Use base skill only

### Multiple Domains
→ Use highest-scoring domain, can mention secondary domain

### Unclear Intent
→ Ask clarifying question, then re-evaluate

## Skill Files to Load

```
Always load:
- improver/prompts/system.md
- improver/prompts/01_gather.md OR 02_research.md OR 03_recommend.md (current phase)
- improver/skills/base/gather.md OR research.md OR patterns.md (current phase)

If domain detected:
- improver/skills/{domain}/skill.yaml
- improver/skills/{domain}/gather.md OR research.md OR patterns.md (current phase)
- improver/patterns/{domain}.md
```

## Domain Keywords Reference

```
base: general, help, advice, improve, goal, problem

career: job, career, promotion, interview, resume, salary, transition, professional, work, workplace, boss, colleague, office, remote, employment

creative: music, art, singer, artist, musician, writer, creative, band, album, song, portfolio, creative career, artistic

business: startup, business, entrepreneur, company, launch, product, customers, revenue, funding, growth, scaling, strategy

tech: programming, code, developer, engineer, technical, algorithm, database, api, cloud, devops, security, software

health: health, fitness, exercise, workout, diet, nutrition, mental, stress, sleep, wellness, weight, muscle, running, gym, meditation

education: learning, study, course, degree, school, university, certification, knowledge, teach, student
```
