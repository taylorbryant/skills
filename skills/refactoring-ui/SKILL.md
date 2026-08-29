---
name: refactoring-ui
description: Audit and refine existing web and application interfaces using systematic hierarchy, spacing, typography, color, depth, and image treatment. Use for visual cleanup, design-system normalization, or polish of an existing implementation. Do not select for general net-new UI unless the user explicitly asks for Refactoring UI.
---

# Refactoring UI

Make interfaces clear and polished by improving decisions in order of leverage. Preserve the product's requirements, content, interaction model, framework, and existing design-system constraints unless the user asks to change them.

This skill is an original synthesis inspired by *Refactoring UI* by Adam Wathan and Steve Schoger. Treat its heuristics as decision aids, not immutable rules.

For net-new UI, use this skill only when the user explicitly invokes it or asks for a Refactoring UI approach. If another design skill is active, let that skill define the visual language and use this one as a refinement lens.

## Choose the Mode

- **Create (explicit use):** Design the smallest useful version of a concrete feature before designing the surrounding application shell.
- **Refine:** Diagnose the current interface and fix the highest-leverage visual problems first. Preserve working behavior.
- **Review:** Report prioritized, evidence-based findings. Do not modify files unless the user also asks for changes.

For a substantial design, redesign, or full-page review, read [references/principles.md](references/principles.md) before acting. For a small isolated edit, use the workflow below directly.

## Work in Leverage Order

1. **Function and content**
   - Identify the user's main job, the smallest useful feature, the primary action, required information, and important states.
   - Do not invent features merely to make a mockup look complete.
   - When the direction is uncertain, explore structure at low fidelity. Grayscale is useful when color would hide weak hierarchy.

2. **Hierarchy**
   - Rank information and actions as primary, secondary, or tertiary.
   - Make importance visible through a coordinated mix of weight, contrast, size, position, and spacing.
   - Reduce competition before adding emphasis. A page usually needs one visually dominant action.
   - Keep semantic markup and visual styling separate: choose HTML for meaning and style it for the intended hierarchy.

3. **Layout and spacing**
   - Reuse existing tokens. If none exist, choose a small non-linear spacing and sizing scale instead of accumulating one-off values.
   - Give content the width it needs; do not stretch controls, forms, prose, or sidebars merely to fill the viewport.
   - Make within-group spacing smaller than between-group spacing.
   - Let large elements compress more aggressively than small elements across breakpoints. Do not scale every property proportionally.

4. **Typography**
   - Reuse the project's type scale or establish a constrained one.
   - Prefer readable text and hierarchy through weight and contrast before introducing extra sizes.
   - Constrain prose measure, adjust line-height to size and line length, and align mixed-size text by baseline where appropriate.

5. **Color**
   - Reuse or define purpose-driven palette roles: neutrals, brand/primary, and semantic accents.
   - Create deliberate shade steps; do not generate near-duplicate colors ad hoc.
   - Validate contrast in context. Never make color the sole carrier of status or meaning.

6. **Depth and separation**
   - Use spacing, background shifts, borders, overlap, and shadows according to the relationship being communicated.
   - Treat shadows as an elevation system, not decoration. Higher layers may use broader, softer shadows; pressed states should feel closer to the surface.
   - Prefer the quietest separator that still makes grouping clear.

7. **Images and finishing states**
   - Use assets at an appropriate source size and preserve important detail.
   - Guarantee text contrast over variable imagery with a crop, overlay, contrast treatment, or separate text surface.
   - Design loading, empty, error, disabled, selected, hover, focus, and destructive-confirmation states in proportion to the feature.

## Implementation Rules

- Prefer the project's existing components and tokens. Extend them only when the current system cannot express a recurring need.
- Keep changes proportional to the request. A visual refinement does not authorize a framework migration or information-architecture rewrite.
- Use real or representative content when possible; test long labels, missing values, dense data, and user-supplied media.
- Preserve keyboard access, visible focus, semantic structure, and applicable contrast requirements.
- Make dense layouts intentionally dense. Do not add whitespace that reduces task efficiency without improving comprehension.
- Avoid ornamental polish until hierarchy, grouping, alignment, and responsive behavior are sound.

## Verify

- Inspect the result at the actual target viewport sizes, including at least one narrow and one wide layout when responsive behavior is in scope.
- Confirm the eye lands on the intended primary information and action.
- Confirm related items group clearly, interactive states remain discoverable, text is readable, and no content clips or overflows.
- When a runnable interface and rendering tool are available, render the affected states and inspect screenshots; do not treat code inspection alone as visual verification.
- If rendered verification is unavailable, state that verification was code-only and identify the unverified viewports or states.
- Report the important design decisions and any deliberate tradeoffs; do not list every token-level change.
