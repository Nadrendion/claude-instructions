---
name: plan-a-slice
description: Use first in a new session, when the startup prompt asks to plan a feature or issue, to agree with the user on what to build before anything is built.
---

# Plan a slice

Agree on what to build before building anything.

1. Read the reference material for the feature, and show what it says in a few lines.
2. If the slice changes a screen that other issues will change too, and that screen has no agreed design as a whole, design the whole screen first, with every part that's coming, and agree on it before planning the slice.
3. In one message, list every question the reference material leaves open, each with a recommendation and the reason, and show a sketch of each screen the slice adds or changes, at a phone's width with realistic data, drawn with the recommendations. The user answers only where they disagree.
4. Show the API: each call, what it does and its answers.
5. Show the specification tests as a tree. Every test has all three parts: an initial state, an action and a result (given, when, then). Nest tests by one of those parts only when several tests share it. A test that shares nothing with others isn't nested at all. Verify each rule once, with each branch of a rule as its own test.
6. Name the logic tests, and the one regression probe, if any.
7. List every existing test that would change or be deleted, file by file, and ask for approval.
8. Build nothing until the user agrees. When they change something, update the plan and record the decision.
