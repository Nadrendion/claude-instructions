---
name: end-a-session
description: Use when the user wants to end a session or move to a new one.
---

# End a session

1. **Check that nothing is half-done:** uncommitted changes, unmerged branches, open pull requests. If there are any, say so first and ask what to do before ending. Otherwise, say so in one line after the recommendation.
2. **Update the progress notes** with where things stand.
3. **Lead with the recommended next step,** under a heading of its own at the top of the message, with one line on why.
4. **List the other steps below it,** two to four, from the milestones, open issues and notes, each with one line on why.
5. **Ask with the recommendation named,** such as "Start with planning the next issue?", with the recommendation as the first answer and "Pick another" as the second.
6. **When the user picks one, write a startup prompt** for the new session, in a `text` code block, so the user can copy it with the copy button. It names the issue with a link, what's already decided, what's still open, where to look, and which skill to start with. Keep it short, and don't repeat what the notes and docs already hold.
7. **Mention anything running** that stops with the session, such as dev servers.
