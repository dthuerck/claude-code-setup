# claude-code-setup

My setup and configurations for Claude Code. EVentually, this should grow into
some kind of "standard library" with the following kinds of building blocks:
- conventions (tech stacks, components and conventions how projects should be structured)
- roles (persona descriptions, mostly used in subagents)
- rules (guidelines and process descriptions to guide the models)

Leveraging these building blocks are:
- agents (subagents with a specific function, often used within commands)
- commands (explicit commands and control instructions to the model)
- workflows (description of process steps, mostly using commands)

The collection pretty much stems from my (daily) usage of Claude Code. I myself, besides
Sonnet and Opus, also use GLM-4.6 and test these blocks for all models.

## Sources

I've taken the liberty to use, include and/or adapt contents from the following projects:
- [Awesome Claude Code Subagents](https://github.com/VoltAgent/awesome-claude-code-subagents)

Kudos to their authors and thnaks for sharing with the world!