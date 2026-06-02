# Outputs and tool connections

Decide early **what the skill produces** and **whether it needs another tool**. This shapes the steps, the tests, and how you check it is done.

## What does the skill produce?

Pick the closest match. Most skills do one well.

| Output type | Looks like | Notes |
|-------------|-----------|-------|
| **Markdown** | A report, doc, checklist, or summary | Easiest to test; define section headings. |
| **Code / files** | A component, `tokens.json`, config | Specify language, path, format. |
| **Design file** | Figma (or similar) frames, variables, components | Usually needs the **Figma** MCP. |
| **Workspace doc** | Notion page, database row, task | Usually needs the **Notion** MCP. |
| **Team comms** | Slack message, thread summary, channel post | Usually needs the **Slack** MCP. |
| **Tracker** | Jira issue, Confluence page, comment | Usually needs **Atlassian** MCP. |
| **HTML / web** | Page, prototype, snippet | State stack (plain, React, Tailwind). |
| **Action (other)** | Creates/updates something in a product | Highest risk; confirm before every write. |

Write the output format in the skill — use a template so every run looks the same.

## Does it need an MCP?

An **MCP** lets the agent read or act in another product. If the skill touches live data outside this repo, it likely needs one.

**Ask first:** "Does this skill need to read from or write to another app?" If **no**, skip MCP setup and move on.

If **yes**, ask **which app** they use today (Figma, Notion, Slack, Jira, Confluence, etc.). Designers often need more than design tools — specs in Notion, tickets in Jira, updates in Slack.

### They know the tool

Guide them to **set it up before building** — install the plugin/MCP, authenticate, smoke-test. Full walkthrough: [mcp-setup-guide.md](mcp-setup-guide.md).

In `SKILL.md`: name the tool, list the exact MCP actions, and add an edge case if the connection is missing (ask the user; do not guess).

### They need an MCP but are not sure which tool

**Only do this when necessary** — not every skill needs market research.

1. From their JTBD, list what the skill must **read** or **write** (e.g. "our task board", "design file", "post a summary to the team").
2. Run a **short research pass** (a few minutes): which products + MCPs designers commonly use for that job. Check Cursor Plugins and well-known integrations (Figma, Notion, Slack, Atlassian/Jira, etc.).
3. Present **2–3 options** with one line each: what it connects, best for what, setup effort.
4. Let them **pick one**, then follow [mcp-setup-guide.md](mcp-setup-guide.md) step by step.
5. If setup will blow the ~20-minute budget, pick a **fallback input** (paste, export, screenshot) and record that in the plan.

## Read-only vs acting

Prefer **read-only** for a first build. If the skill **creates, sends, or edits** in another product, require explicit user confirmation each time.

Record output type, MCP choice, connected yes/no, and fallback in [../assets/skill-spec.md](../assets/skill-spec.md).
