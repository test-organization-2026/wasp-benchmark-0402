Wasp automatically invalidates caches based on the `entities` array defined in `main.wasp`. However, for complex scenarios like partial updates or non-entity data fetching, developers must bypass this and manually manage the React Query cache keys abstracted by Wasp.

You need to manually invalidate the frontend cache for a specific custom query after a non-standard backend operation is executed from a React component. 

**Constraints:**
- You MUST locate and use Wasp's abstracted internal query key using `query.queryCacheKey`.
- You MUST manually trigger the invalidation using standard `react-query` methods (e.g., `queryClient.invalidateQueries`).
- Do NOT rely on Wasp's automatic `entities` array invalidation feature in the `main.wasp` DSL for this specific task.