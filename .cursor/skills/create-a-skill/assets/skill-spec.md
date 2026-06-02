# Skill spec — <skill name>

The decision record for the skill being built. Fill this from the draft paper once the direction and scope are agreed. Save to `skills/<skill-name>/_planning/skill-spec.md`.

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

## Chosen direction

- Direction: <A / B / C — name>
- Why over the others: <one line>

## Eval prompts (tests, written before building)

1. Happy path — Prompt: "<...>" -> Expect: <...>
2. Edge case — Prompt: "<...>" -> Expect: <...>
3. Variation — Prompt: "<...>" -> Expect: <...>

## Files to create (gallery PR)

```
skills/<name>/
├── SKILL.md
├── references/     # optional — longer docs
├── scripts/        # optional — executable helpers
├── assets/         # optional — templates, fixtures
└── _planning/      # onboarding notes (committed)
```

## Scope note

Buildable in ~20 minutes including testing: <yes / no>. Anything deferred: <list>.
