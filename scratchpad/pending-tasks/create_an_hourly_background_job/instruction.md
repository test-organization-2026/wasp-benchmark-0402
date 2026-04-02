Wasp supports scheduled background jobs directly through its DSL, allowing developers to execute recurring backend logic without setting up external chron scheduling tools. 

You need to set up a recurring background job that runs every hour to count the total number of completed tasks in the database and logs the summary to the console. 

**Constraints:**
- The job MUST be declared in `main.wasp` using a standard cron expression schedule for an hourly interval.
- The TypeScript implementation for the job must run asynchronously and query the database via Wasp's provided context.
- Do NOT expose this background job as an HTTP endpoint.