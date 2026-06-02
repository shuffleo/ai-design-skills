# Naming the skill

The name is the folder name and the `name` in frontmatter. It must be clear, unique, and **credited to the author**.

## Rules

- **Core name:** up to **three words**, kebab-case, name the task: `accessibility-checker`, `figma-to-tailwind`.
- **Author suffix:** folder and `name` must end with **`-by-<username>`** — use their GitHub username or the name they give you (lowercase, hyphens for spaces). Example: `accessibility-checker-by-alex`.
- **Ask if unsure.** If you do not know their username, ask before creating the folder.
- **Folder name = `name` in frontmatter.** They must match exactly.

Full pattern: `<task-words>-by-<username>` (e.g. `design-critique-by-sam`).

## Good vs weak

| Good | Weak | Why |
|------|------|-----|
| `token-extractor-by-jane` | `design-magic-by-jane` | Task vs vibe. |
| `a11y-checker-by-alex` | `helper-by-alex` | Specific vs vague. |
| `figma-to-tailwind-by-chen` | `figma-to-tailwind` | Missing author suffix. |

Avoid `helper`, `utils`, `tools`, `assistant` in the task part.

## Avoid conflicts

1. Check existing skills under `skills/` (see [../../../../README.md](../../../../README.md)) — another author's suffix makes yours unique.
2. Check installed skills in `~/.cursor/skills/` and `.cursor/skills/`.
3. If descriptions could overlap, add trigger words or a negative trigger in `description`.

## Quick check

- [ ] Task part is three words or fewer.
- [ ] Ends with `-by-<username>`.
- [ ] kebab-case; folder matches frontmatter `name`.
- [ ] No clash with another skill's triggers.

Record the final name in [../assets/skill-spec.md](../assets/skill-spec.md), then copy [../../../../_template](../../../../_template) into `skills/<name>/`.
