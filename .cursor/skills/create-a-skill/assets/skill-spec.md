# Skill spec — <skill name>

The decision record for the skill being built. Fill this from the draft paper once the direction and scope are agreed. Save to `skills-we-built/<skill-name>/_planning/skill-spec.md`.

## Name and description

- Name: `<task-kebab-by-username>` (task part ≤3 words; must end with `-by-<username>`)
- Description (WHAT + WHEN + triggers, third person):

> <draft description here>

## Job to be done

When <situation>, I want to <motivation>, so I can <outcome>.

## Definition of done

- Happy path: When <normal input>, the skill <observable output>.
- Edge case: When <bad/missing input>, the skill <safe behavior>.
- Constraints: Does not <X> / stays within <guardrail>.
- Evidence: <file / report section / check> proves success.

## Output and tools

- Output type: <markdown / code / figma / html / action>
- MCP needed: <tool, or none> — confirmed: <yes / no>
- Read-only or acting: <read-only / requires confirmation>
- Expected output shape (written artifacts only): <sections/template + must-have elements, or N/A>

## Chosen direction

- Direction: <A / B / C — name>
- Why over the others: <one line>

## Eval prompts (written before building)

Use 2-4 prompts total, including:

1. Happy path — Prompt: "<...>" -> Expect: <...>
2. Variation — Prompt: "<...>" -> Expect: <...>
3. Edge case — Prompt: "<...>" -> Expect: <...>
4. Negative trigger — Prompt: "<...>" -> Expect: skill should not fire

## Closeout eval gate (run once after build)

Deterministic checks:

- Happy/variation prompts pass expected behavior.
- Edge case fails safely.
- Negative trigger does not over-fire.
- Required sections/format present (when applicable).

Optional rubric (subjective quality only):

- Clarity: <score + one-line evidence>
- Usefulness: <score + one-line evidence>
- Structure: <score + one-line evidence>

Evidence:

- Notes/file path: <_planning/eval-closeout.md>
- Time/tokens snapshot (if available): <...>

## Files to create (gallery PR)

```
skills-we-built/<name>/
├── SKILL.md
├── references/     # optional — longer docs
├── scripts/        # optional — executable helpers
├── assets/         # optional — templates, fixtures
└── _planning/      # onboarding notes (committed)
```

## Scope note

Buildable in ~20 minutes including testing: <yes / no>. Anything deferred: <list>.
