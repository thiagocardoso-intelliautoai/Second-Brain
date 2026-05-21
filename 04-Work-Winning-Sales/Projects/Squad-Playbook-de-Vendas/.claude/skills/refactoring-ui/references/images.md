# Images

Images can elevate a design or torpedo it. The first principle is brutally simple: bad images make good design look bad, and there is no styling trick that will save you from a low-quality photo.

## Use good photos

If your design relies on photography and you're not a great photographer, your two options are:

1. **Hire a professional** — for product shots, team photos, anything brand-specific that needs a particular subject.
2. **Use high-quality stock photography** — Unsplash (free), Pexels (free), or paid sources like Stocksy and Death to Stock for less generic-looking work.

What doesn't work: building the layout against placeholder images, then planning to swap in your own phone photos before launch. Phone photos in well-designed UIs almost always look like phone photos in a well-designed UI. Plan for the real images from day one.

For interfaces specifically (not marketing pages), often the cleanest move is to use **fewer photos** and lean on type, color, illustration, and layout instead.

## Text over photos needs consistent contrast

Hero images with text overlaid almost always have a contrast problem — photos are dynamic, with bright and dark areas. White text disappears into the bright spots; dark text disappears into the dark spots.

The fix isn't about the text — it's about reducing the dynamic range of the *image* so contrast is consistent across it.

**Four techniques** (often combined):

**1. Add a semi-transparent overlay.**
A dark overlay tones down bright areas (helps light text); a light overlay tones up dark areas (helps dark text). Simple and reliable:

```html
<div class="relative">
  <img src="hero.jpg" class="absolute inset-0 h-full w-full object-cover" />
  <div class="absolute inset-0 bg-black/40"></div>
  <h1 class="relative text-white">...</h1>
</div>
```

The trade-off: you're flattening the whole image, including the bits that didn't need flattening.

**2. Lower the image's contrast** at the source (in your photo editor or with CSS `filter: contrast()`). More surgical than an overlay because it preserves the average brightness. You'll usually need to bump exposure/brightness afterward to keep the image from feeling muddy.

**3. Colorize the image with a single hue.**
Three steps: lower contrast → desaturate → apply a solid color fill in "multiply" blend mode. This gives you total control of the background tone and is great for matching a photo to your brand palette. Editorial sites use this constantly.

**4. Add a soft text-shadow as a glow** behind the text — large blur radius, no offset. Lets you preserve image dynamics while still giving the text local contrast wherever it sits. Best when combined with a mild overall contrast reduction so the shadow doesn't have to work too hard.

## Everything has an intended size

Images and icons are designed for a specific display size. Scaling them violates that intent in different ways:

**Photos scaled up** — visible blur, soft edges, "phone-camera" look.

**Photos scaled down** — wasteful (large file for small display), and detail-rich photos become muddy noise at thumbnail sizes.

**Icons scaled up** — drawn for 16-24px, the line weights and corner radii were tuned for that size. At 64px they look chunky and clumsy.

**Icons scaled down** — drawn for 64px+, the detail collapses into mush at 16px. Favicons are the classic disaster: a beautifully detailed logo at 128px renders as a pixel sludge at 16px.

**The rule:** use images and icons at or near their intended display size. If you need a small version of something detailed (like a product UI screenshot in a thumbnail), **redraw a simplified version** rather than letting the browser shrink the original. You control the compromises instead of the renderer.

For icons specifically, modern icon libraries (Lucide, Heroicons) ship multiple sizes precisely so you don't have to scale.

## Beware user-uploaded content

The moment you let users upload images, you lose control over aspect ratio, contrast, color, and quality. Three problems and three fixes:

**Problem 1: aspect ratios destroy the layout.**
A page with 6 user-uploaded photos looks completely random when each photo is a different shape. The fix: **fixed-aspect containers with `object-cover`**. Crop the image to fit the container; let some content be cut off rather than letting the container reflow.

```html
<div class="aspect-square overflow-hidden rounded-lg">
  <img src="user-upload.jpg" class="h-full w-full object-cover" />
</div>
```

**Problem 2: image background bleeds into UI background.**
A user uploads a photo with a white background, your page background is white, and the photo loses its rectangular shape. The image "leaks" into the page.

A hard border fixes the bleed but often clashes with the colors in the photo. Better: **a subtle inner box-shadow** — most users won't consciously see it, but the image edge now reads cleanly.

```css
img {
  box-shadow: inset 0 0 0 1px hsl(0, 0%, 0% / 0.1);
}
```

A semi-transparent inner border (`outline: 1px solid rgba(0,0,0,0.1)` in a wrapper) achieves the same effect without the inset look.

**Problem 3: user images may have terrible contrast for any text overlay.**
If you're putting text on user-supplied images (e.g. video thumbnails with titles), assume contrast will fail. Use one of the techniques from "Text over photos needs consistent contrast" above — overlays, contrast reduction, text shadow — and test against the worst-case images you can find.

## A practical default for product UIs

When in doubt, a clean default that almost always looks fine:

- Photos cropped to fixed aspect ratios (`aspect-video`, `aspect-square`, or `aspect-[4/3]`)
- `object-cover` so the crop is automatic
- Subtle rounded corners (`rounded-lg`)
- Subtle inner shadow OR semi-transparent border to prevent background bleed
- For overlay text: dark gradient from bottom (`bg-gradient-to-t from-black/60 to-transparent`)
