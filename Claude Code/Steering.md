## An Agent MD file
You can think of `AGENTS.md` as a readme for agents, a dedicated predictable place to provide the context and instructions to help AI coding agents work on your project.

Don't make it too big.

- AGENTS.md used by: Gemini CLI, Devin, Codex, Cursor.
- CLAUDE.md used by: Claude

Claude might ignore the CLAUDE.md file if it thinks it is not relevant. 

In an agent.md (claude.md) file, it is better to write things that are sticky, that will evolve easily like: coding preferences, where and how to write tests... 

Don't rewrite your scripts or packages, it gets out of date pretty quickly. 

### Progressive Discloser with Agent Skills
Agent skills are folders of instructions, scripts, and resources that agents can discover. They are not forced to read them. 

Agent skills can be scoped to the user (computer) or to the project. (Like agents.md)

If you don't want the agent to read a skill, you can type, in the frontmatter:
```markdown
name: some-name
description: some-description
disable-model-invocation: true 
```

If you don't want the user to invoke a skill, you can type, in the frontmatter:
```markdown
name: some-name
description: some-description
user-invocable: false
```