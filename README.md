# Agent Store — AI Agent Prompts

A lightweight repository for storing, sharing, and evolving reusable system prompts for AI agents used in engineering, planning, and testing workflows.

Use these prompts as the “system” or “instruction” message for your chat-based LLM or tooling. Each prompt is self-contained, opinionated, and optimized for clarity, determinism, and repeatable outputs.

---

## Table of contents

- Repository contents
- Quick start
- Agent catalog
- How to choose an agent
- Naming conventions
- Authoring guidelines
- Contribution checklist
- Optional metadata (front matter)
- License suggestions
- FAQ
- Changelog
 - Cross-agent guardrails & quality gates
 - New agent template

---

## Repository contents

This repo currently includes the following agent prompts:

- `universal-strategy-planning-agent.md`
	- Lead Software Engineer – Planning & Strategy Agent. Transforms requirements/RFCs into a clear technical plan with risks, testing strategy, and ticket breakdowns.
- `universal-ai-engineer-agent.md`
	- Senior AI Engineer Agent. Switches between reasoning and execution with a strict phased output structure.
- `senior-golang-ai-engineer-agent.md`
	- “GoSenior” — Senior Golang AI Engineer Agent. Enforces idiomatic Go, security, testing, CI practices, and a rigorous delivery format.
- `golang-test-expert-ai-engineer-agent.md`
	- “GoTestExpert” — Golang Testing Engineer Agent. Focuses on deterministic, idiomatic tests and ≥ 90% package coverage with enforcement guidance.

---

## Quick start

Use with chat-based tools (ChatGPT, Claude, Copilot Chat, etc.):

1) Open an agent file above.
2) Copy the entire prompt.
3) Paste it as the system/instruction message in your chat, then provide your task as the user message.

Programmatic/API usage:
- Provide the file contents as the system message when creating a chat/session.
- Keep your specific task and any repo context in the user message and subsequent turns.

Tips for best results:
- Be specific and include acceptance criteria.
- If the prompt defines an “Output Structure,” ask the model to follow it exactly.
- Share minimal repo context/constraints up front to reduce iteration.

---

## Agent catalog

| File | Role | Primary focus |
|---|---|---|
| `universal-strategy-planning-agent.md` | Lead Software Engineer – Planning & Strategy | Planning, technical design, risks, testing strategy, ticket breakdown |
| `universal-ai-engineer-agent.md` | Senior AI Engineer | Reasoning → plan → implementation workflow, anti-hallucination guardrails |
| `senior-golang-ai-engineer-agent.md` | “GoSenior” – Senior Golang Engineer | Idiomatic Go, secure/maintainable code, tests, ops, CI, delivery format |
| `golang-test-expert-ai-engineer-agent.md` | “GoTestExpert” – Golang Testing Engineer | Deterministic tests, ≥90% coverage, patterns, coverage enforcement |

---

## How to choose an agent

- Planning a new feature or RFC with unknowns → use `universal-strategy-planning-agent.md`.
- Need both reasoning and hands-on coding across stacks → use `universal-ai-engineer-agent.md`.
- Building or reviewing Go services/libraries with strong delivery expectations → use `senior-golang-ai-engineer-agent.md`.
- Raising test quality for Go repos and enforcing coverage ≥90% → use `golang-test-expert-ai-engineer-agent.md`.

---

## Naming conventions

Use descriptive, kebab-case file names:

- `<domain-or-scope>-<role>-agent.md`
- Examples:
	- `universal-strategy-planning-agent.md`
	- `senior-golang-ai-engineer-agent.md`
	- `golang-test-expert-ai-engineer-agent.md`

Prefer “universal-” for prompts that apply across stacks. Use stack or domain qualifiers (e.g., golang, frontend, data, security) for specialized agents.

---

## Authoring guidelines (add a new agent)

Keep each prompt self-contained and execution-focused.

Recommended sections:
- Title and one-line identity (who the agent is, what it guarantees)
- Role / Mission
- Core Principles / Non-negotiables
- Output Structure (required sections and their order)
- Anti-hallucination and Halt conditions
- Optional: CI/testing/security expectations

Quality checklist:
- Clear scope and success criteria
- Deterministic output sections (no ambiguity in order/format)
- No secrets or proprietary content
- Concise, skimmable, actionable language

---

## Contribution checklist

- [ ] File name follows naming conventions
- [ ] Prompt includes Role/Mission and Output Structure
- [ ] Anti-hallucination/Halt rules present
- [ ] No secrets or proprietary content
- [ ] Examples/acceptance criteria are clear and minimal

To contribute, add a new Markdown file at the repository root following the guidelines above. If you change an existing prompt meaningfully, add a short “Changelog” section at the bottom and bump the `version` in metadata if you use front matter.

---

## Optional metadata (front matter)

You can add YAML front matter at the top of an agent file to track ownership and revisions:

```yaml
---
title: GoSenior – Senior Golang AI Engineer Agent
slug: senior-golang-ai-engineer-agent
version: 1.0.0
owner: your-handle
lastUpdated: 2025-09-28
tags: [golang, engineering, testing, architecture]
---
```

---

## License suggestions

This repository currently does not define a license. If you intend to allow reuse:
- Prompts/text: consider a documentation/content license such as CC BY 4.0
- Code examples/snippets: consider MIT or Apache-2.0

Add a `LICENSE` file to formalize the choice.

---

## Cross-agent guardrails & quality gates

All prompts favor clarity, determinism, and safe defaults.

- Do not invent APIs/data models; state assumptions explicitly and ask before proceeding.
- Prefer minimal, working solutions first; refactor after meeting acceptance criteria.
- Quality gates before “done”:
	- Build/typecheck passes (or N/A)
	- Lint/static checks pass or are explicitly deferred with rationale
	- Unit tests pass; include a tiny smoke test or clearly documented steps
	- For Go repos, use race and coverage flags where relevant

---

## New agent template

Copy and adapt this template when adding a new agent:

```markdown
# <Agent Name>

Role: <who this agent is and what it guarantees>

🎯 Mission
<What this agent must deliver and how success is measured>

🧠 Core Principles
- <principle 1>
- <principle 2>

🧾 Output Structure (REQUIRED)
<section_1>
<section_2>
...

Guardrails
- Do not invent requirements; ask targeted questions.
- Keep outputs deterministic and follow repo conventions.

Quality Gates
- Build/lint/tests pass (or explicitly N/A with reason)
- Small smoke test or run instructions provided
```

## FAQ

- Can I customize these prompts?
	Yes. Treat them as starting points; adapt wording and constraints to your workflow or organization.

- Do these prompts require specific tools?
	No. They are tool-agnostic and work in any chat-based or API-driven LLM environment.

- How long should a prompt be?
	Long enough to be unambiguous, but short enough to be read and followed. Prefer strict, numbered sections over prose.

---

## Changelog

- 2025-09-28: Replace placeholder README with comprehensive repository documentation.
