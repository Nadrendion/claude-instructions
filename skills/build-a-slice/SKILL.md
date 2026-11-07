---
name: build-a-slice
description: Use when building a plan the user has agreed to.
---

# Build a slice

1. Create the issue's branch. The first commit records the decisions.
2. Change the API definition before the code.
3. Write the specification tests, and see them fail for the right reason. Use a stub if the code won't compile without one.
4. Write the code until they pass, with logic tests as the logic takes shape.
5. Add the regression probe last.
6. Run every test, lint, format and build, and the smoke test.
7. Check it in the browser at a phone's width, from every role involved.
8. Report what was checked, what failed first, and what wasn't seen failing. Commit nothing yet.
9. When the user is happy, show the commits and the pull request text, and wait for a yes.

A bug found along the way gets a failing test before its fix.
