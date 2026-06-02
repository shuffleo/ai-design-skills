# TDD for skills

A skill is prose, not code — but you still test first. Write what good looks like **before** you write the skill, then build until it passes. This stops you from writing a skill that only works in your head.

## The loop

```
Task progress:
- [ ] 1. Write 2-3 eval prompts + expected behavior (the tests)
- [ ] 2. Write the minimal SKILL.md to pass them
- [ ] 3. Run each prompt in a fresh agent
- [ ] 4. Compare output to expected; fix the skill
- [ ] 5. Repeat 3-4 until all pass
```

## Step 1: Write the tests first

An eval is a realistic prompt plus the behavior you expect. Write them before any skill text.

```markdown
### Eval 1: happy path
Prompt: "Check this Figma frame for accessibility: [url]"
Expect: A report grouped by severity covering contrast, focus order,
target size, alt text. No edits to the file.

### Eval 2: edge case
Prompt: "Check accessibility" (no link)
Expect: Asks for a public URL or screenshot. Does not guess.

### Eval 3: variation
Prompt: "Is this screenshot accessible?" [image]
Expect: Same report format, reading from the image.
```

Cover at least one happy path and one edge/failure case.

## Step 2: Build minimal

Write only enough `SKILL.md` to satisfy the evals. Resist adding "nice to have" steps now — that is over-engineering.

## Step 3: Run in a fresh agent

Test in a clean chat (no memory of this conversation) so you see what a real user sees. Paste each eval prompt. A skill that needs your context to work will fail here.

## Step 4: Compare and fix

For each eval, ask:
- Did the skill **fire** at the right time?
- Did the output **match** the expected format?
- Did it handle the **edge case** safely?

Fix the skill — usually the description (firing) or the steps/output format (quality) — and rerun.

## Done when

- [ ] All evals pass in a fresh agent.
- [ ] The description fires on the right prompts and not the wrong ones.
- [ ] Output format is consistent across runs.
- [ ] Edge cases are handled, not crashed.

Save your evals in `skills/<skill-name>/_planning/` so reviewers can rerun them.
