# Design System Strategy: The Artisanal Digital Kitchen

## 1. Overview & Creative North Star: "The Digital Pâtisserie"
This design system is built to evoke the sensory experience of a high-end dessert boutique. Our Creative North Star is **"The Digital Pâtisserie"**—a philosophy that treats the digital interface as a curated, physical space where warmth meets precision. 

To move beyond the generic "template" look of most QSR (Quick Service Restaurant) apps, we utilize an **Editorial Grid**. This means breaking away from rigid, centered blocks in favor of intentional asymmetry, generous white space (the "creamy white" void), and overlapping imagery. Our goal is to make the user feel as though they are flipping through a luxury food magazine, not scrolling through a spreadsheet of products.

## 2. Color & Materiality: A Tonal Feast
The palette is a celebration of ingredients. We use a high-contrast relationship between deep chocolate neutrals and vibrant honey accents to guide the eye.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning. Structural boundaries must be defined solely through background color shifts. Use `surface-container-low` sections sitting on a `surface` background to create natural separation. Lines are rigid; colors are fluid.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, physical layers.
*   **Base:** `surface` (#FFF9F0) is our canvas.
*   **Layering:** Use the `surface-container` tiers (Lowest to Highest) to define importance. An inner card should be `surface-container-lowest` placed on a `surface-container-low` section to create a soft, "pillowy" lift.
*   **The Glass & Gradient Rule:** For floating elements or top-tier promotions, use **Glassmorphism**. Apply `surface-variant` with a 60% opacity and a 16px backdrop-blur. This ensures the "warmth" of the background bleeds through the component, feeling integrated rather than detached.
*   **Signature Textures:** Apply a subtle radial gradient transitioning from `primary` (#745853) to `primary-container` (#E8C2BC) on Hero CTAs to mimic the sheen of melted chocolate.

## 3. Typography: The Editorial Voice
Our type scale prioritizes a "Playful Precision" aesthetic, balancing the roundness of the brand with the clarity of modern editorial design.

*   **Display (Plus Jakarta Sans):** These are our "hero" moments. Use `display-lg` for headlines that break the grid—overlap them slightly with product photography for a custom, layered feel.
*   **Headlines (Plus Jakarta Sans):** Clean and authoritative. Use `headline-md` for category titles (e.g., "Signature Waffles") to provide a clear anchor.
*   **Body & Titles (Be Vietnam Pro):** This is our workhorse. It provides a geometric, modern contrast to the expressive headers. Use `body-lg` for descriptions to ensure every ingredient sounds as good as it looks.
*   **Labels:** Always in `label-md` using `on-surface-variant`. Keep them subtle to ensure the focus remains on the visuals.

## 4. Elevation & Depth: Tonal Layering
We do not use structural lines to convey hierarchy; we use light and shadow.

*   **The Layering Principle:** Depth is achieved by "stacking." A `surface-container-highest` card provides maximum prominence without needing a border.
*   **Ambient Shadows:** When an element must float (like a "Cart" FAB), use an extra-diffused shadow. 
    *   *Spec:* `0px 12px 32px` blur, 6% opacity. 
    *   *Color:* Use a tinted version of `on-surface` (#1D1B16) rather than pure black to keep the "warmth" of the system intact.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, it must be a "Ghost Border." Use `outline-variant` at 15% opacity. **100% opaque borders are strictly forbidden.**

## 5. Components: Crafted Primitives

### Buttons
*   **Primary:** A "Honey-Dipped" look. Background: `tertiary-container` (#FFC107); Text: `on-tertiary-container`. Use `DEFAULT` (1rem) roundedness.
*   **Secondary:** Background: `secondary-container` (#FDCDBC); Text: `on-secondary-container`. No border.
*   **Interaction:** On hover, primary buttons should scale slightly (1.02x) rather than just changing color, mimicking a "soft press."

### Chips (Topping & Filter Selection)
*   **Unselected:** `surface-container-high` with `on-surface-variant` text.
*   **Selected:** `primary` (#745853) with `on-primary` text. Use `full` (pill) roundedness to echo the shape of a waffle iron's indentations.

### Input Fields
*   **Style:** Minimalist. No bottom line. Use a `surface-container-low` background with a `DEFAULT` (1rem) corner radius. 
*   **Focus State:** Instead of a heavy border, use a subtle `outline` (#827660) at 30% opacity and a slight tonal shift to `surface-container-highest`.

### Cards & Product Lists
*   **The "No-Divider" Rule:** Forbid the use of divider lines between list items. Use 24px–32px of vertical white space or a subtle shift between `surface-container-lowest` and `surface-container-low` to separate items.
*   **Visual Dominance:** Product cards should feature "bleeding" imagery—photos that touch the top and side edges of the card, breaking the container's internal padding.

### Added Component: The "Drizzle" Progress Bar
*   A custom progress bar for checkout or loyalty points. Use a thick `secondary-container` track with a `primary` (Chocolate) fill that has a rounded, "droplet" cap on the leading edge.

## 6. Do’s & Don’ts

### Do:
*   **Do** use asymmetrical layouts where text sits left-aligned and imagery "breaks" the container to the right.
*   **Do** use the `tertiary-fixed-dim` (Honey) for high-conversion highlights like price tags or "New" badges.
*   **Do** ensure all imagery has a warm, high-key lighting style to match the `surface` color (#FFF9F0).

### Don’t:
*   **Don’t** use pure black (#000000) for text. Always use `on-surface` (#1D1B16) to maintain the "Rich Chocolate" tonal depth.
*   **Don’t** use sharp corners. The minimum radius is `sm` (0.5rem); the standard is `DEFAULT` (1rem). 
*   **Don’t** use standard Material shadows. If a shadow looks like a "drop shadow," it’s too heavy. It should look like an "ambient glow."