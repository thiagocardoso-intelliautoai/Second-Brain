# Starting from Scratch

How you *begin* a new design has outsized effect on the result. Most people start with the wrong question and get stuck in the wrong place. This reference is about the workflow, not the visual rules.

## Start with a feature, not a layout

The single most common way to get stuck on a new design is to start by "designing the app" — the navigation bar, the logo position, the sidebar vs topbar, the container width.

The problem: an "app" is a collection of features. Until you've designed a few features, you literally don't have the information needed to make good shell-level decisions. How can you decide whether to use a sidebar before you know what's *in* the app?

**Start with a single feature.** For a flight booking tool, that's "search for a flight" — the form fields, the results display. Design that first, by itself, with no app shell around it. Once that exists, design the next feature. After three or four features, the structure of the app becomes obvious — you can tell whether you need a sidebar or a topbar because you can see what items would go in it.

Many of the cleanest apps in the world (Google search, Stripe Checkout) barely have an app shell at all. The feature is the app.

## Detail comes later

Early in a design, don't agonize over typefaces, exact shadow values, icon sets, or color choices. Those details matter eventually, but they don't matter at the layout-discovery stage. Working in **low-fidelity** keeps your attention on the right level.

A trick from Jason Fried (Basecamp): sketch with a thick Sharpie. You physically can't obsess over fine details with a Sharpie, so you're forced to think structurally.

In code, the equivalent is starting with **unstyled HTML or grayscale Tailwind**. No colors yet, no fonts, no shadows. Just the structure and the spacing. If the layout looks good in greyscale, color will only make it better. If it doesn't, no amount of color will save it.

## Hold the color (until later)

Designing in greyscale forces you to use **spacing, contrast, and size** to create hierarchy — which is what hierarchy *should* be built from anyway. Color added later is decoration on top of an already-clear structure. Color added too early ends up doing all the heavy lifting because the underlying hierarchy is weak, and you'll struggle to introduce color *changes* later because everything depends on the existing palette.

Practical move: build the first version of any new screen entirely with `gray-50` through `gray-900`. Add brand color last, sparingly, where it actually conveys meaning (primary action, active state, brand identity).

## Don't over-invest in mockups

Static mockups (Figma, Sketch, paper) are *exploration tools*. They help you decide. Once decided, ship them — don't polish them. Users can't do anything with a mockup, and every hour spent perfecting one in design tools is an hour not spent learning what doesn't work in the real interface.

A working real interface (even an ugly one) teaches you more in 5 minutes of using it than a beautiful mockup teaches you in a week of staring at it.

## Don't design too much (in advance)

Trying to design every screen and every edge case before any of it ships is a trap. You'll burn out trying to imagine "what if the user has 2000 contacts?" or "what if two calendar events overlap?" using only your imagination — these are fundamentally hard to reason about abstractly.

**Work in cycles.** Design a small piece, build it, use it, find what's broken, fix it, then design the next piece. Real interfaces reveal problems that imaginary ones don't.

This applies to AI-assisted code generation specifically: don't try to one-shot an entire complex UI. Build a single screen well, evaluate it, then move to the next. Each iteration informs the next better than any upfront plan would.

## Be a pessimist (don't imply functionality you can't ship)

When you're sketching a feature, don't include UI for things you might not actually build.

The classic example: you're designing a comment system, and you know users *might eventually* want to attach files to comments, so you include an attachments button in the design. Then implementation hits — attachments turn out to be much more work than expected. Now the whole comment feature stalls because you committed to attachments by including them in the design.

A comment system without attachments would have been better than no comment system at all. **Design the smallest version that's actually useful**, ship that, then add the rest later if it earns its place.

In practice: each piece of UI in your mockup is a commitment. Make sure every commitment is one you're prepared to fulfill.

## Choose a personality

A design's "personality" feels abstract but is actually controlled by a few concrete decisions:

**Font choice.** Serif feels classic / editorial / formal. Rounded sans-serif feels playful / friendly. Neutral sans-serif (Inter, Helvetica, system) feels professional / safe.

**Color.** Blue feels safe, trustworthy, corporate (banking, social, SaaS — there's a reason). Gold/amber feels expensive, sophisticated. Pink/magenta feels fun, modern. Saturated greens feel fresh, organic. Black-and-white with accent feels luxurious, editorial.

**Border radius.** Small radius (~4px) is neutral. Large radius (~16px+) feels playful, soft. No radius (sharp corners) feels formal, serious, brutalist.

**Language.** "Submit your application" vs "Let's get started" vs "Ship it 🚀" — the words you use affect personality as much as visuals do. Pick a tone and use it consistently.

**Decide the personality before you design.** Look at sites used by your audience: are they "serious business" sites? Then yours probably should be too. Are they playful and casual? Match that. Don't borrow directly from competitors (you'll look like a discount version), but observe the *category's* visual language.

## Limit your choices (the meta-principle)

This is the throughline of every chapter in the book and worth restating: **unconstrained design is harder, slower, and worse than constrained design.**

When the choice is between any of 16 million colors, any of 100+ pixel sizes, any of 1000+ fonts, decision-making becomes torture and consistency becomes accidental. When the choice is between 8 shades of one color, 12 type-scale sizes, and 3 fonts, decisions are fast and consistency is automatic.

Define systems for:
- Font sizes (a fixed type scale)
- Font weights (usually 2-3 weights)
- Line-heights (a small set, e.g. 1, 1.25, 1.5, 1.75)
- Colors and shades (8-10 shades per color family)
- Spacing and sizing (a geometric scale)
- Border-radius values (a few options: none, small, medium, large, full)
- Box-shadow elevations (~5 levels)
- Border widths (1px, 2px, maybe 4px for accents)
- Opacity values (a few levels)

You don't need to define all of this on day one — but adopt a systems mindset from the start. Whenever you find yourself pixel-tweaking the same kind of decision twice, that's the moment to introduce a system for it.

Tailwind already provides excellent defaults for almost all of these. The discipline isn't "design a custom system" — it's "stick to whatever system exists rather than reaching for arbitrary values."

## Designing by elimination

When you do have to pick from a constrained set, the easiest method is process of elimination:

1. Take a guess at the right value
2. Try the values immediately above and below it
3. Two of the three usually look obviously wrong; the remaining one is your answer
4. If your initial guess was on an edge, slide your "window" over and try again

This is dramatically faster than picking by feel from infinite options, because the differences between adjacent system values are big enough to *see* clearly. With unconstrained values, you can spend 20 minutes deciding between 14px and 15px because neither is obviously right or wrong.
