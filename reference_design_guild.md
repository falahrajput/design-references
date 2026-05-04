---
name: Design Reference — guild.ai
description: AI agent control-plane / dev-infra site. Warm cream + black contrast, Syndicat Grotesk + Suisse Neue, GitHub-dark syntax-highlighted code snippets, orange #ff5500 selection accent, full dark mode. Use when referencing this aesthetic for AI infra / governance / dev-platform design.
type: reference
url: https://www.guild.ai/
---
# guild.ai — Full Design Reference
**URL:** https://www.guild.ai/
**Product:** Guild — "the control plane for AI agents"
**Tagline:** "Building AI agents is easy. Managing them isn't"
**Stage:** Venture-backed (GV, NFX, Khosla logos prominent)
**Audience:** Engineering leaders / DevOps teams deploying AI automation
**Tech stack:** Next.js, custom Tailwind-flavor CSS, Osano cookie banner, full dark mode

---

## Aesthetic / Mood
**Editorial-tech with warm neutrals and aggressive code-forwardness.** Where most AI-infra sites default to cold gray-on-white SaaS, Guild leans into a **warm cream background `#f8f6f3` with deep black `#0a0a0a` text** — closer to a magazine or premium SaaS brand (Linear-adjacent) than a typical dev-tool. Code snippets are *everywhere* and rendered in true GitHub-dark syntax, signaling "we're builders, not marketers." Animations are subtle pulse/marquee loops (logo carousel, agent-row pulse, icon color pulse) — never showy.

The single splash of saturated color is **orange `#ff5500`** — used for `::selection`, button hover states, and CTA highlights. Everything else is neutral. The site has a complete inverted **dark mode** (background flips to near-black `#141413`, text to off-white `#f8f7f5`).

If adaline.ai is "sage / botanical infrastructure," Guild is "warehouse loft / industrial editorial" — same dev-tool seriousness, but warmer paper-stock feel and more code visible.

---

## Color Palette (exact tokens from `:root`)

### Brand colors
| Token | Value | Usage |
|---|---|---|
| `--black` | `#0a0a0a` | Primary text, dark surfaces |
| `--white` | `#fafafa` | Inverted text, light surfaces |
| `--blue` | `#15b9eb` | Brand cyan |
| `--guild-blue` | `#2f6bff` | True brand blue |
| `--green` | `#22c55e` | Success states |
| `--red` | `#ef4444` | Error/destructive |
| `--yellow` | `#f2e863` | Highlights |
| `--orange` | `#ff5500` | **Signature accent** — selection, hover, CTA |
| `--purple` | `#fafafa` | (intentionally remapped to white — likely fallback override) |
| `--graph-slate` | `#0f172a` | Charts/graphs |
| `--interface-gray` | `#94a3b8` | UI chrome |

### Light mode (default)
| Token | Value |
|---|---|
| `--color-font` | `#000000` |
| `--color-font-light` | `rgba(0,0,0,0.5)` |
| `--color-font-semilight` | `rgba(0,0,0,0.6)` |
| `--color-font-reverse` | `#f8f7f5` |
| `--color-background` | `#fff` |
| `--color-background-reverse` | `#000000` |
| `--color-border` | `rgba(0,0,0,0.2)` |
| `--color-border-alt` | `rgba(0,0,0,0.1)` |
| `--card-bg` | `#fff` |
| `--card-pill` | `#f2f2f2` |
| `--input-bg` | `#f8f6f3` (warm cream — the signature surface) |
| `--input-placeholder` | `#7c7b7a` |
| `--callout-bg` | `#000` |
| `--callout-font` | `#fff` |

### Dark mode (`:root.dark-mode`)
| Token | Value |
|---|---|
| `--color-font` | `#f8f7f5` |
| `--color-background` | `#141413` (near-black, slightly warm) |
| `--card-bg` | `#1d1d1d` |
| `--card-pill` | `#141413` |
| `--input-bg` | `#141413` |
| `--callout-bg` | `#fff` (inverted) |

### Warm neutral surface ladder (used in sections)
- `#fbfaf9`, `#f9f9f7`, `#f8f8f6`, `#f8f6f3` (default cream), `#efedea`, `#edeae6`, `#eceae7`, `#e9e7e3`, `#d0cfcc`
- All slightly warm/yellow-leaning — never cool gray

### Code-block (GitHub dark syntax) palette
- `#c9d1d9` — default text
- `#79c0ff` — keywords (light blue)
- `#a5d6ff` — strings
- `#7ee787` — function names (green)
- `#ffab70` — numbers/constants (orange)
- `#8b949e` — comments

### Section gradient (signature)
`background: radial-gradient(circle, rgba(55,48,40,.06) 1px, transparent 0), linear-gradient(180deg, #f9f9f7 30%, #eceae7 ...)` — a **subtle dot-grid pattern overlaid on a warm cream gradient**. Distinctive backdrop for hero/feature zones.

### Selection
`::selection { background: var(--orange); color: #fff }` — orange highlight, very recognizable when copying text.

---

## Typography

**Three custom fonts loaded as woff2:**

| Font | Style | Usage |
|---|---|---|
| **Syndicat Grotesk** | Regular 400 | Body text, UI, default |
| **Suisse Neue** | Light 400 + Bold 700 | Display headlines |
| **Suisse Intl Mono** | Light 400 | Inline mono / labels (loaded but lightly used) |
| **Geist Mono** / **JetBrains Mono** | (system fallback) | Code blocks |
| **Doto** | (loaded) | Pixelated/decorative — likely for one specific moment |

**Key typographic choices:**
- Body: `font-family: Syndicat Grotesk, sans-serif`
- Body size: `clamp(1.4rem, calc(1.4rem + .2 * (100vw - 48rem) / 80), 1.6rem)` — fluid 14–16px
- Line-height: `1.5`
- Antialiased everywhere
- `font-size: 62.5%` on `:root` (10px base — rem math is `1rem = 10px`)
- Mobile clamp: scales from 50% to 62.5% based on aspect ratio for tall viewports

**Syndicat Grotesk** is a contemporary geometric grotesk (similar feel to GT America / Söhne but slightly more idiosyncratic). **Suisse Neue** is the classic Swiss neo-grotesque from Swiss Typefaces — the same family used by Stripe, Linear, etc. The combination signals "premium dev-tool, not generic SaaS."

---

## Border Radius System

| Value | Usage |
|---|---|
| `2px` | Tight UI (badges, chips) |
| `4px` | Small elements |
| `5px` / `6px` / `8px` | Standard UI, buttons |
| `10px` / `12px` | Cards |
| `16px` / `20px` / `24px` | Large surfaces, modals |
| `50px` | Pills (cookie banner buttons) |
| `50%` | Circular avatars, mode-switcher icon |
| Cookie dialog | `border-radius: 20px` |

Conservative-to-medium rounding. No extreme pill usage — rounded but precise.

---

## Layout

- Root font-size: `62.5%` (10px) — `1.6rem` body = 16px
- Aspect-ratio-based scaling: `@media (min-aspect-ratio: 3/2)` clamps font-size for wide displays
- Page width: `--page-width: 135rem` (1350px)
- Gutter: `--grid-overlay-gutter: 2rem` (20px)
- `scrollbar-gutter: stable` — no layout shift on overflow
- `overflow-x: hidden` on `html`

**Page structure (top → bottom):**
1. Announcement bar (optional, `--announcement-height: 30px`)
2. Nav — Platform / Solutions / Resources + dual CTAs
3. Hero — *"Building AI agents is easy. Managing them isn't"* + Start free trial / Book demo
4. **Animated agent hub showcase** — grid of agent use cases (PR review, ticket triage, RCA, on-call) with pulse animations on icons and rows
5. Control plane features — policies, permissions, observability, audit/logs
6. **Logo marquee** — scrolling integration partners (Jira, Slack, GitHub, etc.) — `LogoMarquee_marquee` keyframe
7. Build / Deploy / Govern / Share — four pillars **with inline TypeScript code snippets** (syntax-highlighted)
8. Model & credential flexibility — "Model-agnostic. Your stack. Your keys"
9. Agent library — 6 detailed agent cards with code examples
10. Agent marketplace — GitHub-style fork/customize table
11. Testimonials — circular avatars + company quotes
12. CTA section + footer

---

## Animation System (signature pulse keyframes)

The hero is alive with subtle, staggered pulses:
- `HomeHeroV3_agentRowPulse` — entire agent rows
- `HomeHeroV3_dotPulse` — dot indicators
- `HomeHeroV3_pixelPulse` — pixel/sparkle effect
- `HomeHeroV3_iconBgPulse` / `iconColorPulse` — icon backgrounds + colors
- `HomeHeroV3_pulseUp` / `pulseDown` — directional pulses
- `HomeHeroV3_toolIconPulse` / `toolImgPulse` — tool integration icons
- Pulse delays: `0.3s, 0.5s, 2.4s, 2.65s, 2.85s, 3s` — choreographed, not random
- `LogoMarquee_marquee` — infinite scroll for partner logos
- `ProductCarousel_productDotFill` — pagination dot fill animation

---

## Component Notes

### Buttons
- Standard: `border-radius: 8px`, `padding: 12px 18px`, `font-size: 12px`, line-height 90%
- Hover: white → `#ff5500` (orange) bg, black → white text
- Cookie banner buttons: same shape, gap 10px

### Cards
- `--card-bg: #fff` light / `#1d1d1d` dark
- `--card-pill: #f2f2f2` light (chip/tag bg) / `#141413` dark
- Subtle borders via `rgba(0,0,0,0.1)`

### Code blocks
- Full GitHub-dark color scheme (see palette above)
- Mono fonts: Geist Mono, JetBrains Mono fallback chain
- Inline TypeScript SDK examples are the primary "feature illustration" — code IS the visual

### Cookie banner (Osano, customized)
- `border-radius: 20px`, `bottom-right: 16px`, width 420px
- Black bg, 60% white text — distinctive, high-contrast modal

### Mode switcher
- Circular icon (50% radius), `--mode-switcher-bg: #fff`, swaps fg/bg in dark mode

### Selection highlight
- `background: var(--orange)`, `color: #fff` — instantly identifies the brand on copy

---

## Brand Voice (informs design)
- *"Building AI agents is easy. Managing them isn't"* — problem-first, blunt
- *"The control plane for AI agents"*
- *"Model-agnostic. Your stack. Your keys."*
- Emphasis on: governance, visibility, audit trails, scoped credentials
- Tone: enterprise-credible but builder-first. Code is the proof.
- Investor logo wall (GV/NFX/Khosla) is prominent — credibility signal

Design mirrors voice: serious, code-forward, no decorative excess. The orange accent and warm cream surfaces add personality without breaking the technical credibility.

---

## Comparison to Other Saved References

| | guild.ai | adaline.ai | useallowance.com | zerotoagent.com | tahahossain.com |
|---|---|---|---|---|---|
| Style | Warehouse-editorial dev infra | AI-infra sage | iOS consumer fintech | B2B operator min | Blueprint brutalism |
| BG | Warm cream `#f8f6f3` + full dark mode | Olive-tinted off-white `#f8f9f5` | Pure white | White | Cream `#f6f5f1` |
| Primary | Black `#0a0a0a` text + orange `#ff5500` accent | Olive-forest `#4a6d47` | Forest green `#0A7C52` | Blue/teal | None |
| Text | Pure black / off-white | Deep olive | Slate `#0F172A` | Dark charcoal | Pure black |
| Type | Syndicat Grotesk + Suisse Neue + Suisse Mono | Akkurat + fragmentMono | SF Pro Rounded | Bold geo sans | Unica 77 + Diatype Mono + EB Garamond |
| Radius | 4–20px (varied) | 8–12px | 12–28px + 100px pills | Moderate | N/A |
| Code | **Inline TS, GitHub-dark syntax everywhere** | Minimal | None | None | None |
| Animation | Choreographed pulse hero + logo marquee | Animated stat counters | Chat bubble entrance | GIF figures | None |
| Dark mode | **Full** (warm near-black `#141413`) | No | No | No | No |
| Distinguishing trick | Orange `#ff5500` selection + dot-grid gradient hero + warm cream | Material 3 surface tiers + olive-on-olive | 100px pill buttons | Custom tenex SVG icons | Hairline registration lines |
