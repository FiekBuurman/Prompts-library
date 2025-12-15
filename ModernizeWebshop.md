## Prompt

```
CONTEXT:
I'm a senior C# developer working on a legacy ASP.NET Web Site (not Web Application) on .NET Framework 4.8.

CURRENT SITUATION:
All underlying referenced projects have been migrated to SDK-style project files.
All classes in App_Code are moved to other underlying projects.
The legay website project is now a Web Application, and all pages and controls do have designer files.

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
1.What would be the next steps? 

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
