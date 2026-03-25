# Design System Strategy: High-End Editorial

## 1. Overview & Creative North Star
**Creative North Star: The Vibrant Curator**
This design system rejects the "template-heavy" aesthetic of traditional digital agencies in favor of a high-end editorial experience. It is designed to feel like a premium digital monograph—confident, spacious, and meticulously curated. 

By leveraging intentional asymmetry, high-contrast typography, and layered depth, we move beyond flat UI. The layout should breathe through generous white space, using the vibrant spectrum of the brand's logo not as a distraction, but as a precise tool for wayfinding and emotional resonance. The core philosophy is "Sophisticated Vibrancy": where clean, #FFFFFF backgrounds meet the high-energy pulse of a spectrum gradient.

---

## 2. Colors & Surface Logic
The palette is a sophisticated interplay between a stark, sterile canvas and a high-energy spectrum.

### The Palette (Material Design Tokens)
*   **Surface:** `#f6f6f6` (Primary Canvas)
*   **Surface Container Lowest:** `#ffffff` (Card Highlight / Elevated Surface)
*   **Primary:** `#652fe7` (The "M" Purple)
*   **Secondary:** `#006859` (The "M" Deep Green)
*   **Tertiary:** `#7e5200` (The "M" Golden Ochre)
*   **On-Surface:** `#2d2f2f` (Deep Charcoal for readability)

### Critical Visual Rules
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. Boundaries must be defined solely through background shifts. Transition from `surface` to `surface-container-low` to create spatial logic. 
*   **Surface Hierarchy & Nesting:** Treat the UI as stacked sheets of fine paper. An inner `surface-container-highest` element should sit atop a `surface-container-low` background to provide natural, line-free containment.
*   **The "Glass & Gradient" Rule:** Use the multi-color logo gradient (Green → Yellow → Orange → Red → Purple → Blue) for major CTAs and section headers. Navigation bars and floating cards should utilize Glassmorphism: a semi-transparent `surface` color with a `backdrop-filter: blur(20px)`.
*   **Signature Textures:** For hero backgrounds, apply a subtle linear gradient from `primary` to `primary-container` at a 135-degree angle to provide tonal depth that avoids the "flat" look of standard CSS.

---

## 3. Typography
Typography is our primary vehicle for "Confidence." We use a high-contrast scale to create an editorial rhythm.

*   **Display (Plus Jakarta Sans):** Set at `display-lg` (3.5rem), these are the "hook." Use bold weights with tight letter-spacing (-0.02em) to mimic premium magazine mastheads.
*   **Body (Manrope):** Manrope provides a clean, geometric balance. `body-lg` (1rem) is the standard for long-form content, ensuring high legibility against the stark white background.
*   **Hierarchy as Identity:** By pairing the "aggressive" modernism of Plus Jakarta Sans with the functional "quietness" of Manrope, we signal an agency that is both creative (vibrant) and results-driven (organized).

---

## 4. Elevation & Depth
We eschew traditional shadows in favor of **Tonal Layering**.

*   **The Layering Principle:** Depth is achieved by stacking. A `surface-container-lowest` card (#FFFFFF) placed on a `surface` background (#F6F6F6) creates a "Soft Lift."
*   **Ambient Shadows:** If an element must float (e.g., a primary CTA or a Modal), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(45, 47, 47, 0.06)`. The tint is derived from the `on-surface` token, never pure black.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use the `outline-variant` token at 15% opacity. It should be felt, not seen.
*   **Glassmorphism:** Navigation menus should use a 60% opacity version of `surface-container-lowest` with a heavy blur. This allows the vibrant brand gradients to "bleed" through the UI as the user scrolls, maintaining a sense of place.

---

## 5. Components

### Buttons
*   **Primary:** A full spectrum gradient background with `on-primary` (#F7F0FF) text. Roundedness: `full` (9999px) for a modern, pill-shaped aesthetic.
*   **Secondary:** `surface-container-highest` background with `primary` text. No border.
*   **Tertiary:** Ghost style. No background, `primary` text, becomes `surface-container-low` on hover.

### Cards
*   **Editorial Card:** No borders. Background: `surface-container-lowest`. Padding: `spacing-8` (2.75rem). Use `spacing-12` for vertical separation between cards rather than dividers.
*   **Glass Card:** Used for floating stats or highlights. 40% opacity `surface-container-lowest` with `backdrop-filter: blur(12px)`.

### Input Fields
*   **Text Inputs:** Soft `surface-container-high` backgrounds. On focus, the bottom edge gains a 2px `primary` gradient "underline" rather than a full box stroke.

### Specialized Components
*   **The Spectrum Divider:** Instead of a grey line, use a 2px tall horizontal gradient spanning the brand colors to separate major editorial themes.
*   **Contextual Tooltips:** Use `inverse-surface` with `inverse-on-surface` text to provide a high-contrast pop against the light UI.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical margins. For example, a headline may be offset to the left while body text stays centered to create "Editorial Tension."
*   **Do** use the `spacing-20` (7rem) and `spacing-24` (8.5rem) tokens for section breathing room.
*   **Do** use the brand gradient for high-impact moments only (CTAs, icons, or hero accents).

### Don't:
*   **Don't** use 1px solid black or grey borders. They break the premium "paper-like" feel.
*   **Don't** use standard "drop shadows" with high opacity.
*   **Don't** crowd the interface. If a layout feels "busy," increase the whitespace using the next tier in the spacing scale.
*   **Don't** use dividers. If two pieces of content need separation, use a background color shift or `spacing-16`.