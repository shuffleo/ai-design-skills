# Where skills live

## Cursor discovery paths

| Location | Scope |
|----------|--------|
| `.cursor/skills/<skill-name>/` | This project |
| `.agents/skills/<skill-name>/` | This project (same standard) |
| `~/.cursor/skills/<skill-name>/` | All your projects |

The folder name must match the `name` in `SKILL.md` frontmatter.

## This repo: two folders

1. **`.cursor/skills/`** — skills Cursor loads here (including `create-a-skill` for the workshop).
2. **`skills/`** — community gallery for PRs. Copy your finished skill here when you ship.

Build locally in `.cursor/skills/your-skill-name/` to test, then copy to `skills/your-skill-name/` before opening a PR.

## Standard folder layout

```
your-skill-name/
├── SKILL.md
├── references/     # longer docs, loaded on demand
├── scripts/        # executable helpers
└── assets/         # templates, fixtures
```

Link from `SKILL.md` one level deep: `references/checklist.md`, `scripts/validate.py`, `assets/template.md`.
