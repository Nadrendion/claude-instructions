---
name: plan-a-slice
description: Use before building any feature or issue, to agree with the user on what to build.
---

# Plan a slice

Agree on what to build before building anything.

1. Read the reference material for the feature, and show what it says in a few lines.
2. List the questions it leaves open, each with a recommendation and the reason. Keep each answer in the user's hands.
3. Show the API: each call, what it does and its answers.
4. Show the specification tests as a tree. Every test has all three parts: an initial state, an action and a result (given, when, then). Nest tests by one of those parts only when several tests share it. A test that shares nothing with others isn't nested at all. Verify each rule once, with each branch of a rule as its own test.
5. Name the logic tests, and the one regression probe, if any.
6. List every existing test that would change or be deleted, file by file, and ask for approval.
7. Build nothing until the user agrees. When they change something, update the plan and record the decision.
