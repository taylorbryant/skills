# Interface Design Principles

Use this reference for examples and detailed heuristics during substantial creation, redesign, or visual review. Follow the diagnostic order in [SKILL.md](../SKILL.md) for broad problems; consult the relevant sections for focused requests.

## 1. Start with the Feature

- Sketch enough to choose a direction, then test the idea in the real medium. Static mockups are cheap exploration, not the final proof.
- Work in short design-build-review cycles. Defer optional capability until the simple version works.
- Choose a coherent personality through type, color, corner treatment, imagery, and voice. The choices should reinforce one another and fit the audience without imitating a direct competitor.
- Reduce decision fatigue with explicit systems for type, spacing, color, radius, border, and elevation.

## 2. Build Visual Hierarchy

- Two body-text weights and roughly three text tones are often enough. Avoid thin small text; reduce contrast instead.
- Heavy icons can overpower neighboring text. Lower their contrast or simplify their container to restore balance.
- Avoid repetitive label-value grids when format or context already explains the value. When labels are needed for scanning, decide whether the user searches by label or by value and emphasize accordingly.
- Style actions by contextual importance, not semantics alone. A destructive action can remain quiet until the confirmation step where it becomes the primary decision.
- On a colored surface, derive secondary text from the surface's hue family rather than applying low-opacity white that may look washed out or reveal a patterned background.

## 3. Compose Layout and Spacing

- Begin looser than feels necessary and remove space deliberately. Compactness is valid for data-heavy work, but it should be a choice.
- Reuse the product's spacing scale. If no system exists, a practical starter sequence is `4, 8, 12, 16, 24, 32, 48, 64, 96`; extend it only when repeated needs justify it.
- Adjacent values should differ enough to make choices clear. Small steps can be close together; large steps need bigger jumps.
- Use intrinsic, fixed, minimum, and maximum widths according to content. A fixed sidebar and flexible main region may behave better than forcing both onto a percentage grid.
- Keep components at their useful size until the viewport actually requires compression.
- Scale component properties independently. A small button may need disproportionately tighter padding rather than a uniformly shrunken copy of the large button.

## 4. Design the Text

- Prefer the existing type system. If one is absent, start with a small hand-tuned scale such as `12, 14, 16, 18, 20, 24, 30, 36, 48` and add only demonstrated needs.
- Define font-size tokens in `rem` or `px`, not `em`, so nested elements remain on the intended scale. Relative units such as `em` are still useful for content measure; `20-35em` is a practical starting range for prose.
- Choose a highly legible family for interface text. Verify the required weights and scripts instead of choosing on personality alone.
- Keep paragraph lines around 45-75 characters where practical. Allow images, tables, and code to exceed the prose measure without widening the prose itself.
- Use taller line-height for small text and long lines; tighten large headings. A single line-height ratio should not govern every size.
- Left-align longer passages in left-to-right languages. Center only short, self-contained text; right-align comparable numbers in tables.
- Use link color when needed for discovery inside prose. In link-dense interfaces, weight, underline, position, or hover/focus treatment may create a quieter hierarchy.
- Trust the typeface's tracking by default. Modest tightening can help large headlines, while all-caps labels often benefit from extra letter spacing.

## 5. Construct the Color System

Define colors by role, not by individual component:

- A neutral ramp for text, surfaces, controls, and borders.
- One or two brand ramps for primary actions, selection, and identity.
- Focused accent ramps for semantic states or data categories.

Use enough shades to support real interface states without creating indistinguishable options. Five shades may be sufficient for a narrow accent; a frequently used neutral or primary ramp may need closer to nine.

Choose the useful middle, darkest, and lightest colors in real contexts first, then fill the gaps. Evaluate the resulting ramp visually instead of assuming equal numeric steps produce equal perceived steps. Slightly tinted neutrals can make the interface feel warmer or cooler.

Tune ramps in a color model that makes hue, saturation or chroma, and lightness explicit; HSL is the book's example, but preserve the project's established model when one exists. As shades approach light or dark endpoints, adjust saturation or chroma to prevent them from looking washed out. Small hue shifts toward perceptually brighter or darker hues can preserve intensity, but keep the shifts restrained so every shade still reads as the same color family.

For accessibility and hierarchy:

- Test text and controls against their actual surfaces, including hover, disabled, selected, and image-backed states.
- If white text forces an unhelpfully dominant dark surface, consider dark text on a pale tint instead.
- Pair status color with a concrete non-color cue, such as an error message beside an invalid field or a checkmark and text for completion.
- In charts, vary lightness, line style, marker, or direct labels when hues alone would be ambiguous.

## 6. Create Meaningful Depth

- Maintain one implied light direction. Highlights generally belong on light-facing edges; shadows belong beneath or inside the occluded edge.
- Use a small elevation vocabulary, commonly three to five levels. Map each level to a purpose such as raised control, card, dropdown, and modal.
- A two-part shadow can combine a broad low-opacity cast shadow with a tighter contact shadow. Fade the contact component as elevation increases.
- During drag, lift, or open interactions, increase apparent elevation. During press, reduce it.
- Flat interfaces can still show depth through lighter raised surfaces, darker inset surfaces, solid offset shadows, and controlled overlap.
- When images overlap, add a surface-colored gap or outline so their edges remain legible.

## 7. Handle Images and Edge States

- Source quality is part of the design. Do not plan around temporary images that have different composition, contrast, or aspect ratio from final content.
- Do not enlarge small icons merely because they are vectors; glyph detail and stroke weight were designed for a target size. Place a target-sized icon inside a larger supporting shape when more presence is needed.
- Do not shrink detailed screenshots until their text becomes decorative noise. Crop to the important region or create a simplified illustration of the interface.
- Constrain user-uploaded media with explicit aspect ratios, crop behavior, focal positioning, and fallbacks. Use a subtle inset edge when light images could bleed into the page surface.
- For text on photos, control the image: crop around a stable region, lower local contrast, add an overlay, colorize, or place text on a separate surface. A text shadow is supplemental, not the only contrast strategy.
- Treat empty states as the beginning of the feature. Explain the value, present the next action, and hide controls that cannot yet do anything.
- Prefer separation by spacing or surface change before adding a border. Use borders when they clarify interaction, boundaries, or dense scanning.
- Keep decorative accents lower in contrast than the content they support.

## Report Findings

Report only the highest-value findings the user can act on. Explain the observed problem, its effect on the user, and the smallest coherent correction. Avoid vague judgments such as "make it pop."
