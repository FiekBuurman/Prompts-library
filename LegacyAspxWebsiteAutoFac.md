```
CONTEXT:
I'm a senior C# developer working on a legacy ASP.NET Web Site (not Web Application) on .NET Framework 4.8.
All underlying referenced projects have been migrated to SDK-style project files.

CURRENT SITUATION:
In the Global.cs the IocContainer is registered, but this is called a few times, so im pretty sure there are multiple instances.

public class Global : Dionysos.Web.HttpApplication  
{
    private readonly IConfigurationProvider _configurationProvider;
	private readonly IConfigurationEntityService _configurationEntityService;
    private static int _maxRequestLength;

    public Global()
    {
        IocConfig.Register(new IocContainer());
    }
  }

GOAL:
Before Migrate the legacy ASP.NET Web Site to a more modern framework/architecture we want to clean up as much code possible, so registering the interfaces should be at a obvious position.

REQUIREMENTS:


SPECIFIC QUESTIONS:
1. Is the Global constructer cuasing multiple instances?
2. What is the best place to start registering interfaces and autofac modules?

CONSTRAINTS:
- If you're uncertain about something, clearly state it and explain your reasoning
- Prioritize practical, proven solutions over experimental approaches
- Consider that this is production code with active users
```
