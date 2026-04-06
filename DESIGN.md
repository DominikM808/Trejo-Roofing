# Design System Document: Industrial Editorial

## 1. Overview & Creative North Star
**Creative North Star: "The Architectural Monolith"**

This design system moves away from the "template" look of local contractor sites and moves toward a high-end, editorial experience. It balances the rugged, blue-collar grit of West Texas construction with the precision of modern architecture. We achieve this through **Intentional Asymmetry** and **Tonal Depth**. Instead of a standard grid, we use overlapping elements—such as a high-contrast image of a steel roof breaking the boundary of a dark charcoal container—to create a sense of movement and structural integrity. The goal is to feel "built," not just "designed."

---

## 2. Colors & Surface Philosophy
The palette is rooted in the "Deep Night" of the Texas plains, punctuated by the "Molten Glow" of industrial safety equipment.

### Color Tokens
- **Background (Base):** `#131313` (The void; the foundational site canvas)
- **Primary:** `#ffb68b` / **Primary Container:** `#e87722` (The signature "West Texas Orange")
- **Secondary Container:** `#3e495e` (A muted navy for subtle utility)
- **Surface Tiers:** 
    - `surface_container_lowest`: `#0e0e0e`
    - `surface_container_low`: `#1b1b1b`
    - `surface_container_high`: `#2a2a2a`

### The "No-Line" Rule
To maintain a premium, custom feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined solely through background color shifts. For example, a "Services" section (`surface_container_low`) should sit directly against the main `background` without a divider. This creates a seamless, "machined" look.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
- Use `surface_container_lowest` for deep, inset areas (like a form field background).
- Use `surface_container_high` for elevated cards or floating navigation.
- **The Glass & Gradient Rule:** For hero sections or high-impact CTAs, use a subtle linear gradient from `primary` to `primary_container` at a 135-degree angle. This mimics the sheen of powder-coated steel.

---

## 3. Typography
The typography is designed to feel authoritative and steady.

- **Display & Headlines (Plus Jakarta Sans / Montserrat Bold):** These are our "Structural Beams." Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero headlines to convey strength. 
- **Body (Work Sans / Open Sans):** Our "Utility" layer. We use Work Sans for its slightly wider stance, which improves readability against dark backgrounds.
- **Hierarchy of Trust:** Large, bold headlines convey the scale of the company, while clean, spacious body text (`body-lg`) ensures contracts and service descriptions are transparent and easy to digest.

---

## 4. Elevation & Depth
In this design system, depth is earned through **Tonal Layering**, not artificial dropshadows.

- **The Layering Principle:** Place a `surface_container_highest` card on a `surface_container_low` background. The subtle 2-3% difference in lightness provides a sophisticated "lift."
- **Ambient Shadows:** Shadows are only permitted on "Active" floating elements (like a triggered modal). Use a large blur (32px) at 8% opacity, using the `on_surface` color as the shadow tint to ensure it feels like natural ambient light.
- **The Ghost Border Fallback:** If a layout requires a boundary for accessibility, use the `outline_variant` token at **15% opacity**. It should be felt, not seen.
- **Glassmorphism:** Use `backdrop-blur: 12px` on the navigation bar with a semi-transparent `surface_container` color. This allows the rugged textures of project photography to bleed through as the user scrolls.

---

## 5. Components

### Buttons (The "Actuators")
Buttons must feel like heavy-duty equipment.
- **Primary:** `primary_container` background, `on_primary` text. Use `rounded-md` (0.375rem).
- **Interactions:** On hover, transition to a slight outer glow using the primary color at 20% opacity. Avoid "shrinking" or "lifting" animations; use a steady "color fill" transition.
- **Padding:** 16px top/bottom, 32px left/right. High-density padding reinforces the "rugged" feel.

### Form Inputs
- **Style:** Background should be `surface_container_lowest`. 
- **Active State:** A 2px bottom-border using the `primary` token. No full-box focus rings. This mimics architectural drafting lines.

### Cards
- **Forbid Dividers:** Never use a line to separate a card header from its body. Use a shift from `surface_container_high` to `surface_container_lowest` or simply use a 24px vertical gap.
- **Texture:** Apply a subtle 5% opacity "grit" or "brushed metal" overlay to card backgrounds to ground them in the construction industry.

### Service Icons
- **Style:** Dual-tone icons using `primary` and `secondary_fixed_dim`. Use thick 2px strokes; thin lines feel too fragile for a construction brand.

---

## 6. Do’s and Don’ts

### Do
- **Do** use aggressive white space. A "rugged" brand needs room to breathe to avoid looking "cluttered" or "cheap."
- **Do** use high-contrast imagery (high-key lighting, deep shadows) to match the dark UI.
- **Do** align text-heavy blocks to a strict left-hand axis to mimic the "plumb line" of a building.

### Don't
- **Don't** use pure black (#000000). It kills the depth of the Navy and Charcoal tones. Use `surface_container_lowest`.
- **Don't** use default Material shadows. They feel too "software-standard."
- **Don't** use bright, saturated blues or greens. Stay within the Navy/Charcoal/Orange spectrum to maintain the "West Texas Industrial" vibe.