# [Prompt Name]

## Purpose
Brief description of what this prompt accomplishes and when to use it.

## Context Required
List the information you need to provide for this prompt to work effectively:
- [ ] Tech stack details (C# version, .NET framework, libraries)
- [ ] Architecture pattern (clean architecture, DDD, etc.)
- [ ] Project constraints (performance, scalability, team conventions)
- [ ] Domain knowledge (business rules, specific requirements)

## Prompt Template

```
{{CONTEXT}}
I'm a {{YOUR_ROLE}} working on {{PROJECT_TYPE}} using {{TECH_STACK}}.

{{CURRENT_SITUATION}}
Currently, we have {{EXISTING_IMPLEMENTATION}}.

{{GOAL}}
I need to {{OBJECTIVE}}.

{{REQUIREMENTS}}
Requirements:
- {{REQUIREMENT_1}}
- {{REQUIREMENT_2}}
- {{REQUIREMENT_3}}

{{CONSTRAINTS}}
Constraints:
- {{CONSTRAINT_1}}
- {{CONSTRAINT_2}}

{{OUTPUT_FORMAT}}
Please provide {{DESIRED_OUTPUT}}.
```

## Variables Reference

| Variable | Description | Example |
|----------|-------------|---------|
| `{{YOUR_ROLE}}` | Your role/expertise level | "senior C# developer", "architect" |
| `{{PROJECT_TYPE}}` | Type of project | "REST API", "microservice", "web application" |
| `{{TECH_STACK}}` | Technologies used | ".NET 8, Entity Framework Core, PostgreSQL" |
| `{{OBJECTIVE}}` | What you want to achieve | "implement a caching strategy", "refactor for testability" |
| `{{DESIRED_OUTPUT}}` | Expected format | "code with unit tests", "architectural diagram", "comparison table" |

## Example Usage

See [example-usage.md](./example-usage.md) for a complete example.

## Variations

### Variation 1: [Name]
Modify for: [specific use case]
- Change: [what to change]
- Add: [what to add]

### Variation 2: [Name]
Modify for: [specific use case]
- Change: [what to change]
- Remove: [what to remove]

## Tips for Best Results

- **Tip 1**: Be specific about coding standards and conventions
- **Tip 2**: Include examples of existing code style when relevant
- **Tip 3**: Ask for explanations of design decisions to learn patterns
- **Tip 4**: Iterate - refine the output with follow-up questions

## Related Prompts

- [Link to related prompt 1]
- [Link to related prompt 2]

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | YYYY-MM-DD | Initial version |

## Tags

`#csharp` `#category` `#use-case`
