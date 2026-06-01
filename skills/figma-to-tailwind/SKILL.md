---
name: figma-to-tailwind
description: Convert a Figma frame into a responsive React + Tailwind component that uses the project's existing design tokens instead of hardcoded values. Use when the user shares a Figma URL or selection and asks to "build this", "code this up", "turn this into a component", or "make a React version".
---

# Figma to Tailwind

Generates a clean, responsive React component from a Figma frame. Reuses tokens from the project (`tokens.json`, `tailwind.config.*`, or existing components) rather than dumping hex values inline.

## When to use

- "Build this Figma frame as a React component"
- "Turn this design into code"
- "Make a responsive Tailwind version of this"
- After tokens have been extracted via [design-token-extractor](../design-token-extractor)

## When NOT to use

- The user wants a quick visual mockup, not production code (use an artifact instead)
- The codebase uses a different styling system (CSS modules, styled-components, vanilla CSS) — adapt manually
- Pixel-perfect static reproduction is required and tokens don't exist yet — extract tokens first

## Inputs

- A Figma frame URL or selection (via Figma MCP if connected, otherwise a screenshot + a description)
- The project root, so the skill can find `tailwind.config`, `tokens.json`, or existing component patterns

## Steps

1. **Read the design.** Pull frame data via the Figma MCP if available; otherwise inspect the screenshot.
2. **Map to tokens.** For every color, font size, spacing, and radius — find the matching token in the project. If no match exists, flag it (don't silently hardcode).
3. **Detect breakpoints.** If the design includes mobile/tablet/desktop frames, infer `sm:` / `md:` / `lg:` variants. Otherwise design mobile-first and note assumptions.
4. **Identify reusable pieces.** If the frame contains a card, badge, button, or input that already exists in the codebase — import it instead of re-implementing.
5. **Generate the component.** Functional component, named export, TypeScript if the project uses it. Props for any obvious variant (size, intent, disabled state).
6. **Add a usage example** in a comment at the top.
7. **Print a checklist** of: tokens used, tokens missing, components reused, things to verify with the designer.

## Output format

A single `.tsx` (or `.jsx`) file ready to drop into the project, plus a short summary in chat:

```tsx
// Usage:
// <PricingCard plan="pro" price="$29" features={["Unlimited", "Priority support"]} />

import { Button } from "@/components/ui/button"; // reused from existing codebase

interface PricingCardProps {
  plan: string;
  price: string;
  features: string[];
}

export function PricingCard({ plan, price, features }: PricingCardProps) {
  return (
    <div className="rounded-lg border border-neutral-200 p-6 shadow-sm md:p-8">
      {/* ... */}
    </div>
  );
}
```

Followed by:

```
✓ Tokens used: bg-brand-primary, text-neutral-900, p-6, rounded-lg
⚠ Missing tokens: shadow-lg-soft (Figma uses 0 8px 24px rgba(0,0,0,0.04) — not in config)
↻ Reused: Button (from @/components/ui/button)
? Verify with designer: hover state for primary CTA wasn't specified
```

## Notes

- Mobile-first by default. Use `sm:` / `md:` / `lg:` only when the design shows breakpoint variants.
- Never invent token names. If `bg-brand-purple` doesn't exist in the config, either use the closest existing one and flag it, or output the raw value with a `// TODO: add token` comment.
- Accessibility: include semantic HTML (`<button>`, not `<div onClick>`), `aria-label` for icon-only buttons, focus-visible styles.
