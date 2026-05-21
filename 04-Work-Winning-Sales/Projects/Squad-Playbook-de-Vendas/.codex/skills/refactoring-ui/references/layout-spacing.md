# Layout & Spacing

Most "this UI looks cramped" or "this form looks confusing" problems are spacing problems. The good news: spacing is the most mechanical part of design — once you have a system, the decisions are almost free.

## Start with too much white space

When you build something and add spacing only when things actively look broken, you end up with a UI where every element has the *minimum* breathing room. Looking at one element in isolation, that feels right. In aggregate, the whole screen feels tight and busy.

The reverse approach works better: **start with way too much spacing, then remove until you're happy.** What feels like "a bit much" on an isolated element usually feels like "just right" on a full screen.

Dense UIs do have their place — dashboards, financial tools, anything that genuinely needs lots of data on one screen. But density should be a **deliberate choice**, not the default.

## Establish a spacing & sizing system

Don't agonize over whether a margin should be 16px or 18px. Pick from a fixed scale up front. A linear "everything is a multiple of 4" scale isn't enough — at small sizes, +4px is a 33% jump (huge); at large sizes, +4px is barely visible (useless).

A practical scale ramps geometrically — adjacent values should differ by **roughly 25% or more**.

**How to build one from scratch:** start with a sensible base value (16px is a great default — it divides nicely and matches the browser's default font size), then build the scale using factors and multiples of that base. Tight increments at the small end (where 4px is meaningful), wider gaps at the large end (where 4px is invisible).

A solid default (and what Tailwind ships):

```
4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96, 128, 160, 192, 224, 256
```

Notice the spacing of the values themselves: `12 → 16` is a +33% jump, `64 → 80` is +25%, `192 → 224` is +17% (and the values *above* there get progressively closer because at that scale you don't need fine resolution).

Use this scale for **margins, padding, widths, heights** — anywhere you'd otherwise type a pixel value. The same scale works for sizing fixed-width components (a 256px sidebar, a 384px modal).

When working in Tailwind, this means: stick to `p-4`, `p-6`, `p-8`, `p-12`. The moment you reach for `p-[13px]`, ask yourself if you're abandoning the system for a real reason or because you're nudging pixels by feel.

## You don't have to fill the whole screen

Modern displays are 1400–2400px wide. The temptation is to use that whole canvas. Resist. If a form needs 480px to look good, use 480px and let the rest be empty. A login card centered on a vast empty page looks more confident than one stretched across half the screen.

This applies *within* sections too — just because the navbar is full-width doesn't mean every section below has to be. Give each piece of content the width it actually needs.

## Grids are overrated

A 12-column responsive grid is a useful tool, but it's not gospel. Two common mistakes:

**1. Making every width fluid.** A sidebar at 25% gets too wide on big screens (wasting space the main content could use) and too narrow on smaller screens (wrapping text awkwardly). Give the sidebar a **fixed width** (say 256px) optimized for its content, and let the main area flex to fill the rest. Modals, cards, login forms — same idea: fixed `max-width`, then let the screen handle layout around them.

**2. Shrinking elements that have room to breathe.** A login card at 6 columns wide (50%) on desktop and 8 columns (66%) on tablet ends up *wider on tablet* than on desktop, which is silly. Better: give it `max-width: 480px` and let it sit at that width whenever there's space.

The rule: don't shrink an element until you have to. `max-width` + flexible parent is almost always cleaner than column-based responsive widths.

## Relative sizing doesn't scale linearly

Tempting to think: "If desktop body is 18px and headline is 45px (2.5×), I'll just use `2.5em` and it'll scale on mobile too." It won't — when body shrinks to 14px on mobile, your headline becomes 35px, which is too big for a phone screen.

**Large elements need to shrink *faster* than small elements at smaller breakpoints.** A desktop headline at 48px might want to be 24px on mobile (2× smaller); body text at 18px might only drop to 16px (1.1× smaller). The proportional relationship between large and small isn't preserved across breakpoints — and that's fine. Use breakpoint-specific values.

This applies *within* components too. A "small button" isn't just a "big button" zoomed down 50%; it has tighter padding-to-text ratios. Don't define padding as `0.75em`; use breakpoint-specific values for each size.

## Avoid ambiguous spacing

This is the #1 cause of "this form looks confusing" feedback. When elements are grouped by spacing alone (no border, no background), **the space between groups must be larger than the space within a group**.

A form with `<label>` above `<input>`:
- Space between label and its input: small (e.g. `mb-2`)
- Space between one form field and the next: large (e.g. `mb-6`)

If those two spaces are equal, the eye can't tell which label belongs to which input. Same problem with:
- Section headings (need *more* space above than below)
- Bulleted lists where line-height equals bullet-gap (looks like one big paragraph)
- Horizontal lists of metrics where between-item spacing equals within-item spacing

Whenever you're using *only* spacing to group, audit: is the gap between groups visibly bigger than the gap inside groups?

## Putting it together in code

In Tailwind:

```html
<!-- Good: clear spacing hierarchy -->
<form class="space-y-6">
  <div>
    <label class="mb-2 block text-sm font-medium">Email</label>
    <input class="block w-full ..." />
  </div>
  <div>
    <label class="mb-2 block text-sm font-medium">Password</label>
    <input class="block w-full ..." />
  </div>
</form>
```

The `space-y-6` between fields is much larger than `mb-2` within a field. The grouping reads clearly without any borders or backgrounds.
