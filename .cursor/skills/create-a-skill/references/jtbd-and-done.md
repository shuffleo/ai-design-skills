# JTBD and definition of done

Before building, describe the **job** the skill does and how you will know it is **done**. This keeps the agent aimed at the outcome, not a guessed feature.

## JTBD statement

Use this format. Never mention a specific tool or solution in it.

> When **[situation/trigger]**, I want to **[motivation/action]**, so I can **[outcome]**.

- **Situation** — what is happening when the need appears.
- **Motivation** — the progress the designer wants to make.
- **Outcome** — what good looks like for them.

### Examples

> When **I finish a Figma screen**, I want to **check it against accessibility rules**, so I can **catch issues before handoff**.

> When **I get a new component file**, I want to **generate its prop and variant docs**, so I can **keep the design system documented without manual work**.

A test: can you state the job in one sentence without naming a product? If not, you are still feature-focused.

## Definition of done

Make "done" something an agent can verify. Cover three things:

1. **Happy path** — given a normal input, the skill produces this observable output.
2. **Edge / failure case** — given a bad or missing input, the skill responds this way (clear message, no crash, asks for what it needs).
3. **Evidence** — what proves it worked (a file created, a report with the right sections, a passing check).

### Template

```markdown
## Definition of done
- Happy path: When [normal input], the skill [observable output].
- Edge case: When [bad/missing input], the skill [safe behavior].
- Constraints: Does not [touch X] / stays within [guardrail].
- Evidence: [file / report section / check] proves success.
```

### Example

```markdown
## Definition of done
- Happy path: Given a Figma frame URL, returns a WCAG report grouped by severity.
- Edge case: If the URL is missing or private, asks for a public URL or screenshot.
- Constraints: Flags issues only; never edits the Figma file.
- Evidence: Report lists contrast, focus order, target size, and alt text.
```

## Acceptance criteria (optional, for richer skills)

Write 4–6 checks, each independently verifiable, focused on outcomes not steps:

- [ ] [Thing] [does/shows/enables] [behavior] under [condition].
- [ ] Includes at least one edge or error case.

Save the final JTBD and definition of done into the skill spec — see [../assets/skill-spec.md](../assets/skill-spec.md).
