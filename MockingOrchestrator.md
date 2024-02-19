# Mocking Orchestrator

**Goal:** practice TDD against mock objects.

In this kata you will create a class which acts as an _orchestrator:_
it directs the flow of work without actually performing any of the individual pieces of work.

Rules for this kata:
* You can create as many interfaces as you want,
  but the only (non-test) class you may have is the orchestrator.
* The orchestrator can call dependency-injected interfaces,
  but must not implement any other behaviors such as caching, API calling, database, etc.

This orchestrator will take in a `Guid` id and use it to interact with an API.

## Iterations

Practice this exercise one iteration at a time, making sure to fully complete each one before moving to the next.

1. Call the API to get some data then return that data
2. If calling the API throws an exception, return a failure result (don't throw)
3. Store the API result in a repository based on the id before returning the data
4. If the data for the given id already exists in the repository, return it instead of calling the API
5. If the data for the given id exists in the repository, but is more than 5 min old, call the API and store the newest data
6. If there is data for the given id in the repository, but calling the API fails, then return the stale data along with an indication that it is stale
7. Call a parser which takes the data string (if available) and returns an object with a `WasSuccessful` boolean and a `Value` integer; include this in the Orchestrator's return result
8. Add a logger which you call every time there is a failure, or if the parser returns `false` for `WasSuccessful`
9. Add a command interface which takes the `Guid` id and an `int` value; 
   call this command if the parser returns a `Value` greater than 0