---
name: Design Reference — generalintelligencecompany.com
description: Boutique applied-AI-lab aesthetic. Editorial cream surfaces, signature PP Mondwest display serif paired with bespoke "af" sans + Geist Mono, hand-drawn sun icon flourish, chevron list pattern. Use when referencing this aesthetic for AI labs / studio brands that want literary-warmth instead of generic SaaS.
type: reference
url: https://www.generalintelligencecompany.com/
---
# generalintelligencecompany.com — Full Design Reference
**URL:** https://www.generalintelligencecompany.com/ (careers: `/careers`)
**Product:** Cofounder — multi-agent coordination software ("automate your business with natural language")
**Tagline:** "We're building tools for businesses that run themselves" / "Agentic companies are on the horizon, and we're building them"
**Vision:** *"A world where anyone with an idea can start a business as easy as playing a video game."*
**Audience:** Ambitious entrepreneurs / AI builders; secondary: AI engineering candidates (the careers page leans into this)
**Tech stack:** Next.js + Tailwind v4 (`oklch` colors, full `--radius-*` token ladder)

---

## Aesthetic / Mood
**Boutique applied-AI-lab with literary warmth.** Where most AI startups default to a sans-serif marketing template, GIC leans on a **single romantic display serif (PP Mondwest)** as its signature voice — paired with a custom sans ("af") for body and Geist Mono for technical accents. The result reads like a small studio with taste: editorial more than corporate, warm more than slick.

Surfaces are barely-tinted cream-greens (`#f9faf7`, `#eef1ed`, `#dee2de`) — a warm neutral ladder that avoids the "Notion white-on-white" cliché. A **hand-drawn sun glyph** floats above the headline as a non-functional decorative mark — signaling "we have a designer with a pen, not just a Figma library."

If guild.ai is "warm warehouse editorial" and adaline.ai is "sage botanical," GIC is "Mondwest morning paper" — the same warmth, but with serif ornamentation that reads as a small applied-AI lab rather than infrastructure software.

---

## Typography — the signature

Three custom fonts loaded as `woff2`:

| Token | Font | Usage |
|---|---|---|
| `--font-mondwest` | **PP Mondwest** (Pangram Pangram) | **Display serif — the headline voice.** Romantic transitional/old-style serif with that recognisable "literary AI lab" feel. Used at hero scale on every marquee headline (e.g. *"We're building tools for businesses that run themselves"*). |
| `--font-af-foundary` | **af** (variable, weight 100–900) | Body text, UI labels, navigation. A clean grotesque sans — the workhorse. |
| `--font-geist-mono` | Geist Mono | Technical accents, code, occasional metadata labels |

**Why this matters:** PP Mondwest is the design fingerprint. It's the same family showing up across boutique AI/design studios in 2025 (Linear-adjacent indie tier) — it instantly signals "small, tasteful, deliberate." Reproducing this aesthetic without that exact font (or a close cousin like PP Editorial Old, GT Super Display, or Reckless Neue) won't land.

**Fallback chain:**
- `af Fallback`: Arial-mapped (`ascent-override: 101.79%; descent-override: 30.54%; size-adjust: 98.24%`)
- `ppmondwest Fallback`: Arial-mapped (`ascent-override: 88.47%; size-adjust: 90.41%`)

---

## Color Palette (Tailwind v4 tokens + ranked extracts)

### Brand neutrals (warm-cream surface ladder, slight green tint)
| Value | Usage |
|---|---|
| `#fefffc` | Top elevation surface |
| `#f9faf7` | Page background — the dominant cream |
| `#f3f5f2` | Alt surface |
| `#eef1ed` | Recessed surface |
| `#dee2de` | Card borders, dividers |

### Text scale
| Value | Usage |
|---|---|
| `#000000` | Primary headlines (when on cream) |
| `#2c2c2c` | Body text (off-black) |
| `#454040` / `#444141` | Strong secondary |
| `#646464` | Body muted |
| `#b4b8b4` | Tertiary (e.g. "Full Time" labels) |

### Tailwind grays (oklch — Tailwind v4 standard ladder)
- `--color-gray-200: oklch(92.8% .006 264.531)` — light borders
- `--color-gray-400: oklch(70.7% .022 261.325)` — muted text
- `--color-gray-500: oklch(55.1% .027 264.364)`
- `--color-gray-600: oklch(44.6% .03 256.802)`
- `--color-gray-700: oklch(37.3% .034 259.733)`
- `--color-gray-800: oklch(27.8% .033 256.848)`
- `--color-gray-900: oklch(21% .034 264.665)`

### Functional accents (used very sparingly)
- `--color-green-600: oklch(62.7% .194 149.214)` — success states only
- `--color-red-600: oklch(57.7% .245 27.325)` — destructive/error
- `#005885` — a single deep blue accent (sparse links/icons)
- `#484852`, `#454040`, `#383841`, `#282834` — dark navy/charcoal variants

**The page is essentially monochrome warm-grayscale + serif.** No multi-hue brand palette. That restraint is the point.

---

## Border Radius (Tailwind v4 standard ladder)

| Token | Value | Usage |
|---|---|---|
| `--radius-sm` | `.25rem` (4px) | Small chips |
| `--radius-md` | `.375rem` (6px) | Inputs, small buttons |
| `--radius-lg` | `.5rem` (8px) | Standard buttons |
| `--radius-xl` | `.75rem` (12px) | Cards |
| `--radius-2xl` | `1rem` (16px) | Large cards, modals |
| `--radius-3xl` | `1.5rem` (24px) | **The job-listings card** (the big rounded container with subtle border) |
| `27px` | Custom | Specific component (likely a tagged section card) |
| `50.496px` | Custom | Pill-style ("See more job offers" button) |
| `3.40282e+38px` | Max float | True pills |

The job-listings card in the screenshot uses `--radius-3xl` (24px) on a 1px border — that gentle, generous rounding paired with hairline borders is a recurring move on the page.

---

## Layout (careers page, from the screenshot)

```
┌───────────── viewport ─────────────┐
│                                     │
│              ☼  (sun glyph)        │
│                                     │
│       We're building tools for      │  ← PP Mondwest, large display
│     businesses that run themselves  │     (~64–96px), centered, italic-leaning
│                                     │
│  ┌─────────── card (24px radius) ───────────┐
│  │  Agents Research Lead          ›        │  ← af, semibold + chevron-right
│  │  Full Time                              │  ← af, #b4b8b4 muted
│  │  ─────────────────────────              │  ← hairline divider
│  │  Applied AI Engineer – Agents  ›        │
│  │  Full Time                              │
│  │  …                                      │
│  └──────────────────────────────────────────┘
│                                     │
│         See more job offers  →      │  ← 50.5px pill button
│                                     │
└─────────────────────────────────────┘
```

- Page bg: `#f9faf7` (warm cream)
- Card: white-ish `#fefffc` with 1px border `#dee2de`, 24px radius (`--radius-3xl`)
- Job titles: `af`, ~16–18px, weight 600, color `#000`
- "Full Time" sub-labels: `af`, ~13–14px, color `#b4b8b4`
- Chevron `›`: thin stroke, color matches text muted
- Dividers between rows: 1px `#eef1ed`
- Page is centered with substantial side padding; max-width ~720–820px
- The sun glyph is a small (~24×24px) inline SVG hand-drawn — sits ~24px above the headline, centered

---

## Component Notes

### Headline (the signature)
- `font-family: var(--font-mondwest)` — PP Mondwest
- Large display size (~clamp 48px → 96px responsively)
- Centered, two-line break tuned by hand
- Italic-leaning glyphs (PP Mondwest's lowercase has those distinctive curving terminals)
- No subtitle, no CTA below — the serif carries the whole moment

### Decorative sun glyph
- Small (~24×24px) SVG, centered above the headline
- Hand-drawn linework feel (uneven stroke, organic angles)
- A "moon at sunrise" / "horizon" glyph — references "agentic companies on the horizon" copy
- Pure decoration, no link/no semantic role

### Job listing rows
- Large container card with 24px (`--radius-3xl`) corners, hairline `#dee2de` border
- Each row: title (semibold) + subtitle (muted) + chevron-right
- Hover/focus likely shifts chevron right slightly (common micro-interaction)
- Hairline dividers `#eef1ed` between rows
- Generous vertical padding (~28–32px per row)

### "See more job offers" pill
- Pill button (`border-radius: 50.496px`)
- Cream-on-cream — sits in a slightly darker inline circle around an arrow icon
- Mid-weight `af` text, centered with the icon

---

## Iconography
- Hand-drawn / inline SVG decorative marks (the sun)
- Standard chevron-right `›` for list affordances
- Right-arrow `→` inside circular wells for buttons
- No icon library in evidence (no Lucide / Heroicons signature) — bespoke marks throughout

---

## Brand Voice (informs design)
- *"We're building tools for businesses that run themselves"* — declarative, calm
- *"Agentic companies are on the horizon, and we're building them"* — horizon metaphor → echoes the sun glyph
- *"A world where anyone with an idea can start a business as easy as playing a video game"* — playful aspiration
- Self-described: **applied AI lab** building **Cofounder** (multi-agent coordination)

Voice patterns:
- Aspirational + concrete in same breath ("video game" simile inside an AI manifesto)
- No urgency language, no growth-hack copy, no enterprise-jargon
- Reads like a small lab newsletter, not a pitch deck

Design mirrors the voice: **PP Mondwest serif = literary**, **sun glyph = horizon/aspiration**, **cream surfaces = unhurried**, **single accent palette = restrained**.

---

## Reproducing this aesthetic — minimum viable kit

1. **The serif is non-negotiable.** PP Mondwest if you can buy/license it; PP Editorial Old, GT Super Display, or Reckless Neue as substitutes. A generic Times/Georgia won't read the same.
2. **Surfaces:** `bg: #f9faf7`, card: `#fefffc`, border: `#dee2de`. Avoid pure white.
3. **Body sans:** any neutral grotesque (Inter/Geist/IBM Plex Sans/Söhne) at variable weight.
4. **Mono accent:** Geist Mono or JetBrains Mono for any technical metadata.
5. **Decorative SVG:** one hand-drawn glyph per major section. Inline, monochrome, ~24px.
6. **Radius:** generous (24px / `--radius-3xl`) for big content cards, 8px for buttons.
7. **Restraint:** no gradient backgrounds, no shadows beyond the absolute minimum, no multi-hue accents. The serif does the personality work alone.

---

## Comparison to Other Saved References

| | generalintelligencecompany.com | varickagents.com | guild.ai | adaline.ai | useallowance.com | zerotoagent.com | tahahossain.com |
|---|---|---|---|---|---|---|---|
| Style | Boutique AI lab editorial | Enterprise ops minimalism | Warehouse editorial dev infra | AI-infra sage | iOS consumer fintech | B2B operator min | Blueprint brutalism |
| BG | Cream `#f9faf7` (warm green tint) | Off-white `#f8f8f8` | Warm cream `#f8f6f3` + dark mode | Olive off-white `#f8f9f5` | Pure white | White | Cream `#f6f5f1` |
| Display | **PP Mondwest serif** | Bold geo sans | Suisse Neue + Syndicat Grotesk | Akkurat | SF Pro Rounded | Bold geo sans | Unica 77 + EB Garamond |
| Body | af (custom) | Framer default | Syndicat Grotesk | Akkurat | SF Pro Rounded | Sans | Diatype Mono |
| Accent | None (monochrome warm) | Electric `#0099ff` + navy | Orange `#ff5500` | Olive `#4a6d47` | Forest `#0A7C52` | Blue/teal | Red/green/blue hairlines |
| Radius | 24px cards + 50px pills | Square corners | 4–20px | 8–12px | 100px pills | Rounded | None |
| Distinguishing trick | **PP Mondwest serif + hand-drawn sun glyph + warm cream** | Square CTAs + SVG particle wave | Orange selection + dot-grid | Material 3 surface tiers | 100px pill buttons | Custom tenex SVG icons | Hairline registration lines |
