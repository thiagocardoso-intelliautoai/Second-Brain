# Color

Color is the part of UI design where teams most often resort to magic — picking values from a Dribbble palette generator and hoping they work. They almost never do. The systematic approach is more boring and dramatically more effective.

## Use HSL (or OKLCH), not hex

Hex codes are great for storage but terrible for thinking. Two colors that are clearly related to your eye (a blue and a slightly darker blue) look like unrelated random strings in hex: `#3b82f6` vs `#1d4ed8`.

**HSL** breaks color into three perceptual axes:

- **Hue (0–360°)** — the color itself (red is 0°, green is 120°, blue is 240°)
- **Saturation (0–100%)** — how vivid (0% is grey, 100% is pure)
- **Lightness (0–100%)** — how close to black (0%) or white (100%)

When picking shades of the same color, you keep the hue locked and adjust saturation/lightness. Code becomes readable: `hsl(220, 90%, 60%)` and `hsl(220, 80%, 30%)` are obviously the same family.

**OKLCH** is even better (perceptually uniform, more consistent lightness across hues) and now has wide browser support — worth using on new projects. Tailwind v4 uses OKLCH internally.

> Watch out: HSL ≠ HSB. HSB's "brightness" behaves differently than HSL's "lightness." Browsers only understand HSL, so for web work, HSL is what you use.

## You need more colors than you think

A 5-color palette generator gives you 5 colors. That's not enough to build anything. A real interface needs:

**Greys (8–10 shades)**
Almost everything in a UI is some shade of grey — text, borders, backgrounds, panels, form controls, dividers. Three or four greys feels like enough until you're three days in and wishing you had something between #3 and #4. Aim for 8–10 from the start.

True black usually looks unnatural; start your darkest grey at something like `hsl(220, 15%, 10%)`, not pure `#000`.

**Primary color(s) (5–10 shades each)**
The brand colors — the ones that define the look of the product. You need ultra-light shades for tinted backgrounds (a faint blue panel for an info alert), mid shades for buttons and links, and very dark shades for text on the brand color or for hover/active states.

**Accent colors (5–10 shades each)**
For semantic states and emphasis:
- **Success** (green) — confirmation, positive trends, "completed"
- **Warning** (amber/yellow) — caution, soon-to-expire, "review needed"
- **Danger** (red) — errors, destructive actions, "delete"
- **Info** (often the same as primary, or a distinct blue) — neutral notifications

Each needs multiple shades — a dark red for error text, a mid red for the destructive button, a pale red for the alert background.

**Categorical colors** (if you have charts, calendars, or tags) — possibly 5–10 more distinct hues.

It's normal for a complex product to ship with **8–10 distinct color families × 5–10 shades each = 50–100 individual colors** in the design system.

The good news: **you only have to pick them once.** And Tailwind already ships excellent defaults for all of this — `gray-50` through `gray-950` for greys, named families like `blue-`, `red-`, `green-`, `amber-` with the same scale.

## Define every shade up front

Tempting to use SCSS `lighten()` / `darken()` and generate shades on the fly. Don't. You'll end up with 35 slightly-different blues that all look almost the same and the codebase becomes impossible to keep consistent.

Pick all the shades **once**, name them (`blue-100`, `blue-200`, ... `blue-900`), and only use those.

A practical process to build a 9-shade scale for a color:

1. **Pick the base** (call it `500`) — usually the shade you'd use for a button background. No formula; trust your eye.
2. **Pick the darkest** (`900`) — what you'd use for dark text in this color family.
3. **Pick the lightest** (`100`) — what you'd use as a subtle tinted background.
4. **Fill the middle** — pick `300` and `700` (the midpoints). Then fill `200`, `400`, `600`, `800` between those. Each step should feel like a clean, balanced compromise between its neighbors.

Same process for greys. Pick the darkest text grey, pick the off-white background, fill in between.

## Don't let lightness kill saturation

In HSL, as a color gets very light (near 100%) or very dark (near 0%), saturation has less perceptual impact — the same saturation value looks "more colorful" at 50% lightness than at 90%.

**Practical consequence:** as you make lighter and darker shades of a color, you need to *increase* saturation to keep the color from looking washed out.

A rough pattern for a primary blue:
- Mid shade (500): saturation ~85%
- Light shade (200): saturation ~95%
- Dark shade (800): saturation ~95%

It's subtle but the difference is real, especially over large background areas.

## Change brightness by rotating hue

Beyond just adjusting lightness, you can change how light a color *feels* by rotating its hue toward a perceptually-bright one. Yellow, cyan, and magenta are perceived as brighter than red, green, and blue at the same HSL lightness.

To make a color **lighter**, rotate the hue toward the nearest of 60° (yellow), 180° (cyan), or 300° (magenta).
To make a color **darker**, rotate toward 0° (red), 120° (green), or 240° (blue).

This is most useful for warm light shades. Lightening a yellow with pure HSL lightness gives you a dull washed-out cream; rotating toward orange as you darken gives you a rich warm scale.

Don't rotate more than ~20–30° or you'll perceive it as a different color, not a shade of the same one.

## Greys don't have to be grey

True 0%-saturation grey often looks lifeless and clinical. Almost all modern UI greys carry **a small amount of saturation** — usually toward blue (cool grey, looks "tech") or toward yellow/orange (warm grey, looks "natural" or "editorial").

A practical default: ~5–15% saturation toward blue (e.g. `hsl(220, 10%, 50%)`) gives you a grey that feels modern and intentional rather than dead.

Match temperature consistently across all shades — don't have warm light greys and cool dark greys in the same palette.

## Accessibility: contrast ratios

WCAG sets minimum contrast ratios:
- **4.5:1** for normal text (under ~18px)
- **3:1** for large text (~24px+ or ~18px+ bold)
- **3:1** for UI components and graphical objects (icons, borders)

For dark-text-on-light-background, this is usually easy. It gets tricky with:

**White text on a colored background.** The colored background often needs to be much darker than feels right to hit 4.5:1 with white text. If that makes the element draw too much attention to itself in the page hierarchy, **flip the contrast** — use dark colored text on a light tinted background instead. The color is still present, but as accent rather than dominant.

**Colored text on a colored background** (e.g. secondary text in a dark-blue panel). Adjusting only saturation/lightness, you'll struggle to hit ratio without going to nearly-pure-white. Try **rotating the hue** toward a perceptually-brighter one (cyan, yellow, magenta) — you can hit ratio while keeping the text colorful and on-brand.

## Don't rely on color alone

Roughly 8% of men and 0.5% of women have some form of color blindness, most often red-green. If a UI uses *only* color to communicate state — green up-arrow / red down-arrow with no other distinction — those users miss the signal.

Always pair color with a second signal:
- ↑ / ↓ icons or `+` / `−` text on metrics
- Different line styles (solid/dashed) on charts, not just different colors
- Text labels ("Approved" / "Rejected") next to color dots
- Variation in **contrast/lightness**, not just hue, when distinguishing categories

Color should *enhance* the signal, never *be* the signal.
