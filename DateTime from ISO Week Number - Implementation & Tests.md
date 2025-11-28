# DateTime from ISO Week Number - Implementation & Tests

## Context
I'm a senior C# developer working on an ASP.NET Website using .NET Framework 4.8.
- Testing framework: NUnit
- Date handling standard: ISO 8601 week date system
- Team coding style: Prefer explicit/readable code over clever one-liners

## Current Situation
We need to calculate a specific DateTime from calendar week components. This is for [business feature: reporting/scheduling/etc.].

**Example scenario that must work correctly:**
- Input: Year 2026, Week 1, Monday
- Expected output: Monday, December 29, 2025
- Reason: ISO 8601 week 1 is the week containing the first Thursday of the year

## Goal
Create a reliable method to convert ISO 8601 week numbers to DateTime objects, with comprehensive test coverage for edge cases.

## Requirements

**Functional Requirements:**
- Accept inputs: `int year`, `int weekNumber`, `DayOfWeek dayOfWeek`
- Return: `DateTime` representing the specified day
- Follow ISO 8601 week date system:
  - Week 1 is the week containing the first Thursday of the year
  - Weeks start on Monday
  - Week 53 occurs in years where December 31 falls on Thursday (or Wednesday in leap years)
- Handle week 52/53 to week 1 transitions correctly
- Handle leap years correctly
- Validate inputs (week 1-53, valid DayOfWeek)

**Code Quality Requirements:**
- Method should be static and placed in a utility class
- Include XML documentation comments explaining the ISO 8601 behavior
- Clear variable names that explain intent
- Throw `ArgumentOutOfRangeException` for invalid inputs with descriptive messages
- No external dependencies (use only System namespace)

**Testing Requirements:**
- Use NUnit framework
- Naming format: `MethodName_InputDescription_ShouldReturnExpectedResult`
- Cover all edge cases listed below
- Use `TestCase` attribute for parameterized tests where appropriate
- Include both positive and negative test cases

## Edge Cases to Test

**Critical edge cases:**
1. Week 1 spanning previous year (e.g., 2026-W01 starts in 2025)
2. Week 53 in years that have it (e.g., 2020, 2026, 2032)
3. December 31st in different week scenarios
4. January 1st in different week scenarios
5. Leap year February 29th
6. All seven days of the week (Monday through Sunday)
7. Invalid inputs:
   - Week 0
   - Week 54
   - Week 53 in years that only have 52 weeks (e.g., 2025)

**Test data examples:**
- (2026, 1, Monday) → 2025-12-29
- (2026, 1, Sunday) → 2026-01-04
- (2020, 53, Thursday) → 2020-12-31
- (2025, 53, Monday) → Should throw (2025 has only 52 weeks)

## Constraints
- .NET Framework 4.8 compatible (no C# 8+ features like ranges or nullable reference types)
- No third-party libraries (e.g., NodaTime) - use built-in `System` namespace only
- Keep code maintainable: prefer clarity over performance micro-optimizations
- Method should complete in < 1ms for all valid inputs

## Specific Requirements
- Include a helper method to determine if a year has 53 weeks (for validation)
- Add a comment explaining why the ISO 8601 algorithm works
- Consider creating an extension method vs static utility method (recommend which is better)

## Output Format

Please provide:

1. **Class Design:**
   - Recommended class name and namespace
   - Method signature with XML documentation
   - Whether to use extension method or static utility class (with reasoning)

2. **Implementation:**
   - Complete C# code with inline comments explaining the ISO 8601 logic
   - Input validation with descriptive exception messages
   - Helper methods if needed

3. **Unit Tests:**
   - Complete NUnit test class
   - Minimum 15 test cases covering:
     - Happy path (typical weeks)
     - Edge cases (week 1, week 52/53)
     - Boundary conditions (year transitions)
     - Invalid inputs (should throw exceptions)
   - Use `[TestCase]` for parameterized tests where it improves readability

4. **Documentation:**
   - Table showing how ISO 8601 week 1 is determined
   - List of years between 2020-2030 that have 53 weeks
   - Code comments explaining the algorithm's key steps

5. **Gotchas & Edge Cases:**
   - Explanation of why 2026-W01 starts in 2025
   - How to determine if a year has 53 weeks
   - Common mistakes developers make with week numbers
   - Timezone considerations (should always use unspecified/local/UTC?)

6. **Usage Example:**
   - 2-3 practical examples showing how to call the method
   - Example of catching and handling validation exceptions

## Additional Context

**Why this matters:**
- [If applicable: "Our reports group data by ISO week and users need to filter by specific dates"]
- [If applicable: "We're migrating from a buggy implementation that uses a different week standard"]

**Success Criteria:**
- All test cases pass
- Code review approval from team (readability is critical)
- No surprises when deployed to production with edge case dates
