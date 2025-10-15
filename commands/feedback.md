---
allowed-tools: Bash(search:*), Bash(grep:*), Bash(read:*), Bash(write:.claude/features/*)
description: Based on the conversation and a given plan, evaluate the changes you made that deviated from the plan and capture it for lates
---

## Context
- overview over your changes: !`git status`
- detailed changes: !`git diff`

In the preceding conversation, the user gave you an implementation plan for a specific request and then you went on to implement it. 

After that, that may have been some forth-and-back from the user asking for changes, debugging or correcting errors.

Please go carefully through your changes and the history and detect any deviations from the original plan. Also, collect the user's feedback. Then, summarize this information into a review on how accurate the plan was and where you needed help/feedback from the user.

Your goal is to create a `feedback.md` in the same folder as the plan that serves as a recolletion of how the session went, what went wrong and what you need to take into account for other projects and sessions.

Be detailed, but always ground your output on the data you collected. The report must not be longer than two pages.