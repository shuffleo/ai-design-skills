# Workflow recall

Use this when the designer has a past chat where they did this task with an agent. It turns that history into reusable knowledge: what worked, what to avoid.

## Paste prompt (give this to the designer)

> Paste your previous chat below. I will summarize how you worked with the agent on this task — the steps you took, what went well, and the mistakes to avoid next time. Paste everything between the lines.
>
> ---
> <designer pastes the old chat here>
> ---

## Summary template (the agent fills this in)

```markdown
# Workflow recall — <task>

## What the designer was trying to do
<one or two lines>

## Steps that worked
1. <step the agent took that helped>
2. <step>

## Wins to repeat
- <a prompt, format, or move that produced a good result>

## Errors to prevent
- <a mistake, wrong turn, or dead end> -> <how the skill should avoid it>

## Inputs the agent needed
- <files, URLs, or context that were required>

## Turns it took
<rough count, and where time was lost>
```

## How to use it

- Pull the **errors to prevent** into the skill's steps or a "when NOT to" note.
- Pull the **wins to repeat** into the steps and output format.
- Save the finished summary to `skills-we-built/<skill-name>/_planning/workflow-recall.md`.

Keep it short — extract the lessons, do not transcribe the whole chat.
