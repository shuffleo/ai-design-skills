---
name: accessibility-checker-by-stranger
description: Audit a design, screenshot, or live component against WCAG 2.1 AA — color contrast, target size, focus order, semantic structure, alt text. Use when the user says "check a11y", "is this accessible?", "audit accessibility", or shares a design before engineering handoff.
---

# Accessibility Checker

Runs a structured WCAG 2.1 AA audit on whatever the user shares — a Figma frame, a screenshot, a live URL, or a component file. Returns issues ranked by severity with specific fixes.

## When to use

- "Check accessibility of this screen"
- "Is this WCAG compliant?"
- "Audit a11y before handoff"
- Any time a design is about to ship and hasn't been reviewed

## When NOT to use

- The user wants a full legal compliance review (recommend a human auditor)
- The user only wants a contrast check — answer inline without invoking the full skill

## Inputs

One of:
- A screenshot or Figma frame
- A live URL (use Chrome tools if available)
- A component file

Plus, ideally: known user base context (does it need to support screen readers? keyboard-only? high contrast mode?)

## Steps

Walk through each category. For every issue found, record: **severity** (blocker / major / minor), **WCAG criterion**, **what's wrong**, **specific fix**.

1. **Color contrast** — Every text/background pair against WCAG AA: 4.5:1 for body text, 3:1 for large text (18pt+ or 14pt+ bold) and UI components. Compute actual ratios; don't eyeball.
2. **Target size** — Interactive elements ≥ 24×24 CSS px (WCAG 2.5.8). Recommend 44×44 for primary touch targets.
3. **Focus order & visible focus** — Tab order matches visual order; every focusable element has a visible focus indicator (not removed by `outline: none` without replacement).
4. **Semantic structure** — Headings in order (no skipping h2 → h4), buttons vs. links used correctly, lists marked up as `<ul>`/`<ol>`, landmarks (`<nav>`, `<main>`, `<footer>`) present.
5. **Text alternatives** — Every meaningful image has `alt`; decorative images have `alt=""`; icon-only buttons have `aria-label`.
6. **Forms** — Every input has a visible `<label>`; errors are announced (not just colored red); required fields marked beyond color.
7. **Motion & timing** — Auto-playing content can be paused; no content flashes more than 3× per second; respects `prefers-reduced-motion`.
8. **Keyboard** — Every interactive element reachable and operable via keyboard; no keyboard traps.

## Output format

```
## Accessibility Audit: <screen/component name>

### Blockers (must fix before ship)
1. **Contrast 2.8:1** — Primary CTA "Continue" — white text on `#7AAEFF` background.
   - WCAG 1.4.3 (AA): requires 4.5:1 for body text.
   - Fix: darken background to `#0B5FFF` (8.1:1) or use the existing `bg-brand-primary` token.

### Major (fix this sprint)
2. **Missing visible focus** — All buttons remove outline on focus.
   - WCAG 2.4.7 (AA): focus must be visible.
   - Fix: add `focus-visible:ring-2 focus-visible:ring-brand-primary focus-visible:ring-offset-2`.

### Minor (track for next iteration)
3. **Heading skip** — Page jumps from h1 to h3 in the FAQ section.
   - WCAG 1.3.1: structure should reflect document outline.
   - Fix: change FAQ section headings from h3 to h2.

### Passed
- All touch targets ≥ 44px
- Color is not the only indicator for required form fields
- Images have appropriate alt text

### Couldn't verify (static image)
- Tab order — needs live page or prototype
- Screen reader announcements — needs implementation review
```

## Notes

- Always compute contrast ratios numerically. Don't guess.
- Static images can't reveal keyboard traps or screen reader issues — say so explicitly.
- Severity guide: **blocker** = users actually cannot use the feature; **major** = users struggle; **minor** = polish.
- For brand colors that fail contrast, recommend the closest token that passes rather than inventing new hex values.
