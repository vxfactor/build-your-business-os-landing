# Composed Page Playbook — `index`

_Page type_: **landing page**  
_Archetype_: **lead-magnet**  
_Design dials_: variance=6, motion=5, density=6

This is the single design-discipline reference for this page. The page-builder reads it alongside the brand `DESIGN.md` and the per-page prompt. Sliced from multiple workspace playbooks by `## §` boundaries — see `compose_page_playbook()` in `scripts/build.py` for the slice spec.

---

## SOURCE: `reference/taste-playbook.md` (§3., §7., §11)

# High-Agency Frontend Skill

## §3. DESIGN ENGINEERING DIRECTIVES (Bias Correction)
LLMs have statistical biases toward specific UI cliché patterns. Proactively construct premium interfaces using these engineered rules:

**Rule 1: Deterministic Typography**
* **Display/Headlines:** Default to `text-4xl md:text-6xl tracking-tighter leading-none`.
    * **ANTI-SLOP:** Discourage `Inter` for "Premium" or "Creative" vibes. Force unique character using `Geist`, `Outfit`, `Cabinet Grotesk`, or `Satoshi`.
    * **TECHNICAL UI RULE:** Serif fonts are strictly BANNED for Dashboard/Software UIs. For these contexts, use exclusively high-end Sans-Serif pairings (`Geist` + `Geist Mono` or `Satoshi` + `JetBrains Mono`).
* **Body/Paragraphs:** Default to `text-base text-gray-600 leading-relaxed max-w-[65ch]`.

**Rule 2: Color Calibration**
* **Constraint:** Max 1 Accent Color. Saturation < 80%.
* **THE LILA BAN:** The "AI Purple/Blue" aesthetic is strictly BANNED. No purple button glows, no neon gradients. Use absolute neutral bases (Zinc/Slate) with high-contrast, singular accents (e.g. Emerald, Electric Blue, or Deep Rose).
* **COLOR CONSISTENCY:** Stick to one palette for the entire output. Do not fluctuate between warm and cool grays within the same project.

**Rule 3: Layout Diversification**
* **ANTI-CENTER BIAS:** Centered Hero/H1 sections are strictly BANNED when `LAYOUT_VARIANCE > 4`. Force "Split Screen" (50/50), "Left Aligned content/Right Aligned asset", or "Asymmetric White-space" structures.

**Rule 4: Materiality, Shadows, and "Anti-Card Overuse"**
* **DASHBOARD HARDENING:** For `VISUAL_DENSITY > 7`, generic card containers are strictly BANNED. Use logic-grouping via `border-t`, `divide-y`, or purely negative space. Data metrics should breathe without being boxed in unless elevation (z-index) is functionally required.
* **Execution:** Use cards ONLY when elevation communicates hierarchy. When a shadow is used, tint it to the background hue.

**Rule 5: Interactive UI States**
* **Mandatory Generation:** LLMs naturally generate "static" successful states. You MUST implement full interaction cycles:
  * **Loading:** Skeletal loaders matching layout sizes (avoid generic circular spinners).
  * **Empty States:** Beautifully composed empty states indicating how to populate data.
  * **Error States:** Clear, inline error reporting (e.g., forms).
  * **Tactile Feedback:** On `:active`, use `-translate-y-[1px]` or `scale-[0.98]` to simulate a physical push indicating success/action.

**Rule 6: Data & Form Patterns**
* **Forms:** Label MUST sit above input. Helper text is optional but should exist in markup. Error text below input. Use a standard `gap-2` for input blocks.

## §7. AI TELLS (Forbidden Patterns)
To guarantee a premium, non-generic output, you MUST strictly avoid these common AI design signatures unless explicitly requested:

### Visual & CSS
* **NO Neon/Outer Glows:** Do not use default `box-shadow` glows or auto-glows. Use inner borders or subtle tinted shadows.
* **NO Pure Black:** Never use `#000000`. Use Off-Black, Zinc-950, or Charcoal.
* **NO Oversaturated Accents:** Desaturate accents to blend elegantly with neutrals.
* **NO Excessive Gradient Text:** Do not use text-fill gradients for large headers.
* **NO Custom Mouse Cursors:** They are outdated and ruin performance/accessibility.

### Typography
* **NO Inter Font:** Banned. Use `Geist`, `Outfit`, `Cabinet Grotesk`, or `Satoshi`.
* **NO Oversized H1s:** The first heading should not scream. Control hierarchy with weight and color, not just massive scale.
* **Serif Constraints:** Use Serif fonts ONLY for creative/editorial designs. **NEVER** use Serif on clean Dashboards.

### Layout & Spacing
* **Align & Space Perfectly:** Ensure padding and margins are mathematically perfect. Avoid floating elements with awkward gaps.
* **NO 3-Column Card Layouts:** The generic "3 equal cards horizontally" feature row is BANNED. Use a 2-column Zig-Zag, asymmetric grid, or horizontal scrolling approach instead.

### Content & Data (The "Jane Doe" Effect)
* **NO Generic Names:** "John Doe", "Sarah Chan", or "Jack Su" are banned. Use highly creative, realistic-sounding names.
* **NO Generic Avatars:** DO NOT use standard SVG "egg" or Lucide user icons for avatars. Use creative, believable photo placeholders or specific styling.
* **NO Fake Numbers:** Avoid predictable outputs like `99.99%`, `50%`, or basic phone numbers (`1234567`). Use organic, messy data (`47.2%`, `+1 (312) 847-1928`).
* **NO Startup Slop Names:** "Acme", "Nexus", "SmartFlow". Invent premium, contextual brand names.
* **NO Filler Words:** Avoid AI copywriting clichés like "Elevate", "Seamless", "Unleash", or "Next-Gen". Use concrete verbs.

### External Resources & Components
* **NO Broken Unsplash Links:** Do not use Unsplash. Use absolute, reliable placeholders like `https://picsum.photos/seed/{random_string}/800/600` or SVG UI Avatars.
* **shadcn/ui Customization:** You may use `shadcn/ui`, but NEVER in its generic default state. You MUST customize the radii, colors, and shadows to match the high-end project aesthetic.
* **Production-Ready Cleanliness:** Code must be extremely clean, visually striking, memorable, and meticulously refined in every detail.

## §11 Anti-patterns (Impeccable)

Adapted from [reference/impeccable/brand.md](impeccable/brand.md). Single source of truth for the AI-tells we ban across `/website`. Page-builder reads this block; `website-reviewer` cross-checks against it.

### The slop test
> If a visitor could glance at the page and say "AI made that" without hesitation, it's failed. The bar is distinctiveness — they should ask "how was this made?", not "which AI made this?"

### Reflex-reject fonts (training-data defaults — ban list)

These have flooded AI-generated output. Picking any of them is a reflex, not a decision. Look further (Pangram Pangram, Future Fonts, Klim, Velvetyne, ABC Dinamo) before defaulting:

> Fraunces · Newsreader · Lora · Crimson · Crimson Pro · Crimson Text · Playfair Display · Cormorant · Cormorant Garamond · Syne · IBM Plex (Mono / Sans / Serif) · Space Mono · Space Grotesk · Inter · DM Sans · DM Serif Display · DM Serif Text · Outfit · Plus Jakarta Sans · Instrument Sans · Instrument Serif

Exception: when the *existing* brand has already committed to one of these as its identity, identity-preservation wins. The reflex-reject list applies to **greenfield decisions** and Slot-departure variants — not to surfaces that are already shipping with the font.

### Reflex-reject aesthetic lanes

- **Editorial-typographic.** Display serif (often italic) + small mono labels + ruled separators + monochromatic restraint. Klim-influenced, magazine-cover affectation. Fingerprint: three rule-separated columns, italic Fraunces / Recoleta / Newsreader headline, lowercase track-spaced metadata, no imagery. Reject unless the brief is *literally* a magazine.

### Brand bans (on top of the existing em-dash + AI-buzzword bans)

- Monospace as lazy shorthand for "technical / developer." Reads as costume on non-technical brands.
- Large rounded-corner icons above every heading. Screams template.
- Single-family pages picked by reflex (not voice). One family chosen *deliberately* is fine.
- All-caps body copy. Reserve caps for short labels and headings only.
- Timid palettes + average layouts. Safe = invisible.
- Zero imagery on a brief that implies imagery (restaurant, hotel, food, travel, fashion, photography, hobbyist). Solid-color rectangles where a hero photo belongs are worse than representative stock.
- Defaulting to editorial-magazine aesthetics on non-magazine briefs (display serif + italic + drop caps + broadsheet grid).
- Centered icon-title-subtitle card stacks ("template hero"). Read as scaffolding, not design.
- Purple-to-blue gradients, gradient text, side-stripe borders, nested cards, gray text on color, pure black/white. All AI-tells.

### Brand permissions (use these — don't hedge)

- Ambitious first-load motion: reveals, scroll-triggered transitions, typographic choreography (gated by `motion_intensity` in `design_dials`).
- Single-purpose viewports: one dominant idea per fold, deliberate pacing.
- Typographic risk: enormous display type, unexpected italic cuts, mixed cases, hand-drawn headlines, a single oversize word as the hero.
- Unexpected color strategies. Palette IS voice. A calm brand and a restless brand should not share palette mechanics.
- Art direction per section. Different sections can have different visual worlds if the narrative demands it. Consistency of voice beats consistency of treatment.

### Variation rule (across projects)

Don't converge. If the last brand surface was restrained-on-cream, this one is not. If the last build used display serif, this one doesn't. The reviewer flags drift toward a single house aesthetic across consecutive builds.

---

## SOURCE: `reference/composition-playbook.md` (ALL)

# Composition Playbook

Rules the `build.py` script and its per-page sub-agents must follow to produce sites that look professional, not "AI-generic."

## §The three hard rules

1. **One design system, top to bottom.** Color tokens, type scale, and component styling come from exactly one DESIGN.md. Never mix Linear's colors with Stripe's type. If Nic wants a hybrid vibe, fork a DESIGN.md in `_custom/` first — don't improvise at build time.
2. **Nav + footer are identical across pages.** Every page on a multi-page site shares the same `<header>` and `<footer>` HTML. Use a single partial (duplicated into each page file is fine — static site, no build system). Different nav across pages is the #1 tell of an AI-generated site.
3. **Whitespace is the budget, not the decoration.** If you're tempted to add a gradient, a shadow, an extra icon, or a divider — remove something else first. Cramming more into a section is always worse than less.

## §Section-level rules

- Every section has ONE primary purpose. Hero has one headline + one CTA. Pricing has one comparison. FAQ is not mixed with testimonials.
- **Background alternation** for multi-section pages: choose 2-3 bg values from the DESIGN.md and alternate them. Never 5 different backgrounds in a row.
- **CTAs repeat deliberately.** Hero CTA + final CTA on LPs. Nav CTA + hero CTA + in-section CTAs on marketing sites. Always the same button style and same destination.
- **Copy length follows section type.** Hero headline ≤ 10 words. Sub-headline ≤ 20 words. Feature descriptions ≤ 25 words. Longer than that = move it to a dedicated page.

## §Typography

- Pull font families and weights directly from the DESIGN.md's typography section. Do not substitute. If the DESIGN.md says Inter Variable weight 510, use that — even if most sites use 500.
- Follow the scale. If a DESIGN.md lists H1=72px with -1.584px letter-spacing, don't use H1=64px because "it looks better." It looks better because the whole system is designed around that scale.
- For Google Fonts fallback, map common premium fonts:
  - Inter Variable → `Inter` (Google Fonts)
  - SF Pro / -apple-system → Inter or DM Sans
  - Satoshi / General Sans → DM Sans or Outfit
  - Berkeley Mono → JetBrains Mono

## §Color

- Use the DESIGN.md's exact hex values. Don't "approximate." `#08090a` ≠ `#0a0a0a` ≠ `#000`.
- Brand accent appears only on interactive elements (CTA, links, selected state) and on the one place the DESIGN.md calls out (e.g. Linear uses `#5e6ad2` for CTA bg, not for body text or backgrounds).
- Borders are nearly invisible. `rgba(255,255,255,0.05)` on dark, `#E8E2DE` on light. If you can see them from across the room, they're too strong.

## §Images

- Hero image is either (a) a generated editorial subject (via `generate_images.py`), (b) a product screenshot, or (c) absent entirely. Not three at once.
- Section images are optional. If included, match the DESIGN.md's photo treatment — halftone for silver-ai, cinematic color grade for cursor/revolut, flat for notion.
- Never use stock photos. If you can't generate a real-looking image, use a typographic hero instead.

## §Motion

- Subtle only. Fade-in on scroll, SVG draw-on for signature elements (silver-ai's doodles, Framer's paths).
- No parallax on marketing sites unless the DESIGN.md explicitly specifies it.
- Hover transitions ~200ms eased.

## §Forms

- Lead-magnet archetype uses Flodesk native embed (see `mini-course` skill's pattern — don't build backend forms).
- Contact forms use Netlify Forms (`netlify` attribute on `<form>`) as the default. No server needed.
- SaaS marketing pricing CTAs link to Stripe payment link (see `stripe-payment-link` skill) if Nic provides one.

## §Multi-page coherence

- Build all pages in one session, with the same DESIGN.md context loaded for each page agent.
- After each page is generated, read back the `<head>` and top of `<body>` and diff against the other pages. If nav or font imports differ, fix before moving on.
- Footer always shows: logo, copyright, 3-5 link columns max, one reassuring tagline under the logo.

## §Skim-first

People scan headlines, bullets, and bold phrases. They do not read paragraphs. Full reasoning lives in [`website-principles.md`](website-principles.md) §Skim-first sections.

Three hardest rules:

- Lead every section with a one-sentence claim. Above the H2, not below.
- Paragraphs are three sentences or fewer. Longer = split or convert to a list.
- Bold one phrase per paragraph at most. Bolding everything bolds nothing.

## §Visitor-first copy

Visitors care about their problem, not your origin story. Full reasoning in [`website-principles.md`](website-principles.md) §Visitor-first voice + §Sell the result.

Three hardest rules:

- "You" beats "we". In body copy, "you / your" appears at least as often as "we / us / our / I". In hero copy, target 2:1 or better in the visitor's favor.
- Lead with the problem. Hero owns the problem statement; About owns the origin story (and not above the fold).
- No clever vague headlines. Banned: "Reimagine your workflow", "Unleash creativity", "Where strategy meets execution". The hero sentence answers what you do, who it is for, the outcome.

## §Don't list

- No em-dashes in customer-facing copy. Use " — " → ", " or a period. (Workspace rule.)
- No "Optimize your workflow / Leverage AI / Comprehensive solution" — any of these = rewrite the line.
- No fake testimonials. If Nic hasn't supplied a real quote, use a placeholder marked `TK - replace with real testimonial` and surface it in the build summary.
- No auto-playing video. No auto-scroll carousels. No "33 people signed up in the last hour" widgets.
- No light-mode-forced design system rendered on a dark bg (or vice versa). The DESIGN.md's tone is non-negotiable.

---

## SOURCE: `reference/redesign-playbook.md` (§Upgrade Techniques, §Rules, §Preserve, don't rewrite)

# Redesign Skill

## §Preserve, don't rewrite (the prime directive)

When a site comes in via `--from-url`, the prospect's existing copy is the source of truth. Generated copy must not "improve" their voice into AI slop. Apply only:

1. Strip em-dashes — replace with periods, commas, colons, or parens.
2. Strip banned AI words from [`.claude/rules/plain-english.md`](../../../rules/plain-english.md) — leverage, optimize, comprehensive, cutting-edge, innovative, strategic, synergy, game-changer.
3. Tighten obvious bloat — sentences over 30 words split into two, hedging clauses removed.
4. Preserve their claims, numbers, names, voice cadence, and idiosyncratic phrasing.

Structural changes (adding a pricing section, adding a who-this-is-for filter, reordering for social-proof-early) are allowed. Copy inside new sections pulls from existing scraped content where possible.

**Never** invent new claims. **Never** rewrite a headline that is not broken. **Never** "improve" a sentence that is already clean.

The `copy_preservation_gate` in [`scripts/review_build.py`](../scripts/review_build.py) diffs generated section copy against `site.json.scraped.scraped_copy` per section. Sections with under 60% word-level overlap flag P1. If a specific section genuinely needs a full rewrite, set `site.json.copy_rewrite_authorized: <section_id>: true`.

The website-reviewer also runs a "voice drift" LLM-judge check — sample one paragraph from the scrape, the matching rendered paragraph, score 0-3 on voice cadence match. ≤1 flags.

Source of truth for the principles this enforces: [`website-principles.md`](website-principles.md) §How redesigns differ.

## §Upgrade Techniques

When upgrading a project, pull from these high-impact techniques to replace generic patterns:

### Typography Upgrades
- **Variable font animation.** Interpolate weight or width on scroll or hover for text that feels alive.
- **Outlined-to-fill transitions.** Text starts as a stroke outline and fills with color on scroll entry or interaction.
- **Text mask reveals.** Large typography acting as a window to video or animated imagery behind it.

### Layout Upgrades
- **Broken grid / asymmetry.** Elements that deliberately ignore column structure — overlapping, bleeding off-screen, or offset with calculated randomness.
- **Whitespace maximization.** Aggressive use of negative space to force focus on a single element.
- **Parallax card stacks.** Sections that stick and physically stack over each other during scroll.
- **Split-screen scroll.** Two halves of the screen sliding in opposite directions.

### Motion Upgrades
- **Smooth scroll with inertia.** Decouple scrolling from browser defaults for a heavier, cinematic feel.
- **Staggered entry.** Elements cascade in with slight delays, combining Y-axis translation with opacity fade. Never mount everything at once.
- **Spring physics.** Replace linear easing with spring-based motion for a natural, weighty feel on all interactive elements.
- **Scroll-driven reveals.** Content entering through expanding masks, wipes, or draw-on SVG paths tied to scroll progress.

### Surface Upgrades
- **True glassmorphism.** Go beyond `backdrop-filter: blur`. Add a 1px inner border and a subtle inner shadow to simulate edge refraction.
- **Spotlight borders.** Card borders that illuminate dynamically under the cursor.
- **Grain and noise overlays.** A fixed, pointer-events-none overlay with subtle noise to break digital flatness.
- **Colored, tinted shadows.** Shadows that carry the hue of the background rather than using generic black.

## §Rules

- Work with the existing tech stack. Do not migrate frameworks or styling libraries.
- Do not break existing functionality. Test after every change.
- Before importing any new library, check the project's dependency file first.
- If the project uses Tailwind, check the version (v3 vs v4) before modifying config.
- If the project has no framework, use vanilla CSS.
- Keep changes reviewable and focused. Small, targeted improvements over big rewrites.

---

## SOURCE: `reference/conversion-playbook.md` (ALL)

# Conversion Playbook (CRO)

The CRO contract for `/website`. Page-builder reads this in Phase 6 (M2 PAGE_PLAYBOOK composer slices it by `## §` markers). `review_build.py` enforces the deterministic gates (M2). `website-reviewer` runs the LLM judge layer (M2).

The whole point: a beautiful site that doesn't convert is a portfolio piece, not a business asset. These rules prevent that.

## §Strictness matrix

Different page types tolerate different levels of CRO discipline. The strictness level is set by `pick_type.py` and consumed by every gate below.

| Page type | Strictness | Behavior |
|---|---|---|
| `company` | `relaxed` | Above-fold CTA + footer reassurance only. Editorial pacing wins; CTAs must exist but don't have to be in the first 600px. Social-proof position is not gated. |
| `landing` | `strict` | All 5 gates hard-pass required. Above-fold CTA, social proof in first 2 sections, one primary CTA per section, footer reassurance, friction check. |
| `product` | `strict` | All 5 gates hard-pass. Demo / use-cases substitute for traditional logo bars when the product is too new or audience is too niche to have recognizable logos — surfacing one named customer story counts as social proof. |

Page-builder receives `conversion_strictness` and adapts. Reviewer receives it and chooses which gates fire as P0 vs P1.

## §Gate 1 — Above-the-fold CTA

The visitor must see a clear, primary CTA without scrolling. "First viewport" ≈ first 600-800px on desktop, first 600px on mobile.

**Rules:**
- The hero section must contain at least one primary CTA (button or styled anchor with `class*="cta"|"btn-primary"|"primary"`).
- Verb-led, outcome-led copy. "Get the audit" beats "Submit". "Book a call" beats "Contact us".
- The CTA must be visually dominant in the hero — not a tertiary link in the nav.
- For `company` type: a `relaxed` pass is OK if the nav contains a primary CTA button (not just a text link).
- For `landing` and `product`: hero CTA is mandatory. No exceptions.

**Anti-patterns:**
- Hero with no CTA at all. Visitor has to scroll or read the nav to know what to do.
- Two equally-weighted CTAs in the hero ("Buy now" and "Watch demo" with identical styling). Pick one primary; demote the other.
- Generic copy: "Learn more", "Submit", "Click here", "Sign up" without a clear payoff.

## §Gate 2 — Social proof position

Trust is hard-won and visitors are skeptical. Surface proof early.

**Rules:**
- For `landing`: at least one `social-proof` section must appear in the first 2 sections after `hero` (i.e., it's the second or third section). Logo bar, named customer count, single high-impact testimonial — any of these count.
- For `product`: a logo bar is optional, but at least one of `{logo-bar, named-customer-story, demo-with-attribution, before-after-metric}` must appear in the first 3 sections.
- For `company`: not gated. Social proof can live deeper — testimonials section, dedicated case-studies page, etc.
- Numbers beat names. A logo with "$112k recovered for AcmeCo" beats a logo on its own.
- Specific beats generic. "B2B SaaS founders, 4-25 employees" beats "trusted by businesses everywhere."

**Anti-patterns:**
- Fake logos / invented company names. The reviewer's LLM judge specifically looks for this.
- A "customers" section that's a wall of identical placeholder logos — reviewer flags as TK.
- Stuffing the hero with awards/badges/press logos as a substitute for actual product proof.

## §Gate 3 — One primary CTA per section

Sections that try to do two conversions at once do neither.

**Rules:**
- Every section may have **at most one** primary CTA (button styled as `class*="cta-primary"|"btn-primary"|"primary"`).
- Secondary actions (in-text links, footnotes, "learn more") are unlimited.
- The primary CTA across the whole page should converge: hero CTA = mid-page CTA = final-CTA. Same verb, same destination. Three different "Buy now" / "Book a demo" / "Get the guide" CTAs on one page = three different intents = no conversion.
- Exception: `pricing` section is allowed one primary per tier (max 3) — that's the section's job.

**Anti-patterns:**
- A "features" section with a CTA on every feature card. Reviewer flags as friction.
- Hero with one CTA, mid-page with a different CTA, footer with a third CTA — the page is asking for three different things. Reviewer flags as conversion confusion.

## §Gate 4 — Footer reassurance

The visitor scrolled to the bottom and didn't convert. Last chance to remove a barrier.

**Rules:**
- Footer must contain at least one of:
  - A reassurance line ("No credit card required", "Cancel anytime", "30-day money back", "Free for teams under 5", "Read by X founders weekly")
  - A direct contact path (email or contact form link, not just "support" buried in nav)
  - A risk-reversal phrase tied to the offer
- For `landing`: must contain BOTH a reassurance line AND a direct contact path. Strict.
- For `product`: same — risk reversal is non-negotiable on a paid offer.
- For `company`: a single reassurance line OR contact path is enough.

**Anti-patterns:**
- Footer that's just nav links + copyright. Wasted real estate.
- Footer with "Newsletter signup" as the only conversion path on a page that was selling a paid offer. Misaligned.
- Generic "Contact us if you have questions" with no email, no form, no link.

## §Gate 5 — Friction check (forms + asks)

The number of fields a form asks for is the inverse of how many people fill it out.

**Rules:**
- For `landing` pages with a primary form (lead-magnet, waitlist, demo request): max 4 visible fields. Email-only is the gold standard.
- For `product` pages: max 5 fields if a paid trial / signup form lives on the page.
- For `company` pages: not gated — contact forms can ask what they need (contact forms are exit-funnel, not entry).
- Phone number, company size, role, "how did you hear about us" are conversion killers above the primary CTA. Move them to a post-signup step.
- Hidden fields (UTM tracking, etc.) don't count.

**Anti-patterns:**
- A 9-field form gating the lead magnet. Reviewer auto-fails.
- "Comments" or "Tell us about your project" textarea on a hero CTA. Reserve for a later qualifying step.
- Two-column form layouts that hide fields below the fold and look short until you scroll.

## §Gate 6 — Pricing transparency

Hiding the price wastes time on poor-fit leads. Showing at least a range filters early.

**Rules:**
- For `landing` and `product` types with a paid offer (`site.offer.price` set, or scraped copy contains a currency string): the page must include either a `pricing` section (id/class matching `pricing|plans|tiers|cost|price`) or a `/pricing` page on multi-page archetypes. Hard fail otherwise.
- "Starting from $X" is acceptable. Bespoke quotes are fine — but the order of magnitude must be visible.
- Pair every price with the outcome it produces, not just a feature list.
- For `company` (agency / consultancy): pricing range or "engagements start at $X" is strongly preferred. Soft warning if missing.

**Anti-patterns:**
- Paid offer with no visible price anywhere.
- Pricing table with no outcome attached to any tier — just feature checklists.
- "Contact us for pricing" with no range hint anywhere on the page.

## §Gate 7 — About-page-trust shape

Multi-page builds only. The About page is the second most visited page; visitors land there to decide whether to trust you.

**Rules:**
- Open with the **transformation** you create for clients. Not the founder's origin story.
- At least one of the following must appear in the first viewport: a client metric, a named customer count, a short client story.
- Real faces. Founder photo, team, or at least one client face. AI-generated portraits are banned on the About page.
- Origin story belongs at the bottom, not the top.

**Rule (deterministic, regex-checked):**
- The first 50 words of the About page body must not match autobiographical openers: `I started`, `Our story`, `Founded in`, `Back in <year>`, `My journey`. Flag P1 if matched.

**Anti-patterns:**
- "I started this in 2019 after leaving my agency job…" as the opener.
- About page with no metrics, no stories, no faces — just a wall of bio.
- AI-generated team portraits anywhere on the page.

## §Gate 8 — "Who this is for" filter

Repels wrong-fit visitors early. Saves both sides time.

**Rules:**
- For `landing` and `product` types: must include EITHER a section with id/class matching `who-this-is-for|audience|for-whom` OR a hero sub-header containing an audience qualifier (`for <noun>`, `built for`, `made for`).
- For `company` type: soft warning if missing. Audience qualifier in section 2 is recommended.
- "Trusted by businesses everywhere" without a vertical or size qualifier is flagged.
- A "Who this is for / Who this is not for" two-column section is encouraged — visitors who recognize themselves in the wrong column self-eliminate.

**Anti-patterns:**
- Pages with no audience qualifier anywhere.
- "For everyone" language.
- Generic "Trusted by industry leaders" badge strips without size / vertical context.

## §LLM-judge checks (semantic, run by website-reviewer)

These can't be regex-checked. The reviewer runs Sonnet against the rendered HTML + scraped tone words.

- **Headline clarity.** Is the headline a clear value prop, or vague aspiration? "Get 15-30 qualified calls per month" passes; "Unlock your potential" fails. Reviewer flags fail with a 1-sentence rewrite suggestion.
- **CTA verb match.** Does the CTA verb match user intent at this stage of the funnel? "Buy now" on a cold-traffic landing page is wrong; "Get the audit" is right. Reviewer flags mismatches.
- **Social-proof believability.** Are testimonials / logos believable? Real names + roles + companies, or placeholder lorem? Reviewer cross-checks against `site.scraped` data when present.
- **Offer-promise gap.** Does the page deliver on what the headline promised, or does it pivot to something else mid-scroll? Reviewer flags unfulfilled promises.
- **Skim test.** Read each page using only headers + the first bullet of each section. If the story does not read coherently from those alone, the section needs restructuring.
- **Visitor-first voice ratio.** Count "we / us / our / I" vs "you / your" in body copy. If "we" outnumbers "you", flag. Hero copy needs 2:1 in the visitor's favor.
- **Animation with purpose.** List every motion module on the page; if any module cannot be tied to a content claim, flag it.
- **Industry-cliché.** Does the site look like 80% of B2B SaaS / agency sites? Reviewer scores 0-3 on "differentiation" and flags ≤1. Default-template cues: hero / logo bar / 3-card features / CTA / 4-column footer-link-farm; stock-photo "diverse team" hero; banned AI words in body copy.
- **Sell-the-result.** Does the hero promise a deliverable ("a website", "a brand", "a video") or an outcome ("more qualified calls", "shorter sales cycles")? Deliverable framing fails.
- **Voice drift (redesign mode only).** When `site.json.scraped.scraped_copy` is present, sample one paragraph from the scrape and the matching rendered paragraph. Score 0-3 on voice cadence match; ≤1 → flag with the diff. Catches generated copy that "improves" the prospect into AI slop.

## §Reviewer reporting format

When `review_build.py` fails a deterministic gate, it appends a P0 (strict types) or P1 (relaxed types) issue to `qa/reviewer-report.md` with:
- Gate name
- Page slug + section id
- Specific evidence (line snippet, count, etc.)
- One-line fix suggestion

The page-builder agent reads the report and patches before re-running.

## §What's NOT in this playbook

- SEO best practices — see `seo-audit` skill, run as a separate step after deploy.
- Email capture popup mechanics — see `popup-cro` skill.
- A/B test setup — see `ab-test-setup` skill.
- Analytics wiring — see `analytics-tracking` skill.

These live as separate skills because they're optimization passes after the site exists, not page-build-time concerns.

---

## SOURCE: `reference/website-principles.md` (§The reader, §Skim-first sections, §Visitor-first voice, §Fewer pages, better pages, §About-page-trust shape, §Repel wrong clients, §Sell the result, §How redesigns differ)

# Website Principles

## §The reader

Picture the visitor:

- They are skimming. They are not reading.
- They are skeptical by default. They have seen a hundred sites this week.
- They are not you. They do not care about your origin story until they trust you.
- They will decide within half a second whether your site looks credible.
- They will leave if they cannot tell what you do in five seconds.

Every rule below comes back to one question: would this make the reader stop scrolling, or scroll past?

**What the page-builder should do:** write for that reader. Every section answers either "what is this?", "is this for me?", or "what do I do next?"

**What the reviewer should flag:** sections that read like internal company memos. Sections that need a glossary to follow.

## §Skim-first sections

People do not read top to bottom. They scan headlines, bold phrases, and images. If the value is buried in a paragraph, it is invisible.

Rules:

- Lead every section with a one-sentence claim. Above the H2, not below.
- Headlines state the benefit in plain language. "Get more qualified leads" beats "Unlock your full pipeline potential".
- Paragraphs are three sentences or fewer. Longer = split or convert to a list.
- Bullets win over prose for any list of three or more items.
- Bold one phrase per paragraph at most. Bolding everything bolds nothing.
- Images and icons support the claim. They never decorate.

**What the page-builder should do:** every H2 has the claim as the first child text node. Every paragraph passes the 3-sentence cap. Every supporting list is a `<ul>`, not prose.

**What the reviewer should flag:** "wall of text" sections. Bolding inflation. Headers that are clever and vague (Reviewer's job, see §Clarity).

## §Visitor-first voice

Business owners write copy about themselves, their colors, their layouts. Visitors do not care. Visitors care about one thing: can you solve my problem?

Rules:

- "You" beats "we". Lead with the visitor's problem, then the product, then who you are.
- Hero owns the problem statement. Section 2 owns the outcome. About page owns the credibility.
- Concrete nouns beat abstract ones. "Cold emails that get replies" beats "engagement-optimized communication".
- Use analytics and behavior data to decide layout changes, not personal preference. A/B test headlines, CTAs, sections.

Target voice ratio: "you / your" appears at least as often as "we / us / our / I" in body copy. Hero copy ratio: 2:1 or better in the visitor's favor.

**What the page-builder should do:** when generating copy, draft with "you" pronouns. Only switch to "we" when the section explicitly covers the company (About, Team, Story).

**What the reviewer should flag:** any page where "we" outnumbers "you" in body copy. Heroes that lead with "We help…" or "Our platform…".

## §Fewer pages, better pages

Most sites do not need more pages. They need a few strong ones. Each extra page is a chance for the visitor to get lost.

Rules:

- Top-nav lists 5 items or fewer. Home, Services / Product, About, Resources / Pricing, Contact. That is the upper bound.
- Each page has exactly one primary CTA. Hero CTA = mid-page CTA = footer CTA. Same verb. Same destination.
- Consolidate overlapping content. Two thin pages on the same topic become one strong page.
- Every page makes the next step obvious. If the reader scrolls to the bottom and does not know what to do, the page failed.

**What the page-builder should do:** when building a multi-page archetype, audit the nav before generating. If two pages overlap by more than 50% in topic, merge them. Cap nav at 5 entries.

**What the reviewer should flag:** more than one primary CTA per page. Top-nav with 7+ entries. Pages that end without a CTA.

## §About-page-trust shape

The About page is often the second most visited page on the site. Visitors land there to decide whether to trust you. It is not the place for an origin story.

Rules:

- Lead with the transformation you create for clients. "We help B2B SaaS founders book 15-30 qualified calls a month." Not "Founded in 2019 by Jane after she left her agency job…"
- Add real metrics. Revenue generated for clients, number of clients served, years in market, success rate, average outcome.
- Show real faces. Founder photo, team photos, or at least one client face. AI-generated portraits never appear here.
- Short client stories beat long paragraphs. One sentence per client outcome. Three to five outcomes total.
- Origin story is fine — at the bottom, not the top. It is reassurance, not the lead.

**What the page-builder should do:** scaffold the About page in this order: (1) Transformation H1 + sub, (2) metrics row, (3) client stories, (4) team, (5) founder origin (optional). Reject any About-page draft that opens with "I started…" or "Our story began…".

**What the reviewer should flag:** About pages where the first 50 words are autobiographical. About pages with no metrics, no client stories, no faces. AI-generated team portraits.

## §Repel wrong clients

A great site attracts ideal customers and actively repels bad-fit ones. Filtering early saves both sides time, energy, and money.

Rules:

- State clearly who the offer is for. "Built for B2B SaaS founders, 2-25 employees." "For agencies running 3+ retainer clients." Not "for businesses everywhere."
- A "Who this is for / Who this is not for" section is a feature, not a bug. Visitors who recognize themselves in the wrong column self-eliminate.
- Be honest about price tier. If you are premium, say so. If you are entry-level, say so.
- Industry / size qualifiers in the hero, audience details in section 2, full filter (who-for / who-not-for) optional but recommended.

**What the page-builder should do:** on `landing` and `product` archetypes, scaffold either a `who-this-is-for` section OR a hero sub-header containing an audience qualifier ("for <noun>", "built for", "made for"). On `company`, audience qualifier is recommended in section 2.

**What the reviewer should flag:** landing / product pages with no audience qualifier anywhere. "For everyone" language. "Trusted by businesses everywhere" without a vertical or size qualifier.

## §Sell the result, not "a website"

Nobody wakes up wanting a website. They want more leads, more sales, shorter sales cycles, better customers, a specific outcome. Sell the outcome.

Rules:

- The hero promises an outcome, never a deliverable.
  - Outcome framing: "Book more qualified demos." "Shorten sales cycles by half." "Get 4 ready-to-publish posts every week."
  - Deliverable framing (banned in hero): "We build websites." "A brand identity service." "Custom video production."
- Show before / after scenarios, testimonials with metrics, case-study outcomes.
- Every key section answers one of: "How does this help me get what I want?", "How do I know it works?", "What does it cost me?", "What do I do next?"

**What the page-builder should do:** when drafting hero copy, run the outcome / deliverable test on the first sentence. If the first sentence describes what you make instead of what the visitor gets, rewrite.

**What the reviewer should flag:** any hero that promises a deliverable. Case-study sections that describe the work without the result.

## §How redesigns differ

When a site comes in via `--from-url`, the prospect's existing copy is the source of truth. The principles above apply as **structural nudges**:

- Add a pricing section if missing. Pull dollar figures from anywhere in the scraped copy.
- Add a who-this-is-for filter. Pull audience qualifiers from the scraped hero / about.
- Reorder so social proof lands in section 2-3.
- Swap autobiographical About openers for transformation-led ones — using the prospect's own words about their work.

Copy treatment for redesigns is strict:

- Strip em-dashes (replace with period, comma, colon, or parens).
- Strip banned AI words from [`.claude/rules/plain-english.md`](../../../rules/plain-english.md).
- Tighten obvious bloat (sentences over 30 words split, hedging clauses removed).
- **Preserve** the prospect's claims, numbers, names, voice cadence, and idiosyncratic phrasing.
- **Never** invent new claims. **Never** rewrite a headline that is not broken.
- **Never** "improve" a sentence that is already clean.

The `copy_preservation_gate` in [`scripts/review_build.py`](../scripts/review_build.py) diffs generated section copy against `site.json.scraped.scraped_copy` per section. Sections with under 60% word-level overlap flag P1.

If a section genuinely needs a full rewrite (the original is unsalvageable), set `site.json.copy_rewrite_authorized: <section_id>: true` for that section only.


---

## SOURCE: `reference/impeccable/typography.md` (ALL)

# Typography

## §Classic Typography Principles

### Vertical Rhythm

Your line-height should be the base unit for ALL vertical spacing. If body text has `line-height: 1.5` on `16px` type (= 24px), spacing values should be multiples of 24px. This creates subconscious harmony; text and space share a mathematical foundation.

### Modular Scale & Hierarchy

The common mistake: too many font sizes that are too close together (14px, 15px, 16px, 18px...). This creates muddy hierarchy.

**Use fewer sizes with more contrast.** A 5-size system covers most needs:

| Role | Typical Ratio | Use Case |
|------|---------------|----------|
| xs | 0.75rem | Captions, legal |
| sm | 0.875rem | Secondary UI, metadata |
| base | 1rem | Body text |
| lg | 1.25-1.5rem | Subheadings, lead text |
| xl+ | 2-4rem | Headlines, hero text |

Popular ratios: 1.25 (major third), 1.333 (perfect fourth), 1.5 (perfect fifth). Pick one and commit.

### Readability & Measure

Use `ch` units for character-based measure (`max-width: 65ch`). Line-height scales inversely with line length: narrow columns need tighter leading, wide columns need more.

**Non-obvious**: Light text on dark backgrounds needs compensation on three axes, not just one. Bump line-height by 0.05–0.1, add a touch of letter-spacing (0.01–0.02em), and optionally step the body weight up one notch (regular → medium). The perceived weight drops across all three; fix all three.

**Paragraph rhythm**: Pick either space between paragraphs OR first-line indentation. Never both. Digital usually wants space; editorial/long-form can justify indent-only.

## §Font Selection & Pairing

The tactical selection procedure and the reflex-reject list live in [reference/brand.md](brand.md) under **Font selection procedure** and **Reflex-reject list** (loaded for brand-register tasks). The rest of this section covers the adjacent knowledge: anti-reflex corrections, system font use, and pairing rules.

### Anti-reflexes worth defending against

- A technical/utilitarian brief does NOT need a serif "for warmth." Most tech tools should look like tech tools.
- An editorial/premium brief does NOT need the same expressive serif everyone is using right now. Premium can be Swiss-modern, can be neo-grotesque, can be a literal monospace, can be a quiet humanist sans.
- A children's product does NOT need a rounded display font. Kids' books use real type.
- A "modern" brief does NOT need a geometric sans. The most modern thing you can do is not use the font everyone else is using.

**System fonts are underrated**: `-apple-system, BlinkMacSystemFont, "Segoe UI", system-ui` looks native, loads instantly, and is highly readable. Consider this for apps where performance > personality.

### Pairing Principles

**The non-obvious truth**: You often don't need a second font. One well-chosen font family in multiple weights creates cleaner hierarchy than two competing typefaces. Only add a second font when you need genuine contrast (e.g., display headlines + body serif).

When pairing, contrast on multiple axes:
- Serif + Sans (structure contrast)
- Geometric + Humanist (personality contrast)
- Condensed display + Wide body (proportion contrast)

**Never pair fonts that are similar but not identical** (e.g., two geometric sans-serifs). They create visual tension without clear hierarchy.

### Web Font Loading

The layout shift problem: fonts load late, text reflows, and users see content jump. Here's the fix:

```css
/* 1. Use font-display: swap for visibility */
@font-face {
  font-family: 'CustomFont';
  src: url('font.woff2') format('woff2');
  font-display: swap;
}

/* 2. Match fallback metrics to minimize shift */
@font-face {
  font-family: 'CustomFont-Fallback';
  src: local('Arial');
  size-adjust: 105%;        /* Scale to match x-height */
  ascent-override: 90%;     /* Match ascender height */
  descent-override: 20%;    /* Match descender depth */
  line-gap-override: 10%;   /* Match line spacing */
}

body {
  font-family: 'CustomFont', 'CustomFont-Fallback', sans-serif;
}
```

Tools like [Fontaine](https://github.com/unjs/fontaine) calculate these overrides automatically.

**`swap` vs `optional`**: `swap` shows fallback text immediately and FOUT-swaps when the web font arrives. `optional` uses the fallback if the web font misses a small load budget (~100ms) and avoids the shift entirely. Pick `optional` when zero layout shift matters more than seeing the branded font on slow networks.

**Preload the critical weight only**: typically the regular-weight body font used above the fold. Preloading every weight costs more bandwidth than it saves.

**Variable fonts for 3+ weights or styles**: a single variable font file is usually smaller than three static weight files, gives fractional weight control, and pairs well with `font-optical-sizing: auto`. For 1–2 weights, static is fine.

## §Modern Web Typography

### Fluid Type

Fluid typography via `clamp(min, preferred, max)` scales text smoothly with the viewport. The middle value (e.g., `5vw + 1rem`) controls scaling rate (higher vw = faster scaling). Add a rem offset so it doesn't collapse to 0 on small screens.

**Use fluid type for**: Headings and display text on marketing/content pages where text dominates the layout and needs to breathe across viewport sizes.

**Use fixed `rem` scales for**: App UIs, dashboards, and data-dense interfaces. No major app design system (Material, Polaris, Primer, Carbon) uses fluid type in product UI; fixed scales with optional breakpoint adjustments give the spatial predictability that container-based layouts need. Body text should also be fixed even on marketing pages, since the size difference across viewports is too small to warrant it.

**Bound your clamp()**: keep `max-size ≤ ~2.5 × min-size`. Wider ratios break the browser's zoom and reflow behaviour and make large viewports feel like the page is shouting.

**Scale container width and font-size together** so effective character measure stays in the 45–75ch band at every viewport. A heading that widens faster than its container drifts out of the comfortable measure at the top end.

### OpenType Features

Most developers don't know these exist. Use them for polish:

```css
/* Tabular numbers for data alignment */
.data-table { font-variant-numeric: tabular-nums; }

/* Proper fractions */
.recipe-amount { font-variant-numeric: diagonal-fractions; }

/* Small caps for abbreviations */
abbr { font-variant-caps: all-small-caps; }

/* Disable ligatures in code */
code { font-variant-ligatures: none; }

/* Enable kerning (usually on by default, but be explicit) */
body { font-kerning: normal; }
```

Check what features your font supports at [Wakamai Fondue](https://wakamaifondue.com/).

### Rendering polish

```css
/* Even out heading line lengths (browser picks better break points) */
h1, h2, h3 { text-wrap: balance; }

/* Reduce orphans and ragged endings in long prose */
article p { text-wrap: pretty; }

/* Variable fonts: pick the right optical-size master automatically */
body { font-optical-sizing: auto; }
```

**ALL-CAPS tracking**: capitals sit too close at default spacing. Add 5–12% letter-spacing (`letter-spacing: 0.05em` to `0.12em`) to short all-caps labels, eyebrows, and small headings. Real small caps (via `font-variant-caps`) need the same treatment, slightly gentler.

## §Typography System Architecture

Name tokens semantically (`--text-body`, `--text-heading`), not by value (`--font-size-16`). Include font stacks, size scale, weights, line-heights, and letter-spacing in your token system.

## §Accessibility Considerations

Beyond contrast ratios (which are well-documented), consider:

- **Never disable zoom**: `user-scalable=no` breaks accessibility. If your layout breaks at 200% zoom, fix the layout.
- **Use rem/em for font sizes**: This respects user browser settings. Never `px` for body text.
- **Minimum 16px body text**: Smaller than this strains eyes and fails WCAG on mobile.
- **Adequate touch targets**: Text links need padding or line-height that creates 44px+ tap targets.

---

**Avoid**: More than 2-3 font families per project. Skipping fallback font definitions. Ignoring font loading performance (FOUT/FOIT). Using decorative fonts for body text.

---

