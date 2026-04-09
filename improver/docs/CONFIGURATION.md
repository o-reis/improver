# Configuration Files

YAML configuration specifications.

## context.yaml

Controls how context is managed:

```yaml
context:
  max_tokens: 100000        # Max context window
  compression_threshold: 0.7  # When to compress
  
  layers:
    - system_instructions   # Base role
    - long_term_memory       # Past cases
    - retrieved_documents    # Search results
    - tool_definitions       # Available tools
    - recent_conversation    # Session history
    - current_task           # Active problem
```

## safety.yaml

Constraints that cannot be overridden:

```yaml
safety:
  confirmation_required:
    - destructive_operations
    - irreversible_changes
    
  transparency:
    explain_reasoning: always
    cite_sources: always
    
  scope:
    stay_within_user_request: true
    no_unasked_recommendations: true
```

## skill.yaml

Domain skill configuration:

```yaml
skill:
  name: creative
  priority: 10
  keywords:
    - music
    - art
    - singer
    
  gathering:
    skill_specific_questions:
      - [question 1]
      - [question 2]
```

## Configuration Priority

1. System defaults in `rules/`
2. Skill-specific overrides
3. User preferences (when provided)
