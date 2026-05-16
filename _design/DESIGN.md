# Design System — Build Your Business OS (scraped)

> Generated from the live URL via `scripts/scrape_brand.py`. This is the prospect's
> own brand, not a vendored library system. The page-builder agent must render
> these tokens verbatim — no Apple-system fallbacks, no Inter-default substitutions.

## 1. Visual Theme & Atmosphere

Build Your Business OS.

Tone words from the scrape: (none captured).

## 2. Color Palette & Roles

### Surfaces
- **Surface (primary background)**: `#ffffff` — page bg, hero bg, dominant section bg.
- **Border / divider**: `#e5e5e5` — 1px lines between sections, card edges.

### Text
- **Primary text**: `#111111` — headlines, body copy on `#ffffff`.
- **Muted text**: `#666666` — captions, labels, metadata.

### Accent
- **Accent (CTA + emphasis)**: `#000000` — buttons, links, hover emphasis. ONE accent rule from the composition-playbook applies — never use this color for body copy or large background fills.


### Full extracted palette (use only when the role-mapped tokens above don't fit)
(none extra)

## 3. Typography Rules

### Font families
- **Display + Body**: `system-ui, -apple-system, sans-serif` — load from Google Fonts if available, otherwise from a self-hosted webfont.
- **Fallback chain**: `system-ui, -apple-system, sans-serif`
- **Other families captured on the scraped pages** (use sparingly, only if the live site uses them in a specific role like monospace or accent display):
(none extra)

### Hierarchy

| Role | Size | Weight | Line-height | Letter-spacing |
|------|------|--------|-------------|----------------|
| Display / Hero H1 | clamp(2.75rem, 6vw, 4.5rem) | 700 | 1.05 | -0.02em |
| Section H2 | clamp(2rem, 4vw, 3rem) | 700 | 1.1 | -0.015em |
| H3 | 1.5rem | 600 | 1.25 | normal |
| Body | 1.125rem | 400 | 1.65 | normal |
| Body Small | 1rem | 400 | 1.55 | normal |
| Label / Eyebrow | 0.8rem | 500 | 1.3 | +0.08em UPPERCASE |

Paragraph max-width ~65ch (per the redesign-playbook's "body too wide" rule).

## 4. Components

### Buttons
- **Primary CTA**: bg `#000000`, text `#ffffff`, 6px corner radius, 0.875rem 1.5rem padding, weight 600. Hover: darken bg ~10% via `filter: brightness(0.9)` (no shadow glow).
- **Secondary**: transparent bg, text `#000000`, 1px solid `#000000` border, same padding. Hover fills with the accent at 10% opacity.
- **Text link**: underline `#000000`. Use `text-decoration-thickness: 1px; text-underline-offset: 4px;` — never the default thick underline.

### Cards
- Background `#ffffff`, 2rem internal padding, 1px solid `#e5e5e5`, optional 8px radius. Hover lifts 2px via `transform: translateY(-2px)` (transform only — never animate width/height).

### Inputs
- 1px `#e5e5e5` border, 4px radius, 1rem padding, bg `#ffffff`. Focus state: border `#000000`, no glow.

### Navigation
- Sticky top, `#ffffff` bg, 1.25rem vertical padding. When scrolled past 80px, add a 1px `#e5e5e5` bottom line.

## 5. Layout Principles

- Container max-width 1200px, horizontal padding 2rem (1.25rem mobile).
- Section vertical padding 6rem desktop → 3.5rem mobile.
- Background alternates `#ffffff` → (slightly tinted variant) for rhythm. Never two adjacent identical backgrounds with no visual delineation.
- Grid > flex-math. Use `grid-template-columns` with fractional units, not flex percentage math.

## 6. Depth & Elevation

- Flat-first. Color shifts and 1px borders do the work.
- Shadow allowed ONLY on card hover (`0 2px 12px rgba(0,0,0,0.06)`) and sticky-nav scrolled separator.
- Tint shadows toward the surface hue — pure black shadow at low opacity is a redesign-playbook AI-tell.

## 7. Motion

- Subtle. Fade-in on scroll, transform-only animations.
- Hover transitions ~200ms eased: `transition: transform 200ms cubic-bezier(0.16, 1, 0.3, 1), opacity 200ms ease;`
- Never animate `top`, `left`, `width`, `height` — hardware-accelerate via `transform` and `opacity`.

## 8. Responsive Breakpoints

- Mobile-first base, scaling at 768px, 1024px, 1440px.
- Below 768: single column, section padding 3.5rem, hero H1 floor at 2.75rem, nav collapses to hamburger.
- Full-height sections use `min-height: 100dvh`, never `height: 100vh` (iOS Safari viewport bug).

## 9. Real assets captured from the scrape

- **Logo**: `(missing)` (downloaded from ``).
- **Hero image candidate**: `(missing)`.
- **Source-of-truth screenshot**: `build/_design/source-screenshot.png` (1440×900, the live site at scrape time).

## 10. Real services / testimonials captured

### Services
(none surfaced — fall back to scraped page bodies)

### Real testimonials (use these verbatim in the testimonial section — do not invent new quotes)
(no real testimonials with attribution — leave the testimonial section as TK)

## 11. Agent Prompt Guidance

When generating pages in this system:

1. **The accent (`#000000`) is sacred.** It only appears on CTAs, links, and hover emphasis. Never as a body-text color or large background fill.
2. **Headlines use `system-ui, -apple-system, sans-serif`.** Don't substitute Inter, system-ui, or Apple defaults — load the actual font (Google Fonts via `<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=system-ui,+-apple-system,+sans-serif:wght@400;500;600;700&display=swap">` if available) and reference it in `font-family` declarations.
3. **Sharp, considered borders.** 1px solid `#e5e5e5` does most of the structural work. Avoid `box-shadow` for separation.
4. **Real testimonials only.** The list above is the truth set. Inventing quotes or adding emoji/avatars violates the no-fabrication rule.
5. **Voice rules from `.claude/rules/outbound-copy.md` apply** — no em-dashes, no AI buzzwords, plain English.
