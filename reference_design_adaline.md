---
name: Design Reference — adaline.ai
description: AI infra dev-tool aesthetic. Material 3 / Tailwind v4 token system, warm off-white surfaces, olive-green primary, custom Akkurat + fragmentMono type. Use when referencing this aesthetic for AI/developer-tooling product design.
type: reference
url: https://adaline.ai/
---
# adaline.ai — Full Design Reference
**URL:** https://adaline.ai/
**Product:** Adaline — single platform to iterate, evaluate, deploy, and monitor AI agents
**Target market:** "World-class product and engineering teams" (AI-infra/devtool)
**Tech stack:** Next.js + Tailwind v4 (uses `@layer theme`, `oklch()`, `--spacing:.25rem`)

---

## Aesthetic / Mood
**Modern AI-infra polish with an organic warm-neutral base.** Not the typical cold gray dev-tool palette — the surfaces are warm off-whites tinted faintly green, and the text is deep olive/forest rather than pure black. Reads as serious enterprise infrastructure (200M+ API calls/day, 99.998% uptime stats) but with humane, almost editorial color choices. Hero is screenshot-forward (product UI), not abstract illustration. Decorative footer elements ("hills", "dock reflection") add personality without compromising the serious tone.

If allowance.com is "consumer fintech green" and zerotoagent is "B2B operator white," Adaline is "developer platform sage" — precise, calm, infrastructure-grade, with a botanical undertone.

---

## Color Palette (exact tokens from CSS)

### Surface tiers (Material 3 elevation model)
| Token | Value | Usage |
|---|---|---|
| `--color-surface-highest` | `#fdfefb` | Top elevation — modals, popovers |
| `--color-surface-high` | `#fafbf7` | Elevated cards |
| `--color-surface-base` | `#f8f9f5` | Page background (warm off-white) |
| `--color-surface-low` | `#f1f3ef` | Recessed sections |
| `--color-surface-lowest` | `#e9ede9` | Deepest recess / dividers |

Each surface also has a `-transparent` variant (same hex + `00` alpha) for fade effects.

### On-surface text (deep olive, never pure black)
| Token | Value | Usage |
|---|---|---|
| `--color-on-surface-highest` | `#2b390a` | Strongest text on highest surface |
| `--color-on-surface-high` | `#2f3f1b` | Body on elevated cards |
| `--color-on-surface-base` | `#2e4320` | Default body text |
| `--color-on-surface-low` | `#243b1b` | Body on recessed surface |
| `--color-on-surface-lowest` | `#123b0e` | Strongest contrast text |

Each has `-subtle` (70% alpha, `b3`) and `-disabled` (40% alpha, `66`) variants.

### Primary (forest/olive green)
| Token | Value | Usage |
|---|---|---|
| `--color-primary` | `#4a6d47` | CTAs, links, brand |
| `--color-on-primary` | `#eef6dc` | Text on primary fills |
| `--color-primary-container` | `#ddeabd` | Soft primary backgrounds (badges, chips) |
| `--color-on-primary-container` | `#4a6d47` | Text on primary containers |

### Inverse / dark mode
| Token | Value | Usage |
|---|---|---|
| `--color-inverse-surface` | `#2a332a` | Dark surface (footer, inverted sections) |
| `--color-inverse-on-surface` | `#fdfefb` | Text on dark surface |

### Accent splashes (used sparingly, likely for category/illustration moments)
- Mint highlight: `#75ffbc`
- Purple/magenta: `#b14eaa`, `#7e42a6`, `#9c2fa6`, `#cf2184`, `#d41665`, `#92174a`
- Teal: `#0f9397`, `#1a7474`, `#2b6b5e`, `#bed7d7`
- Warm peach/cream: `#fff0e5`, `#feebfb`
- Earth tones: `#886a00`, `#b54c1f`, `#c23934`
- Royal blue: `#3963b7`, `#c2d8ec`

### Surface tint (subtle elevation overlays)
- `--color-surface-tint-mild` — `#344f3108` (3% olive)
- `--color-surface-tint-base` — `#344f3112` (7% olive)
- `--color-surface-tint-strong` — `#33503024` (14% olive)

---

## Typography

| Token | Stack |
|---|---|
| `--font-akkurat` | `"akkurat", "akkurat Fallback"` |
| `--font-fragment-mono` | `fragmentMono, fragmentMono Fallback, SFMono-Regular, SF Mono, JetBrains Mono, Fira Code, Cascadia Code, Source Code Pro, ui-monospace, Menlo, Monaco, Consolas, Liberation Mono, Courier New, monospace` |
| Body fallback chain | `var(--font-akkurat), "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif` |

**Akkurat** (Lineto, by Laurenz Brunner) — Swiss neo-grotesque, slightly humanist, very common in design-tool/dev-tool sites (Linear, Vercel-adjacent aesthetic). Loaded as 5 woff2 files (multiple weights/styles).
**fragmentMono** — geometric monospace, used for code samples / numerical metrics (the "0123456789" animated counter pattern).

---

## Border Radius System

| Token | Value | Usage |
|---|---|---|
| `--radius` | `0.5rem` (8px) | Default — `rounded` |
| `--radius-xl` | `0.75rem` (12px) | Large cards |
| `rounded-sm` | `calc(var(--radius) - 2px)` = 6px | Small elements |
| `rounded-xs` | `calc(var(--radius) - 4px)` = 4px | Pills, tags |
| Full pill | `3.40282e+38px` (max float — full pill) | Status pills |

Notably more **conservative rounding** than allowance.com (which uses 100px pills and 28px cards). Adaline tops out at 12px corners — this signals "developer tool" precision over "consumer app" softness.

---

## Layout

- **Tailwind v4** with `--spacing:.25rem` base unit
- Container max widths: `--container-2xl: 42rem` (672px) and standard Tailwind tiers
- Page structure (top → bottom):
  1. Nav — Products / Pricing / Blog / Demo
  2. Hero — headline + subhead + product screenshot ("hero-product-shot")
  3. Four-pillar product overview — Iterate / Evaluate / Deploy / Monitor
  4. "Trusted by" social proof
  5. Feature boxes — prompt management, version history, rollback, "smart diffing", "magical test set up"
  6. Animated stat counters — 200M+ API calls/day, 5B+ tokens/day, 300+ models, 99.998% uptime
  7. Testimonial quotes (McKinsey, Discord, startups)
  8. Content library — blog, case studies, research
  9. Decorative footer with "hills" + "dock reflection" SVGs

---

## Component Notes

### Buttons
- Standard Tailwind `rounded` (8px), no extreme pill radius
- Primary: `#4a6d47` background, `#eef6dc` text
- Secondary/ghost: surface tints + olive text

### Cards
- Surface tier system — base on `#f8f9f5`, elevated on `#fafbf7` or `#fdfefb`
- Border-radius typically 8–12px
- Subtle olive tint shadows via `--color-surface-tint-*`

### Stat counters
- Animated number rolls (digits 0–9 cycle into final value)
- Likely uses `fragmentMono` for the numerals

### Decorative SVGs
- "Footer Hills", "dock reflection", "dock" — botanical/landscape motifs reinforce the warm-organic palette
- Hero file icons: work, prompt, dataset, airplane

---

## Brand Voice (informs design)
- *"The single platform to iterate, evaluate, deploy, and monitor AI agents"*
- *"Magical test set up"* / *"Smart diffing"* — small playful word choices inside otherwise precise copy
- *"Handles massive scale effortlessly"* — confident, not boastful
- Targets "world-class product and engineering teams" — premium positioning without flexing
- Voice: technical precision + light humanizing flourishes. Design mirrors this — strict token system + warm/organic palette.

---

## Comparison to Other Saved References

| | adaline.ai | useallowance.com | zerotoagent.com | tahahossain.com |
|---|---|---|---|---|
| Style | AI-infra developer platform | iOS-native consumer fintech | Premium B2B minimalism | Blueprint editorial brutalism |
| BG | Warm off-white `#f8f9f5` (olive-tinted) | Pure white `#FFFFFF` | White | Cream `#f6f5f1` |
| Primary | Olive-forest `#4a6d47` | Forest green `#0A7C52` | Blue/teal | None (hairlines only) |
| Text | Deep olive (never pure black) | Slate `#0F172A` | Dark charcoal | Pure black |
| Type | Akkurat + fragmentMono | SF Pro Rounded (system) | Bold geo sans | Unica 77 + Diatype Mono + EB Garamond |
| Radius | 8–12px (conservative) | 12–28px + 100px pills | Moderate | N/A |
| Token system | Material 3 surface tiers | Flat semantic tokens | Unknown | CSS vars |
| Feel | Sage / infrastructure-grade | Calm / consumer / trust | Operator confidence | Architectural precision |
| Distinguishing trick | Surface elevation tiers + olive-on-olive | 100px pill buttons + Lucide 1.5 stroke | Custom tenex SVG icons | Hairline registration lines |
