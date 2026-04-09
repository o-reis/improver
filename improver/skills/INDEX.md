# Skills Index

Domain-specific knowledge and behavior guides.

## Structure

Each skill folder contains:
- `skill.yaml` - Skill definition and configuration
- `gather.md` - Domain-specific gathering questions
- `research.md` - Domain-specific research focus
- `patterns.md` - Domain-specific patterns

## Available Skills

| Skill | Domain | Status |
|-------|--------|--------|
| base/ | General purpose | Core |
| career/ | Professional development | Ready |
| creative/ | Arts, music, writing | Ready |
| business/ | Entrepreneurship | Ready |
| tech/ | Software development | Ready |
| health/ | Fitness and wellness | Ready |
| education/ | Learning and academia | Ready |

## Skill Activation

When `/improve` is invoked, identify the primary domain:
1. Match keywords to skill domains
2. Load skill-specific prompts
3. Apply domain patterns
4. Generate tailored recommendations

## Skill Priority

Base skill has priority 0 (fallback). All other skills have priority 10.

When multiple skills match, the most specific match wins.

## Creating New Skills

1. Create folder: `skills/{domain}/`
2. Add `skill.yaml` with metadata
3. Add domain-specific prompt files
4. Add patterns to `patterns/{domain}.md`
5. Update this index
