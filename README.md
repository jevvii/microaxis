# MicroAxis — Landing Page Proposals & Tiered Quotation Engine

<div align="center">

![Direction](https://img.shields.io/badge/DIRECTION-CONTEMPORARY_MINIMAL-1B44D8?style=for-the-badge&labelColor=151513)
![Proposals](https://img.shields.io/badge/PROPOSALS-3_STANDALONE_HTML-131310?style=for-the-badge&labelColor=151513)
![Engine](https://img.shields.io/badge/QUOTATION-3--TIER_%2B_ADDON_DETECTION-0C7A43?style=for-the-badge&labelColor=151513)
![Dependencies](https://img.shields.io/badge/DEPENDENCIES-FONTS_ONLY-F5F5F5?style=for-the-badge&labelColor=151513)

<br />

**Small team. Atomic precision. An honest price before the first call.**

[Hub](index.html) · [1 · Spec Sheet](preview-1-spec-sheet.html) · [2 · Monolith](preview-2-monolith.html) · [3 · Five Questions](preview-3-five-questions.html)

</div>

---

## Direction (v2 — researched rework)

This revision replaces the original maximalist dark-HUD concepts with **contemporary minimalism**, grounded in 2025–26 design and pricing-UX research conducted before any code was written:

| Research finding | What it changed |
| :--- | :--- |
| Type is the layout; 1–2 typefaces, hierarchy by size/weight/space | No cards, no shadows, no gradients — hairlines and whitespace do the work |
| 2–3 colors max; the accent reserved for interactive states only | Each proposal has one accent (or none); accents never decorate |
| Motion answers the visitor, not the scroll | No scroll-jacking, no entrance animations on sections; motion only on selection/input |
| Estimate ranges build more trust than fake-precise numbers | Every tier shows a **band range**; the computed figure is itemised line by line |
| 5–9 questions, easy → hard, contact gated last | Proposal 3 is built as exactly that flow; 1 and 2 keep their contact capture after the estimate |
| Grey-on-white contrast failures are the most common accessibility defect | Body text contrast ≥ AA in all three proposals |

Old HUD/cyber proposals were removed in `e2ee` rework commit; see git history for v1.

---

## Brand

**MicroAxis** = *micro* (atomic detail, sub-50ms care) + *axis* (directional clarity, the line a business scales around). The quote configurator is the brand made tangible: precision you can operate.

### The mark

The name, drawn: *micro* — one small, precisely plotted point; *axis* — the coordinate frame it sits in. The dot rests at the golden-section coordinate of both axes (≈ 0.618). Nothing else.

```
microaxis/
├── index.html                        # Hub — includes logo section with local SVG/PNG downloads
├── preview-1-spec-sheet.html         # Proposal 01 · light · document
├── preview-2-monolith.html           # Proposal 02 · dark · monochrome · typographic
├── preview-3-five-questions.html     # Proposal 03 · light · guided 5-step flow
└── logo/
    ├── microaxis-mark.svg            # Mark only (ink)
    ├── microaxis-lockup.svg          # Mark + wordmark (ink)
    └── microaxis-lockup-inverse.svg  # Mark + wordmark (inverse, for dark surfaces)
```

---

## The three proposals

All three are **standalone HTML files** — zero build, zero JS dependencies, Google Fonts only. They share one quotation engine and one data model; what changes is the visual language and the way the form behaves.

### 01 — [Spec Sheet](preview-1-spec-sheet.html) · light · document
Cool paper, ink, one drafting-blue accent used only for interactive states. IBM Plex Sans with Plex Mono reserved for numbers. **Interactivity:** the estimate is a specification document that writes itself — line items with dot leaders, a running subtotal, add-ons appending as rows, the recommended tier stamped on the sheet.

### 02 — [Monolith](preview-2-monolith.html) · dark · monochrome · typographic
Pure black/white/grey — **zero chromatic accent**; every selected state inverts to white. Archivo variable carries display (expanded) and body (normal) in a single family. **Interactivity:** all inputs on one page; a sticky panel holds a ~110px price numeral that re-renders live; tiers are a clickable word-stack.

### 03 — [Five Questions](preview-3-five-questions.html) · light · guided flow
White, ink, one affirmation-green reserved for progress/selected/recommended. Instrument Sans, with Instrument Serif for numerals. **Interactivity:** one question per step, auto-advance on single answers, thin progress line, contact details collected last, then a reveal screen — tier recommendation, all three tier cards with computed prices, add-ons itemised.

---

## The shared quotation engine

Five inputs → complexity score → tier recommendation → itemised estimate inside the tier's fixed band.

```
 inputs: product (base) · modules (count) · launch scale (users) · timeline (×0.95–1.15) · add-ons (separable rows)
 score = product weight + ⌈modules/3⌉ + scale index          →  ≤2 Standard · 3–6 Premium · 7+ Elegant
 estimate = (band floor + modules × $800 × tier factor + scale × $1,500 × tier factor) × timeline + add-ons
```

| Tier | Band | Timeline | Inclusions |
| :--- | :--- | :--- | :--- |
| **Standard** — core launchpad | $16k–24k | 3–4 wks | Full-stack responsive platform · auth, roles & PostgreSQL · automated CI/CD · core SEO & Web Vitals · 14-day warranty |
| **Premium** — accelerated scale | $32k–48k | 6–8 wks | Everything in Standard · atomic design system · AI copilot / workflow sync · Redis caching & edge routing · 30-day dedicated SRE |
| **Elegant** — sovereign engine | $65k–110k | 10–14 wks | Everything in Premium · multi-agent autonomous swarm · 3D WebGL micro-interactions · multi-region failover (99.999%) · principal tech lead + 24/7 SLA |

**Add-on detection** (itemised separately in all three proposals):
Vector RAG & semantic search `+$5,500` · SOC2 & HIPAA hardening `+$4,500` · 3D kinetics & micro-motion `+$3,800` · 24/7 dedicated SRE & SLA `+$4,200`

---

## Services (adapted from Symph's model)

| MicroAxis practice | Equivalent |
| :--- | :--- |
| AI & technology advisory | AI consultancy — audits, feasibility, 14-day prototype |
| Custom AI agents | Agent systems — private vector RAG, guardrails, orchestration |
| Custom software | Web platforms, mobile apps, business systems (Next.js, Go, PostgreSQL) |

---

## Preview

```bash
git clone git@github.com:deutzgalila/microaxis.git
cd microaxis
xdg-open index.html      # or double-click any preview-*.html
```

No server, no build. Each file works offline of any other.

## Accessibility & quality floor

- `prefers-reduced-motion` respected everywhere
- Visible focus states on every interactive element
- Real `<input>`/`<label>` semantics — keyboard operable, screen-reader friendly
- Responsive down to mobile; the estimate region announces changes (`aria-live`)

© 2026 MicroAxis. Service model adapted from Symph; design and copy are original.
