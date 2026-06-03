# Desk research method

Before building, learn how others solve this task and what principles apply. Research serves the skill — extract **frameworks and principles** you can bake into `SKILL.md`, not a literature review.

## Run the research

Spawn one or more **subagents** in parallel. Each subagent gets a narrow angle. Together you must review **at least 10 sources** (docs, standards, blog posts, skill repos, product guidelines, etc.). Good targets:

- Industry standards for the task (e.g. WCAG for accessibility).
- Frameworks and mental models (JTBD, checklists, review rubrics).
- How strong teams describe "done" for this work.
- Existing agent skills or harnesses that do something similar.
- Example inputs and outputs of an excellent result.

Track every source with a URL or title in the notes.

## Save learning notes

Write to `skills-we-built/<skill-name>/_planning/research/` — one file per theme or source cluster. **No word limit** on these notes; be thorough for your own synthesis.

Use this format:

```markdown
# [Topic or source cluster]

## Sources (aim for 10+ total across all research files)
- [Title](url) — one-line why it matters

## Frameworks and principles to extract
- Named framework or principle and what it implies for our skill.

## Use in the skill
- Concrete rule, step, or check we should add to SKILL.md or references/.
```

Focus on **what to build**, not background trivia.

## Present key learnings

Summarize for the designer in plain language:

- Top frameworks or principles worth using.
- Patterns from existing skills worth copying or avoiding.
- Anything that changes scope or output format.

Then ask explicitly: **Which of these feel valid and useful for your task? Which feel irrelevant?** Update the draft from their answers. Do not treat research as final until they react.

## Propose 3 directions

After validated learnings, offer **three ways to build the skill**. For each: one-line summary, pros, cons. Vary by effort and ambition.

```markdown
## Build directions

### A. [Name] — simplest
- Pros: …
- Cons: …

### B. [Name] — balanced
- Pros: …
- Cons: …

### C. [Name] — ambitious
- Pros: …
- Cons: …
```

Ask them to pick one. For a workshop, steer toward what is testable in ~20 minutes. Record the choice in [../assets/skill-spec.md](../assets/skill-spec.md).
