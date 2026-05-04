---
name: Design Reference — useallowance.com
description: Full extracted design system for Allowance (YC-backed consumer fintech app). iOS-native rounded aesthetic, deep forest green on white, pill buttons, SF Pro Rounded font. Self-described as "Consumer | Calm | Trustworthy".
type: reference
url: https://useallowance.com/
originSessionId: 3abfba9b-b504-4c96-a62d-5886b907999f
---
# useallowance.com — Full Design Reference
**URL:** https://useallowance.com/
**Product:** Allowance — AI agent wallet / virtual card with spending rules
**Company stage:** Early public beta, YC-backed
**Platform:** iOS app (consumer), web landing page
**Tech stack:** Vanilla HTML/CSS + Lucide icons (not React, not Tailwind — hand-written CSS)

---

## Aesthetic / Mood
**"Consumer | Calm | Trustworthy"** — self-described in the stylesheet comment.

Feels like a premium iOS app's web presence. Warm, rounded, green — closer to Robinhood or Monzo in spirit than to a typical B2B SaaS. No hard edges, no corporate coldness. The forest green signals trustworthiness and financial calm (not growth-hack neon green). Everything is soft, open, and breathable. YC badge in the hero positions it as startup-credible.

---

## Color Palette (exact values from CSS custom properties)

| Token | Value | Usage |
|---|---|---|
| `--color-bg` | `#FFFFFF` | Page background (pure white) |
| `--color-primary` | `#0A7C52` | Deep forest green — CTAs, links, nav logo, icons |
| `--color-primary-hover` | `#09754D` | Hover state darkening |
| `--color-accent` | `#0A7C52` | Same as primary |
| `--color-text` | `#0F172A` | Near-black (slate-900) — headings, body |
| `--color-text-muted` | `#475569` | Slate-500 — secondary text |
| `--text-tertiary` | `#64748B` | Slate-400 — captions, labels |
| `--color-border` | `#E2E8F0` | Slate-200 — all borders |
| `--border-hover` | `#CBD5E1` | Slate-300 — hover border |
| `--color-tint` | `#E6F4EF` | Light green wash — active states, step numbers |
| `--color-focus-ring` | `rgba(10,124,82,0.24)` | Green focus outline |
| `--bg-secondary` | `#F8FAFC` | Slate-50 — card/phone bg |
| `--bg-card` | `#FFFFFF` | Card surfaces |
| `yc-text` | `#FB651E` | YC orange — used only on YC badge |
| `theme-color` | `#FFFFFF` | Browser chrome color |

---

## Typography

| Token | Value |
|---|---|
| `--font-brand` | `ui-rounded, "SF Pro Rounded", -apple-system, system-ui, "Segoe UI", Roboto, Helvetica, Arial, sans-serif` |
| `--font-ui` | Same stack as brand |

**No external font CDN** — relies entirely on system fonts, prioritizing `ui-rounded` / `SF Pro Rounded` (the iOS rounded variant of SF Pro). On macOS/iOS this renders as the native rounded font; on Windows/Android it falls back to system-ui gracefully.

**Type scale:**
- Hero h1: `3.8rem`, weight 700, `letter-spacing: -0.04em`, `line-height: 1.08`
- Section h2: `2.4rem`, weight 700, `letter-spacing: -0.035em`
- CTA h2: `2rem`, weight 700, `letter-spacing: -0.03em`
- Section label: `0.75rem`, weight 600, uppercase, `letter-spacing: 0.08em`, green
- Body: `1.1–1.2rem`, `line-height: 1.65`
- Card body: `0.85–0.95rem`
- `-webkit-font-smoothing: antialiased`

---

## Border Radius System

| Token | Value | Usage |
|---|---|---|
| `--radius-sm` | `8px` | Small elements |
| `--radius-md` | `12px` | Cards, allowance-card, chat bubbles |
| `--radius-lg` | `20px` | Demo phone, legal cards |
| `--radius-xl` | `28px` | Demo phone container |
| Pill | `100px` | All buttons (nav CTA, btn-primary, btn-secondary) |
| Circle | `50%` | Step number badges |

Very rounded overall — the 100px pill buttons are the signature gesture.

---

## Layout

- **Max width:** `1080px`
- **Section gap:** `6rem` (desktop), `4rem` (mobile)
- **Container padding:** `0 2rem` (desktop), `0 1.25rem` (mobile)
- **Scroll behavior:** `smooth`

**Page structure:**
1. Fixed nav — white 92% opacity + `backdrop-filter: blur(10px)` + 1px border-bottom
2. Hero — centered, large headline, YC badge, subtitle, CTA buttons
3. Demo section — horizontal-scroll prompt cards + phone mockup with animated chat
4. Pain point quote
5. Features grid (3-col, `1px` gap border trick = faint grid lines between cards)
6. How it works — 3 steps
7. Use cases — 2-col grid
8. Developer callout card
9. CTA section
10. Footer — logo left, links right, `border-top: 1px solid var(--border)`

---

## Component Specs

### Buttons
- `btn-primary`: `background: #0A7C52`, white text, `border-radius: 100px`, `padding: 0.8rem 2rem`, hover: `translateY(-1px)`
- `btn-secondary`: transparent bg, 1px border, `border-radius: 100px`
- `nav-cta`: same pill shape, `border-radius: 100px`, lighter weight

### Cards
- 1px border `#E2E8F0`, `border-radius: 12px` (md)
- Shadows: `0 12px 32px rgba(15, 23, 42, 0.08)` — very subtle, barely-there elevation
- Hover: `border-color: #CBD5E1`

### Features Grid
- `display: grid`, `grid-template-columns: repeat(3, 1fr)`, `gap: 1px`, `background: var(--border)` — a clever 1px gap trick that creates hairline dividers between cards
- Each card: `padding: 2.25rem 2rem`, white bg

### Chat Demo (phone mockup)
- User bubbles: `background: #0A7C52` (green), white text, `border-bottom-right-radius: 4px`
- AI bubbles: white bg, 1px border, `border-bottom-left-radius: 4px`
- Animated entrance: `opacity: 0 → 1`, `translateY(8px → 0)`

### Icons
- **Lucide** icons from unpkg CDN
- `stroke-width: 1.5` — light, elegant line weight
- `width/height: 22–24px` typical

### Section Labels
- `0.75rem`, `font-weight: 600`, `text-transform: uppercase`, `letter-spacing: 0.08em`, `color: #0A7C52`

---

## Logo
- **Web logo:** Text-only — "Allowance" in `font-weight: 600`, `color: #0A7C52`, `letter-spacing: -0.01em`
- **SVG icon:** Organic/flowing green blob shape. Colors: bright green `#00FC33` / dark greens `#007019+` on black. Abstract, nature-ish, 2048×2048px.
- **App icon (App Store):** The icon used for Claude agent = terracotta/orange rounded square with white asterisk (this is Claude's icon, not Allowance's)

---

## Brand Voice (informs design)
- "Give your AI a wallet with rules."
- "Set a limit, lock a merchant, add an expiry."
- Very plain English, calm confidence. No hype, no superlatives.
- Consumer-focused — explains what it does, not why it's revolutionary.

---

## Comparison to Other Saved References

| | useallowance.com | zerotoagent.com | tahahossain.com |
|---|---|---|---|
| Style | iOS-native consumer fintech | Premium B2B minimalism | Blueprint editorial brutalism |
| BG | White `#FFFFFF` | White | Cream `#f6f5f1` |
| Primary color | Forest green `#0A7C52` | Blue/teal | None (hairlines only) |
| Font | SF Pro Rounded (system) | Bold geo sans | Unica 77 + Diatype Mono + EB Garamond |
| Buttons | Pill (100px radius) | Rounded | N/A |
| Cards | Very rounded (12–28px) | Moderate rounding | N/A |
| Feel | Calm, consumer, trust | Operator confidence | Architectural precision |
| Icons | Lucide 1.5 stroke | Custom SVG set | None |
| Shadows | Subtle, barely-there | Minimal | None |
