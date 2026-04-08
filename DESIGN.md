# Design System Documentation: The Cinematic Editorial

## 1. Overview & Creative North Star: "The Digital Curator"
This design system is not a utility; it is a gallery. Our Creative North Star is **The Digital Curator**. In the world of high-end photography, the interface must never compete with the art—it must frame it. We move away from the "app-like" grid and toward an editorial layout characterized by intentional asymmetry, vast negative space, and a sense of "hush."

To achieve a "premium" feel, we reject standard UI tropes. We use overlapping elements to create depth, high-contrast typography scales to establish authority, and a tonal layering system that feels like light hitting a physical surface. Every interaction should feel like turning the page of a heavy, matte-finish coffee table book.

---

## 2. Colors: Tonal Depth & Gold Accents
The palette is rooted in the absence of light, using deep charcoal and black to allow photography to "pop." 

### The Palette (Material Design Mapping)
*   **Background / Surface:** `#131313` (The base of our darkroom).
*   **Primary (Gold):** `#f2ca50` (Used for critical focus points and brand signature).
*   **Primary Container:** `#d4af37` (A muted gold for sophisticated interactive states).
*   **Surface Tiers:** From `surface_container_lowest` (`#0e0e0e`) to `surface_bright` (`#3a3939`).

### The "No-Line" Rule
**Borders are strictly prohibited for sectioning.** We do not use 1px lines to separate content. Boundaries must be defined solely by shifting between background tiers. For example, a `surface_container_low` card sits on a `surface` background. The change in tone is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
*   **Base:** `surface` (`#131313`)
*   **Interactive Containers:** `surface_container` (`#201f1f`)
*   **Floating Modals/Dialogs:** `surface_container_highest` (`#353534`)
This creates "natural depth" without the clutter of lines.

### The "Glass & Gradient" Rule
To elevate beyond flat design, use **Glassmorphism** for navigation bars and floating elements.
*   **Formula:** `surface_variant` at 60% opacity + `backdrop-filter: blur(20px)`.
*   **Gradients:** For primary CTAs, use a linear gradient from `primary` (`#f2ca50`) to `primary_container` (`#d4af37`) at a 135-degree angle to mimic the sheen of real gold leaf.

---

## 3. Typography: Editorial Authority
We pair a high-fashion serif with a functional, architectural sans-serif.

*   **Display & Headlines (Noto Serif):** These are our "Art" fonts. Use `display-lg` for hero titles with generous tracking (-0.02em). This font conveys luxury, history, and craftsmanship.
*   **Body & Labels (Manrope):** Our "Utility" font. Modern, geometric, and highly legible. Manrope provides a clean contrast to the serif, ensuring the studio feels modern rather than "antique."

**Hierarchy Tip:** Always lead with a large Serif headline, but support it with a `label-md` uppercase sub-header in Gold (`primary`) to create a professional, curated look.

---

## 4. Elevation & Depth: Tonal Layering
We do not use "drop shadows" in the traditional sense. We use ambient light.

*   **The Layering Principle:** Depth is achieved by "stacking." Place a `surface_container_highest` element on top of a `surface_dim` background to create a "lift" that feels integrated.
*   **Ambient Shadows:** If a shadow is required for a floating action, use a blur radius of 40px+ with an opacity of 8% using the `on_secondary_fixed` color. It should feel like a soft glow of light blocked by the object, not a black smudge.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use the `outline_variant` token at **15% opacity**. It should be felt, not seen.

---

## 5. Components: The Primitive Set

### Buttons
*   **Primary:** Gradient of Gold (`primary` to `primary_container`), `on_primary` text, `md` (0.375rem) roundedness. No border.
*   **Secondary:** Ghost style. Transparent background, `primary` text, and a `primary` Ghost Border (20% opacity).
*   **Tertiary:** Text-only, `on_surface` color, `label-md` styling, with a subtle gold underline on hover.

### Cards & Lists
*   **Forbid Dividers:** Use `surface_container_low` backgrounds to group list items.
*   **Image-First:** Cards should lead with a high-resolution image. Use a subtle `secondary_container` overlay on the bottom 30% of the image to ensure white text remains legible.

### Input Fields
*   **Style:** Minimalist. No background fill. Only a bottom border using `outline_variant` (30% opacity). When focused, the border transitions to `primary` (Gold) and the label floats upward using `label-sm`.

### Glass Overlay (Signature Component)
*   Used for image captions or navigation menus. A semi-transparent `surface_container_highest` with a heavy backdrop blur, creating a "frosted glass" effect over photography.

---

## 6. Do's and Don'ts

### Do
*   **Do use asymmetric margins.** Off-set a headline to the left and a description to the right to create a "gallery layout" feel.
*   **Do use plenty of vertical white space.** If you think there is enough space, double it.
*   **Do use Gold (`primary`) sparingly.** It is a highlight, not a paint bucket. It should only appear on 5-10% of the screen.

### Don't
*   **Don't use 100% opaque white for body text.** Use `on_surface_variant` (`#d0c5af`) for long-form text to reduce eye strain and look more "expensive."
*   **Don't use sharp 90-degree corners.** Use the `md` (0.375rem) or `lg` (0.5rem) scale to soften the digital edge.
*   **Don't use standard icons.** Use ultra-thin (200 weight) line icons to match the sophistication of the typography.