---
name: Design Reference — workers.cloudflare.com
description: Cloudflare Workers / Developer Platform marketing site. Signature deep oxblood text #521000 + Cloudflare orange #ff4801 on warm cream #fffbf5, FT Kunst Grotesk + Apercu Mono Pro, full dark mode, semantic token system (accent / ai / foreground / background ladders), bracketed-corner annotations, Three.js wireframe globe centerpiece. Use when referencing this aesthetic for developer-platform sites that want warm/branded over cold/neutral.
type: reference
url: https://workers.cloudflare.com/
---
# workers.cloudflare.com — Full Design Reference
**URL:** https://workers.cloudflare.com/
**Product:** Cloudflare Workers — serverless compute platform on Cloudflare's edge network
**Tagline:** *"Region: Earth"* — one smart network for workloads + security
**Audience:** Developers building serverless / edge / AI applications
**Tech stack:** **Astro** (`/_astro/...`) + Tailwind v4 + custom semantic token system + Three.js (globe) + Vue/Svelte islands

---

## Aesthetic / Mood
**Warm Cloudflare-branded developer platform.** Distinct from the typical "blue-and-white SaaS" or "black-and-green dev terminal" archetypes — Workers leans into a **warm-cream surface palette** (`#fffbf5`, `#fef7ed`) with **deep oxblood foreground text (`#521000`)** and the iconic **Cloudflare orange (`#ff4801`)** as the accent. The result reads as friendly, almost editorial dev-platform — closer to a designed magazine than typical infrastructure documentation.

The visual centerpiece is the **"Region: Earth" rotating wireframe globe** — a Three.js scene with lat/lng grid lines in orange, animated great-circle arcs between cities, and bracketed-corner annotation callouts. It's the showpiece moment of the page and the single most-recognisable design fingerprint.

If modal.com is "clean-room dev infra with lime LEDs," Cloudflare Workers is "warm campfire dev platform" — same enterprise-credible technical category, but with cream-and-oxblood warmth instead of monochrome dark.

---

## Typography

| Font | File | Usage |
|---|---|---|
| **FT Kunst Grotesk** | `/fonts/Kunst Grotesk Regular.woff2` + Medium | **Default sans** — body, UI, headlines. Self-hosted. |
| **Apercu Mono Pro** | (woff2) | **Monospace** — code, technical labels, metric values |

**FT Kunst Grotesk** (Fast Type Foundry, "Kunst" = "art" in German) — a contemporary humanist grotesque with subtle warmth. Reads more "design-conscious" than Inter or Geist while being just as legible. Pairing with **Apercu Mono Pro** (a premium mono used by Linear, Stripe, Vercel-tier brands) signals serious typographic investment.

**Substitutes if you can't license:**
- Kunst Grotesk → Söhne, GT America, Inter (less character)
- Apercu Mono Pro → Berkeley Mono, JetBrains Mono, Geist Mono

---

## Color System — semantic token ladders (light + dark)

Workers uses **semantic token names** (foreground / background / accent / ai) rather than raw color names. Each has 100/200/300 tiers and **separate values for light vs dark mode** (the CSS contains both definitions; the `:root` switches at runtime).

### Foreground (text) — light mode
| Token | Value |
|---|---|
| `--color-foreground-100` | `#521000` (signature **deep oxblood**) |
| `--color-foreground-200` | `#525252` (neutral muted) |
| `--color-foreground-300` | `#140400` (near-black warm) |

### Foreground — dark mode
| Token | Value |
|---|---|
| `--color-foreground-100` | `#fafafa` |
| `--color-foreground-200` | `#a3a3a3` |
| `--color-foreground-300` | `#0a0a0a` |

### Background — light mode (warm cream ladder)
| Token | Value |
|---|---|
| `--color-background-100` | `#fffdfb` (top elevation, near-white warm) |
| `--color-background-200` | `#fffbf5` (page bg — the dominant cream) |
| `--color-background-300` | `#fef7ed` (recessed sections) |
| `--color-background-content` | `#fff` (pure white card bodies) |
| `--color-background` | `#fefefe` |

### Background — dark mode (warm near-black)
| Token | Value |
|---|---|
| `--color-background-100` | `#171717` |
| `--color-background-200` | `#1a1a1a` |
| `--color-background-300` | `#262626` |

### Accent (Cloudflare orange ladder)
| Token | Light value | Dark value |
|---|---|---|
| `--color-accent-100` | `#f14602` | `#ff4801` (signature CF orange) |
| `--color-accent-200` | `#ff6d33` | `#ff7038` |

### AI (sub-product accent — bright green)
Used specifically for AI Workers / Workers AI sections to differentiate from the orange Workers brand.
| Token | Light | Dark |
|---|---|---|
| `--color-ai-100` | `#19e306` (saturated green) | `#5eff3a` (electric lime) |
| `--color-ai-200` | `#2a3d1f` (deep moss) | `#f2f5e1` (pale cream-green) |

### Status colors
- Red error: `#fb2c36`
- Green success: `#00bb7f`
- Amber warning: `#f99c00`

### Most-used (frequency in CSS)
| Frequency | Value | What |
|---|---|---|
| 202 | `#521000` | **Signature oxblood foreground** — most-used token! |
| 121 | `#ff4801` | Cloudflare orange |
| 92 | `#000000` | True black |
| 84 | `#ffffff` | White |
| 54 | `#fffbf5` | Warm cream bg |
| 47 | `#171717` | Dark mode bg |
| 42 | `#fb2c36` | Red |
| 38 | `#ebd5c1` | Sand / peach surface |
| 26 | `#fef7ed` | Recessed cream |
| 19 | `#f99c00` | Amber |
| 16 | `#00bb7f` | Green success |

The fact that **`#521000` (oxblood) is more frequent than `#000000`** is the single biggest tell: this is a designed system, not a default. Cloudflare deliberately chose warm-toned ink over pure black.

---

## Border Radius

Mixed/precise system — many specific values, not just a token ladder:

| Value | Likely usage |
|---|---|
| `0` | Full-bleed sections, intentionally square accents |
| `1px`, `1.5px`, `2px`, `3px`, `4px` | Hairline accents, bracket corners |
| `0.25rem` (4px), `6px`, `10px`, `11px` | Small UI |
| `12px`, `14px`, `16px` | Cards |
| `20px`, `24px` | Large cards |
| `50%` | Avatars, dots |
| `3.40282e38px` | Pills |

**Distinctive:** the use of `1.5px` and small odd values like `11px` suggests very precise component-by-component design — not just dropping into a token ladder.

---

## Layout & Animation

- Tailwind v4 utility system
- `--blur-sm: 8px`, `md: 12px`, `lg: 16px`, `xl: 24px`, `2xl: 40px` — generous blur scale for glassmorphism
- `--animate-pulse: pulse 2s cubic-bezier(.4, 0, .6, 1) infinite`
- `--animate-ping: ping 1s cubic-bezier(0, 0, .2, 1) infinite` — used on live indicators (e.g. animated dots radiating outward)
- `--animate-spin: spin 1s linear infinite` — loaders

**Page structure (top → bottom):**
1. Nav — Cloudflare logo + Workers wordmark + product menu
2. Hero — large Kunst Grotesk headline, primary CTA in orange
3. Code samples in Apercu Mono Pro
4. **Region: Earth** section — Three.js wireframe globe with arcs + bracketed callouts
5. Three-column feature row ("Run everywhere / Run anywhere / Run at massive scale")
6. AI Workers section — switches to the green AI accent
7. Pricing / customer logos
8. Documentation / footer

---

## Signature Component: The "Region: Earth" globe

The page's iconic moment. Recreated in [`demos/rotating-globe.html`](demos/rotating-globe.html).

**Anatomy:**
- **Three.js** scene with a custom `THREE.Group()` containing:
  - **Latitude rings** (parallels) — 11 horizontal circles drawn as `THREE.Line` from `BufferGeometry` with `LineBasicMaterial({ color: 0xf1a36a, opacity: 0.55 })`
  - **Longitude meridians** — 24 half-circles from pole to pole
  - **Pin spheres** — small `SphereGeometry` (`r: 0.04–0.06`) positioned via lat/lng → vec3 conversion
  - **Animated arcs** — great-circle interpolation (slerp) between two surface points, lifted into a parabolic curve, with `setDrawRange()` used to animate "head" and "tail" reveal each frame
- **Continuous Y-axis rotation:** `globe.rotation.y += dt * 0.12` (≈1 rev / 52 s)
- **Slight Z tilt** (`0.18 rad`) so it reads as a tilted Earth, not a stationary ball

**Why custom lat/lng instead of `wireframe: true`:**
The default `SphereGeometry` wireframe triangulates the surface, producing busy diagonal lines. A clean lat/lng grid (matching the Cloudflare aesthetic) requires manually constructing the parallels and meridians as `Line` objects. About 30 lines of code.

**Annotation callouts** in the screenshot:
- Plain `<div>` overlays positioned over the canvas with `position: absolute`
- Bracketed corners drawn via `::before` and `::after` pseudo-elements with one-sided borders (top-left + bottom-right) — gives the "schematic / engineering drawing" feel
- Same bracket pattern reused on the three-column feature card below

---

## Component Notes

### Bracket-corner cards / annotations
The signature decorative motif. Two L-shaped corners (top-left + bottom-right) drawn with thin orange borders. Used on:
- Globe annotation callouts ("4.5x faster", "95% of the world's…")
- Feature row container (the three-column "Run everywhere / anywhere / massive scale")
- Code snippets and stat blocks

```css
.bracketed { position: relative; border: 0; }
.bracketed::before, .bracketed::after {
  content: ""; position: absolute; width: 14px; height: 14px;
  border: 1.5px solid var(--accent);
}
.bracketed::before { top: -1px; left: -1px; border-right: 0; border-bottom: 0; }
.bracketed::after  { bottom: -1px; right: -1px; border-left: 0; border-top: 0; }
```

### Buttons
- Primary: filled orange `#ff4801`, white text, ~6–10px radius
- Ghost: transparent with orange border, oxblood text
- Tertiary: text-only with subtle underline

### Code blocks
- Apercu Mono Pro
- Cream surface (light mode) or warm dark (dark mode)
- Syntax highlighted but with restraint — not a full rainbow

### Live indicators (`animate-ping`)
A small dot with a pinging halo ring radiating outward — used on "live" status, deployments, network activity. Cloudflare-coded.

---

## Brand Voice (informs design)
- *"Region: Earth"* — characteristic Cloudflare cleverness
- *"One smart network for workloads + security — close to users, close to data"*
- *"330+ cities"*, *"449 Tbps"*, *"81 million HTTP requests per second"* — concrete scale numbers
- Tone: confidently technical, occasionally playful (the *"Region: Earth"* line is half a joke at AWS regions)

Design mirrors voice:
- **Warm cream + oxblood** = "we're not generic SaaS"
- **Wireframe rotating globe** = literal interpretation of "Region: Earth"
- **Bracket-corner annotations** = engineering-drawing precision
- **Cloudflare orange** = decades-strong brand recognition, used as primary

---

## Reproducing this aesthetic — minimum viable kit

1. **Warm cream surface ladder** (`#fffbf5`, `#fef7ed`, `#fffdfb`) — never pure white as the page bg.
2. **Oxblood foreground (`#521000`)** instead of pure black for body text. This single change defines the vibe.
3. **Single brand-orange accent** (`#ff4801`) for CTAs and hairlines.
4. **Custom-feeling humanist grotesque** + premium mono. Kunst Grotesk + Apercu Mono Pro is the fingerprint; Söhne + Berkeley Mono is the closest substitute.
5. **Bracket-corner annotation pattern** for callouts and cards. Add to your component library.
6. **Semantic token names** (foreground / background / accent / ai) with light + dark values. Don't use raw color tokens at the component level.
7. **Three.js wireframe globe** as a hero centerpiece if your product is geographic — pure custom lat/lng grid (not `wireframe: true`), animated great-circle arcs.

---

## Comparison to Other Saved References

| | workers.cloudflare.com | modal.com | velvet.vc | adaline.ai | guild.ai | varickagents.com |
|---|---|---|---|---|---|---|
| Category | Edge serverless platform | AI infra cloud | Private capital network | AI agent platform | AI agent control plane | Enterprise AI ops |
| BG (light) | Warm cream `#fffbf5` | Dark `#181818` | Cream `#fbf8f3` | Olive `#f8f9f5` | Cream `#f8f6f3` | Off-white `#f8f8f8` |
| Foreground | **Oxblood `#521000`** (not black!) | White on dark | Off-black `#212322` | Deep olive | Black | Off-black `#202020` |
| Accent | **Cloudflare orange `#ff4801`** + AI green `#5eff3a` | Lime `#7fee64` | Multi-hue editorial | Olive `#4a6d47` | Orange `#ff5500` | Electric `#0099ff` |
| Display | FT Kunst Grotesk | Degular Display | Gloock (didone) | Akkurat | Suisse Neue | Bold geo sans |
| Mono | Apercu Mono Pro | Fira Mono + KaTeX | Geist Mono | fragmentMono | Geist Mono | (none) |
| Token system | Semantic (foreground/background/accent/ai with light+dark) | Named ladders + dataviz | Standard Tailwind v4 | Material 3 | Custom semantic | Framer default |
| Dark mode | **Yes (full)** | Native dark | No | No | **Yes (warm `#141413`)** | No |
| Tech | **Astro + Three.js** | SvelteKit | Next.js | Next.js + Tailwind v4 | Next.js | Framer |
| Distinguishing trick | **Region:Earth Three.js globe + oxblood text + bracket-corner annotations + warm cream** | Lime + Degular + obsessive token system + math rendering | Gloock+Calluna double-serif + couture palette | Material 3 surface tiers | Orange selection + dot grid | SVG particle wave + square CTAs |
