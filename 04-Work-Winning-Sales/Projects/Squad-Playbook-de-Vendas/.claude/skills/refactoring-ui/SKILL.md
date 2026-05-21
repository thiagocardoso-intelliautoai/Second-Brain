---
name: refactoring-ui
description: Apply Refactoring UI principles (Adam Wathan & Steve Schoger) to make web interfaces look polished and professionally designed. Use this skill any time the user is working on web design, frontend code (HTML, CSS, React, Vue, Tailwind, etc.), UI components, dashboards, landing pages, or visual artifacts that have a UI — whether they're building from scratch, editing existing code, asking for a critique, or just asking "how do I make this look better?". Trigger even when the user doesn't explicitly mention "design" — if they're touching UI code or screens, these principles apply. This skill complements `frontend-design` (which is about bold creative direction); use both together when relevant. Skip only for pure backend/infra work, terminal tools with no UI, or strictly logo/print/illustration work.
---

# Refactoring UI

This skill captures the design methodology from *Refactoring UI* by Adam Wathan and Steve Schoger. Its job is to help build interfaces that **look designed**, not just functional — using systematic decisions instead of guesswork.

The core insight of the book: most "this UI looks bad and I don't know why" problems come from a small set of recurring mistakes (weak hierarchy, no spacing system, unconstrained color, naive use of grids, ignored depth cues). Once you know the patterns, fixing them is mechanical.

## When to actually open the references

The body of this skill is a checklist + decision framework. The references in `references/` go deeper. **Don't read them all upfront** — you'd burn context for nothing. Open a reference when:

- You're stuck on a specific category of decision (e.g. "what shadows should this card use?" → open `depth.md`)
- The user is asking *why* something looks off and you want to give them the precise principle
- You're doing a thorough audit/critique and want to be exhaustive

For most UI tasks, the checklist below is enough.

## The mindset shift

Before any specific rule, internalize this: **good UI design is mostly about hierarchy, systems, and restraint** — not about being clever or artistic. A boring, systematic interface beats a creative inconsistent one almost every time.

Three meta-principles run through everything:

1. **Design with constraints.** Pick limited sets of values up front (a type scale, a spacing scale, a color palette with fixed shades, a shadow elevation system) and then *only* pick from those sets. Unconstrained design produces inconsistent design and slows you down.

2. **Hierarchy is everything.** When a UI feels noisy or unclear, it's almost always because too many elements are competing for attention. The fix is rarely "add more emphasis to the important thing" — it's usually "de-emphasize everything else." Make some things small, some things grey, some things out of the way. Then the important thing stands out automatically.

3. **The shell comes last.** When designing a new screen, start from the actual feature/content, not the navigation/layout/branding. The chrome should serve the content, not the other way around.

## The Refactoring UI checklist

Run through this checklist when building or reviewing a UI. Each item points to a deeper reference if you need it.

### Starting a new design → see `references/starting-from-scratch.md`

- [ ] Are you designing a *feature*, not a *layout*? Build the actual functionality first; let the shell emerge after you've designed a few features.
- [ ] Are you working in greyscale first? Add color only after the structure works without it.
- [ ] Are you avoiding low-level details (exact fonts, shadows, icons) until the layout is settled?
- [ ] Have you decided on a *personality* (font choice, color temperature, border-radius style, copy tone) and committed to it consistently?
- [ ] Are you working in cycles (design small → build → iterate) rather than trying to design everything upfront?

### Hierarchy → see `references/hierarchy.md`

- [ ] Is there exactly **one** primary action per screen? Secondary actions should look secondary (outline/subdued), tertiary actions should look like links.
- [ ] Are you over-relying on font *size* for hierarchy? Try font *weight* and *color* instead. A bold 16px heading beats a thin 32px one.
- [ ] Are secondary labels styled as labels (small, low-contrast) and the actual data as the focus? `Subscribers: 1,247` should be `1,247 subscribers` or have the label de-emphasized.
- [ ] Are you using grey text on a colored background? Don't — pick a hand-tuned color in the same hue family instead.
- [ ] If the active nav item doesn't pop, are you trying to *de-emphasize the inactive ones* rather than further emphasizing the active one?
- [ ] Don't let HTML semantics drive visual size. An `<h1>` titled "Manage Account" probably shouldn't be 48px.

### Layout & spacing → see `references/layout-spacing.md`

- [ ] Is there a defined spacing scale in use (e.g. 4, 8, 12, 16, 24, 32, 48, 64, 96…)? Never pick spacing values arbitrarily. **Tailwind's default spacing scale already does this** — use it.
- [ ] Start with **too much** white space, then remove. Cramped UIs almost always need more breathing room than feels right.
- [ ] Don't fill the screen just because you have width. A 600px column on a 1400px screen is fine.
- [ ] **Fixed widths beat percentages** for things like sidebars, cards, modals. Use `max-width` to cap, then let the screen handle the rest.
- [ ] When elements are visually grouped by spacing alone (no border/background), the **space between groups must be larger than space within groups**. This is the #1 cause of "this form looks confusing."
- [ ] Don't size everything with `em`/relative units expecting it to "scale together" — large elements need to shrink *faster* than small ones at smaller breakpoints.

### Typography → see `references/typography.md`

- [ ] Is there a defined type scale (e.g. 12, 14, 16, 18, 20, 24, 30, 36, 48, 60, 72)? Don't use arbitrary `px` values.
- [ ] For body paragraphs, line length is **45–75 characters** (≈ `max-w-prose` in Tailwind, or 20–35em).
- [ ] Line-height and font size are **inversely** proportional: ~1.5–1.7 for body text, ~1.1–1.2 for big headlines.
- [ ] Mixed-size text on the same line (e.g. price + currency) → align by **baseline**, not center.
- [ ] All-caps labels need **extra letter-spacing** (`tracking-wide`). Headlines often look better with **slightly negative** letter-spacing (`tracking-tight`).
- [ ] Right-align numbers in tables. Left-align long-form text.
- [ ] Pick fonts with 5+ weights available (signal of a well-crafted typeface). Avoid font weights below 400 for UI text.
- [ ] Not every link needs a color. In dense UIs, font-weight or hover-only color is often enough.

### Color → see `references/color.md`

- [ ] Use **HSL** (or OKLCH) when picking/manipulating colors, not hex. Hex makes related colors look unrelated in code.
- [ ] You need ~**8–10 shades** of grey, ~**5–10 shades** of each primary, plus accent colors (success, warning, danger, info) — also with multiple shades each. Five hex codes are not a palette.
- [ ] Define every shade *up front*. Don't generate them on the fly with `lighten()`/`darken()`.
- [ ] When making a color lighter, **bump saturation** to compensate (and consider rotating hue toward yellow/cyan/magenta). Pure HSL lightness changes look washed out near the extremes.
- [ ] **Greys can be saturated.** A blue-tinted grey feels cool, a yellow-tinted grey feels warm. True 0% saturation grey often looks lifeless.
- [ ] WCAG: 4.5:1 contrast for body text, 3:1 for large text. White-on-color often needs darker color than you'd expect.
- [ ] Never rely on color *alone* to convey state — pair with icons, text, or contrast for color-blind users.

### Depth → see `references/depth.md`

- [ ] Light comes from **above**. Raised elements: lighter top edge, darker shadow below. Inset elements: darker top edge, lighter bottom edge.
- [ ] Use a defined **elevation system** of ~5 shadow sizes. Map them to z-axis meaning: subtle for buttons, medium for dropdowns, large for modals.
- [ ] Use **two-layer shadows** for realism: a larger soft shadow (direct light) + a smaller darker shadow (ambient occlusion). The smaller shadow fades at higher elevations.
- [ ] In flat designs: lighter elements feel closer, darker elements feel further. Color difference alone can imply depth.
- [ ] **Overlap elements** to create layering — a card crossing a section boundary, an avatar overlapping a card edge.

### Images → see `references/images.md`

- [ ] Are you using real, high-quality images? Bad/placeholder photos ruin otherwise-great designs.
- [ ] Text over a photo? Reduce photo dynamics: dark/light overlay, lower contrast, colorize, or text-shadow as a glow.
- [ ] Crop user-uploaded images into fixed-aspect containers (`object-cover`). Don't let them wreck your layout.
- [ ] Icons designed for one size don't scale to another. Use icons at their intended size; redraw or swap if you need very large or very small.
- [ ] If user-uploaded image background might match your UI background, use a subtle inner shadow or semi-transparent inner border instead of a hard border.

### Finishing touches → see `references/finishing-touches.md`

- [ ] Replace generic bullets with relevant icons. Style blockquotes/testimonials. Custom-style checkboxes/radios with brand color.
- [ ] **Accent borders** (a colored top stripe on a card, a colored left bar on an alert, a colored underline on a heading) add a lot of polish for almost no work.
- [ ] Backgrounds don't have to be flat — try subtle gradients (hues within ~30° of each other), repeating patterns, or a single decorative shape/illustration.
- [ ] **Empty states matter.** Don't ship "No items." Use an illustration + a clear next-step CTA.
- [ ] Try removing borders. Replace with: a slightly different background color, a soft shadow, or just more spacing. UIs almost always have too many borders.
- [ ] Question component-shape conventions. A dropdown can be multi-column. A radio group can be selectable cards. A table column can combine related fields.

## Special cases

### When you're working in Tailwind

Tailwind's defaults (`spacing`, `text-*`, `gray-50` through `gray-950`, `shadow-sm/md/lg/xl/2xl`) already implement most of these systems. The right move with Tailwind is almost always: **stick to the default scale**. Reaching for arbitrary values (`p-[13px]`, `text-[#3a4f6c]`) is a yellow flag that you're abandoning the system.

### When you're auditing/critiquing an existing UI

Walk the checklist in this order — fixing earlier items often makes later items moot:
1. **Hierarchy** first (is the wrong thing dominant?)
2. **Spacing** second (is everything cramped, or is grouping ambiguous?)
3. **Type scale & color system** third (are values arbitrary?)
4. **Depth & finishing** last (polish only matters once the bones are right)

When delivering critique, frame it as principles + concrete fix, not just "this looks bad." E.g. *"Your secondary buttons are competing with your primary CTA — give them an outline style instead of a filled background, and the primary action will pop without changing it at all."*

### When the user wants something distinctive/bold

Pair this skill with `frontend-design`. *Refactoring UI* is about systematic craft (the rules); `frontend-design` is about creative direction (the personality). A great UI usually needs both — strong personality executed with disciplined craft.

## How to apply this in code

When generating or editing UI code:

1. **State the system before writing the values.** Decide the spacing scale, type scale, and color palette first (or confirm what's already in the codebase). Then implement against that.
2. **Use design tokens / CSS variables / Tailwind config** so the system is referenceable. Avoid magic numbers in the markup itself.
3. **Comment your hierarchy intent** when it's non-obvious. `<!-- secondary action: outlined, lower contrast -->` makes future edits stay on-system.
4. **When in doubt, look at the checklist above.** Most "I don't know why this looks off" moments map to one of those bullets.

The principles here are tools for thinking, not laws. Break them deliberately when you have a reason — but break them rarely.
