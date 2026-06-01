---
name: design-token-extractor
description: Extract design tokens (colors, typography, spacing, radii, shadows) from a Figma file, screenshot, or pasted style sheet into a clean tokens.json. Use when the user shares a design and asks to "pull tokens", "extract the design system", "get the colors and type", or before starting a Figma-to-code conversion.
---

# Design Token Extractor

Turns a visual reference (Figma URL, screenshot, or pasted CSS) into a normalized `tokens.json` that downstream code-gen skills can consume.

## When to use

- "Pull design tokens from this Figma file"
- "What colors and fonts are in this screenshot?"
- "Extract the design system before I start coding"
- As a first step before [figma-to-tailwind](../figma-to-tailwind) or similar code-gen skills

## When NOT to use

- The user already has a `tokens.json` or design system spec — use it directly
- The user wants pixel-perfect implementation of a single component (use figma-to-tailwind instead)

## Inputs

One of:
- A Figma frame or file URL (use the Figma MCP if connected)
- An uploaded screenshot (PNG/JPG)
- A pasted CSS/SCSS/Tailwind config

## Steps

1. **Identify the source.** If Figma URL and the Figma MCP is connected, fetch styles directly. Otherwise inspect the image or text.
2. **Extract by category:**
   - `color` — name + hex, group by role (brand, neutral, semantic)
   - `typography` — font family, weights, sizes (px and rem), line-heights, letter-spacing
   - `spacing` — scale used for padding/margin/gap
   - `radius` — corner radii in use
   - `shadow` — elevation/shadow styles
3. **Normalize names.** Use semantic names where intent is clear (`color.brand.primary`), neutral names otherwise (`color.gray.900`). Never invent values — if uncertain, mark `TODO: confirm`.
4. **Output `tokens.json`** in the format below.
5. **Print a summary** of what was extracted and flag anything ambiguous.

## Output format

```json
{
  "color": {
    "brand": { "primary": "#0B5FFF", "primaryHover": "#0848C2" },
    "neutral": { "0": "#FFFFFF", "100": "#F5F6F8", "900": "#0E1116" },
    "semantic": { "success": "#1DB954", "danger": "#E5484D" }
  },
  "typography": {
    "fontFamily": { "sans": "Inter, system-ui, sans-serif" },
    "fontSize": { "xs": "12px", "sm": "14px", "base": "16px", "lg": "18px" },
    "fontWeight": { "regular": 400, "medium": 500, "semibold": 600 },
    "lineHeight": { "tight": 1.2, "normal": 1.5 }
  },
  "spacing": { "1": "4px", "2": "8px", "3": "12px", "4": "16px", "6": "24px", "8": "32px" },
  "radius": { "sm": "4px", "md": "8px", "lg": "12px", "full": "9999px" },
  "shadow": {
    "sm": "0 1px 2px rgba(0,0,0,0.06)",
    "md": "0 4px 12px rgba(0,0,0,0.08)"
  }
}
```

## Notes

- If extracting from a screenshot, color picks are approximate. Always flag this in the summary.
- Prefer rem units for typography when the user is targeting web; px for native.
- If you find 14 shades of "almost grey", consolidate. Designers rarely intend that many.
