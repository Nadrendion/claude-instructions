# Working instructions

## Decisions

- When the work reaches something we haven't agreed on, ask instead of assuming.
- Ask at a detailed level, with a recommendation.
- Ask when the decision comes up, not everything up front.
- Record each decision when it's made. Decisions that apply to any project go in this file. Project-specific decisions go in that project's own files.

## Git

- Each issue gets its own branch and pull or merge request.
- Commit messages and pull or merge request titles follow Conventional Commits.
- Use a scope in commit messages and pull or merge request titles, such as `feat(login): add logout button`.
- Write the description so it completes the sentence "applying this PR will ...".
- Commit messages have a title only, with no body.
- Squash merge into the main branch. The request title becomes the commit title, and the body lists the branch commit messages.
- Claude's co-author line goes once at the end of the squash commit, never on branch commits.
- Don't merge a pull or merge request with failing checks.

## Infrastructure

- Define infrastructure as code in the repository, with no manual setup steps.

## Tests

- Tests exist to build trust, not to reach a number or a coverage figure.
- Don't sort tests into unit, integration or end-to-end. Use three layers: specification tests, logic tests and regression probes.
- Each application is its own system under test.

### Specification tests

- They declare, as facts, which rules the application implements.
- They test the application as a black box through its API, mocking only external services.
- Names use business language, with no filler words or technical details.
- Nest names to avoid repetition, by initial state, operation or outcome: "A logged in customer > can place > an order".
- Each rule is verified once, and each branch of a rule counts as its own rule.
- When a rule depends on a definition, use one obvious example here and verify the definition in logic tests.
- Write a negative test only when a rule forbids something.

### Logic tests

- They verify definitions and fine-grained logic extensively, including edge cases.
- They call public methods directly, without frameworks or databases.
- Your own code may be mocked when it isn't needed for what's being verified.

### Regression probes

- Use them on a few key responses only.
- They are simple, coarse checks that a response keeps its shape, using a hash or snapshot.
- Mask values that change between runs, such as IDs and timestamps.
- They only say that something changed. Specification tests say what stopped working, and logic tests say why.

### Working with tests

- Write specification tests before the code, logic tests as the logic takes shape, and regression probes last.
- Run specification and logic tests before regression probes.
- A bug means a specification or logic test is missing. Add the test first, then fix the bug so it passes.
- Never change an existing test, hash or snapshot without review and approval.

## This file

- Keep it free of project names, specific technologies and employers.
- It is public, so keep personal and confidential information out of it.
