---
description: Bootstrap a claude project by importing several files from my stdlib.
model: sonnet
---

Analyze this project's CLAUDE.md (if there is none, create one) whether
relevant content from the user's standard lib is included. You are responsible
for compelting the list of imports according to this list:
- in any project
    - `@~/.claude/stdlib/rules/character.md`
- in any code project:
    - `@~/.claude/stdlib/conventions/agent_files.md`
    - `@~/.claude/stdlib/rules/general.md`
    - `@~/.claude/stdlib/rules/process.md`
- in any code project containing Python code: `@~/.claude/stdlib/conventions/python.md` 
- in projects that have unit tests: @~/.claude/stdlib/rules/tdd.md

If the project matches a description, add its import to the CLAUDE.md. Do not
remove any of the imports, but avoid double imports.