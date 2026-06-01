# AI Design Skills

A community-curated collection of Skills built by designers, for designers — to automate the repetitive parts of design work in **Cursor** (and any other agent that supports the open [SKILL.md format](https://github.com/anthropics/skills): Claude Code, Claude.ai, Codex, Windsurf, etc).

Created during the **Cursor x Goodnotes AI Design Workshop**, this repo is where workshop attendees publish the skills they build during the live hands-on session. Everyone is welcome to contribute.

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](#contributing) [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)

---

## What is a Skill?

A Skill is a folder with a `SKILL.md` file that teaches an AI agent how to perform a specific task. It loads only when the agent thinks it's relevant — so you can stack hundreds of skills without bloating context. Cursor added native Skills support in **2.4** (Jan 2026), using the same SKILL.md format Anthropic introduced for Claude.

Minimal skill:

```
my-skill/
└── SKILL.md
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

- [design-token-extractor](skills/design-token-extractor) — Pull colors, typography, spacing, and radii out of a Figma file or screenshot into a clean `tokens.json`.
- [component-doc-writer](skills/component-doc-writer) — Generate variant tables, prop docs, and usage examples for a React/Vue/Swift component from its source file.

### Figma → Code

- [figma-to-tailwind](skills/figma-to-tailwind) — Convert a Figma frame URL into a responsive Tailwind + React component using your design tokens.

### Review & Critique

- [accessibility-checker](skills/accessibility-checker) — Audit a screen or component against WCAG 2.1 AA: contrast, focus order, target size, alt text.
- [design-critique](skills/design-critique) — Structured feedback on a mockup: hierarchy, consistency, copy, and usability — ranked by severity.

<!-- Add your skill above this line, under the appropriate category. Create a new category if none fit. -->

---

## How to Use a Skill in Cursor

**Project-scoped** (only this repo):

```bash
mkdir -p .cursor/skills
cp -r path/to/this/repo/skills/design-token-extractor .cursor/skills/
```

**Global** (every Cursor project):

```bash
mkdir -p ~/.cursor/skills
cp -r path/to/this/repo/skills/design-token-extractor ~/.cursor/skills/
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