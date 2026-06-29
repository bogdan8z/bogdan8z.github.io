# Copilot useful stuff

## Description

This project contains a collection of reusable Copilot agents and instructions designed to enhance productivity and code quality. It includes specialized agents for code review, performance analysis, and security assessment, along with comprehensive Copilot configuration guidelines. All the agents files you need to copy to your project in .github/agents folder. All the instruction files you need to copy in **.github** folder of your project.

##### This page structure
- `agents/`
  - [code-reviewer.agent.md](agents/code-reviewer.agent.md) — Agent for automated code review and quality checks
  - [performance-analyst.agent.md](agents/performance-analyst.agent.md) — Agent for performance profiling and optimization
  - [security-specialist.agent.md](agents/security-specialist.agent.md) — Agent for security vulnerability detection
- `instructions/`
  - [create-instructions.md](instructions/create-instructions.md) — Copilot configuration and usage guidelines
- `README.md` — Project overview and documentation (this file)
---

## Example of prompt for code reviewer agent, for the changes inside a branch:

> my changes are pushed to branch1 branch, created from branch2 branch, review them. don't review any local changes.

## Links

- [Agent Skills](https://agentskills.io)
- [Awesome Copilot Skills](https://awesome-copilot.github.com/skills/)
- [Anthropic Skills](https://github.com/anthropics/skills/tree/main/skills/skill-creator)
