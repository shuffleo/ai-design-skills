# TDD for skills

A skill is prose, not code — but you still test first. Define what good looks like **before** writing `SKILL.md`, then use one release check at the end.

## The loop

```
Task progress:
- [ ] 1. Write eval prompts + expected behavior (the tests)
- [ ] 2. Write the minimal SKILL.md to pass them
- [ ] 3. Build the skill
- [ ] 4. Run one closeout eval gate before PR-ready
```

## Step 1: Write the tests first

Write eval inputs during onboarding/planning:

- **2-4 realistic prompts**: happy path, variation, edge case, negative trigger.
- **Expected output shape** (sections/template + must-have elements) only for written artifacts.
- If the skill is action-first and output shape is already captured elsewhere, skip that field.

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

### Eval 4: negative trigger
Prompt: "Rename this folder in my repo."
Expect: Skill should not fire.
```

## Step 2: Build minimal

Write only enough `SKILL.md` to satisfy the evals. Resist adding "nice to have" steps now — that is over-engineering.

## Step 3: Closeout eval gate (release gate only)

Run this once after build, before PR-ready confirmation:

1. Run all eval prompts in a fresh agent.
2. Check deterministic pass/fail first:
   - triggers correctly (and does not over-fire on negative prompt),
   - edge case fails safely,
   - required sections/format present (when applicable).
3. For subjective quality only, add a short rubric (clarity, usefulness, structure) with one-line evidence per score.
4. Record closeout evidence in `_planning/` so reviewers can rerun.

## Done when

- [ ] Prompt set includes happy, variation, edge, and negative trigger.
- [ ] Closeout gate run is recorded with evidence.
- [ ] Skill fires on the right prompts and not the wrong ones.
- [ ] Edge cases are handled safely.
- [ ] Written output format is consistent when applicable.

Save eval artifacts in `skills-we-built/<skill-name>/_planning/` so reviewers can rerun them.
