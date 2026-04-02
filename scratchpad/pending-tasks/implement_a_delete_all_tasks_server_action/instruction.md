Wasp operations connect frontend React components to backend Node.js logic using the `main.wasp` declarative DSL. By defining an action and attaching it to specific entities, Wasp automatically handles full-stack type safety and basic cache invalidation.

You need to create a server-side action that deletes all tasks belonging to the currently authenticated user in a standard Wasp application. 

**Constraints:**
- You MUST declare the `deleteAllTasks` action in the `main.wasp` file and explicitly link it to the `Task` entity.
- The TypeScript implementation must check for `context.user` and throw an `HttpError(401)` if the user is unauthenticated.
- Ensure the Prisma database call correctly filters the deletion by `userId`.