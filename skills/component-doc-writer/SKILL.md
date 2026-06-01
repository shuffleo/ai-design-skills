---
name: component-doc-writer
description: Generate documentation for a UI component from its source file — variant table, prop reference, usage examples, do/don't, and accessibility notes. Use when the user shares a component file and says "document this", "write docs for this component", or "add this to the design system".
---

# Component Doc Writer

Reads a React, Vue, or SwiftUI component and produces design-system-quality documentation: prop reference, variant matrix, usage examples, and accessibility notes.

## When to use

- "Document this Button component"
- "Add this to the design system"
- "Write Storybook docs for this"
- Onboarding a new component into an existing system

## When NOT to use

- The component is one-off and doesn't belong in the system — say so
- The user wants tests, not docs (different skill)

## Inputs

- The component source file (`.tsx`, `.vue`, `.swift`, etc.)
- Optionally: the design system's existing doc format (so output matches the house style)

## Steps

1. **Read the source.** Identify props, default values, variants (typically a `variant` or `size` prop with a union type), and any internal state.
2. **Infer intent.** What is this component for? When should a designer reach for it vs. a similar one?
3. **Build the variant matrix.** Every combination of `variant` × `size` × `state` (hover, focus, disabled, loading). If the matrix is huge, focus on the meaningful subset.
4. **Write usage examples.** At least: basic, with variant, with all common props, edge case (long content, async loading).
5. **Add do/don't.** Two or three each. Be specific — "don't use Primary for destructive actions" not "use appropriately".
6. **Accessibility notes.** Keyboard behavior, ARIA attributes, what assistive tech announces.
7. **Cross-link related components.** "Use [Button] for actions; use [Link] for navigation."

## Output format

Markdown, ready to drop into Storybook MDX, Notion, or a docs site:

```markdown
# Button

A primary interactive element for user actions. Use for things the user does — submit, save, open. For navigation, use [Link](../link) instead.

## Props

| Prop       | Type                                  | Default     | Description                          |
|------------|---------------------------------------|-------------|--------------------------------------|
| `variant`  | `'primary' \| 'secondary' \| 'ghost'` | `'primary'` | Visual emphasis level.               |
| `size`     | `'sm' \| 'md' \| 'lg'`                | `'md'`      | Affects height, padding, font size.  |
| `disabled` | `boolean`                             | `false`     | Disables interaction.                |
| `loading`  | `boolean`                             | `false`     | Shows spinner, disables click.       |
| `icon`     | `ReactNode`                           | —           | Optional icon before label.          |

## Variants

|           | sm | md | lg |
|-----------|----|----|----|
| primary   | ✓  | ✓  | ✓  |
| secondary | ✓  | ✓  | ✓  |
| ghost     | ✓  | ✓  | —  |

## Usage

```tsx
<Button variant="primary" onClick={handleSave}>Save</Button>

<Button variant="secondary" size="sm" icon={<PlusIcon />}>
  Add row
</Button>

<Button variant="primary" loading>Submitting…</Button>
```

## Do

- Use **primary** for the single most important action on a screen.
- Use **secondary** for alternatives to the primary action.
- Use **ghost** inside dense UI (toolbars, tables) where a filled button would be visual noise.

## Don't

- Don't use two primary buttons in the same view — pick the one the user is most likely to take.
- Don't use Button for navigation — use [Link](../link).
- Don't manually override colors with `className`. If you need a new variant, add it to the component.

## Accessibility

- Renders as native `<button>`. Keyboard: Enter and Space activate; Tab navigates.
- Disabled state uses `aria-disabled="true"` (not the `disabled` attribute) so screen readers still announce it.
- When `loading` is true, the button is announced as "busy".
- Icon-only usage requires `aria-label`.

## Related

- [IconButton](../icon-button) — for icon-only actions in dense UI
- [Link](../link) — for navigation
- [Menu](../menu) — when offering multiple actions
```

## Notes

- If the component has no `variant` prop, skip the variant matrix.
- Pull defaults from the actual source, not from what feels right.
- If the source has comments explaining intent, weave them in — they're usually the highest-signal content.
- Keep do/don't to 2–3 each. Long lists get ignored.
