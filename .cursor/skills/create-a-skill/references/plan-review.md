# Plan double-check

Catching problems at the plan stage is far cheaper than fixing them in a built skill. Offer this review after drafting the implementation plan and before building. Read the plan with fresh eyes and check each item below.

## Gaps

- Does the plan cover the **definition of done** from the skill spec?
- Is every step in the JTBD outcome actually produced?
- Are inputs the skill needs clearly available (URL, file, screenshot)?

## Missed dependencies

- Does it rely on an **MCP or tool** that is not set up?
- Does a step assume an output from an earlier step that the plan never creates?
- Are referenced files (`references/`, `scripts/`) listed to be written?

## Contradictions and conflicts

- Do any two steps disagree on format, naming, or order?
- Does the skill **name or description** clash with an installed skill, causing it to over-fire?
- Does the output format match what the JTBD outcome promised?

## Missed corners (edge cases)

- What happens on **bad or missing input**?
- What about an empty result, a private/locked file, or a huge input?
- Is there a safe failure path, or does it just guess?

## Over-engineering

- Can any step be **cut** without failing an eval?
- Is anything built for a case no eval covers? Defer it.
- Could a simpler direction pass the same tests in the 20-minute budget?
- Are there more options offered than needed? Prefer one default.

## Output of the review

List findings as fixes, not essays:

```markdown
## Plan review findings
- [ ] Gap: no edge case for missing URL — add to plan step 2.
- [ ] Dependency: Figma MCP not confirmed — verify or switch to screenshot input.
- [ ] Over-engineering: cut the export-to-HTML step; no eval needs it.
```

Apply the fixes to the plan, then continue to build. Re-run this check only if the plan changes a lot.
