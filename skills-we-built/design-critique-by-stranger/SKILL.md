---
name: design-critique-by-stranger
description: Give structured, prioritized design feedback on a mockup or screenshot — hierarchy, consistency, copy, and usability. Use when the user says "review this design", "critique this", "what do you think of this screen?", or shares a Figma frame for feedback.
---

# Design Critique

Acts as a sharp but kind design reviewer. Returns feedback organized by category and ranked by impact, so the designer knows what to fix first.

## When to use

- "Review this mockup"
- "Critique this screen"
- "What would you change about this design?"
- After a design iteration, before sharing with stakeholders

## When NOT to use

- The user wants accessibility-only feedback → use [accessibility-checker](../accessibility-checker)
- The user wants code, not feedback → use [figma-to-tailwind](../figma-to-tailwind)
- The user only wants validation ("looks good right?") — give honest feedback anyway, but lead with what's working

## Inputs

- A screenshot, Figma frame, or live URL
- Optionally: the goal of the screen ("we're trying to increase signup conversion"), the user it's for, and constraints (brand, platform, deadline)

If the goal isn't stated, ask once — it changes the critique substantially.

## Steps

1. **Start with what's working.** Two or three specific strengths. Not flattery — concrete observations.
2. **Critique by category:**
   - **Hierarchy** — Does the eye land on the most important thing first? Is the primary action obvious within 2 seconds?
   - **Consistency** — Spacing, type scale, color usage, component patterns. Flag anything that breaks the system.
   - **Copy** — Clarity, voice, length, jargon. Empty states, error messages, button labels.
   - **Usability** — Can the user complete the primary task without thinking? Common patterns followed? Edge cases handled (loading, error, empty)?
   - **Visual polish** — Alignment, optical balance, contrast, density.
3. **Rank by impact.** Group findings into Must-fix / Should-fix / Nice-to-have. Don't bury the lede.
4. **Be specific.** "The CTA button feels weak" is useless. "The CTA button is the same weight as the secondary link below it — bump to filled style, increase contrast, and add 8px more padding" is useful.
5. **Suggest, don't dictate.** Offer 1–2 concrete options where appropriate.

## Output format

```
## Critique: <screen name>

**Goal:** <stated or inferred>

### What's working
- <Specific strength 1>
- <Specific strength 2>

### Must fix
1. **<Issue title>** — <One-line description>
   - Why it matters: <impact on goal/user>
   - Suggestion: <specific fix, or 2 options>

### Should fix
…

### Nice to have
…

### Open questions
- <Anything you couldn't critique without more context>
```

## Notes

- Lead with strengths but don't pad. If only one thing is working, say one thing.
- Avoid design-school jargon ("the visual rhythm lacks tension") unless the user is clearly a designer.
- If the user shares 3 iterations, compare them — don't critique each in isolation.
- Reference established patterns by name when relevant (Material's elevation system, iOS HIG navigation patterns, etc.) — but don't cargo-cult.
- Voice: honest, concrete, kind. Not "this is bad" — "this isn't doing the job because X, try Y".
