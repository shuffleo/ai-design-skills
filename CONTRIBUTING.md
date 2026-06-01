# Contributing

Thanks for sharing what you built! This repo exists so workshop attendees (and anyone else) can publish their skills and find ones built by others.

## The 60-second version

1. **Fork** this repo.
2. **Copy** `_template/` to `skills/your-skill-name/` (use kebab-case).
3. **Edit** `SKILL.md`:
   - `name`: must match the folder name
   - `description`: one sentence — the agent uses this to decide when to load your skill, so be specific about the *trigger*
   - Body: clear, step-by-step instructions
4. **Add a one-liner** to `README.md` under the right category:
   ```markdown
   - [your-skill-name](skills/your-skill-name) — One sentence describing what it does.
   ```
5. **Open a PR** with a short title (`add: your-skill-name`).

That's it. A maintainer will merge once the skill loads cleanly and the README entry is in place.

## What makes a good `description`?

The description is the only part of your skill the agent sees by default. It decides whether to load the full `SKILL.md` based on this one line. Be specific about **when** it should fire, not just what it does.

Good:
> Audit a Figma frame or screenshot against WCAG 2.1 AA — contrast, focus order, target size, alt text. Use when the user says "check a11y", "is this accessible?", or shares a design for review before handoff.

Less good:
> Helps with accessibility.

## Skill structure

Minimum:

```
skills/your-skill-name/
└── SKILL.md
```

Optional extras (load on demand):

```
skills/your-skill-name/
├── SKILL.md
├── scripts/           # executable helpers the skill can run
├── references/        # longer docs the skill points to
└── assets/            # templates, examples, fixtures
```

Reference these from inside `SKILL.md` with relative paths (`scripts/check.py`, `references/wcag-checklist.md`).

## Quality bar

- Skill works end-to-end on a fresh agent with no extra setup beyond what `SKILL.md` documents
- No secrets, API keys, or proprietary brand assets committed
- No skill larger than ~5,000 tokens in the body (move long content to `references/`)
- One skill per folder; one PR per skill keeps review fast

## Updates and removals

Update your own skill any time via PR. If a skill stops working or its author goes inactive, anyone can submit a PR to fix it — the original author gets pinged for review but a maintainer can merge after 7 days if there's no response.

## Code of conduct

Be kind. Assume good intent. Designers reviewing each other's work is the whole point — keep critique on the skill, not the person.
