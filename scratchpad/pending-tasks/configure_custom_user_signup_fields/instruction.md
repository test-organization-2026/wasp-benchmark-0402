While Wasp provides pre-built `LoginForm` and `SignupForm` components for authentication, adding custom fields to the user registration process requires specific configuration in both the DSL and the database schema. This is a common point of friction for developers.

You need to add a required "Company Name" field to the default email authentication signup process. 

**Constraints:**
- Update `main.wasp` to define `userSignupFields` under the authentication configuration block.
- Update `schema.prisma` to include `companyName` as a string field on the `User` model.
- You MUST NOT build a completely custom React form from scratch; use the built-in Wasp UI components configured to accept the new field.