# Design System Document: The Editorial Lens

## 1. Overview & Creative North Star: "The Digital Curator"
This design system is built to transform a digital interface into a high-end gallery experience. Our Creative North Star is **The Digital Curator**. We are not building a website; we are curating a physical exhibition. 

To achieve this, we move beyond the "template" look by embracing **intentional asymmetry** and **expansive white space**. In this system, imagery is the protagonist, and the UI is the sophisticated architecture that houses it. We prioritize a "High-End Editorial" feel through the use of extreme typographic contrast, overlapping elements that break the grid, and a total rejection of traditional structural lines. The goal is a layout that feels "breathtakingly empty" yet intentionally dense in detail.

---

## 2. Colors: Tonal Depth & The Gold Standard
Our palette is rooted in a "High-Contrast Minimalist" philosophy. We use light to define space rather than lines.

*   **Primary (#735c00 / #D4AF37):** This is our "Signature Gold." It must be used sparingly to maintain its luxury status. Reserve it for primary CTAs, active states, or singular decorative accents.
*   **Surface Hierarchy:** We utilize the `surface-container` tiers to create depth without borders.
    *   **Surface (#f9f9f9):** The primary canvas.
    *   **Surface-Container-Lowest (#ffffff):** Used for elevated content blocks or hero sections to create a "bright" focus.
    *   **Surface-Container-Highest (#e2e2e2):** Used for deep-set elements like footers or utility bars.
*   **The "No-Line" Rule:** 1px solid borders for sectioning are strictly prohibited. Boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section should sit flush against a `surface` background to create a soft, sophisticated transition.
*   **The "Glass & Gradient" Rule:** For floating navigation or modal overlays, use **Glassmorphism**. Utilize `surface` colors at 70% opacity with a `backdrop-filter: blur(20px)`. 
*   **Signature Textures:** For primary CTAs, do not use flat hex codes. Apply a subtle linear gradient from `primary` (#735c00) to `primary-container` (#d4af37) at a 135-degree angle to mimic the natural luster of gold leaf.

---

## 3. Typography: The Editorial Scale
We use a high-contrast pairing to evoke the feeling of a luxury fashion magazine.

*   **Display & Headlines (Noto Serif / Playfair Equivalent):** These are our "Art" layers. 
    *   Use `display-lg` (3.5rem) for hero moments. 
    *   **The Italic Emphasis:** Frequently use the italic variant of the serif for the first or last word in a headline to create a rhythmic, curated feel.
*   **Body & Titles (Manrope / Modern Sans):** Our "Utility" layer.
    *   `body-lg` (1rem) should be used for descriptions to ensure readability against high-resolution photography.
    *   Letter spacing for `label-md` should be increased by 0.05em to provide an "architectural" feel to small metadata.
*   **Hierarchy Strategy:** Establish dominance by pairing a massive `display-sm` heading with a significantly smaller `title-sm` sub-headline. This "Gap of Authority" is what defines luxury.

---

## 4. Elevation & Depth: Tonal Layering
In this system, depth is felt, not seen. We avoid the "drop shadow" look of standard web apps.

*   **The Layering Principle:** Stack surfaces. A `surface-container-lowest` card placed on a `surface-container-low` background creates a natural, soft lift.
*   **Ambient Shadows:** If a floating element (like a lightbox) requires a shadow, it must be an "Ambient Shadow." Use the `on-surface` color at 4% opacity with a 40px-60px blur and 0px offset. This mimics soft, natural studio lighting.
*   **The "Ghost Border" Fallback:** If accessibility requires a container edge, use the "Ghost Border": the `outline-variant` token (#d0c5af) at 15% opacity. Never use a 100% opaque border.
*   **Intentional Overlap:** To break the "flat" feel, allow high-quality imagery to slightly overlap into the next `surface-container` section or have a `display-lg` text element sit 20% over a photograph.

---

## 5. Components
All components follow a **0px Border Radius (None)** policy to maintain a sharp, architectural, and premium edge.

*   **Buttons:**
    *   **Primary:** Gradient fill (Gold), no border, white text (`on-primary`). 
    *   **Secondary:** Ghost style. No fill, a "Ghost Border" (15% opacity Gold), and `primary` text.
    *   **Padding:** Use the Spacing Scale `4` (1.4rem) for horizontal and `2.5` (0.85rem) for vertical.
*   **Cards & Lists:**
    *   **Forbid Divider Lines.** Separate list items using the Spacing Scale `8` (2.75rem) of vertical white space or a subtle shift from `surface` to `surface-container-low`.
    *   Images in cards should occupy 100% of the container width to emphasize the studio's work.
*   **Input Fields:**
    *   Underline style only. Use `outline-variant` for the underline. On focus, transition the underline to `primary` (Gold) and shift the label color.
*   **The Gallery Masonry (Custom Component):**
    *   Instead of a grid, use a staggered masonry layout with varying widths (e.g., one image at 60% width, the next at 40%) to mimic a physical art gallery wall.

---

## 6. Do's and Don'ts

### Do:
*   **Use Massive Margins:** If you think there is enough white space, add 20% more. Use `spacing-24` (8.5rem) for section breathing room.
*   **Embrace Asymmetry:** Place a heading on the left and the body text on the far right of a grid to create visual tension.
*   **Prioritize Image Quality:** Only use high-bitrate, professional photography. The UI is designed to disappear behind the art.

### Don't:
*   **Don't Use Rounded Corners:** Any radius above 0px will break the "high-end" architectural feel of this system.
*   **Don't Use Pure Black:** Use `on-surface` (#1a1c1c) for text to keep the contrast sophisticated rather than jarring.
*   **Don't Use Icons in CTAs:** Let the typography speak. Icons often "cheapen" the editorial aesthetic unless they are custom-drawn, ultra-thin line weights.
*   **Don't Use Traditional Dividers:** If you feel the need for a line, use a wide margin instead. Space is your separator.