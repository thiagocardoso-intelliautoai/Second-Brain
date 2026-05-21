# Finishing Touches

Once the bones of a UI are right (hierarchy, spacing, type, color, depth), there's a category of small moves that take it from "fine" to "polished." These are cheap to do and disproportionately effective. They're also where most "AI-generated" looking UIs fall short — the structural decisions are okay, but the polish is missing.

## Supercharge the defaults

Default HTML elements are functional but generic. A handful of small upgrades transform them:

**Bullets → relevant icons.** A `<ul>` with default bullets is fine. The same list with checkmarks (for features), padlock icons (for security points), arrow icons (for steps) instantly looks more "designed."

**Quotes → visual elements.** Don't just put a testimonial in italics. Make the opening quote mark large, colorful, and decorative. Put the quote in a card with the photo and name aligned thoughtfully. A testimonial section is high-attention — it deserves more than `<blockquote>`.

**Links → real styling decisions.** In paragraph prose, a thick semi-transparent custom underline that overlaps the text descenders looks dramatically more crafted than the browser default.

**Checkboxes / radios → branded controls.** Default form controls look like Windows 95. Even a minimal restyle — your brand color for the selected state, a slightly different shape, custom focus ring — turns "form" into "designed form."

The pattern: any time you're using an HTML element with its browser-default appearance, ask if a small custom touch would help.

## Add color with accent borders

If you don't have great photography or illustrations, the cheapest visual flair you can add is **a stripe of solid color**. It works almost everywhere:

- A 4px colored bar across the top of a card
- A 4px colored bar on the left edge of an alert message (where the color also encodes severity)
- A short colored underline beneath a section heading
- A colored top stripe across the entire page (e.g. the iconic Stripe-blue bar at the top of stripe.com landing pages)
- A colored line/bar marking the active item in a sidebar nav

These take 5 seconds to add and make a generic UI feel branded. Don't underestimate them.

## Decorate your backgrounds

Solid white/grey backgrounds are safe but flat. A few cheap upgrades:

**Tinted background sections.** Alternate page sections between white and a very light grey/colored tint. Helps separate sections without adding borders or shadows.

**Subtle gradients.** A diagonal gradient between two close hues (within ~30° on the color wheel) feels more energetic than a flat color. Keep it subtle — high-contrast gradients look dated.

**Repeating patterns.** Sites like Hero Patterns offer SVG patterns that tile cleanly. Use them at very low contrast (the pattern color should be barely visible against the background) so they add texture without competing with content.

**Single decorative shapes.** A simple geometric shape (a circle, a blob, an angled line) positioned in a hero area or behind a content block. Or a small repeating pattern applied just to a corner. Or a faded world map / topographic line behind a stats section.

The unifying rule: decoration sits *behind* content and never competes with it. If you can't read the content as easily as on a flat background, the decoration is too loud.

## Empty states matter

The empty state is often a user's *first* interaction with a feature. "No items yet." with no styling is a wasted opportunity — and worse, it makes the feature feel broken.

A good empty state has:

1. **A focal element** — an illustration, icon, or graphic that gives the screen something to anchor on
2. **A clear, friendly message** explaining what *will* be here
3. **An obvious next action** — a primary button to create the first item, import data, or whatever the next step is
4. **Hidden secondary UI** — if the feature has tabs, filters, sort controls, etc., hide them in the empty state. There's nothing to filter yet, so don't show filters.

Examples of where empty states get neglected: empty inboxes, empty search results, empty dashboards before data syncs, freshly-created projects with no tasks. All of these deserve real design attention.

## Use fewer borders

Borders are the easiest separator to reach for, which is why UIs end up over-bordered. Every border adds visual noise. Many UIs would look cleaner with most borders removed.

When you're tempted to add a border, try one of these alternatives instead:

**1. A different background color.** Two adjacent panels with slightly different backgrounds read as separate without a border. (Bonus: this also gives you a depth cue — see `depth.md`.)

**2. A soft box-shadow.** A subtle shadow outlines an element more gently than a hard border, especially when the element sits on a different-colored background.

**3. More space.** The simplest separator is just more space between elements. If two groups are 64px apart, the eye reads them as separate without any drawn divider.

**The audit:** look at any border in your UI and ask "what would happen if I just deleted it?" Often, nothing — the design just gets quieter.

When you do need a border, prefer **soft, low-contrast** borders (e.g. `border-gray-200`) over hard dark ones. Soft borders separate without shouting.

## Think outside the box

Some component shapes are conventional but not required. Most "this UI looks generic" feedback is really about defaulting to the most expected version of every component.

**Dropdowns** — don't have to be plain vertical lists of links. They can have multiple columns, sectioned content, icons, supporting descriptions, headers, footer actions. A dropdown is just "a floating panel" — anything you'd put in a panel can go in there.

**Tables** — don't need one column per data field. Combine related fields into richer cells (an "Owner" column showing avatar + name + role together; a "Status" column with a colored dot + label + last-updated date). Add product images. Use color and weight inside cells for hierarchy. The more cells your table has, the *less* uniform they should look.

**Radio buttons** — a stack of small circles next to text labels is the conventional treatment, but if the choice is meaningful, **selectable cards** are dramatically better. Each option becomes a card the user can tap, with room for an icon, description, and price. Same input semantics, much richer presentation.

**Forms in general** — don't need to be vertical lists of `<label>` + `<input>`. Group related fields into cards. Use horizontal layouts for related short fields (city + state + zip). Replace dropdowns with toggle groups when there are 2-4 options. Replace text inputs with sliders for bounded numerical values.

**Buttons** — don't have to be rectangles with text. Icon buttons, split buttons, button groups, segmented controls, FABs, contextual menus all have their place.

The mindset: **for every standard component, ask "what's the version of this that's actually shaped like the data?"** Convention is a starting point, not the finish line.

## Level up: study designs you admire

Two practices that compound over time:

**1. When you see a UI you like, ask: "what did they do here that I wouldn't have thought to do?"** That unexpected decision is usually where the polish came from. Maybe the date picker has its background colors inverted from what you'd expect. Maybe the search button is *inside* the input instead of next to it. Maybe a heading uses two different text colors for emphasis. Collect these moves; they're hard to invent from scratch but trivial to recognize once you've seen them.

**2. Recreate your favorite interfaces from scratch, without peeking at devtools.** When yours doesn't match the original, the diagnostic process — "why does theirs look better?" — teaches you specific tricks that no design book can spoon-feed you. "Tighten line-height for headlines." "Add letter-spacing to caps." "Use two-layer shadows." You learn these by *missing them and noticing*, not by being told.
