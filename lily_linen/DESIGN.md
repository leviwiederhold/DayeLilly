# Design System Specification: The Boutique Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Tactile Curator"**

This design system rejects the clinical sterility of modern SaaS. Instead, it embraces the warmth of a high-end boutique—balancing the editorial elegance of a fashion magazine with the grounded, rustic textures of a physical beauty bar. We move beyond "templates" by employing intentional asymmetry, layered depth, and a "No-Line" philosophy. The digital experience should feel like flipping through a heavy-stock linen catalog: tactile, intentional, and curated.

To break the "standard" look:
- **Asymmetric Grid:** Align imagery slightly off-center from text blocks to create a custom, high-end feel.
- **Floral Overlays:** Use lily-inspired vector motifs (using the `secondary` sage green) that partially overlap container boundaries, breaking the "box" mentality.
- **Tonal Depth:** We use background shifts rather than lines to guide the eye.

## 2. Colors
Our palette is rooted in organic warmth. We move away from pure white and harsh blacks in favor of creams and soft charcoals.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. All separation must be achieved through:
1.  **Background Shifts:** Transitioning from `surface` to `surface-container-low`.
2.  **Vertical Space:** Utilizing generous padding from our spacing scale.
3.  **Soft Texture:** Introducing a subtle grain or light wood texture overlay on `surface-container` tiers.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine paper.
- **Base Layer:** `surface` (#fbf9f5) for the primary background.
- **The "Inset" Layer:** Use `surface-container-low` for large content sections (e.g., service descriptions).
- **The "Lifted" Layer:** Use `surface-container-lowest` (#ffffff) for interactive cards to create a natural, bright "pop" against the cream background.

### The "Glass & Gradient" Rule
For floating headers and modal overlays, use **Glassmorphism**:
- **Tokens:** `surface` at 80% opacity with a `20px` backdrop-blur.
- **Signature Gradient:** For primary CTAs, use a subtle linear gradient from `primary` (#6d5a5a) to `primary_container` (#f4dada) at a 45-degree angle to add "soul" and dimension.

## 3. Typography
We pair the authority of a classical serif with the approachability of a geometric sans-serif.

| Level | Token | Font | Size | Weight | Character |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Display** | `display-lg` | Noto Serif | 3.5rem | 400 | Editorial, poetic, oversized. |
| **Headline** | `headline-md` | Noto Serif | 1.75rem | 500 | Sophisticated and welcoming. |
| **Title** | `title-lg` | Plus Jakarta Sans | 1.375rem | 600 | Clear, modern, and structured. |
| **Body** | `body-lg` | Plus Jakarta Sans | 1rem | 400 | Highly legible, open kerning. |
| **Label** | `label-md` | Plus Jakarta Sans | 0.75rem | 700 | All-caps for utility navigation. |

**The Identity Blend:** Always use `display` styles for boutique storytelling (e.g., "The Lily Standard") and `body` styles for service details. High contrast in scale between headlines and body text is mandatory to maintain the "Editorial" look.

## 4. Elevation & Depth
We define hierarchy through **Tonal Layering** rather than structural lines.

- **The Layering Principle:** Place a `surface-container-lowest` card on top of a `surface-container` background. The slight shift in brightness provides all the affordance a user needs to recognize an interactive element.
- **Ambient Shadows:** When a float is required (e.g., a "Book Now" sticky button), use a shadow tinted with `on-surface`: `box-shadow: 0 12px 32px -4px rgba(27, 28, 26, 0.06);`. Never use pure black shadows.
- **The "Ghost Border":** For input fields or cards that require high accessibility, use the `outline-variant` token at **15% opacity**. It should be felt, not seen.
- **Floral Depth:** Lily-inspired accents should live in a layer between the `surface` and the `content`, appearing to grow from the background.

## 5. Components

### Buttons (The "Soft Rounding" Scale)
- **Primary:** `primary` background, `on-primary` text. Border-radius: `md` (0.75rem). Use the Signature Gradient on hover.
- **Secondary:** `secondary_container` background, `on-secondary_container` text. This sage/beige combo feels "boutique rustic."
- **Tertiary:** No background. Text uses `primary` with a 2px underline in `primary_container`.

### Cards (Service & Boutique Items)
- **Rule:** Absolute prohibition of divider lines. 
- **Structure:** Use `surface-container-lowest` background with `xl` (1.5rem) padding. 
- **Visuals:** Images should have a `lg` (1rem) corner radius. Use `surface-dim` for a 1px "Ghost Border" if the image is very light.

### Inputs & Fields
- **Style:** Underline-only or very soft-filled containers using `surface-container-high`.
- **States:** On focus, the label (using `label-md`) should animate upward and shift color to `secondary` (Sage Green).

### Signature Component: The "Lily" Sticky Header
A persistent navigation bar using Glassmorphism (`surface` @ 85% opacity). The logo should be centered and "break" the bottom boundary of the header slightly, creating an organic, non-linear edge.

## 6. Do's and Don'ts

### Do
- **Do** use generous white space. If you think there is enough room, add 16px more.
- **Do** lean into the "Sage Green" (`secondary`) for success states and organic accents.
- **Do** mix serif and sans-serif within the same section to create typographic texture.
- **Do** use "Plus Jakarta Sans" for all functional UI (buttons, inputs) to ensure speed of use.

### Don't
- **Don't** use 100% black (#000000). Use `on-surface` (#1b1c1a) for all text.
- **Don't** use sharp 90-degree corners. Everything must feel "soft-touch."
- **Don't** use standard "Material Design" blue for links. Use `primary` or `secondary`.
- **Don't** use "Card-in-Card" layouts unless the background colors shift significantly. Use vertical padding instead.