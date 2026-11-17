# Working instructions

## Decisions

- When the work reaches something we haven't agreed on, ask instead of assuming.
- Ask at a detailed level, with a recommendation.
- When planning, ask every open question in one message, each with a recommendation. The user answers only where they disagree.
- Ask a question that comes up later, such as while building, when it comes up.
- Record each decision when it's made. Decisions that apply to any project go in this file. Project-specific decisions go in that project's own files.

## Screens

- Design a screen that several issues will change once, as a whole, with every part that's coming, before building the first of them. Each issue then fills in its part of that design.
- Show a sketch of every screen a plan adds or changes, at a phone's width with realistic data, before writing any tests.

## Git

- Each issue gets its own branch and pull or merge request.
- Commit messages and pull or merge request titles follow Conventional Commits.
- Use a scope in commit messages and pull or merge request titles, such as `feat(login): add logout button`.
- Write the description so it completes the sentence "applying this PR will ...".
- A commit message has a body: a short list, in plain words, of what the commit changes. Why it changed goes in the project's decisions and the pull or merge request.
- Squash merge into the main branch. The request title becomes the commit title, and the body lists each branch commit's title with its body under it.
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
- Names describe the rule, not the test data. Names of people, animals or things in the test stay in its body.
- Every test has an initial state, an operation and an outcome (given, when, then).
- Nest names by whichever part several tests share, to avoid repetition. The shared part comes first, whichever it is:
  - By initial state: "A logged in customer > can place > an order".
  - By operation: "Cancelling an order > before it ships > refunds the customer" and "Cancelling an order > after it ships > starts a return".
  - By outcome: "An error log is written > when a customer cannot place > an order" and "An error log is written > when a customer cannot place > an item in the shopping cart".
- A test that shares nothing with other tests isn't nested.
- The subject of a name is what the rule is about, which isn't always a person: "A discount code > can be turned off and on" reads better than "A shop owner > can manage > a discount code".
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
