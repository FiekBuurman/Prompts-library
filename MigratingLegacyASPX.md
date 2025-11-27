## Prompt

```
CONTEXT:
I'm a senior C# developer working on a legacy ASP.NET Web Site (not Web Application) on .NET Framework 4.8.
All underlying referenced projects have been migrated to SDK-style project files.

CURRENT SITUATION:
When building the website, I'm getting "Could not get dependencies for project reference" errors for all SDK-style project references.

GOAL:
Migrate the legacy ASP.NET Web Site to a more modern framework/architecture.

REQUIREMENTS:
- Recommend a target framework that is:
  * Future-proof with long-term support
  * Minimizes breaking changes from .NET Framework 4.8
  * Has a clear migration path
- Provide a step-by-step migration plan with:
  * Risk assessment for each step
  * Estimated effort level (low/medium/high)
  * Order of operations (what to do first)
- Evaluate whether an intermediate solution (like a bridge/facade project) would be beneficial as a stepping stone

SPECIFIC QUESTIONS:
1. Should I migrate to .NET 6/8/9, or stay on .NET Framework 4.8 but convert to Web Application project?
2. What are the major breaking changes I should anticipate?
3. Can I migrate incrementally, or does it need to be all-at-once?
4. How should I handle ASP.NET-specific features (Web Forms, HttpContext, etc.)?

CONSTRAINTS:
- If you're uncertain about something, clearly state it and explain your reasoning
- Prioritize practical, proven solutions over experimental approaches
- Consider that this is production code with active users

OUTPUT FORMAT:
1. Recommended migration path (with rationale)
2. Step-by-step plan
3. Assessment of intermediate solutions
4. Potential gotchas and how to handle them
5. Resources/documentation I should reference

```
