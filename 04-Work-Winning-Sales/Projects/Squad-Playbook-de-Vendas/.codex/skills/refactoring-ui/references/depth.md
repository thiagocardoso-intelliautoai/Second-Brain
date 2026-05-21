# Depth

Depth is what separates UIs that feel like static pictures from UIs that feel like physical surfaces with elements arranged in space. Even completely flat designs can convey depth through color and overlap. The trick is doing it deliberately and systematically.

## Light comes from above

This is the single rule that makes shadows and depth effects look right. In the real world, ambient light comes from the sky — from above. Our brains are wired to interpret edges accordingly:

- An edge that's **lighter on top, darker on bottom** reads as **raised** (like a button or panel sitting above the page)
- An edge that's **darker on top, lighter on bottom** reads as **inset** (like a text input or a recessed well)

Once you internalize this, you can build any "raised" or "inset" effect by mimicking how light would actually hit that shape.

## Building a raised element

For a button you want to feel like it sits above the page:

1. **Top edge slightly lighter than the face.** Use a top border or an inset box shadow with a small positive vertical offset. Don't use semi-transparent white — it desaturates the underlying color. Pick a hand-tuned lighter shade in the same hue.

2. **Below the element: a small dark shadow with a slight positive Y offset.** This is the shadow the raised element casts on the surface below. Don't go crazy with blur radius — a couple of pixels is plenty. Real-world raised elements (the lip of a power outlet, a picture frame) cast crisp short shadows, not soft long ones.

```css
.raised-button {
  background: hsl(220, 80%, 50%);
  border-top: 1px solid hsl(220, 80%, 60%);
  box-shadow: 0 1px 2px hsl(220, 30%, 20% / 0.3);
}
```

## Building an inset element

For a "well" or recessed area (text inputs, search boxes, code blocks):

1. **Top edge slightly darker** — the lip above is blocking light from reaching the top of the well. Use a top border or inset shadow with a small positive Y offset (so the shadow appears at the top of the inset element).

2. **Bottom edge slightly lighter** — that edge is angled upward toward the light. Use a bottom border or inset shadow with a small negative Y offset.

```css
.inset-input {
  background: hsl(220, 15%, 96%);
  box-shadow: 
    inset 0 1px 2px hsl(220, 20%, 50% / 0.2),  /* dark top */
    inset 0 -1px 0 hsl(0, 0%, 100%);            /* light bottom */
}
```

This treatment also works for text inputs, checkboxes, sliders — anything that should feel "carved into" the surface.

## Don't get carried away

The temptation is to keep tweaking shadows until you've recreated photo-realistic plastic buttons. Don't. Borrowing a *little* visual realism is great for clarity; trying for full skeuomorphism produces busy and dated interfaces. A single subtle hint of depth (a 1px lighter top edge + a 1px shadow) is often all you need.

## Use shadows to convey elevation

Treat shadows as a **z-axis system**, not just decoration. Different shadow sizes communicate different "heights" above the page:

- **Small, tight shadow** — barely raised. For static cards, buttons, tiles.
- **Medium shadow** — clearly above the page. For dropdowns, popovers, hover states.
- **Large shadow with high blur** — floating well above the page. For modals, dialogs, anything that should dominate attention.

The closer to the user something feels, the more it commands focus.

**Define a shadow elevation system** of about 5 levels up front, just like you do for colors and spacing. Tailwind ships this as `shadow-sm`, `shadow`, `shadow-md`, `shadow-lg`, `shadow-xl`, `shadow-2xl` — that's already a good system.

When you build it from scratch, start with the smallest and largest you'll need, then fill in roughly linear steps between.

**Map each level to a meaning:**
- `shadow-sm` → subtle raise (cards, inputs)
- `shadow-md` → button, picked-up state
- `shadow-lg` → dropdown, popover
- `shadow-xl` → modal, dialog
- `shadow-2xl` → reserved for the highest-priority floating element

Once you do this, you stop choosing shadows by feel. You think about *what z-position the element belongs at*, then pick the corresponding shadow.

## Combine shadows with interaction

Shadows aren't just for static elevation — they're powerful interaction signals. Common patterns:

- **Drag-and-drop:** when the user picks up a card, jump it up an elevation level (smaller shadow → larger shadow). This makes "I'm holding it" obvious.
- **Button press:** when the user clicks down on a button, *reduce* the shadow (or remove it entirely). The button feels physically pressed into the page.
- **Hover lift:** raise the shadow on hover to invite the click.

Always think about elevation movement, not shadow specifics. "This element should rise on click" is the design intent; the shadow change is the implementation.

## Two-layer shadows

Single shadows look flat. The way to get rich, designed-looking shadows is to **layer two**:

1. **The bigger, softer shadow** — larger Y offset, larger blur radius. This simulates the shadow cast by a direct light source above and behind the element.
2. **The tighter, darker shadow** — smaller Y offset, small blur radius, slightly darker. This simulates the *ambient occlusion* — the small dark area immediately under an object where ambient light can't reach.

```css
.elevated-card {
  box-shadow:
    0 10px 20px hsl(220, 30%, 20% / 0.1),    /* soft cast shadow */
    0 3px 6px hsl(220, 30%, 20% / 0.15);     /* tight contact shadow */
}
```

This gives you crisp edges close to the element *and* soft falloff farther away — much more realistic than either alone.

**Important detail:** as elevation increases, the *contact shadow fades*. Try setting something on your desk and lifting it: the dark area underneath shrinks and lightens. So at your highest elevation level (a modal floating well above the page), the second shadow should be very subtle or absent — only the soft cast shadow remains.

## Even flat designs have depth

If your aesthetic is flat (no shadows, no gradients), you can still convey depth through:

**Color (lightness contrast).** Lighter elements feel closer to the user; darker elements feel further. Make a card lighter than its parent background to feel raised; make it darker to feel recessed (like a well).

This works in non-flat designs too — color is just another tool in the depth toolkit.

**Solid offset shadows.** A short hard-edged shadow with no blur (`box-shadow: 4px 4px 0 black`) gives a flat-design-friendly sense of pop. Common in maximalist / brutalist / retro aesthetics.

**Overlap.** This is the most underused depth technique.

## Overlap to create layers

Containing every element neatly inside its parent is safe and a little boring. **Letting elements cross boundaries** instantly adds a sense of layered z-space:

- A hero card that crosses the boundary between two background colors
- An avatar that overlaps the top edge of its containing card
- A product image that pokes out above its surrounding panel
- Carousel arrows that sit *outside* the carousel frame

This trick is incredibly effective for landing pages, marketing UI, and anywhere you want a layered editorial feel.

**Watch for clashing on overlapping images:** when two images sit close together, their colors can blend visually in distracting ways. Add a small "invisible border" (a few pixels of the surrounding background color, e.g. white) around each image to keep a clean separation. The eye still reads them as overlapping, but without the visual mud.
