# Development Process

These are the preliminary development processes for developers and QAs. These processes are subject to continuous changes so it's advice to frequently review it for changes.

## Developer Development Process

1. Pick up ticket (3 amigos; optional)
2. Define branch.

   ```text
   Format:
   
   e.g.
   
   feat/SWNPDO-XXX/focus
   bug/SWNPDO-XXX/focus
   ```

3. Run tests to make sure you know everything is working before you start.
4. Implement the necessary changes
5. Implement playwright tests and fix broken tests
6. Commit changes
    1. Message format:

      ```text
      SWNPDO-XXX {message}
      
      {details}
      ```

7. Create pull request
8. Update e2e environment
9. Rerun the checks in pull request, if failed in e2e environment
10. When pull request has been approved and merged, do step 8 for the test environment
11. Move the ticket to the Jira `Test` column and inform any QA/Testers.
12. QA/Tester to perform manual tests to see if the acceptance criteria was met.
13. Once QA/Test has signed off.
14. Update `production` environment
    1. Use `Deploy - Environment` to deploy the code changes made to the `test` azure instance
    2. Use `Deploy - Environment` to deploy the code changes made to the `production` azure instance
15. Inform the team in MS Teams group chat, that the code changes have been deployed.

## QA Test Suite Development Process

1. Define or Pick up ticket in Jira Test column
    1. Subtask to fix related tests (Ideally the responsibility of the Devs).
    2. Define general test fix, load testing, etc. ticket(s).
2. Move Jira ticket the 'In Progress'.
3. Define branch. Format:
   1. task/SWNPDO-XXX/{focus} (for test fixes, modifications, etc.)
   2. test/SWNPDO-XXX/{focus} (for running complex tests, e.g. performance, load, security, etc. testing)
4. Implement the necessary changes
   1. Add test modifications
   2. Potentially, update e2e and/or test environments
5. Commit changes
   1. Message format: "SWNPDO-XXX {message}"
6. Create pull request
7. Move Jira ticket the 'Ready for Review (Tech)'.
8. Pull request approved and merged, by at least a Dev, QA or Technical Architecture
9. Mark ticket as 'Done'.site. Pass or fail. (In development)
