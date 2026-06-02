# AI Design Skills

A community-curated collection of Skills built by designers, for designers — to automate the repetitive parts of design work in **Cursor** (and any other agent that supports the open [SKILL.md format](https://github.com/anthropics/skills): Claude Code, Claude.ai, Codex, Windsurf, etc).

Created during the **Cursor x Goodnotes AI Design Workshop**, this repo is where workshop attendees publish the skills they build during the live hands-on session. Everyone is welcome to contribute.

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](#contributing) [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)

---

## New here? Let the agent onboard you

This repo onboards you. Open it in Cursor (or any agent that reads `AGENTS.md`) and the agent greets you and walks you through building your first skill, step by step. If it doesn't start on its own, just say **"onboard me"**.

- [AGENTS.md](AGENTS.md) — what the agent does the moment you open the repo.
- [.cursor/skills/create-a-skill/SKILL.md](.cursor/skills/create-a-skill/SKILL.md) — the one workshop guide (onboarding + how to write a skill; `references/` + `assets/` per Cursor layout).

Built for designers of every AI-literacy level. No prior skill-writing experience needed.

---

## What is a Skill?

A Skill is a folder with a `SKILL.md` file that teaches an AI agent how to perform a specific task. It loads only when the agent thinks it's relevant — so you can stack hundreds of skills without bloating context. Cursor added native Skills support in **2.4** (Jan 2026), using the same SKILL.md format Anthropic introduced for Claude.

Minimal skill (Cursor standard):

```
my-skill/
└── SKILL.md
```

With optional bundles:

```
my-skill/
├── SKILL.md
├── references/   # longer docs, loaded on demand
├── scripts/        # executable helpers
└── assets/         # templates, fixtures
```

`SKILL.md` starts with YAML frontmatter and then plain instructions:

```markdown
---
name: my-skill
description: One sentence describing when this skill should fire.
---

Step-by-step instructions for the agent...
```

> **Skills vs. Cursor Rules.** `.cursorrules` is always-on project context (conventions, stack, style). A Skill is loaded on demand, based on its description matching the task. Use both — rules for "how we work here", skills for "how to do this specific thing".

---

## Workshop Skills

Skills built by workshop attendees. **Add yours via PR** — see [CONTRIBUTING.md](CONTRIBUTING.md).

### Design Systems

- [design-token-extractor-by-stranger](skills-we-built/design-token-extractor-by-stranger) — Pull colors, typography, spacing, and radii out of a Figma file or screenshot into a clean `tokens.json`.
- [component-doc-writer-by-stranger](skills-we-built/component-doc-writer-by-stranger) — Generate variant tables, prop docs, and usage examples for a React/Vue/Swift component from its source file.

### Figma → Code

- [figma-to-tailwind-by-stranger](skills-we-built/figma-to-tailwind-by-stranger) — Convert a Figma frame URL into a responsive Tailwind + React component using your design tokens.

### Review & Critique

- [accessibility-checker-by-stranger](skills-we-built/accessibility-checker-by-stranger) — Audit a screen or component against WCAG 2.1 AA: contrast, focus order, target size, alt text.
- [design-critique-by-stranger](skills-we-built/design-critique-by-stranger) — Structured feedback on a mockup: hierarchy, consistency, copy, and usability — ranked by severity.

<!-- Add your skill above this line, under the appropriate category. Create a new category if none fit. -->

---

## How to Use a Skill in Cursor

**Project-scoped** (only this repo):

```bash
mkdir -p .cursor/skills
cp -r path/to/this/repo/skills-we-built/design-token-extractor-by-stranger .cursor/skills/
```

**Global** (every Cursor project):

```bash
mkdir -p ~/.cursor/skills
cp -r path/to/this/repo/skills-we-built/design-token-extractor-by-stranger ~/.cursor/skills/
```

Reload the Cursor workspace (`Cmd/Ctrl+Shift+P` → "Reload Window"). Open the Skills panel in the sidebar to confirm it's loaded. The skill activates automatically when your prompt matches its `description`.

> Skills also work in **Claude Code** (`.claude/skills/`), **Claude.ai** (upload via Settings → Capabilities), **Codex**, and **Windsurf** — same SKILL.md, different install path.

---

## Contributing

PRs welcome. The bar is low: a working `SKILL.md` and a one-line description in this README. See [CONTRIBUTING.md](CONTRIBUTING.md) for the 60-second version.

Copy [`_template/`](_template) to get started.

---

## Resources

- [Cursor Skills docs](https://cursor.com/help/customization/skills) — official Cursor docs
- [Anthropic Skills repo](https://github.com/anthropics/skills) — the canonical reference set

---

## License

MIT — see [LICENSE](LICENSE). Each contributed skill remains the copyright of its author; submitting a PR licenses the skill under MIT unless the skill folder specifies otherwise.