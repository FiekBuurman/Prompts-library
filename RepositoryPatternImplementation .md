# Repository Pattern Implementation - Example

## Purpose
Generate a complete repository implementation following clean architecture principles with proper error handling, async operations, and unit tests.

## Context Required
- [x] Tech stack details (.NET 8, Entity Framework Core 8, SQL Server)
- [x] Architecture pattern (Clean Architecture with CQRS)
- [x] Project constraints (must be testable, follow team conventions)
- [x] Domain knowledge (working with Product entity)

## Filled Prompt

```
CONTEXT:
I'm a senior C# developer working on an e-commerce REST API using .NET 8, Entity Framework Core 8, and SQL Server.

CURRENT SITUATION:
Currently, we have a basic DbContext setup with Product entity. We're following Clean Architecture principles with separate layers for Domain, Application, Infrastructure, and API.

GOAL:
I need to implement a generic repository pattern for the Product entity that supports async operations.

REQUIREMENTS:
- Generic repository interface with common CRUD operations
- Concrete implementation using Entity Framework Core
- Support for specification pattern for complex queries
- Proper error handling with custom exceptions
- Async/await throughout
- Unit of Work pattern integration
- Follow SOLID principles

CONSTRAINTS:
- Must use Entity Framework Core 8 features
- All database operations must be async
- Include XML documentation comments
- Follow our team naming conventions (interfaces start with 'I', private fields use '_' prefix)
- Repository should NOT expose IQueryable to prevent leaky abstractions

OUTPUT FORMAT:
Please provide:
1. Generic repository interface (IRepository<T>)
2. Concrete EF Core implementation (EfRepository<T>)
3. Product-specific repository interface if needed (IProductRepository)
4. Example specification class for filtering
5. Unit tests using xUnit and Moq showing how to test the repository
6. Brief explanation of design decisions
```

## Actual AI Response Summary

The AI would provide:

### 1. IRepository<T> Interface
```csharp
/// <summary>
/// Generic repository interface for common data operations
/// </summary>
/// <typeparam name="T">Entity type</typeparam>
public interface IRepository<T> where T : class
{
    Task<T?> GetByIdAsync(int id, CancellationToken cancellationToken = default);
    Task<IEnumerable<T>> GetAllAsync(CancellationToken cancellationToken = default);
    // ... additional methods
}
```

### 2. Implementation + Tests
Complete implementation with EF Core, specifications, and comprehensive unit tests.

### 3. Design Explanation
- Why generic repository reduces code duplication
- How specification pattern prevents leaky abstractions
- Trade-offs between flexibility and complexity

## Follow-up Refinements

After receiving the initial response, I refined with these prompts:

**Follow-up 1**: "Add pagination support to the GetAllAsync method using a PaginationParams class"

**Follow-up 2**: "Include an example of how to use this repository in an MediatR command handler"

**Follow-up 3**: "Add soft delete support with a IsDeleted flag in the base entity"

## Results

This prompt successfully generated:
- ✅ Production-ready repository code
- ✅ Comprehensive unit tests (95% coverage)
- ✅ Clear documentation
- ✅ Followed team conventions
- ✅ Included design rationale

## Lessons Learned

1. **Specificity matters**: Mentioning ".NET 8" got EF Core 8 features automatically
2. **Constraints shape output**: Specifying "no IQueryable" prevented common anti-patterns
3. **Examples accelerate**: Asking for tests provided learning material
4. **Iteration is key**: Follow-ups added pagination and soft delete cleanly

## Variations Used

### For Integration Tests
Changed OUTPUT FORMAT to:
```
Please provide integration tests using WebApplicationFactory and test containers for SQL Server
```

### For Dapper Version
Changed TECH_STACK to:
```
.NET 8, Dapper, SQL Server (no Entity Framework)
```

## Related Prompts

- [Unit of Work Pattern Implementation](./unit-of-work-pattern.md)
- [CQRS Command Handler](./cqrs-command-handler.md)
- [Entity Configuration](./entity-configuration.md)

## Tags

`#csharp` `#repository-pattern` `#entity-framework` `#clean-architecture` `#example`
