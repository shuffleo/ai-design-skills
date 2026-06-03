# Onboarding flow

Run these steps in order. Ask **one focused thing at a time**, keep language simple, and append answers to `skills-we-built/<skill-name>/_planning/draft.md`.

## Before anything: check for existing context

Scan the current conversation for answers to the onboarding questions below. Then decide:

- **Fresh chat, no prior context** — run the full flow from step 0.
- **Mid-conversation with partial context** — skip to the brief-first path below.

### Brief-first path (mid-conversation)

1. Summarise what you already know in 3-5 sentences: skill idea, JTBD, tools/output, scope, constraints.
2. Present the brief: *"Here's what I've gathered from our conversation — does this look right?"*
3. List which steps have **gaps** (not answered, vague, or contradictory).
4. Ask only the **gap questions**, one at a time, in step order. Skip steps that are fully answered.
5. Once gaps are filled, create or update the draft paper and move straight to planning.

If unsure, ask a one-line confirmation instead of rerunning the full step.

---

## 0. Greet and set up

Welcome the designer. In two sentences explain what a skill is and what this session produces. Start [../assets/draft-paper.md](../assets/draft-paper.md).

## 1. Capture ideas and pick one

Ask for **top 2** skill ideas; note which fit (repeatable, procedural, clear in/out). Then run [scope-first.md](scope-first.md) — **one skill chosen** before step 2.

## 2. Frame as jobs

For the **chosen idea only**, write JTBD + definition of done per [jtbd-and-done.md](jtbd-and-done.md).

## 3. Tools and output

Per [outputs-and-mcp.md](outputs-and-mcp.md): output type + app (Figma, Notion, Slack, Jira, etc.). If MCP is needed but tool is unclear, run short MCP discovery, then [mcp-setup-guide.md](mcp-setup-guide.md).

## 4. Eval inputs (prepare now, run later)

Capture these now for the release eval gate:

- **2-4 prompts**: happy path, variation, edge case, negative trigger.
- **Expected output shape** (sections/template + must-have elements) only for written artifacts.
- If the skill is action-first and format is already defined elsewhere, skip output-shape capture.

## 5. Workflow and recall

Turns today: **1 / 2-3 / 5-10 / 10+**. Optional past chat -> [../assets/workflow-recall.md](../assets/workflow-recall.md).

## 6. Desk research

Per [research-method.md](research-method.md): **10+ sources**, no note word cap, extract frameworks/principles, validate what is useful, then pick 1 of 3 directions.

## 7. The intern question

One question at a time; check and clarify each answer. Full sequence: [intern-extraction.md](intern-extraction.md).

## 8. Confirm workshop scope

Still buildable in **~20 minutes**? Narrow if needed; confirm before planning.

## 9. Plan it (TDD first)

Plan mode. Write prompts/expectations before `SKILL.md` per [tdd-for-skills.md](tdd-for-skills.md). Tradeoffs: [plan-tradeoffs.md](plan-tradeoffs.md).

## 10. Double-check the plan

Optional review per [plan-review.md](plan-review.md).

## 11. Name it and close out

Per [naming.md](naming.md): folder ends with **`-by-<username>`**; ask their name if unknown.

After build, run **one closeout eval gate**:

1. Run the 2-4 prompts in a fresh agent.
2. Confirm negative trigger does not over-fire and edge case is safe.
3. Confirm required output sections/format when applicable.
4. Record evidence in `_planning/`, then continue PR flow per [../../../../CONTRIBUTING.md](../../../../CONTRIBUTING.md).

Keep the draft updated throughout.
