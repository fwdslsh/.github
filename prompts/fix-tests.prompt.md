---
mode: agent
---

# Fix Tests Command

Run the project's test suite, analyze failures, and systematically resolve all issues with expert review and validation.

## Task Steps

1. **Run Tests & Document Failures**
   - Execute the test runner to identify all failing tests
   - Create `tests/failing.md` with comprehensive failure documentation
   - Include error messages, stack traces, and test context

2. **Expert Test Review**
    - Test validity and current relevance
    - Correctness of test assertions
    - Test design and implementation quality
    - Recommendations for fixes or removal
    - Document recommendations in `tests/failing.md`

3. **Investigation & Root Cause Analysis**
   - For each failing test, determine:
     - Is the test assertion still valid with current implementation?
     - Has the related code changed recently (check git history)?
     - Is the tested functionality deprecated/removed?
     - Is this a legitimate bug or regression?
   - Prioritize tests based on expert recommendations and impact analysis

4. **Prioritization & Planning**
   - Organize tests by priority considering:
     - Recommendations
     - Interdependencies between tests
     - Potential cascade fixes
   - Create numbered priority list in `tests/failing.md`

5. **Systematic Resolution**
   - Work through priority list systematically
   - For each test:
     - Apply recommended fixes
     - Update or remove tests as appropriate
     - Mark as completed in documentation
     - Verify fix doesn't break other tests

6. **Final Validation**
   - Run complete test suite after all fixes
   - Document any new failures in `tests/failing.md`
   - Ensure all changes maintain code quality and test coverage

## Expert Review Focus Areas

- Test assertion accuracy and relevance
- Implementation vs. specification alignment  
- Test maintainability and clarity
- Coverage gaps or redundancies
- Performance and reliability concerns
- Best practices adherence
