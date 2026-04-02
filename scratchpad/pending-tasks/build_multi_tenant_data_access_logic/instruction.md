Multi-tenant applications require strict separation of data based on user roles and memberships. Accessing contextual user data in Wasp operations is critical for enforcing these boundaries safely.

You need to create a `getProjects` query that fetches and returns only the projects where the currently logged-in user is a registered member. 

**Constraints:**
- Update `schema.prisma` to configure a valid relation between `User` and `Project` models (e.g., a multi-tenant membership mapping).
- The TypeScript logic for `getProjects` MUST throw an `HttpError(401)` if `context.user` is undefined.
- The Prisma query MUST strictly filter results to only include projects associated with `context.user.id`.