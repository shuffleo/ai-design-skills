---
name: create-a-skill
description: Guides designers through creating an agent skill in this workshop repo — onboarding, JTBD, TDD, naming, and shipping a PR. Use when the user says onboard me, start onboarding, how to write a skill, or wants to create a design skill from scratch.
disable-model-invocation: true
---

# Create a skill

This is the **one guide** for the workshop: onboarding plus how to write a skill. `AGENTS.md` starts onboarding automatically in this repo; you can also type **`/create-a-skill`**.

## Onboarding

Follow [references/onboarding-flow.md](references/onboarding-flow.md) step by step. Save answers to `skills/<skill-name>/_planning/draft.md`. Templates: [assets/draft-paper.md](assets/draft-paper.md), [assets/workflow-recall.md](assets/workflow-recall.md), [assets/skill-spec.md](assets/skill-spec.md).

## How to write a skill (short)

A skill is a folder with `SKILL.md` that teaches an agent **one repeatable task**. Good candidates are procedural, repeatable, and have clear input/output.

Every `SKILL.md` looks like this:

```markdown
---
name: your-skill-name-by-username
description: WHAT it does. Use when [specific triggers].
---

## Quick start
> User says: "…" — Skill returns: …

## Workflow
1. Step one.
2. Step two.
3. Return the output below.

## Output format
[Copy/paste template of the exact output]

## When NOT to use
- [Over-fire case or better-fit skill]
```

1. **Frame the job** — When [situation], I want to [motivation], so I can [outcome]. Add a checkable definition of done. See [references/jtbd-and-done.md](references/jtbd-and-done.md).
2. **Write the description** — WHAT + WHEN, third person, trigger words. This line decides when the skill fires. See [references/skill-writing.md](references/skill-writing.md).
3. **Test first (TDD)** — 2–3 realistic prompts + expected behavior before you write the body. See [references/tdd-for-skills.md](references/tdd-for-skills.md).
4. **Keep it lean** — Core steps in `SKILL.md` (under 500 words); long detail in `references/`, code in `scripts/`, templates in `assets/`. Link one level deep.
5. **Name and ship** — Task name ≤3 words, kebab-case, suffix `-by-<username>`. Copy [../../../../_template](../../../../_template) into `skills-we-built/<name>/`. PR per [../../../../CONTRIBUTING.md](../../../../CONTRIBUTING.md).

Where folders live in Cursor and this repo: [references/repo-layout.md](references/repo-layout.md).

## Reference docs

| Topic | File |
|-------|------|
| Onboarding steps | [references/onboarding-flow.md](references/onboarding-flow.md) |
| Pick one idea first | [references/scope-first.md](references/scope-first.md) |
| Intern Q&A | [references/intern-extraction.md](references/intern-extraction.md) |
| Plan tradeoffs | [references/plan-tradeoffs.md](references/plan-tradeoffs.md) |
| Repo + folder layout | [references/repo-layout.md](references/repo-layout.md) |
| JTBD + definition of done | [references/jtbd-and-done.md](references/jtbd-and-done.md) |
| Desk research | [references/research-method.md](references/research-method.md) |
| Writing SKILL.md | [references/skill-writing.md](references/skill-writing.md) |
| TDD for skills | [references/tdd-for-skills.md](references/tdd-for-skills.md) |
| Plan review | [references/plan-review.md](references/plan-review.md) |
| Outputs + MCP | [references/outputs-and-mcp.md](references/outputs-and-mcp.md) |
| MCP setup walkthrough | [references/mcp-setup-guide.md](references/mcp-setup-guide.md) |
| Naming | [references/naming.md](references/naming.md) |
