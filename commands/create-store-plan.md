---
allowed-tools: Bash(git status:*), Bash(git commit:*), Bash(mkdir:.claude/features/*)
description: Create a plan how to process a user's change request
---

## Context

- Current git status: !`git status`
- Last committed changes and commit messages: !`git log -n 20`

## Your Task
Above, the user has given you a request. For now, your task is to create a detailed plan 
on how to execute and, if needed, implement the user's request. 

Execute the following steps:
- Read through the user's request thoroughly. If the request is not clear enough or if you have
any further questions, please ask the user and confirm his choices.
- Collect all information for the request by 
  - reading any files that the user references,
  - reading the specs of the project (in `specs/, if available`) first and validate the request against those (i.e. also note necessary changes to the specs)
  - follow function calls, includes, references, imports to find other possibly important files,
  - reading documentation and tests,
  - reading earlier plans (`sessions` with earlier dates)
- Digest this information and based on it, review the current state of the code w.r.t the user's request
- If the user requests a change, then
  - consider how this change fits the current architecture,
  - collect the files, classes etc that need to be changed,
  - write up an overview (including changes - as a short statement, not necessarily the full code already - per file) of the proposed change and implementation
- lastly, use the subagents to check the plan thoroughly: Did you overcomplicate the change? Does it
fit the project well? Is there a simple implementation? Have the user confirm any changes to the plan stemming from the criticism.

Finally, formulate your plan as an markdown file and present it to the user. Then, if the user greenlights it, store it as indicated.

While you work, keep a regularly-updated Todo-List and present it to the user so he can follow your steps.

## Hints
- use subagents to gather information on the projects without overly filling the context windows; especially use
  - the `investigator` to answer singular, specific questions about the codebase and collect more relevant files (note that general requests like "understand X" are not useful, rather formulate specific, pointed questions such as "what is the process to extract X from input JSONs?")
  - the `search-specialist` to inquire about concrete techniques, frameworks and standards from the web
- the `architect-reviewer` to get a review on architectural proposals concerning high-level information on the context, specifically on parts of your plan
- read older plans which might have dealt with similar issues (folders under `./sessions`)

## Structure of a good plan

A good plan contains the following information in a well-structured fashion:
- re-state the user's request in your own words, including results of the exchange between you and the user
- give enough context for the reader to understand the current state of the codebase w.r.t the user's request
- if possible, list a few critical code snippets that show the status quo
- present the planned changes in two layers:
  - first, give the _architectural_ overview in plain language: what is your approach and how does it fit into the project's architecture?
  - second, detail the changes on a file level, for each file just stating in a few bullet points what are the changes - do not spill the full code here, that's left to the implementation team
- propose unit tests to validate your changes,
- lastly, add a short step-by-step plan showing the order of which the concrete changes should be executed - make sure this includes regularly testing and correctness verification, but keep this on a purely abstract level, without time estimates!

This is not the place to mix in general, project manager-level advice like "add testing regime and update docs", but keep your scope to the concrete request at hand (only implementation phase).

In general, in each section, the plan should follow a top-down principle where
you first set the context for the reader, then present the modification and lastly explain
the motication and the intent of the change.

## Storing the plan
For this plan, please create a new folder named 
```
{today's date in yyyy-mm-dd format}-$1
```
inside this project's `project/sessions/` and store the plan file as `plan.md`
in this folder.

Remember: YOU ARE NOT SUPPOSED TO EDIT ANY CODE YET. Your last action should be storing
this plan.