# Writing the SKILL.md

Skills load through **progressive disclosure**: the agent reads the least it needs, then more on demand. Write to that grain.

## Three levels

| Level | Content | Loaded |
|-------|---------|--------|
| 1 | Frontmatter (`name`, `description`) | Always — ~100 words max |
| 2 | `SKILL.md` body | When the skill triggers — **under 500 words** |
| 3 | `references/`, `scripts/`, `assets/` | On demand only |

100 words is the practical target for the body. 500 words is the hard ceiling. If you're near 500, move content to `references/` — do not push past it.

## The description decides everything

It is the only line the agent sees by default. Make it carry **WHAT** and **WHEN**.

- Write in **third person**: "Audits a design…", not "I can audit…".
- First sentence: what it does. Second: "Use when [specific triggers]."
- Add a negative trigger if the skill could over-fire.

> Good: "Extract design tokens from a Figma file or screenshot into tokens.json. Use when the user mentions design tokens, color/spacing/type scales, or shares a Figma URL for token extraction."

> Weak: "Helps with design tokens."

## When to add a script

- The operation is deterministic — same input always produces the same output (e.g. contrast ratio check, token formatter, lint pass).
- The same code would otherwise be regenerated from scratch each run.
- Errors need consistent, explicit handling you can't trust the agent to improvise.

If none of these apply, plain instructions in `SKILL.md` are enough.

## When to split into references/

- A section of `SKILL.md` exceeds ~50 words and is not needed for the common case.
- The content covers a distinct domain (a long checklist, a platform-specific output format, an advanced edge case).
- Advanced instructions that most runs will skip.

Link from `SKILL.md` one level deep: `[references/checklist.md](references/checklist.md)`.

## Set the right degree of freedom

Match how strict you are to how fragile the task is:

- **High freedom** (plain instructions) — many valid approaches, like a critique.
- **Medium freedom** (templates / pseudocode) — preferred pattern with variation.
- **Low freedom** (exact scripts) — fragile steps where consistency is critical.

## Anti-patterns to avoid

- Bloated body — move detail to `references/`.
- Too many options — one default plus an escape hatch.
- Time-sensitive notes — split into "current / deprecated" instead.
- Inconsistent terms — pick one word and keep it.
- Vague names — `helper`, `utils`. Name the task.

## Quality checklist

- [ ] `name` is lowercase-with-hyphens, ends with `-by-<username>`, matches the folder.
- [ ] Description: WHAT + "Use when [triggers]", third person, under ~100 words.
- [ ] Body under 500 words; long content moved to `references/`.
- [ ] References linked one level deep from `SKILL.md`.
- [ ] Output format shown as a copy/paste template.
- [ ] At least one concrete example.
- [ ] Tested against 2–3 realistic prompts in a fresh agent — see [tdd-for-skills.md](tdd-for-skills.md).
