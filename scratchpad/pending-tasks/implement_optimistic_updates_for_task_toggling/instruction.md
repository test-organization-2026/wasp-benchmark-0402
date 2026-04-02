Wasp wraps React Query on the frontend, which handles caching and server synchronization. To make the application feel highly responsive, developers can configure optimistic updates to immediately reflect UI changes before the backend responds.

You need to implement an optimistic update on the frontend React component for a task's "completed" checkbox toggle. 

**Constraints:**
- You MUST use Wasp's `useAction` hook configurations (e.g., passing an `optimisticUpdate` configuration object).
- The local React Query cache for the task list must be manually updated within the action's configuration to reflect the toggled state instantly.
- Ensure the update rolls back automatically if the server action fails.