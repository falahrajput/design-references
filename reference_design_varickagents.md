---
name: Design Reference — varickagents.com
description: Enterprise AI ops site. Off-white #f8f8f8 background with sharp navy #10296e + electric blue #0099ff CTAs, square-edged buttons, signature SVG `<animateMotion>` particle-wave hero animation. Built in Framer. Use when referencing this aesthetic for enterprise AI infrastructure / operations consultancies.
type: reference
url: https://www.varickagents.com/
---
# varickagents.com — Full Design Reference
**URL:** https://www.varickagents.com/
**Product:** Varick Agents — custom AI implementations for enterprise (Fortune 5000)
**Tagline:** "Transform Your Enterprise With AI"
**Audience:** Operational leaders at Fortune 5000 / enterprise; finance, procurement, revenue ops, compliance teams
**Tech stack:** Framer (framerusercontent.com), Lenis smooth-scroll, custom SVG SMIL animations

---

## Aesthetic / Mood
**Sharp enterprise minimalism with a dust-of-data backdrop.** The page reads as serious B2B consultancy software — restrained off-white surfaces, blocky sans-serif headlines, generous whitespace, no gradients on copy. The signature flourish is a **pixel-particle wave animation** that flows behind the hero text like data exhaust drifting across the page. CTAs are **square-cornered solid-color tiles** (electric blue + deep navy), not pills — a deliberately blunt, "we mean business" gesture.

If guild.ai is "warm warehouse editorial" and adaline.ai is "sage/botanical," Varick is "operational gray with electric blue interrupts" — the visual equivalent of a McKinsey deck rendered by someone who actually ships software.

---

## Color Palette (extracted from page; ranked by frequency of use)

### Surfaces
| Value | Usage | Frequency |
|---|---|---|
| `#f8f8f8` / `rgb(248,248,248)` | **Page background** (off-white, slightly cooler than cream) | 206 |
| `#ffffff` | Card / inverted panels | 165 |
| `#f4f4f4` | Subtle alt surface | 2 |

### Text / neutrals
| Value | Usage |
|---|---|
| `#202020` / `rgb(32,32,32)` | Primary body text (near-black) |
| `#5f5f5f` / `rgb(95,95,95)` | Secondary / muted text |
| `#a1a1a1` | Tertiary / disabled |
| `#cccccc` | **Particle color in hero animation** (135 occurrences = the dust pixels) |
| `#d3d3d3` / `#e2e2e2` | Borders, dividers |
| `#101010` | Strongest text |
| `#000000` | True black accents |

### Brand blues (the entire accent system)
| Value | Usage |
|---|---|
| `#0099ff` / `rgb(0,153,255)` | **Electric/cyan blue** — primary "Book a Call" CTA (105 uses) |
| `#10296e` / `rgb(16,41,110)` | **Deep navy** — "Case Studies" CTA, dark surfaces (28 uses + `#10296e` token 7) |
| `#0a3eff` / `rgb(10,62,255)` | Royal/cobalt blue — links, secondary accents (92 uses) |
| `#1a65d5` | Mid-blue, hover/active states |
| `#0059ff` | Saturated CTA blue |
| `#003290` | Dark interactive blue |
| `#74a5ff` | Light blue accent / hover tint |
| `#01081b` | Near-black with blue cast — deepest dark |

**The accent system is monochromatic in blue** — no greens, oranges, yellows, or purples anywhere. This is intentional: a single hue ladder reads as more "infrastructure" than "marketing site."

---

## Typography

The HTML uses Framer's typical font loading (custom + Google Fonts). Headlines feel like a **sharp neo-grotesque** — likely Inter, Geist, or a similar Framer-default. Body is a clean sans, slightly looser tracking. The hero uses a tight headline:

> # Transform Your Enterprise With AI

With supporting body copy:
> *"Custom AI implementations tailored to your business that automate entire departments from the inside, end to end. No generalized software that only does half the job. No 18-month timelines or migrations required."*

The voice is **enterprise-confident** — no superlatives, plain English, lots of "no X / no Y" negation patterns ("No generalized software", "No 18-month timelines").

---

## Border Radius / Component Shape

Distinctive choice: **square corners on CTAs.** The two hero buttons ("Book a Call" / "Case Studies") in the screenshot are **fully rectangular** — no rounding, no pill. This is unusual in 2025 where almost every SaaS uses 8–12px+ rounded buttons. The square corners signal:
- "We're not a consumer app"
- "We're software for serious operations"

Cards may have very subtle rounding (Framer default 4–8px), but the hero CTAs are deliberately unrounded.

---

## Layout

- Page background: `#f8f8f8`
- Container max-width: standard Framer (1200px-ish)
- Hero: 2-column on desktop — left = headline + body + CTA stack, right = particle animation backdrop occupying full lower half
- Generous bottom padding under hero (the particle wave continues below the CTAs)

**Page structure (top → bottom):**
1. Nav
2. Hero — *"Transform Your Enterprise With AI"* + body + Book a Call (blue) / Case Studies (navy) CTAs + **particle wave animation backdrop**
3. Differentiator — *"We Don't Just Automate Tasks"*
4. 4-step process — Audit → Architecture → Deployment → Optimization
5. 3-pillar benefits grid — reduce overhead / accelerate execution / scale without hiring
6. Industry verticals — Finance, Procurement, Revenue Ops, Compliance
7. System integration claim — "no migrations required"
8. 3 product demos — Finance / Revenue / Logistics agent showcases
9. FAQ
10. Footer CTA + footer

---

## Signature Animation: Particle-Wave Hero (the part you asked about)

**Technique: pure SVG with `<animateMotion>`** — no canvas, no JS library, no Spline 3D.

**Anatomy of the hero SVG:**
- Single `<svg viewBox="0 0 1000 1000" preserveAspectRatio="none">` (stretches across container)
- **6 invisible `<path>`** elements describing the wave/dune curves (the "ribbons" the particles flow along)
- **138 `<circle>`** elements — small circles (`r ≈ 1.5–2`) that read as pixels at screen size
- **6 `<animateMotion>`** drivers — each circle uses `<mpath href="#waveN"/>` to follow one of the paths
- **`<filter id="pw_glow">`** with `feGaussianBlur stdDeviation="5"` + `feColorMatrix` — produces the soft halo around each pixel
- **`<linearGradient id="pw_grad">`** — silver-shine fill: `#ccc` 55%α → `#fff` 95%α → `#ccc` 70%α → `#ccc` 45%α (creates the "lit" look)
- **`<radialGradient id="pw_shine">`** — additive sparkle on hot spots
- Easing: `keySplines="0.2 0 0.2 1"` with `calcMode="spline"` — slow-fast-slow ribbon flow

**Naming convention** (`pw_grad`, `pw_shine`, `pw_glow`) → likely a Framer community component called **"Path Wave"**. If reproducing in Framer, search for that component. To build from scratch, see the recipe below.

### Reproduce-from-scratch recipe

```html
<svg viewBox="0 0 1000 1000" preserveAspectRatio="none" style="width:100%;height:100%">
  <defs>
    <filter id="glow" x="-80%" y="-80%" width="260%" height="260%">
      <feGaussianBlur stdDeviation="5" result="blur"/>
      <feColorMatrix in="blur" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 0.9 0" result="g"/>
      <feMerge><feMergeNode in="g"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <linearGradient id="fill" x1="0" y1="0" x2="1000" y2="1000" gradientUnits="userSpaceOnUse">
      <stop offset="0%"   stop-color="#ccc" stop-opacity=".55"/>
      <stop offset="35%"  stop-color="#fff" stop-opacity=".95"/>
      <stop offset="70%"  stop-color="#ccc" stop-opacity=".70"/>
      <stop offset="100%" stop-color="#ccc" stop-opacity=".45"/>
    </linearGradient>
    <path id="w1" d="M 0 600 Q 250 400 500 550 T 1000 500"/>
    <path id="w2" d="M 0 700 Q 300 500 600 650 T 1000 600"/>
    <!-- …5–7 paths total… -->
  </defs>
  <g filter="url(#glow)">
    <!-- generate ~25 circles per path with JS (random `begin`, slight `dur` variance) -->
  </g>
</svg>
```

**JS particle generator:**
```js
const PARTICLES_PER_PATH = 25;
['w1','w2','w3','w4','w5','w6'].forEach(id => {
  for (let n = 0; n < PARTICLES_PER_PATH; n++) {
    const dur = 12 + Math.random() * 6;
    const begin = -Math.random() * dur; // negative = pre-rolled, no empty start
    svgGroup.insertAdjacentHTML('beforeend', `
      <circle r="${1 + Math.random()}" fill="url(#fill)">
        <animateMotion dur="${dur}s" begin="${begin}s" repeatCount="indefinite"
          keyTimes="0;1" keySplines="0.2 0 0.2 1" calcMode="spline">
          <mpath href="#${id}"/>
        </animateMotion>
      </circle>`);
  }
});
```

**Why it looks "alive":**
1. Negative `begin` values pre-roll particles — wave is full on first paint.
2. Per-circle `dur` variance (12–18s) prevents lockstep rhythm.
3. `feGaussianBlur stdDev=5` is the entire glow — no shadows, no CSS filter.
4. Tiny `r` (1.5–2 in viewBox units) renders as 1–2px on screen, reads as "pixels."
5. 5–7 layered paths create density without one busy curve.

**CSS Motion Path alternative** (no SMIL, more browser-friendly):
```css
.particle {
  offset-path: path("M 0 600 Q 250 400 500 550 T 1000 500");
  animation: flow 14s linear infinite;
}
@keyframes flow { to { offset-distance: 100%; } }
```

---

## Component Notes

### CTAs
- **Square-cornered solid-color tiles** (no border-radius)
- Primary: `#0099ff` background, white text, ↗ arrow icon top-right
- Secondary: `#10296e` (deep navy) background, white text, same arrow icon
- Same fixed size — sit in a 2-up grid

### Cards
- White on `#f8f8f8` background
- Subtle 1px borders
- Likely 4–8px rounding (Framer default)

### Iconography
- ↗ arrows (compositional, not Lucide/Material)
- SVG illustrations for industry verticals

### Smooth scroll
- **Lenis** (`unpkg.com/lenis@1.3.15-framer.0`) — that buttery slow-scroll feel typical of premium Framer sites

---

## Brand Voice (informs design)
- *"Transform Your Enterprise With AI"*
- *"Custom AI implementations tailored to your business that automate entire departments from the inside, end to end."*
- *"No generalized software that only does half the job. No 18-month timelines or migrations required."*
- *"Enterprise operations were designed for human coordination. The next generation will be designed for intelligent execution."*

Voice patterns: **negation-heavy** ("No X. No Y. No Z."), enterprise-confident, contrast-driven (we vs. legacy SaaS / consultancies). Design echoes this with: square CTAs (refusal of consumer-app pill conventions), monochrome-blue accent system (refusal of rainbow palettes), data-dust animation (signaling "operations as data flow").

---

## Comparison to Other Saved References

| | varickagents.com | guild.ai | adaline.ai | useallowance.com | zerotoagent.com | tahahossain.com |
|---|---|---|---|---|---|---|
| Style | Enterprise ops minimalism | Warehouse editorial dev infra | AI-infra sage | iOS consumer fintech | B2B operator min | Blueprint brutalism |
| BG | Off-white `#f8f8f8` | Warm cream `#f8f6f3` + dark mode | Olive off-white `#f8f9f5` | Pure white | White | Cream `#f6f5f1` |
| Primary | Electric `#0099ff` + navy `#10296e` | Black + orange `#ff5500` | Olive `#4a6d47` | Forest `#0A7C52` | Blue/teal | None |
| Button shape | **Square corners** | 8px rounded | 8px rounded | 100px pill | Rounded | N/A |
| Animation | **SVG `animateMotion` particle wave** | Choreographed pulse hero + logo marquee | Stat counters | Chat bubble | GIF figures | None |
| Built with | Framer | Next.js custom | Next.js + Tailwind v4 | Vanilla HTML/CSS | Framer/Webflow | Webflow |
| Dark mode | No | Full | No | No | No | No |
| Distinguishing trick | **Square CTAs + pixel-particle wave hero** | Orange selection + dot-grid gradient | Material 3 surface tiers | 100px pill buttons | Custom tenex SVG icons | Hairline registration lines |
