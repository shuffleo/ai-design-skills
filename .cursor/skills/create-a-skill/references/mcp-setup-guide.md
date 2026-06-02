# MCP setup (hand-in-hand)

Use this **only when** the skill needs an MCP and the designer has chosen which tool. Go step by step; do not skip verification.

## Before you start

Confirm in the draft: **which MCP**, **read or write**, and **what action** the skill needs (e.g. "read a Notion page", "post to Slack").

## Setup loop

1. **Check what they already have** — Ask: "In Cursor, open Settings → MCP (or Plugins). Do you see [tool name] connected?" Use what you can see from available MCP tools in this session if helpful.
2. **Install if missing** — Point them to Cursor Plugins or the official MCP docs for that product. One tool at a time.
3. **Authenticate** — Walk them through sign-in or API token. Never ask them to paste secrets into chat; use Cursor's connection UI.
4. **Smoke test** — Run one tiny real action (e.g. search Notion, list a Slack channel, fetch a Jira issue). If it fails, fix setup before building the skill.
5. **Record in the draft** — Tool name, connected yes/no, and the exact MCP actions the skill will use.

## Product quick links (common in design workshops)

| Tool | Typical use in a skill |
|------|------------------------|
| **Figma** | Read or edit frames, variables, components |
| **Notion** | Read/write pages, databases, tasks |
| **Slack** | Search messages, post updates |
| **Jira / Confluence** (Atlassian) | Issues, specs, comments |
| **Amplitude** | Metrics, funnels, feedback themes |

If setup blocks the workshop, offer a **fallback** in the skill (e.g. paste export, screenshot, CSV) and note it in the skill spec.
