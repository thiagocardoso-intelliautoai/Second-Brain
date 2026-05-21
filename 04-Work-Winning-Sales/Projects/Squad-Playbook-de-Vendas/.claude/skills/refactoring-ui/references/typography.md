# Typography

Typography is doing more work than people realize. Most "this looks unprofessional" problems are typography problems disguised as something else — wrong line length, no type scale, generic font, awkward letter-spacing on caps.

## Establish a type scale

Define a fixed set of font sizes up front and only use those. A linear scale (10, 11, 12, 13, 14...) is too granular at the bottom (12 vs 13 makes no real difference) and too sparse at the top.

A solid hand-crafted scale that works for almost any project:

```
12, 14, 16, 18, 20, 24, 30, 36, 48, 60, 72, 96, 128
```

Tailwind ships this scale by default (`text-xs` through `text-9xl`). Use it.

**Avoid `em` units for the type scale itself.** `em` is relative to the parent's font size, so nesting compounds: a `1.25em` element inside a `1.25em` element renders at 1.5625× — a value that isn't in your scale anymore. Stick to `px` or `rem`.

A modular scale built from a ratio (golden ratio, perfect fifth, etc.) is mathematically tidy but produces fractional pixel values that subpixel-render differently across browsers. Just hand-pick whole numbers.

## Use good fonts

Developing taste in typography takes years. Some shortcuts to reasonable choices:

- **System font stack** — the safest possible choice. `-apple-system, Segoe UI, Roboto, "Noto Sans", Ubuntu, Cantarell, "Helvetica Neue"`. Fast, familiar, and matches platform conventions.
- **Filter by weight count** — fonts shipped with 5+ weights are usually crafted with more care than fonts with just regular and bold. Google Fonts has a "number of styles ≥ 10" filter that cuts ~85% of the catalog.
- **Use fonts at their intended size.** Display fonts (tight letter-spacing, short x-heights) look great in headlines and bad in body text. Text fonts (wider spacing, taller x-heights) look great in paragraphs and a bit boring in headlines.
- **Sort by popularity.** A font that's popular is usually popular for a reason — collective taste is a decent filter when yours is uncalibrated.
- **Steal from sites you admire.** Inspect the CSS. Designers with strong opinions land on great choices you wouldn't have found on your own.

For UI work specifically, a neutral sans-serif almost always works. Distinctive personality usually belongs in headlines or marketing pages, not in dashboards.

## Keep line length in check

Body text is most readable at **45–75 characters per line**. The easiest way to enforce this on the web is `max-width: 65ch` (or roughly `20em` to `35em`).

In Tailwind: `max-w-prose` (~65ch) is the right utility for paragraph blocks.

If your overall content area is wide because it includes images or other large elements, that's fine — but **the paragraphs inside should still be capped**. Looks counterintuitive (mixed widths in the same column), works in practice.

## Baseline, not center

When you mix font sizes on the same line — like a card title with a smaller meta line, or a price with a smaller currency symbol — vertically centering them looks subtly wrong. The fix is to **align by baseline** (the imaginary line letters rest on), which is what your eye already perceives as "lined up."

In CSS this is the default for inline-level elements. With flexbox: `align-items: baseline`.

## Line-height is proportional

The "1.5 is good" advice is too simplistic. Line-height should adapt to two factors:

**Line length** — longer lines need more line-height. Eyes that have to traverse 700px of text need extra vertical signal to find the next line. Wide text columns: line-height up to 2. Narrow columns: 1.5 is plenty.

**Font size** — small text needs more line-height; large text needs less. Body text at 16px looks good at line-height 1.5–1.7. A 60px headline needs line-height 1.0–1.1; anything more and the lines look disconnected.

Inversely proportional: as font size goes up, line-height goes down.

## Not every link needs a color

Blue + underline on every link is a holdover from prose. In a UI where almost every element is clickable, that styling becomes overwhelming.

For high-density UIs:
- **Primary navigation links** — heavier font weight, no underline
- **Body text links** — color shift (or weight shift) inline
- **Tertiary/ancillary links** — no styling at all by default; underline-on-hover only

Save the full "blue underline" treatment for actual paragraph prose where users need to spot a link inside running text.

## Align with readability in mind

For LTR languages, **left-align body text**. Centered or right-aligned long text is hard to read because every line starts at a different position, forcing extra eye-tracking work.

When centering is fine:
- Headlines and short headings (1–2 lines)
- Independent blocks of text (a hero tagline)
- Short marketing copy
- Buttons and labels

When centering is bad:
- Multi-paragraph body text
- List items longer than ~3 lines

If you want to center a block but one piece is too long — **rewrite the content shorter**. That fixes the alignment problem and tightens the copy.

**Right-align numbers in tables.** A column of `1,234.56`, `89.00`, `12,000.00` is much easier to compare when the decimal points line up.

**Justified text** can work for print-style layouts, but on the web it creates ugly inter-word gaps unless you also enable hyphenation (`hyphens: auto`). For most web work, left-aligned is the safer default.

## Letter-spacing

Trust the typeface designer by default. Two common situations where you should tweak:

**Tighten large headlines.** Fonts designed for body text have wide letter-spacing for legibility at small sizes. When you scale that font up to 60px+, the wide spacing looks loose. Tighten with negative `letter-spacing` (e.g. `tracking-tight` in Tailwind: `-0.025em`).

**Loosen all-caps text.** Lowercase letters have visual variety (descenders, ascenders, varying widths). All-caps is uniform — every letter the same height — which makes it harder to read at default spacing. Add letter-spacing to all-caps labels, buttons, and small headings (`tracking-wide` or `tracking-wider`).

```html
<!-- All-caps small label -->
<span class="text-xs font-semibold uppercase tracking-wider text-gray-500">
  Settings
</span>

<!-- Big headline -->
<h1 class="text-6xl font-bold tracking-tight">
  Designing software is hard.
</h1>
```

## Quick mental checklist when typography feels off

1. Is the line length within 45–75 characters?
2. Is the line-height appropriate for the size + width? (small text + wide column → tall line-height; big text → tight line-height)
3. Are mixed-size lines aligned by baseline, not center?
4. Are all-caps elements letter-spaced?
5. Are you using a real type scale, or arbitrary pixel values?
6. Are you over-relying on size to express hierarchy when weight/color would do better? (see `hierarchy.md`)
