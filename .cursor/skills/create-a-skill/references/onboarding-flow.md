# Onboarding flow

Run these steps in order. Ask **one focused thing at a time**, keep language simple, and append answers to `skills/<skill-name>/_planning/draft.md`. Use AskQuestion for choices.

## Before anything: check for existing context

**Do this every time the skill is invoked — fresh chat or mid-conversation.**

Scan the current conversation for answers to the onboarding questions below. Then decide:

- **Fresh chat, no prior context** — run the full flow from step 0.
- **Mid-conversation with partial context** — skip to the brief-first path below.

### Brief-first path (mid-conversation)

1. Summarise what you already know in 3–5 sentences — skill idea, JTBD, tools/output, scope, examples, any constraints mentioned.
2. Present the brief: *"Here's what I've gathered from our conversation — does this look right?"*
3. List which steps have **gaps** (not answered, vague, or contradictory).
4. Ask only the **gap questions**, one at a time, in step order. Skip steps that are fully answered.
5. Once gaps are filled, create or update the draft paper and move straight to planning.

If in doubt about whether something is answered, ask a quick one-liner to confirm rather than re-running the full step.

---

## 0. Greet and set up

Welcome the designer. In two sentences explain what a skill is and what this session produces. Start [../assets/draft-paper.md](../assets/draft-paper.md).

## 1. Capture ideas and pick one

Ask for **top 2** skill ideas; note which fit (repeatable, procedural, clear in/out). Then run [scope-first.md](scope-first.md) — **one skill chosen** before step 2.

## 2. Frame as jobs

For the **chosen idea only**, write JTBD + definition of done per [jtbd-and-done.md](jtbd-and-done.md).

## 3. Tools and output

Per [outputs-and-mcp.md](outputs-and-mcp.md): output type, which app (Figma, Notion, Slack, Jira, etc.). If they need an MCP but are unsure which tool, run the **short MCP discovery** there (only when needed), then [mcp-setup-guide.md](mcp-setup-guide.md) hand-in-hand.

## 4. Workflow and recall

Turns today: **1 / 2–3 / 5–10 / 10+**. Optional past chat → [../assets/workflow-recall.md](../assets/workflow-recall.md).

## 5. Desk research

Per [research-method.md](research-method.md): **10+ sources**, learning notes without a word cap, extract frameworks/principles. Present key learnings; ask what is **valid** vs **irrelevant**. Then **3 build directions** — pick one.

## 6. The intern question

One question at a time; check and clarify each answer. Full sequence: [intern-extraction.md](intern-extraction.md).

## 7. Confirm workshop scope

Still buildable in **~20 minutes**? Narrow if needed; confirm before planning.

## 8. Plan it (TDD first)

Plan mode. Evals before `SKILL.md` per [tdd-for-skills.md](tdd-for-skills.md). Tradeoffs + directional questions: [plan-tradeoffs.md](plan-tradeoffs.md).

## 9. Double-check the plan

Optional review per [plan-review.md](plan-review.md).

## 10. Name it

Per [naming.md](naming.md): folder ends with **`-by-<username>`**; ask their name if unknown. Build, test, PR per [../../../../CONTRIBUTING.md](../../../../CONTRIBUTING.md).

Keep the draft updated throughout.
