# Page Build Prompt — index

Build the HTML/CSS/JS for this page inside `build/index.html`.

## Business brief
- Name: Build Your Business OS
- Description: Free email-gated course landing page. Twelve paste-the-prompt steps that turn Claude Code or Codex into a workspace that runs your business.
- Archetype: Lead magnet / waitlist (lead-magnet)
- Design system: _scraped

## Design system spec
Read the full DESIGN.md at:
`/Users/niclassilver/Projects/Business/active/websites/build-your-business-os-landing/build/_design/DESIGN.md`

**Use EVERY token verbatim** — exact hex colors, exact type scale, exact component styling.
Never "approximate."

## Composed page playbook (READ THIS — single design-discipline reference for this page)
`/Users/niclassilver/Projects/Business/active/websites/build-your-business-os-landing/build/_design/PAGE_PLAYBOOK_index.md`

This file is sliced for the **Landing page** page type. It bundles taste rules + composition + redesign upgrade techniques + conversion playbook + typography + (for `landing` / `product`) motion / cinematic — pre-cut so you don't have to dereference six different files. The composition playbook's hard rules + the conversion playbook's CRO gates are inside it.

## Conversion strictness
This page is built under **`strict`** strictness (set by `pick_type.py` from `--type`). The deterministic CRO gates in `review_build.py` (above-fold CTA, social-proof position, one primary CTA per section, footer reassurance, friction check) fire as **P0 hard fails** when strictness is `strict`, and as **P1 warnings** when `relaxed`. Build for the gates regardless — relaxed just means the run doesn't block on them.

## Design source — what the DESIGN.md is for, and what it ISN'T

The DESIGN.md is the prospect's own brand (when `_scraped`) or a generic visual reference (when a library system was passed via `--system`). Either way, you lift **visual tokens** from it — colors, type scale, spacing, button/card styling, motion timing. That's it.

You do NOT lift:
- **Nav structure / labels** — if the DESIGN.md describes a SaaS product nav with "Log in / Sign up / Pricing / Docs / Changelog", and the brief is a consultancy / agency / service business, render the nav for the brief, not the design system. Marketing consultancies don't have logins.
- **CTA copy** — "Start free trial", "Get a demo", "Request access" only belong on a real SaaS product. A consultancy CTA is "Book a call", "Get in touch", "Start a project". Match the brief.
- **Page-level layout patterns** — pricing tables, app dashboards, comparison grids, integration logos. Only render these when the brief explicitly calls for them.
- **Section types** — feature grids, testimonial carousels, FAQ accordions are universal; SaaS-specific patterns (changelog feed, integration directory, status page) are not. Use only what the archetype's section list specifies.

If the brief says "marketing consultancy for biotech", the nav has the consultancy's actual links (Services / About / Contact). Period.

## Sections to render (in order)
- **hero** — What the user gets + who it's for + the email form. Form is above the fold. The headline describes the outcome, not the deliverable.

- **what-you-get** — 3-5 bullet points describing exactly what's inside.
- **who-its-for** — 2-3 "this is for you if..." statements to qualify the audience.
- **about-author** — Short credibility paragraph — why trust this source.
- **social-proof** — Testimonials or numeric proof that this works.
- **secondary-cta** — Repeated email form at bottom with a reframed headline.
- **footer** — Minimal — copyright + privacy link.

## Shared layout
- Header nav items: None
- Header CTA: None
- Footer columns: None

## Copy for this page (from the copywriting skill)
```json
{
  "hero": {
    "eyebrow": "FREE COURSE",
    "headline": "Build the AI-Native Business OS Nic Silver runs every day.",
    "subheadline": "Twelve paste-the-prompt steps that run under Claude Code or Codex, backed by public GitHub repos for every section.",
    "primary_cta": {
      "label": "Get the course",
      "href": "#signup"
    }
  },
  "benefits": {
    "eyebrow": "WHAT YOU GET",
    "heading": "A workspace that already knows your business.",
    "items": [
      "A workspace where Claude already knows your brand voice.",
      "Search that pulls from the live web, not training data.",
      "A second brain that grows automatically as you work.",
      "Inbox, calendar, Drive, and YouTube uploads all running through one OAuth.",
      "Plans, audits, and reports rendered as real HTML pages, not chat scrollback.",
      "Skills that stay under your token budget even when they run heavy.",
      "Hard guardrails on dangerous commands and secrets, automatic.",
      "Every skill works under both Claude Code and Codex CLI."
    ]
  },
  "whats_inside": {
    "eyebrow": "TWELVE SECTIONS",
    "heading": "Twelve copy-pastes. One Business OS.",
    "sub": "Each section is one prompt. The setup builds itself.",
    "sections": [
      {
        "num": "01",
        "title": "Set Up Your Business OS the Right Way",
        "summary": "Lay down the workspace your AI will live in. Get this right once and every skill slots in."
      },
      {
        "num": "02",
        "title": "Make Claude Code and Codex Cross-Compatible",
        "summary": "Never lose a day because one runtime is down. Same workspace, both runtimes."
      },
      {
        "num": "03",
        "title": "Add a Search Stack That Actually Works",
        "summary": "Stop your AI from making things up. Three tools turn it into a real researcher."
      },
      {
        "num": "04",
        "title": "Build a Second Brain with the Wiki",
        "summary": "Give your AI a memory that grows with your business. Stop re-explaining things."
      },
      {
        "num": "05",
        "title": "Connect Google Workspace",
        "summary": "Gmail, Calendar, Drive, YouTube. Once your AI sees them, it starts running your week."
      },
      {
        "num": "06",
        "title": "Train Claude on Your Voice",
        "summary": "Every draft sounds like you wrote it. First drafts at 80%, not 20%."
      },
      {
        "num": "07",
        "title": "Lock Your Visual Brand",
        "summary": "Every image, site, header looks like the same brand. Consistency builds trust."
      },
      {
        "num": "08",
        "title": "Build Websites That Don't Look AI-Generated",
        "summary": "Ship real-looking sites without hiring a designer. Principles plus a vision-model QA pass."
      },
      {
        "num": "09",
        "title": "Make Your Workspace Token-Efficient",
        "summary": "Cut your AI bill by 85% on the workflows you run most. Three small patterns, big savings."
      },
      {
        "num": "10",
        "title": "Generate HTML Reports Instead of Walls of Text",
        "summary": "Anything you'll read twice deserves a real document. One command makes it automatic."
      },
      {
        "num": "11",
        "title": "Compress Agent-to-Agent Handoffs",
        "summary": "Squeeze more cost out when agents talk to each other behind the scenes. Quiet utility, real savings."
      },
      {
        "num": "12",
        "title": "Lock It Down and Let It Improve Itself",
        "summary": "Safe by default, smarter every week. Install once, it keeps working."
      }
    ]
  },
  "audience_filter": {
    "eyebrow": "WHO THIS IS FOR",
    "heading": "Built for operators, not engineers.",
    "items": [
      "Solo founders running their own business.",
      "Operators who want AI working inside the company, not theoretical.",
      "People comfortable pasting a prompt into a terminal once or twice."
    ]
  },
  "why_nic": {
    "eyebrow": "WHY NIC SILVER",
    "heading": "The same workspace I run my own consultancy from.",
    "body": "Silver AI Consulting builds AI systems for marketing agencies and small businesses. This is the workspace I ship that work from. I packaged the foundation up because every client kept asking how to get started. You're welcome to copy it."
  },
  "signup": {
    "eyebrow": "GET THE COURSE",
    "heading": "Free. No credit card. The course link arrives in your inbox in under a minute.",
    "sub": "Drop your email below. You'll get a short welcome and a direct link to all twelve sections.",
    "embed_placeholder": "FLODESK_FORM_EMBED"
  },
  "faq": {
    "eyebrow": "FAQ",
    "heading": "Common questions.",
    "items": [
      {
        "q": "What is this?",
        "a": "Twelve paste-the-prompt steps that set up an AI-native workspace. Each step has a public GitHub repo behind it, so you can read the source before running it."
      },
      {
        "q": "Do I need to code?",
        "a": "No. Each section is a single prompt you paste into Claude Code or Codex. The runtime does the work."
      },
      {
        "q": "What does it cost?",
        "a": "Free. The course is the foundation. The polished Skills Library at skills.nicsilver.com is the paid layer on top."
      },
      {
        "q": "Claude Code vs Codex?",
        "a": "Both work. Five of the twelve sections also ship a Cowork-compatible zip if you're on Claude Cowork."
      },
      {
        "q": "What if I get stuck?",
        "a": "Reply to the welcome email or book a call. The course is free; a quick reply costs nothing."
      }
    ]
  },
  "closing_cta": {
    "eyebrow": "GET STARTED",
    "heading": "Twelve prompts away from an AI-native business.",
    "primary_cta": {
      "label": "Send me the course",
      "href": "#signup"
    }
  },
  "footer": {
    "owner": "Nic Silver",
    "company": "Silver AI Consulting",
    "year": "2026",
    "links": [
      {
        "label": "nicsilver.com",
        "href": "https://nicsilver.com"
      },
      {
        "label": "Skills Library",
        "href": "https://skills.nicsilver.com"
      }
    ]
  }
}
```

## Output requirements
- Single HTML file at `build/index.html` with inline `<style>` block — no external CSS except what's already in `build/assets/`.
- Include `<link rel="stylesheet" href="/assets/reset.css">` at the top of `<head>`.
- Include any Google Fonts imports matching the DESIGN.md typography.
- All interactive CSS (hover, focus) must match the DESIGN.md component rules.
- Mobile breakpoints at 768/1024/1440 minimum. Mobile-first.
- No React, no build step, no JS framework. Vanilla only. Progressive enhancement.
- No placeholder Lorem ipsum. If a copy field is missing, insert `TK - <what's needed>` so it surfaces in QA.

## Hero above-the-fold rule (P0 — applies to every page, not just variants)

**The hero section's first visible content must land within 100px of the bottom of the nav.** Eyebrow line, headline, or whichever element comes first — it lands fast, immediately under the nav. NEVER apply 6rem section-padding-top to the hero section itself; that pattern (which Impeccable's spatial-design.md calls for between *internal* sections) creates a CRO violation when applied to the hero. Above-the-fold attention is the most expensive real estate on the page; do not waste it on whitespace.

CSS pattern:
```css
.hero { padding: 1.5rem 0 6rem; /* small top, generous bottom */ }
@media (min-width: 768px) { .hero { padding: 2rem 0 8rem; } }
```

NOT:
```css
.hero { padding: 6rem 0; }  /* WRONG — hides the headline below the fold */
```

Other sections (services, proof, case-study, process, final-cta) DO get the symmetric `padding: 6rem 0` between-section spacing — just not the hero.

## Fabrication ladder (non-negotiable — overrides any blueprint default)

The page-builder's job is to compose the prospect's REAL claims into a polished page. Inventing names, numbers, or structure the live site doesn't carry is a brand-trust violation — they spot it instantly when they review the redesign.

### Forbidden patterns (do NOT generate these unless verbatim in scraped copy)

- **Invented service tiers / package names**: "90-Day Foundation", "12-Week Sprint", "Growth Tier", "Foundation Package". If the prospect lists "consulting" or "marketing strategy" as a flat list, render it as a flat list. Don't compose tiered packages.
- **Invented values blocks**: "We measure what matters", "We move at your pace", "We learn the science first". The "We <verb> the <noun>" pattern in lists of 3+ items is the AI tell — it reads like a manifesto written by a bot. If the prospect doesn't have a values manifesto on the live site, the redesign doesn't either.
- **Invented numbered process steps**: "01 / Discovery → 02 / Strategy → 03 / Execution" unless the prospect's site shows these exact steps. If the live site has 2 process steps, the redesign has 2. If it has none, the section is a TK or gets dropped.
- **Invented stats**: "24h response time", "98% client satisfaction", "4x faster" — never make these up. Either pull a real number from the scrape or skip the stat.
- **Invented channel descriptions**: "Best for sharing a deck", "When you want a quick reply". These read like a UI-copy dictionary auto-fill. Real contact pages just list the email/phone.
- **The logo is NEVER a section image**. The brand logo (any `source-logo*.webp` / `source-logo*.png` file) lives in the nav and the footer. Period. Do NOT use it as a hero photo, a case-study photo, a tagline-tile background, an "about" section image, or a fill for any image slot that has no real photo. If a section needs an image and no real photo is available in `build/assets/source-*.webp`, mark the slot `TK - <what's needed>` and DROP the image entirely — leave the section text-only or omit the section. A logo rendered at hero-tile scale is the failure mode that kills brand trust faster than any other.

### Legal alternatives

- Paraphrase scraped paragraphs, light polish on phrasing. The scraped copy is the source of truth.
- List scraped deliverables flat: a bullet list of what the prospect already lists, in their words and order.
- Drop sections that have no scraped source. If the prospect doesn't have a testimonial, the testimonial section gets dropped, not stubbed with placeholder quotes.
- Mark `TK - <what's needed>` and surface in QA. When a section is part of the archetype but the prospect's content doesn't fill it, write `TK - need <real services list / real founder bio / real client logos>`. The reviewer agent picks these up.

### One-of-X rule

If the live site has only one of X, the redesign also has only one of X.
- Live site has one CTA email address? Redesign has one, not three "channel options."
- Live site lists one office location? Redesign lists one, not a fabricated map of three.
- Live site has one service? Redesign has one card on the services page, not three tiered packages.

The reviewer subagent runs deterministic gates (`gate_invented_tiers`, `gate_values_block`) against the rendered HTML. If they fire, the build fails with `high=N` — patch the offending sections before re-running. The patcher annotates `<!-- FABRICATION SUSPECT -->` on flagged elements so they're easy to find.

## Voice rules (non-negotiable)
- No em-dashes in any visible copy.
- No AI buzzwords: "optimize", "leverage", "cutting-edge", "comprehensive", "innovative", "strategic".
- No AI-phrase auto-fill: "what we cover", "ready when you are", "tell us where", "pick the channel".
- Short sentences. Plain English. Sound like a real human wrote it.
- See `.claude/rules/outbound-copy.md` for the full brand voice.

## Nav + asset path conventions (non-negotiable)

The page-builder agents have shipped two recurring 404 / inconsistency bugs. Both are auto-gated by `scripts/review_build.py` now, but composing it right the first time saves a re-run.

### Nav hrefs — always trailing-slash absolute paths
Every nav link, footer link, CTA, and inline cross-page reference uses **`/services/`, `/about/`, `/contact/`** — never bare `/services` or relative `services/`. Trailing slashes resolve cleanly under Python's local `http.server`, GitHub Pages, AND Netlify; bare-path hrefs only work in some of those. The home anchor stays as `/`.

Use ONLY the following nav items on this build (filtered to pages we actually shipped — anything else is a 404):
(none)

If a section needs a "view all" link to a page not in that list, render the link as plain text — never a broken href.

### Asset paths — always absolute `/assets/...`
Every `<img src=…>`, `<link href=…>`, `<script src=…>`, and inline `url(...)` reference to a file under `assets/` must start with a leading slash: **`/assets/source-logo.png`**, not `assets/source-logo.png`. Absolute paths resolve identically from `/index.html`, `/services/`, `/about/`, etc.; relative paths break on subpages.

The `<link rel="stylesheet" href="/assets/reset.css">` line is the canonical example — every other asset reference matches that shape.

## Scroll-reveal convention (cross-page consistency)
If you wire IntersectionObserver-based scroll reveals on this page, use these exact class names so the QA probe and other pages stay aligned:

- Base class: `.reveal` (initial hidden state — `opacity: 0; transform: translateY(...)`).
- Promoted class: `.reveal.is-visible` (final state — `opacity: 1; transform: none`). **NOT `.visible`** — every page in this build uses `.is-visible`.
- Stagger delays: `style="--delay: 100ms"` (or `.reveal-delay-N` modifier) — your call, but pick one and stick with it on this page.
- JS pattern (verbatim):

```js
const revealEls = document.querySelectorAll('.reveal');
const revealObserver = new IntersectionObserver((entries) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) {
      entry.target.classList.add('is-visible');
      revealObserver.unobserve(entry.target);
    }
  });
}, { threshold: 0.15, rootMargin: '0px 0px -10% 0px' });
revealEls.forEach((el) => revealObserver.observe(el));
```

The animation-QA agent probes `.reveal.is-visible` at 60% scroll and flags class-name divergence as a build failure.


## Available image slots (use these filenames verbatim)

- `/assets/index-hero.webp` — hero slot for this page (Wavespeed-generated, branded).

Rules:
- Reference each `<slug>-<section>.webp` slot ONCE per page. Do not reuse the same WebP across multiple sections.
- `source-hero.png` is a fallback only — prefer the per-section slot if it exists for this page.
- Never substitute a CSS text tile or initial in place of `source-logo.png`. The logo is real and goes in every header + footer.
- Decorative images get a short, factual `alt`. Never `alt=""` on hero or feature imagery — screen readers need it.
- For REAL PHOTO slots, alt text describes what's actually in the photograph (a person, a desk, a product). For Wavespeed-generated slots, alt text describes the conceptual subject.


## Taste + redesign rules (READ BEFORE WRITING ANY HTML)

These three documents are non-negotiable and override any default LLM bias toward "safe" three-equal-cards layouts:

1. **`/Users/niclassilver/Projects/Business/.claude/skills/website/reference/composition-playbook.md`** — the three hard rules (one design system top-to-bottom; nav + footer byte-identical across pages; whitespace is the budget). Section-level rules. Don't list.
2. **`/Users/niclassilver/Projects/Business/.claude/skills/website/reference/taste-playbook.md`** — design dials, hardware acceleration, anti-Inter-everywhere typography, the LILA BAN (no AI-purple gradients), the THREE-COLUMN-CARD BAN, perpetual micro-interactions, the AI Tells forbidden patterns list. Sections 3–7 specifically.
3. **`/Users/niclassilver/Projects/Business/.claude/skills/website/reference/redesign-playbook.md`** — the audit list: what to swap (Inter → Geist/Outfit/Cabinet Grotesk/Satoshi when the design system permits; pure black → off-black; symmetric → asymmetric; equal-card grids → zig-zag/masonry). Section "Layout" + "Component Patterns" specifically.

Read all three before composing. Then return to this prompt.

## Design dials (target values for this build)

These knobs were set in `site.json.design_dials` and tune how every section is composed. Treat them as a contract — sections that ignore them fail QA.

| Dial | Target | What that means here |
|---|---|---|
| `design_variance` | **6 / 10** | offset / asymmetric — fractional grids (`grid-template-columns: 5fr 7fr`), zig-zag features, left-aligned headers over centered data, intentional whitespace gaps. |
| `motion_intensity` | **5 / 10** | fluid CSS — `transition: transform 200ms cubic-bezier(0.16, 1, 0.3, 1)` on interactive elements. Stagger reveals with `animation-delay` cascades. `transform`/`opacity` only — never `width`/`height`/`top`/`left`. |
| `visual_density` | **6 / 10** | standard agency rhythm — 6rem section padding desktop, 3.5rem mobile. 1.5–2rem element gaps. Deliberate but not airy. |

Rationale: default values.

### Hard targets, not suggestions
- Variance ≥ 4: **NO centered-Hero/H1 layouts.** Force split-screen, left-aligned-content with right-aligned asset, or asymmetric whitespace per the taste-playbook Rule 3.
- Variance ≥ 7: **NO 3-equal-cards feature row.** Use 2-column zig-zag, asymmetric grid, masonry, or a horizontal-scroll strip per the redesign-playbook "Layout" section.
- Motion ≥ 5: **Embed perpetual micro-interactions** (pulse on status dots, float on hero accents, shimmer on placeholders). Use `transform`/`opacity` only. Per taste-playbook §5, never animate `top/left/width/height`.
- Motion ≥ 7: **Add scroll-triggered reveals** (stagger lists with `animation-delay: calc(var(--index) * 100ms)`, fade-and-translate sections into view).
- Density 4–6: **Standard agency rhythm** — 6rem section padding desktop, 1.5–2rem element gaps. Not airy, not packed.

### Variance-7 worked example (zig-zag features instead of 3-equal-cards)

```html
<section class="features">
  <div class="features__container">
    <article class="features__row features__row--right">
      <div class="features__media">
        <img src="..." alt="...">
      </div>
      <div class="features__copy">
        <span class="eyebrow">01 / Foundation</span>
        <h3>...</h3>
        <p>...</p>
      </div>
    </article>
    <article class="features__row features__row--left">
      <div class="features__copy">
        <span class="eyebrow">02 / Growth</span>
        <h3>...</h3>
        <p>...</p>
      </div>
      <div class="features__media">
        <img src="..." alt="...">
      </div>
    </article>
  </div>
</section>

<style>
  .features__row {
    display: grid;
    grid-template-columns: 5fr 7fr;  /* fractional, not 50/50 */
    gap: 4rem;
    align-items: center;
    margin-bottom: 6rem;
  }
  .features__row--left { grid-template-columns: 7fr 5fr; }
  @media (max-width: 768px) {
    .features__row,
    .features__row--left { grid-template-columns: 1fr; gap: 1.5rem; }
  }
</style>
```

The rhythm: alternating left/right with **5fr/7fr or 7fr/5fr** (asymmetric, never 6/6) creates visual variance without breaking responsiveness. Mobile collapses to single column per the taste-playbook MOBILE OVERRIDE rule.
