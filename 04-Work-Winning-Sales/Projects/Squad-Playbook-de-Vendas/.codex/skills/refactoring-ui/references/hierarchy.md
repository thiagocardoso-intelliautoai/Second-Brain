# Hierarchy

Visual hierarchy is the deliberate ordering of which elements get attention and which fade into the background. It is the single biggest factor in whether a UI looks "designed" rather than amateur — more than typography, more than color, more than spacing. When you fix nothing else but the hierarchy, the same content with the same fonts and colors suddenly stops feeling like noise.

The most common mental trap is treating UI design as decoration — picking pretty colors and styling things to "look good." Hierarchy isn't decoration. It's a structural decision about *relationships of importance* between elements. Everything on a screen lives somewhere in a pyramid: one dominant element, a few secondary ones, the rest as supporting context. Identify that pyramid before styling anything — once you know which thing is the main thing, most styling decisions become obvious.

When a UI feels off and you can't say why, the diagnosis is almost always *too many things are shouting*. The fix is rarely to make the important thing louder; it's to make the unimportant things quieter.

## Not all elements are equal

**Intuition:** When every element uses the same visual weight, the user can't parse what matters most. The screen reads as a flat wall.

**Rule:** Deliberately de-emphasize secondary and tertiary information instead of trying to amplify the primary thing.

**Defaults:** Three contrast levels carry most of the work — dark for primary, medium grey for secondary, light grey for tertiary.

```html
<p class="text-slate-900">Primary content</p>
<p class="text-slate-600">Secondary content</p>
<p class="text-slate-400">Tertiary content (footnote, timestamp, copyright)</p>
```

## Size isn't everything

**Intuition:** Relying only on `font-size` for hierarchy produces headlines that are obnoxiously large and captions that are illegibly small. Font weight and color give you two more axes that don't pay the readability tax.

**Rule:** Use weight and color before reaching for size. Two weights is usually enough across an entire UI.

**Defaults:** Normal weight `400` or `500` for body text; heavier `600` or `700` for emphasis. Avoid weights below 400 in UI — they're hard to read at body sizes. To de-emphasize, use a lighter color or smaller size, not a thinner weight.

```html
<!-- Same size, weight + color carry the hierarchy -->
<h3 class="text-base font-semibold text-slate-900">Project Atlas</h3>
<p class="text-base font-normal text-slate-500">Updated 2 hours ago</p>
```

## Don't use grey text on colored backgrounds

**Intuition:** Grey-on-white works because the effect is *reduced contrast*, not greyness itself. On a colored background, grey just looks dirty. The reflexive fix — white text with reduced opacity (`text-white/60`) — looks washed out and, over images, lets the background bleed through the letterforms.

**Rule:** Hand-pick a new color in the **same hue family** as the background, adjusting saturation and lightness until contrast is reduced cleanly.

```html
<!-- Murky and bleeds over images -->
<div class="bg-blue-700 text-white/60">Subtle text</div>

<!-- Better: tinted in the same hue family -->
<div class="bg-blue-700 text-blue-200">Subtle text</div>
```

## Emphasize by de-emphasizing

**Intuition:** When the primary element refuses to stand out, your instinct is to keep amplifying it — bigger, bolder, more saturated. Past a point this just makes the screen heavier without solving the problem.

**Rule:** Stop styling the target element up. Style its competitors *down*. Soften adjacent backgrounds, fade inactive items, drop unnecessary container chrome.

```html
<!-- Active link doesn't pop? Don't bold it more — fade the inactive ones -->
<nav class="flex gap-6">
  <a class="font-medium text-slate-900">Dashboard</a>
  <a class="text-slate-400 hover:text-slate-600">Reports</a>
  <a class="text-slate-400 hover:text-slate-600">Settings</a>
</nav>
```

Same trick at larger scales: if a sidebar is competing with the main content, *remove* the sidebar's background color so it sits on the page background, instead of darkening the main area.

## Labels are a last resort

**Intuition:** The naive `Label: Value` format gives both halves equal visual weight, doubling the visual elements without doubling the information. When the format or context already communicates what the data is, the label is dead weight.

**Rule:** First try to drop the label. If you can't, fold it into the value. Only fall back to a separate label when both fail — and treat it as secondary content.

The format itself often tells the user what something is:
- `jane@acme.com` is obviously an email
- `(555) 765-4321` is obviously a phone number
- `$19.99` is obviously a price
- "Customer Support" listed under someone's name is obviously their department

When you can't drop the label, **fold it into the value**:

```html
<!-- Label as separate element -->
<div>Bedrooms: 3</div>
<div>In stock: 12</div>

<!-- Label folded into the value -->
<div>3 bedrooms</div>
<div>12 left in stock</div>
```

When you genuinely need a discrete label (e.g. a dense dashboard or scannable specs), de-emphasize it as supporting content — small, uppercase, low-contrast — and let the data dominate:

```html
<div>
  <p class="text-xs font-semibold uppercase tracking-wide text-slate-500">Status</p>
  <p class="mt-1 text-base text-slate-900">Approved</p>
</div>
```

**Exception:** when users are scanning *for the label* — like a product spec sheet where they're hunting for "depth" rather than "7.6mm" — emphasize the label, not the value.

## Separate visual hierarchy from document hierarchy

**Intuition:** Browsers ship `<h1>` at 32px and `<h6>` at ~10px, which trains developers to assume semantic headings must be visually large. They don't have to be. Section titles often act more like *labels* for the content beneath them — supporting elements, not focal ones.

**Rule:** Pick HTML tags for semantics (accessibility, SEO, document outline). Pick visual styles independently, based on what hierarchy the screen actually needs. The two axes are decoupled.

```html
<!-- Semantic h2, but styled as a small section label -->
<h2 class="text-xs font-semibold uppercase tracking-wider text-slate-500">
  Manage Account
</h2>
```

Taken to the extreme, you can include a heading in markup purely for screen readers and hide it visually:

```html
<h2 class="sr-only">Recent activity</h2>
```

## Balance weight and contrast

**Intuition:** Bold text covers more pixels than regular text in the same space — it has structural "weight." Icons, especially solid ones, work the same way: an icon next to a word will steal attention even when the word is the more important element. You can't change a solid icon's weight, so you balance it through contrast.

**Rule:** Two complementary moves:
- To make a *heavy* element feel lighter, **reduce its contrast** (give the icon a softer color than the text next to it).
- To make a *low-contrast* element feel noticeable without darkening it, **increase its weight** (a 2px soft border instead of 1px).

```html
<!-- Icon de-emphasized via softer color so the text leads -->
<div class="flex items-center gap-2">
  <svg class="h-4 w-4 text-slate-400" viewBox="0 0 20 20" fill="currentColor">
    <path d="M10 2a8 8 0 100 16 8 8 0 000-16zM9 9V5h2v4h4v2h-4v4H9v-4H5V9h4z"/>
  </svg>
  <span class="font-medium text-slate-900">Add new project</span>
</div>
```

## Semantics are secondary (for buttons)

**Intuition:** Styling buttons by semantic meaning ("destructive actions are big and red") destroys page hierarchy when the destructive action isn't the primary task. A red "Delete account" sitting next to a grey "Save changes" wins attention it doesn't deserve, and the user's eyes go to the wrong place.

**Rule:** Style every button by its position in the *page's* hierarchy, not by what the action does. Each screen has at most one true primary action.

**Defaults:**
- **Primary** — solid filled, high-contrast background. Exactly one per screen.
- **Secondary** — outline, or filled with a much softer background.
- **Tertiary** — styled as a text link (no border, no fill).

```html
<!-- On a settings page where saving is the main action -->
<button class="rounded-md bg-indigo-600 px-4 py-2 font-medium text-white">
  Save changes  <!-- primary -->
</button>
<button class="rounded-md border border-slate-300 px-4 py-2 font-medium text-slate-700">
  Cancel  <!-- secondary -->
</button>
<button class="px-4 py-2 font-medium text-slate-500 hover:text-rose-600">
  Delete account  <!-- destructive but tertiary on this page -->
</button>
```

The big-red-bold treatment for "Delete account" belongs on the **confirmation dialog** that opens after the user clicks the tertiary version — because *there*, deletion is the primary action.

## Quick diagnosis

When something feels wrong but you can't name it:

| Symptom | Principle that fixes it |
|---|---|
| Screen reads as a flat wall of content | Not all elements are equal — de-emphasize secondary info |
| Headlines are obnoxiously large, captions illegibly small | Size isn't everything — use weight and color instead |
| Subtle text looks muddy on a colored background | Don't use grey on colored backgrounds — tint within the hue |
| The active state still doesn't pop | Emphasize by de-emphasizing — fade the inactive items |
| Data lists feel cluttered with `Label: Value` repetition | Labels are a last resort — drop, fold, or de-emphasize |
| `<h2>` headings dominate the content beneath them | Separate visual from document hierarchy — style independent of tag |
| An icon overpowers the text it sits next to | Balance weight and contrast — soften the icon's color |
| A destructive button is winning the page's attention | Semantics are secondary — style by hierarchy, not action type |
